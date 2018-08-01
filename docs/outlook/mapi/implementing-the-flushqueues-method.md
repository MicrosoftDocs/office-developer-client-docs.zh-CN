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
ms.openlocfilehash: baafd8b6437f4febaee9420b274c20ba3242cae6
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775832"
---
# <a name="implementing-the-flushqueues-method"></a>实现 FlushQueues 方法

  
  
**适用于**： Outlook 
  
MAPI 后台处理程序使用[IXPLogon::FlushQueues](ixplogon-flushqueues.md)方法下载和上载任何挂起邮件与传输提供程序。 通常，MAPI 后台处理程序将刷新队列的所有传输提供程序登录到会话，用户的配置文件传输顺序部分中设置启动的第一个传输提供程序。 刷新队列始终是由用户，直接请求的结果，因此发送和接收的消息时将刷新队列是同步到 MAPI 后台处理程序。 这些呼叫是同步的因为传输提供程序应尽可能快地处理它们。 
  
传输提供程序必须处理**FlushQueues**呼叫的步骤顺序如下所述启用适当的消息处理以及启用外部的资源，如调制解调器的 MAPI 后台处理程序的一部分使用由其他传输提供程序**FlushQueues**操作。 
  
|**步骤**|**组件**|**实现**|
|:-----|:-----|:-----|
|1。  <br/> |MAPI 后台处理程序  <br/> |为第一个传输提供程序中的用户配置的传输顺序列出传递_ulFlags_参数中的请求的标志调用**FlushQueues**方法。 与所有标志设置为整个上载和下载操作调用**FlushQueues**一次。  <br/> |
|2。  <br/> |传输提供程序  <br/> |需要从**FlushQueues**呼叫返回之前执行大量操作。 如果以前提交的邮件将被延迟， [IMAPISupport::SpoolerNotify](imapisupport-spoolernotify.md)方法应调用设置了 NOTIFY_SENT_DEFERRED 标志。 请注意，可能为 MAPI 后台处理程序取消一条消息，已传输提供程序之前延迟有机会完成处理邮件。  <br/> 如果传输提供程序使用外部资源，如调制解调器，应该建立的连接到外部资源。  <br/> 必须使用[IMAPISupport::ModifyStatusRow](imapisupport-modifystatusrow.md)方法设置 STATUS_OUTBOUND_FLUSH 位传输提供程序的状态行的**PR_STATUS_CODE** ([PidTagStatusCode](pidtagstatuscode-canonical-property.md)) 属性中。  <br/> 传输提供程序然后应**FlushQueues**呼叫返回 S_OK。  <br/> |
|3.  <br/> |MAPI 后台处理程序  <br/> |检查 STATUS_OUTBOUND_FLUSH 位传输提供程序的状态行，并调用[IXPLogon::SubmitMessage](ixplogon-submitmessage.md)程序队列中的第一条消息。  <br/> |
|4。  <br/> |传输提供程序  <br/> |处理邮件，并返回从**SubmitMessage**呼叫。  <br/> |
|5。  <br/> |MAPI 后台处理程序  <br/> |如果传输提供程序从**SubmitMessage**返回 S_OK，MAPI 后台处理程序调用邮件[IXPLogon::EndMessage](ixplogon-endmessage.md) ，，这与正常的消息发送。  <br/> 传输提供程序从**SubmitMessage**返回 S_OK 之外的一个值，如果 MAPI 后台处理程序处理值相应地之前调用**EndMessage**，或再次调用**SubmitMessage**之前。  <br/> |
|6。  <br/> |传输提供程序  <br/> |返回的范围是从**EndMessage**与其消息处理_lpulFlags_参数中的状态。  <br/> |
|7。  <br/> |MAPI 后台处理程序和传输提供程序  <br/> |**SubmitMessage**- 继续**EndMessage**循环，直到已下载队列中的所有邮件。  <br/> |
|8。  <br/> |MAPI 后台处理程序  <br/> |通知传输提供程序，它已完成下载邮件通过调用设置了 NOTIFY_END_OUTBOUND_FLUSH 标志的传输提供程序的[IXPLogon::TransportNotify](ixplogon-transportnotify.md)方法。  <br/> |
|9。  <br/> |传输提供程序  <br/> |释放发送出站邮件，以便他们可以使用由其他传输提供程序刷新其队列中使用的任何外部资源。  <br/> 必须使用**ModifyStatusRow**设置中的传输提供程序的状态行的**PR_STATUS_CODE**属性位 STATUS_INBOUND_FLUSH。  <br/> |
|10。  <br/> |MAPI 后台处理程序  <br/> |检查 STATUS_INBOUND_FLUSH 位传输提供程序的状态行，并调用[IXPLogon::StartMessage](ixplogon-startmessage.md) ，如果将其设置。  <br/> |
|11。  <br/> |传输提供程序  <br/> |处理邮件，并返回从**StartMessage**。 如果传输提供程序具有上载其他消息，它应调用**SpoolerNotify**设置了 NOTIFY_NEWMAIL 标志。  <br/> 如果传输提供程序不具有上载任何消息，它应 MAPI 后台处理程序中**StartMessage**传递，并返回对邮件调用[IMAPIProp::SaveChanges](imapiprop-savechanges.md) 。  <br/> |
|12。  <br/> |MAPI 后台处理程序  <br/> |继续调用**StartMessage** ，直到**SaveChanges**调用上一条消息。 传输提供程序完成上载后，则 MAPI 后台处理程序调用**TransportNotify**设置了 NOTIFY_END_INBOUND_FLUSH 标志。  <br/> |
|13。  <br/> |传输提供程序  <br/> |清除由其他传输提供程序中使用**ModifyStatusRow**和所有外部的资源，以使其可供使用的版本其状态行的**PR_STATUS_CODE**属性位 STATUS_INBOUND_FLUSH。  <br/> |
|14。  <br/> |MAPI 后台处理程序  <br/> |为下一个传输提供程序的用户的配置文件传输顺序列出调用**FlushQueues** 。  <br/> |
   
如果客户端应用程序[IMAPIStatus::FlushQueues](imapistatus-flushqueues.md)对象上的调用传输提供程序的状态，传输提供程序应与**ModifyStatusRow**其状态行中设置相应的位。 MAPI 后台处理程序然后在 MAPI 后台处理程序的方便调用传输提供程序的**IXPLogon::FlushQueues**方法。 传输提供程序的**IXPLogon::FlushQueues**方法调用时客户端应用程序的**IMAPIStatus::FlushQueues**呼叫，由于操作发生异步客户端应用程序。 否则**IXPLogon::FlushQueues**适用于同步的 MAPI 后台处理程序。 
  
出于性能原因，MAPI 后台处理程序仅将调用传输提供程序的**FlushQueues**方法，如果传输提供程序的状态行中设置了 STATUS_INBOUND_FLUSH 和 STATUS_OUTBOUND_FLUSH 标志。 因此，传输提供程序可以通过清除其状态行中的 STATUS_OUTBOUND_FLUSH 和 STATUS_INBOUND_FLUSH 标志停止随时**FlushQueues**操作。 如果 MAPI 后台处理程序已关闭，并且需要结束**FlushQueues**操作，则设置的 NOTIFY_END_INBOUND_FLUSH 和 NOTIFY_END_OUTBOUND_FLUSH flags 调用**TransportNotify** 。 传输提供程序应释放所有外部的资源，并返回。 
  

