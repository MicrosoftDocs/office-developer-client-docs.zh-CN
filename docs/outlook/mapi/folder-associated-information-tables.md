---
title: 文件夹关联的信息表
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: b72a0d36-c489-41d6-af57-72fbf4b7a3f5
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 09cac591aac9d266571348531e378974b86a3a9d
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774957"
---
# <a name="folder-associated-information-tables"></a>文件夹关联的信息表

  
  
**适用于**： Outlook 
  
MAPI 定义各种 MAPI 组件处理相关的信息表时要使用 MAPI_ASSOCIATED 标志。 每个文件夹中的消息存储应有以及其标准内容表关联的内容表。 客户端应用程序的文件夹关联的内容表来保存表单和视图中存储特殊的邮件。 实际上，若要支持表单和视图，消息存储提供程序必须实现关联的内容表。
  
若要实现关联的内容表，存储提供程序必须执行以下操作：
  
- 支持 MAPI_ASSOCIATED 标志[IMAPIContainer::GetContentsTable](imapicontainer-getcontentstable.md)方法中，因此客户端应用程序可以获取文件夹的关联的内容而不是标准内容表的表。 
    
- 支持 MAPI_ASSOCIATED 标志[IMAPIFolder::CreateMessage](imapifolder-createmessage.md)方法中，因此客户端应用程序可以将消息添加到的文件夹关联的内容表。 
    
- 对文件夹对象的**PR_ACCESS** ([PidTagAccess](pidtagaccess-canonical-property.md)) 属性中设置 MAPI_ACCESS_CREATE_ASSOCIATED 位。
    
- 在[IMAPIFolder::EmptyFolder](imapifolder-emptyfolder.md)方法支持 DEL_ASSOCIATED 标志。 
    
- 设置中的关联的内容表中的邮件的**PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) 属性位 MSGFLAG_ASSOCIATED。
    
- 公开和响应对文件夹的**PR_FOLDER_ASSOCIATED_CONTENTS** ([PidTagFolderAssociatedContents](pidtagfolderassociatedcontents-canonical-property.md)) 属性。
    
- 维护文件夹的**PR_ASSOC_CONTENT_COUNT** ([PidTagAssociatedContentCount](pidtagassociatedcontentcount-canonical-property.md)) 属性。
    
**PR_STORE_SUPPORT_MASK** ([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md)) 属性，以指示消息存储提供程序是否支持关联的内容表中没有任何位。 如果消息存储提供程序不支持它们，则应在客户端应用程序调用任何 MAPI_ASSOCIATED 标志与上述方法时返回 MAPI_E_NO_SUPPORT。
  
## <a name="see-also"></a>另请参阅



[邮件存储区功能](message-store-features.md)

