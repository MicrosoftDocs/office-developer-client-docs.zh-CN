---
title: 实现通知接收器对象
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 7461c4f6-7030-4ba2-ada4-26ebfbbfa001
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: a95222f8ec75c519558636cf54111f28cbe14066
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775797"
---
# <a name="implementing-an-advise-sink-object"></a>实现通知接收器对象

  
  
**适用于**： Outlook 
  
客户端可以实现自己 advise 接收器对象也可以使用的实用工具函数， [HrAllocAdviseSink](hrallocadvisesink.md)。 **HrAllocAdviseSink**调用的回调函数的**OnNotify**实现用来创建 advise 接收器对象。 
  
有其优点和缺点使用**HrAllocAdviseSink**。 它可以保存的工作，但它提供无法控制它创建 advise 接收器对象进行引用计数。 因此，客户端的需要来仔细控制其通知接收器版本或具有其通知接收器和其他客户端对象之间的依赖关系的应构造自己**IMAPIAdviseSink**实现并避免使用**HrAllocAdviseSink**完全忽略。 
  
客户端实现自己通知接收器应使独立对象不相关的或依赖于以便消除潜在的问题，引用计数和对象版本中的任何其他对象。 但是，如果您必须实现通知接收器另一个对象的一部分或包括指向后向另一个对象的数据成员作为指针，它建议的维护两个单独的引用计数： 一个用于通知接收器，另一个用于所引用的对象建议接收器。 
  
当引用的对象的引用计数降为零时，所有其方法可能会失败和可以销毁其 vtable，但通知接收器的内存必须保持不变，直到后引用计数还会为零。 这意味着通知接收器**释放**方法必须引用计数递减并完成时的计数为零时销毁的对象。 如果两个单独的引用计数不会被保留，它可以轻松地无意大对象的**发布**过程的一部分销毁通知接收器。 
  
使用**HrAllocAdviseSink**来实现通知接收器的客户端必须同样不要将其回调函数为在另一个 advise 接收器对象的方法。 对于 c + + 客户端，它很容易执行此操作，并作为参数传递_此_指针。 这是危险策略，因为客户端通常释放对象，当其引用计数为零时。 释放 advise 接收器对象的内存，将会呈现_this_指针无效。 
  
根据事件和 advise 源类型， **OnNotify**方法可以处理事件以各种方式。 下表提供了建议中如何处理的某些标准事件。 
  
|**事件的类型**|**在 OnNotify 处理**|
|:-----|:-----|
|移动对象  <br/> |如果移动的对象的原始父与新父级，更新文件夹或通讯簿容器层次结构中最高视图开头。 如果两个父容器无关，更新这两个其视图。  <br/> |
|新的邮件  <br/> |更改通知的一个或多个新邮件到达用户的用户界面。 当前视图中放置的接收文件夹。  <br/> |
|错误  <br/> |对于除会话的所有对象，如果必要和返回记录错误。 对于会话对象中，先注销如果可能。  <br/> |
|搜索完成  <br/> |没有必要的处理。  <br/> |
   
> [!NOTE]
> 应重入通知处理程序。 
  

