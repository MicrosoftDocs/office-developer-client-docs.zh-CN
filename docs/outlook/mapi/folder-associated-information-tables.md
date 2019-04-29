---
title: 与文件夹关联的信息表
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
# <a name="folder-associated-information-tables"></a>与文件夹关联的信息表

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
mapi 定义了在处理关联的信息表时要使用的各种 MAPI 组件的 MAPI_ASSOCIATED 标志。 邮件存储区中的每个文件夹都应具有关联的内容表及其标准内容表。 客户端应用程序将特殊邮件存储在文件夹的关联内容表中, 以容纳表单和视图。 事实上, 若要支持表单和视图, 您的邮件存储提供程序必须实现关联的内容表。
  
若要实现关联的内容表, 您的存储提供程序必须执行以下操作:
  
- 支持[IMAPIContainer:: GetContentsTable](imapicontainer-getcontentstable.md)方法中的 MAPI_ASSOCIATED 标志, 以便客户端应用程序可以获取文件夹的关联内容表, 而不是标准内容表。 
    
- 支持[IMAPIFolder:: CreateMessage](imapifolder-createmessage.md)方法中的 MAPI_ASSOCIATED 标志, 以便客户端应用程序可以将邮件添加到文件夹的关联内容表。 
    
- 在 folder 对象的**PR_ACCESS** ([PidTagAccess](pidtagaccess-canonical-property.md)) 属性中设置 MAPI_ACCESS_CREATE_ASSOCIATED 位。
    
- 支持[IMAPIFolder:: EmptyFolder](imapifolder-emptyfolder.md)方法中的 DEL_ASSOCIATED 标志。 
    
- 在 "关联的内容" 表中的邮件的**PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) 属性中设置 MSGFLAG_ASSOCIATED 位。
    
- 公开和响应文件夹的**PR_FOLDER_ASSOCIATED_CONTENTS** ([PidTagFolderAssociatedContents](pidtagfolderassociatedcontents-canonical-property.md)) 属性。
    
- 维护文件夹的**PR_ASSOC_CONTENT_COUNT** ([PidTagAssociatedContentCount](pidtagassociatedcontentcount-canonical-property.md)) 属性。
    
**PR_STORE_SUPPORT_MASK** ([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md)) 属性中没有任何位来指示您的邮件存储提供程序是否支持关联的内容表。 如果您的邮件存储提供程序不支持它们, 则当客户端应用程序使用 MAPI_ASSOCIATED 标志调用上述任何方法时, 它应返回 MAPI_E_NO_SUPPORT。
  
## <a name="see-also"></a>另请参阅



[邮件存储区功能](message-store-features.md)

