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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32338491"
---
# <a name="sending-messages-with-tnef"></a>使用 TNEF 发送邮件

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
许多传输提供程序会自动以传输中性封装格式 (TNEF) 发送所有传出邮件。 TNEF 用于传输多个客户端和邮件存储区提供程序在其邮件中支持的格式化文本、各种类型的附件以及自定义邮件类的自定义属性。 尽管大多数传输提供程序的默认模式是使用 TNEF 发送传出邮件, 但某些传输提供程序不支持它。 对于发送和接收 IPM 邮件的标准邮件客户端而言, 缺少 TNEF 支持不是问题。 但是, 对于需要自定义属性的基于表单的客户端或客户端, 使用 TNEF 是非常重要的。 依赖表单或自定义属性的客户端的设计者必须知道它们所使用的传输提供程序的功能。
  
邮件收件人可以通过设置**PR_SEND_RICH_INFO**属性来控制传输提供程序是否通过 TNEF 传输邮件。 有关详细信息, 请参阅**PR_SEND_RICH_INFO** ([PidTagSendRichInfo](pidtagsendrichinfo-canonical-property.md))。 当收件人的**PR_SEND_RICH_INFO**属性设置为 TRUE 时, 支持 TNEF 的传输提供程序会将邮件传输到邮件中。 当该属性设置为 FALSE 时, 格式将被丢弃。 如果**PR_SEND_RICH_INFO**不存在, 则由传输提供程序来选择默认的操作过程。 
  
当客户端和服务提供商创建自定义收件人时, 它们可能会影响其**PR_SEND_RICH_INFO**属性的值, 方法是将_ulFlags_参数中的 MAPI_SEND_NO_RICH_INFO 标志传递给**IAddrBook:: CreateOneOff**或**IMAPISupport:: CreateOneOff**调用。 有关详细信息, 请参阅[IAddrBook:: CreateOneOff](iaddrbook-createoneoff.md)和[IMAPISupport:: CreateOneOff](imapisupport-createoneoff.md)。 传递 MAPI_SEND_NO_RICH_INFO 会导致 MAPI 将自定义收件人的**PR_SEND_RICH_INFO**属性设置为 FALSE;在大多数情况下, 不传递该标志将导致 MAPI 将该属性设置为 TRUE。 一个例外是将自定义收件人的地址解释为 Internet 地址。 在这种情况下, MAPI 会将**PR_SEND_RICH_INFO**设置为 FALSE。 
  

