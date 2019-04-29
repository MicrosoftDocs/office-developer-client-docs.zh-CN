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
# <a name="mviprop"></a>MVI_PROP

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
设置指定属性的 MVI_FLAG。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |mapidefs。h  <br/> |
|相关结构:  <br/> |[SPropValue](spropvalue.md) <br/> |
   
```cpp
MVI_PROP (tag)
```

## <a name="parameters"></a>参数

 _tag_
  
> 要修改的属性标记。
    
## <a name="remarks"></a>说明

MVI_FLAG 结合了 MV_FLAG 的设置、将属性标识为多值和 MV_INSTANCE, 请求多值属性以多行的形式显示在表中。 将修改受影响的属性的属性类型, 但标识符保持不变。 
  
例如, 将 MVI_PROP 宏应用于 PT_FLOAT 类型的属性时, 其类型将更改为 PT_MV_FLOAT。 包含在表中时, 多行用于表示每个值具有一行的属性。 其他列的属性重复。 
  
有关这些标志的详细信息, 请参阅[MAPI 属性类型概述](mapi-property-type-overview.md)和使用[多值列](working-with-multivalued-columns.md)。
  
## <a name="see-also"></a>另请参阅



[SPropValue](spropvalue.md)


[与结构相关的宏](macros-related-to-structures.md)

