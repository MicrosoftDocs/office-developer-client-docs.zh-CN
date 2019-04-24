---
title: 将 Internet 邮件属性映射到 MAPI 属性
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
# <a name="mapping-of-internet-mail-attributes-to-mapi-properties"></a>将 Internet 邮件属性映射到 MAPI 属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
本附录介绍了连接到 Internet 的 mapi 传输提供程序或识别 mapi 的网关应如何在 mapi 邮件属性和简单邮件传输协议 (SMTP) 邮件属性之间进行转换。 SMTP 是在许多 Internet 上使用的邮件协议。 SMTP 定义一组邮件头 (邮件信封) 和邮件内容格式。 SMTP 在一组两个文档 (rfc 821 和 rfc 822) 中进行了详细记录, 这些文档可在 Internet 上的大量 FTP 和 WWW 站点中找到。
  
有关用于与基于 smtp 的邮件代理进行通信的 SMTP 协议的信息, 请参阅上[https://www.rfc-editor.org](https://www.rfc-editor.org)的 RFC 821、"简单邮件传输协议"。
  
有关寻址和标准邮件头, 请参阅 RFC 822 "ARPA Internet 短信的格式标准" [https://www.rfc-editor.org](https://www.rfc-editor.org)。
  
对于 MIME, 请参阅 RFC 1521, "MIME (多用途 Internet 邮件扩展) 第一部分: 指定和描述 Internet 邮件正文的格式的机制" at [https://www.rfc-editor.org](https://www.rfc-editor.org)。
  
将 SMTP 邮件属性映射到 MAPI 属性 (反之亦然) 的目标是确保 mapi 邮件的完整内容 (可以使用本机 SMTP 邮件属性进行编码) 可以在不同 MAPI 之间可靠地交换必须通过 Internet 进行通信的组件。 本文档基于在 Microsoft 的此类组件上已完成的工时。 
  
本文档假设您熟悉 MAPI 传输、TNEF 和 SMTP 邮件。 它非常简单, 而不是 abundantly。
  
在约定中, "出站" 是指从 MAPI 兼容的 UA 或 MTA 传递到 Internet 的邮件, "入站" 指邮件从 Internet 传输到 MAPI 组件。
  

