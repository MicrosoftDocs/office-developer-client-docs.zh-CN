---
title: 邮件内容
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: ce643afe-e5b6-42f2-b3cf-4efb957c4f2e
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: c4d2439c06da292c9cc72c1506a1ae4d10c6704f
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33435458"
---
# <a name="message-content"></a><span data-ttu-id="381cc-103">邮件内容</span><span class="sxs-lookup"><span data-stu-id="381cc-103">Message Content</span></span>

  
  
<span data-ttu-id="381cc-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="381cc-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="381cc-105">邮件内容有两种可能的编码：一种使用 MIME，另一种使用 uuencode。</span><span class="sxs-lookup"><span data-stu-id="381cc-105">There are two possible encodings for the message content: one using MIME, the other using uuencode.</span></span> <span data-ttu-id="381cc-106">MIME 是首选编码。</span><span class="sxs-lookup"><span data-stu-id="381cc-106">MIME is the preferred encoding.</span></span> <span data-ttu-id="381cc-107">此外，MAPI 定义每收件人属性 **PR_SEND_RICH_INFO** ([PidTagSendRichInfo](pidtagsendrichinfo-canonical-property.md)) ，该属性控制是否在传出邮件中包含 TNEF 信息。</span><span class="sxs-lookup"><span data-stu-id="381cc-107">In addition, MAPI defines a per-recipient property, **PR_SEND_RICH_INFO** ([PidTagSendRichInfo](pidtagsendrichinfo-canonical-property.md)), which governs whether or not TNEF information should be included in an outgoing message.</span></span> <span data-ttu-id="381cc-108">因此，总共有四种方法可以编码邮件内容：</span><span class="sxs-lookup"><span data-stu-id="381cc-108">So there are a total of four ways of encoding message content:</span></span>
  
- <span data-ttu-id="381cc-109">MIME 与 TNEF</span><span class="sxs-lookup"><span data-stu-id="381cc-109">MIME with TNEF</span></span>
    
- <span data-ttu-id="381cc-110">没有 TNEF 的 MIME</span><span class="sxs-lookup"><span data-stu-id="381cc-110">MIME without TNEF</span></span>
    
- <span data-ttu-id="381cc-111">使用 TNEF 的 uuencode</span><span class="sxs-lookup"><span data-stu-id="381cc-111">uuencode with TNEF</span></span>
    
- <span data-ttu-id="381cc-112">不含 TNEF 的 uuencode</span><span class="sxs-lookup"><span data-stu-id="381cc-112">uuencode without TNEF</span></span>
    
<span data-ttu-id="381cc-113">未指定如何为出站邮件选择 MIME 或 uuencode。</span><span class="sxs-lookup"><span data-stu-id="381cc-113">How to choose MIME or uuencode for outbound messages is not specified.</span></span>
  
<span data-ttu-id="381cc-114">TNEF 中不包括以下属性 **：PR_SENDER_ \*** **\* 、PR_ATTACH_DATA_** **、PR_BODY**。</span><span class="sxs-lookup"><span data-stu-id="381cc-114">The following properties are excluded from TNEF: **PR_SENDER_\***, **PR_ATTACH_DATA_\***, **PR_BODY**.</span></span> <span data-ttu-id="381cc-115">所有其他可传输邮件属性都包含在 TNEF 流中。</span><span class="sxs-lookup"><span data-stu-id="381cc-115">All other transmittable message properties are included in the TNEF stream.</span></span>
  
<span data-ttu-id="381cc-116">以下建议旨在提供实现可决定如何支持的参数列表：</span><span class="sxs-lookup"><span data-stu-id="381cc-116">The following suggestions are intended to provide a list of parameters that the implementation can decide how to support:</span></span>
  
- <span data-ttu-id="381cc-117">是使用 MIME 还是 uuencode 对出站邮件进行编码：boolean。</span><span class="sxs-lookup"><span data-stu-id="381cc-117">Whether to encode using MIME or uuencode for outbound messages: boolean.</span></span>
    
- <span data-ttu-id="381cc-118">用于出站邮件的字符集：字符串 (直接复制到 charset 参数) 或枚举 (内部转换为 charset 字符串) 。</span><span class="sxs-lookup"><span data-stu-id="381cc-118">Character set to use for outbound messages: string (copied directly to charset parameter) or enumeration (translated internally to charset string).</span></span>
    

