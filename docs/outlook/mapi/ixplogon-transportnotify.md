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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32351560"
---
# <a name="ixplogontransportnotify"></a>IXPLogon::TransportNotify

**适用于**：Outlook 2013 | Outlook 2016 
  
指示发生了传输提供程序请求通知的事件。
  
```cpp
HRESULT TransportNotify(
  ULONG FAR * lpulFlags,
  LPVOID FAR * lppvData
);
```

## <a name="parameters"></a>参数

 _lpulFlags_
  
> [in, out]指示通知事件的标志的位掩码。 在输入时, MAPI 后台处理程序可以设置以下标志, 并且在输出时必须返回不变的标志:
    
NOTIFY_ABORT_DEFERRED 
  
> 通知传输提供程序其接受其接受责任的邮件已延迟。 仅支持延期的传输提供程序必须支持此标志。 _lppvData_参数指向已取消邮件的条目标识符。 MAPI 后台处理程序尚未处理的邮件仍可以通过调用[IMsgStore:: AbortSubmit](imsgstore-abortsubmit.md)方法来延迟。 
    
NOTIFY_BEGIN_INBOUND 
  
> MAPI 后台处理程序现在可以接受此传输提供程序会话的入站邮件。 如果传输提供程序在登录时将 LOGON_SP_POLL 标记设置为[IXPProvider:: TransportLogon](ixpprovider-transportlogon.md) , MAPI 后台处理程序将定期调用[IXPLogon::P oll](ixplogon-poll.md)方法。 设置 NOTIFY_BEGIN_INBOUND 标志后, MAPI 后台处理程序会在调用[IMAPISupport:: SpoolerNotify](imapisupport-spoolernotify.md)方法时接受在调用中传递的 NOTIFY_NEWMAIL 标志。 在返回之前, 应通过调用[IMAPISupport:: ModifyStatusRow](imapisupport-modifystatusrow.md)方法来更新传输提供程序会话的状态表格行。 NOTIFY_BEGIN_INBOUND 和 NOTIFY_END_INBOUND 标志是相互排斥的。 
    
NOTIFY_BEGIN_INBOUND_FLUSH 
  
> 通知传输提供程序尽快通过入站邮件进行循环。 若要符合此通知, 传输提供程序应尽快在其状态表行的**PR_STATUS_CODE** ([PidTagStatusCode](pidtagstatuscode-canonical-property.md)) 属性中设置 STATUS_INBOUND_FLUSH 标志, 方法是使用**ModifyStatusRow**。 当提供程序确定已下载所有的传入邮件循环时, 或者在使用 NOTIFY_END_INBOUND_FLUSH 标志集收到**TransportNotify**方法调用时, 该循环将完成。 在入站邮件循环结束之前, 提供程序不应调用[IMAPISupport:: SpoolerYield](imapisupport-spooleryield.md)方法或以其他方式放弃操作系统以加快传入邮件的传递。 这是可以接受的, 因为 MAPI 后台处理程序通常仅使用 NOTIFY_BEGIN_INBOUND_FLUSH 响应用户的请求, 通过客户端应用程序立即传递所有邮件。 在入站刷新操作结束时, 提供程序应使用**SpoolerNotify**来清除其状态行的**PR_STATUS_CODE**属性中的 STATUS_INBOUND_FLUSH 标志。 
    
NOTIFY_BEGIN_OUTBOUND 
  
> 现在可以对此传输提供程序会话执行出站操作。 如果要为此提供程序发送的任何邮件, 请调用[IXPLogon:: SubmitMessage](ixplogon-submitmessage.md)方法。 应在返回之前更新此会话的状态表行。 NOTIFY_BEGIN_OUTBOUND 和 NOTIFY_END_OUTBOUND 标志是相互排斥的。 
    
NOTIFY_BEGIN_OUTBOUND_FLUSH 
  
> 的工作方式与 NOTIFY_BEGIN_INBOUND_FLUSH 标志类似, 但引用出站邮件。 相应的状态标志为 STATUS_OUTBOUND_FLUSH。
    
NOTIFY_CANCEL_MESSAGE 
  
> MAPI 后台处理程序必须取消从**IXPLogon:: SubmitMessage**方法调用的_lppvData_参数指向32位值的邮件的传输。 可以在没有传输提供程序的情况下设置 NOTIFY_CANCEL_MESSAGE 标志, 该传输提供程序从**SubmitMessage**、 **IXPLogon:: StartMessage**或**IXPLogon:: EndMessage**方法调用 (与邮件关联) 中返回。 传输提供程序必须从处理已取消的邮件的入口点尽快返回。 对于当前正在处理的入站邮件, 传输提供程序应在其当前存储的任何位置保存传入邮件, 并在下一个方便的时间再次传递该邮件。 已为传入邮件存储的邮件对象数据将被丢弃。 如果传输提供程序未在**StartMessage**或**SubmitMessage**时间更新此32位值, 则值为0表示出站邮件, 1 表示入站邮件。 
    
NOTIFY_END_INBOUND 
  
> 对于此传输提供程序会话, 入站操作必须停止。 MAPI 后台处理程序将停止使用**轮询**方法, 并忽略此会话的 NOTIFY_NEWMAIL。 应完成进程内邮件。 应在返回之前调用[ModifyStatusRow](imapisupport-modifystatusrow.md) , 以更新传输会话的状态表格行。 NOTIFY_END_INBOUND 和 NOTIFY_BEGIN_INBOUND 标志是相互排斥的。 
    
NOTIFY_END_INBOUND_FLUSH 
  
> 通知传输提供程序无法进入入站刷新模式。 传输提供程序不应停止下载, 但应在后台进行下载。 传输会话的状态表行应在传输提供程序可以符合此通知时调用**ModifyStatusRow**进行更新。 
    
NOTIFY_END_OUTBOUND 
  
> 对于此传输提供程序会话, 出站操作必须停止。 MAPI 后台处理程序将停止调用**SubmitMessage**并忽略**SpoolerNotify** NOTIFY_READYTOSEND 标记。 如果当前正在发送出站邮件, 则不应将其停止;若要停止传递邮件, 请使用 NOTIFY_CANCEL_MESSAGE 标志。 在返回之前, 应通过调用**ModifyStatusRow**更新此会话的状态表格行。 NOTIFY_END_INBOUND 和 NOTIFY_BEGIN_OUTBOUND 标志是相互排斥的。 
    
NOTIFY_END_OUTBOUND_FLUSH 
  
> 的工作方式与 NOTIFY_END_INBOUND_FLUSH 类似, 但引用出站邮件。 相应的状态标志为 STATUS_OUTBOUND_FLUSH。
    
 _lppvData_
  
> 排除指向指向事件特定数据的指针的指针。 有关_lppvData_指定的内容的详细信息, 请参阅_lpulFlags_参数的说明。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功, 并返回了所需的一个或一些值。
    
## <a name="remarks"></a>注解

MAPI 后台处理程序调用**IXPLogon:: TransportNotify**方法向传输提供程序发出通知请求的事件。 这些事件包括取消邮件传输的 MAPI 后台处理程序请求、入站或出站传输操作的开始或结束以及清除入站或出站邮件队列的操作的开始或结束。 
  
当用户尝试取消传输提供程序之前已延迟的邮件时, MAPI 后台处理程序将调用**TransportNotify**, 同时在_ulFlags_中传入 NOTIFY_ABORT_DEFERRED 和 NOTIFY_CANCEL_MESSAGE 标志。 如果 MAPI 后台处理程序正在注销, 并且队列中仍有邮件, 则它会在调用**TransportNotify**时仅在_ulFlags_中传递 NOTIFY_ABORT_DEFERRED。
  
## <a name="notes-to-implementers"></a>针对实现者的说明

提供程序必须在此调用上同步对其数据的访问, 因为 MAPI 后台处理程序可以从另一个执行线程或从另一个窗口的过程中调用此方法。 当 MAPI 后台处理程序发出邮件的取消通知传输提供程序已开始发送邮件时, 这很可能会发生这种情况。
  
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

