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
  
在可以打开任何文件夹之前，其条目标识符必须可用。 对于大多数文件夹，这意味着 **检索其PR_ENTRYID** 属性。 对于特殊文件夹（如某些 IPM 子树文件夹和其他根文件夹），MAPI 定义可通过调用邮件存储的 **IMAPIProp：：GetProps** 方法访问的特殊条目标识符属性。 这些条目标识符始终是长期标识符，并按如下方式命名： 
  
|**Folder**|**条目标识符属性**|
|:-----|:-----|
|发件箱文件夹  <br/> |**PR_IPM_OUTBOX_ENTRYID (** IPM 邮件类)  ([PidTagIpmOutboxEntryId](pidtagipmoutboxentryid-canonical-property.md))   <br/> |
|“已删除邮件”文件夹  <br/> |**PR_IPM_WASTEBASKET_ENTRYID (** [PidTagIpmWastebasketEntryId](pidtagipmwastebasketentryid-canonical-property.md))   <br/> |
|"已发送项目"文件夹  <br/> |**PR_IPM_SENTMAIL_ENTRYID (** [PidTagIpmSentMailEntryId](pidtagipmsentmailentryid-canonical-property.md))   <br/> |
|IPM 根文件夹  <br/> |**PR_IPM_SUBTREE_ENTRYID (** [PidTagIpmSubtreeEntryId](pidtagipmsubtreeentryid-canonical-property.md))   <br/> |
|搜索结果根文件夹  <br/> |**PR_FINDER_ENTRYID (** [PidTagFinderEntryId](pidtagfinderentryid-canonical-property.md))   <br/> |
|常见视图根文件夹  <br/> |**PR_COMMON_VIEWS_ENTRYID (** [PidTagCommonViewsEntryId)](pidtagcommonviewsentryid-canonical-property.md)  <br/> |
|个人视图根文件夹  <br/> |**PR_VIEWS_ENTRYID (** [PidTagViewsEntryId)](pidtagviewsentryid-canonical-property.md)  <br/> |
|联系人根文件夹  <br/> |**PR_IPM_CONTACT_ENTRYID (** [PidTagIpmContactEntryId](pidtagipmcontactentryid-canonical-property.md))   <br/> |
|草稿根文件夹  <br/> |**PR_IPM_DRAFTS_ENTRYID (** [PidTagIpmDraftsEntryId](pidtagipmdraftsentryid-canonical-property.md))   <br/> |
|日记根文件夹  <br/> |**PR_IPM_JOURNAL_ENTRYID (** [PidTagIpmJournalEntryId](pidtagipmjournalentryid-canonical-property.md))   <br/> |
|日历根文件夹  <br/> |**PR_IPM_APPOINTMENT_ENTRYID (** [PidTagIpmAppointmentEntryId)](pidtagipmappointmententryid-canonical-property.md)  <br/> |
|备注根文件夹  <br/> |**PR_IPM_NOTE_ENTRYID (** [PidTagIpmNoteEntryId](pidtagipmnoteentryid-canonical-property.md))   <br/> |
|任务根文件夹  <br/> |**PR_IPM_TASK_ENTRYID (** [PidTagIpmTaskEntryId)](pidtagipmtaskentryid-canonical-property.md)  <br/> |
   
在尝试检索这些特殊条目标识符之一之前，请检索邮件存储的 **PR \_ VALID_FOLDER_MASK** ([PidTagValidFolderMask](pidtagvalidfoldermask-canonical-property.md)) 属性。 **PR \_VALID_FOLDER_MASK** 是标识存在哪些特殊条目标识符的位掩码。 每个特殊文件夹都有一个位。 如果设置了位，则指示相应的文件夹受支持并且具有有效的条目标识符。 例如，如果"已删除邮件"文件夹存在且具有有效的条目标识符，则 folder IPM_WASTEBASKET_VALID bit 将在 PR_VALID_FOLDER_MASK \_ 中设置。  
  
## <a name="open-the-folder-where-all-incoming-messages-of-a-particular-class-are-placed"></a>打开放置特定类的所有传入邮件的文件夹
  
1. 调用 [IMsgStore：：GetReceiveFolder](imsgstore-getreceivefolder.md) 以检索其条目标识符，将  _lpszMessageClass_ 参数设置为指向标识邮件类的字符串。 例如，如果要打开 IPM 子树的"收件箱"，请指向  _lpszMessageClass_ 到 IPM。 如果要打开 IPC 邮件的接收文件夹，请设置为指向 IPC。 

   如果邮件类没有注册的接收文件夹 **，GetReceiveFolder** 会选择其关联邮件类与传入的邮件类的最长可能前缀匹配的接收文件夹。 有关详细信息，请参阅 [MAPI Receive Folders](mapi-receive-folders.md)。 
   
   请注意 **，PR_IPM_OUTBOX_ENTRYID** 属性仅用于 IPM 邮件的发件箱文件夹。 如果要打开 IPC 邮件的发件箱，请改为使用其接收文件夹的条目标识符。 传入和传出 IPC 邮件都放置在接收文件夹中。 
    
2. 调用四个 **OpenEntry** 方法之一以打开文件夹并返回可用于访问它的接口指针。 可以调用以下任一方法打开文件夹： 
    
   - [IMAPISession::OpenEntry](imapisession-openentry.md)
    
   - [IMSLogon::OpenEntry](imslogon-openentry.md)
    
   - [IMsgStore::OpenEntry](imsgstore-openentry.md)
    
   - [IMAPIContainer::OpenEntry](imapicontainer-openentry.md)
    
   选择的特定方法取决于要打开的文件夹和当时可用的对象。 由于 **IMAPISession** 方法可以打开当前配置文件中任何邮件存储的任何文件夹，因此当您不知道要打开的文件夹的任何信息时，请调用此 **OpenEntry。** 如果你知道哪个邮件存储拥有该文件夹，并且你有一个指向邮件存储的指针，请调用 **IMsgStore：：OpenEntry**。 
    
   例如，使用 **IMsgStore** 方法打开接收文件夹。 如果您有一个指向邮件存储提供程序的登录对象的指针，请调用 **IMSLogon：：OpenEntry**。 由于这些调用直接转到邮件存储提供程序，而不是通过 MAPI，因此处理速度更快。 如果要打开的文件夹是已打开的文件夹的子文件夹，请调用打开文件夹的 **IMAPIContainer：：OpenEntry** 方法。 **IMAPIContainer** 方法仅打开当前打开的文件夹的子文件夹，它是保证使用短期条目标识符的唯一方法。 
    
3. 如果要对要打开的文件夹进行更改，请通过设置 \_ \_ \_ **OpenEntry** 调用中的 MAPI BEST ACCESS 或 MAPI MODIFY 标志来指定访问级别。 这些标志是建议邮件存储提供程序在打开文件夹时授予对 MAPI BEST ACCESS 的最高访问权限级别或对 MAPI MODIFY 的读 \_ \_ / \_ 写访问权限。 

   由于这些标志只是建议，文件夹可能会打开，也可能没有使用您期望的访问级别打开。 通过检索 PR_ACCESS  ([PidTagAccess](pidtagaccess-canonical-property.md)) 属性，可以确定可在打开的文件夹上执行的操作范围。 
    
   但是，因为许多邮件存储提供程序会按需计算此属性的值，而不是作为文件夹属性或层次结构表中的列来支持它，所以检索它可能会很耗时。 备用策略是尝试执行所需的任何操作，并在必要时返回错误。
    
## <a name="see-also"></a>另请参阅

- [PidTagEntryId 规范属性](pidtagentryid-canonical-property.md) 
- [IMAPIProp::GetProps](imapiprop-getprops.md)

