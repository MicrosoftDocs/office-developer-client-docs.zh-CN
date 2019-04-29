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
  
MAPI 后台处理程序是一种 Microsoft Office Outlook 进程的功能, 该进程负责向邮件系统发送邮件以及从邮件系统接收邮件。 MAPI 后台处理程序在邮件接收和传递中起着重要作用。 当邮件系统不可用时, MAPI 后台处理程序将存储邮件并在以后自动将其转发。 此功能可以在必要时保留或发送数据 (如存储和转发) 环境中的一项关键功能, 远程连接是常见的, 网络流量较高。 MAPI 后台处理程序在 Outlook 中作为后台线程运行。
  
MAPI 后台处理程序具有与邮件分发相关的额外职责。 这些额外的职责包括以下几项:
  
- 跟踪由特定传输提供程序处理的收件人类型。
    
- 在传递新邮件时通知客户端应用程序。
    
- 调用邮件预处理和后处理。
    
- 生成指示邮件传递已发生的报告。
    
- 维护已处理收件人的状态。
    
下图显示了如何将邮件从客户端流向邮件系统的高级别。
  
**传出消息流**
  
![传出邮件流](media/amapi_46.gif "传出邮件流")
  
客户端应用程序的用户向一个或多个收件人发送邮件。 邮件存储提供程序启动发送过程, 并使用传输所需的其他信息设置邮件格式。
  
如果出现以下任一情况, MAPI 后台处理程序将收到要处理的邮件:
  
- 邮件存储提供程序未与传输提供程序紧密结合。
    
- 邮件需要进行预处理。
    
- 邮件存储和传输提供程序紧密结合在一起, 但无法处理邮件的所有收件人。
    
如果 MAPI 后台处理程序收到邮件, 它将执行任何必需的预处理并将邮件传递给相应的传输提供程序。 传输提供程序将邮件发送到其邮件系统, 并将其发送给预期的收件人。
  
对于传入的邮件, 流是反向的。 传输提供程序从其邮件系统接收邮件, 并通知 MAPI 后台处理程序。 后台打印程序执行任何必要的后处理并通知邮件存储提供程序是否已到达新邮件。 此通知会导致客户端刷新其消息显示, 从而使用户能够阅读新邮件。
  
## <a name="see-also"></a>另请参阅

- [MAPI 功能和体系结构](mapi-features-and-architecture.md)

