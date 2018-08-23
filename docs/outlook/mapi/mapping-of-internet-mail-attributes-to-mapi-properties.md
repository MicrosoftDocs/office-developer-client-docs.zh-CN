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
ms.openlocfilehash: 54443001e3cb14603c8f8f798f2a4068d73b00eb
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22568061"
---
# <a name="mapping-of-internet-mail-attributes-to-mapi-properties"></a><span data-ttu-id="87f13-103">将 Internet Mail 属性映射到 MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="87f13-103">Mapping of Internet Mail Attributes to MAPI Properties</span></span>

  
  
<span data-ttu-id="87f13-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="87f13-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="87f13-105">此附录介绍 MAPI 消息属性和简单邮件传输协议 (SMTP) 邮件属性之间的 MAPI 传输提供程序或其连接到 Internet 的 MAPI 感知网关应翻译。</span><span class="sxs-lookup"><span data-stu-id="87f13-105">This appendix describes how a MAPI transport provider or MAPI-aware gateway which connects to the Internet should translate between MAPI message properties and Simple Mail Transport Protocol (SMTP) message attributes.</span></span> <span data-ttu-id="87f13-106">SMTP 是何种 Internet 上使用的消息协议。</span><span class="sxs-lookup"><span data-stu-id="87f13-106">SMTP is the messaging protocol used on much of the Internet.</span></span> <span data-ttu-id="87f13-107">SMTP 定义一组的邮件头 — 对邮件信封进行 — 和邮件内容格式。</span><span class="sxs-lookup"><span data-stu-id="87f13-107">SMTP defines a set of message headers — the message envelope — and a message content format.</span></span> <span data-ttu-id="87f13-108">SMTP 完全记录集中的两个文档，RFC 821 和 RFC 822，可以在 Internet 找到 FTP 和 WWW 网站的号码。</span><span class="sxs-lookup"><span data-stu-id="87f13-108">SMTP is fully documented in a set of two documents, RFC 821 and RFC 822, which can be found at a number of FTP and WWW sites on the Internet.</span></span>
  
<span data-ttu-id="87f13-109">用于与基于 SMTP 邮件代理进行通信的 SMTP 协议的信息，请参阅 RFC 821，"简单邮件传输协议，"在[http://www.rfc-editor.org](http://www.rfc-editor.org)。</span><span class="sxs-lookup"><span data-stu-id="87f13-109">For information on the SMTP protocol used to communicate with SMTP-based mail agents, see RFC 821, "Simple Mail Transfer Protocol," at [http://www.rfc-editor.org](http://www.rfc-editor.org).</span></span>
  
<span data-ttu-id="87f13-110">寻址和标准的邮件头，请参阅 RFC 822，"标准的格式的 ARPA Internet 文本邮件，"at [http://www.rfc-editor.org](http://www.rfc-editor.org)。</span><span class="sxs-lookup"><span data-stu-id="87f13-110">For addressing and standard message headers, see RFC 822, "Standard for the Format of ARPA Internet Text Messages," at [http://www.rfc-editor.org](http://www.rfc-editor.org).</span></span>
  
<span data-ttu-id="87f13-111">MIME，请参阅 RFC 1521"MIME （多用途 Internet 邮件扩展） 部件一个： 指定和描述的 Internet 邮件正文的格式的机制"在[http://www.rfc-editor.org](http://www.rfc-editor.org)。</span><span class="sxs-lookup"><span data-stu-id="87f13-111">For MIME, see RFC 1521, "MIME (Multipurpose Internet Mail Extensions) Part One: Mechanisms for Specifying and Describing the Format of Internet Message Bodies," at [http://www.rfc-editor.org](http://www.rfc-editor.org).</span></span>
  
<span data-ttu-id="87f13-112">映射到 MAPI 属性 （反之亦然） 的 SMTP 邮件属性的目标是以确保可以在不同的 MAPI 之间可靠地交换 MAPI 消息，除了，其中可以使用本机 SMTP 邮件特性、 编码的完全内容必须通过 Internet 进行通信的组件。</span><span class="sxs-lookup"><span data-stu-id="87f13-112">The goal of mapping SMTP message attributes to MAPI properties (and vice versa) is to ensure that the full content of MAPI messages, over and above that which can be encoded using native SMTP message attributes, can be reliably exchanged among different MAPI components that must communicate over the Internet.</span></span> <span data-ttu-id="87f13-113">本文档基于 microsoft 此类组件的已完成的工时。</span><span class="sxs-lookup"><span data-stu-id="87f13-113">This document is based on work already done on such components at Microsoft.</span></span> 
  
<span data-ttu-id="87f13-114">本文档假定您熟悉 MAPI 传输、 TNEF 和 SMTP 邮件。</span><span class="sxs-lookup"><span data-stu-id="87f13-114">This document assumes familiarity with MAPI transports, TNEF, and SMTP mail.</span></span> <span data-ttu-id="87f13-115">它在努力是简洁，而不是显而易见。</span><span class="sxs-lookup"><span data-stu-id="87f13-115">It strives to be concise rather than abundantly clear.</span></span>
  
<span data-ttu-id="87f13-116">作为约定，"出站"引用邮件从 MAPI 兼容的 UA 或 MTA 到达 Internet 和"入站"指的是从 Internet 到 MAPI 组件旅行的邮件。</span><span class="sxs-lookup"><span data-stu-id="87f13-116">As a convention, "outbound" refers to mail traveling from a MAPI-compliant UA or MTA to the Internet, and "inbound" refers to mail traveling from the Internet to a MAPI component.</span></span>
  

