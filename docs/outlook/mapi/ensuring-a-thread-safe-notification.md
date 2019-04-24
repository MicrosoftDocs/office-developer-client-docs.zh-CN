---
title: 确保线程安全通知
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: d46ce99a-4d7f-45b0-ba21-154498c15775
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 88c58d14893f2ac561dc56441eb38b7f4bd0db32
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32316582"
---
# <a name="ensuring-a-thread-safe-notification"></a>确保线程安全通知

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
如果您的客户端在多线程平台上运行, 您可能需要确保对[IMAPIAdviseSink:: OnNotify](imapiadvisesink-onnotify.md)方法的调用在特定的线程上出现。 由于对**OnNotify**的调用通常会在任何线程上发生, 因此可以在意外和不需要的线程上接收通知, 从而导致难以调试的错误。 
  
若要确保对用于通知调用的同一线程发出特定通知的**OnNotify**调用, 请先调用[HrThisThreadAdviseSink](hrthisthreadadvisesink.md)再调用**建议**。 **** * * * * HrThisThreadAdviseSink * * * * 从您的建议接收器对象创建一个新的通知接收器对象。 在调用中将此新对象传递给 "**建议**"。 如果所有客户端的建议接收器对象可能无法在特定线程的上下文外部运行, 则应始终使用**HrThisThreadAdviseSink**创建的通知接收器对象。
  

