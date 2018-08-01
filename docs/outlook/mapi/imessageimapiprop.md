---
title: IMessage IMAPIProp
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMessage
api_type:
- COM
ms.assetid: 7e244d40-595e-432c-aa8c-f9f62ca3c138
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 9ed02e19a2934f785b03bb8553a08e16c7bb30e0
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775763"
---
# <a name="imessage--imapiprop"></a>IMessage : IMAPIProp

  
  
**适用于**： Outlook 
  
管理邮件、 附件和收件人。
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapidefs.h  <br/> |
|由公开：  <br/> |Message 对象  <br/> |
|通过实现：  <br/> |消息存储提供程序  <br/> |
|调用：  <br/> |客户端应用程序  <br/> |
|接口标识符：  <br/> |IID_IMessage  <br/> |
|指针类型：  <br/> |LPMESSAGE  <br/> |
|事务模型：  <br/> |事务处理  <br/> |
   
## <a name="vtable-order"></a>Vtable 顺序排列

|||
|:-----|:-----|
|[GetAttachmentTable](imessage-getattachmenttable.md) <br/> |返回邮件的附件表。  <br/> |
|[OpenAttach](imessage-openattach.md) <br/> |打开附件。  <br/> |
|[CreateAttach](imessage-createattach.md) <br/> |创建一个新附件。  <br/> |
|[DeleteAttach](imessage-deleteattach.md) <br/> |删除附件。  <br/> |
|[GetRecipientTable](imessage-getrecipienttable.md) <br/> |返回邮件的收件人表。  <br/> |
|[ModifyRecipients](imessage-modifyrecipients.md) <br/> |添加、 删除或修改邮件的收件人。  <br/> |
|[SubmitMessage](imessage-submitmessage.md) <br/> |将所有更改都保存到邮件并将其标记为供发送。  <br/> |
|[SetReadFlag](imessage-setreadflag.md) <br/> |设置或清除 MSGFLAG_READ 标志邮件的**PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) 属性中并管理阅读报告的发送。  <br/> |
   
在其生命周期期间上某一点的邮件需要以下属性。 客户端呼叫消息的[IMAPIProp::SaveChanges](imapiprop-savechanges.md)方法时，大部分只读属性都设置消息存储提供程序。 由传输提供程序设置的其他只读属性。 
  
|**Required 的属性的邮件的所有类**|**Access**|
|:-----|:-----|
|**PR_CREATION_TIME**([PidTagCreationTime](pidtagcreationtime-canonical-property.md))  <br/> |只读  <br/> |
|**PR_DISPLAY_BCC**([PidTagDisplayBcc](pidtagdisplaybcc-canonical-property.md))  <br/> |只读  <br/> |
|**PR_DISPLAY_CC**([PidTagDisplayCc](pidtagdisplaycc-canonical-property.md))  <br/> |只读  <br/> |
|**仅包含显示名称**([PidTagDisplayTo](pidtagdisplayto-canonical-property.md))  <br/> |只读  <br/> |
|**PR_ENTRYID**([PidTagEntryId](pidtagentryid-canonical-property.md))  <br/> |只读  <br/> |
|**操作**([PidTagLastModificationTime](pidtaglastmodificationtime-canonical-property.md))  <br/> |只读  <br/> |
|**PR_MESSAGE_ATTACHMENTS**([PidTagMessageAttachments](pidtagmessageattachments-canonical-property.md))  <br/> |只读  <br/> |
|**PR_MESSAGE_CLASS**([PidTagMessageClass](pidtagmessageclass-canonical-property.md))  <br/> |读/写  <br/> |
|**PR_MESSAGE_FLAGS**([PidTagMessageFlags](pidtagmessageflags-canonical-property.md))  <br/> |读/写  <br/> |
|**PR_MESSAGE_RECIPIENTS**([PidTagMessageRecipients](pidtagmessagerecipients-canonical-property.md))  <br/> |只读  <br/> |
|**PR_MESSAGE_SIZE**([PidTagMessageSize](pidtagmessagesize-canonical-property.md))  <br/> |只读  <br/> |
|**PR_MESSAGE_CC_ME**([PidTagMessageCcMe](pidtagmessageccme-canonical-property.md))  <br/> |只读  <br/> |
|**PR_MESSAGE_RECIP_ME**([PidTagMessageRecipientMe](pidtagmessagerecipientme-canonical-property.md))  <br/> |只读  <br/> |
|**PR_MESSAGE_TO_ME**([PidTagMessageToMe](pidtagmessagetome-canonical-property.md))  <br/> |只读  <br/> |
|**PR_NORMALIZED_SUBJECT**([PidTagNormalizedSubject](pidtagnormalizedsubject-canonical-property.md))  <br/> |只读  <br/> |
|**PR_ORIGINATOR**属性  <br/> |只读  <br/> |
|**PR_PARENT_DISPLAY**([PidTagParentDisplay](pidtagparentdisplay-canonical-property.md))  <br/> |只读  <br/> |
|**PR_PARENT_ENTRYID**([PidTagParentEntryId](pidtagparententryid-canonical-property.md))  <br/> |只读  <br/> |
|**PR_RECEIVED_BY**属性  <br/> |只读  <br/> |
|**PR_RECIPIENT_TYPE**([PidTagRecipientType](pidtagrecipienttype-canonical-property.md))  <br/> |只读  <br/> |
|**PR_RECORD_KEY**([PidTagRecordKey](pidtagrecordkey-canonical-property.md))  <br/> |只读  <br/> |
|**PR_SEARCH_KEY**([PidTagSearchKey](pidtagsearchkey-canonical-property.md))  <br/> |只读  <br/> |
|**PR_SENDER**属性  <br/> |只读  <br/> |
|**PR_STORE_ENTRYID**([PidTagStoreEntryId](pidtagstoreentryid-canonical-property.md))  <br/> |只读  <br/> |
|**PR_STORE_RECORD_KEY**([PidTagStoreRecordKey](pidtagstorerecordkey-canonical-property.md))  <br/> |只读  <br/> |
   
以下属性是只读的客户端， **PR_BODY**除外。 客户端构造此属性，当他们处理报表。
  
|**报告消息属性**|
|:-----|
|**PR_BODY**([PidTagBody](pidtagbody-canonical-property.md))  <br/> |
|**PR_CONVERSATION_INDEX**([PidTagConversationIndex](pidtagconversationindex-canonical-property.md))  <br/> |
|**PR_CONVERSATION_TOPIC**([PidTagConversationTopic](pidtagconversationtopic-canonical-property.md))  <br/> |
|**PR_MESSAGE_CLASS** <br/> |
|**PR_MESSAGE_DELIVERY_TIME**([PidTagMessageDeliveryTime](pidtagmessagedeliverytime-canonical-property.md))  <br/> |
|**PR_ORIGINAL_DELIVERY_TIME**([PidTagOriginalDeliveryTime](pidtagoriginaldeliverytime-canonical-property.md))  <br/> |
|**PR_ORIGINAL_DISPLAY_BCC**([PidTagOriginalDisplayBcc](pidtagoriginaldisplaybcc-canonical-property.md))  <br/> |
|**PR_ORIGINAL_DISPLAY_CC**([PidTagOriginalDisplayCc](pidtagoriginaldisplaycc-canonical-property.md))  <br/> |
|**PR_ORIGINAL_DISPLAY_TO**([PidTagOriginalDisplayTo](pidtagoriginaldisplayto-canonical-property.md))  <br/> |
|**PR_ORIGINAL_SUBJECT**([PidTagOriginalSubject](pidtagoriginalsubject-canonical-property.md))  <br/> |
|**PR_ORIGINAL_SUBMIT_TIME**([PidTagOriginalSubmitTime](pidtagoriginalsubmittime-canonical-property.md))  <br/> |
|**PR_REPORT_TAG**([PidTagReportTag](pidtagreporttag-canonical-property.md))  <br/> |
|**PR_REPORT_TEXT**([PidTagReportText](pidtagreporttext-canonical-property.md))  <br/> |
|**PR_REPORT_TIME**([PidTagReportTime](pidtagreporttime-canonical-property.md))  <br/> |
|**PR_SEARCH_KEY** <br/> |
|**PR_SENDER**属性  <br/> |
|**PR_SUBJECT**([PidTagSubject](pidtagsubject-canonical-property.md))  <br/> |
   
|**邮件收件人属性**|**Access**|**必需或可选**|
|:-----|:-----|:-----|
|**PR_ADDRTYPE**([PidTagAddressType](pidtagaddresstype-canonical-property.md))  <br/> |只读  <br/> |必需  <br/> |
|**PR_DISPLAY_NAME**([PidTagDisplayName](pidtagdisplayname-canonical-property.md))  <br/> |读/写  <br/> |必需  <br/> |
|**PR_DISPLAY_TYPE**([PidTagDisplayType](pidtagdisplaytype-canonical-property.md))  <br/> |读/写  <br/> |必需  <br/> |
|**PR_EMAIL_ADDRESS**([PidTagEmailAddress](pidtagemailaddress-canonical-property.md))  <br/> |只读  <br/> |可选  <br/> |
|**PR_ENTRYID** <br/> |只读  <br/> |必需  <br/> |
|**PR_OBJECT_TYPE**([PidTagObjectType](pidtagobjecttype-canonical-property.md))  <br/> |只读  <br/> |必需  <br/> |
|**PR_SEARCH_KEY** <br/> |只读  <br/> |可选  <br/> |
   

