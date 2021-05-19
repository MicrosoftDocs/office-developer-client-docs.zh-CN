---
title: Internet 邮件属性到 MAPI 属性的映射
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 79d1d2ba-34fe-4851-918f-adbc69c20eee
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: c0a71cbd3b6cdbef091e75ade5d190369a4626a4
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32355816"
---
# <a name="mapping-of-internet-mail-attributes-to-mapi-properties"></a>Internet 邮件属性到 MAPI 属性的映射

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
本附录介绍连接到 Internet 的 MAPI 传输提供程序或 MAPI 感知网关如何在 MAPI 邮件属性与简单邮件传输协议 (SMTP) 邮件属性之间转换。 SMTP 是大部分 Internet 上使用的消息协议。 SMTP 定义一组邮件头（即邮件信封）和邮件内容格式。 SMTP 完全记录在一组两个文档（RFC 821 和 RFC 822）中，可以在 Internet 上的多个 FTP 和 WWW 站点找到这些文档。
  
有关用于与基于 SMTP 的邮件代理通信的 SMTP 协议的信息，请参阅 RFC 821，"简单邮件传输协议"，位于 [https://www.rfc-editor.org](https://www.rfc-editor.org) 。
  
有关寻址和标准邮件头的信息，请参阅 RFC 822，"STANDARD for the Format of ARPA Internet Text Messages"，位于 [https://www.rfc-editor.org](https://www.rfc-editor.org) 。
  
有关 MIME，请参阅 RFC 1521，"MIME (多用途 Internet 邮件扩展) 第一部分：用于指定和描述 Internet 邮件正文格式的机制"，位于 [https://www.rfc-editor.org](https://www.rfc-editor.org) 。
  
将 SMTP 邮件属性映射到 MAPI 属性 (反之亦然) 的目标是确保 MAPI 邮件的完整内容（超过可以使用本机 SMTP 邮件属性进行编码）可以在必须通过 Internet 进行通信的不同 MAPI 组件之间可靠地进行交换。 本文档基于 Microsoft 已对此类组件完成的工作。 
  
本文档假定熟悉 MAPI 传输、TNEF 和 SMTP 邮件。 它尽量简洁，而不是简洁明了。
  
通常，"出站"是指从符合 MAPI 的 UA 或 MTA 到 Internet 的邮件，"入站"是指从 Internet 到 MAPI 组件的邮件。
  

