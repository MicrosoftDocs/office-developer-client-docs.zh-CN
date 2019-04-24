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
ms.openlocfilehash: 38263f46ccb50e1836f31d457f54f52abca7ce9f
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32357517"
---
# <a name="sbinary"></a>SBinary

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
描述类型 PT_BINARY 的属性。
  
|||
|:-----|:-----|
|标头文件：  <br/> |mapidefs。h  <br/> |
   
```cpp
typedef struct _SBinary
{
  ULONG      cb;
  LPBYTE     lpb;
} SBinary, FAR *LPSBinary;

```

## <a name="members"></a>Members

 **cb**
  
> **lpb**成员中的字节数。 
    
 **lpb**
  
> 指向 PT_BINARY 属性值的指针。
    
## <a name="remarks"></a>注解

有关属性类型的信息, 请参阅[MAPI 属性类型概述](mapi-property-type-overview.md)。
  
## <a name="see-also"></a>另请参阅



[SPropValue](spropvalue.md)


[MAPI 结构](mapi-structures.md)

