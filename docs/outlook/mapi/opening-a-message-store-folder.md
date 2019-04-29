---
title: 打开邮件存储文件夹
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: d858e4fe-822e-4330-9ed3-4b7d22fa51dc
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: df7db013cb435484c721388abab51ab4ba43828f
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33436536"
---
# <a name="opening-a-message-store-folder"></a>打开邮件存储文件夹

**适用于**：Outlook 2013 | Outlook 2016 
  
在可以打开任何文件夹之前, 必须提供其条目标识符。 对于大多数文件夹, 这意味着检索其**PR_ENTRYID**属性。 对于特殊文件夹 (如一些 IPM 子树文件夹和其他根文件夹), MAPI 定义了可通过调用邮件存储区的**IMAPIProp:: GetProps**方法访问的特殊条目标识符属性。 这些条目标识符始终为长期, 并按如下方式命名: 
  
|**Folder**|**条目标识符属性**|
|:-----|:-----|
|发件箱文件夹  <br/> |**PR_IPM_OUTBOX_ENTRYID**([PidTagIpmOutboxEntryId](pidtagipmoutboxentryid-canonical-property.md))(仅限 IPM 邮件类)  <br/> |
|“已删除邮件”文件夹  <br/> |**PR_IPM_WASTEBASKET_ENTRYID**([PidTagIpmWastebasketEntryId](pidtagipmwastebasketentryid-canonical-property.md))  <br/> |
|"已发送邮件" 文件夹  <br/> |**PR_IPM_SENTMAIL_ENTRYID**([PidTagIpmSentMailEntryId](pidtagipmsentmailentryid-canonical-property.md))  <br/> |
|IPM 根文件夹  <br/> |**PR_IPM_SUBTREE_ENTRYID**([PidTagIpmSubtreeEntryId](pidtagipmsubtreeentryid-canonical-property.md))  <br/> |
|搜索结果根文件夹  <br/> |**PR_FINDER_ENTRYID**([PidTagFinderEntryId](pidtagfinderentryid-canonical-property.md))  <br/> |
|公用视图根文件夹  <br/> |**PR_COMMON_VIEWS_ENTRYID**([PidTagCommonViewsEntryId](pidtagcommonviewsentryid-canonical-property.md))  <br/> |
|个人视图根文件夹  <br/> |**PR_VIEWS_ENTRYID**([PidTagViewsEntryId](pidtagviewsentryid-canonical-property.md))  <br/> |
|联系人根文件夹  <br/> |**PR_IPM_CONTACT_ENTRYID**([PidTagIpmContactEntryId](pidtagipmcontactentryid-canonical-property.md))  <br/> |
|草稿根文件夹  <br/> |**PR_IPM_DRAFTS_ENTRYID**([PidTagIpmDraftsEntryId](pidtagipmdraftsentryid-canonical-property.md))  <br/> |
|日记根文件夹  <br/> |**PR_IPM_JOURNAL_ENTRYID**([PidTagIpmJournalEntryId](pidtagipmjournalentryid-canonical-property.md))  <br/> |
|日历根文件夹  <br/> |**PR_IPM_APPOINTMENT_ENTRYID**([PidTagIpmAppointmentEntryId](pidtagipmappointmententryid-canonical-property.md))  <br/> |
|备注根文件夹  <br/> |**PR_IPM_NOTE_ENTRYID**([PidTagIpmNoteEntryId](pidtagipmnoteentryid-canonical-property.md))  <br/> |
|任务根文件夹  <br/> |**PR_IPM_TASK_ENTRYID**([PidTagIpmTaskEntryId](pidtagipmtaskentryid-canonical-property.md))  <br/> |
   
在尝试检索这些特殊条目标识符之一之前, 请先检索邮件存储区的**\_PR VALID_FOLDER_MASK** ([PidTagValidFolderMask](pidtagvalidfoldermask-canonical-property.md)) 属性。 **PR\_VALID_FOLDER_MASK**是标识存在哪些特殊条目标识符的位掩码。 每个特殊文件夹都有一个位。 如果设置了位, 则表明相应的文件夹受支持且具有有效的条目标识符。 例如, 如果 "已删除邮件" 文件夹存在且具有有效的条目标识符, 则\_将在**PR_VALID_FOLDER_MASK**中设置文件夹 IPM_WASTEBASKET_VALID 位。 
  
## <a name="open-the-folder-where-all-incoming-messages-of-a-particular-class-are-placed"></a>打开在其中放置特定类的所有传入邮件的文件夹
  
1. 调用[IMsgStore:: GetReceiveFolder](imsgstore-getreceivefolder.md)以检索其条目标识符, 并将_lpszMessageClass_参数设置为指向标识邮件类的字符字符串。 例如, 如果要打开 ipm 子树的收件箱, 请将_lpszMessageClass_指向 ipm。 如果要打开接收文件夹中的 IPC 消息, 请将其设置为指向 "ipc"。 

   如果邮件类别没有已注册的接收文件夹, **GetReceiveFolder**将选择其关联邮件类别与传入的邮件类别的最长可能前缀相匹配的接收文件夹。 有关详细信息, 请参阅[MAPI 接收文件夹](mapi-receive-folders.md)。 
   
   请注意, **PR_IPM_OUTBOX_ENTRYID**属性仅用于为 IPM 邮件打开 "发件箱" 文件夹。 如果要打开 IPC 邮件的发件箱, 请改用其接收文件夹的条目标识符。 传入和传出的 IPC 消息都放在接收文件夹中。 
    
2. 调用四个**OpenEntry**方法之一以打开文件夹, 并返回可用于访问该文件夹的接口指针。 您可以调用下列任意一种方法来打开文件夹: 
    
   - [IMAPISession::OpenEntry](imapisession-openentry.md)
    
   - [IMSLogon::OpenEntry](imslogon-openentry.md)
    
   - [IMsgStore::OpenEntry](imsgstore-openentry.md)
    
   - [IMAPIContainer::OpenEntry](imapicontainer-openentry.md)
    
   您选择的具体方法取决于要打开的文件夹以及在该时间可用的对象。 由于**IMAPISession**方法可以打开当前配置文件中任何邮件存储区的任何文件夹, 因此当您不知道要打开的文件夹的任何内容时, 请调用此**OpenEntry** 。 如果您知道哪个邮件存储区拥有该文件夹, 并且您具有指向邮件存储区的指针, 则调用**IMsgStore:: OpenEntry**。 
    
   例如, 使用**IMsgStore**方法打开接收文件夹。 如果您有一个指向邮件存储提供程序的登录对象的指针, 则调用**IMSLogon:: OpenEntry**。 由于这些呼叫直接转到邮件存储提供程序 (而不是通过 MAPI), 因此处理速度更快。 如果要打开的文件夹是已打开的文件夹的子文件夹, 请调用 open 文件夹的**IMAPIContainer:: OpenEntry**方法。 **IMAPIContainer**方法仅打开当前打开的文件夹的子文件夹, 并且是保证使用短期输入标识符的唯一方法。 
    
3. 如果您\_希望能够对要打开的文件夹进行更改, 请通过在**OpenEntry**调用中设置 mapi 最佳\_访问或 mapi\_修改标志来指定访问级别。 这些标志是邮件存储提供程序的建议, 用于在打开文件夹时授予最高级别的\_访问\_权限、mapi 最佳访问或读/写访问\_权限 (用于 mapi 修改)。 

   由于这些标志只是建议, 因此可能会打开文件夹, 也可能无法使用所需的访问级别打开文件夹。 通过检索**PR_ACCESS** ([PidTagAccess](pidtagaccess-canonical-property.md)) 属性, 可以确定可在打开的文件夹上执行的操作的范围。 
    
   但是, 由于许多邮件存储提供程序都按需计算此属性的值, 而不是将其作为 folder 属性或作为其层次结构表中的列进行支持, 因此检索它可能非常耗时。 另一种策略是尝试执行所需的任何操作, 并在必要时返回一个错误。
    
## <a name="see-also"></a>另请参阅

- [PidTagEntryId 规范属性](pidtagentryid-canonical-property.md) 
- [IMAPIProp::GetProps](imapiprop-getprops.md)

