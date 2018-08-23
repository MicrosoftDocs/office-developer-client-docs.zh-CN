---
title: 邮件存储区表
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: cdb7d8c5-8e35-47ff-8be7-2cb17e341ad3
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 735c778cd8e6ccb41de3d3d8cb0fdc163493f712
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22572016"
---
# <a name="message-store-tables"></a>邮件存储区表

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
消息存储表包含有关当前配置文件中的消息存储提供程序的信息。 没有为每个 MAPI 会话，由 MAPI 实现和客户端使用的一个消息存储表。 客户端可以使用此表中，例如，来查找特定提供程序的所有实例，或查找特定的邮件存储区。 
  
消息存储表是动态的。 如果客户端应用程序的用户编辑配置文件更改默认的邮件存储，例如**PR_DEFAULT_STORE**值受影响的邮件存储的属性将立即更新。 
  
客户端通过调用[IMAPISession::GetMsgStoresTable](imapisession-getmsgstorestable.md)方法访问消息存储表。 
  
以下属性构成设置消息存储表中所需的列：
  
|||
|:-----|:-----|
|**PR_DEFAULT_STORE**([PidTagDefaultStore](pidtagdefaultstore-canonical-property.md))  <br/> |**PR_DISPLAY_NAME**([PidTagDisplayName](pidtagdisplayname-canonical-property.md))  <br/> |
|**PR_ENTRYID**([PidTagEntryId](pidtagentryid-canonical-property.md))  <br/> |**PR_INSTANCE_KEY**([PidTagInstanceKey](pidtaginstancekey-canonical-property.md))  <br/> |
|**PR_MDB_PROVIDER**([PidTagStoreProvider](pidtagstoreprovider-canonical-property.md))  <br/> |**PR_OBJECT_TYPE**([PidTagObjectType](pidtagobjecttype-canonical-property.md))  <br/> |
|**PR_PROVIDER_DISPLAY**([PidTagProviderDisplay](pidtagproviderdisplay-canonical-property.md))  <br/> |**PR_RECORD_KEY**([PidTagRecordKey](pidtagrecordkey-canonical-property.md))  <br/> |
|**PR_RESOURCE_FLAGS**([PidTagResourceFlags](pidtagresourceflags-canonical-property.md))  <br/> |**PR_RESOURCE_TYPE**([PidTagResourceType](pidtagresourcetype-canonical-property.md))  <br/> |
   
## <a name="see-also"></a>另请参阅



[MAPI 表](mapi-tables.md)

