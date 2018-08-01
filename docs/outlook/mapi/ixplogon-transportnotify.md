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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 5429f98a0335ae99b719d0f15b66a95ba87430e3
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776135"
---
# <a name="ixplogontransportnotify"></a>IXPLogon::TransportNotify

**适用于**： Outlook 
  
信号传输提供程序有关哪些请求发送通知的事件的匹配项。
  
```cpp
HRESULT TransportNotify(
  ULONG FAR * lpulFlags,
  LPVOID FAR * lppvData
);
```

## <a name="parameters"></a>参数

 _lpulFlags_
  
> [传入、 传出]位掩码的标志指示通知事件。 以下标志可由上输入 MAPI 后台打印程序设置和必须返回不变输出：
    
NOTIFY_ABORT_DEFERRED 
  
> 通知传输提供程序为其接受它，责任邮件将被延迟。 仅传输提供程序支持延期必须支持此标志。 _LppvData_参数指向已取消的消息的项标识符。 调用[IMsgStore::AbortSubmit](imsgstore-abortsubmit.md)方法，仍可以延迟 MAPI 后台处理程序尚未处理的消息。 
    
NOTIFY_BEGIN_INBOUND 
  
> MAPI 后台处理程序现在可以接受该传输提供程序会话的入站的邮件。 MAPI 后台处理程序定期调用[IXPLogon::Poll](ixplogon-poll.md)方法，如果传输提供程序在登录设置[IXPProvider::TransportLogon](ixpprovider-transportlogon.md)调用 LOGON_SP_POLL 标志。 一旦设置 NOTIFY_BEGIN_INBOUND 标志，MAPI 后台处理程序采用对[IMAPISupport::SpoolerNotify](imapisupport-spoolernotify.md)方法的调用中传递的 NOTIFY_NEWMAIL 标志。 通过调用[IMAPISupport::ModifyStatusRow](imapisupport-modifystatusrow.md)方法返回之前，应更新传输提供程序会话状态表格行。 NOTIFY_BEGIN_INBOUND 和 NOTIFY_END_INBOUND 标志是互斥的。 
    
NOTIFY_BEGIN_INBOUND_FLUSH 
  
> 信号传输提供程序尽快循环入站邮件。 为遵守此通知，传输提供程序应设置 STATUS_INBOUND_FLUSH 标志其状态表格行的**PR_STATUS_CODE** ([PidTagStatusCode](pidtagstatuscode-canonical-property.md)) 属性中为它可以使用**ModifyStatusRow**。 入站消息周期已完成时提供程序确定它已下载所有可以, 或者它已接收**TransportNotify**方法调用设置了 NOTIFY_END_INBOUND_FLUSH 标志。 之前的入站消息周期结束时，提供程序不应调用[IMAPISupport::SpoolerYield](imapisupport-spooleryield.md)方法或否则释放给操作系统的传入消息的速度传递周期。 这是可接受的因为 MAPI 后台处理程序通常使用 NOTIFY_BEGIN_INBOUND_FLUSH 仅在响应用户的请求，通过客户端应用程序，现在将所有邮件的都传递。 在的入站刷新操作的末尾，提供程序应使用**SpoolerNotify**清除 STATUS_INBOUND_FLUSH 标志其状态的行的**PR_STATUS_CODE**属性中。 
    
NOTIFY_BEGIN_OUTBOUND 
  
> 出站操作会立即发生该传输提供程序会话的。 如果有任何邮件发送此提供程序，遵循对[IXPLogon::SubmitMessage](ixplogon-submitmessage.md)方法的调用。 返回之前，应更新此会话状态表格行。 NOTIFY_BEGIN_OUTBOUND 和 NOTIFY_END_OUTBOUND 标志是互斥的。 
    
NOTIFY_BEGIN_OUTBOUND_FLUSH 
  
> 工作方式类似于 NOTIFY_BEGIN_INBOUND_FLUSH 标志，但指的出站邮件。 相应的状态标志是 STATUS_OUTBOUND_FLUSH。
    
NOTIFY_CANCEL_MESSAGE 
  
> MAPI 后台处理程序必须取消转接呼叫的_lppvData_参数指向的 32 位值从**IXPLogon::SubmitMessage**方法的邮件。 传输提供程序具有返回来自**SubmitMessage**、 **IXPLogon::StartMessage**或与邮件相关联的**IXPLogon::EndMessage**方法调用的情况下，可设置 NOTIFY_CANCEL_MESSAGE 标志。 传输提供程序必须尽可能快地返回从处理已取消的邮件的入口点。 当前正在处理入站邮件，传输提供程序应无论目前正在保存传入邮件，并提供再次在下一个方便的时间。 部分将被丢弃的传入邮件已存储的消息对象数据。 如果传输提供程序没有**StartMessage**或**SubmitMessage**次更新此 32 位值，则值将为出站邮件 0 和 1 入站邮件。 
    
NOTIFY_END_INBOUND 
  
> 入站的操作必须停止此传输提供程序会话。 MAPI 后台处理程序停止使用**投票**方法，并为此会话忽略 NOTIFY_NEWMAIL。 应完成在处理邮件。 通过调用[ModifyStatusRow](imapisupport-modifystatusrow.md)返回之前，应更新传输会话状态表格行。 NOTIFY_END_INBOUND 和 NOTIFY_BEGIN_INBOUND 标志是互斥的。 
    
NOTIFY_END_INBOUND_FLUSH 
  
> 通知传输提供程序可以利用入站刷新模式。 传输提供程序应停止下载，但在后台应完成下载。 通过调用**ModifyStatusRow**传输提供程序可以符合此通知时，应更新传输会话状态表格行。 
    
NOTIFY_END_OUTBOUND 
  
> 出站操作必须停止此传输提供程序会话。 MAPI 后台处理程序调用**SubmitMessage**中消失，并忽略**SpoolerNotify** NOTIFY_READYTOSEND 标志。 如果没有当前发送出站邮件，则应不停止;若要停止邮件传递，请使用 NOTIFY_CANCEL_MESSAGE 标志。 通过调用**ModifyStatusRow**返回之前，应更新此会话状态表格行。 NOTIFY_END_INBOUND 和 NOTIFY_BEGIN_OUTBOUND 标志是互斥的。 
    
NOTIFY_END_OUTBOUND_FLUSH 
  
> 工作原理同样到 NOTIFY_END_INBOUND_FLUSH，但指出站邮件。 相应的状态标志是 STATUS_OUTBOUND_FLUSH。
    
 _lppvData_
  
> [输出]指向特定于事件的数据的指针的指针。 有关哪些_lppvData_指定的详细信息，请参阅_lpulFlags_参数的说明。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 呼叫成功，并返回预期的值。
    
## <a name="remarks"></a>说明

MAPI 后台处理程序调用信号传输提供程序为其请求通知的事件有关的**IXPLogon::TransportNotify**方法。 这些事件包括 MAPI 后台处理程序请求取消邮件传输、 开始或结束的入站或出站传输操作和开始或结束的操作以清除入站或出站消息队列。 
  
当用户尝试取消以前延迟传输提供程序具有一条消息时，MAPI 后台处理程序调用**TransportNotify**中的 NOTIFY_ABORT_DEFERRED 和 NOTIFY_CANCEL_MESSAGE 标志_ulFlags_中传递。 如果 MAPI 后台处理程序正在注销，仍在队列中邮件，它将传递仅 NOTIFY_ABORT_DEFERRED _ulFlags_中时它调用**TransportNotify**。
  
## <a name="notes-to-implementers"></a>针对实施者的注释

提供程序必须同步到此呼叫，其数据的访问，因为 MAPI 后台处理程序可以调用此方法从另一个线程的执行或过程对于另一个窗口。 这很可能会发生时 MAPI 后台处理程序信号传输提供程序已启动发送一条消息的取消。
  
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

