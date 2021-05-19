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
  
MAPI 定义了一些特殊文件夹，因为它们将预定义角色用作某些类型的邮件的默认文件夹。 通常无法删除这些特殊文件夹，它们具有特殊的条目标识符属性。
  
有八个特殊文件夹，其中一些是 IPM 子树中 (邮件) 部分。 MAPI 在客户端接收对邮件存储的访问权限之前创建这些文件夹，之后，客户端可能会在必要时删除这些文件夹。 某些邮件存储提供程序允许删除，而其他邮件存储提供程序不允许删除。 下表介绍了这些文件夹。
  
**MAPI 文件夹**

|**Folder**|**说明**|
|:-----|:-----|
|发件箱文件夹  <br/> |包含传出 IPM 邮件。  <br/> |
|“已删除邮件”文件夹  <br/> |包含标记为删除的 IPM 邮件。  <br/> |
|"已发送项目"文件夹  <br/> |包含已发送的 IPM 邮件。  <br/> |
|IPM 根文件夹  <br/> |包含用于管理 IPM 邮件的文件夹。  <br/> |
|接收文件夹  <br/> |包含特定邮件类的传入邮件。  <br/> |
|搜索结果根文件夹  <br/> |包含用于管理搜索结果的文件夹。  <br/> |
|通用视图根文件夹  <br/> |包含用于管理邮件存储视图的文件夹。  <br/> |
|个人视图根文件夹  <br/> |包含用于管理特定用户的视图的文件夹。  <br/> |
   
前四个文件夹与 IPM 子树相关，该树是 MAPI 在初始化邮件存储时创建的文件夹树。 交互式邮件客户端的默认邮件存储始终包括 IPM 文件夹子树及其文件夹层次结构中的其他特殊文件夹。 非默认邮件存储仅支持搜索结果根文件夹、IPM 子树根文件夹、"已删除邮件"文件夹和接收文件夹。 为了确保 IPM 子树文件夹存在且有效，客户端可以调用 [HrValidateIPMSubtree](hrvalidateipmsubtree.md) 函数。 **HrValidateIPMSubtree** 检查文件夹，如果出现问题，请重新创建它们。 
  
搜索结果、常见视图和个人视图的根文件夹不是 IPM 子树的一部分;这些文件夹是在邮件存储的根文件夹中创建的。 搜索结果根文件夹包含支持包含满足一组搜索条件的邮件的内容表的文件夹。 尽管允许客户端在任何文件夹中创建搜索结果文件夹，但大多数客户端将单个根文件夹指定为会话期间创建的所有搜索结果文件夹的父文件夹。 
  
常见视图和个人视图根文件夹包含描述视图或显示邮件和文件夹数据的首选方法的邮件。 通用视图根文件夹包含客户端可用于邮件存储中任何文件夹的视图;personal-views 文件夹包含特定用户为特定文件夹定义的视图。
  
使用 IPM 邮件的客户端应在 IPM 子树根文件夹（而不是邮件存储的根文件夹）下创建所有文件夹和邮件。 这为非 IPM 客户端（处理计算机之间或人与计算机之间交换的消息的客户端）提供了一种向 IPM 客户端隐藏其消息的简便方法。 
  
MAPI 为这些特殊文件夹分配特殊条目标识符属性。 有关特殊文件夹条目标识符的列表，请参阅打开 [邮件存储文件夹](opening-a-message-store-folder.md)。
  
### <a name="outlook-special-folders"></a>Outlook特殊文件夹

Outlook特殊文件夹由存储在"收件箱"文件夹和邮件存储的根文件夹中的条目标识。
  
|**Folder**|**要设置的属性**|
|:-----|:-----|
|日历  <br/> |**PR_IPM_APPOINTMENT_ENTRYID (** [PidTagIpmAppointmentEntryId)](pidtagipmappointmententryid-canonical-property.md)  <br/> |
|联系人  <br/> |**PR_IPM_CONTACT_ENTRYID (** [PidTagIpmContactEntryId](pidtagipmcontactentryid-canonical-property.md))   <br/> |
|日志  <br/> |**PR_IPM_JOURNAL_ENTRYID (** [PidTagIpmJournalEntryId](pidtagipmjournalentryid-canonical-property.md))   <br/> |
|备注  <br/> |**PR_IPM_NOTE_ENTRYID (** [PidTagIpmNoteEntryId](pidtagipmnoteentryid-canonical-property.md))   <br/> |
|任务  <br/> |**PR_IPM_TASK_ENTRYID (** [PidTagIpmTaskEntryId)](pidtagipmtaskentryid-canonical-property.md)  <br/> |
|草稿  <br/> |**PR_IPM_DRAFTS_ENTRYID (** [PidTagIpmDraftsEntryId](pidtagipmdraftsentryid-canonical-property.md))   <br/> |
   
## <a name="see-also"></a>另请参阅



[MAPI 文件夹](mapi-folders.md)

