---
title: IXPLogonTransportNotify
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IXPLogon.TransportNotify
api_type:
- COM
ms.assetid: c712fc17-f436-41cf-9aa3-186c9a86d56e
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 2482dc39d3f1d1568b45dd3de88358e08d190be4
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33428856"
---
# <a name="ixplogontransportnotify"></a>IXPLogon::TransportNotify

**适用于**：Outlook 2013 | Outlook 2016 
  
指示出现传输提供程序请求通知的事件。
  
```cpp
HRESULT TransportNotify(
  ULONG FAR * lpulFlags,
  LPVOID FAR * lppvData
);
```

## <a name="parameters"></a>参数

 _lpulFlags_
  
> [in， out]向通知事件发送信号的标志的位掩码。 以下标志可通过 MAPI 后台处理程序在输入上设置，并且必须在输出上返回未更改：
    
NOTIFY_ABORT_DEFERRED 
  
> 通知传输提供程序已接受其责任的邮件正在延迟。 只有支持延迟的传输提供程序必须支持此标志。 _lppvData_ 参数指向已取消邮件的条目标识符。 MAPI 后台处理程序尚未处理的邮件仍可通过调用 [IMsgStore：：AbortSubmit](imsgstore-abortsubmit.md) 方法来延迟。 
    
NOTIFY_BEGIN_INBOUND 
  
> MAPI 后台处理程序现在可以接受此传输提供程序会话的入站邮件。 如果传输提供程序在登录时通过[IXPProvider：：TransportLogon](ixpprovider-transportlogon.md)调用设置 LOGON_SP_POLL 标志，MAPI 后台处理程序会定期调用[IXPLogon：:P oll](ixplogon-poll.md)方法。 设置NOTIFY_BEGIN_INBOUND标记后，MAPI 后台处理程序将采用在调用中传递至 [IMAPISupport：：SpoolerNotify](imapisupport-spoolernotify.md) 方法的 NOTIFY_NEWMAIL 标志。 在通过调用 [IMAPISupport：：ModifyStatusRow](imapisupport-modifystatusrow.md) 方法返回之前，应更新传输提供程序会话的状态表行。 该NOTIFY_BEGIN_INBOUND和NOTIFY_END_INBOUND标志是互斥的。 
    
NOTIFY_BEGIN_INBOUND_FLUSH 
  
> 指示传输提供商尽快循环访问入站邮件。 为遵守此通知，传输提供程序应尽快使用 **ModifyStatusRow** 在其状态表行的 PR_STATUS_CODE ([PidTagStatusCode](pidtagstatuscode-canonical-property.md)) 属性中设置 **STATUS_INBOUND_FLUSH** 标志。 当提供商确定已下载所有邮件时，或收到设置了 NOTIFY_END_INBOUND_FLUSH 标志的 **TransportNotify** 方法调用时，入站邮件循环即完成。 在入站消息周期结束之前，提供程序不应调用 [IMAPISupport：：SpoolerYield](imapisupport-spooleryield.md) 方法，否则将循环释放到操作系统以加快传入邮件的传递。 这是可接受的，因为 MAPI 后台处理程序通常NOTIFY_BEGIN_INBOUND_FLUSH响应用户的请求（通过客户端应用程序）来现在传递所有邮件。 在入站刷新操作结束时，提供程序应该使用 **SpoolerNotify** 清除其状态行的 STATUS_INBOUND_FLUSH PR_STATUS_CODE 标记。  
    
NOTIFY_BEGIN_OUTBOUND 
  
> 现在，可以对此传输提供程序会话执行出站操作。 如果有任何要为此提供程序发送的消息，将调用 [IXPLogon：：SubmitMessage](ixplogon-submitmessage.md) 方法。 在返回之前，应更新此会话的状态表行。 该NOTIFY_BEGIN_OUTBOUND和NOTIFY_END_OUTBOUND标志是互斥的。 
    
NOTIFY_BEGIN_OUTBOUND_FLUSH 
  
> 与邮件NOTIFY_BEGIN_INBOUND_FLUSH类似，但指的是出站邮件。 相应的状态标志STATUS_OUTBOUND_FLUSH。
    
NOTIFY_CANCEL_MESSAGE 
  
> MAPI 后台处理程序必须取消传输  _lppvData_ 参数指向 **IXPLogon：：SubmitMessage** 方法调用中的 32 位值的邮件。 无需传输提供程序从与邮件关联的 **SubmitMessage** **、IXPLogon：：StartMessage** 或 **IXPLogon：：EndMessage** 方法调用返回，即可设置 NOTIFY_CANCEL_MESSAGE 标志。 传输提供程序必须从处理已取消邮件的入口点尽快返回。 对于当前正在处理的入站邮件，传输提供程序应该将传入邮件保存到当前存储的位置，并下次方便时再次传递。 已为传入邮件存储的邮件对象数据将被丢弃。 如果传输提供程序在 **StartMessage 或 SubmitMessage** 时未更新此 32 位值，则出站邮件的值为 0，入站邮件的值为 1。 
    
NOTIFY_END_INBOUND 
  
> 对于此传输提供程序会话，入站操作必须停止。 MAPI 后台处理程序将停止使用 **Poll** 方法，并忽略NOTIFY_NEWMAIL的轮询。 应完成进程内消息。 传输会话的状态表行应在返回前通过调用 [ModifyStatusRow](imapisupport-modifystatusrow.md) 进行更新。 该NOTIFY_END_INBOUND和NOTIFY_BEGIN_INBOUND标志是互斥的。 
    
NOTIFY_END_INBOUND_FLUSH 
  
> 通知传输提供程序退出入站刷新模式。 传输提供程序不应停止下载，但应在后台进行下载。 传输会话的状态表行应在传输提供程序符合此通知时通过调用 **ModifyStatusRow** 进行更新。 
    
NOTIFY_END_OUTBOUND 
  
> 对于此传输提供程序会话，出站操作必须停止。 MAPI 后台处理程序停止调用 **SubmitMessage** 并忽略 **SpoolerNotify** NOTIFY_READYTOSEND标志。 如果当前正在发送出站邮件，则不应停止;若要停止传递邮件，请使用 NOTIFY_CANCEL_MESSAGE 标志。 应先调用 **ModifyStatusRow** 更新此会话的状态表行，然后再返回。 该NOTIFY_END_INBOUND和NOTIFY_BEGIN_OUTBOUND标志是互斥的。 
    
NOTIFY_END_OUTBOUND_FLUSH 
  
> 与邮件NOTIFY_END_INBOUND_FLUSH类似，但指的是出站邮件。 相应的状态标志STATUS_OUTBOUND_FLUSH。
    
 _lppvData_
  
> [out]指向特定于事件的数据的指针的指针。 有关  _lppvData 指定_ 内容的信息，请参阅  _lpulFlags_ 参数的说明。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功并返回预期值。
    
## <a name="remarks"></a>备注

MAPI 后台处理程序调用 **IXPLogon：：TransportNotify** 方法，向传输提供程序发送有关已请求通知的事件的信号。 这些事件包括取消邮件传输的 MAPI 后台处理程序请求、入站或出站传输操作开始或结束，以及清除入站或出站邮件队列的操作的开始或结束。 
  
当用户尝试取消传输提供程序之前已延迟的邮件时，MAPI 后台处理程序将调用 **TransportNotify**，在  _ulFlags_ 中同时传递 NOTIFY_ABORT_DEFERRED 和 NOTIFY_CANCEL_MESSAGE 标志。 如果 MAPI 后台处理程序正在注销并且队列中仍有消息，则它在调用 **TransportNotify** NOTIFY_ABORT_DEFERRED _仅在 ulFlags_ 中传递消息。
  
## <a name="notes-to-implementers"></a>针对实现者的说明

提供程序必须同步对此调用中其数据的访问，因为 MAPI 后台处理程序可以从另一个执行线程或其他窗口的过程调用此方法。 当 MAPI 后台处理程序发出取消传输提供程序已开始发送的邮件的信号时，很可能会发生这种情况。
  
## <a name="see-also"></a>另请参阅

- [IMAPISupport::SpoolerNotify](imapisupport-spoolernotify.md) 
- [IMAPISupport::SpoolerYield](imapisupport-spooleryield.md) 
- [IMsgStore::AbortSubmit](imsgstore-abortsubmit.md) 
- [IXPLogon::EndMessage](ixplogon-endmessage.md) 
- [IXPLogon::Poll](ixplogon-poll.md)
- [IXPLogon::StartMessage](ixplogon-startmessage.md)
- [IXPLogon::SubmitMessage](ixplogon-submitmessage.md)
- [IXPProvider::TransportLogon](ixpprovider-transportlogon.md)
- [IXPLogon : IUnknown](ixplogoniunknown.md)

