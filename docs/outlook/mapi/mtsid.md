---
title: MTSID
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.MTSID
api_type:
- COM
ms.assetid: 3d9bc643-332f-4c8e-83e6-ce9b15711945
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: e42bbf23ea8cf4e6196017a962329366e168420d
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776534"
---
# <a name="mtsid"></a>MTSID

  
  
**适用于**： Outlook 
  
包含 X.400 邮件传输系统 (MTS) 条目标识符。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapidefs.h  <br/> |
|相关的宏：  <br/> |[CbMTSID](cbmtsid.md) [CbNewMTSID](cbnewmtsid.md) <br/> |
   
```cpp
typedef struct
{
  ULONG cb;
  BYTE abEntry[MAPI_DIM];
} MTSID, FAR *LPMTSID;

```

## <a name="members"></a>Members

 **cb**
  
> 描述**abEntry**成员数组中的字节数。 
    
 **abEntry**
  
> 包含 MTS 条目标识符数据的字节数组。
    
## <a name="remarks"></a>说明

**MTSID**结构仅用于 X.400 映射的 MAPI 条目标识符。 对应于 MAPI [FLATENTRY](flatentry.md)结构。 
  
MTS 标识符具有与 MAPI 条目标识符或二进制属性值相同的格式。 MTS 标识符可以取消延迟的消息特别有用。 
  
## <a name="see-also"></a>另请参阅



[FLATENTRY](flatentry.md)
  
[FLATMTSIDLIST](flatmtsidlist.md)


[MAPI 结构](mapi-structures.md)

