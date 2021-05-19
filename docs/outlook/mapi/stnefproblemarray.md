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
ms.openlocfilehash: 721b14f101e87299f654507f94d4a957f905cac1
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33434261"
---
# <a name="stnefproblemarray"></a>STnefProblemArray

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含一个 **STnefProblem** 结构数组，该数组描述在 TNEF 流中对传输中性封装格式 (进行编码或解码期间发生的一个或多个) 问题。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Tnef.h  <br/> |
   
```cpp
typedef struct _STnefProblemArray
{
  ULONG cProblem;
  STnefProblem aProblem[MAPI_DIM];
}STnefProblemArray, FAR * LPSTnefProblemArray

```

## <a name="members"></a>Members

 **cProblem**
  
> 在problem 成员中指定的 **数组中的元素** 计数。 
    
 **aProblem**
  
> [STnefProblem 结构](stnefproblem.md)数组。 每个结构都包含有关属性或属性处理问题的信息。 
    
## <a name="remarks"></a>备注

如果在属性或属性处理过程中出现问题， [则 ITnef：：ExtractProps](itnef-extractprops.md) 方法和 [ITnef：：Finish](itnef-finish.md) 方法中的输出参数各自会收到一个指向 **STnefProblemArray** 结构的指针 **，ExtractProps** 和 **Finish** 各自返回值 MAPI_W_ERRORS_RETURNED。 此错误值指示处理过程中出现问题，并生成 **STnefProblemArray** 结构。 
  
如果在处理属性或属性期间未生成 **STnefProblem** 结构，则客户端应用程序可以在该属性或属性处理成功的假设下继续。 唯一的异常是在解码封装块期间出现问题时发生。 如果在此解码过程中发生错误，MAPI_E_UNABLE_TO_COMPLETE返回为[结构中的 SCODE。](scode.md) 在这种情况下，将停止与块对应的组件解码，并且在另一个组件中继续解码。 
  
## <a name="see-also"></a>另请参阅



[STnefProblem](stnefproblem.md)
  
[SCODE](scode.md)


[MAPI 结构](mapi-structures.md)

