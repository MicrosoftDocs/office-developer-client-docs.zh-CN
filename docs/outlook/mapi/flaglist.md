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
ms.openlocfilehash: a5e508f5f7e6554a115517da87a8eac39f39aecf
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33412973"
---
# <a name="flaglist"></a>FLAGLIST

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含用于在名称解析过程中指示地址条目状态的标志列表。
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapidefs.h  <br/> |
   
```cpp
typedef struct
{
  ULONG cFlags;
  ULONG ulFlags[MAPI_DIM];
} FlagList, FAR * LPFlagList;

```

## <a name="members"></a>Members

 **cFlags**
  
> 列表中 MAPI 定义标志的计数。
    
 **ulFlags**
  
> 一个标志数组，用于为收件人提供名称解析操作的状态。 可以设置以下标志：
    
MAPI_AMBIGUOUS 
  
> 收件人已解析，但无法解析为唯一条目标识符。 其他通讯簿容器不应尝试解析此收件人。 
    
MAPI_RESOLVED 
  
> 收件人已解析为唯一条目标识符。 其他通讯簿容器不应尝试解析此收件人。 
    
MAPI_UNRESOLVED 
  
> 条目尚未解析。 其他通讯簿容器应尝试解析此收件人。
    
## <a name="remarks"></a>备注

**FLAGLIST** 结构用作 [IABContainer：：ResolveNames 的参数](iabcontainer-resolvenames.md)。 要解析的每个收件人都包含在 [ADRLIST](adrlist.md) 结构中。 当通讯簿容器尝试解析每个收件人时，它会在 **FLAGLIST** 结构的相应条目中设置相应的标志。 **FLAGLIST** 结构的所有条目的顺序与 **ADRLIST** 结构中的条目的顺序相同。 这便于将标志设置与收件人关联。 
  
## <a name="see-also"></a>另请参阅



[ADRLIST](adrlist.md)
  
[IABContainer::ResolveNames](iabcontainer-resolvenames.md)


[MAPI 结构](mapi-structures.md)

