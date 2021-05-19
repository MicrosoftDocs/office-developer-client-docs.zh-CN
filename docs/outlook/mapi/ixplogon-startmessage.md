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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 00273d5572fa0c12a9501a1620db11ea087fd5d1
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33427603"
---
# <a name="ixplogonstartmessage"></a>IXPLogon::StartMessage

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
启动将入站邮件从传输提供程序转移到 MAPI 后台处理程序。
  
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
  
> [in]一个指向邮件 (表示具有读/写) 的入站邮件的指针，传输提供程序使用该对象访问和操作该邮件。 在传输提供程序从对 **IXPLogon：：StartMessage** 的调用中返回之前，此对象一直有效。
    
 _lpulMsgRef_
  
> [out]指向分配给邮件的引用值的指针。 MAPI 后台处理程序在返回指向传输提供程序的指针之前将此值初始化为 1。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功并返回了预期值。
    
## <a name="remarks"></a>备注

MAPI 后台处理程序调用 **IXPLogon：：StartMessage** 方法以启动将入站邮件从传输提供程序转移到 MAPI 后台处理程序。 在传输提供程序开始使用  _lpMessage_ 指向的邮件之前，它应在  _lpulMsgRef_ 参数中存储邮件引用，以通过调用 [IXPLogon：：TransportNotify](ixplogon-transportnotify.md) 方法来可能使用它。 
  
在 **StartMessage** 调用期间，MAPI 后台处理程序处理在邮件传输期间打开的对象的方法，并且还会处理任何附件。 此处理可能需要很长时间。 传输提供程序可以在此处理过程中经常调用 MAPI 后台处理程序的 [IMAPISupport：：SpoolerYield](imapisupport-spooleryield.md) 回调函数，以释放其他系统任务的 CPU 时间。 
  
传输提供程序为邮件创建的收件人表中的所有收件人都必须包含所有必需的寻址属性。 如有必要，提供程序可以构造一个自定义收件人来表示特定收件人。 但是，如果提供程序可以生成包含详细信息的收件人条目，则应该这样做。 例如，如果传输提供程序具有有关通讯簿提供程序的收件人格式的足够信息，可以针对该格式为收件人生成有效的条目标识符，则应该构建条目标识符。
  
如果收到任何不可传输的属性，则传输提供程序不应将它们存储在新邮件中。 但是，传输提供程序应在新邮件中存储其接收的所有可传输属性。
  
如果传入的邮件是送达报告或未送达报告，并且传输提供程序无法使用 [IMAPISupport：：StatusRecips](imapisupport-statusrecips.md) 方法从原始邮件生成报告，则提供程序本身应该使用适当的属性填充邮件。 但是，传输提供程序无法将邮件的 PR_ENTRYID ( [PidTagEntryId](pidtagentryid-canonical-property.md)) 属性。
  
若要在处理后将传入邮件保存在相应的 MAPI 邮件存储中，传输提供程序会调用 [IMAPIProp：：SaveChanges](imapiprop-savechanges.md) 方法。 如果传输提供程序没有任何要传递到 MAPI 后台处理程序的邮件，则可以通过不调用 **SaveChanges** 从 **StartMessage** 调用返回来停止传入邮件。
  
传输提供程序在 **StartMessage** 调用期间打开的所有对象都应在返回之前释放。 但是，提供程序不应释放 MAPI 后台处理程序最初在  _lpMessage_ 参数中传递的消息对象。 
  
如果 **StartMessage** 返回错误，则过程中的消息在未保存更改的情况下释放并丢失。 在这种情况下，传输提供程序应该通过调用 [IMAPISupport：：SpoolerNotify](imapisupport-spoolernotify.md) 方法传递 NOTIFY_CRITICAL_ERROR 标志，并调用 [IXPLogon：:P oll](ixplogon-poll.md) 方法以通知 MAPI 后台处理程序它受到严重错误情况。 
  
有关详细信息，请参阅与 [MAPI 后台处理程序交互](interacting-with-the-mapi-spooler.md)。 
  
## <a name="see-also"></a>另请参阅



[IMAPIProp::SaveChanges](imapiprop-savechanges.md)
  
[IMAPISupport::SpoolerNotify](imapisupport-spoolernotify.md)
  
[IMAPISupport::SpoolerYield](imapisupport-spooleryield.md)
  
[IMAPISupport::StatusRecips](imapisupport-statusrecips.md)
  
[IMessage::GetRecipientTable](imessage-getrecipienttable.md)
  
[IXPLogon::Poll](ixplogon-poll.md)
  
[IXPLogon::TransportNotify](ixplogon-transportnotify.md)
  
[IXPLogon : IUnknown](ixplogoniunknown.md)

