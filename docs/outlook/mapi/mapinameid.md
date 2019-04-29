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
ms.openlocfilehash: baec750a460b3ba9becd2e1dddf967705424ac4e
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33411678"
---
# <a name="mapinameid"></a>MAPINAMEID

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
描述命名属性。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |mapidefs。h  <br/> |
   
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
  
> 指向定义特定属性集的[GUID](guid.md)结构的指针;此成员不能为 NULL。 有效值如下： 
    
PS_PUBLIC_STRINGS
  
> 
    
PS_MAPI
  
> 
    
客户端定义的值
  
> 
    
 **ulKind**
  
> 描述**Kind**成员中的值类型的值。 有效值如下： 
    
MNID_ID 
  
> **Kind**成员包含一个整数值, 表示属性名称。 
    
MNID_STRING 
  
> **Kind**成员包含表示属性名称的 Unicode 字符字符串。 
    
 **Kind**
  
> 描述命名属性的名称的联合。 名称可以是整数值 (存储在**盖子**中), 也可以是存储在**lpwstrName**中的 Unicode 字符字符串。
    
## <a name="remarks"></a>说明

**MAPINAMEID**结构用于描述其标识符超过0x8000 的命名属性属性。 属性集是命名属性的重要部分。 例如, PS_PUBLIC_STRINGS 或 PS_ROUTING_ADDRTYPE 是由 MAPI 定义的属性集。 
  
命名属性使客户端能够在更大的命名空间中定义自定义属性, 而不是 MAPI 定义的属性标识符范围中提供的属性。 属性名称不能用于直接获取属性值;必须先通过[IMAPIProp:: GetIDsFromNames](imapiprop-getidsfromnames.md)方法将它们映射到属性标识符。 对于特定的对象 (如邮件), MAPI 会为自定义属性保留一系列属性标识符。 因此, 对于这些对象, 客户端无需使用命名属性, 并且可以节省相关开销。 
  
有关命名属性的详细信息, 请参阅[命名属性](mapi-named-properties.md)。
  
## <a name="see-also"></a>另请参阅



[GUID](guid.md)
  
[IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md)


[MAPI 结构](mapi-structures.md)

