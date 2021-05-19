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
ms.openlocfilehash: b3818e5e1429c7e2b7d5f7533db733ba29e672c8
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33418111"
---
# <a name="sizedspropproblemarray"></a>SizedSPropProblemArray

**适用于**：Outlook 2013 | Outlook 2016 
  
创建一个名为 [SPropProblemArray](spropproblemarray.md) 的结构，其中包含指定数量的 [SPropProblem](spropproblem.md) 结构。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapidefs.h  <br/> |
|相关结构：  <br/> |**SPropProblemArray** <br/> |
   
```cpp
SizedSPropProblemArray(_cprob, _name)
```

## <a name="parameters"></a>参数

_ _cprob_
  
> 要包含在新结构中的 **SPropProblem** 结构计数。 
    
_ _name_
  
> 新结构的名称。
    
## <a name="remarks"></a>备注

使用 **SizedSPropProblemArray** 宏创建具有显式边界的属性问题数组。 若要使用由 **SizedSPropProblemArray** 宏产生的新结构作为 **指向 SPropProblemArray** 结构的指针，请执行以下转换： 
  
```cpp
lpPropProbArray = (LPSPropProblemArray) &SizedSPropProblemArray;
```

## <a name="see-also"></a>另请参阅

- [SPropProblemArray](spropproblemarray.md)
- [SPropProblem](spropproblem.md)
- [与结构相关的宏](macros-related-to-structures.md)

