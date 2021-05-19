---
title: 组件对象模型和 MAPI
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: cca4c70d-b73a-4834-80b5-9cb5889f63cc
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: a91ab8497a690fd4b99f76274d0213284253fd06
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32334466"
---
# <a name="component-object-model-and-mapi"></a>组件对象模型和 MAPI

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
此Windows SDK 文档包含有关实现符合 COM 组件对象模型组件模型 (对象的) 。 这些规则将解决如何执行以下操作：
  
- 设计接口和对象。
    
- 实现 [IUnknown](https://msdn.microsoft.com/library/ms680509%28VS.85%29.aspx) 接口。 
    
- 管理内存。
    
- 处理引用计数。
    
- 实现单元线程对象。
    
尽管所有 MAPI 对象都被视为基于 COM，因为它们实现从 [IUnknown](https://msdn.microsoft.com/library/ms680509%28VS.85%29.aspx)继承的接口，但在某些情况下 MAPI 偏离标准 COM 规则。 此偏差允许开发人员更灵活地实现。 例如，MAPI 接口（如任何 COM 接口）描述了实现者与调用方之间的协定。 创建和发布接口后，其定义将不能且不会更改。 MAPI 不会偏离此说明，但它稍微缓解了该说明。 实现者可以选择不实现特定方法，同时向调用方返回以下错误值之一： 
  
- MAPI_E_NO_SUPPORT
    
- MAPI_E_TOO_COMPLEX
    
- MAPI_E_BAD_CHARWIDTH
    
- MAPI_E_TYPE_NO_SUPPORT
    
下表介绍了与标准 COM 规则的其他偏差。
  
|**COM 编程规则**|**MAPI 变体**|
|:-----|:-----|
|接口方法中所有字符串参数应为 Unicode。  <br/> |MAPI 接口定义为允许 Unicode 或 ANSI 字符串参数。 具有字符串参数的许多方法也具有 **ulFlags** 参数;字符串参数的宽度由 **ulFlags** 中 MAPI_UNICODE 标记的值指示。 有些 MAPI 接口不支持 Unicode，在设置 MAPI_E_BAD_CHARWIDTH 标志MAPI_UNICODE返回 Unicode。  <br/> |
|所有接口方法都应具有 HRESULT 的返回类型。  <br/> |MAPI 至少有一个返回非 HRESULT 值的方法 [：IMAPIAdviseSink：：OnNotify](imapiadvisesink-onnotify.md)。  <br/> |
|调用方和实施者应该使用标准 COM 任务分配器为接口参数分配和释放内存。  <br/> |所有 MAPI 方法都使用链接的分配器[MAPIAllocateBuffer、MAPIAllocateMore](mapiallocatebuffer.md)和[MAPIFreeBuffer](mapifreebuffer.md)来管理接口参数的内存。 [](mapiallocatemore.md) 所有由 OLE 定义的接口的 MAPI 实现（如 [IStream）](https://msdn.microsoft.com/library/aa380034%28VS.85%29.aspx)都使用标准 COM 任务分配器。  <br/> |
|方法失败时，必须将所有 out 指针参数显式设置为 NULL。  <br/> |MAPI 接口要求将指针参数设置为 NULL，或在方法失败时保持不变。 所有由 OLE 定义的接口的 MAPI 实现在出现故障时显式将参数设置为 NULL。  <br/> |
|尽可能实现可聚合对象。  <br/> |MAPI 接口不可聚合。  <br/> |
   
## <a name="see-also"></a>另请参阅



[MAPIAllocateBuffer](mapiallocatebuffer.md)
  
[MAPIAllocateMore](mapiallocatemore.md)
  
[MAPIFreeBuffer](mapifreebuffer.md)


[MAPI 对象和接口概述](mapi-object-and-interface-overview.md)

