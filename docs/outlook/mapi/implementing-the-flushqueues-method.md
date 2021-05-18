---
title: 实现 FlushQueues 方法
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 8719f8aa-a537-4253-b67d-c4d38c40472b
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 1e5c78c71f7fddb04d3517aca0a34efa151ece08
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33411776"
---
# <a name="implementing-the-flushqueues-method"></a>实现 FlushQueues 方法

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
MAPI 后台处理程序使用 [IXPLogon：：FlushQueues](ixplogon-flushqueues.md) 方法在传输提供程序中下载和上载任何挂起的邮件。 通常，MAPI 后台处理程序将刷新登录到会话的所有传输提供程序的队列，从用户配置文件的传输顺序部分中设置的第一个传输提供程序开始。 刷新队列几乎始终是用户直接请求的结果，因此队列刷新时发送和接收邮件与 MAPI 后台处理程序同步。 由于这些调用是同步的，因此传输提供程序应尽快处理它们。 
  
传输提供程序必须按照以下步骤序列所述处理 **FlushQueues** 调用，以启用正确的邮件处理，并启用外部资源（如调制解调器）由其他传输提供程序用作 MAPI 后台处理程序 **FlushQueues** 操作一部分。 
  
|**步骤**|**组件**|**实现**|
|:-----|:-----|:-----|
|1.  <br/> |MAPI 后台处理程序  <br/> |为用户配置文件的传输顺序中列出的第一个传输提供程序调用 **FlushQueues** 方法，在  _ulFlags_ 参数中传递请求的标志。 **FlushQueues** 调用一次，同时为整个上载和下载操作设置所有标志。  <br/> |
|2.  <br/> |传输提供程序  <br/> |在从 **FlushQueues** 调用返回之前需要执行许多操作。 如果之前提交的消息被延迟，应在设置 [imAPISupport：：SpoolerNotify](imapisupport-spoolernotify.md) 标志NOTIFY_SENT_DEFERRED调用此方法。 请注意，MAPI 后台处理程序可以取消在传输提供程序有机会完成邮件处理之前延迟的邮件。  <br/> 如果传输提供程序使用调制解调器等外部资源，应建立与外部资源的连接。  <br/> 必须使用[IMAPISupport：：ModifyStatusRow](imapisupport-modifystatusrow.md)方法设置STATUS_OUTBOUND_FLUSH传输提供程序状态行的 PR_STATUS_CODE ([PidTagStatusCode](pidtagstatuscode-canonical-property.md)) 属性中的位。   <br/> 然后，传输提供程序应S_OK **FlushQueues** 调用的呼叫。  <br/> |
|3.  <br/> |MAPI 后台处理程序  <br/> |检查传输提供程序的状态行中是否包含STATUS_OUTBOUND_FLUSH，并针对队列中的第一封邮件调用[IXPLogon：：SubmitMessage。](ixplogon-submitmessage.md)  <br/> |
|4.  <br/> |传输提供程序  <br/> |处理消息，然后从 **SubmitMessage 调用** 返回。  <br/> |
|5.  <br/> |MAPI 后台处理程序  <br/> |如果传输提供程序从 **SubmitMessage** 返回 S_OK，MAPI 后台处理程序会像对常规邮件发送一样为邮件调用 [IXPLogon：：EndMessage。](ixplogon-endmessage.md)  <br/> 如果传输提供程序从 **SubmitMessage** 返回 S_OK 值，MAPI 后台处理程序将在调用 **EndMessage** 或再次调用 **SubmitMessage** 之前适当地处理该值。  <br/> |
|6.  <br/> |传输提供程序  <br/> |返回 **EndMessage，** 其邮件处理状态在  _lpulFlags_ 参数中。  <br/> |
|7.  <br/> |MAPI 后台处理程序和传输提供程序  <br/> |**SubmitMessage** -  **EndMessage** 循环将继续，直到队列中的所有邮件都下载完。  <br/> |
|8.  <br/> |MAPI 后台处理程序  <br/> |通过调用传输提供程序的 [IXPLogon：：TransportNotify 方法（设置了传输提供程序的 IXPLogon：：TransportNotify](ixplogon-transportnotify.md) 方法）通知NOTIFY_END_OUTBOUND_FLUSH消息。  <br/> |
|9.  <br/> |传输提供程序  <br/> |释放发送出站邮件时所使用的任何外部资源，以便其他传输提供程序可以使用这些资源刷新其队列。  <br/> 传输STATUS_INBOUND_FLUSH行的 **PR_STATUS_CODE** 属性中的位必须使用 **ModifyStatusRow 进行设置**。  <br/> |
|10.  <br/> |MAPI 后台处理程序  <br/> |检查传输提供程序的状态行中是否STATUS_INBOUND_FLUSH，如果已设置，则调用[IXPLogon：：StartMessage。](ixplogon-startmessage.md)  <br/> |
|11.  <br/> |传输提供程序  <br/> |处理邮件，然后从 **StartMessage 返回**。 如果传输提供程序具有要上载的其他邮件，则它应调用 **SpoolerNotify，NOTIFY_NEWMAIL** 设置。  <br/> 如果传输提供程序没有要上载的消息，则应当对在 **StartMessage** 中传递的 MAPI 后台处理程序的消息调用 [IMAPIProp：：SaveChanges](imapiprop-savechanges.md)并返回。  <br/> |
|12.  <br/> |MAPI 后台处理程序  <br/> |继续调用 **StartMessage，直到** 在邮件上调用 **SaveChanges。** 传输提供程序完成上载后，MAPI 后台处理程序调用 **TransportNotify，NOTIFY_END_INBOUND_FLUSH** 设置。  <br/> |
|13.  <br/> |传输提供程序  <br/> |使用 **ModifyStatusRow** 清除STATUS_INBOUND_FLUSH行的 **PR_STATUS_CODE** 属性中的位，并释放所有外部资源，以便可供其他传输提供程序使用。  <br/> |
|14.  <br/> |MAPI 后台处理程序  <br/> |为用户配置文件的传输顺序中列出的下一个传输提供程序调用 **FlushQueues。**  <br/> |
   
如果客户端应用程序对传输提供程序的状态对象调用 [IMAPIStatus：：FlushQueues，](imapistatus-flushqueues.md) 则传输提供程序应该使用 **ModifyStatusRow** 在其状态行中设置相应的位。 然后，MAPI 后台处理程序在 MAPI 后台处理程序方便时调用传输提供程序的 **IXPLogon：：FlushQueues** 方法。 当由于客户端应用程序的 **IMAPIStatus：：FlushQueues** 调用而调用传输提供程序的 **IXPLogon：：FlushQueues** 方法时，该操作将异步对客户端应用程序执行。 否则 **，IXPLogon：：FlushQueues** 与 MAPI 后台处理程序同步工作。 
  
出于性能原因，如果 STATUS_INBOUND_FLUSH 和 STATUS_OUTBOUND_FLUSH 标志在传输提供程序的状态行中设置，MAPI 后台处理程序将仅调用传输提供程序的 **FlushQueues** 方法。 因此，传输提供程序可通过清除其状态行中的 STATUS_OUTBOUND_FLUSH 和 STATUS_INBOUND_FLUSH 标志来随时停止 **FlushQueues** 操作。 如果 MAPI 后台处理程序正在关闭并需要结束 **FlushQueues** 操作，它将使用设置 NOTIFY_END_INBOUND_FLUSH 和 NOTIFY_END_OUTBOUND_FLUSH 调用 **TransportNotify。** 传输提供程序应释放并返回所有外部资源。 
  

