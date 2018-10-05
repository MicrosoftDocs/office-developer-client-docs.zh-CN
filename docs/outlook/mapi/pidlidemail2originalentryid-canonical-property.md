---
title: PidLidEmail2OriginalEntryId 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidEmail2OriginalEntryId
api_type:
- COM
ms.assetid: 10d45a99-54aa-4721-8847-1c7033a8a5b5
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: af644af12eb40d0f00f327892228a03d98700f21
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25382937"
---
# <a name="pidlidemail2originalentryid-canonical-property"></a>PidLidEmail2OriginalEntryId 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
指定对象对应于第二个电子邮件地址的**EntryId** 。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |dispidEmail2OriginalEntryID  <br/> |
|属性进行设置：  <br/> |PSETID_Address  <br/> |
|长 ID （盖）：  <br/> |0x00008095  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |联系人  <br/> |
   
## <a name="remarks"></a>说明

此属性的值必须是此电子通讯一次性**EntryId**或有效的通讯簿对象**EntryId**。
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供属性集定义和相关的 Exchange Server 协议规范的引用。
    
[[MS OXOCNTC]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)
  
> 指定的属性和操作所允许的联系人和个人通讯组列表。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

