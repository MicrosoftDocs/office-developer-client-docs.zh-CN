---
title: 与 MAPI 后台处理程序交互
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 5cc1d0a8-ad23-4173-b220-b7c0169073fa
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: c8032172ef19fbb01af68058b2e0255e269183a8
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22587892"
---
# <a name="interacting-with-the-mapi-spooler"></a>与 MAPI 后台处理程序交互

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
中的方法[IXPLogon: IUnknown](ixplogoniunknown.md)接口使用 MAPI 后台处理程序调用传输提供程序时。 它应可能为传输提供程序，以便他们快速返回实现这些方法的大多数大多数类型。 这是不可或缺的因为如果方法需要很长时间，以返回然后它应该被回 MAPI 后台处理程序的呼叫释放 CPU 的其他任务。 
  
MAPI 后台处理程序自己的工作，并使其传输提供程序，当前景色的应用程序处于空闲状态的呼叫。 传输提供程序首次登录时 （为由标志从 MAPI 传递到传输提供程序），也可以显示对话框之后, 传输提供程序在后台操作除非由客户端刷新发送和接收队列中调用。 刷新队列是传输提供程序不需要释放 CPU 的唯一时间，然后才可能很长操作正在进行通知用户。 MAPI 后台处理程序通常请求传输提供程序刷新其队列以响应用户操作，以便传输提供程序通常不需要执行任何操作，以确保会通知用户。
  
传输提供程序可以独立决定要刷新队列，并使用其状态的行的**PR_STATUS_CODE** ([PidTagStatusCode](pidtagstatuscode-canonical-property.md)) 属性中的 STATUS_INBOUND_FLUSH 和 STATUS_OUTBOUND_FLUSH 位通知 MAPI 后台打印其想注意，就使其可以获取完成的作业。 使用[IMAPISupport::ModifyStatusRow](imapisupport-modifystatusrow.md)方法更新的状态行。 在这种情况下传输提供程序可能应显示进度指示器或其他界面长操作出现通知用户。 
  
由于网络活动通常采用多个 0.2 秒，传输提供程序应，只要有可能，使用异步网络请求。 这将使他们能够发起的请求，通过调用后到 MAPI 后台处理程序，和 MAPI 后台处理程序再次使这些控件，检查是否已完成其网络请求发行 CPU。 如果它尚未完成，它们再次通过调用后 MAPI 后台处理程序使用[IMAPISupport::SpoolerYield](imapisupport-spooleryield.md)方法释放 CPU。 
  
期间消息处理期间[IXPLogon::StartMessage](ixplogon-startmessage.md)，以及[IXPLogon::SubmitMessage](ixplogon-submitmessage.md) [IXPLogon::EndMessage](ixplogon-endmessage.md)之间传输提供程序通常使多次调用上 MAPI 后台处理程序向其公开的对象。 作为其处理这些对象的一部分，MAPI 后台处理程序可帮助使用合适的作为后台进程通过自己在适当时生成的传输提供程序。 传输提供程序需要时间关键处理可以声明到 MAPI 后台处理程序使用[IMAPISupport::SpoolerNotify](imapisupport-spoolernotify.md)支持对象方法的关键部分。 在这种情况下，CPU 上释放时仅显式**SpoolerYield**呼叫由传输提供程序直到传输提供程序结束处理与**SpoolerNotify**到另一个通话的关键部分。
  
> [!NOTE]
> 这不是 Win32 关键部分相同。 这应该仅进行传输提供程序所需的外部的资源，如从传真行读取传入数据的实时控制时。 由于这会引发 MAPI 后台处理程序进程的优先级，并且会导致工作站可操作的持续时间内未响应，它是最好通知可能很长操作正在进行的用户，如果可能提供进度指示器。 
  

