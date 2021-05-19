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
ms.openlocfilehash: 087d38face72e1e067350b1959b37313ebbd7c44
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33410677"
---
# <a name="mvi_prop"></a>MVI_PROP

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
设置MVI_FLAG属性的属性值。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapidefs.h  <br/> |
|相关结构：  <br/> |[SPropValue](spropvalue.md) <br/> |
   
```cpp
MVI_PROP (tag)
```

## <a name="parameters"></a>参数

 _tag_
  
> 要修改的属性标记。
    
## <a name="remarks"></a>备注

该MVI_FLAG组合了 MV_FLAG 设置，将属性标识为多值属性和 MV_INSTANCE，并请求多值属性显示在多行的表中。 修改受影响属性的属性类型，但标识符保持不变。 
  
例如，当MVI_PROP宏应用于 PT_FLOAT 类型的属性时，其类型将更改为 PT_MV_FLOAT。 当包含在表中时，多行用于表示每个值具有一行的属性。 其他列的属性是重复的。 
  
有关这些标志的信息，请参阅 [MAPI 属性类型概述](mapi-property-type-overview.md) 和 [处理多值列](working-with-multivalued-columns.md)。
  
## <a name="see-also"></a>另请参阅



[SPropValue](spropvalue.md)


[与结构相关的宏](macros-related-to-structures.md)

