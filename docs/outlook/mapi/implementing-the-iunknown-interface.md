---
title: 实现 IUnknown 接口
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 01bba63b-a2a1-490e-8b78-5c9ba8d9547b
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 5165476ea131e40153191e8625af5ea3c49f47b1
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32310043"
---
# <a name="implementing-the-iunknown-interface"></a>实现 IUnknown 接口

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
[IUnknown](https://msdn.microsoft.com/library/ms680509%28v=VS.85%29.aspx)接口的方法（在每种 MAPI 对象中实现）支持对象间通信和对象管理。 
  
 **IUnknown** 有三种方法 [：IUnknown：：AddRef、IUnknown：：QueryInterface](https://msdn.microsoft.com/library/ms691379%28v=VS.85%29.aspx)和 [IUnknown：：Release](https://msdn.microsoft.com/library/ms682317%28v=VS.85%29.aspx)。 [](https://msdn.microsoft.com/library/ms682521%28v=VS.85%29.aspx) **QueryInterface** 使一个对象可以确定另一个对象是否支持特定接口。 使用 **QueryInterface，** 之前对彼此的功能没有了解的两个对象可以交互。 如果实现 **QueryInterface** 的对象确实支持该接口，它将返回一个指向该接口的实现指针。 如果对象不支持请求的接口，它将返回MAPI_E_INTERFACE_NOT_SUPPORTED值。 
  
当 **QueryInterface** 返回请求的接口指针时，它还必须增加新对象的引用计数。 对象的引用计数是一个数值，用于管理对象生命期。 当引用计数大于 1 时，无法释放对象的内存，因为它被主动使用。 只有当引用计数下降为 0 时，对象才能安全释放。 
  
其他两个 **IUnknown** 方法 **AddRef** 和 **Release** 管理引用计数。 **AddRef** 增加引用计数，而 **Release** 会缩小引用计数。 返回接口指针的所有方法或 API 函数（如 **QueryInterface）** 都必须调用 **AddRef** 来增加引用计数。 接收接口指针的方法的所有实现都必须调用 **Release，** 以在不再需要指针时减计数。 **释放** 检查现有引用计数，仅在计数为 0 时释放与接口关联的内存。 
  
> [!NOTE]
> 由于 **AddRef** 和 **Release** 不需要返回准确的值，因此这些方法的调用方不得使用返回值来确定对象是否仍然有效或已被销毁。 
  
## <a name="see-also"></a>另请参阅



[实现 MAPI 对象](implementing-mapi-objects.md)

