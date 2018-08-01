---
title: 邮件内容
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: ce643afe-e5b6-42f2-b3cf-4efb957c4f2e
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 5e8debcd5a60357f05dfb7b6bde1faf972e50a26
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776502"
---
# <a name="message-content"></a><span data-ttu-id="0bd4a-103">邮件内容</span><span class="sxs-lookup"><span data-stu-id="0bd4a-103">Message Content</span></span>

  
  
<span data-ttu-id="0bd4a-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="0bd4a-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="0bd4a-105">有两个可能的消息内容编码： 一个使用 MIME，其他使用 uuencode。</span><span class="sxs-lookup"><span data-stu-id="0bd4a-105">There are two possible encodings for the message content: one using MIME, the other using uuencode.</span></span> <span data-ttu-id="0bd4a-106">MIME 是首选编码。</span><span class="sxs-lookup"><span data-stu-id="0bd4a-106">MIME is the preferred encoding.</span></span> <span data-ttu-id="0bd4a-107">此外，MAPI 定义的每个收件人属性， **PR_SEND_RICH_INFO** ([PidTagSendRichInfo](pidtagsendrichinfo-canonical-property.md))，其控制 TNEF 信息应包含传出邮件中。</span><span class="sxs-lookup"><span data-stu-id="0bd4a-107">In addition, MAPI defines a per-recipient property, **PR_SEND_RICH_INFO** ([PidTagSendRichInfo](pidtagsendrichinfo-canonical-property.md)), which governs whether or not TNEF information should be included in an outgoing message.</span></span> <span data-ttu-id="0bd4a-108">因此，共有四种方式的编码消息内容的：</span><span class="sxs-lookup"><span data-stu-id="0bd4a-108">So there are a total of four ways of encoding message content:</span></span>
  
- <span data-ttu-id="0bd4a-109">使用 TNEF MIME</span><span class="sxs-lookup"><span data-stu-id="0bd4a-109">MIME with TNEF</span></span>
    
- <span data-ttu-id="0bd4a-110">MIME TNEF 的情况下</span><span class="sxs-lookup"><span data-stu-id="0bd4a-110">MIME without TNEF</span></span>
    
- <span data-ttu-id="0bd4a-111">使用 TNEF 的 uuencode</span><span class="sxs-lookup"><span data-stu-id="0bd4a-111">uuencode with TNEF</span></span>
    
- <span data-ttu-id="0bd4a-112">uuencode 不 TNEF</span><span class="sxs-lookup"><span data-stu-id="0bd4a-112">uuencode without TNEF</span></span>
    
<span data-ttu-id="0bd4a-113">未指定如何选择 MIME 或 uuencode 出站邮件。</span><span class="sxs-lookup"><span data-stu-id="0bd4a-113">How to choose MIME or uuencode for outbound messages is not specified.</span></span>
  
<span data-ttu-id="0bd4a-114">从 TNEF 排除以下属性： **PR_SENDER_\***， **PR_ATTACH_DATA_\***， **PR_BODY**。</span><span class="sxs-lookup"><span data-stu-id="0bd4a-114">The following properties are excluded from TNEF: **PR_SENDER_\***, **PR_ATTACH_DATA_\***, **PR_BODY**.</span></span> <span data-ttu-id="0bd4a-115">TNEF 用于将 stream 中包含其他可传输的消息中的所有属性。</span><span class="sxs-lookup"><span data-stu-id="0bd4a-115">All other transmittable message properties are included in the TNEF stream.</span></span>
  
<span data-ttu-id="0bd4a-116">以下建议旨在提供实现可以决定如何支持的参数的列表：</span><span class="sxs-lookup"><span data-stu-id="0bd4a-116">The following suggestions are intended to provide a list of parameters that the implementation can decide how to support:</span></span>
  
- <span data-ttu-id="0bd4a-117">是否要编码的出站邮件使用 MIME 或 uuencode: boolean。</span><span class="sxs-lookup"><span data-stu-id="0bd4a-117">Whether to encode using MIME or uuencode for outbound messages: boolean.</span></span>
    
- <span data-ttu-id="0bd4a-118">字符集用于出站邮件: （直接复制到 charset 参数） 的字符串或枚举 （转换内部为 charset 字符串）。</span><span class="sxs-lookup"><span data-stu-id="0bd4a-118">Character set to use for outbound messages: string (copied directly to charset parameter) or enumeration (translated internally to charset string).</span></span>
    

