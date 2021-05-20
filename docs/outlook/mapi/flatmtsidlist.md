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
ms.openlocfilehash: bd9bfe4d1411b84a7811235aa68728afaefe64ab
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33439217"
---
# <a name="flatmtsidlist"></a>FLATMTSIDLIST

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含 [MTSID](mtsid.md) 结构数组，其中每个结构都包含一个 X.400 邮件传输系统 (MTS) 标识符。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapidefs.h  <br/> |
|相关宏：  <br/> |[CbFLATMTSIDLIST](cbflatmtsidlist.md) [、CbNewFLATMTSIDLIST](cbnewflatmtsidlist.md) <br/> |
   
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
  
> **abMTSIDs** 成员描述的数组中的 **MTSID** 结构计数。 
    
 **cbMTSIDs**
  
> **abMTSIDs** 描述的数组中的字节数。
    
 **abMTSIDs**
  
> 包含一个或多个 **MTSID** 结构的字节数组。 
    
## <a name="remarks"></a>备注

**FLATMTSIDLIST** 结构在 X.400 邮件中的使用与 [FLATENTRYLIST](flatentrylist.md)结构在 MAPI 邮件中的使用相对应。 MAPI 使用 **FLATMTSIDLIST** 结构在邮件处理过程中维护 X.400 属性。 在处理传入和传出 X.400 邮件时，服务提供商使用 **FLATMTSIDLIST** 结构。 
  
在 **abMTSIDs** 数组中，每个 **MTSID** 结构在自然对齐的边界上对齐。 额外字节作为填充包括在内，以确保任何两 **个 MTSID** 结构之间的自然对齐。 数组中的第一个 **MTSID** 结构始终正确对齐，因为 **abMTSIDs** 成员偏移量为 8。 若要计算下一结构的偏移量，请使用向上舍入到下一个 4 倍数的第一个条目的大小。 使用 [CbNewMTSID](cbnewmtsid.md) 宏计算 **MTSID** 结构的大小。 
  
## <a name="see-also"></a>另请参阅



[CbNewFLATMTSIDLIST](cbnewflatmtsidlist.md)
  
[FLATENTRYLIST](flatentrylist.md)
  
[MTSID](mtsid.md)


[MAPI 结构](mapi-structures.md)

