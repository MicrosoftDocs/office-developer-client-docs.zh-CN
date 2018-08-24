---
title: 编写远程查看器
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: f4d7d42f-688a-4199-b972-dd42528c0cdf
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 0125bd57f0f2958c112fb03e7bf4166a7017cd03
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22584763"
---
# <a name="writing-a-remote-viewer"></a>编写远程查看器

**适用于**：Outlook 2013 | Outlook 2016 
  
远程查看器是提供控制的访问存储在另一台计算机上的电子邮件客户端应用程序中的窗口。 此控制的访问可能较慢的通讯链接上运行。 而不是每次用户打开一个文件夹，则检索可用的消息的完整选定内容，远程查看器将首先显示仅邮件头。 用户然后选择 from 标头的完整中显示的消息。 远程查看器客户端可以允许他们他们下载程序之前删除邮件的用户。 
  
## <a name="to-retrieve-the-headers-of-messages-stored-remotely"></a>若要检索的远程存储的邮件头
  
1. 调用[IMAPISession::GetStatusTable](imapisession-getstatustable.md)访问状态表。 
    
2. 调用[IMAPITable::Restrict](imapitable-restrict.md)限制状态表中包含的行到其**PR\_资源\_类型**([PidTagResourceType](pidtagresourcetype-canonical-property.md)) 列设置为 MAPI\_传输\_提供程序。 
    
3. 呼叫[IMAPITable::SetColumns](imapitable-setcolumns.md)状态表中包括以下各列： 
   - **PR\_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md))
   - **PR\_资源\_方法**([PidTagResourceMethods](pidtagresourcemethods-canonical-property.md))
   - **PR\_资源\_类型**， **PR\_提供程序\_显示**([PidTagProviderDisplay](pidtagproviderdisplay-canonical-property.md))
   - **PR\_状态\_代码**([PidTagStatusCode](pidtagstatuscode-canonical-property.md))。
    
4. 调用[HrQueryAllRows](hrqueryallrows.md)检索状态表中的所有行。 
    
5. 传递[IMAPISession::OpenEntry](imapisession-openentry.md)将调用表中的每一行的项标识符。 因为此接口从 MAPI 后台处理程序的过程上下文封送到客户端的过程上下文 — 与接口从通讯簿或消息通常获取不同存储提供程序 — 关于多线程是多个重要的问题。 
    
6. 呼叫状态对象的[IUnknown::QueryInterface](http://msdn.microsoft.com/library/54d5ff80-18db-43f2-b636-f93ac053146d.aspx)方法，传递 IID_IMAPIFolder 接口标识，以检索远程文件夹。 远程文件夹不是整个文件夹实现;它支持仅 folder 方法和属性的子集。 支持以下属性检索所需的方法， [IMAPIProp::GetProps](imapiprop-getprops.md)，之一：
    
    |||
    |:-----|:-----|
    |**PR\_访问**([PidTagAccess](pidtagaccess-canonical-property.md))  <br/> |**PR_ACCESS_LEVEL**([PidTagAccessLevel](pidtagaccesslevel-canonical-property.md))  <br/> |
    |**PR_CONTENT_COUNT**([PidTagContentCount](pidtagcontentcount-canonical-property.md))  <br/> |**PR_ASSOC_CONTENT_COUNT**([PidTagAssociatedContentCount](pidtagassociatedcontentcount-canonical-property.md))  <br/> |
    |**PR_FOLDER_TYPE**([PidTagFolderType](pidtagfoldertype-canonical-property.md))  <br/> |**PR_OBJECT_TYPE**([PidTagObjectType](pidtagobjecttype-canonical-property.md))  <br/> |
    |**PR\_子文件夹**([PidTagSubfolders](pidtagsubfolders-canonical-property.md))  <br/> |**PR_CREATION_TIME**([PidTagCreationTime](pidtagcreationtime-canonical-property.md))  <br/> |
    |**PR_DISPLAY_NAME**([PidTagDisplayName](pidtagdisplayname-canonical-property.md))  <br/> |**PR_DISPLAY_TYPE**([PidTagDisplayType](pidtagdisplaytype-canonical-property.md))  <br/> |
    
    远程文件夹还必须支持[IMAPIProp::GetPropList](imapiprop-getproplist.md)、 [IMAPIContainer::GetContentsTable](imapicontainer-getcontentstable.md)和[IMAPIFolder::SetMessageStatus](imapifolder-setmessagestatus.md)方法。 远程文件夹内容表通常支持下列： 
        
    |||
    |:-----|:-----|
    |**PR\_显示\_收件人**([PidTagDisplayTo](pidtagdisplayto-canonical-property.md))  <br/> |**PR\_ENTRYID** <br/> |
    |**PR\_HASATTACH** ([PidTagHasAttachments](pidtaghasattachments-canonical-property.md))  <br/> |**PR_IMPORTANCE**([PidTagImportance](pidtagimportance-canonical-property.md))  <br/> |
    |**PR_INSTANCE_KEY**([PidTagInstanceKey](pidtaginstancekey-canonical-property.md))  <br/> |**PR_MESSAGE_CLASS**([PidTagMessageClass](pidtagmessageclass-canonical-property.md))  <br/> |
    |**PR\_MESSAGE_DELIVERY_TIME** ([PidTagMessageDeliveryTime](pidtagmessagedeliverytime-canonical-property.md))  <br/> |**PR_MESSAGE_FLAGS**([PidTagMessageFlags](pidtagmessageflags-canonical-property.md))  <br/> |
    |**PR\_MESSAGE_DOWNLOAD_TIME** ([PidTagMessageDownloadTime](pidtagmessagedownloadtime-canonical-property.md))  <br/> |**PR_MESSAGE_SIZE**([PidTagMessageSize](pidtagmessagesize-canonical-property.md))  <br/> |
    |**PR_MSG_STATUS**([PidTagMessageStatus](pidtagmessagestatus-canonical-property.md))  <br/> |**PR_OBJECT_TYPE** <br/> |
    |**PR_NORMALIZED_SUBJECT**([PidTagNormalizedSubject](pidtagnormalizedsubject-canonical-property.md))  <br/> |**PR_PRIORITY**([PidTagPriority](pidtagpriority-canonical-property.md))  <br/> |
    |**PR_SENDER_NAME**([PidTagSenderName](pidtagsendername-canonical-property.md))  <br/> |**PR_SENSITIVITY**([PidTagSensitivity](pidtagsensitivity-canonical-property.md))  <br/> |
    |**PR\_SENT_REPRESENTING_NAME** ([PidTagSentRepresentingName](pidtagsentrepresentingname-canonical-property.md))  <br/> |**PR_SUBJECT**([PidTagSubject](pidtagsubject-canonical-property.md))  <br/> |
   
7. 呼叫转接选项之一选取的传输提供程序的[IMAPIStatus::ValidateState](imapistatus-validatestate.md)方法第一个时间。 REFRESH_XP_HEADER_CACHE 或 PROCESS_XP_HEADER_CACHE 过程标志应以及 SHOW_XP_SSESSION_UI 标志设置，以允许用户界面以显示。 
    
   > [!NOTE]
   > 若要标记下载或删除的特定邮件头，客户端调用[IMAPIFolder::SetMessageStatus](imapifolder-setmessagestatus.md) ，并设置 MSGSTATUS_REMOTE_DOWNLOAD 或 MSGSTATUS_REMOTE_DELETE 标志。 
  

