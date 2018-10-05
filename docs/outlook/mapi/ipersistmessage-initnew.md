---
title: IPersistMessageInitNew
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IPersistMessage.InitNew
api_type:
- COM
ms.assetid: 4bf37c35-4f72-438a-912c-402f3711a5ea
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 9f70b178e7c30e1cdf94b485c77f80374113211c
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25394879"
---
# <a name="ipersistmessageinitnew"></a>IPersistMessage::InitNew

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
初始化新邮件。
  
```cpp
HRESULT InitNew(
  LPMAPIMESSAGESITE pMessageSite,
  LPMESSAGE pMessage
);
```

## <a name="parameters"></a>参数

 _pMessageSite_
  
> [in]表单将用于处理查看器中邮件消息站点链接。
    
 _pMessage_
  
> [in]一个指向新邮件。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功初始化新邮件。
    
## <a name="remarks"></a>说明

当用户写入属于窗体处理邮件类的新消息时，表单查看器调用**IPersistMessage::InitNew**方法。 如果窗体对象具有一个有效的用户界面指针，应显示的消息对象的用户界面。 
  
 仅当表单处于[未初始化](uninitialized-state.md)状态以外的所有状态时，不应调用**丢失**。 如果表单没有其他状态之一，调用**丢失**时，返回 E_UNEXPECTED。 
  
## <a name="notes-to-implementers"></a>针对实现者的说明

通常情况下，有未保存的属性的邮件被标记为修改，以便客户端可以显示一个对话框，提示用户是否应该保存这些属性。 如果用户指示应保存一条消息，保存数据、 邮件标记为干净，并正常退出。
  
但是，如果新初始化邮件处理包括设置其中一个或多计算属性，并且一点很重要保存这些属性，不要将邮件标记为已修改。 因为计算属性应为对用户不可见，应不显示任何对话框。
  
如果窗体有一个引用传递到**丢失**以外的活动邮件网站，释放原始网站，因为不再使用它。 存储从_pMessageSite_和_pMessage_参数的消息网站和消息的指针和调用这两个对象的[IUnknown::AddRef](https://msdn.microsoft.com/library/b4316efd-73d4-4995-b898-8025a316ba63%28Office.15%29.aspx)方法，以增加其引用计数。 
  
设置为适合于您的邮件类的**PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) 和新邮件的**PR_MSG_STATUS** ([PidTagMessageStatus](pidtagmessagestatus-canonical-property.md)) 属性。 多个邮件类别，例如，设置**PR_MESSAGE_FLAGS**为 MSGFLAG_UNSENT 新邮件。 
  
返回之前, 出现转换为[普通](normal-state.md)状态，如果没有错误窗体。 通过调用其[IMAPIViewAdviseSink::OnNewMessage](imapiviewadvisesink-onnewmessage.md)方法向所有已注册的查看者发送新邮件通知，并返回 S_OK。 
  
## <a name="notes-to-callers"></a>给调用方的说明

所做的**丢失**成功调用后，可以假定以下必需的属性，或任何其他已设置的表单：
  
 **PR_DELETE_AFTER_SUBMIT**([PidTagDeleteAfterSubmit](pidtagdeleteaftersubmit-canonical-property.md))
  
 **PR_IMPORTANCE**([PidTagImportance](pidtagimportance-canonical-property.md))
  
 **邮件已被阅读**([PidTagOriginatorDeliveryReportRequested](pidtagoriginatordeliveryreportrequested-canonical-property.md))
  
 **PR_PRIORITY**([PidTagPriority](pidtagpriority-canonical-property.md))
  
 **PR_READ_RECEIPT_REQUESTED**([PidTagReadReceiptRequested](pidtagreadreceiptrequested-canonical-property.md))
  
 **PR_SENSITIVITY**([PidTagSensitivity](pidtagsensitivity-canonical-property.md))
  
 **PR_SENTMAIL_ENTRYID**([PidTagSentMailEntryId](pidtagsentmailentryid-canonical-property.md))
  
有关窗体的状态的详细信息，请参阅[窗体状态](form-states.md)。 有关如何初始化存储对象的详细信息，请参阅[IPersistStorage::InitNew](https://msdn.microsoft.com/library/79caf1f6-d974-4aee-8563-eda4876a0a90%28Office.15%29.aspx)方法。 
  
## <a name="see-also"></a>另请参阅



[IPersistMessage : IUnknown](ipersistmessageiunknown.md)

