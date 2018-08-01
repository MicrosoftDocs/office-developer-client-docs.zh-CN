---
title: PidTagValidFolderMask 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagValidFolderMask
api_type:
- COM
ms.assetid: 83a44aee-5269-42a8-8078-4bc063bb6e29
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: ae09723c78fe4e333fb5c46e8c79da4b77c0b331
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778535"
---
# <a name="pidtagvalidfoldermask-canonical-property"></a>PidTagValidFolderMask 规范属性

  
  
**适用于**： Outlook 
  
包含这些标志指示邮件存储区中的文件夹的项标识符的有效性的位掩码。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_VALID_FOLDER_MASK  <br/> |
|标识符：  <br/> |0x35DF  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |MAPI 邮件存储  <br/> |
   
## <a name="remarks"></a>说明

如果用户删除文件夹，或者如果消息存储已损坏，某个文件夹的条目标识符可以成为无效。
  
可以为位掩码设置一个或多个以下标志： 
  
FOLDER_COMMON_VIEWS_VALID 
  
> 公共视图文件夹具有一个有效项标识符。 请参阅**PR_COMMON_VIEWS_ENTRYID** ([PidTagCommonViewsEntryId](pidtagcommonviewsentryid-canonical-property.md))。
    
FOLDER_FINDER_VALID 
  
> Finder 文件夹有一个有效项标识符。 请参阅**PR_FINDER_ENTRYID** ([PidTagFinderEntryId](pidtagfinderentryid-canonical-property.md))。 
    
FOLDER_IPM_INBOX_VALID 
  
> 人际邮件 (IPM) 接收文件夹都有一个有效项标识符。 请参阅[IMsgStore::GetReceiveFolder](imsgstore-getreceivefolder.md)。 
    
FOLDER_IPM_OUTBOX_VALID 
  
> IPM 发件箱文件夹具有一个有效项标识符。 请参阅**PR_IPM_OUTBOX_ENTRYID** ([PidTagIpmOutboxEntryId](pidtagipmoutboxentryid-canonical-property.md))。 
    
FOLDER_IPM_SENTMAIL_VALID 
  
> IPM 发送邮件文件夹具有一个有效项标识符。 请参阅**PR_IPM_SENTMAIL_ENTRYID** ([PidTagIpmSentMailEntryId](pidtagipmsentmailentryid-canonical-property.md))。
    
FOLDER_IPM_SUBTREE_VALID 
  
> IPM 文件夹子树有一个有效项标识符。 请参阅**PR_IPM_SUBTREE_ENTRYID** ([PidTagIpmSubtreeEntryId](pidtagipmsubtreeentryid-canonical-property.md))。
    
FOLDER_IPM_WASTEBASKET_VALID 
  
> IPM 已删除邮件文件夹具有一个有效项标识符。 请参阅**PR_IPM_WASTEBASKET_ENTRYID** ([PidTagIpmWastebasketEntryId](pidtagipmwastebasketentryid-canonical-property.md))。
    
FOLDER_VIEWS_VALID 
  
> 在 views 文件夹有一个有效项标识符。 请参阅**PR_VIEWS_ENTRYID** ([PidTagViewsEntryId](pidtagviewsentryid-canonical-property.md))。
    
## <a name="related-resources"></a>相关资源

### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含作为替代名称列出的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

