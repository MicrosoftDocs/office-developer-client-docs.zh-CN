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
  
传输提供程序控制 MAPI 后台处理程序是否必须在收到邮件时对其进行轮询, 或者是否在新邮件到达时对 mapi 后台处理程序执行回调。 传输提供程序在从[IXPProvider:: TransportLogon](ixpprovider-transportlogon.md)返回到请求轮询时设置 SP_LOGON_POLL 标志。 否则, 在传入邮件可用时, 传输提供程序将使用[IMAPISupport:: SpoolerNotify](imapisupport-spoolernotify.md) 。 了解传入邮件可用后, MAPI 后台处理程序将打开一封新邮件, 并要求传输提供程序将接收到的邮件属性存储到邮件中。 
  
此过程的工作方式如下所示:
  
1. 可用的邮件由传输提供程序调用**IMAPISupport:: SpoolerNotify**或 MAPI 后台处理程序调用[IXPLogon::P oll](ixplogon-poll.md)。
    
2. MAPI 后台处理程序调用[IXPLogon:: StartMessage](ixplogon-startmessage.md)以启动进程。 
    
3. 传输提供程序将引用值放在**StartMessage**中引用的位置。 这些引用值允许传输提供程序和 MAPI 后台处理程序在有多个要传递的邮件时跟踪正在处理的邮件。
    
4. 传输提供程序将邮件数据存储到传递的[IMessage: IMAPIProp](imessageimapiprop.md)实例中。 
    
5. 传输提供程序对**IMessage**实例调用[IMAPIProp:: SaveChanges](imapiprop-savechanges.md)方法, 并从**StartMessage**返回。
    
6. MAPI 后台处理程序调用[IXPLogon:: TransportNotify](ixplogon-transportnotify.md) (如果它必须停止邮件传递)。 
    
> [!NOTE]
> 如果传输提供程序必须传递大量邮件, 而传输提供程序正在使用**IMAPISupport:: SpoolerNotify**而不是**IXPLogon::P oll**, 则应谨慎地将**SpoolerNotify**调用得过于频繁, 以便不会deprive 其他传输提供程序的 CPU 时间。 MAPI 后台处理程序具有防止发生这种情况的逻辑, 但一般情况下, **SpoolerNotify**呼叫之间的时间间隔应长于您的传输提供程序处理一封邮件所需的时间。 > 此外, MAPI 后台处理程序可能不会立即处理传入的邮件。 MAPI 后台处理程序可能要求传输提供程序在接收传入邮件之前执行其他任务。 
  

