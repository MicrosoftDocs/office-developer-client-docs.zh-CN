---
title: ITnefExtractProps
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- ITnef.ExtractProps
api_type:
- COM
ms.assetid: 9169a5be-21dd-4938-8db3-522bea165c92
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 5a01c65bbec061248537558257c66d1a90128b5e
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33407499"
---
# <a name="itnefextractprops"></a>ITnef::ExtractProps

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
从 TNEF 封装中提取属性。 
  
```cpp
HRESULT ExtractProps(
  ULONG ulFlags,
  LPSPropTagArray lpPropList,
  LPSTnefProblemArray FAR * lpProblems
);
```

## <a name="parameters"></a>参数

 _ulFlags_
  
> 实时用于控制如何对属性进行解码的标志的位掩码。 可以设置以下标志:
    
TNEF_PROP_EXCLUDE 
  
> 对未在_lpPropList_参数中指定的所有属性进行解码。 
    
TNEF_PROP_INCLUDE 
  
> 对在_lpPropList_中指定的所有属性进行解码。
    
 _lpPropList_
  
> 实时一个指针, 指向要在解码操作中包含或排除的属性的列表。
    
 _lpProblems_
  
> 排除指向返回的[STnefProblemArray](stnefproblemarray.md)结构的指针的指针。 **STnefProblemArray**结构指示哪些属性 (如果有) 未正确编码。 如果在_lpProblems_参数中传递 NULL, 则不返回属性问题数组。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功, 并返回了所需的一个或一些值。
    
MAPI_E_CORRUPT_DATA 
  
> 解码为流的数据已损坏。
    
## <a name="remarks"></a>说明

传输提供程序、邮件存储提供程序和网关调用**ITnef:: ExtractProps**方法从传递给[OpenTnefStream](opentnefstream.md)函数的邮件或附件的封装中提取 (即解码) 属性。 调用提供程序或网关可以指定要解码的属性列表。 提供程序和网关也可以使用**ExtractProps**来提供有关附件的任何特殊处理的信息。 
  
 **ExtractProps**使用已解码的属性填充传递给**OpenTnefStream**的原始邮件。 随后的**ExtractProps**调用将返回到邮件并提取新的属性列表。 
  
与[ITnef:: AddProps](itnef-addprops.md)方法 (该方法在调用**ITnef:: Finish**方法之前对所请求的操作进行排队) 不同, **ExtractProps**方法会在调用时立即对封装的属性进行解码。 因此, 封装解码的目标邮件应相对空。 目标邮件中的现有属性将被封装属性覆盖。 
  
 仅在使用**OpenTnefStream**或[OpenTnefStreamEx](opentnefstreamex.md)函数的 TNEF_DECODE 标志打开的对象中, 才支持**ExtractProps** 。 
  
tnef 实现在不停止**ExtractProps**进程的情况下报告 TNEF 流编码问题。 _lpProblems_中返回的[STnefProblemArray](stnefproblemarray.md)结构指示无法处理 TNEF 属性或 MAPI 属性 (如果有)。 在**STnefProblemArray**中包含的**STnefProblem**结构之一的**scode**成员中返回的值指出了具体的问题。 提供程序或网关可以在假定**ExtractProps**未返回问题报告的所有属性或属性已成功处理时进行工作。 
  
> [!NOTE]
> 如果无法处理 MAPI 封装块中的某个属性, 并且在解码 TNEF 流的过程中使该流不可靠, 则会停止对封装块进行解码, 并报告问题。 此类问题的问题数组中`attMAPIProps` `attAttachment`包含**ulPropTag**成员的0L 或**ulAttribute**成员的问题, 以及**scode**成员的 MAPI_E_UNABLE_TO_COMPLETE。 请注意, 流的解码不会暂停, 只是对 MAPI 封装块进行解码。 流解码将继续进行下一个属性块。 
  
如果提供程序或网关无法处理问题数组, 则它可以在_lppProblems_中传递 NULL;在这种情况下, 不会返回任何问题数组。 
  
仅当调用返回 S_OK 时, _lpProblems_中返回的值才有效。 当返回 S_OK 时, 提供程序或网关应检查**STnefProblemArray**结构中返回的值。 如果调用时出现错误, 则不会填写**STnefProblemArray**结构, 并且调用提供程序或网关不应使用或释放结构。 如果调用中没有发生错误, 则调用提供程序或网关必须通过调用[MAPIFreeBuffer](mapifreebuffer.md)函数来释放**STnefProblemArray**结构的内存。 
  
## <a name="see-also"></a>另请参阅



[ITnef::AddProps](itnef-addprops.md)
  
[ITnef::Finish](itnef-finish.md)
  
[ITnef::SetProps](itnef-setprops.md)
  
[MAPIFreeBuffer](mapifreebuffer.md)
  
[OpenTnefStream](opentnefstream.md)
  
[OpenTnefStreamEx](opentnefstreamex.md)
  
[STnefProblemArray](stnefproblemarray.md)
  
[ITnef : IUnknown](itnefiunknown.md)

