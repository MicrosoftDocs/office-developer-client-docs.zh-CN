---
title: 邮件存储表
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: cdb7d8c5-8e35-47ff-8be7-2cb17e341ad3
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: dd28c146f6b05b2dea03f73fab7131f23ca99e5f
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33405350"
---
# <a name="message-store-tables"></a>邮件存储表

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
邮件存储表包含有关当前配置文件中邮件存储提供程序的信息。 每个 MAPI 会话有一个消息存储表，由 MAPI 实现，供客户端使用。 例如，客户端可以使用此表查找特定提供程序的所有实例或查找特定邮件存储。 
  
邮件存储表是动态的。 如果客户端应用程序的用户编辑配置文件，则更改默认邮件存储（例如，受影响邮件存储的 **PR_DEFAULT_STORE** 属性的值）将立即更新。 
  
客户端通过调用 [IMAPISession：：GetMsgStoresTable](imapisession-getmsgstorestable.md) 方法访问消息存储表。 
  
下列属性将包含邮件存储表中所需的列集：
  
|||
|:-----|:-----|
|**PR_DEFAULT_STORE (** [PidTagDefaultStore](pidtagdefaultstore-canonical-property.md))   <br/> |**PR_DISPLAY_NAME (** [PidTagDisplayName](pidtagdisplayname-canonical-property.md))   <br/> |
|**PR_ENTRYID (** [PidTagEntryId](pidtagentryid-canonical-property.md))   <br/> |**PR_INSTANCE_KEY (** [PidTagInstanceKey](pidtaginstancekey-canonical-property.md))   <br/> |
|**PR_MDB_PROVIDER (** [PidTagStoreProvider](pidtagstoreprovider-canonical-property.md))   <br/> |**PR_OBJECT_TYPE (** [PidTagObjectType](pidtagobjecttype-canonical-property.md))   <br/> |
|**PR_PROVIDER_DISPLAY (** [PidTagProviderDisplay](pidtagproviderdisplay-canonical-property.md))   <br/> |**PR_RECORD_KEY (** [PidTagRecordKey)](pidtagrecordkey-canonical-property.md)  <br/> |
|**PR_RESOURCE_FLAGS (** [PidTagResourceFlags)](pidtagresourceflags-canonical-property.md)  <br/> |**PR_RESOURCE_TYPE (** [PidTagResourceType](pidtagresourcetype-canonical-property.md))   <br/> |
   
## <a name="see-also"></a>另请参阅



[MAPI 表](mapi-tables.md)

