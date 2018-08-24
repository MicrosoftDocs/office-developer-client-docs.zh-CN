---
title: PidLidHasPicture 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidHasPicture
api_type:
- COM
ms.assetid: c3bea11c-3197-4060-8672-f1b4bf352112
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 30046bd7982d08d99c5581c27d1616162d904dee
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22577105"
---
# <a name="pidlidhaspicture-canonical-property"></a>PidLidHasPicture 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
指定联系人是否存在的照片附件。
  
|||
|:-----|:-----|
|相关属性：  <br/> |dispidHasPicture  <br/> |
|属性进行设置：  <br/> |PSETID_Address  <br/> |
|长 ID （盖）：  <br/> |0x00008015  <br/> |
|数据类型：  <br/> |PT_BOOLEAN  <br/> |
|区域：  <br/> |联系人  <br/> |
   
## <a name="remarks"></a>注解

如果该属性存在，并且设置为 TRUE，则该联系人的附件表包含附件**PR_ATTACHMENT_CONTACTPHOTO** ([PidTagAttachmentContactPhoto](pidtagattachmentcontactphoto-canonical-property.md)) 属性设置为 TRUE。
  
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

