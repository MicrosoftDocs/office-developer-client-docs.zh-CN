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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32327305"
---
# <a name="flatmtsidlist"></a>FLATMTSIDLIST

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含[MTSID](mtsid.md)结构的数组, 其中每个结构都包含一个 X. 400 邮件传输系统 (MTS) 条目标识符。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |mapidefs。h  <br/> |
|相关宏:  <br/> |[CbFLATMTSIDLIST](cbflatmtsidlist.md)、 [CbNewFLATMTSIDLIST](cbnewflatmtsidlist.md) <br/> |
   
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
  
> 由**abMTSIDs**成员描述的数组中的**MTSID**结构的计数。 
    
 **cbMTSIDs**
  
> 由**abMTSIDs**描述的数组中的字节数。
    
 **abMTSIDs**
  
> 包含一个或多个**MTSID**结构的字节数组。 
    
## <a name="remarks"></a>注解

X. 400 邮件传递中的**FLATMTSIDLIST**结构与 MAPI 邮件中的[FLATENTRYLIST](flatentrylist.md)结构使用相对应。 MAPI 在邮件处理过程中使用**FLATMTSIDLIST**结构来维护 X. 400 属性。 服务提供程序在处理传入和传出的 X 400 邮件时使用**FLATMTSIDLIST**结构。 
  
在**abMTSIDs**数组中, 每个**MTSID**结构在自然对齐的边界处对齐。 填充包含额外的字节以确保任意两个**MTSID**结构之间的自然对齐。 数组中的第一个**MTSID**结构始终正确对齐, 因为**abMTSIDs**成员的偏移量为8。 若要计算下一个结构的偏移量, 请使用第一项的大小向上舍入到接下来的4个。 使用[CbNewMTSID](cbnewmtsid.md)宏计算**MTSID**结构的大小。 
  
## <a name="see-also"></a>另请参阅



[CbNewFLATMTSIDLIST](cbnewflatmtsidlist.md)
  
[FLATENTRYLIST](flatentrylist.md)
  
[MTSID](mtsid.md)


[MAPI 结构](mapi-structures.md)

