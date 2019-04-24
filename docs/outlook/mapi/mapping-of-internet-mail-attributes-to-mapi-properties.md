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
# <a name="mapping-of-internet-mail-attributes-to-mapi-properties"></a><span data-ttu-id="8c11c-103">将 Internet 邮件属性映射到 MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="8c11c-103">Mapping of Internet Mail Attributes to MAPI Properties</span></span>

  
  
<span data-ttu-id="8c11c-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="8c11c-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="8c11c-105">本附录介绍了连接到 Internet 的 mapi 传输提供程序或识别 mapi 的网关应如何在 mapi 邮件属性和简单邮件传输协议 (SMTP) 邮件属性之间进行转换。</span><span class="sxs-lookup"><span data-stu-id="8c11c-105">This appendix describes how a MAPI transport provider or MAPI-aware gateway which connects to the Internet should translate between MAPI message properties and Simple Mail Transport Protocol (SMTP) message attributes.</span></span> <span data-ttu-id="8c11c-106">SMTP 是在许多 Internet 上使用的邮件协议。</span><span class="sxs-lookup"><span data-stu-id="8c11c-106">SMTP is the messaging protocol used on much of the Internet.</span></span> <span data-ttu-id="8c11c-107">SMTP 定义一组邮件头 (邮件信封) 和邮件内容格式。</span><span class="sxs-lookup"><span data-stu-id="8c11c-107">SMTP defines a set of message headers — the message envelope — and a message content format.</span></span> <span data-ttu-id="8c11c-108">SMTP 在一组两个文档 (rfc 821 和 rfc 822) 中进行了详细记录, 这些文档可在 Internet 上的大量 FTP 和 WWW 站点中找到。</span><span class="sxs-lookup"><span data-stu-id="8c11c-108">SMTP is fully documented in a set of two documents, RFC 821 and RFC 822, which can be found at a number of FTP and WWW sites on the Internet.</span></span>
  
<span data-ttu-id="8c11c-109">有关用于与基于 smtp 的邮件代理进行通信的 SMTP 协议的信息, 请参阅上[https://www.rfc-editor.org](https://www.rfc-editor.org)的 RFC 821、"简单邮件传输协议"。</span><span class="sxs-lookup"><span data-stu-id="8c11c-109">For information on the SMTP protocol used to communicate with SMTP-based mail agents, see RFC 821, "Simple Mail Transfer Protocol," at [https://www.rfc-editor.org](https://www.rfc-editor.org).</span></span>
  
<span data-ttu-id="8c11c-110">有关寻址和标准邮件头, 请参阅 RFC 822 "ARPA Internet 短信的格式标准" [https://www.rfc-editor.org](https://www.rfc-editor.org)。</span><span class="sxs-lookup"><span data-stu-id="8c11c-110">For addressing and standard message headers, see RFC 822, "Standard for the Format of ARPA Internet Text Messages," at [https://www.rfc-editor.org](https://www.rfc-editor.org).</span></span>
  
<span data-ttu-id="8c11c-111">对于 MIME, 请参阅 RFC 1521, "MIME (多用途 Internet 邮件扩展) 第一部分: 指定和描述 Internet 邮件正文的格式的机制" at [https://www.rfc-editor.org](https://www.rfc-editor.org)。</span><span class="sxs-lookup"><span data-stu-id="8c11c-111">For MIME, see RFC 1521, "MIME (Multipurpose Internet Mail Extensions) Part One: Mechanisms for Specifying and Describing the Format of Internet Message Bodies," at [https://www.rfc-editor.org](https://www.rfc-editor.org).</span></span>
  
<span data-ttu-id="8c11c-112">将 SMTP 邮件属性映射到 MAPI 属性 (反之亦然) 的目标是确保 mapi 邮件的完整内容 (可以使用本机 SMTP 邮件属性进行编码) 可以在不同 MAPI 之间可靠地交换必须通过 Internet 进行通信的组件。</span><span class="sxs-lookup"><span data-stu-id="8c11c-112">The goal of mapping SMTP message attributes to MAPI properties (and vice versa) is to ensure that the full content of MAPI messages, over and above that which can be encoded using native SMTP message attributes, can be reliably exchanged among different MAPI components that must communicate over the Internet.</span></span> <span data-ttu-id="8c11c-113">本文档基于在 Microsoft 的此类组件上已完成的工时。</span><span class="sxs-lookup"><span data-stu-id="8c11c-113">This document is based on work already done on such components at Microsoft.</span></span> 
  
<span data-ttu-id="8c11c-114">本文档假设您熟悉 MAPI 传输、TNEF 和 SMTP 邮件。</span><span class="sxs-lookup"><span data-stu-id="8c11c-114">This document assumes familiarity with MAPI transports, TNEF, and SMTP mail.</span></span> <span data-ttu-id="8c11c-115">它非常简单, 而不是 abundantly。</span><span class="sxs-lookup"><span data-stu-id="8c11c-115">It strives to be concise rather than abundantly clear.</span></span>
  
<span data-ttu-id="8c11c-116">在约定中, "出站" 是指从 MAPI 兼容的 UA 或 MTA 传递到 Internet 的邮件, "入站" 指邮件从 Internet 传输到 MAPI 组件。</span><span class="sxs-lookup"><span data-stu-id="8c11c-116">As a convention, "outbound" refers to mail traveling from a MAPI-compliant UA or MTA to the Internet, and "inbound" refers to mail traveling from the Internet to a MAPI component.</span></span>
  

