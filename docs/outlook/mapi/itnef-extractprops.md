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
  
> [in]控制属性解码方式的标志的位掩码。 可以设置以下标志：
    
TNEF_PROP_EXCLUDE 
  
> 解码  _lpPropList_ 参数中未指定的所有属性。 
    
TNEF_PROP_INCLUDE 
  
> 解码在  _lpPropList 中指定的所有属性_。
    
 _lpPropList_
  
> [in]指向要包括在解码操作中或从解码操作中排除的属性列表的指针。
    
 _lpProblems_
  
> [out]指向返回的 [STnefProblemArray 结构的指针的](stnefproblemarray.md) 指针。 **STnefProblemArray** 结构指示哪些属性（如果有）未正确编码。 如果在  _lpProblems_ 参数中传递 NULL，则不返回任何属性问题数组。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功并返回预期值。
    
MAPI_E_CORRUPT_DATA 
  
> 解码为流的数据已损坏。
    
## <a name="remarks"></a>备注

传输提供程序、邮件存储提供程序和网关调用 **ITnef：：ExtractProps** 方法来提取 (，即从传递到 [OpenTnefStream](opentnefstream.md) 函数的邮件或附件的封装中解码) 属性。 呼叫提供商或网关可以指定要解码的属性列表。 提供程序和网关还可使用 **ExtractProps** 提供有关附件的任何特殊处理的信息。 
  
 **ExtractProps** 使用解码的属性填充传递到 **OpenTnefStream** 的原始消息。 后续 **的 ExtractProps** 调用将返回到邮件并提取新的属性列表。 
  
与 [ITnef：：AddProps](itnef-addprops.md) 方法不同，该方法在 **调用 ITnef：：Finish** 方法之前对请求的操作进行排队，而 **ExtractProps** 方法在调用它时会立即对封装的属性进行解码。 因此，封装解码的目标消息应相对空白。 目标邮件中的现有属性被封装属性覆盖。 
  
 只有使用 **OpenTnefStream 或 OpenTnefStreamEx** 函数的 TNEF_DECODE 标志打开的对象 [](opentnefstreamex.md)才支持 **ExtractProps。** 
  
TNEF 实现报告 TNEF 流编码问题，而不停止 **ExtractProps** 进程。 _lpProblems_ 中返回的 [STnefProblemArray](stnefproblemarray.md)结构指示无法处理哪些 TNEF 属性或 MAPI 属性（如果有）。 **STnefProblemArray** 中包含的 **STnefProblem** 结构之一的 **scode** 成员中返回的值指示特定问题。 提供商或网关可以假定 **ExtractProps** 未返回问题报告的所有属性或属性都已成功处理。 
  
> [!NOTE]
> 如果在 TNEF 流解码期间无法处理 MAPI 封装块中的属性，并且流不可靠，将停止封装块的解码并报告问题。 此类型的问题的问题数组包含 **ulPropTag** 成员或 `attMAPIProps` `attAttachment` **ulAttribute** 成员为 0L，而 scode 成员MAPI_E_UNABLE_TO_COMPLETE为 **0L。** 请注意，流解码不会停止，只是对 MAPI 封装块的解码。 流解码将继续处理下一个属性块。 
  
如果提供程序或网关不处理问题数组，它可以在  _lppProblems_ 中传递 NULL;在这种情况下，不会返回问题数组。 
  
_lpProblems_ 中返回的值仅在调用返回 S_OK。 返回S_OK时，提供商或网关应检查 **STnefProblemArray** 结构中返回的值。 如果呼叫出错， **则 STnefProblemArray** 结构不会填充，并且调用提供程序或网关不应使用或释放结构。 如果呼叫中未发生错误，则调用提供程序或网关必须通过调用 [MAPIFreeBuffer](mapifreebuffer.md)函数释放 **STnefProblemArray** 结构的内存。 
  
## <a name="see-also"></a>另请参阅



[ITnef::AddProps](itnef-addprops.md)
  
[ITnef::Finish](itnef-finish.md)
  
[ITnef::SetProps](itnef-setprops.md)
  
[MAPIFreeBuffer](mapifreebuffer.md)
  
[OpenTnefStream](opentnefstream.md)
  
[OpenTnefStreamEx](opentnefstreamex.md)
  
[STnefProblemArray](stnefproblemarray.md)
  
[ITnef : IUnknown](itnefiunknown.md)

