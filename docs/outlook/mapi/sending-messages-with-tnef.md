---
title: 使用 TNEF 发送邮件
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 6e2df265-b9dd-4e19-8ca5-3e31804e9120
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: fb26d854b47894d8f37763b17e5ba0b26fd25ff6
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778752"
---
# <a name="sending-messages-with-tnef"></a>使用 TNEF 发送邮件

  
  
**适用于**： Outlook 
  
许多传输提供程序自动发送所有传出邮件使用传输中性封装格式 (TNEF)。 TNEF 用于传输多个客户端和消息存储提供程序支持在其邮件、 各种类型和自定义属性自定义邮件类的附件中的格式化的文本。 尽管大多数传输提供程序的默认模式是发送传出邮件 TNEF，某些传输提供程序不支持它。 缺少的 TNEF 支持不是标准消息的客户端的发送和接收 IPM 消息的问题。 但是，对于基于窗体的客户端或需要自定义属性的客户端，使用 TNEF 非常重要。 设计器的依赖于窗体或自定义属性的客户端必须知道他们使用的传输提供程序的功能。
  
邮件的收件人，可以控制传输提供程序将使用 TNEF 的消息传输通过**PR_SEND_RICH_INFO**属性设置。 有关详细信息，请参阅**PR_SEND_RICH_INFO** ([PidTagSendRichInfo](pidtagsendrichinfo-canonical-property.md))。 当收件人的**PR_SEND_RICH_INFO**属性设置为 TRUE 时，支持 TNEF 传输提供程序将其传送消息。 当该属性设置为 FALSE 时，格式将被丢弃。 **PR_SEND_RICH_INFO**不存在，它由传输提供程序选择操作的默认参加其他课程。 
  
在客户端和服务提供商创建一个自定义收件人，就可以通过将 MAPI_SEND_NO_RICH_INFO 标志_ulFlags_参数中传递给**IAddrBook::CreateOneOff**或**影响其**PR_SEND_RICH_INFO**属性的值IMAPISupport::CreateOneOff**呼叫。 有关详细信息，请参阅[IAddrBook::CreateOneOff](iaddrbook-createoneoff.md)和[IMAPISupport::CreateOneOff](imapisupport-createoneoff.md)。 将传递 MAPI_SEND_NO_RICH_INFO 会导致 MAPI 将自定义收信人**PR_SEND_RICH_INFO**属性设置为 FALSE;在大多数情况下不传递标志会导致 MAPI 属性设置为 TRUE。 一个例外，如果自定义收信人地址被解释为 Internet 地址。 在此一个的情况下，MAPI 将**PR_SEND_RICH_INFO**设置为 FALSE。 
  

