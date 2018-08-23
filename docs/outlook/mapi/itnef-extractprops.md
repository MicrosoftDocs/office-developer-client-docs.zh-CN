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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 0765e46a6f0545682b16e484d08d296ea13e2136
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22571344"
---
# <a name="itnefextractprops"></a>ITnef::ExtractProps

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
从 TNEF 封装提取属性。 
  
```cpp
HRESULT ExtractProps(
  ULONG ulFlags,
  LPSPropTagArray lpPropList,
  LPSTnefProblemArray FAR * lpProblems
);
```

## <a name="parameters"></a>参数

 _ulFlags_
  
> [in]位掩码的标志，控制如何能够解码属性。 可以设置以下标志：
    
TNEF_PROP_EXCLUDE 
  
> 解码未在_lpPropList_参数中指定的所有属性。 
    
TNEF_PROP_INCLUDE 
  
> 解码_lpPropList_中指定的所有属性。
    
 _lpPropList_
  
> [in]一个指向属性中包含或排除解码操作的列表。
    
 _lpProblems_
  
> [输出]指向返回[STnefProblemArray](stnefproblemarray.md)结构指针的指针。 **STnefProblemArray**结构表明哪些属性中，如果有，已未编码的正确。 如果_lpProblems_参数中传递了 NULL，则返回没有属性问题数组。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 呼叫成功，并返回预期的值。
    
MAPI_E_CORRUPT_DATA 
  
> 正在为流解码的数据已损坏。
    
## <a name="remarks"></a>注解

传输提供程序、 消息存储提供程序，和网关调用**ITnef::ExtractProps**方法以提取 （即，解码） 从邮件或附件已传递给[OpenTnefStream](opentnefstream.md)函数封装的属性。 呼叫提供商或网关可以指定要解码属性的列表。 提供程序和网关还可以使用**ExtractProps**提供信息的附件的任何特殊处理。 
  
 **ExtractProps**填充原始邮件传递到**OpenTnefStream**具有已解码的属性。 后续**ExtractProps**调用返回到邮件并提取的属性的新列表。 
  
与[ITnef::AddProps](itnef-addprops.md)方法，调用**ITnef::Finish**方法之前，队列将请求操作，不同**ExtractProps**方法在被调用时立即解码封装的属性。 因此，用于封装解码的目标消息应为相对空。 通过封装属性来覆盖目标邮件中的现有属性。 
  
 **ExtractProps**仅支持使用 TNEF_DECODE 标志**OpenTnefStream**或[OpenTnefStreamEx](opentnefstreamex.md)函数打开的对象。 
  
TNEF 实现报告而不停止**ExtractProps**进程 TNEF 流编码问题。 返回在_lpProblems_ [STnefProblemArray](stnefproblemarray.md)结构指示哪些 TNEF 属性或 MAPI 属性，如果有，无法进行处理。 在**STnefProblemArray**中包含的**STnefProblem**结构之一的**scode**成员中返回的值指示特定问题。 所有属性或特性**ExtractProps**不会返回问题报告都已成功都处理假定可以处理提供程序或网关。 
  
> [!NOTE]
> 如果 MAPI 封装块中的属性不能处理，并保持流解码 TNEF 流过程不可靠，解码封装块的已停止并报告问题。 此类型的问题的问题数组包含 0 L **ulPropTag**成员，`attMAPIProps`或`attAttachment` **ulAttribute**成员和 MAPI_E_UNABLE_TO_COMPLETE **scode**成员。 请注意，流的解码不停止，只需解码的 MAPI 封装块。 流解码继续下一个属性块。 
  
如果提供程序或网关不适用于问题数组，它可以在_lppProblems_; 传递 NULL在这种情况下，则返回没有问题数组。 
  
仅当呼叫，则返回 S_OK 有效_lpProblems_中返回的值。 返回 S_OK 时，提供程序或网关应检查**STnefProblemArray**结构中返回的值。 如果在调用出错， **STnefProblemArray**结构未填写并调用提供程序或网关不应使用或释放结构。 如果在调用不产生任何错误，呼叫提供商或网关必须通过调用[MAPIFreeBuffer](mapifreebuffer.md)函数释放**STnefProblemArray**结构的内存。 
  
## <a name="see-also"></a>另请参阅



[ITnef::AddProps](itnef-addprops.md)
  
[ITnef::Finish](itnef-finish.md)
  
[ITnef::SetProps](itnef-setprops.md)
  
[MAPIFreeBuffer](mapifreebuffer.md)
  
[OpenTnefStream](opentnefstream.md)
  
[OpenTnefStreamEx](opentnefstreamex.md)
  
[STnefProblemArray](stnefproblemarray.md)
  
[ITnef : IUnknown](itnefiunknown.md)

