---
title: MAPINAMEID
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.MAPINAMEID
api_type:
- COM
ms.assetid: 9a92e9cd-8282-4cf0-93af-4089b3763594
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: f0ff4d8beb9c9d82d685630a35aefebaf7de71fc
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22570826"
---
# <a name="mapinameid"></a>MAPINAMEID

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
描述的命名的属性。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapidefs.h  <br/> |
   
```cpp
typedef struct _MAPINAMEID
{
  LPGUID lpguid;
  ULONG ulKind;
  union
  {
    LONG lID;
    LPWSTR lpwstrName;
  } Kind;
} MAPINAMEID, FAR *LPMAPINAMEID;

```

## <a name="members"></a>Members

 **lpguid**
  
> 指向定义特定属性的[GUID](guid.md)结构设置;此成员不能为 NULL。 有效值如下： 
    
PS_PUBLIC_STRINGS
  
> 
    
PS_MAPI
  
> 
    
客户端定义的值
  
> 
    
 **ulKind**
  
> 描述**类型**成员中的值的类型的值。 有效值如下： 
    
MNID_ID 
  
> **类型**成员包含一个整数值，表示的属性名称。 
    
MNID_STRING 
  
> **类型**成员包含表示的属性名称的 Unicode 字符串。 
    
 **种类**
  
> 联合描述的命名属性的名称。 名称可以存储在**盖**，整数值或**lpwstrName**中存储的 Unicode 字符字符串。
    
## <a name="remarks"></a>注解

**MAPINAMEID**结构用于描述具有超过 0x8000 标识符的命名的属性属性。 属性集是一个重要组成部分的命名属性。 例如 PS_PUBLIC_STRINGS 或 PS_ROUTING_ADDRTYPE 是由 MAPI 的属性集。 
  
命名的属性允许客户端比可用 MAPI 定义属性标识符的范围中的较大命名空间中定义自定义属性。 属性名称不能用于直接调用获取属性值他们必须首先将映射到属性标识符通过[IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md)方法。 例如，消息的特定对象，MAPI 保留自定义属性的属性标识符的范围。 因此，对于这些对象，客户端没有以使用命名的属性，可以保存关联开销。 
  
有关命名属性的详细信息，请参阅[名为属性](mapi-named-properties.md)。
  
## <a name="see-also"></a>另请参阅



[GUID](guid.md)
  
[IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md)


[MAPI 结构](mapi-structures.md)

