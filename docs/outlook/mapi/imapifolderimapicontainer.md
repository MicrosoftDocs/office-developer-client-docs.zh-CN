---
title: IMAPIFolder IMAPIContainer
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIFolder
api_type:
- COM
ms.assetid: bc2e8d17-7687-43c2-8f01-b677703f7288
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 5e31896354141999e02f2cba117ef9739340be61
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33424236"
---
# <a name="imapifolder--imapicontainer"></a>IMAPIFolder : IMAPIContainer

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
对文件夹中的邮件和子文件夹执行操作。
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapidefs.h  <br/> |
|公开者：  <br/> |Folder 对象  <br/> |
|实现者：  <br/> |邮件存储提供程序  <br/> |
|调用者：  <br/> |客户端应用程序和 MAPI  <br/> |
|接口标识符：  <br/> |IID_IMAPIFolder  <br/> |
|指针类型：  <br/> |LPMAPIFOLDER  <br/> |
|事务模型：  <br/> |Nontransacted  <br/> |
   
## <a name="vtable-order"></a>Vtable 顺序

|||
|:-----|:-----|
|[CreateMessage](imapifolder-createmessage.md) <br/> |创建新邮件。  <br/> |
|[CopyMessages](imapifolder-copymessages.md) <br/> |复制或移动一个或多个邮件。  <br/> |
|[DeleteMessages](imapifolder-deletemessages.md) <br/> |删除一个或多个邮件。  <br/> |
|[CreateFolder](imapifolder-createfolder.md) <br/> |创建新的子文件夹。  <br/> |
|[CopyFolder](imapifolder-copyfolder.md) <br/> |复制或移动子文件夹。  <br/> |
|[DeleteFolder](imapifolder-deletefolder.md) <br/> |删除子文件夹。  <br/> |
|[SetReadFlags](imapifolder-setreadflags.md) <br/> |设置或清除文件夹的一个或多个邮件的 **PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) 属性中的 MSGFLAG_READ 标志，并管理读取报表的发送。  <br/> |
|[GetMessageStatus](imapifolder-getmessagestatus.md) <br/> |获取与特定文件夹中的邮件相关联的状态。  <br/> |
|[SetMessageStatus](imapifolder-setmessagestatus.md) <br/> |设置与邮件关联的状态。  <br/> |
|[SaveContentsSort](imapifolder-savecontentssort.md) <br/> |设置文件夹的内容表的默认排序顺序。  <br/> |
|[EmptyFolder](imapifolder-emptyfolder.md) <br/> |从文件夹中删除所有邮件和子文件夹，而不删除文件夹本身。  <br/> |
   
|**必需属性**|**Access**|
|:-----|:-----|
|**PR_DISPLAY_NAME (** [PidTagDisplayNamePrefix](pidtagdisplaynameprefix-canonical-property.md))   <br/> |读/写  <br/> |
|**PR_ENTRYID (** [PidTagEntryId](pidtagentryid-canonical-property.md))   <br/> |只读  <br/> |
|**PR_FOLDER_TYPE (** [PidTagFolderType)](pidtagfoldertype-canonical-property.md)  <br/> |读/写  <br/> |
|**PR_OBJECT_TYPE (** [PidTagObjectType](pidtagobjecttype-canonical-property.md))   <br/> |只读  <br/> |
|**PR_PARENT_ENTRYID (** [PidTagParentEntryId](pidtagparententryid-canonical-property.md))   <br/> |只读  <br/> |
|**PR_RECORD_KEY (** [PidTagRecordKey)](pidtagrecordkey-canonical-property.md)  <br/> |只读  <br/> |
|**PR_STORE_ENTRYID (** [PidTagStoreEntryId)](pidtagstoreentryid-canonical-property.md)  <br/> |只读  <br/> |
|**PR_STORE_RECORD_KEY (** [PidTagStoreRecordKey)](pidtagstorerecordkey-canonical-property.md)  <br/> |只读  <br/> |
   
## <a name="see-also"></a>另请参阅



[MAPI 接口](mapi-interfaces.md)

