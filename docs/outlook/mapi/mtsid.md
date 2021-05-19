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
ms.openlocfilehash: 96da91acec741322e6c07c64555171d35f0f7e00
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33435171"
---
# <a name="mtsid"></a>MTSID

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含一个 X.400 邮件传输系统 (MTS) 标识符。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapidefs.h  <br/> |
|相关宏：  <br/> |[CbMTSID](cbmtsid.md) [、CbNewMTSID](cbnewmtsid.md) <br/> |
   
```cpp
typedef struct
{
  ULONG cb;
  BYTE abEntry[MAPI_DIM];
} MTSID, FAR *LPMTSID;

```

## <a name="members"></a>Members

 **cb**
  
> **abEntry** 成员描述的数组中的字节数。 
    
 **abEntry**
  
> 包含 MTS 条目标识符数据的字节数组。
    
## <a name="remarks"></a>备注

**MTSID** 结构仅用于 MAPI 条目标识符的 X.400 映射。 它对应于 MAPI [FLATENTRY](flatentry.md) 结构。 
  
MTS 标识符的格式与 MAPI 条目标识符或二进制属性值的格式相同。 MTS 标识符对于取消延迟邮件特别有用。 
  
## <a name="see-also"></a>另请参阅



[FLATENTRY](flatentry.md)
  
[FLATMTSIDLIST](flatmtsidlist.md)


[MAPI 结构](mapi-structures.md)

