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
ms.openlocfilehash: 5b76f9daec89e9229fc7f81e1332c3075c951067
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33435675"
---
# <a name="itneffinish"></a>ITnef::Finish

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
完成 TNEF 中Transport-Neutral和 (TNEF) 封装格式的处理。 
  
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
  
> [out]指向附件PR_ATTACH_NUM ( [PidTagAttachNumber](pidtagattachnumber-canonical-property.md)) 键属性的指针。 TNEF 封装对象使用此键将附件与邮件中的附件放置标记相匹配。 此键应对于每个附件是唯一的。
    
 _lpProblem_
  
> [out]指向返回的 [STnefProblemArray 结构的指针的](stnefproblemarray.md) 指针。 **STnefProblemArray** 结构指示哪些属性（如果有）未正确编码。 如果在  _lpProblem_ 参数中传递 NULL，则不返回任何属性问题数组。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功并返回预期值。
    
## <a name="remarks"></a>备注

传输提供程序、邮件存储提供程序和网关调用 **ITnef：：Finish** 方法，以执行对 [ITnef：：AddProps](itnef-addprops.md) 和 [ITnef：：SetProps](itnef-setprops.md) 方法的调用中请求编码的所有属性的编码。 如果 TNEF 对象是使用 [OpenTnefStream 或 OpenTnefStreamEx](opentnefstream.md)函数的 TNEF_ENCODE 标志打开的，**则 Finish** 方法将请求的属性编码为传递给该对象的封装流。 [](opentnefstreamex.md) 如果 TNEF 对象是使用 TNEF_DECODE 标志打开的 **，Finish** 方法将解码 TNEF 流中的属性，并写回它们所属的消息。 
  
完成 **调用** 后，指向封装流的指针指向 TNEF 数据的末尾。 如果提供商或网关需要在 **Finish** 调用后使用 TNEF 流数据，则必须将流指针重置为 TNEF 流数据的开头。 
  
TNEF 实现报告 TNEF 流编码问题，而不停止 **Finish** 过程。 _lpProblem_ 参数中返回的 [STnefProblemArray](stnefproblemarray.md)结构指示无法处理哪些 TNEF 属性或 MAPI 属性（如果有）。 **STnefProblemArray** 中包含的 **STnefProblem** 结构之一的 **scode** 成员中返回的值指示特定问题。 提供商或网关可以基于以下假设工作 **：Finish** 不返回问题报告的所有属性或属性都已成功处理。 
  
如果提供程序或网关不处理问题数组，它可以在  _lpProblem_ 中传递 NULL;在这种情况下，不会返回问题数组。 
  
_lpProblem_ 中返回的值仅在调用返回值时S_OK。 返回S_OK时，提供商或网关应检查 **STnefProblemArray** 结构中返回的值。 如果呼叫出错， **则 STnefProblemArray** 结构不会填充，并且调用提供程序或网关不应使用或释放结构。 如果呼叫中未发生错误，则调用提供程序或网关必须通过调用 [MAPIFreeBuffer](mapifreebuffer.md)函数释放 **STnefProblemArray** 的内存。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|File.cpp  <br/> |SaveToTNEF  <br/> |MFCMAPI 使用 **ITnef：：Finish** 方法完成新 TNEF 流的处理。  <br/> |
   
## <a name="see-also"></a>另请参阅



[ITnef::AddProps](itnef-addprops.md)
  
[MAPIFreeBuffer](mapifreebuffer.md)
  
[OpenTnefStream](opentnefstream.md)
  
[OpenTnefStreamEx](opentnefstreamex.md)
  
[PidTagAttachNumber 规范属性](pidtagattachnumber-canonical-property.md)
  
[STnefProblemArray](stnefproblemarray.md)
  
[ITnef : IUnknown](itnefiunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

