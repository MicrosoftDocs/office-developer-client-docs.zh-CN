---
title: SNotRestriction
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.SNotRestriction
api_type:
- COM
ms.assetid: e86ca032-d973-4b79-976e-5240ab38a0da
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 174da93e7682246565b12c4fc4ffa6d1a9de065c
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22575061"
---
# <a name="snotrestriction"></a>SNotRestriction

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
介绍**不**限制，用来将逻辑**NOT**操作应用于限制。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapidefs.h  <br/> |
   
```cpp
typedef struct _SNotRestriction
{
  ULONG ulReserved;
  LPSRestriction lpRes;
} SNotRestriction;

```

## <a name="members"></a>Members

 **ulReserved**
  
> [in]保留;必须为零。
    
 **lpRes**
  
> 指向[SRestriction](srestriction.md)结构，描述要加入到逻辑**NOT**运算符的限制。 
    
## <a name="remarks"></a>注解

有关**SNotRestriction**结构的详细信息，请参阅[有关限制](about-restrictions.md)。 
  
## <a name="see-also"></a>另请参阅



[SRestriction](srestriction.md)


[MAPI 结构](mapi-structures.md)

