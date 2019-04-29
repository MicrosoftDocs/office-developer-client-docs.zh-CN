---
title: PROP_TYPE
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PROP_TYPE
api_type:
- COM
ms.assetid: 746d63fa-bfb7-479f-94dc-ba40011c1ec9
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 0c33633c4decd697cf241f8b7c27360f776a1ade
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33412833"
---
# <a name="proptype"></a>PROP_TYPE

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
返回指定的属性标记的属性类型。
  
|||
|:-----|:-----|
|标头文件：  <br/> |mapidefs。h  <br/> |
|相关结构:  <br/> |[SPropValue](spropvalue.md) <br/> |
   
```cpp
PROP_TYPE (ulPropTag)
```

## <a name="parameters"></a>参数

 _ulPropTag_
  
> 包含要返回的属性类型的属性标记。
    
## <a name="remarks"></a>说明

**PROP_TYPE**宏可用于确定属性的类型。 例如, 调用 PROP_TYPE (**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md))) 会导致返回 PT_BINARY 值。
  
每个属性标记都包含低序位字 (0 到 15) 中的属性类型和高序位字 (位16到 31) 中的属性标识符。 **PROP_TYPE**宏提取属性类型, 并将其放在要返回的整数的0到15位。 返回值的剩余位设置为零。 
  
## <a name="see-also"></a>另请参阅



[SPropValue](spropvalue.md)


[与结构相关的宏](macros-related-to-structures.md)

