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
ms.openlocfilehash: 3fd61828cd631c4abc0131da867ca213a3c44d20
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778866"
---
# <a name="spropproblemarray"></a>SPropProblemArray

  
  
**适用于**： Outlook 
  
包含一个或多个[SPropProblem](spropproblem.md)结构的数组。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapidefs.h  <br/> |
|相关的宏：  <br/> |[CbNewSPropProblemArray](cbnewspropproblemarray.md) <br/> [CbSPropProblemArray](cbspropproblemarray.md) <br/> [SizedSPropProblemArray](sizedspropproblemarray.md) <br/> |
   
```cpp
typedef struct _SPropProblemArray
{
  ULONG cProblem;
  SPropProblem aProblem[MAPI_DIM];
} SPropProblemArray, FAR *LPSPropProblemArray;

```

## <a name="members"></a>Members

 **cProblem**
  
> [SPropProblem](spropproblem.md)结构由**aProblem**成员数组中的计数。 
    
 **aProblem**
  
> 每个描述属性错误的**SPropProblem**结构数组。 
    
## <a name="remarks"></a>说明

有关的**SPropProblem**和**SPropProblemArray**结构有属性相关的错误的工作原理的详细信息，请参阅[MAPI 命名属性](mapi-named-properties.md)。 
  
## <a name="see-also"></a>另请参阅



[SCODE](scode.md)
  
[SPropProblem](spropproblem.md)


[MAPI 结构](mapi-structures.md)

