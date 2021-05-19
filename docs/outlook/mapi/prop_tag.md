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
# <a name="prop_tag"></a>PROP_TAG

**适用于**：Outlook 2013 | Outlook 2016 
  
返回通过组合指定的属性类型和标识符创建的属性标记。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapidefs.h  <br/> |
|相关结构：  <br/> |[SPropValue](spropvalue.md) <br/> |
   
```cpp
PROP_TAG (ulPropType, ulPropID)
```

## <a name="parameters"></a>参数

_ulPropType_
  
> 新属性标记的属性类型。
    
_ulPropID_
  
> 新属性标记的属性标识符。
    
## <a name="remarks"></a>备注

**PROP \_ TAG** 宏为 _ulPropType_ 类型的属性和 _ulPropID_ 中指定的标识符创建属性标记。 例如，可以使用以下宏创建条目标识符 **PROP_TAG标记：** 
  
```cpp
PROP_TAG( PT_BINARY, 0x0FFF)

```

返回的属性标记的低顺序 16 位包含属性类型 PT_BINARY，高顺序 16 位包含属性标识符 0xFFFF。
  
有关属性标记详细信息，请参阅 [MAPI Property Tags](mapi-property-tags.md)。
  
## <a name="see-also"></a>另请参阅

- [SPropValue](spropvalue.md)
- [与结构相关的宏](macros-related-to-structures.md)

