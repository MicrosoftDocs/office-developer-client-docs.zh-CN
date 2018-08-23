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
ms.openlocfilehash: 59e9cf23aed2a389384318468c3853cd41c9ec1e
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22585680"
---
# <a name="mtsid"></a>MTSID

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
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
    
## <a name="remarks"></a>注解

**MTSID**结构仅用于 X.400 映射的 MAPI 条目标识符。 对应于 MAPI [FLATENTRY](flatentry.md)结构。 
  
MTS 标识符具有与 MAPI 条目标识符或二进制属性值相同的格式。 MTS 标识符可以取消延迟的消息特别有用。 
  
## <a name="see-also"></a>另请参阅



[FLATENTRY](flatentry.md)
  
[FLATMTSIDLIST](flatmtsidlist.md)


[MAPI 结构](mapi-structures.md)

