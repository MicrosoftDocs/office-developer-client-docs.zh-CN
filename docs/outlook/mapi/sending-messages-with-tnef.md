---
title: 使用 TNEF 发送邮件
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 6e2df265-b9dd-4e19-8ca5-3e31804e9120
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 7ff7f79b5e74412e9bbb4b4882c6a7d45e50fe6a
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33420848"
---
# <a name="sending-messages-with-tnef"></a>使用 TNEF 发送邮件

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
许多传输提供程序使用 TNEF 传输中性封装格式自动发送所有 (发) 。 TNEF 用于传输许多客户端和邮件存储提供程序支持其邮件、各种类型的附件以及自定义邮件类的自定义属性的格式化文本。 虽然大多数传输提供程序的默认模式是使用 TNEF 发送传出邮件，但一些传输提供程序不支持此模式。 TNEF 支持不足不是发送和接收 IPM 邮件的标准邮件客户端的问题。 但是，对于基于表单的客户端或需要自定义属性的客户端，使用 TNEF 至关重要。 依赖于窗体或自定义属性的客户端设计者必须了解他们使用的传输提供程序的功能。
  
邮件收件人可以通过设置 TNEF 属性来控制传输 **PR_SEND_RICH_INFO传输邮件** 。 有关详细信息，请参阅 **PR_SEND_RICH_INFO** ([PidTagSendRichInfo](pidtagsendrichinfo-canonical-property.md)) 。 当收件人的 **PR_SEND_RICH_INFO** 属性设置为 TRUE 时，支持 TNEF 的传输提供程序会随邮件一起传输它。 当该属性设置为 FALSE 时，将丢弃格式。 当 **PR_SEND_RICH_INFO** 不存在时，由传输提供程序选择默认操作过程。 
  
当客户端和服务提供商创建自定义收件人时，它们可以通过将 _ulFlags_ 参数中的 MAPI_SEND_NO_RICH_INFO 标志传递给 **IAddrBook：：CreateOneOff** 或 **IMAPISupport：：CreateOneOff** 调用来影响其 **PR_SEND_RICH_INFO** 属性的值。 有关详细信息，请参阅 [IAddrBook：：CreateOneOff](iaddrbook-createoneoff.md) 和 [IMAPISupport：：CreateOneOff](imapisupport-createoneoff.md)。 传递MAPI_SEND_NO_RICH_INFO会导致 MAPI 将自定义收件人的 PR_SEND_RICH_INFO **属性设置为** FALSE;在大多数情况下，不传递标志会导致 MAPI 将该属性设置为 TRUE。 一个例外是自定义收件人的地址被解释为 Internet 地址。 在这种情况下，MAPI **将PR_SEND_RICH_INFO** FALSE。 
  

