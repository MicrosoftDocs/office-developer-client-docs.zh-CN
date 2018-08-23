---
title: SCurrencyArray
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.SCurrencyArray
api_type:
- COM
ms.assetid: d28852ab-b542-40e1-b2ec-85d20a2eddfd
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 1b262ba9c83e9890719f716a373c566be172ae73
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22572450"
---
# <a name="scurrencyarray"></a>SCurrencyArray

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
包含用于描述 PT_MV_CURRENCY 类型的属性的货币值的数组。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapidefs.h  <br/> |
   
```cpp
typedef struct _SCurrencyArray
{
  ULONG         cValues;
  CURRENCY FAR *lpcur;
} SCurrencyArray;

```

## <a name="members"></a>Members

 **cValues**
  
> 由**lpcur**成员指向数组中的值的数目。 
    
 **lpcur**
  
> 指向的[货币](currency.md)结构包含货币值的数组。 
    
## <a name="remarks"></a>注解

有关 PT_MV_CURRENCY 的信息，请参阅[列表的属性类型](property-types.md)。 
  
## <a name="see-also"></a>另请参阅



[CURRENCY](currency.md)
  
[SPropValue](spropvalue.md)


[MAPI 结构](mapi-structures.md)

