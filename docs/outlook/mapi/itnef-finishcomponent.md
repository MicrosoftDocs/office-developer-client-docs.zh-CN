---
title: ITnefFinishComponent
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- ITnef.FinishComponent
api_type:
- COM
ms.assetid: bcdd0688-0897-47d7-9601-f592ba453b39
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: c8dc10bdb8bcde15dccf7bab4d9e10d2481cef11
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33416438"
---
# <a name="itneffinishcomponent"></a>ITnef::FinishComponent

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
将邮件中的单个组件一次处理成一个Transport-Neutral封装格式 (TNEF) 流。
  
```cpp
HRESULT FinishComponent(
  ULONG ulFlags,
  ULONG ulComponentID,
  LPSPropTagArray lpCustomPropList,
  LPSPropValue lpCustomProps,
  LPSPropTagArray lpPropList,
  LPSTnefProblemArray FAR * lppProblems
);
```

## <a name="parameters"></a>参数

 _ulFlags_
  
> [in]用于控制哪些组件将完成的标记的位掩码。 必须设置以下标志之一：
    
TNEF_COMPONENT_ATTACHMENT 
  
> 将完成附件对象的处理;_ulComponentID_ 参数包含PR_ATTACH_NUM ([的 PidTagAttachNumber](pidtagattachnumber-canonical-property.md)) 属性。  
    
TNEF_COMPONENT_MESSAGE 
  
> 将完成消息对象的处理。 
    
 _ulComponentID_
  
> [in] 0 指示邮件的处理，或 **PR_ATTACH_NUM** 附件的 属性。 如果在  _ulFlags_ 参数中设置了 TNEF_COMPONENT_MESSAGE 标志，  _则 ulComponentID_ 必须为 0。 
    
 _lpCustomPropList_
  
> [in]指向 [SPropTagArray](sproptagarray.md) 结构的指针，其中包含标识在  _lpCustomProps_ 参数中传递的属性的属性标记。 _lpCustomProps_ 中每个属性值与 _lpCustomPropList_ 参数中的属性标记之间必须存在一对一的对应关系。 
    
 _lpCustomProps_
  
> [in]指向 [SPropValue](spropvalue.md) 结构的指针，其中包含要编码的属性的属性值。 
    
 _lpPropList_
  
> [in]指向 **SPropTagArray** 结构的指针，其中包含要编码的属性的属性标记。 
    
 _lppProblems_
  
> [out]指向返回的 [STnefProblemArray 结构的指针的](stnefproblemarray.md) 指针。 **STnefProblemArray** 结构指示哪些属性（如果有）未正确编码。 如果在  _lppProblems_ 参数中传递 NULL，则不返回任何属性问题数组。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功并返回了预期值。
    
## <a name="remarks"></a>备注

传输提供程序、邮件存储提供程序和网关调用 **ITnef：：FinishComponent** 方法来对一个组件（邮件或附件）执行 TNEF 处理，如  _ulFlags_ 参数中设置的标志所指示。 
  
为了启用组件处理，调用提供程序或网关在  _ulFlags_ 中为 [OpenTnefStream 或 OpenTnefStreamEx](opentnefstream.md) 函数传递 TNEF_COMPONENT_ENCODING 标志，该 [函数](opentnefstreamex.md) 打开对象以接收编码。 
  
在  _lpCustomPropList_ 和  _lpCustomProps_ 参数中传递值将执行与 [ITnef：：SetProps](itnef-setprops.md) 方法所完成的组件编码等效的组件编码。 在  _lpPropList_ 参数中传递值将执行与 [ITnef：：AddProps](itnef-addprops.md) 方法等效的组件编码，该方法在  _ulFlags_ 中设置了 TNEF_PROP_INCLUDE 标志。 通过传递这些值，可以通过单个调用（而不是多个呼叫）执行编码。
  
TNEF 实现报告 TNEF 流编码问题，而不停止 **FinishComponent** 进程。 _lppProblems_ 中返回的 **STnefProblemArray** 结构指示无法处理哪些 TNEF 属性或 MAPI 属性（如果有）。 **STnefProblemArray** 中包含的 **STnefProblem** 结构之一的 **scode** 成员中返回的值指示特定问题。 提供商或网关可以在以下假设下工作 **：FinishComponent** 未返回问题报告的所有属性或属性都已成功处理。 
  
如果提供程序或网关不处理问题数组，它可以在  _lppProblems_ 中传递 NULL;在这种情况下，不会返回问题数组。
  
_lppProblems_ 中返回的值仅在调用返回值时S_OK。 返回S_OK时，提供商或网关应检查 [STnefProblemArray](stnefproblemarray.md) 结构中返回的值。 如果呼叫出错， **则不填充 STnefProblemArray** 结构，并且调用提供程序或网关不应使用或释放结构。 如果呼叫中未发生错误，则调用提供程序或网关必须通过调用 [MAPIFreeBuffer](mapifreebuffer.md)函数释放 **STnefProblemArray** 的内存。 
  
## <a name="see-also"></a>另请参阅



[ITnef::AddProps](itnef-addprops.md)
  
[ITnef::SetProps](itnef-setprops.md)
  
[MAPIFreeBuffer](mapifreebuffer.md)
  
[OpenTnefStream](opentnefstream.md)
  
[OpenTnefStreamEx](opentnefstreamex.md)
  
[SPropTagArray](sproptagarray.md)
  
[STnefProblemArray](stnefproblemarray.md)
  
[ITnef : IUnknown](itnefiunknown.md)

