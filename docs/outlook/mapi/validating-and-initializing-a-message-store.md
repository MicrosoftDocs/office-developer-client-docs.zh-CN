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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32329580"
---
# <a name="validating-and-initializing-a-message-store"></a>验证和初始化邮件存储

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
通过[IMAPISession:: OpenMsgStore](imapisession-openmsgstore.md)方法打开邮件库时, 如果不设置 MDB_NO_MAIL 标志, MAPI 会创建多个文件夹并为其分配默认名称和角色。 MAPI 负责创建这些文件夹, 以避免在客户端或邮件存储提供程序负责创建时不可避免的不兼容情况。 
  
有时, 有必要验证是否已创建了适当的文件夹以及它们是否有效。 [HrValidateIPMSubtree](hrvalidateipmsubtree.md)函数可用于此目的。 如果要验证默认邮件存储, 请传递 MAPI_FULL_IPM_TREE 标志。 为默认邮件存储区创建更广泛的文件夹组。 当**HrValidateIPMSubtree**收到 MAPI_FULL_IPM_TREE 标志时, 它会检查以下文件夹: 
  
- IPM 子树的根文件夹
    
- IPM 根文件夹中的 "已删除邮件" 文件夹
    
- IPM 根文件夹中的 "收件箱" 文件夹
    
- IPM 根文件夹中的 "发件箱" 文件夹
    
- IPM 根文件夹中的 "已发送邮件" 文件夹
    
- 邮件存储区的根文件夹中的文件夹视图
    
- 邮件存储区的根文件夹中的常见视图
    
- 邮件存储区的根文件夹中的 "搜索文件夹"
    
如果邮件存储不是默认的, 则可以设置或不设置 MAPI_FULL_IPM_TREE 标志。 如果未设置此标志, 则**HrValidateIPMSubtree**仅检查子树的根文件夹、"已删除邮件" 文件夹和邮件存储区搜索结果的根文件夹。 
  
若要初始化邮件存储区, 请将以下属性存储在内存中, 以供随时使用:
  
- **PR_VALID_FOLDER_MASK**([PidTagValidFolderMask](pidtagvalidfoldermask-canonical-property.md))
    
- **PR_STORE_SUPPORT_MASK**([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md))
    
这些属性是用于描述邮件存储的功能的位掩码。 对于邮件存储区中存在的每个特殊文件夹, **PR_VALID_FOLDER_MASK**都设置了一个位, 并且具有有效的已分配条目标识符。 有关访问这些文件夹及其条目标识符的详细信息, 请参阅[打开邮件存储文件夹](opening-a-message-store-folder.md)。 
  
 **PR_STORE_SUPPORT_MASK**为邮件存储区中支持的每项功能设置了一个位。 例如, 如果邮件存储区支持通知和格式化文本, 则其**PR_STORE_SUPPORT_MASK**将设置 STORE_NOTIFY_OK 和 STORE_RTF_OK 位。 
  
应在本地存储的其他属性包括**PR_VALID_FOLDER_MASK**属性描述为有效的文件夹的条目标识符。 每个特殊文件夹 ("收件箱" 文件夹除外) 都有一个与之关联的条目标识符属性。 例如, "发件箱" 文件夹的条目标识符是其**PR_IPM_OUTBOX_ENTRYID** ([PidTagIpmOutboxEntryId](pidtagipmoutboxentryid-canonical-property.md)) 属性。 由于这些文件夹是将频繁打开的文件夹, 因此最好让其条目标识符易于使用。
  

