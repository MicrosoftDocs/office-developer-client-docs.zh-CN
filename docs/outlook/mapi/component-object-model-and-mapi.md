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
ms.openlocfilehash: cf687a7bfadb0981ca3440c2f81bc5de8f910924
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774689"
---
# <a name="component-object-model-and-mapi"></a>组件对象模型和 MAPI

  
  
**适用于**： Outlook 
  
Windows SDK 文档中包含的规则实现符合到组件对象模型 (COM) 的对象的全面讨论。 这些规则地址如何执行下列操作：
  
- 设计接口和对象。
    
- 实现[IUnknown](http://msdn.microsoft.com/en-us/library/ms680509%28VS.85%29.aspx)接口。 
    
- 管理内存。
    
- 处理引用计数。
    
- 实现单元线程对象。
    
虽然所有 MAPI 对象都视为基于 COM，这是因为它们实现继承[IUnknown](http://msdn.microsoft.com/en-us/library/ms680509%28VS.85%29.aspx)接口，MAPI 偏离在某些情况下，从标准 COM 的规则。 此偏差使开发人员在其实现更大的灵活性。 例如，任何 COM 接口，类似的 MAPI 界面介绍之间实施和呼叫者的合同。 后的接口是创建和发布，其定义无法，并且不会更改。 MAPI 不偏离此说明，但它 ア ネ 较解除说明。 实施者可以选择不实现特定方法，调用方返回下列错误值之一： 
  
- MAPI_E_NO_SUPPORT
    
- MAPI_E_TOO_COMPLEX
    
- MAPI_E_BAD_CHARWIDTH
    
- MAPI_E_TYPE_NO_SUPPORT
    
标准的 COM 规则其他流入下表所述。
  
|**COM 编程规则**|**MAPI 变体**|
|:-----|:-----|
|接口方法中的所有字符串参数应都为 Unicode。  <br/> |MAPI 接口定义允许 Unicode 或 ANSI 字符串参数。 具有字符串参数的许多方法还具有**ulFlags**参数;由中**ulFlags**MAPI_UNICODE 标志的值指示字符串参数的宽度。 一些 MAPI 接口不支持 Unicode，并返回 MAPI_E_BAD_CHARWIDTH 时设置 MAPI_UNICODE 标志。  <br/> |
|所有接口方法应都具有 HRESULT 返回的类型。  <br/> |MAPI 具有至少一个返回非 HRESULT 值的方法： [IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md)。  <br/> |
|呼叫者和实施者应分配并使用标准的 COM 任务分配器释放内存接口参数。  <br/> |所有 MAPI 方法都使用链接的分配器[MAPIAllocateBuffer](mapiallocatebuffer.md)、 [MAPIAllocateMore](mapiallocatemore.md)和[MAPIFreeBuffer](mapifreebuffer.md)管理接口参数的内存。 所有 MAPI 实现的接口定义的 OLE，如[IStream](http://msdn.microsoft.com/en-us/library/aa380034%28VS.85%29.aspx)，都使用标准的 COM 任务分配器。  <br/> |
|所有出指针参数必须明确设置为 NULL 时方法将失败。  <br/> |MAPI 接口要求的 out 指针参数设置为 NULL 或保持不变，当方法时将失败。 所有 MAPI 实现的接口定义 OLE 显式设置出故障参数为 NULL。  <br/> |
|实现尽可能可聚合的对象。  <br/> |MAPI 接口不可聚合。  <br/> |
   
## <a name="see-also"></a>另请参阅



[MAPIAllocateBuffer](mapiallocatebuffer.md)
  
[MAPIAllocateMore](mapiallocatemore.md)
  
[MAPIFreeBuffer](mapifreebuffer.md)


[MAPI 对象和接口概述](mapi-object-and-interface-overview.md)

