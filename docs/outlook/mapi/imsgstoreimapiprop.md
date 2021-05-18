---
title: IMsgStore IMAPIProp
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMsgStore
api_type:
- COM
ms.assetid: 20090114-b183-4767-8971-a304a9aa47e6
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: af4bf73b58f7723066bb8fad7c087ba0238ceec2
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33422325"
---
# <a name="imsgstore--imapiprop"></a>IMsgStore : IMAPIProp

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
提供对邮件存储信息以及邮件和文件夹的访问权限。
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapidefs.h  <br/> |
|公开者：  <br/> |邮件存储对象  <br/> |
|实现者：  <br/> |邮件存储提供程序  <br/> |
|调用者：  <br/> |客户端应用程序、MAPI 后台处理程序和 MAPI  <br/> |
|接口标识符：  <br/> |IID_IMsgStore  <br/> |
|指针类型：  <br/> |LPMDB  <br/> |
|事务模型：  <br/> |Nontransacted  <br/> |
   
## <a name="vtable-order"></a>Vtable 顺序

|||
|:-----|:-----|
|[建议](imsgstore-advise.md) <br/> |注册以接收影响邮件存储的指定事件的通知。  <br/> |
|[非企业](imsgstore-unadvise.md) <br/> |取消发送以前通过调用 **IMsgStore：：Advise** 方法设置的通知。  <br/> |
|[CompareEntryIDs](imsgstore-compareentryids.md) <br/> |比较两个条目标识符以确定它们是否引用邮件存储中的同一条目。  <br/> |
|[OpenEntry](imsgstore-openentry.md) <br/> |打开文件夹或邮件并返回接口指针以进一步访问。  <br/> |
|[SetReceiveFolder](imsgstore-setreceivefolder.md) <br/> |建立一个文件夹作为特定邮件类的传入邮件的目标。  <br/> |
|[GetReceiveFolder](imsgstore-getreceivefolder.md) <br/> |获取已建立为指定邮件类的传入邮件的目标或作为邮件存储的默认接收文件夹的文件夹。  <br/> |
|[GetReceiveFolderTable](imsgstore-getreceivefoldertable.md) <br/> |提供对接收文件夹表的访问权限，该表包含有关邮件存储的所有接收文件夹的信息。  <br/> |
|[StoreLogoff](imsgstore-storelogoff.md) <br/> |启用邮件存储的有序注销。  <br/> |
|[AbortSubmit](imsgstore-abortsubmit.md) <br/> |尝试从传出队列中删除邮件。  <br/> |
|[GetOutgoingQueue](imsgstore-getoutgoingqueue.md) <br/> |提供对传出队列表的访问，该表包含有关邮件存储的传出队列中所有邮件的信息。  <br/> |
|[SetLockState](imsgstore-setlockstate.md) <br/> |锁定或解锁邮件。  <br/> |
|[FinishedMsg](imsgstore-finishedmsg.md) <br/> |使邮件存储提供程序能够对已发送的邮件执行处理。  <br/> |
|[NotifyNewMail](imsgstore-notifynewmail.md) <br/> |通知邮件存储新邮件已到达。  <br/> |
   
|**必需属性**|**访问级别**|
|:-----|:-----|
|**PR_DISPLAY_NAME (** [PidTagDisplayName](pidtagdisplayname-canonical-property.md))   <br/> |读/写  <br/> |
|**PR_ENTRYID (** [PidTagEntryId](pidtagentryid-canonical-property.md))   <br/> |只读  <br/> |
|**PR_OBJECT_TYPE (** [PidTagObjectType](pidtagobjecttype-canonical-property.md))   <br/> |只读  <br/> |
|**PR_RECORD_KEY (** [PidTagRecordKey)](pidtagrecordkey-canonical-property.md)  <br/> |只读  <br/> |
|**PR_STORE_ENTRYID (** [PidTagStoreEntryId)](pidtagstoreentryid-canonical-property.md)  <br/> |只读  <br/> |
|**PR_STORE_RECORD_KEY (** [PidTagStoreRecordKey)](pidtagstorerecordkey-canonical-property.md)  <br/> |只读  <br/> |
|**PR_MDB_PROVIDER (** [PidTagStoreProvider](pidtagstoreprovider-canonical-property.md))   <br/> |只读  <br/> |
|**PR_STORE_SUPPORT_MASK (** [PidTagStoreSupportMask)](pidtagstoresupportmask-canonical-property.md)  <br/> |只读  <br/> |
   
以下属性用于 IPM (邮件) 邮件：
  
- **PR_IPM_OUTBOX_ENTRYID (** [PidTagIpmOutboxEntryId](pidtagipmoutboxentryid-canonical-property.md)) 
    
- **PR_IPM_SENTMAIL_ENTRYID (** [PidTagIpmSentMailEntryId](pidtagipmsentmailentryid-canonical-property.md)) 
    
- **PR_IPM_SUBTREE_ENTRYID (** [PidTagIpmSubtreeEntryId](pidtagipmsubtreeentryid-canonical-property.md)) 
    
- **PR_IPM_WASTEBASKET_ENTRYID (** [PidTagIpmWastebasketEntryId](pidtagipmwastebasketentryid-canonical-property.md)) 
    
- **PR_MDB_PROVIDER**
    
- **PR_STORE_SUPPORT_MASK**
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)

