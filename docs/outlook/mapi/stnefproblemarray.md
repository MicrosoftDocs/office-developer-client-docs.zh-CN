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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32336496"
---
# <a name="stnefproblemarray"></a>STnefProblemArray

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含描述在编码或解码传输中性封装格式 (TNEF) 流的过程中发生的一个或多个处理问题的**STnefProblem**结构数组。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Tnef  <br/> |
   
```cpp
typedef struct _STnefProblemArray
{
  ULONG cProblem;
  STnefProblem aProblem[MAPI_DIM];
}STnefProblemArray, FAR * LPSTnefProblemArray

```

## <a name="members"></a>Members

 **cProblem**
  
> **aProblem**成员中指定的数组中的元素数。 
    
 **aProblem**
  
> [STnefProblem](stnefproblem.md)结构的数组。 每个结构都包含有关属性或属性处理问题的信息。 
    
## <a name="remarks"></a>注解

如果在属性或属性处理过程中出现问题, 则[ITnef:: ExtractProps](itnef-extractprops.md)方法和[ITnef:: Finish](itnef-finish.md)方法中的 output 参数都会收到指向**STnefProblemArray**结构和 ExtractProps 的指针**** 并**完成**每个返回值 MAPI_W_ERRORS_RETURNED。 此错误值指示在处理过程中出现问题并生成**STnefProblemArray**结构。 
  
如果在处理属性或属性的过程中不会生成**STnefProblem**结构, 则在假定该属性或属性的处理成功的情况下, 客户端应用程序可以继续。 仅当在封装块解码过程中出现问题时, 才会发生此异常。 如果在此解码过程中出现错误, 则 MAPI_E_UNABLE_TO_COMPLETE 可以作为[SCODE](scode.md)在结构中返回。 在这种情况下, 将停止对与块相对应的组件进行解码, 并在另一个组件中继续解码。 
  
## <a name="see-also"></a>另请参阅



[STnefProblem](stnefproblem.md)
  
[SCODE](scode.md)


[MAPI 结构](mapi-structures.md)

