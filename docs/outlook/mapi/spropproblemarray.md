---
title: SPropProblemArray
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.SPropProblemArray
api_type:
- COM
ms.assetid: 3fbaa77a-be43-4fce-af67-1826ee101799
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: f78e0ed939e190a9855ea4b040d18c01cfecc91d
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32357839"
---
# <a name="spropproblemarray"></a>SPropProblemArray

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含一个或多个[SPropProblem](spropproblem.md)结构的数组。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |mapidefs。h  <br/> |
|相关宏:  <br/> |[CbNewSPropProblemArray](cbnewspropproblemarray.md) <br/> [CbSPropProblemArray](cbspropproblemarray.md) <br/> [SizedSPropProblemArray](sizedspropproblemarray.md) <br/> |
   
```cpp
typedef struct _SPropProblemArray
{
  ULONG cProblem;
  SPropProblem aProblem[MAPI_DIM];
} SPropProblemArray, FAR *LPSPropProblemArray;

```

## <a name="members"></a>Members

 **cProblem**
  
> 由**aProblem**成员指示的数组中的[SPropProblem](spropproblem.md)结构的计数。 
    
 **aProblem**
  
> **SPropProblem**结构的数组, 每个结构描述属性错误。 
    
## <a name="remarks"></a>注解

有关**SPropProblem**和**SPropProblemArray**结构如何处理与属性相关的错误的详细信息, 请参阅[MAPI 命名属性](mapi-named-properties.md)。 
  
## <a name="see-also"></a>另请参阅



[SCODE](scode.md)
  
[SPropProblem](spropproblem.md)


[MAPI 结构](mapi-structures.md)

