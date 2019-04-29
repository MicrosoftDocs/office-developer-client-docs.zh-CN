---
title: MAPI 特殊文件夹
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: f2aa2376-b293-4d05-9104-218cc1fe1758
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: fa221510a5f6a8c8be24b4869960d1770cef5882
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33410922"
---
# <a name="mapi-special-folders"></a>MAPI 特殊文件夹

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
MAPI 定义了一些特殊的文件夹, 因为它们为特定类型的邮件提供了预定义角色作为默认文件夹。 这些特殊文件夹通常不能删除, 并且它们具有特殊的条目标识符属性。
  
有八个特殊文件夹, 一些是人际邮件 (IPM) 子树的一部分。 MAPI 会在客户端访问其邮件存储区之前创建这些文件夹, 如果需要, 客户端可能能够删除这些文件夹。 某些邮件存储提供程序允许删除, 而其他则不是。 下表介绍了这些文件夹。
  
**MAPI 文件夹**

|**Folder**|**说明**|
|:-----|:-----|
|发件箱文件夹  <br/> |包含传出的 IPM 邮件。  <br/> |
|“已删除邮件”文件夹  <br/> |包含标记为要删除的 IPM 邮件。  <br/> |
|"已发送邮件" 文件夹  <br/> |包含已发送的 IPM 邮件。  <br/> |
|IPM 根文件夹  <br/> |包含用于管理 IPM 邮件的文件夹。  <br/> |
|接收文件夹  <br/> |包含特定邮件类别的传入邮件。  <br/> |
|搜索结果根文件夹  <br/> |包含用于管理搜索结果的文件夹。  <br/> |
|常见的视图根文件夹  <br/> |包含用于管理邮件存储的视图的文件夹。  <br/> |
|个人-视图根文件夹  <br/> |包含用于管理特定用户的视图的文件夹。  <br/> |
   
前四个文件夹与 IPM 子树相关, 在初始化邮件存储时 MAPI 创建的文件夹树。 交互邮件客户端的默认邮件存储总是在其文件夹层次结构中包含 IPM 文件夹子树和其他特殊文件夹。 仅支持搜索结果根文件夹、IPM 子树根文件夹、"已删除邮件" 文件夹和 "接收" 文件夹时, 才需要非默认邮件存储。 若要确保 IPM 子树文件夹存在且有效, 客户端可以调用[HrValidateIPMSubtree](hrvalidateipmsubtree.md)函数。 **HrValidateIPMSubtree**检查文件夹并在出现问题时重新创建它们。 
  
搜索结果、常见视图和个人视图的根文件夹不是 IPM 子树的一部分;这些文件夹是在邮件存储区的根文件夹中创建的。 搜索结果根文件夹包含的文件夹支持具有符合一组搜索条件的邮件的内容表格。 尽管允许客户端在任何文件夹中创建搜索结果文件夹, 但大多数客户端都将单个根文件夹指定为在会话期间创建的所有搜索结果文件夹的父文件夹。 
  
常见视图和个人视图根文件夹包含描述视图的消息, 或用于显示邮件和文件夹数据的首选方法。 常见视图根文件夹包含客户端可用于邮件存储区中的任何文件夹的视图。"个人视图" 文件夹包含已由特定用户为特定文件夹或文件夹定义的视图。
  
使用 ipm 邮件的客户端应在 IPM 子树根文件夹下创建所有文件夹和邮件, 而不是邮件存储区的根文件夹。 这将为非 ipm 客户端—处理在计算机之间或在人类和计算机之间交换的邮件的客户端, 这是一种从 IPM 客户端隐藏邮件的简单方法。 
  
MAPI 为这些特殊文件夹分配特殊的条目标识符属性。 有关特殊文件夹项标识符的列表, 请参阅[打开邮件存储文件夹](opening-a-message-store-folder.md)。
  
### <a name="outlook-special-folders"></a>Outlook 特殊文件夹

Outlook 特殊文件夹由其在 "收件箱" 文件夹和邮件存储区的根文件夹中存储的条目 id 标识。
  
|**Folder**|**要设置的属性**|
|:-----|:-----|
|日历  <br/> |**PR_IPM_APPOINTMENT_ENTRYID**([PidTagIpmAppointmentEntryId](pidtagipmappointmententryid-canonical-property.md))  <br/> |
|联系人  <br/> |**PR_IPM_CONTACT_ENTRYID**([PidTagIpmContactEntryId](pidtagipmcontactentryid-canonical-property.md))  <br/> |
|分类账  <br/> |**PR_IPM_JOURNAL_ENTRYID**([PidTagIpmJournalEntryId](pidtagipmjournalentryid-canonical-property.md))  <br/> |
|注释  <br/> |**PR_IPM_NOTE_ENTRYID**([PidTagIpmNoteEntryId](pidtagipmnoteentryid-canonical-property.md))  <br/> |
|任务  <br/> |**PR_IPM_TASK_ENTRYID**([PidTagIpmTaskEntryId](pidtagipmtaskentryid-canonical-property.md))  <br/> |
|草稿  <br/> |**PR_IPM_DRAFTS_ENTRYID**([PidTagIpmDraftsEntryId](pidtagipmdraftsentryid-canonical-property.md))  <br/> |
   
## <a name="see-also"></a>另请参阅



[MAPI 文件夹](mapi-folders.md)

