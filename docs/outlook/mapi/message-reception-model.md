---
title: 邮件接收模型
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: d85d269e-2251-4399-9159-a2f47a85e3d1
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 487598374f15300cc8b899a50d74b535b5a33c91
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33415115"
---
# <a name="message-reception-model"></a>邮件接收模型

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
传输提供程序控制 MAPI 后台处理程序是否必须轮询它以接收传入的邮件，或者是否执行新邮件到达时对 MAPI 后台处理程序的调用。 传输提供程序在从 [IXPProvider：：TransportLogon](ixpprovider-transportlogon.md) 返回SP_LOGON_POLL请求轮询时设置该标志。 否则，当传入邮件可用时，传输提供程序将使用[IMAPISupport：：SpoolerNotify。](imapisupport-spoolernotify.md) 在了解传入邮件可用后，MAPI 后台处理程序将打开一封新邮件，并要求传输提供程序将接收的邮件属性存储到该邮件中。 
  
此过程的工作方式如下：
  
1. 可用消息由调用 **IMAPISupport：：SpoolerNotify** 的传输提供程序或调用 [IXPLogon：:P oll](ixplogon-poll.md)的 MAPI 后台处理程序指示。
    
2. MAPI 后台处理程序调用 [IXPLogon：：StartMessage](ixplogon-startmessage.md) 以启动此过程。 
    
3. 传输提供程序在 **StartMessage** 中引用的位置中提供引用值。 这些引用值允许传输提供程序和 MAPI 后台处理程序在有多个要传递的邮件时跟踪正在处理的邮件。
    
4. 传输提供程序将邮件数据存储到传递 [的 IMessage ： IMAPIProp](imessageimapiprop.md) 实例中。 
    
5. 传输提供程序对 **IMessage** 实例调用 [IMAPIProp：：SaveChanges](imapiprop-savechanges.md)方法，然后从 **StartMessage 返回**。
    
6. 如果必须停止邮件传递，MAPI 后台处理程序将调用[IXPLogon：：TransportNotify。](ixplogon-transportnotify.md) 
    
> [!NOTE]
> 如果传输提供程序必须传递大量邮件，并且传输提供程序使用 **IMAPISupport：：SpoolerNotify** 而不是 **IXPLogon：:P oll，** 则应该注意不要过于频繁地调用 **SpoolerNotify，** 以便不会占用其他传输提供商的 CPU 时间。 MAPI 后台处理程序确实具有防止发生这种情况的逻辑，但通常 **，SpoolerNotify** 调用之间的间隔应长于传输提供程序处理一封邮件所花的时间。 >，MAPI 后台处理程序可能不会立即处理传入邮件。 MAPI 后台处理程序可能会要求传输提供程序在接收传入邮件之前执行其他任务。 
  

