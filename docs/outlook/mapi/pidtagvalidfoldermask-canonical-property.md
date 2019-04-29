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
ms.openlocfilehash: 925e0eb60d55349ded114b827b6ca67e3b5ac1ce
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33427792"
---
# <a name="pidtagvalidfoldermask-canonical-property"></a>PidTagValidFolderMask 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含标志的位掩码, 用于指示邮件存储区中的文件夹的条目标识符的有效性。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_VALID_FOLDER_MASK  <br/> |
|标识符:  <br/> |0x35DF  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |MAPI 邮件存储  <br/> |
   
## <a name="remarks"></a>说明

如果用户删除文件夹或邮件存储区损坏, 则文件夹的条目标识符可能会变得无效。
  
可以为位掩码设置以下一个或多个标志: 
  
FOLDER_COMMON_VIEWS_VALID 
  
> "常见视图" 文件夹具有有效的条目标识符。 请参阅**PR_COMMON_VIEWS_ENTRYID** ([PidTagCommonViewsEntryId](pidtagcommonviewsentryid-canonical-property.md))。
    
FOLDER_FINDER_VALID 
  
> finder 文件夹具有有效的条目标识符。 请参阅**PR_FINDER_ENTRYID** ([PidTagFinderEntryId](pidtagfinderentryid-canonical-property.md))。 
    
FOLDER_IPM_INBOX_VALID 
  
> 人际邮件 (IPM) 接收文件夹具有有效的条目标识符。 请参阅[IMsgStore:: GetReceiveFolder](imsgstore-getreceivefolder.md)。 
    
FOLDER_IPM_OUTBOX_VALID 
  
> IPM "发件箱" 文件夹具有有效的条目标识符。 请参阅**PR_IPM_OUTBOX_ENTRYID** ([PidTagIpmOutboxEntryId](pidtagipmoutboxentryid-canonical-property.md))。 
    
FOLDER_IPM_SENTMAIL_VALID 
  
> "IPM 已发送邮件" 文件夹具有有效的条目标识符。 请参阅**PR_IPM_SENTMAIL_ENTRYID** ([PidTagIpmSentMailEntryId](pidtagipmsentmailentryid-canonical-property.md))。
    
FOLDER_IPM_SUBTREE_VALID 
  
> IPM 文件夹子树具有有效的条目标识符。 请参阅**PR_IPM_SUBTREE_ENTRYID** ([PidTagIpmSubtreeEntryId](pidtagipmsubtreeentryid-canonical-property.md))。
    
FOLDER_IPM_WASTEBASKET_VALID 
  
> "IPM 已删除邮件" 文件夹具有有效的条目标识符。 请参阅**PR_IPM_WASTEBASKET_ENTRYID** ([PidTagIpmWastebasketEntryId](pidtagipmwastebasketentryid-canonical-property.md))。
    
FOLDER_VIEWS_VALID 
  
> views 文件夹具有有效的条目标识符。 请参阅**PR_VIEWS_ENTRYID** ([PidTagViewsEntryId](pidtagviewsentryid-canonical-property.md))。
    
## <a name="related-resources"></a>相关资源

### <a name="header-files"></a>头文件

mapidefs。h
  
> 提供数据类型定义。
    
Mapitags
  
> 包含列为替换名称的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

