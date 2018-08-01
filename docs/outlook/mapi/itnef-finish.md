---
title: ITnefFinish
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- ITnef.Finish
api_type:
- COM
ms.assetid: 01a868f4-afda-43ba-bc17-c33ae56b7b7d
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 2b95e0dd62d83dd83a064ee4627811fcb24af921
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776113"
---
# <a name="itneffinish"></a>ITnef::Finish

  
  
**适用于**： Outlook 
  
处理排队的所有传输中性封装格式 (TNEF) 操作和等待完成。 
  
```cpp
HRESULT Finish(
  ULONG ulFlags,
  WORD FAR * lpKey,
  LPSTnefProblemArray FAR * lpProblem
);
```

## <a name="parameters"></a>参数

 _ulFlags_
  
> [in]保留;必须为零。
    
 _lpKey_
  
> [输出]一个指向附件的**PR_ATTACH_NUM** ([PidTagAttachNumber](pidtagattachnumber-canonical-property.md)) 关键属性。 TNEF 封装对象使用此项匹配附件的邮件及其附件放置标记。 此参数应是唯一的每个附件。
    
 _lpProblem_
  
> [输出]指向返回[STnefProblemArray](stnefproblemarray.md)结构指针的指针。 **STnefProblemArray**结构表明哪些属性中，如果有，已未编码的正确。 如果_lpProblem_参数中传递了 NULL，则返回没有属性问题数组。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 呼叫成功，并返回预期的值。
    
## <a name="remarks"></a>说明

传输提供程序、 消息存储提供程序，和网关呼叫给[ITnef::AddProps](itnef-addprops.md)和[ITnef::SetProps](itnef-setprops.md)方法的调用中请求的**ITnef::Finish**方法执行的编码的所有属性的都编码。 如果 TNEF 对象已打开了 TNEF_ENCODE 标记[OpenTnefStream](opentnefstream.md)或[OpenTnefStreamEx](opentnefstreamex.md)函数中，**完成**方法将编码为传递到该对象的封装流请求的属性。 如果 TNEF 对象已打开了 TNEF_DECODE 标记，**完成**方法解码 TNEF 流中的属性，并将它们写回其所属的消息。 
  
在**完成**调用后，该指针指向封装流指向 TNEF 数据的末尾。 如果提供程序或网关需要**完成**呼叫后，请使用 TNEF 流数据，它必须重流指针置到 TNEF 流数据的开头。 
  
TNEF 实现报告而不停止**完成**进程 TNEF 流编码问题。 返回_lpProblem_参数中的[STnefProblemArray](stnefproblemarray.md)结构指示哪些 TNEF 属性或 MAPI 属性，如果有，无法进行处理。 在**STnefProblemArray**中包含的**STnefProblem**结构之一的**scode**成员中返回的值指示特定问题。 所有属性或特性为其**完成**不会返回问题报告都已成功都处理假定可以处理提供程序或网关。 
  
如果提供程序或网关不适用于问题数组，它可以在_lpProblem_; 传递 NULL在这种情况下，则返回没有问题数组。 
  
仅当呼叫，则返回 S_OK 有效_lpProblem_中返回的值。 返回 S_OK 时，提供程序或网关应检查**STnefProblemArray**结构中返回的值。 如果在调用出错， **STnefProblemArray**结构未填写并调用提供程序或网关不应使用或释放结构。 如果在调用不产生任何错误，呼叫提供商或网关必须释放内存的**STnefProblemArray**通过调用[MAPIFreeBuffer](mapifreebuffer.md)函数。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 参考 （英文）

MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**Comment**|
|:-----|:-----|:-----|
|File.cpp  <br/> |SaveToTNEF  <br/> |MFCMAPI 使用**ITnef::Finish**方法完成在新的 TNEF 流处理。  <br/> |
   
## <a name="see-also"></a>另请参阅



[ITnef::AddProps](itnef-addprops.md)
  
[MAPIFreeBuffer](mapifreebuffer.md)
  
[OpenTnefStream](opentnefstream.md)
  
[OpenTnefStreamEx](opentnefstreamex.md)
  
[PidTagAttachNumber 规范属性](pidtagattachnumber-canonical-property.md)
  
[STnefProblemArray](stnefproblemarray.md)
  
[ITnef : IUnknown](itnefiunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

