---
title: PROP_TAG
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PROP_TAG
api_type:
- COM
ms.assetid: d8c9d18c-4043-41f3-8501-8be8e3a2c9ac
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 7ab4e4e9e51849037a91a071f16294cfdf10870c
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33425881"
---
# <a name="proptag"></a>PROP_TAG

**适用于**：Outlook 2013 | Outlook 2016 
  
返回通过组合指定的属性类型和标识符而创建的属性标记。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |mapidefs。h  <br/> |
|相关结构:  <br/> |[SPropValue](spropvalue.md) <br/> |
   
```cpp
PROP_TAG (ulPropType, ulPropID)
```

## <a name="parameters"></a>参数

_ulPropType_
  
> 新属性标记的属性类型。
    
_ulPropID_
  
> 新属性标记的属性标识符。
    
## <a name="remarks"></a>说明

属性**\_标记**宏为类型为_ulPropType_的属性创建属性标记以及在_ulPropID_中指定的标识符。 例如, 可以使用**PROP_TAG**宏创建条目标识符的属性标记, 如下所示: 
  
```cpp
PROP_TAG( PT_BINARY, 0x0FFF)

```

返回的属性标记的低位16位包含属性类型、PT_BINARY 和高序位16位包含属性标识符0xffff。
  
有关属性标记的详细信息, 请参阅[MAPI 属性标记](mapi-property-tags.md)。
  
## <a name="see-also"></a>另请参阅

- [SPropValue](spropvalue.md)
- [与结构相关的宏](macros-related-to-structures.md)

