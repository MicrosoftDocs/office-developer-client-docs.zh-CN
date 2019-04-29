---
title: SOrRestriction
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.SOrRestriction
api_type:
- COM
ms.assetid: 6fee29ce-9a34-4e0c-bb71-03120c3f1117
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 9b4ca4628f356142eb5303c064e3916474810fda
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33437929"
---
# <a name="sorrestriction"></a>SOrRestriction

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
描述用于对限制应用逻辑**OR**操作的**或**限制。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |mapidefs。h  <br/> |
   
```cpp
typedef struct _SOrRestriction
{
  ULONG cRes;
  LPSRestriction lpRes;
} SOrRestriction;

```

## <a name="members"></a>Members

 **cRes**
  
> 由**lpRes**成员指向的数组中的结构计数。 
    
 **lpRes**
  
> 指向描述要使用逻辑**OR**操作联接的限制的[SRestriction](srestriction.md)结构的指针。 
    
## <a name="remarks"></a>说明

有关**SOrRestriction**结构的详细信息, 请参阅[关于限制](about-restrictions.md)。 
  
## <a name="see-also"></a>另请参阅



[SRestriction](srestriction.md)


[MAPI 结构](mapi-structures.md)

