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
ms.openlocfilehash: 054625601b496a8ec8f7745aa4cbc4715eed81a7
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22585057"
---
# <a name="sorrestriction"></a>SOrRestriction

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
描述用来限制应用于逻辑**OR**运算**或**限制。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapidefs.h  <br/> |
   
```cpp
typedef struct _SOrRestriction
{
  ULONG cRes;
  LPSRestriction lpRes;
} SOrRestriction;

```

## <a name="members"></a>Members

 **cRes**
  
> 由**lpRes**成员指向计数的数组中的结构。 
    
 **lpRes**
  
> 指向描述要使用逻辑**或**运算联接的限制的[SRestriction](srestriction.md)结构。 
    
## <a name="remarks"></a>注解

有关**SOrRestriction**结构的详细信息，请参阅[有关限制](about-restrictions.md)。 
  
## <a name="see-also"></a>另请参阅



[SRestriction](srestriction.md)


[MAPI 结构](mapi-structures.md)

