---
title: SizedSSortOrderSet
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.SizedSSortOrderSet
api_type:
- COM
ms.assetid: f0b9c2f4-7011-414d-8e6c-ab22893ef132
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 2eb92c3f1555407a77332bd6ec3b2b7202f0553f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778814"
---
# <a name="sizedssortorderset"></a>SizedSSortOrderSet

**适用于**： Outlook 
  
创建命名的[SSortOrderSet](ssortorderset.md)结构，其中包含指定的数目的排序次序。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapidefs.h  <br/> |
|相关的结构：  <br/> |**SSortOrderSet** <br/> |
   
```cpp
SizedSSortOrderSet (_csort,_name)
```

## <a name="parameters"></a>参数

__csort_
  
> 排序次序要包含的新结构中的计数。
    
__名称_
  
> 新结构的的名称。
    
## <a name="remarks"></a>说明

使用**SizedSSortOrderSet**宏来创建使用显式边界设置排序顺序。 
  
若要使用新结构的结果从**SizedSSortOrderSet**宏作为指针指向**SSortOrderSet**结构，执行下列转换： 
  
```cpp
lpSSortOrderSet = (LPSSortOrderSet) &SizedSSortOrderSet;

```

## <a name="see-also"></a>另请参阅

- [SSortOrderSet](ssortorderset.md)
- [与结构相关的宏](macros-related-to-structures.md)

