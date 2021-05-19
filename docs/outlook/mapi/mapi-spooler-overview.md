---
title: MAPI 后台处理程序概述
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 5866b202-883e-454e-aeb1-61526c43dae9
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 162957ea17b5a82d4da68340e971d328c85cd9f7
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33432714"
---
# <a name="mapi-spooler-overview"></a>MAPI 后台处理程序概述
  
**适用于**：Outlook 2013 | Outlook 2016 
  
MAPI 后台处理程序是邮件Microsoft Office Outlook的一个功能，该过程负责向邮件系统发送邮件和从邮件系统接收邮件。 MAPI 后台处理程序在邮件接收和传递中起到重要作用。 当邮件系统不可用时，MAPI 后台处理程序将存储邮件，并稍后自动转发这些邮件。 这种在必要时保留或发送数据的功能称为存储和转发，这是远程连接很常见且网络流量高的环境中的一项关键功能。 MAPI 后台处理程序作为后台线程在 Outlook。
  
MAPI 后台处理程序具有与邮件分发相关的其他责任。 这些额外职责包括：
  
- 跟踪由特定传输提供程序处理的收件人类型。
    
- 在传递新邮件时通知客户端应用程序。
    
- 调用邮件预处理和后处理。
    
- 生成指示已发生邮件传递的报告。
    
- 维护已处理收件人的状态。
    
下图在高级别显示了邮件如何从客户端流动到邮件系统。
  
**传出消息流**
  
![传出邮件流](media/amapi_46.gif "传出邮件流")
  
客户端应用程序的用户向一个或多个收件人发送邮件。 邮件存储提供程序启动发送过程，使用传输所需的其他信息设置邮件的格式。
  
如果发生以下任一情况，MAPI 后台处理程序将接收要处理的消息：
  
- 邮件存储提供程序不会与传输提供程序紧密结合。
    
- 邮件需要预处理。
    
- 邮件存储和传输提供程序是紧密耦合的，但它们无法处理邮件发送到的所有收件人。
    
如果 MAPI 后台处理程序收到邮件，它将执行任何所需的预处理，将邮件传递至相应的传输提供程序。 传输提供程序将邮件发送到其邮件系统，邮件系统会将其发送给预期收件人。
  
对于传入的邮件，流将反转。 传输提供程序接收来自其邮件系统的邮件，并通知 MAPI 后台处理程序。 后台处理程序执行任何必要的后处理，并通知邮件存储提供程序新邮件已到达。 此通知使客户端刷新其消息显示，使用户可以阅读新邮件。
  
## <a name="see-also"></a>另请参阅

- [MAPI 功能和体系结构](mapi-features-and-architecture.md)

