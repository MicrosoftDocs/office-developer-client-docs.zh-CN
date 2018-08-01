---
title: FLATMTSIDLIST
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.FLATMTSIDLIST
api_type:
- COM
ms.assetid: b66c2815-72bc-4535-b34c-899bb830f29e
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: ea841ef4bc551581fb2d9ca90201b4615e67f134
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774944"
---
# <a name="flatmtsidlist"></a>FLATMTSIDLIST

  
  
**适用于**： Outlook 
  
包含[MTSID](mtsid.md)结构，其中每个包含 X.400 邮件传输系统 (MTS) 条目标识符数组。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapidefs.h  <br/> |
|相关的宏：  <br/> |[CbFLATMTSIDLIST](cbflatmtsidlist.md) [CbNewFLATMTSIDLIST](cbnewflatmtsidlist.md) <br/> |
   
```cpp
typedef struct
{
  ULONG cMTSIDs;
  ULONG cbMTSIDs;
  BYTE abMTSIDs[MAPI_DIM];
} FLATMTSIDLIST, FAR *LPFLATMTSIDLIST;

```

## <a name="members"></a>Members

 **cMTSIDs**
  
> **MTSID**结构由**abMTSIDs**成员描述该数组中的计数。 
    
 **cbMTSIDs**
  
> 描述**abMTSIDs**数组中的字节数。
    
 **abMTSIDs**
  
> 包含一个或多个**MTSID**结构的字节数组。 
    
## <a name="remarks"></a>说明

X.400 消息中的**FLATMTSIDLIST**结构使用对应于 MAPI 消息中的[FLATENTRYLIST](flatentrylist.md)结构的使用。 MAPI 使用**FLATMTSIDLIST**结构消息处理期间维护 X.400 属性。 服务提供商使用**FLATMTSIDLIST**结构处理传入和传出 X.400 邮件时。 
  
在**abMTSIDs**数组中，每个**MTSID**结构自然地对齐边界上对齐。 额外字节都作为包含填充使任意两个**MTSID**结构之间的确保自然对齐。 该数组中的第一个**MTSID**结构对齐始终正确，因为**abMTSIDs**成员的偏移量为 8。 若要计算的偏移量的下一个结构，使用向上舍入到 4 的下一步的倍数的第一个条目的大小。 使用[CbNewMTSID](cbnewmtsid.md)宏来计算**MTSID**结构的大小。 
  
## <a name="see-also"></a>另请参阅



[CbNewFLATMTSIDLIST](cbnewflatmtsidlist.md)
  
[FLATENTRYLIST](flatentrylist.md)
  
[MTSID](mtsid.md)


[MAPI 结构](mapi-structures.md)

