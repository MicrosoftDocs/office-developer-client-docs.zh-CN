---
title: 邮件接收模型
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: d85d269e-2251-4399-9159-a2f47a85e3d1
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: cecdb2c30d6c9df2aafbeed43714269b863ebc48
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/15/2018
ms.locfileid: "19776503"
---
# <a name="message-reception-model"></a>邮件接收模型

  
  
**适用于**： Outlook 
  
传输提供程序控制 MAPI 后台处理程序是否必须轮询其为传入邮件或新邮件到达时是否它执行回调到 MAPI 后台处理程序。 返回从[IXPProvider::TransportLogon](ixpprovider-transportlogon.md)轮询请求时，传输提供程序设置 SP_LOGON_POLL 标志。 否则，传输提供程序使用[IMAPISupport::SpoolerNotify](imapisupport-spoolernotify.md)传入邮件时可用。 学习传入邮件可用之后, MAPI 后台处理程序打开一个新邮件，并请求获得要向邮件存储收到的邮件属性的传输提供程序。 
  
此过程的工作方式如下：
  
1. 通过调用**IMAPISupport::SpoolerNotify**任一传输的提供程序或 MAPI 后台处理程序调用[IXPLogon::Poll](ixplogon-poll.md)表示可用的邮件。
    
2. MAPI 后台处理程序调用[IXPLogon::StartMessage](ixplogon-startmessage.md)要启动过程。 
    
3. 传输提供程序将引用值放在**StartMessage**中引用的位置。 这些参考值允许传输提供程序和 MAPI 后台处理程序，以跟踪多个邮件传递时，正在处理的消息。
    
4. 传输提供程序将消息数据存储到传递[IMessage: IMAPIProp](imessageimapiprop.md)实例。 
    
5. 传输提供程序**IMessage**实例上调用[IMAPIProp::SaveChanges](imapiprop-savechanges.md)方法，并返回**StartMessage**。
    
6. MAPI 后台处理程序调用[IXPLogon::TransportNotify](ixplogon-transportnotify.md) ，如果它必须停止邮件传递。 
    
> [!NOTE]
> 如果传输提供程序必须提供大量的消息，而不**IXPLogon::Poll**传输提供程序使用**IMAPISupport::SpoolerNotify** ，应注意不呼叫**SpoolerNotify**过于频繁顺序不到导致丧失 CPU 时间其他传输提供的程序。 MAPI 后台处理程序具有逻辑以防止此问题的发生，但通常**SpoolerNotify**呼叫之间的间隔应超过所用您的传输提供程序，以处理一条消息的时间。 > 此外，MAPI 后台处理程序可能无法立即处理传入消息。 MAPI 后台处理程序可能会要求要执行其他任务之前收到的传入消息的传输提供程序。 
  

