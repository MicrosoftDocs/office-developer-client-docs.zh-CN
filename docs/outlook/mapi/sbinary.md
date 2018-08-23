---
title: SBinary
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.SBinary
api_type:
- COM
ms.assetid: f21b5e6c-7a63-46bf-acbf-0e042e3519f7
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: f54ef96443e5c9fc5fb587f5a9c25388c1ff9cdb
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22577420"
---
# <a name="sbinary"></a>SBinary

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
介绍 PT_BINARY 类型的属性。
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapidefs.h  <br/> |
   
```cpp
typedef struct _SBinary
{
  ULONG      cb;
  LPBYTE     lpb;
} SBinary, FAR *LPSBinary;

```

## <a name="members"></a>Members

 **cb**
  
> **Lpb**成员中的字节数。 
    
 **lpb**
  
> 指向 PT_BINARY 属性值的指针。
    
## <a name="remarks"></a>注解

属性类型有关的信息，请参阅[MAPI 属性类型概述](mapi-property-type-overview.md)。
  
## <a name="see-also"></a>另请参阅



[SPropValue](spropvalue.md)


[MAPI 结构](mapi-structures.md)

