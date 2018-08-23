---
title: IXPLogonStartMessage
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IXPLogon.StartMessage
api_type:
- COM
ms.assetid: 83c349f7-dcac-4268-befe-fb2bc0cd9c50
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: d9235da7e7ec6ec244ee1a75f4795e9c77ec28bf
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22579947"
---
# <a name="ixplogonstartmessage"></a>IXPLogon::StartMessage

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
启动入站邮件传输提供程序传输到 MAPI 后台处理程序。
  
```cpp
HRESULT StartMessage(
  ULONG ulFlags,
  LPMESSAGE lpMessage,
  ULONG FAR * lpulMsgRef
);
```

## <a name="parameters"></a>参数

 _ulFlags_
  
> [in]保留;必须为零。
    
 _lpMessage_
  
> [in]指向具有读/写权限，由传输提供程序来访问和处理邮件的邮件对象 （表示入站的邮件） 的指针。 传输提供程序返回从**IXPLogon::StartMessage**调用后，该对象保持有效之前。
    
 _lpulMsgRef_
  
> [输出]指向引用值分配给邮件的指针。 将指针返回到传输提供程序之前，MAPI 后台处理程序初始化此值设置为 1。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 呼叫成功或多个预期值返回。
    
## <a name="remarks"></a>注解

MAPI 后台处理程序调用**IXPLogon::StartMessage**方法来启动入站邮件传输提供程序传输到 MAPI 后台处理程序。 传输提供程序开始使用所指的_lpMessage_消息之前，它应通过[IXPLogon::TransportNotify](ixplogon-transportnotify.md)方法调用潜在用于_lpulMsgRef_参数中存储消息引用。 
  
**StartMessage**调用，过程中 MAPI 后台处理程序处理的邮件传输过程中打开的对象的方法，它还处理任何附件。 此处理花费很长时间。 传输提供程序可以[IMAPISupport::SpoolerYield](imapisupport-spooleryield.md)回调函数的 MAPI 后台处理程序经常在过程中调用此处理发布的其他系统任务的 CPU 时间。 
  
收件人的邮件传输提供程序创建的表中的所有收件人都必须都包含所有必需的寻址属性。 如有必要，提供程序可以构造一个自定义的收件人，表示特定收件人。 但是，如果提供程序可能会产生的收件人的条目，其中包含的详细信息，它应这样做。 例如，如果传输提供程序具有足够的信息有关通讯簿提供程序的收件人的格式，它可以为该格式收件人生成的有效条目标识符，它应生成的项标识符。
  
如果收到任何 nontransmittable 属性，则传输提供程序不应存储它们在新邮件。 但是，传输提供程序应将存储在新邮件中收到的所有可传送属性。
  
如果传入邮件送达报告或原件报表及传输提供程序无法[IMAPISupport::StatusRecips](imapisupport-statusrecips.md)方法用于从原始邮件生成报告，提供程序本身也应该填充邮件相应的属性。 但是，传输提供程序无法设置消息的**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 属性。
  
若要保存传入消息中的相应的 MAPI 邮件存储区进行处理之后，传输提供程序，请调用[IMAPIProp::SaveChanges](imapiprop-savechanges.md)方法。 如果传输提供程序没有任何邮件传递到 MAPI 后台处理程序，它可以通过从**StartMessage**调用返回而无需调用**SaveChanges**停止传入消息。
  
返回之前，应释放传输提供程序打开**StartMessage**在呼叫过程中的所有对象。 但是，提供程序不应释放 MAPI 后台处理程序最初在_lpMessage_参数中传递的消息对象。 
  
如果**StartMessage**返回一个错误，过程中的消息不必更改保存年和都将丢失。 在这种情况下，传输提供程序应传递给[IMAPISupport::SpoolerNotify](imapisupport-spoolernotify.md)方法的调用 NOTIFY_CRITICAL_ERROR 标志，并调用[IXPLogon::Poll](ixplogon-poll.md)方法以通知处于严重错误条件 MAPI 后台处理程序。 
  
有关详细信息，请参阅[与 MAPI 后台处理程序的交互](interacting-with-the-mapi-spooler.md)。 
  
## <a name="see-also"></a>另请参阅



[IMAPIProp::SaveChanges](imapiprop-savechanges.md)
  
[IMAPISupport::SpoolerNotify](imapisupport-spoolernotify.md)
  
[IMAPISupport::SpoolerYield](imapisupport-spooleryield.md)
  
[IMAPISupport::StatusRecips](imapisupport-statusrecips.md)
  
[IMessage::GetRecipientTable](imessage-getrecipienttable.md)
  
[IXPLogon::Poll](ixplogon-poll.md)
  
[IXPLogon::TransportNotify](ixplogon-transportnotify.md)
  
[IXPLogon : IUnknown](ixplogoniunknown.md)

