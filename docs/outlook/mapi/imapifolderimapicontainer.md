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
ms.openlocfilehash: 1886987515f3cafe38418960baa4b6fd89e3b6f2
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22590797"
---
# <a name="imapifolder--imapicontainer"></a>IMAPIFolder : IMAPIContainer

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
在文件夹中执行操作的消息和子文件夹。
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapidefs.h  <br/> |
|由公开：  <br/> |文件夹对象  <br/> |
|通过实现：  <br/> |消息存储提供程序  <br/> |
|调用：  <br/> |客户端应用程序和 MAPI  <br/> |
|接口标识符：  <br/> |IID_IMAPIFolder  <br/> |
|指针类型：  <br/> |LPMAPIFOLDER  <br/> |
|事务模型：  <br/> |Nontransacted  <br/> |
   
## <a name="vtable-order"></a>Vtable 顺序排列

|||
|:-----|:-----|
|[CreateMessage](imapifolder-createmessage.md) <br/> |创建新邮件。  <br/> |
|[CopyMessages](imapifolder-copymessages.md) <br/> |复制或移动一个或多条消息。  <br/> |
|[DeleteMessages](imapifolder-deletemessages.md) <br/> |删除一个或多个邮件。  <br/> |
|[CreateFolder](imapifolder-createfolder.md) <br/> |创建新的子文件夹。  <br/> |
|[CopyFolder](imapifolder-copyfolder.md) <br/> |复制或移动的子文件夹。  <br/> |
|[DeleteFolder](imapifolder-deletefolder.md) <br/> |删除子文件夹。  <br/> |
|[SetReadFlags](imapifolder-setreadflags.md) <br/> |设置或清除 MSGFLAG_READ 标志中的一个或多个文件夹的邮件的**PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) 属性并管理阅读报告的发送。  <br/> |
|[GetMessageStatus](imapifolder-getmessagestatus.md) <br/> |获取与特定文件夹中的邮件关联的状态。  <br/> |
|[SetMessageStatus](imapifolder-setmessagestatus.md) <br/> |设置与消息关联的状态。  <br/> |
|[SaveContentsSort](imapifolder-savecontentssort.md) <br/> |设置某个文件夹的内容表的默认排序次序。  <br/> |
|[EmptyFolder](imapifolder-emptyfolder.md) <br/> |删除所有消息和子文件夹从文件夹而不删除该文件夹本身。  <br/> |
   
|**必需属性**|**Access**|
|:-----|:-----|
|**PR_DISPLAY_NAME**([PidTagDisplayNamePrefix](pidtagdisplaynameprefix-canonical-property.md))  <br/> |读/写  <br/> |
|**PR_ENTRYID**([PidTagEntryId](pidtagentryid-canonical-property.md))  <br/> |只读  <br/> |
|**PR_FOLDER_TYPE**([PidTagFolderType](pidtagfoldertype-canonical-property.md))  <br/> |读/写  <br/> |
|**PR_OBJECT_TYPE**([PidTagObjectType](pidtagobjecttype-canonical-property.md))  <br/> |只读  <br/> |
|**PR_PARENT_ENTRYID**([PidTagParentEntryId](pidtagparententryid-canonical-property.md))  <br/> |只读  <br/> |
|**PR_RECORD_KEY**([PidTagRecordKey](pidtagrecordkey-canonical-property.md))  <br/> |只读  <br/> |
|**PR_STORE_ENTRYID**([PidTagStoreEntryId](pidtagstoreentryid-canonical-property.md))  <br/> |只读  <br/> |
|**PR_STORE_RECORD_KEY**([PidTagStoreRecordKey](pidtagstorerecordkey-canonical-property.md))  <br/> |只读  <br/> |
   
## <a name="see-also"></a>另请参阅



[MAPI 接口](mapi-interfaces.md)

