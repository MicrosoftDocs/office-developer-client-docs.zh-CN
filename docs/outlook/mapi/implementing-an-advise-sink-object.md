---
title: 实现 Advise Sink 对象
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 7461c4f6-7030-4ba2-ada4-26ebfbbfa001
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: ecaad65d28f74b843b86ca82dab9a833ade77363
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33412105"
---
# <a name="implementing-an-advise-sink-object"></a>实现 Advise Sink 对象

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
客户端可以实施自己的建议接收器对象或使用实用工具函数 [HrAllocAdviseSink](hrallocadvisesink.md)。 **HrAllocAdviseSink** 使用调用回调函数的 **OnNotify** 实现创建建议接收器对象。 
  
使用 **HrAllocAdviseSink 有一些优缺点**。 它可以省去工作，但无法控制对它创建的通知接收对象的引用计数。 因此，需要仔细控制其建议接收器的发布或在通知接收器与另一个客户端对象之间具有依赖关系的客户应构建自己的 **IMAPIAdviseSink** 实现，并避免完全使用 **HrAllocAdviseSink。** 
  
实现自己的建议接收器的客户端应使其成为不与任何其他对象相关或依赖于任何其他对象的独立对象，以便消除引用计数和对象释放中的潜在复杂性。 但是，如果您必须将建议接收器作为另一个对象的一部分实现，或者包含指向另一个对象的返回指针作为数据成员，则建议维护两个单独的引用计数：一个针对建议接收器引用的对象，另一个针对建议接收器。 
  
当引用对象的引用计数为零时，它的所有方法可能失败，并且其 vtable 可以销毁，但通知接收器的内存必须保持不变，直到其引用计数也降为零。 这意味着，通知接收器的 **Release** 方法必须缩小其引用计数，并完成在计数达到零时销毁对象。 如果未维护两个单独的引用计数，则很容易在包含对象的发布过程中无意中销毁 **通知接收器。** 
  
使用 **HrAllocAdviseSink** 实现建议接收器的客户端必须同样小心，不要将回调函数作为方法包括在另一个建议接收器对象中。 对于 C++ 客户端，它很容易实现此要求，并作为  _参数传递此_ 指针。 这是一种危险策略，因为客户端通常在其引用计数达到零时释放对象。 释放通知接收对象的内存将使此  _指针_ 无效。 
  
根据事件类型和建议源 **，OnNotify** 方法可以通过各种方式处理事件。 下表提供了如何处理某些标准事件的建议。 
  
|**事件类型**|**在 OnNotify 中处理**|
|:-----|:-----|
|对象已移动  <br/> |如果移动对象的原始父对象与新父级相关，请从层次结构中最高的文件夹或通讯簿容器开始更新视图。 如果两个父容器不相关，请更新两个视图。  <br/> |
|新邮件  <br/> |更改用户界面以通知用户一个或多个新邮件到达。 将接收文件夹放在当前视图中。  <br/> |
|错误  <br/> |对于会话之外的所有对象，如有必要，请记录错误并返回。 对于会话对象，如果可能，请注销。  <br/> |
|搜索完成  <br/> |无需处理。  <br/> |
   
> [!NOTE]
> 通知处理程序应重新发送。 
  

