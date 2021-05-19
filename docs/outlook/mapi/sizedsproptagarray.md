---
title: SizedSPropTagArray
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.SizedSPropTagArray
api_type:
- COM
ms.assetid: 1d2dc6e9-735d-4b5b-af6f-adf6a32a666d
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: f873ad5234460f9f1781c7427b60d285f7486196
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33429346"
---
# <a name="sizedsproptagarray"></a>SizedSPropTagArray

**适用于**：Outlook 2013 | Outlook 2016 
  
创建一个名为 [SPropTagArray](sproptagarray.md) 的结构，其中包含指定数量的属性标记。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapidefs.h  <br/> |
|相关结构：  <br/> |**SPropTagArray** <br/> |
   
```cpp
SizedSPropTagArray (_ctag, _name)
```

## <a name="parameters"></a>参数

_ _ctag_
  
> 要包含在新结构中的属性标记的计数。
    
_ _name_
  
> 新结构的名称。
    
## <a name="remarks"></a>备注

使用 **SizedSPropTagArray** 宏创建具有显式边界的属性标记数组。 
  
若要使用由 **SizedSPropTagArray** 宏产生的新结构作为 **指向 SPropTagArray** 结构的指针，请执行以下转换： 
  
```cpp
lpPropTagArray = (LPPropTagArray) &SizedSPropTagArray;

```

## <a name="see-also"></a>另请参阅

- [SPropTagArray](sproptagarray.md)
- [与结构相关的宏](macros-related-to-structures.md)

