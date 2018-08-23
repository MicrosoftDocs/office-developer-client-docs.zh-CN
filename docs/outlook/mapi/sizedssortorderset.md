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
ms.openlocfilehash: 7622baaebf6918cf84c48e53291cf5ec2c0b1a4a
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22572562"
---
# <a name="sizedssortorderset"></a>SizedSSortOrderSet

**适用于**： Outlook 2013 |Outlook 2016 
  
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
    
## <a name="remarks"></a>注解

使用**SizedSSortOrderSet**宏来创建使用显式边界设置排序顺序。 
  
若要使用新结构的结果从**SizedSSortOrderSet**宏作为指针指向**SSortOrderSet**结构，执行下列转换： 
  
```cpp
lpSSortOrderSet = (LPSSortOrderSet) &SizedSSortOrderSet;

```

## <a name="see-also"></a>另请参阅

- [SSortOrderSet](ssortorderset.md)
- [与结构相关的宏](macros-related-to-structures.md)

