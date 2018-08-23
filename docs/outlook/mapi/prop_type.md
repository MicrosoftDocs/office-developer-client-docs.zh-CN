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
ms.openlocfilehash: 7bcaf230eed9cf21388b68f06ab678dc143f64ee
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22571820"
---
# <a name="proptype"></a>PROP_TYPE

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
返回指定的属性标记的属性类型。
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapidefs.h  <br/> |
|相关的结构：  <br/> |[SPropValue](spropvalue.md) <br/> |
   
```cpp
PROP_TYPE (ulPropTag)
```

## <a name="parameters"></a>参数

 _ulPropTag_
  
> 包含要返回的属性类型的属性标记。
    
## <a name="remarks"></a>注解

**PROP_TYPE**宏可以用于确定属性的类型。 例如，调用 PROP_TYPE (**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md))) 结果中 PT_BINARY 要返回的值。
  
每个属性标记包含低序位 word （0 到 15 位） 中的属性类型和高顺序单词 （通过 31 16 位） 中的属性标识符。 **PROP_TYPE**宏提取的属性类型，并将其放入位 0 到 15 的整数要返回。 返回值的剩余的位设置为零。 
  
## <a name="see-also"></a>另请参阅



[SPropValue](spropvalue.md)


[与结构相关的宏](macros-related-to-structures.md)

