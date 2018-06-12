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
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: ad4b9d3f7c2ca1766ecca4fe9467fc49098f2212
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778564"
---
# <a name="propid"></a>PROP_ID

  
  
**适用于**： Outlook 
  
返回指定的属性标记属性标识符。
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapidefs.h  <br/> |
|相关的结构：  <br/> |[SPropValue](spropvalue.md) <br/> |
   
```cpp
PROP_ID (ulPropTag)
```

## <a name="parameters"></a>参数

 _ulPropTag_
  
> 包含要返回的标识符的属性标记。
    
## <a name="remarks"></a>备注

每个属性标记包含低序位 word （0 到 15 位） 中的属性类型和高顺序单词 （通过 31 16 位） 中的属性标识符。 **PROP_ID**宏提取属性标识符，并将其放入位 0 到 15 的整数要返回。 返回值的剩余的位设置为零。 
  
例如， **PROP_ID**宏可用于检索要传递给[IMAPIProp::GetNamesFromIDs](imapiprop-getnamesfromids.md)标识符。 **GetNamesFromIDs**检索与命名属性的标识符关联的属性名称。 
  
## <a name="see-also"></a>另请参阅



[SPropValue](spropvalue.md)


[与结构相关的宏](macros-related-to-structures.md)

