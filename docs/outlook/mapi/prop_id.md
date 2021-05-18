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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33409130"
---
# <a name="prop_id"></a>PROP_ID

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
返回指定属性标记的属性标识符。
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapidefs.h  <br/> |
|相关结构：  <br/> |[SPropValue](spropvalue.md) <br/> |
   
```cpp
PROP_ID (ulPropTag)
```

## <a name="parameters"></a>参数

 _ulPropTag_
  
> 包含要返回的标识符的属性标记。
    
## <a name="remarks"></a>备注

每个属性标记都包含低顺序单词 (位 0 到 15) 中的属性类型，高顺序单词的属性标识符 (位 16 到 31) 。 该 **PROP_ID** 宏提取属性标识符，并将它放在要返回的整数的位 0 到 15 中。 返回值的剩余位设置为零。 
  
例如 **PROP_ID，** 该宏可用于检索要传递给 [IMAPIProp：：GetNamesFromIDs](imapiprop-getnamesfromids.md)的标识符。 **GetNamesFromIDs** 检索与命名属性的标识符关联的属性名称。 
  
## <a name="see-also"></a>另请参阅



[SPropValue](spropvalue.md)


[与结构相关的宏](macros-related-to-structures.md)

