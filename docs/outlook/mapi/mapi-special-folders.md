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
ms.openlocfilehash: 396a6c01d0b9cd867706a7dd4997bd6ddd7fd147
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22578288"
---
# <a name="mapi-special-folders"></a>MAPI 特殊文件夹

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
MAPI 定义几个是特殊的因为它们提供作为默认文件夹的预定义的角色的某些类型的邮件的文件夹。 通常不能删除这些特殊文件夹，并且其特殊的项标识符的属性。
  
有八个特殊文件夹的一部分的人际邮件 (IPM) 子树。 MAPI 客户端获得访问其消息存储库，其后客户端可能导致无法删除文件夹，如有必要之前创建这些文件夹。 某些消息存储提供程序允许删除，而有些则没有。 下表介绍这些文件夹。
  
**MAPI 文件夹**

|**Folder**|**说明**|
|:-----|:-----|
|发件箱文件夹  <br/> |包含传出 IPM 消息。  <br/> |
|已删除的项目文件夹  <br/> |包含 IPM 邮件标记为删除。  <br/> |
|发送的项目文件夹  <br/> |包含 IPM 已发送的邮件。  <br/> |
|IPM 根文件夹  <br/> |包含用于管理 IPM 邮件文件夹。  <br/> |
|接收文件夹  <br/> |包含为特定邮件类的传入消息。  <br/> |
|搜索结果的根文件夹  <br/> |包含用于管理搜索结果的文件夹。  <br/> |
|常见视图的根文件夹  <br/> |包含用于管理消息存储库视图的文件夹。  <br/> |
|个人视图的根文件夹  <br/> |包含用于管理特定用户的视图的文件夹。  <br/> |
   
与 IPM 子树，MAPI 创建初始化的消息存储时的文件夹的树相关的前四个文件夹。 交互式消息客户端的默认邮件存储始终包括 IPM 文件夹子树和其他特殊文件夹，其文件夹层次结构中。 非默认的消息存储仅需要支持的搜索结果的根文件夹、 IPM 子树的根文件夹、 已删除邮件文件夹中和接收文件夹。 若要确保 IPM 子树文件夹存在和有效，客户端可以调用[HrValidateIPMSubtree](hrvalidateipmsubtree.md)函数。 **HrValidateIPMSubtree**检查文件夹，并重新创建这些问题时。 
  
不属于 IPM 子树; 搜索结果、 公共视图和个人视图的根文件夹。消息存储库的根文件夹中创建这些文件夹。 搜索结果的根文件夹包含支持内容表包含符合搜索条件的一组的邮件的文件夹。 允许的客户端在任何文件夹中创建搜索结果文件夹，尽管大多数客户端指定要将所有搜索结果的父对象的单个根文件夹在会话过程中创建的文件夹。 
  
公共视图和个人视图的根文件夹包含描述视图或来显示邮件和文件夹的数据的首选的方法的消息。 常见视图根文件夹中包含的客户端可以使用任何文件夹中的消息存储; 视图个人视图文件夹包含由特定用户的特定文件夹或文件夹已定义的视图。
  
处理 IPM 邮件的客户端应创建的所有文件夹和 IPM 子树的根文件夹，而不是邮件存储区的根文件夹下的邮件。 这种非 IPM 客户端 — 客户端计算机之间人和计算机或之间交换消息处理 — 用于隐藏 IPM 客户端从其邮件简便方法。 
  
MAPI 将这些特殊文件夹的标识符属性分配特殊的条目。 特殊文件夹项标识符的列表，请参阅[打开邮件存储文件夹](opening-a-message-store-folder.md)。
  
### <a name="outlook-special-folders"></a>Outlook 特殊文件夹

由其条目存储在收件箱文件夹和消息存储库的根文件夹中的 Id 标识 outlook 特殊文件夹。
  
|**Folder**|**要设置的属性**|
|:-----|:-----|
|日历  <br/> |**PR_IPM_APPOINTMENT_ENTRYID**([PidTagIpmAppointmentEntryId](pidtagipmappointmententryid-canonical-property.md))  <br/> |
|联系人  <br/> |**PR_IPM_CONTACT_ENTRYID**([PidTagIpmContactEntryId](pidtagipmcontactentryid-canonical-property.md))  <br/> |
|日记  <br/> |**PR_IPM_JOURNAL_ENTRYID**([PidTagIpmJournalEntryId](pidtagipmjournalentryid-canonical-property.md))  <br/> |
|笔记  <br/> |**PR_IPM_NOTE_ENTRYID**([PidTagIpmNoteEntryId](pidtagipmnoteentryid-canonical-property.md))  <br/> |
|任务  <br/> |**PR_IPM_TASK_ENTRYID**([PidTagIpmTaskEntryId](pidtagipmtaskentryid-canonical-property.md))  <br/> |
|草稿  <br/> |**PR_IPM_DRAFTS_ENTRYID**([PidTagIpmDraftsEntryId](pidtagipmdraftsentryid-canonical-property.md))  <br/> |
   
## <a name="see-also"></a>另请参阅



[MAPI 文件夹](mapi-folders.md)

