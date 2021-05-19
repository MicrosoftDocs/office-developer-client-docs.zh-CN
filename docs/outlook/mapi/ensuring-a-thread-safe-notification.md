---
title: 确保Thread-Safe通知
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: d46ce99a-4d7f-45b0-ba21-154498c15775
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 88c58d14893f2ac561dc56441eb38b7f4bd0db32
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33424845"
---
# <a name="ensuring-a-thread-safe-notification"></a>确保Thread-Safe通知

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
如果客户端在多线程平台上运行，你可能需要保证对 [IMAPIAdviseSink：：OnNotify](imapiadvisesink-onnotify.md) 方法的调用发生在特定线程上。 由于对 **OnNotify** 的调用通常可以在任何线程上发生，因此可能会接收意外和不需要的线程上的通知，从而导致难以调试的错误。 
  
若要保证对特定通知 **的 OnNotify** 调用在用于 **Advise** 调用的同一线程上执行，在调用 **Advise** 之前调用 [HrThisThreadAdviseSink。](hrthisthreadadvisesink.md) ** **HrThisThreadAdviseSink**** 从你的建议接收器对象创建新的通知接收器对象。 在调用 Advise 时传递此新 **对象**。 具有建议接收对象（这些对象可能无法在特定线程的上下文之外工作）的所有客户端应始终注册使用 **HrThisThreadAdviseSink** 创建的通知接收器对象。
  

