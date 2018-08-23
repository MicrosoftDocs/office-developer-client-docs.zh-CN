---
title: SizedSPropProblemArray
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.SizedSPropProblemArray
api_type:
- COM
ms.assetid: 2fc3febb-8c69-4315-a112-a28eee98013d
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: bbced8412c2c3438c58af74ef072a46606b59ddc
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22594612"
---
# <a name="sizedspropproblemarray"></a>SizedSPropProblemArray

**适用于**： Outlook 2013 |Outlook 2016 
  
创建包含指定的数目的[SPropProblem](spropproblem.md)结构的命名的[SPropProblemArray](spropproblemarray.md)结构。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapidefs.h  <br/> |
|相关的结构：  <br/> |**SPropProblemArray** <br/> |
   
```cpp
SizedSPropProblemArray(_cprob, _name)
```

## <a name="parameters"></a>参数

__cprob_
  
> 要包含在新结构**SPropProblem**结构的计数。 
    
__名称_
  
> 新结构的的名称。
    
## <a name="remarks"></a>注解

使用**SizedSPropProblemArray**宏来使用显式边界创建属性问题数组。 若要使用新结构的结果从**SizedSPropProblemArray**宏作为指针指向**SPropProblemArray**结构，执行下列转换： 
  
```cpp
lpPropProbArray = (LPSPropProblemArray) &SizedSPropProblemArray;
```

## <a name="see-also"></a>另请参阅

- [SPropProblemArray](spropproblemarray.md)
- [SPropProblem](spropproblem.md)
- [与结构相关的宏](macros-related-to-structures.md)

