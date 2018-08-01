---
title: FLAGLIST
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.FLAGLIST
api_type:
- COM
ms.assetid: b4c0655c-1a3a-4f89-a977-0431db596512
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 2cf5ff69e8453b2da26fd5044823ddf4f99a9f45
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774943"
---
# <a name="flaglist"></a>FLAGLIST

  
  
**适用于**： Outlook 
  
包含用于指示过程名称解析过程中的地址条目的状态标志的列表。
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapidefs.h  <br/> |
   
```cpp
typedef struct
{
  ULONG cFlags;
  ULONG ulFlags[MAPI_DIM];
} FlagList, FAR * LPFlagList;

```

## <a name="members"></a>Members

 **cFlags**
  
> MAPI 定义列表中的标志的计数。
    
 **ulFlags**
  
> 提供的收件人的名称解析操作的状态标志的数组。 可以设置以下标志：
    
MAPI_AMBIGUOUS 
  
> 收件人已得到解决，但不适用于唯一项标识符。 其他地址簿容器不应尝试解析该收件人。 
    
MAPI_RESOLVED 
  
> 收件人已解析为唯一项标识符。 其他地址簿容器不应尝试解析该收件人。 
    
MAPI_UNRESOLVED 
  
> 条目不已解决。 其他地址簿容器应尝试解析该收件人。
    
## <a name="remarks"></a>说明

**FLAGLIST**结构用作[IABContainer::ResolveNames](iabcontainer-resolvenames.md)参数。 [ADRLIST](adrlist.md)结构中包含每个要解析的收件人。 通讯簿容器尝试解决每个收件人，如**FLAGLIST**结构中的相应条目中设置相应的标志。 所有**FLAGLIST**结构中的条目都**ADRLIST**结构中的项的顺序相同。 这便于与收件人关联的标记设置。 
  
## <a name="see-also"></a>另请参阅



[ADRLIST](adrlist.md)
  
[IABContainer::ResolveNames](iabcontainer-resolvenames.md)


[MAPI 结构](mapi-structures.md)

