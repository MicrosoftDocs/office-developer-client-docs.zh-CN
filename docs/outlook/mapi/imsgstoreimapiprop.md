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
ms.openlocfilehash: 4ed17fd7f826432da9460fe01e5aa76802726bad
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22584630"
---
# <a name="imsgstore--imapiprop"></a>IMsgStore : IMAPIProp

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
提供对邮件存储信息和邮件和文件夹访问。
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapidefs.h  <br/> |
|由公开：  <br/> |消息存储对象  <br/> |
|通过实现：  <br/> |消息存储提供程序  <br/> |
|调用：  <br/> |客户端应用程序、 MAPI 后台处理程序和 MAPI  <br/> |
|接口标识符：  <br/> |IID_IMsgStore  <br/> |
|指针类型：  <br/> |LPMDB  <br/> |
|事务模型：  <br/> |Nontransacted  <br/> |
   
## <a name="vtable-order"></a>Vtable 顺序排列

|||
|:-----|:-----|
|[建议](imsgstore-advise.md) <br/> |注册接收影响消息存储库的指定事件的通知。  <br/> |
|[取消通知](imsgstore-unadvise.md) <br/> |取消发送通知之前设置与对**IMsgStore::Advise**方法的调用。  <br/> |
|[CompareEntryIDs](imsgstore-compareentryids.md) <br/> |比较两个条目标识符来确定它们是否引用中的消息存储的同一个条目。  <br/> |
|[OpenEntry](imsgstore-openentry.md) <br/> |打开文件夹或消息并返回进一步访问的接口指针。  <br/> |
|[SetReceiveFolder](imsgstore-setreceivefolder.md) <br/> |为特定邮件类别的传入消息的目标建立一个文件夹。  <br/> |
|[GetReceiveFolder](imsgstore-getreceivefolder.md) <br/> |获取时，传入邮件指定的邮件类的或为默认的目标接收的消息存储库文件夹建立的文件夹。  <br/> |
|[GetReceiveFolderTable](imsgstore-getreceivefoldertable.md) <br/> |提供对接收文件夹表中，所有的接收文件夹的邮件存储的信息与表格的访问。  <br/> |
|[StoreLogoff](imsgstore-storelogoff.md) <br/> |允许的邮件存储的有序注销。  <br/> |
|[AbortSubmit](imsgstore-abortsubmit.md) <br/> |尝试从传出队列中删除一条消息。  <br/> |
|[GetOutgoingQueue](imsgstore-getoutgoingqueue.md) <br/> |提供对传出队列表，具有信息的所有邮件的邮件存储传出队列中的表的访问。  <br/> |
|[SetLockState](imsgstore-setlockstate.md) <br/> |锁定或解除锁定一条消息。  <br/> |
|[FinishedMsg](imsgstore-finishedmsg.md) <br/> |启用对已发送的邮件执行处理的消息存储提供程序。  <br/> |
|[NotifyNewMail](imsgstore-notifynewmail.md) <br/> |通知新消息已到达的消息存储。  <br/> |
   
|**必需属性**|**访问级别**|
|:-----|:-----|
|**PR_DISPLAY_NAME**([PidTagDisplayName](pidtagdisplayname-canonical-property.md))  <br/> |读/写  <br/> |
|**PR_ENTRYID**([PidTagEntryId](pidtagentryid-canonical-property.md))  <br/> |只读  <br/> |
|**PR_OBJECT_TYPE**([PidTagObjectType](pidtagobjecttype-canonical-property.md))  <br/> |只读  <br/> |
|**PR_RECORD_KEY**([PidTagRecordKey](pidtagrecordkey-canonical-property.md))  <br/> |只读  <br/> |
|**PR_STORE_ENTRYID**([PidTagStoreEntryId](pidtagstoreentryid-canonical-property.md))  <br/> |只读  <br/> |
|**PR_STORE_RECORD_KEY**([PidTagStoreRecordKey](pidtagstorerecordkey-canonical-property.md))  <br/> |只读  <br/> |
|**PR_MDB_PROVIDER**([PidTagStoreProvider](pidtagstoreprovider-canonical-property.md))  <br/> |只读  <br/> |
|**PR_STORE_SUPPORT_MASK**([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md))  <br/> |只读  <br/> |
   
人际邮件 (IPM) 消息存储库的以下属性：
  
- **PR_IPM_OUTBOX_ENTRYID**([PidTagIpmOutboxEntryId](pidtagipmoutboxentryid-canonical-property.md))
    
- **PR_IPM_SENTMAIL_ENTRYID**([PidTagIpmSentMailEntryId](pidtagipmsentmailentryid-canonical-property.md))
    
- **PR_IPM_SUBTREE_ENTRYID**([PidTagIpmSubtreeEntryId](pidtagipmsubtreeentryid-canonical-property.md))
    
- **PR_IPM_WASTEBASKET_ENTRYID**([PidTagIpmWastebasketEntryId](pidtagipmwastebasketentryid-canonical-property.md))
    
- **PR_MDB_PROVIDER**
    
- **PR_STORE_SUPPORT_MASK**
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)

