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
ms.openlocfilehash: 63b8224ad56e2b9985c9d733e2a3c27c67eb2f7f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776555"
---
# <a name="opening-a-message-store-folder"></a>打开邮件存储文件夹

**适用于**： Outlook 
  
可打开任何文件夹之前，必须提供其条目标识符。 对于大多数文件夹，这意味着检索其**PR_ENTRYID**属性。 对于特殊文件夹，如的一些 IPM 子树文件夹和其他根文件夹，MAPI 定义通过调用的消息存储**IMAPIProp::GetProps**方法可访问的特殊条目标识符属性。 这些条目标识符始终是长期和名，如下所示： 
  
|**Folder**|**项标识符属性**|
|:-----|:-----|
|发件箱文件夹  <br/> |**PR_IPM_OUTBOX_ENTRYID**([PidTagIpmOutboxEntryId](pidtagipmoutboxentryid-canonical-property.md))（仅适用于 IPM 之前的邮件类）  <br/> |
|已删除的项目文件夹  <br/> |**PR_IPM_WASTEBASKET_ENTRYID**([PidTagIpmWastebasketEntryId](pidtagipmwastebasketentryid-canonical-property.md))  <br/> |
|发送的项目文件夹  <br/> |**PR_IPM_SENTMAIL_ENTRYID**([PidTagIpmSentMailEntryId](pidtagipmsentmailentryid-canonical-property.md))  <br/> |
|IPM 根文件夹  <br/> |**PR_IPM_SUBTREE_ENTRYID**([PidTagIpmSubtreeEntryId](pidtagipmsubtreeentryid-canonical-property.md))  <br/> |
|搜索结果的根文件夹  <br/> |**PR_FINDER_ENTRYID**([PidTagFinderEntryId](pidtagfinderentryid-canonical-property.md))  <br/> |
|常见的视图的根文件夹  <br/> |**PR_COMMON_VIEWS_ENTRYID**([PidTagCommonViewsEntryId](pidtagcommonviewsentryid-canonical-property.md))  <br/> |
|个人视图的根文件夹  <br/> |**PR_VIEWS_ENTRYID**([PidTagViewsEntryId](pidtagviewsentryid-canonical-property.md))  <br/> |
|根联系人文件夹  <br/> |**PR_IPM_CONTACT_ENTRYID**([PidTagIpmContactEntryId](pidtagipmcontactentryid-canonical-property.md))  <br/> |
|根草稿文件夹  <br/> |**PR_IPM_DRAFTS_ENTRYID**([PidTagIpmDraftsEntryId](pidtagipmdraftsentryid-canonical-property.md))  <br/> |
|日记根文件夹  <br/> |**PR_IPM_JOURNAL_ENTRYID**([PidTagIpmJournalEntryId](pidtagipmjournalentryid-canonical-property.md))  <br/> |
|根日历文件夹  <br/> |**PR_IPM_APPOINTMENT_ENTRYID**([PidTagIpmAppointmentEntryId](pidtagipmappointmententryid-canonical-property.md))  <br/> |
|Notes 根文件夹  <br/> |**PR_IPM_NOTE_ENTRYID**([PidTagIpmNoteEntryId](pidtagipmnoteentryid-canonical-property.md))  <br/> |
|任务的根文件夹  <br/> |**PR_IPM_TASK_ENTRYID**([PidTagIpmTaskEntryId](pidtagipmtaskentryid-canonical-property.md))  <br/> |
   
您尝试检索这些特殊条目标识符之一之前，检索**PR\_VALID_FOLDER_MASK**消息存储 ([PidTagValidFolderMask](pidtagvalidfoldermask-canonical-property.md)) 属性。 **PR\_VALID_FOLDER_MASK**是标识哪些特殊的项标识符中存在一个位掩码。 没有为每个特殊文件夹的一位。 如果设置了位，它指示的相应文件夹支持并且有一个有效项标识符。 例如，如果已删除邮件文件夹存在，但具有有效项标识符，该文件夹\_IPM_WASTEBASKET_VALID 位将在**PR_VALID_FOLDER_MASK**中进行设置。 
  
## <a name="open-the-folder-where-all-incoming-messages-of-a-particular-class-are-placed"></a>打开放置的特定类的所有传入邮件的文件夹
  
1. 调用[IMsgStore::GetReceiveFolder](imsgstore-getreceivefolder.md)检索其条目标识符，以指向标识的邮件类的字符字符串_lpszMessageClass_参数设置。 例如，如果您想要打开您 IPM 子树的收件箱，指向_lpszMessageClass_ IPM。 如果您想要打开 IPC 邮件的接收文件夹，请将其指向 IPC 设置。 

   如果没有任何已注册的接收文件夹的邮件类， **GetReceiveFolder**选择其关联的邮件类别匹配的邮件类的最长可能前缀的接收文件夹中传递。 有关详细信息，请参阅[MAPI 接收文件夹](mapi-receive-folders.md)。 
   
   请注意， **PR_IPM_OUTBOX_ENTRYID**属性用于打开仅对 IPM 邮件发件箱文件夹。 如果您打开 IPC 邮件发件箱，而是使用的项标识符其接收文件夹。 传入和传出 IPC 邮件被置于的接收文件夹。 
    
2. 调用四个**OpenEntry**方法，以打开文件夹，并返回可用于访问该接口指针之一。 您可以调用以下方法以打开一个文件夹中的任何一个： 
    
   - [IMAPISession::OpenEntry](imapisession-openentry.md)
    
   - [IMSLogon::OpenEntry](imslogon-openentry.md)
    
   - [IMsgStore::OpenEntry](imsgstore-openentry.md)
    
   - [IMAPIContainer::OpenEntry](imapicontainer-openentry.md)
    
   您选择特定的方法取决于打开的文件夹和时可用的对象。 因为**IMAPISession**方法可以打开任何消息存储的所有文件夹的当前配置文件中，调用此**OpenEntry**时您不知道有关打开的文件夹的任何内容。 如果您知道哪些消息存储库拥有该文件夹，并且您具有对消息存储的指针，调用**IMsgStore::OpenEntry**。 
    
   例如，使用**IMsgStore**方法打开接收文件夹。 如果您有指向消息存储提供程序的登录对象的指针，调用**IMSLogon::OpenEntry**。 因为这些呼叫转直接向消息存储提供程序，而不是通过 MAPI，处理速度更快。 如果您打开的文件夹是已打开文件夹的子文件夹，调用打开文件夹的**IMAPIContainer::OpenEntry**方法。 **IMAPIContainer**方法仅打开当前打开的文件夹的子文件夹并仅方法保证处理短期条目标识符。 
    
3. 如果您希望能够更改以打开文件夹，指定一个访问级别通过设置任一 MAPI\_最佳\_访问或 MAPI\_ **OpenEntry**呼叫中的修改标志。 这些标志为到的消息存储提供程序的建议的 MAPI 授予的访问，最高级别\_最佳\_访问或读/写访问，MAPI 的\_修改，请打开该文件夹时。 

   由于这些标志是只建议，该文件夹可能或不能打开与您预期的访问级别。 通过检索**PR_ACCESS** ([PidTagAccess](pidtagaccess-canonical-property.md)) 属性，您可以确定可以在打开文件夹中执行的操作的范围。 
    
   但是，因为许多消息存储提供程序计算需求，而不是支持它作为文件夹属性或作为其层次结构表中的列上的此属性的值，它检索费时。 另一种策略是尝试执行和返回错误，如有必要所需的任何操作。
    
## <a name="see-also"></a>另请参阅

- [PidTagEntryId 规范属性](pidtagentryid-canonical-property.md) 
- [IMAPIProp::GetProps](imapiprop-getprops.md)

