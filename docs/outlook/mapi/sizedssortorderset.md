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
ms.openlocfilehash: 60a335f85eea8778580e0bd74693a5c28591103c
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32282626"
---
# <a name="sizedssortorderset"></a>SizedSSortOrderSet

**适用于**：Outlook 2013 | Outlook 2016 
  
创建一个包含指定数量的排序次序的命名[SSortOrderSet](ssortorderset.md)结构。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |mapidefs。h  <br/> |
|相关结构:  <br/> |**SSortOrderSet** <br/> |
   
```cpp
SizedSSortOrderSet (_csort,_name)
```

## <a name="parameters"></a>参数

__csort_
  
> 要包含在新结构中的排序顺序的计数。
    
__名称_
  
> 新结构的名称。
    
## <a name="remarks"></a>注解

使用**SizedSSortOrderSet**宏创建具有显式边界的排序次序集。 
  
若要使用作为指向**SSortOrderSet**结构的指针的**SizedSSortOrderSet**宏生成的新结构, 请执行以下转换: 
  
```cpp
lpSSortOrderSet = (LPSSortOrderSet) &SizedSSortOrderSet;

```

## <a name="see-also"></a>另请参阅

- [SSortOrderSet](ssortorderset.md)
- [与结构相关的宏](macros-related-to-structures.md)

