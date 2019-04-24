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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32310113"
---
# <a name="implementing-the-flushqueues-method"></a>实现 FlushQueues 方法

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
MAPI 后台处理程序使用[IXPLogon:: FlushQueues](ixplogon-flushqueues.md)方法下载所有待处理的邮件并将其上载到传输提供程序。 通常情况下, MAPI 后台处理程序将清除登录到会话的所有传输提供程序的队列, 从用户配置文件的 "传输订单" 部分中设置的第一个传输提供程序开始。 刷新队列几乎总是用户的直接请求结果, 因此, 刷新队列时发送和接收邮件的过程与 MAPI 后台处理程序是同步的。 由于这些呼叫是同步的, 因此传输提供程序应尽快处理它们。 
  
传输提供程序必须按照以下步骤序列中所述处理**FlushQueues**调用, 以启用正确的邮件处理并启用外部资源 (如 MAPI 后台处理程序的一部分, 其他传输提供程序使用调制解调器)**FlushQueues**操作。 
  
|**步骤**|**组件**|**实现**|
|:-----|:-----|:-----|
|1.  <br/> |MAPI 后台处理程序  <br/> |调用用户配置文件的传输顺序中列出的第一个传输提供程序的**FlushQueues**方法, 并在_ulFlags_参数中传递请求的标志。 将使用为整个上载和下载操作设置的所有标志调用**FlushQueues** 。  <br/> |
|2.  <br/> |传输提供程序  <br/> |在从**FlushQueues**调用返回之前, 需要执行大量操作。 如果以前提交的邮件被延迟, 则应在设置 NOTIFY_SENT_DEFERRED 标志的情况下调用[IMAPISupport:: SpoolerNotify](imapisupport-spoolernotify.md)方法。 请注意, MAPI 后台处理程序可以取消已延迟的邮件, 在传输提供程序有机会完成对邮件的处理之前。  <br/> 如果传输提供程序使用外部资源 (如调制解调器), 则应建立与外部资源的连接。  <br/> 必须使用[IMAPISupport:: ModifyStatusRow](imapisupport-modifystatusrow.md)方法设置传输提供程序状态行的**PR_STATUS_CODE** ([PidTagStatusCode](pidtagstatuscode-canonical-property.md)) 属性中的 STATUS_OUTBOUND_FLUSH 位。  <br/> 然后, 传输提供程序应返回**FlushQueues**调用的 S_OK。  <br/> |
|3.  <br/> |MAPI 后台处理程序  <br/> |检查 STATUS_OUTBOUND_FLUSH 位的传输提供程序的状态行, 并对队列中的第一条消息调用[IXPLogon:: SubmitMessage](ixplogon-submitmessage.md) 。  <br/> |
|4.  <br/> |传输提供程序  <br/> |处理邮件并从**SubmitMessage**调用返回。  <br/> |
|5.  <br/> |MAPI 后台处理程序  <br/> |如果传输提供程序从**SubmitMessage**返回 S_OK, 则 MAPI 后台处理程序会对邮件调用[IXPLogon:: EndMessage](ixplogon-endmessage.md) , 这与发送常规邮件的方式相同。  <br/> 如果传输提供程序返回的值不是从**SubmitMessage**的 S_OK, MAPI 后台处理程序会在调用**EndMessage**之前或在再次调用**SubmitMessage**之前处理该值。  <br/> |
|6.  <br/> |传输提供程序  <br/> |在_lpulFlags_参数中, 从**EndMessage**返回其邮件处理状态。  <br/> |
|7.  <br/> |MAPI 后台处理程序和传输提供程序  <br/> |**SubmitMessage**- **EndMessage**循环继续下去, 直到队列中的所有邮件都已下载。  <br/> |
|8.  <br/> |MAPI 后台处理程序  <br/> |通过调用传输提供程序的[IXPLogon:: TransportNotify](ixplogon-transportnotify.md)方法并设置 NOTIFY_END_OUTBOUND_FLUSH 标志, 通知传输提供程序已完成下载邮件。  <br/> |
|9.  <br/> |传输提供程序  <br/> |释放在发送出站邮件时使用的任何外部资源, 以便其他传输提供程序可以使用它们来刷新其队列。  <br/> 必须使用**ModifyStatusRow**设置传输提供程序的状态行的**PR_STATUS_CODE**属性中的 STATUS_INBOUND_FLUSH 位。  <br/> |
|10.  <br/> |MAPI 后台处理程序  <br/> |检查 STATUS_INBOUND_FLUSH 位的传输提供程序的状态行, 并调用[IXPLogon:: StartMessage (](ixplogon-startmessage.md)如果已设置)。  <br/> |
|11.  <br/> |传输提供程序  <br/> |处理邮件并从**StartMessage**返回。 如果传输提供程序有要上载的其他邮件, 它应调用**SpoolerNotify**并设置 NOTIFY_NEWMAIL 标志。  <br/> 如果传输提供程序没有要上载的邮件, 它应在邮件中调用[IMAPIProp:: SaveChanges](imapiprop-savechanges.md)在**StartMessage**和 return 中传递的 MAPI 后台处理程序。  <br/> |
|12.  <br/> |MAPI 后台处理程序  <br/> |继续调用**StartMessage** , 直到对邮件调用**SaveChanges** 。 在传输提供程序完成上载后, MAPI 后台处理程序将调用**TransportNotify**并设置 NOTIFY_END_INBOUND_FLUSH 标志。  <br/> |
|13.  <br/> |传输提供程序  <br/> |使用**ModifyStatusRow**清除其状态行的**PR_STATUS_CODE**属性中的 STATUS_INBOUND_FLUSH 位, 并释放所有外部资源, 以便其他传输提供程序可以使用它们。  <br/> |
|日.  <br/> |MAPI 后台处理程序  <br/> |为用户配置文件的传输顺序中列出的下一个传输提供程序调用**FlushQueues** 。  <br/> |
   
如果客户端应用程序在传输提供程序的 status 对象上调用[IMAPIStatus:: FlushQueues](imapistatus-flushqueues.md) , 则传输提供程序应在其状态行中将相应的位设置为**ModifyStatusRow**。 然后, mapi 后台处理程序在 MAPI 后台处理程序的方便性中调用传输提供程序的**IXPLogon:: FlushQueues**方法。 如果将传输提供程序的**IXPLogon:: FlushQueues**方法作为客户端应用程序的**IMAPIStatus:: FlushQueues**调用的结果调用, 则该操作将异步发生到客户端应用程序。 否则, **IXPLogon:: FlushQueues**与 MAPI 后台处理程序同步工作。 
  
出于性能原因, MAPI 后台处理程序将仅调用传输提供程序的**FlushQueues**方法 (如果在传输提供程序的状态行中设置了 STATUS_INBOUND_FLUSH 和 STATUS_OUTBOUND_FLUSH 标志)。 因此, 传输提供程序可以在任何时间通过清除 STATUS_OUTBOUND_FLUSH 和 STATUS_INBOUND_FLUSH 标志在其状态行中停止**FlushQueues**操作。 如果 MAPI 后台处理程序正在关闭并需要结束**FlushQueues**操作, 它将同时调用 NOTIFY_END_INBOUND_FLUSH 和 NOTIFY_END_OUTBOUND_FLUSH 标志集的**TransportNotify** 。 传输提供程序应释放所有外部资源并返回。 
  

