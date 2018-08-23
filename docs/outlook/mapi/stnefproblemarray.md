---
title: STnefProblemArray
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.STnefProblemArray
api_type:
- COM
ms.assetid: 115d845b-4168-4d49-b880-219ee28baa9a
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 924ddbc7c2ad1ed84ce6927ae089b6eb223bfb92
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22563504"
---
# <a name="stnefproblemarray"></a>STnefProblemArray

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
包含描述一个或多个处理的编码期间出现的问题或解码传输中性封装格式 (TNEF) 可将 stream 的**STnefProblem**结构的数组。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Tnef.h  <br/> |
   
```cpp
typedef struct _STnefProblemArray
{
  ULONG cProblem;
  STnefProblem aProblem[MAPI_DIM];
}STnefProblemArray, FAR * LPSTnefProblemArray

```

## <a name="members"></a>Members

 **cProblem**
  
> 指定在**aProblem**成员中声明的数组中的元素的计数。 
    
 **aProblem**
  
> [STnefProblem](stnefproblem.md)结构的数组。 每个结构包含有关的属性或特性处理问题的信息。 
    
## <a name="remarks"></a>注解

输出参数在[ITnef::ExtractProps](itnef-extractprops.md)方法并在每个[ITnef::Finish](itnef-finish.md)方法属性或属性处理过程中出现问题，如果收到一个指向**STnefProblemArray**结构和**ExtractProps**并**完成**每个返回 MAPI_W_ERRORS_RETURNED 的值。 此错误值指示处理过程中出现的问题和生成**STnefProblemArray**结构。 
  
如果属性或属性的处理过程中未生成**STnefProblem**结构，客户端应用程序可以继续处理属性或属性的成功假定下。 解码封装块的过程中出现问题时，发生此事件唯一的例外。 如果此解码期间发生错误，则可以作为[SCODE](scode.md)结构中返回 MAPI_E_UNABLE_TO_COMPLETE。 在这种情况下，解码阻止到相应的组件已停止，解码继续使用在另一个组件。 
  
## <a name="see-also"></a>另请参阅



[STnefProblem](stnefproblem.md)
  
[SCODE](scode.md)


[MAPI 结构](mapi-structures.md)

