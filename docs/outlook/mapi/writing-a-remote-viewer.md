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
ms.openlocfilehash: 1d7fea7f92a315b9671d17c82a82d5d7d180f4bb
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32325660"
---
# <a name="writing-a-remote-viewer"></a>编写远程查看器

**适用于**：Outlook 2013 | Outlook 2016 
  
远程查看器是客户端应用程序中提供对存储在另一台计算机的邮件的受控访问权限的窗口。 这种受控访问可能在慢速通信链接上运行。 远程查看器不是每次用户打开文件夹时检索可用邮件的完整选择，而是首先仅显示邮件头。 然后，用户从标题中选择要完整显示哪些邮件。 远程查看器客户端可以允许用户在下载邮件之前删除邮件。 
  
## <a name="to-retrieve-the-headers-of-messages-stored-remotely"></a>检索远程存储的邮件头
  
1. 调用 [IMAPISession：：GetStatusTable](imapisession-getstatustable.md) 以访问状态表。 
    
2. 调用 [IMAPITable：：Restrict](imapitable-restrict.md) 以将状态表限制为仅其 PR **\_ 资源 \_** 类型为 ([PidTagResourceType](pidtagresourcetype-canonical-property.md)) 列设置为 MAPI TRANSPORT \_ PROVIDER 的 \_ 行。 
    
3. 调用 [IMAPITable：：SetColumns](imapitable-setcolumns.md) 以在状态表中包括以下列： 
   - **PR \_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 
   - **PR \_RESOURCE \_ 方法** ([PidTagResourceMethods)](pidtagresourcemethods-canonical-property.md)
   - **PR \_资源 \_ 类型** **，PR \_ PROVIDER \_ DISPLAY (** [PidTagProviderDisplay](pidtagproviderdisplay-canonical-property.md)) 
   - **PR \_STATUS \_ CODE (** [PidTagStatusCode](pidtagstatuscode-canonical-property.md)) 。
    
4. 调用 [HrQueryAllRows](hrqueryallrows.md) 以检索状态表中的所有行。 
    
5. 对 [IMAPISession：：OpenEntry](imapisession-openentry.md)的调用中传递表中每一行的条目标识符。 由于此接口从 MAPI 后台处理程序的进程上下文封送到客户端的进程上下文（与通常从通讯簿或邮件存储提供程序获取的接口不同）与多线程处理有关的问题更加重要。 
    
6. 调用 status 对象的 [IUnknown：：QueryInterface](https://msdn.microsoft.com/library/54d5ff80-18db-43f2-b636-f93ac053146d.aspx) 方法（将IID_IMAPIFolder作为接口标识符传递）以检索远程文件夹。 远程文件夹不是完整的文件夹实现;它仅支持文件夹方法和属性的子集。 所需方法之一 [IMAPIProp：：GetProps](imapiprop-getprops.md)支持检索以下属性：
    
    |||
    |:-----|:-----|
    |**PR \_ACCESS** ([PidTagAccess)](pidtagaccess-canonical-property.md)  <br/> |**PR_ACCESS_LEVEL (** [PidTagAccessLevel](pidtagaccesslevel-canonical-property.md))   <br/> |
    |**PR_CONTENT_COUNT (** [PidTagContentCount](pidtagcontentcount-canonical-property.md))   <br/> |**PR_ASSOC_CONTENT_COUNT (** [PidTagAssociatedContentCount](pidtagassociatedcontentcount-canonical-property.md))   <br/> |
    |**PR_FOLDER_TYPE (** [PidTagFolderType)](pidtagfoldertype-canonical-property.md)  <br/> |**PR_OBJECT_TYPE (** [PidTagObjectType](pidtagobjecttype-canonical-property.md))   <br/> |
    |**PR \_SUBFOLDERS** ([PidTagSubfolders](pidtagsubfolders-canonical-property.md))   <br/> |**PR_CREATION_TIME (** [PidTagCreationTime](pidtagcreationtime-canonical-property.md))   <br/> |
    |**PR_DISPLAY_NAME (** [PidTagDisplayName](pidtagdisplayname-canonical-property.md))   <br/> |**PR_DISPLAY_TYPE (** [PidTagDisplayType](pidtagdisplaytype-canonical-property.md))   <br/> |
    
    远程文件夹还必须支持[IMAPIProp：：GetPropList、IMAPIContainer：：GetContentsTable](imapiprop-getproplist.md)和[IMAPIFolder：：SetMessageStatus](imapifolder-setmessagestatus.md)方法。 [](imapicontainer-getcontentstable.md) 远程文件夹内容表通常支持以下列： 
        
    |||
    |:-----|:-----|
    |**PR \_显示 \_ 到** ([PidTagDisplayTo](pidtagdisplayto-canonical-property.md))   <br/> |**PR \_ ENTRYID** <br/> |
    |**PR \_HASATTACH** ([PidTagHasAttachments)](pidtaghasattachments-canonical-property.md)  <br/> |**PR_IMPORTANCE (** [PidTagImportance)](pidtagimportance-canonical-property.md)  <br/> |
    |**PR_INSTANCE_KEY (** [PidTagInstanceKey](pidtaginstancekey-canonical-property.md))   <br/> |**PR_MESSAGE_CLASS (** [PidTagMessageClass](pidtagmessageclass-canonical-property.md))   <br/> |
    |**PR \_MESSAGE_DELIVERY_TIME (** [PidTagMessageDeliveryTime](pidtagmessagedeliverytime-canonical-property.md))   <br/> |**PR_MESSAGE_FLAGS (** [PidTagMessageFlags](pidtagmessageflags-canonical-property.md))   <br/> |
    |**PR \_MESSAGE_DOWNLOAD_TIME (** [PidTagMessageDownloadTime)](pidtagmessagedownloadtime-canonical-property.md)  <br/> |**PR_MESSAGE_SIZE (** [PidTagMessageSize](pidtagmessagesize-canonical-property.md))   <br/> |
    |**PR_MSG_STATUS (** [PidTagMessageStatus)](pidtagmessagestatus-canonical-property.md)  <br/> |**PR_OBJECT_TYPE** <br/> |
    |**PR_NORMALIZED_SUBJECT (** [PidTagNormalizedSubject)](pidtagnormalizedsubject-canonical-property.md)  <br/> |**PR_PRIORITY (** [PidTagPriority)](pidtagpriority-canonical-property.md)  <br/> |
    |**PR_SENDER_NAME (** [PidTagSenderName](pidtagsendername-canonical-property.md))   <br/> |**PR_SENSITIVITY (** [PidTagSensitivity)](pidtagsensitivity-canonical-property.md)  <br/> |
    |**PR \_SENT_REPRESENTING_NAME (** [PidTagSentRepresentingName)](pidtagsentrepresentingname-canonical-property.md)  <br/> |**PR_SUBJECT (** [PidTagSubject)](pidtagsubject-canonical-property.md)  <br/> |
   
7. 首次选择其中一个传输选项时，调用传输提供程序的 [IMAPIStatus：：ValidateState](imapistatus-validatestate.md) 方法。 应REFRESH_XP_HEADER_CACHE或PROCESS_XP_HEADER_CACHE进程标记以及 SHOW_XP_SSESSION_UI 标志来显示用户界面。 
    
   > [!NOTE]
   > 为了标记要下载或删除的特定邮件头，客户端调用 [IMAPIFolder：：SetMessageStatus](imapifolder-setmessagestatus.md) 并设置 MSGSTATUS_REMOTE_DOWNLOAD 或 MSGSTATUS_REMOTE_DELETE 标志。 
  

