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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33432147"
---
# <a name="interacting-with-the-mapi-spooler"></a>与 MAPI 后台处理程序交互

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
调用传输提供程序时，MAPI 后台处理程序使用 [IXPLogon ： IUnknown](ixplogoniunknown.md) 接口中的方法。 大多数类型的传输提供程序应该可以实施其中大多数方法，以便它们快速返回。 这是可取的，因为如果某个方法需要很长时间才返回，则该方法应该通过调用回 MAPI 后台处理程序来中断，以释放其他任务的 CPU。 
  
MAPI 后台处理程序执行其工作，在前台应用程序空闲时调用传输提供程序。 在传输提供程序首次登录时显示对话框后 (由从 MAPI 传递到传输提供程序) 的标志控制，除非客户端调用来刷新发送和接收队列，否则传输提供程序将在后台运行。 刷新队列是传输提供程序唯一不需要释放 CPU 的时间，并且仅在用户得到可能长时间的操作正在进行时刷新队列。 MAPI 后台处理程序通常请求传输提供程序刷新其队列以响应用户操作，因此传输提供程序通常不需要执行任何操作来确保通知用户。
  
传输提供程序可以单独决定刷新队列，并使用其状态行的 PR_STATUS_CODE ([PidTagStatusCode](pidtagstatuscode-canonical-property.md)) 属性中的 **STATUS_INBOUND_FLUSH** 和 STATUS_OUTBOUND_FLUSH 位，以通知 MAPI 后台处理程序需要关注，以便可以完成作业。 使用 [IMAPISupport：：ModifyStatusRow 方法更新状态](imapisupport-modifystatusrow.md) 行。 在这种情况下，传输提供程序可能应显示进度指示器或其他界面，以通知用户正在执行长操作。 
  
由于网络活动通常需要 0.2 秒以上的时间，因此传输提供程序应尽可能使用异步网络请求。 这使用户能够启动请求、通过回调用 MAPI 后台处理程序释放 CPU，并且当 MAPI 后台处理程序再次授予其控制权时，可以检查其网络请求是否已完成。 如果尚未完成，它们再次使用 [IMAPISupport：：SpoolerYield](imapisupport-spooleryield.md) 方法调用 MAPI 后台处理程序来释放 CPU。 
  
在处理邮件期间， [在 IXPLogon：：SubmitMessage](ixplogon-submitmessage.md) 和 [IXPLogon：：EndMessage](ixplogon-endmessage.md) 之间以及 [IXPLogon：：StartMessage](ixplogon-startmessage.md)期间，传输提供程序通常会对 MAPI 后台处理程序向它公开的对象进行多次调用。 作为处理这些对象的一部分，MAPI 后台处理程序通过在适当时自行生成来帮助传输提供程序适当地作为后台进程运行。 需要时间关键处理的传输提供程序可以使用 [IMAPISupport：：SpoolerNotify](imapisupport-spoolernotify.md) 支持对象方法向 MAPI 后台处理程序声明关键节。 在这种情况下，CPU 仅在传输提供程序的显式 **SpoolerYield** 调用上释放，直到传输提供程序通过另一个对 **SpoolerNotify** 的调用结束关键节处理。
  
> [!NOTE]
> 这与 Win32 关键部分不同。 只有在传输提供程序需要实时控制外部资源（如从传真行读取传入数据）时，才应完成此操作。 由于这提高了 MAPI 后台处理程序进程的优先级，并且可能导致工作站在操作期间无响应，因此，建议通知用户一个可能很长操作正在进行，并提供进度指示器（如果可能）。 
  

