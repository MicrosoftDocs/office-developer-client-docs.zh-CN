---
title: 验证和初始化邮件存储区
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 74f0a1fe-2a79-4b32-ab88-85a8839a2639
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 7a5a5045594e87953d967fddbdeefd5ac18c8a3d
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22581970"
---
# <a name="validating-and-initializing-a-message-store"></a>验证和初始化邮件存储区

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
打开时的消息存储通过[IMAPISession::OpenMsgStore](imapisession-openmsgstore.md)方法而不设置 MDB_NO_MAIL 标志，MAPI 创建几个文件夹，并将其分配默认名称和角色。 MAPI 负责创建这些文件夹，以避免将不可避免发生，如果客户端或消息存储提供程序负责创建不兼容性。 
  
有时很有必要，若要验证已创建相应的文件夹和它们是有效。 [HrValidateIPMSubtree](hrvalidateipmsubtree.md)函数是可实现此目的。 如果您要验证默认的邮件存储，传递 MAPI_FULL_IPM_TREE 标志。 为默认的邮件存储创建更复杂的一组文件夹。 当**HrValidateIPMSubtree**接收 MAPI_FULL_IPM_TREE 标志时，它会检查的以下文件夹： 
  
- IPM 子树的根文件夹
    
- IPM 根文件夹中的已删除的项目文件夹
    
- IPM 根文件夹中的收件箱文件夹
    
- 发件箱文件夹中的 IPM 根文件夹
    
- 发送项目文件夹 IPM 根文件夹中
    
- 消息存储的根文件夹中的文件夹视图
    
- 消息存储的根文件夹中的公共视图
    
- 消息存储库的根文件夹中的搜索文件夹
    
如果消息存储不是默认值，您可以设置或不设置 MAPI_FULL_IPM_TREE 标志。 时未设置此标志， **HrValidateIPMSubtree**检查的根文件夹将子树中，为已删除邮件文件夹中和消息的根文件夹将存储搜索结果。 
  
若要初始化的消息存储，请在内存中存储以下属性以便它们随时可用：
  
- **PR_VALID_FOLDER_MASK**([PidTagValidFolderMask](pidtagvalidfoldermask-canonical-property.md))
    
- **PR_STORE_SUPPORT_MASK**([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md))
    
这些属性是描述的邮件存储功能的位掩码。 **PR_VALID_FOLDER_MASK**有一位设置为每个邮件存储区中存在具有有效的分配的项标识符的特殊文件夹。 有关访问这些文件夹和它们的项标识符的详细信息，请参阅[打开邮件存储文件夹](opening-a-message-store-folder.md)。 
  
 **PR_STORE_SUPPORT_MASK**有一位设置为消息存储库中支持每个功能。 例如，如果的消息存储支持通知和带格式的文本，其**PR_STORE_SUPPORT_MASK**将具有 STORE_NOTIFY_OK 和 STORE_RTF_OK 设置了位。 
  
应存储在本地其他属性包括**PR_VALID_FOLDER_MASK**属性描述为有效的文件夹的项标识符。 每个这些特殊文件夹，除收件箱文件夹中，有与之关联的项标识符属性。 例如，发件箱文件夹的条目标识符是其**PR_IPM_OUTBOX_ENTRYID** ([PidTagIpmOutboxEntryId](pidtagipmoutboxentryid-canonical-property.md)) 属性。 由于这些文件夹是将经常打开的文件夹，最好具有其随时可用的项标识符。
  

