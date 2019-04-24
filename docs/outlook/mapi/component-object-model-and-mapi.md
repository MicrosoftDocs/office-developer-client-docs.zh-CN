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
  
Windows SDK 文档包含有关实现符合组件对象模型 (COM) 的对象的规则的全面讨论。 这些规则解决了如何执行以下操作:
  
- 设计接口和对象。
    
- 实现[IUnknown](https://msdn.microsoft.com/library/ms680509%28VS.85%29.aspx)接口。 
    
- 管理内存。
    
- 处理引用计数。
    
- 实现单元线程对象。
    
尽管所有 MAPI 对象都是基于 COM 的, 因为它们实现从[IUnknown](https://msdn.microsoft.com/library/ms680509%28VS.85%29.aspx)继承的接口, 而 mapi 在某些情况下与标准 COM 规则发生了偏离。 通过这种差异, 开发者可以更灵活地实现其实现。 例如, MAPI 接口 (如任何 COM 接口) 描述实施者和调用方之间的合约。 创建并发布接口后, 其定义无法且不会更改。 MAPI 并不偏离此说明, 但在某些情况下 relaxes 说明。 实施者可以选择不实现特定的方法, 并将以下错误值之一返回给调用程序: 
  
- MAPI_E_NO_SUPPORT
    
- MAPI_E_TOO_COMPLEX
    
- MAPI_E_BAD_CHARWIDTH
    
- MAPI_E_TYPE_NO_SUPPORT
    
下表介绍了与标准 COM 规则的其他偏差。
  
|**COM 编程规则**|**MAPI 变体**|
|:-----|:-----|
|接口方法中的所有字符串参数都应为 Unicode。  <br/> |MAPI 接口定义为允许 Unicode 或 ANSI 字符串参数。 具有 string 参数的许多方法也具有**ulFlags**参数;字符串参数的宽度由**ulFlags**中的 MAPI_UNICODE 标志的值指示。 某些 MAPI 接口不支持 Unicode, 并在设置 MAPI_UNICODE 标志时返回 MAPI_E_BAD_CHARWIDTH。  <br/> |
|所有接口方法应具有 HRESULT 的返回类型。  <br/> |MAPI 至少有一个返回非 HRESULT 值的方法: [IMAPIAdviseSink:: OnNotify](imapiadvisesink-onnotify.md)。  <br/> |
|调用方和实现者应使用标准的 COM 任务 allocators 为接口参数分配和释放内存。  <br/> |所有 MAPI 方法均使用链接的 allocators [MAPIAllocateBuffer](mapiallocatebuffer.md)、 [MAPIAllocateMore](mapiallocatemore.md)和[MAPIFreeBuffer](mapifreebuffer.md)来管理接口参数的内存。 所有由 OLE 定义的接口的 MAPI 实现 (如[IStream](https://msdn.microsoft.com/library/aa380034%28VS.85%29.aspx)) 使用标准的 COM 任务 allocators。  <br/> |
|当方法失败时, 所有 out 指针参数都必须显式设置为 NULL。  <br/> |MAPI 接口要求输出的指针参数设置为 NULL 或在方法失败时保持不变。 通过 OLE 定义的所有 MAPI 接口实现都会在失败时显式将参数设置为 NULL。  <br/> |
|尽可能实现可聚合对象。  <br/> |MAPI 接口不可聚合。  <br/> |
   
## <a name="see-also"></a>另请参阅



[MAPIAllocateBuffer](mapiallocatebuffer.md)
  
[MAPIAllocateMore](mapiallocatemore.md)
  
[MAPIFreeBuffer](mapifreebuffer.md)


[MAPI 对象和接口概述](mapi-object-and-interface-overview.md)

