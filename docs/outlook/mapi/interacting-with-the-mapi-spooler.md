---
title: 与 MAPI 后台处理程序交互
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 5cc1d0a8-ad23-4173-b220-b7c0169073fa
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: da94347dcb47e5fdbd4a6c1d404b795f4f7938ab
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32317204"
---
# <a name="interacting-with-the-mapi-spooler"></a>与 MAPI 后台处理程序交互

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
MAPI 后台处理程序在调用传输提供程序时使用[IXPLogon: IUnknown](ixplogoniunknown.md)接口中的方法。 大多数类型的传输提供程序都可以实现这些方法中的大多数, 以便快速返回。 这是很有必要的, 因为如果某个方法需要很长时间才能返回, 则应断开回调 MAPI 后台处理程序以释放其他任务的 CPU。 
  
MAPI 后台处理程序执行其工作, 并在前台应用程序空闲时对传输提供程序进行调用。 当传输提供程序首次登录时 (由从 MAPI 传递给传输提供程序的标志来控制), 传输提供程序将在后台运行, 除非由客户端调用以刷新发送和接收队列。 只有在用户收到可能正在进行的长时间的操作时, 才会刷新队列, 传输提供程序才需要释放 CPU。 MAPI 后台处理程序通常会请求传输提供程序刷新其队列以响应用户操作, 因此, 传输提供程序通常不需要执行任何操作以确保通知用户。
  
传输提供程序可以独立决定刷新队列, 并使用其状态行的**PR_STATUS_CODE** ([PidTagStatusCode](pidtagstatuscode-canonical-property.md)) 属性中的 STATUS_INBOUND_FLUSH 和 STATUS_OUTBOUND_FLUSH 位来通知 MAPI 后台处理程序需要请注意, 这样可使其完成作业。 使用[IMAPISupport:: ModifyStatusRow](imapisupport-modifystatusrow.md)方法更新状态行。 在这种情况下, 传输提供程序可能会显示进度指示器或其他接口, 以通知用户发生长时间操作。 
  
由于网络活动通常需要超过0.2 秒, 因此应尽可能使用传输提供程序来使用异步网络请求。 这使他们能够启动请求, 通过回调 mapi 后台处理程序来释放 CPU, 以及当 MAPI 后台处理程序再次向其提供控制时, 检查其网络请求是否已完成。 如果尚未完成, 它们将再次通过使用[IMAPISupport:: SpoolerYield](imapisupport-spooleryield.md)方法回调 MAPI 后台处理程序来释放 CPU。 
  
在邮件处理过程中, 在[IXPLogon:: SubmitMessage](ixplogon-submitmessage.md)和[IXPLogon:: EndMessage](ixplogon-endmessage.md)和在[IXPLogon:: StartMessage](ixplogon-startmessage.md)中, 传输提供程序通常会对它通过 MAPI 后台处理程序向其公开的对象进行大量调用。 在对这些对象进行处理的过程中, MAPI 后台处理程序可帮助传输提供程序在适当时自行生成, 从而帮助传输提供程序的行为与后台进程一样。 需要进行时间关键处理的传输提供程序可以使用[IMAPISupport:: SpoolerNotify](imapisupport-spoolernotify.md)支持对象方法将关键部分声明到 MAPI 后台处理程序。 在这种情况下, 只有在对传输提供程序的显式**SpoolerYield**调用中, 才会释放 CPU, 直到传输提供程序结束与对**SpoolerNotify**的另一次调用的关键部分处理。
  
> [!NOTE]
> 这与 Win32 临界区不同。 仅当传输提供程序需要实时控制外部资源 (例如, 从传真行读取传入数据) 时, 才应执行此操作。 由于这将提高 MAPI 后台处理程序进程的优先级, 并可能导致工作站在操作期间无响应, 因此最好通知用户正在进行可能很长的操作, 并在可能的情况下提供进度指示器。 
  

