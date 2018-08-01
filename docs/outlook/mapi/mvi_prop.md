---
title: MVI_PROP
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.MVI_PROP
api_type:
- COM
ms.assetid: d7f07524-6935-4a60-aaf3-3f753ea8d86a
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: f8f58ee18095dec8a222ae8b5a19cbefbaafa663
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776556"
---
# <a name="mviprop"></a>MVI_PROP

  
  
**适用于**： Outlook 
  
设置指定属性 MVI_FLAG。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapidefs.h  <br/> |
|相关的结构：  <br/> |[SPropValue](spropvalue.md) <br/> |
   
```cpp
MVI_PROP (tag)
```

## <a name="parameters"></a>参数

 _标记_
  
> 要修改的属性标记。
    
## <a name="remarks"></a>说明

MVI_FLAG 结合使用的 MV_FLAG，标识为多个值的属性和 MV_INSTANCE，请求的表中多行显示多值的属性的设置。 修改受影响的属性的属性类型，但标识符保持不变。 
  
例如，当 MVI_PROP 宏应用于 PT_FLOAT 类型的属性，其类型更改为 PT_MV_FLOAT。 当包括在表中，多个行用于表示具有一行，每个值的属性。 重复其他列的属性。 
  
有关这些标志的详细信息，请参阅[MAPI 属性类型概述](mapi-property-type-overview.md)和[使用多值列](working-with-multivalued-columns.md)。
  
## <a name="see-also"></a>另请参阅



[SPropValue](spropvalue.md)


[与结构相关的宏](macros-related-to-structures.md)

