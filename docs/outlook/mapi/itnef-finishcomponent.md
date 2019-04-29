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
  
将邮件中的单个组件一次性处理为非特定传输封装格式 (TNEF) 流。
  
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
  
> 实时用于控制要完成的组件的标志的位掩码。 必须设置以下一个或多个标志:
    
TNEF_COMPONENT_ATTACHMENT 
  
> 将完成对附件对象的处理;_ulComponentID_参数包含附件的**PR_ATTACH_NUM** ([PidTagAttachNumber](pidtagattachnumber-canonical-property.md)) 属性。 
    
TNEF_COMPONENT_MESSAGE 
  
> 将完成对 message 对象的处理。 
    
 _ulComponentID_
  
> [输入] 0 指示对邮件的处理, 或要处理的附件的**PR_ATTACH_NUM**属性。 如果在_ulFlags_参数中设置了 TNEF_COMPONENT_MESSAGE 标志, 则_ulComponentID_必须为0。 
    
 _lpCustomPropList_
  
> 实时指向[SPropTagArray](sproptagarray.md)结构的指针, 该结构包含用于标识在_lpCustomProps_参数中传递的属性的属性标记。 _lpCustomProps_中的每个属性值与_lpCustomPropList_参数中的一个属性标记之间必须有一对一的对应关系。 
    
 _lpCustomProps_
  
> 实时指向[SPropValue](spropvalue.md)结构的指针, 该结构包含要编码的属性的属性值。 
    
 _lpPropList_
  
> 实时指向**SPropTagArray**结构的指针, 该结构包含要编码的属性的属性标记。 
    
 _lppProblems_
  
> 排除指向返回的[STnefProblemArray](stnefproblemarray.md)结构的指针的指针。 **STnefProblemArray**结构指示哪些属性 (如果有) 未正确编码。 如果在_lppProblems_参数中传递 NULL, 则不返回属性问题数组。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功, 并返回了所需的值或值。
    
## <a name="remarks"></a>说明

传输提供程序、邮件存储提供程序和网关调用**ITnef:: FinishComponent**方法, 以执行一个组件 (由_ulFlags_参数中设置的标志所指示) 的 TNEF 处理 (无论是邮件还是附件)。 
  
若要启用组件处理, 调用提供程序或网关在_ulFlags_中传递打开要接收编码的对象的[OpenTnefStream](opentnefstream.md)或[OpenTnefStreamEx](opentnefstreamex.md)函数的 TNEF_COMPONENT_ENCODING 标志。 
  
传递_lpCustomPropList_和_lpCustomProps_参数中的值会执行与[ITnef:: SetProps](itnef-setprops.md)方法所执行的组件编码等效的组件编码。 传递_lpPropList_参数中的值会执行与 ulFlags:: AddProps 方法中的[ITnef::](itnef-addprops.md)方法所做的操作等效的组件编码, 并在__ 中设置 TNEF_PROP_INCLUDE 标志。 通过传递这些值, 可以执行单个调用 (而不是多个调用) 执行编码。
  
tnef 实现在不停止**FinishComponent**进程的情况下报告 TNEF 流编码问题。 _lppProblems_中返回的**STnefProblemArray**结构指示无法处理 TNEF 属性或 MAPI 属性 (如果有)。 在**STnefProblemArray**中包含的**STnefProblem**结构之一的**scode**成员中返回的值指出了具体的问题。 提供程序或网关可以在假定**FinishComponent**未返回问题报告的所有属性或属性已成功处理时进行工作。 
  
如果提供程序或网关无法处理问题数组, 则它可以在_lppProblems_中传递 NULL;在这种情况下, 不会返回任何问题数组。
  
仅当调用返回 S_OK 时, _lppProblems_中返回的值才有效。 当返回 S_OK 时, 提供程序或网关应检查[STnefProblemArray](stnefproblemarray.md)结构中返回的值。 如果调用时出现错误, 则不会填写**STnefProblemArray**结构, 并且调用提供程序或网关不应使用或释放结构。 如果调用中没有发生错误, 则调用提供程序或网关必须通过调用[MAPIFreeBuffer](mapifreebuffer.md)函数来释放**STnefProblemArray**的内存。 
  
## <a name="see-also"></a>另请参阅



[ITnef::AddProps](itnef-addprops.md)
  
[ITnef::SetProps](itnef-setprops.md)
  
[MAPIFreeBuffer](mapifreebuffer.md)
  
[OpenTnefStream](opentnefstream.md)
  
[OpenTnefStreamEx](opentnefstreamex.md)
  
[SPropTagArray](sproptagarray.md)
  
[STnefProblemArray](stnefproblemarray.md)
  
[ITnef : IUnknown](itnefiunknown.md)

