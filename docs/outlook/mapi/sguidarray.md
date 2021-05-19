---
title: SGuidArray
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.SGuidArray
api_type:
- COM
ms.assetid: 2091e5fc-75c8-4ea4-87e9-a9bf508e9c58
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 3d20a0932de0fb29ea73e56c37e262c0ccd062c3
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33424922"
---
# <a name="sguidarray"></a>SGuidArray

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含一个 [GUID](guid.md) 结构数组，用于描述类型为 PT_MV_CLSID。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapidefs.h  <br/> |
   
```cpp
typedef struct _SGuidArray
{
  ULONG cValues;
  GUID FAR *lpguid;
} SGuidArray;

```

## <a name="members"></a>Members

 **cValues**
  
> **lpguid** 成员指向的数组中的值计数。 
    
 **lpguid**
  
> 指向包含类标识符值的 **GUID** 结构的数组的指针。 
    
## <a name="remarks"></a>备注

有关属性类型PT_MV_CLSID，请参阅 [属性类型列表](property-types.md)。
  
## <a name="see-also"></a>另请参阅



[GUID](guid.md)
  
[SPropValue](spropvalue.md)


[MAPI 结构](mapi-structures.md)

