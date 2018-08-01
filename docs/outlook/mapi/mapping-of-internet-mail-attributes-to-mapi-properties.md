---
title: 将 Internet Mail 属性映射到 MAPI 属性
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 79d1d2ba-34fe-4851-918f-adbc69c20eee
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 4d1bc5fc5a5e304d81ab4252a527d0e52b0d6e3c
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/21/2018
ms.locfileid: "19776413"
---
# <a name="mapping-of-internet-mail-attributes-to-mapi-properties"></a>将 Internet Mail 属性映射到 MAPI 属性

  
  
**适用于**： Outlook 
  
此附录介绍 MAPI 消息属性和简单邮件传输协议 (SMTP) 邮件属性之间的 MAPI 传输提供程序或其连接到 Internet 的 MAPI 感知网关应翻译。 SMTP 是何种 Internet 上使用的消息协议。 SMTP 定义一组的邮件头 — 对邮件信封进行 — 和邮件内容格式。 SMTP 完全记录集中的两个文档，RFC 821 和 RFC 822，可以在 Internet 找到 FTP 和 WWW 网站的号码。
  
用于与基于 SMTP 邮件代理进行通信的 SMTP 协议的信息，请参阅 RFC 821，"简单邮件传输协议，"在[http://www.rfc-editor.org](http://www.rfc-editor.org)。
  
寻址和标准的邮件头，请参阅 RFC 822，"标准的格式的 ARPA Internet 文本邮件，"at [http://www.rfc-editor.org](http://www.rfc-editor.org)。
  
MIME，请参阅 RFC 1521"MIME （多用途 Internet 邮件扩展） 部件一个： 指定和描述的 Internet 邮件正文的格式的机制"在[http://www.rfc-editor.org](http://www.rfc-editor.org)。
  
映射到 MAPI 属性 （反之亦然） 的 SMTP 邮件属性的目标是以确保可以在不同的 MAPI 之间可靠地交换 MAPI 消息，除了，其中可以使用本机 SMTP 邮件特性、 编码的完全内容必须通过 Internet 进行通信的组件。 本文档基于 microsoft 此类组件的已完成的工时。 
  
本文档假定您熟悉 MAPI 传输、 TNEF 和 SMTP 邮件。 它在努力是简洁，而不是显而易见。
  
作为约定，"出站"引用邮件从 MAPI 兼容的 UA 或 MTA 到达 Internet 和"入站"指的是从 Internet 到 MAPI 组件旅行的邮件。
  

