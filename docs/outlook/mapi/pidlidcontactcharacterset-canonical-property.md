---
title: PidLidContactCharacterSet 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidContactCharacterSet
api_type:
- COM
ms.assetid: a167e199-a9b2-47f9-a90e-2abc7c29828c
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 9706d1060347609708070140aae51d9dcadbb9c2
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776745"
---
# <a name="pidlidcontactcharacterset-canonical-property"></a>PidLidContactCharacterSet 规范属性

  
  
**适用于**： Outlook 
  
指定用于此联系人的字符集。
  
|||
|:-----|:-----|
|相关属性：  <br/> |dispidContactCharSet  <br/> |
|属性进行设置：  <br/> |PSETID_Address  <br/> |
|长 ID （盖）：  <br/> |0x00008023  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |联系人  <br/> |
   
## <a name="remarks"></a>说明

应用程序可以使用此属性以帮助生成的**dispidFileUnder** ([PidLidFileUnder](pidlidfileunder-canonical-property.md))、 **dispidFileUnderList** ([PidLidFileUnderList](pidlidfileunderlist-canonical-property.md)) 和**dispidFileUnderId 选择字符集相关列表**([PidLidFileUnderId](pidlidfileunderid-canonical-property.md)) 属性。 如果属性的值，"0x00000000"或"0x00000001"应用程序应视为属性未设置。
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供属性集定义和相关的 Exchange Server 协议规范的引用。
    
[[MS OXOCNTC]](http://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)
  
> 指定的属性和操作所允许的联系人和个人通讯组列表。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

