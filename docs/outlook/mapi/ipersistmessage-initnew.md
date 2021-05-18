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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 9f70b178e7c30e1cdf94b485c77f80374113211c
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32317148"
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
  
> [in]指向表单用于处理查看器中邮件的消息网站的指针。
    
 _pMessage_
  
> [in]指向新邮件的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功初始化新邮件。
    
## <a name="remarks"></a>备注

当用户写入属于表单处理的邮件类的新邮件时，表单查看者将调用 **IPersistMessage：：InitNew** 方法。 如果窗体对象具有有效的用户界面指针，应显示消息对象的用户界面。 
  
 当表单除未初始化状态之外的任何状态时，不应调用 **InitNew。** [](uninitialized-state.md) 如果调用 **InitNew** 时窗体位于其他状态之一，则返回E_UNEXPECTED。 
  
## <a name="notes-to-implementers"></a>针对实现者的说明

通常，将具有未保存属性的邮件标记为已修改，以便客户端可以显示一个对话框，提示用户是否应该保存这些属性。 如果用户指示应保存邮件，请保存数据，将邮件标记为干净并正常退出。
  
但是，如果对新初始化的邮件的处理包括设置一个或多个计算属性，并且保存这些属性非常重要，请不要将邮件标记为已修改。 由于计算的属性应该对用户不可见，因此不应显示任何对话框。
  
如果您的表单具有对传入 **InitNew** 的活动邮件网站的引用，请释放原始网站，因为它将不再使用。 从  _pMessageSite_ 和  _pMessage_ 参数存储指向邮件网站和邮件的指针，并调用这两个对象的 [IUnknown：：AddRef](https://msdn.microsoft.com/library/b4316efd-73d4-4995-b898-8025a316ba63%28Office.15%29.aspx) 方法来增加其引用计数。 
  
将 **新邮件** 的 PR_MESSAGE_FLAGS ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) 和 **PR_MSG_STATUS** ([PidTagMessageStatus](pidtagmessagestatus-canonical-property.md)) 属性设置为适用于邮件类的信息。 例如，许多邮件类 **将PR_MESSAGE_FLAGS设置为** MSGFLAG_UNSENT的新邮件。 
  
在返回之前，如果未发生错误，将窗体转换为 [Normal](normal-state.md) 状态。 通过调用所有注册的查看者 [IMAPIViewAdviseSink：：OnNewMessage](imapiviewadvisesink-onnewmessage.md) 方法并返回新消息S_OK。 
  
## <a name="notes-to-callers"></a>给调用方的说明

成功调用 **InitNew** 后，可以假定为表单设置了以下必需属性，而未设置其他属性：
  
 **PR_DELETE_AFTER_SUBMIT (** [PidTagDeleteAfterSubmit](pidtagdeleteaftersubmit-canonical-property.md)) 
  
 **PR_IMPORTANCE (** [PidTagImportance)](pidtagimportance-canonical-property.md)
  
 **PR_ORIGINATOR_DELIVERY_REPORT_REQUESTED (** [PidTagOriginatorDeliveryReportRequested)](pidtagoriginatordeliveryreportrequested-canonical-property.md)
  
 **PR_PRIORITY (** [PidTagPriority)](pidtagpriority-canonical-property.md)
  
 **PR_READ_RECEIPT_REQUESTED (** [PidTagReadReceiptRequested)](pidtagreadreceiptrequested-canonical-property.md)
  
 **PR_SENSITIVITY (** [PidTagSensitivity)](pidtagsensitivity-canonical-property.md)
  
 **PR_SENTMAIL_ENTRYID (** [PidTagSentMailEntryId](pidtagsentmailentryid-canonical-property.md)) 
  
有关表单状态的信息，请参阅窗体 [状态](form-states.md)。 有关存储对象的初始化方式详细信息，请参阅 [IPersistStorage：：InitNew](https://msdn.microsoft.com/library/79caf1f6-d974-4aee-8563-eda4876a0a90%28Office.15%29.aspx) 方法。 
  
## <a name="see-also"></a>另请参阅



[IPersistMessage : IUnknown](ipersistmessageiunknown.md)

