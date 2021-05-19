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
# <a name="mapping-of-internet-mail-attributes-to-mapi-properties"></a><span data-ttu-id="228cc-103">Internet 邮件属性到 MAPI 属性的映射</span><span class="sxs-lookup"><span data-stu-id="228cc-103">Mapping of Internet Mail Attributes to MAPI Properties</span></span>

  
  
<span data-ttu-id="228cc-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="228cc-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="228cc-105">本附录介绍连接到 Internet 的 MAPI 传输提供程序或 MAPI 感知网关如何在 MAPI 邮件属性与简单邮件传输协议 (SMTP) 邮件属性之间转换。</span><span class="sxs-lookup"><span data-stu-id="228cc-105">This appendix describes how a MAPI transport provider or MAPI-aware gateway which connects to the Internet should translate between MAPI message properties and Simple Mail Transport Protocol (SMTP) message attributes.</span></span> <span data-ttu-id="228cc-106">SMTP 是大部分 Internet 上使用的消息协议。</span><span class="sxs-lookup"><span data-stu-id="228cc-106">SMTP is the messaging protocol used on much of the Internet.</span></span> <span data-ttu-id="228cc-107">SMTP 定义一组邮件头（即邮件信封）和邮件内容格式。</span><span class="sxs-lookup"><span data-stu-id="228cc-107">SMTP defines a set of message headers — the message envelope — and a message content format.</span></span> <span data-ttu-id="228cc-108">SMTP 完全记录在一组两个文档（RFC 821 和 RFC 822）中，可以在 Internet 上的多个 FTP 和 WWW 站点找到这些文档。</span><span class="sxs-lookup"><span data-stu-id="228cc-108">SMTP is fully documented in a set of two documents, RFC 821 and RFC 822, which can be found at a number of FTP and WWW sites on the Internet.</span></span>
  
<span data-ttu-id="228cc-109">有关用于与基于 SMTP 的邮件代理通信的 SMTP 协议的信息，请参阅 RFC 821，"简单邮件传输协议"，位于 [https://www.rfc-editor.org](https://www.rfc-editor.org) 。</span><span class="sxs-lookup"><span data-stu-id="228cc-109">For information on the SMTP protocol used to communicate with SMTP-based mail agents, see RFC 821, "Simple Mail Transfer Protocol," at [https://www.rfc-editor.org](https://www.rfc-editor.org).</span></span>
  
<span data-ttu-id="228cc-110">有关寻址和标准邮件头的信息，请参阅 RFC 822，"STANDARD for the Format of ARPA Internet Text Messages"，位于 [https://www.rfc-editor.org](https://www.rfc-editor.org) 。</span><span class="sxs-lookup"><span data-stu-id="228cc-110">For addressing and standard message headers, see RFC 822, "Standard for the Format of ARPA Internet Text Messages," at [https://www.rfc-editor.org](https://www.rfc-editor.org).</span></span>
  
<span data-ttu-id="228cc-111">有关 MIME，请参阅 RFC 1521，"MIME (多用途 Internet 邮件扩展) 第一部分：用于指定和描述 Internet 邮件正文格式的机制"，位于 [https://www.rfc-editor.org](https://www.rfc-editor.org) 。</span><span class="sxs-lookup"><span data-stu-id="228cc-111">For MIME, see RFC 1521, "MIME (Multipurpose Internet Mail Extensions) Part One: Mechanisms for Specifying and Describing the Format of Internet Message Bodies," at [https://www.rfc-editor.org](https://www.rfc-editor.org).</span></span>
  
<span data-ttu-id="228cc-112">将 SMTP 邮件属性映射到 MAPI 属性 (反之亦然) 的目标是确保 MAPI 邮件的完整内容（超过可以使用本机 SMTP 邮件属性进行编码）可以在必须通过 Internet 进行通信的不同 MAPI 组件之间可靠地进行交换。</span><span class="sxs-lookup"><span data-stu-id="228cc-112">The goal of mapping SMTP message attributes to MAPI properties (and vice versa) is to ensure that the full content of MAPI messages, over and above that which can be encoded using native SMTP message attributes, can be reliably exchanged among different MAPI components that must communicate over the Internet.</span></span> <span data-ttu-id="228cc-113">本文档基于 Microsoft 已对此类组件完成的工作。</span><span class="sxs-lookup"><span data-stu-id="228cc-113">This document is based on work already done on such components at Microsoft.</span></span> 
  
<span data-ttu-id="228cc-114">本文档假定熟悉 MAPI 传输、TNEF 和 SMTP 邮件。</span><span class="sxs-lookup"><span data-stu-id="228cc-114">This document assumes familiarity with MAPI transports, TNEF, and SMTP mail.</span></span> <span data-ttu-id="228cc-115">它尽量简洁，而不是简洁明了。</span><span class="sxs-lookup"><span data-stu-id="228cc-115">It strives to be concise rather than abundantly clear.</span></span>
  
<span data-ttu-id="228cc-116">通常，"出站"是指从符合 MAPI 的 UA 或 MTA 到 Internet 的邮件，"入站"是指从 Internet 到 MAPI 组件的邮件。</span><span class="sxs-lookup"><span data-stu-id="228cc-116">As a convention, "outbound" refers to mail traveling from a MAPI-compliant UA or MTA to the Internet, and "inbound" refers to mail traveling from the Internet to a MAPI component.</span></span>
  

