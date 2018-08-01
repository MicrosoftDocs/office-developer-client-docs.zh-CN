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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 7008549111f1b914cf2025c8d61ebc07196706fb
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776104"
---
# <a name="itneffinishcomponent"></a>ITnef::FinishComponent

  
  
**适用于**： Outlook 
  
到传输中性封装格式 (TNEF) stream 一次处理从一个一条消息的各个组件。
  
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
  
> [in]将完成控制哪些组件的标志位掩码。 必须设置一个或多个以下标志：
    
TNEF_COMPONENT_ATTACHMENT 
  
> 处理将完成的 attachment 对象;_ulComponentID_参数包含附件的**PR_ATTACH_NUM** ([PidTagAttachNumber](pidtagattachnumber-canonical-property.md)) 属性。 
    
TNEF_COMPONENT_MESSAGE 
  
> 处理将完成的消息对象中。 
    
 _ulComponentID_
  
> [in] 0，以指示一条消息，或附件的**PR_ATTACH_NUM**属性处理的处理。 如果_ulFlags_参数中设置 TNEF_COMPONENT_MESSAGE 标志， _ulComponentID_必须为 0。 
    
 _lpCustomPropList_
  
> [in]一个指向[SPropTagArray](sproptagarray.md)结构，其中包含属性标记来标识_lpCustomProps_参数中传递的属性。 必须有一一对应_lpCustomProps_中的每个属性值与_lpCustomPropList_参数中的属性标记之间。 
    
 _lpCustomProps_
  
> [in]一个指向[SPropValue](spropvalue.md)结构，其中包含要编码的属性的属性值。 
    
 _lpPropList_
  
> [in]指向**SPropTagArray**结构，其中包含要编码的属性的属性标记的指针。 
    
 _lppProblems_
  
> [输出]指向返回[STnefProblemArray](stnefproblemarray.md)结构指针的指针。 **STnefProblemArray**结构表明哪些属性中，如果有，已未编码的正确。 如果_lppProblems_参数中传递了 NULL，则返回没有属性问题数组。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 呼叫成功或多个预期值返回。
    
## <a name="remarks"></a>说明

传输提供程序、 消息存储提供程序，和网关呼叫**ITnef::FinishComponent**方法执行 TNEF 处理的一个组件，一条消息或附件，如标志所指示的_ulFlags_参数中设置。 
  
若要启用的组件处理，呼叫提供商或网关 TNEF_COMPONENT_ENCODING 标志中传递_ulFlags_ [OpenTnefStream](opentnefstream.md)或[OpenTnefStreamEx](opentnefstreamex.md)函数打开要接收编码的对象。 
  
在_lpCustomPropList_和_lpCustomProps_参数中传递值执行组件编码等价于[ITnef::SetProps](itnef-setprops.md)方法执行的。 _LpPropList_参数中传递值执行组件编码等效项以的[ITnef::AddProps](itnef-addprops.md)方法通过_ulFlags_中设置 TNEF_PROP_INCLUDE 标志。 将这些值传递使您可以执行而不是多个呼叫的单个调用进行编码。
  
TNEF 实现报告而不停止**FinishComponent**进程 TNEF 流编码问题。 返回在_lppProblems_ **STnefProblemArray**结构指示哪些 TNEF 属性或 MAPI 属性，如果有，无法进行处理。 在**STnefProblemArray**中包含的**STnefProblem**结构之一的**scode**成员中返回的值指示特定问题。 所有属性或特性**FinishComponent**不会返回问题报告都已成功都处理假定可以处理提供程序或网关。 
  
如果提供程序或网关不适用于问题数组，它可以在_lppProblems_; 传递 NULL在这种情况下，则返回没有问题数组。
  
仅当呼叫，则返回 S_OK 有效_lppProblems_中返回的值。 返回 S_OK 时，提供程序或网关应检查[STnefProblemArray](stnefproblemarray.md)结构中返回的值。 如果调用时出现错误，不填写**STnefProblemArray**结构，并且呼叫提供商或网关不应使用或释放结构。 如果在调用不产生任何错误，呼叫提供商或网关必须释放内存的**STnefProblemArray**通过调用[MAPIFreeBuffer](mapifreebuffer.md)函数。 
  
## <a name="see-also"></a>另请参阅



[ITnef::AddProps](itnef-addprops.md)
  
[ITnef::SetProps](itnef-setprops.md)
  
[MAPIFreeBuffer](mapifreebuffer.md)
  
[OpenTnefStream](opentnefstream.md)
  
[OpenTnefStreamEx](opentnefstreamex.md)
  
[SPropTagArray](sproptagarray.md)
  
[STnefProblemArray](stnefproblemarray.md)
  
[ITnef : IUnknown](itnefiunknown.md)

