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
  
完成排队和等待的所有传输中性封装格式 (TNEF) 操作的处理。 
  
```cpp
HRESULT Finish(
  ULONG ulFlags,
  WORD FAR * lpKey,
  LPSTnefProblemArray FAR * lpProblem
);
```

## <a name="parameters"></a>参数

 _ulFlags_
  
> 实时保留必须为零。
    
 _lpKey_
  
> 排除指向附件的**PR_ATTACH_NUM** ([PidTagAttachNumber](pidtagattachnumber-canonical-property.md)) 键属性的指针。 TNEF 封装对象使用此键将附件与邮件中的附件放置标记相匹配。 此键对于每个附件应是唯一的。
    
 _lpProblem_
  
> 排除指向返回的[STnefProblemArray](stnefproblemarray.md)结构的指针的指针。 **STnefProblemArray**结构指示哪些属性 (如果有) 未正确编码。 如果在_lpProblem_参数中传递 NULL, 则不返回属性问题数组。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功, 并返回了所需的一个或一些值。
    
## <a name="remarks"></a>说明

传输提供程序、邮件存储提供程序和网关调用**ITnef:: Finish**方法, 以执行在对[ITnef:: AddProps](itnef-addprops.md)和[ITnef:: SetProps](itnef-setprops.md)方法的调用中请求进行编码的所有属性的编码。 如果使用[OpenTnefStream](opentnefstream.md)或[OpenTnefStreamEx](opentnefstreamex.md)函数的 TNEF_ENCODE 标志打开 TNEF 对象, 则**完成**方法会将请求的属性编码到传递给该对象的封装流中。 如果使用 TNEF_DECODE 标志打开 tnef 对象, 则**完成**方法会对 TNEF 流中的属性进行解码, 并将其写回到其所属的邮件中。 
  
**完成**调用后, 指向封装流的指针指向 TNEF 数据的末尾。 如果提供程序或网关需要在**完成**呼叫后使用 tnef 流数据, 则必须将 stream 指针重置为 TNEF 流数据的开头。 
  
tnef 实现在不停止**完成**过程的情况下报告 TNEF 流编码问题。 在_lpProblem_参数中返回的[STnefProblemArray](stnefproblemarray.md)结构指示无法处理 TNEF 属性或 MAPI 属性 (如果有)。 在**STnefProblemArray**中包含的**STnefProblem**结构之一的**scode**成员中返回的值指出了具体的问题。 提供程序或网关可以在假定**完成**时未返回问题报告的所有属性或属性均已成功处理。 
  
如果提供程序或网关无法处理问题数组, 则它可以在_lpProblem_中传递 NULL;在这种情况下, 不会返回任何问题数组。 
  
仅当调用返回 S_OK 时, _lpProblem_中返回的值才有效。 当返回 S_OK 时, 提供程序或网关应检查**STnefProblemArray**结构中返回的值。 如果调用时出现错误, 则不会填写**STnefProblemArray**结构, 并且调用提供程序或网关不应使用或释放结构。 如果调用中没有发生错误, 则调用提供程序或网关必须通过调用[MAPIFreeBuffer](mapifreebuffer.md)函数来释放**STnefProblemArray**的内存。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|文件 .cpp  <br/> |SaveToTNEF  <br/> |MFCMAPI 使用**ITnef:: finish**方法完成对新的 TNEF 流的处理。  <br/> |
   
## <a name="see-also"></a>另请参阅



[ITnef::AddProps](itnef-addprops.md)
  
[MAPIFreeBuffer](mapifreebuffer.md)
  
[OpenTnefStream](opentnefstream.md)
  
[OpenTnefStreamEx](opentnefstreamex.md)
  
[PidTagAttachNumber 规范属性](pidtagattachnumber-canonical-property.md)
  
[STnefProblemArray](stnefproblemarray.md)
  
[ITnef : IUnknown](itnefiunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

