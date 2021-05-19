---
title: 验证和初始化邮件存储
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 74f0a1fe-2a79-4b32-ab88-85a8839a2639
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 77b3f707fc36a868de5acd7c7ba4642a1da4e3c9
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33433687"
---
# <a name="validating-and-initializing-a-message-store"></a>验证和初始化邮件存储

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
通过 [IMAPISession：：OpenMsgStore](imapisession-openmsgstore.md) 方法打开邮件存储而不设置 MDB_NO_MAIL 标志时，MAPI 将创建多个文件夹，并为其分配默认名称和角色。 MAPI 负责创建这些文件夹，以避免在客户端或邮件存储提供程序负责创建时出现不必要的不兼容情况。 
  
有时需要验证是否创建了适当的文件夹，并且这些文件夹是否有效。 [HrValidateIPMSubtree](hrvalidateipmsubtree.md)函数可用于此目的。 如果要验证默认邮件存储，请传递 MAPI_FULL_IPM_TREE 标志。 为默认邮件存储创建了一组更广泛的文件夹。 当 **HrValidateIPMSubtree** 收到 MAPI_FULL_IPM_TREE 标志时，它将检查以下文件夹： 
  
- IPM 子树的根文件夹
    
- IPM 根文件夹中的"已删除邮件"文件夹
    
- IPM 根文件夹中的收件箱文件夹
    
- IPM 根文件夹中的发件箱文件夹
    
- IPM 根文件夹中的"已发送项目"文件夹
    
- 邮件存储的根文件夹中的文件夹视图
    
- 邮件存储的根文件夹中的常见视图
    
- 邮件存储的根文件夹中的搜索文件夹
    
如果邮件存储不是默认存储，您可以设置或不设置MAPI_FULL_IPM_TREE标记。 未设置此标志时 **，HrValidateIPMSubtree** 仅检查子树的根文件夹、"已删除邮件"文件夹以及邮件存储搜索结果的根文件夹。 
  
若要初始化邮件存储，可在内存中存储以下属性，以便它们随时可用：
  
- **PR_VALID_FOLDER_MASK (** [PidTagValidFolderMask)](pidtagvalidfoldermask-canonical-property.md)
    
- **PR_STORE_SUPPORT_MASK (** [PidTagStoreSupportMask)](pidtagstoresupportmask-canonical-property.md)
    
这些属性是描述邮件存储功能的位掩码。 **PR_VALID_FOLDER_MASK** 邮件存储中每个特殊文件夹都有一个位集，并且分配有有效的条目标识符。 有关访问这些文件夹及其条目标识符的信息，请参阅打开 [邮件存储文件夹](opening-a-message-store-folder.md)。 
  
 **PR_STORE_SUPPORT_MASK** 邮件存储中支持的每一个功能都有一个位集。 例如，如果邮件存储支持通知和格式化文本，则其PR_STORE_SUPPORT_MASK将设置 STORE_NOTIFY_OK 和 STORE_RTF_OK 位。 
  
应本地存储的其他属性包括文件夹的条目标识符，PR_VALID_FOLDER_MASK **属性描述** 为有效的文件夹。 除"收件箱"文件夹外，每个特殊文件夹都有一个与之关联的条目标识符属性。 例如，发件箱文件夹的条目标识符PR_IPM_OUTBOX_ENTRYID ([PidTagIpmOutboxEntryId](pidtagipmoutboxentryid-canonical-property.md)) 属性。  由于这些文件夹是经常打开的文件夹，因此建议让条目标识符随时可用。
  

