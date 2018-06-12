---
title: 消息提交模型
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 4bcd19f6-c225-43ac-8c27-c46388e9097a
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 653a9df6ec414aa18c44d8035a59f021d7cc19b8
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776523"
---
# <a name="message-submission-model"></a>消息提交模型

  
  
**适用于**： Outlook 
  
提交邮件被通过一系列调用从 MAPI 后台打印到传输提供程序。 呼叫顺序编排会出现，如下所示：
  
1. MAPI 后台处理程序调用[IXPLogon::SubmitMessage](ixplogon-submitmessage.md)，传递中[IMessage: IMAPIProp](imessageimapiprop.md)实例，以开始过程。 
    
2. 传输提供程序然后放置引用值 — 传输定义的标识符在将来使用引用此消息 — **SubmitMessage**中引用的位置。
    
3. 传输提供程序使用传递的**IMessage**实例访问邮件数据。 为其接受责任传递**IMessage**中每个收件人，传输提供程序将**PR_RESPONSIBILITY** ([PidTagResponsibility](pidtagresponsibility-canonical-property.md)) 属性，设置，然后返回。
    
4. 传输提供程序可以使用[IMAPISupport::StatusRecips](imapisupport-statusrecips.md)方法，以指示是否识别无法送达，任何收件人，或创建一个标准送达报告。 **StatusRecips**是已确定某些收件人不能传送到传输提供程序方便或其基础的消息系统的用户或客户端应用程序可能已接收的传递信息发现有用。 
    
5. 对[IXPLogon::EndMessage](ixplogon-endmessage.md)的 MAPI 后台处理程序的调用是最终的责任交付 MAPI 后台处理程序从到传输提供程序的邮件。 
    
6. MAPI 后台处理程序可以使用[IXPLogon::TransportNotify](ixplogon-transportnotify.md)取消**SubmitMessage**或**EndMessage**呼叫过程中处理的消息。 
    

