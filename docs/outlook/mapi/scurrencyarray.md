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
ms.openlocfilehash: e9468d0c7fc7e46475afe19f12f225e53196639e
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32360695"
---
# <a name="scurrencyarray"></a>SCurrencyArray

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含用于描述类型为 PT_MV_CURRENCY 的属性的货币值数组。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |mapidefs。h  <br/> |
   
```cpp
typedef struct _SCurrencyArray
{
  ULONG         cValues;
  CURRENCY FAR *lpcur;
} SCurrencyArray;

```

## <a name="members"></a>Members

 **cValues**
  
> 由**lpcur**成员指向的数组中的值的计数。 
    
 **lpcur**
  
> 指向包含货币值的[货币](currency.md)结构数组的指针。 
    
## <a name="remarks"></a>注解

有关 PT_MV_CURRENCY 的信息, 请参阅[属性类型列表](property-types.md)。 
  
## <a name="see-also"></a>另请参阅



[CURRENCY](currency.md)
  
[SPropValue](spropvalue.md)


[MAPI 结构](mapi-structures.md)

