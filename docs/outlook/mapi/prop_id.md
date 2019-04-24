---
title: PROP_ID
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PROP_ID
api_type:
- COM
ms.assetid: 6ddaced5-49bb-41fe-95da-4e3300883bf7
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 228ea91969b35a1608dd6b3378b751312aa9c665
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32328572"
---
# <a name="propid"></a>PROP_ID

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
返回指定的属性标记的属性标识符。
  
|||
|:-----|:-----|
|标头文件：  <br/> |mapidefs。h  <br/> |
|相关结构:  <br/> |[SPropValue](spropvalue.md) <br/> |
   
```cpp
PROP_ID (ulPropTag)
```

## <a name="parameters"></a>参数

 _ulPropTag_
  
> 包含要返回的标识符的属性标记。
    
## <a name="remarks"></a>注解

每个属性标记都包含低序位字 (0 到 15) 中的属性类型和高序位字 (位16到 31) 中的属性标识符。 **PROP_ID**宏提取属性标识符, 并将其放在要返回的整数的0到15位。 返回值的剩余位设置为零。 
  
例如, 可以使用**PROP_ID**宏检索要传递给[IMAPIProp:: GetNamesFromIDs](imapiprop-getnamesfromids.md)的标识符。 **GetNamesFromIDs**检索与命名属性的标识符关联的属性名称。 
  
## <a name="see-also"></a>另请参阅



[SPropValue](spropvalue.md)


[与结构相关的宏](macros-related-to-structures.md)

