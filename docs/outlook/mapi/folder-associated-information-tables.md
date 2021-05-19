---
title: Folder-Associated信息表
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: b72a0d36-c489-41d6-af57-72fbf4b7a3f5
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 2332c2a2f7eb46816eab5305b73344e25b2832d7
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33426413"
---
# <a name="folder-associated-information-tables"></a>Folder-Associated信息表

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
MAPI 为处理MAPI_ASSOCIATED表时使用的各种 MAPI 组件定义 mapI 标志。 邮件存储中的每个文件夹都应有一个关联的内容表及其标准内容表。 客户端应用程序将特殊邮件存储在文件夹的关联内容表中，以保存表单和视图。 事实上，为了支持表单和视图，邮件存储提供程序必须实现关联的内容表。
  
若要实现关联的内容表，您的存储提供程序必须执行以下操作：
  
- 支持 [IMAPIContainer：：GetContentsTable](imapicontainer-getcontentstable.md) 方法中的 MAPI_ASSOCIATED 标志，以便客户端应用程序可以获取文件夹的关联内容表，而不是标准内容表。 
    
- 支持 [IMAPIFolder：：CreateMessage](imapifolder-createmessage.md) 方法中的 MAPI_ASSOCIATED 标志，以便客户端应用程序可以将消息添加到文件夹的关联内容表中。 
    
- 在文件夹MAPI_ACCESS_CREATE_ASSOCIATED [PidTagAccess](pidtagaccess-canonical-property.md) PR_ACCESS (设置) 位。 
    
- 支持 [IMAPIFolder：：EmptyFolder](imapifolder-emptyfolder.md) 方法中的 DEL_ASSOCIATED 标记。 
    
- 为MSGFLAG_ASSOCIATED内容表中的邮件设置 PR_MESSAGE_FLAGS  ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) 属性中的位。
    
- 公开并响应文件夹 **PR_FOLDER_ASSOCIATED_CONTENTS (** [PidTagFolderAssociatedContents](pidtagfolderassociatedcontents-canonical-property.md)) 属性。
    
- 维护文件夹 **PR_ASSOC_CONTENT_COUNT (** [PidTagAssociatedContentCount](pidtagassociatedcontentcount-canonical-property.md)) 属性。
    
[PidTagStoreSupportMask PR_STORE_SUPPORT_MASK (PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md)) 属性中没有任何位可指示邮件存储提供程序是否支持关联的内容表。  如果邮件存储提供程序不支持这些方法，则当客户端应用程序MAPI_E_NO_SUPPORT上述任何具有 MAPI_ASSOCIATED 标志的方法时，应返回MAPI_ASSOCIATED消息。
  
## <a name="see-also"></a>另请参阅



[邮件存储功能](message-store-features.md)

