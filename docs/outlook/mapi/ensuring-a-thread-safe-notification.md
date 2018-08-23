---
title: 确保线程安全通知
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: d46ce99a-4d7f-45b0-ba21-154498c15775
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: ad10b2ebd835b21f207fd43ecd8aebc7e1f475f4
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22585302"
---
# <a name="ensuring-a-thread-safe-notification"></a>确保线程安全通知

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
如果在多线程平台上运行您的客户端，您可能需要对[IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md)方法的调用发生在特定线程的保证。 因为调用**OnNotify**通常可以在任何线程上发生，就可以接收通知意外和不需要的线程，从而导致难以调试的错误。 
  
若要保证**Advise**时使用的同一线程呼叫，请调用**Advise**之前调用[HrThisThreadAdviseSink](hrthisthreadadvisesink.md) ，所做的一个特定的通知调用**OnNotify** 。 * * * * HrThisThreadAdviseSink *** 从 advise 接收器对象创建一个新的 advise 接收器对象。 将此新对象传递对**Advise**的调用中。 所有客户端应始终注册可能无法运行的特定主题的上下文之外的对象的通知接收器建议使用**HrThisThreadAdviseSink**创建接收器对象。
  

