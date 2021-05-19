---
title: 消息文本
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 4d1837f1-494f-481b-9e09-ab8249f1488c
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: fcbdec5adcb47ffac431a832cbb851ee4ebe16d8
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33418545"
---
# <a name="message-text"></a><span data-ttu-id="9ef20-103">消息文本</span><span class="sxs-lookup"><span data-stu-id="9ef20-103">Message Text</span></span>

  
  
<span data-ttu-id="9ef20-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="9ef20-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="9ef20-105">对于 MIME 模式下的出站邮件，内容类型取决于是否有附件以及邮件文本的外观。</span><span class="sxs-lookup"><span data-stu-id="9ef20-105">For outbound messages in MIME mode, the content-type depends on whether there are attachments and what the message text looks like.</span></span> <span data-ttu-id="9ef20-106">如果存在附件，则 Content 类型为  _multipart/mixed;_ 邮件文本和每个附件将成为邮件内容的单独部分，每个附件都有自己的内容类型。</span><span class="sxs-lookup"><span data-stu-id="9ef20-106">If there are attachments, the Content-type is  _multipart/mixed;_ the message text and each attachment become a separate part of the message content, each with its own content-type.</span></span> <span data-ttu-id="9ef20-107">如果没有附件，则邮件的内容类型为  _文本/纯_ 文本，并且只有一部分。</span><span class="sxs-lookup"><span data-stu-id="9ef20-107">If there are no attachments, the content-type of the message is  _text/plain_ and there is only one part.</span></span> 
  
<span data-ttu-id="9ef20-108">邮件文本不换行，除非某些行的长度超过 140 个字符。</span><span class="sxs-lookup"><span data-stu-id="9ef20-108">The message text is not line-wrapped unless some line exceeds 140 characters in length.</span></span> <span data-ttu-id="9ef20-109">如果包含，则整个文本将换行为 76 列，并且  _使用 quoted-printable_ 编码来保留换行符。</span><span class="sxs-lookup"><span data-stu-id="9ef20-109">If one does, the entire text is wrapped to 76 columns and the  _quoted-printable_ encoding is used to preserve line breaks.</span></span> <span data-ttu-id="9ef20-110">内容类型取决于在邮件文本中发现的字符，如下所示：</span><span class="sxs-lookup"><span data-stu-id="9ef20-110">The content-type depends on what characters are found in the message text, as follows:</span></span> 
  
- <span data-ttu-id="9ef20-111">如果只找到 7 位字符且行长度不超过 140 个字符，则消息为 ASCII 文本。</span><span class="sxs-lookup"><span data-stu-id="9ef20-111">If only 7-bit characters are found and no line exceeds 140 characters in length, the message is ASCII text.</span></span> <span data-ttu-id="9ef20-112">_Content-type：text/plain;charset=us-ascii_ (Content-Transfer-Encoding=7bit。) </span><span class="sxs-lookup"><span data-stu-id="9ef20-112">_Content-type: text/plain; charset=us-ascii_ (Content-Transfer-Encoding=7bit is assumed.)</span></span> 
    
- <span data-ttu-id="9ef20-113">如果找到长行或 8 位字符，则消息为文本，字符集由区域设置确定。</span><span class="sxs-lookup"><span data-stu-id="9ef20-113">If long lines or 8-bit characters are found, the message is text and the character set is determined by the locale.</span></span> <span data-ttu-id="9ef20-114">应从 ISO 标准 8859 定义的字符集选择它。</span><span class="sxs-lookup"><span data-stu-id="9ef20-114">It should be chosen from the character sets defined by ISO standard 8859.</span></span> <span data-ttu-id="9ef20-115">_Content-type： text/plain; charset=iso-8859-1_ (or another valid charset) </span><span class="sxs-lookup"><span data-stu-id="9ef20-115">_Content-type: text/plain; charset=iso-8859-1_ (or another valid charset)</span></span> 
    
     <span data-ttu-id="9ef20-116">_Content-Transfer-Encoding: quoted-printable_</span><span class="sxs-lookup"><span data-stu-id="9ef20-116">_Content-Transfer-Encoding: quoted-printable_</span></span>
    
<span data-ttu-id="9ef20-117">对于入站 MIME 邮件，如果第一个邮件内容部分具有 _Content-type： text/ \*_ (，即识别任何文本类型) 且其字符集已被识别，它将映射到 **PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) 。</span><span class="sxs-lookup"><span data-stu-id="9ef20-117">For inbound MIME messages, if the first message content part has  _Content-type: text/\*_ (that is, any text type) and its character set is recognized, it is mapped to **PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)).</span></span> <span data-ttu-id="9ef20-118">第一个不满足此条件的邮件内容部件将成为附件。</span><span class="sxs-lookup"><span data-stu-id="9ef20-118">A first message content part not meeting this criterion becomes an attachment.</span></span> <span data-ttu-id="9ef20-119">任何后续部分也成为附件。</span><span class="sxs-lookup"><span data-stu-id="9ef20-119">Any subsequent parts also become attachments.</span></span>
  
<span data-ttu-id="9ef20-120">在 uuencode 模式下，出站邮件中的邮件文本换行为 78 列，而 MS Mail 3.x 则换行。</span><span class="sxs-lookup"><span data-stu-id="9ef20-120">In uuencode mode, message text in outbound messages is line-wrapped to 78 columns, as for MS Mail 3.x.</span></span> <span data-ttu-id="9ef20-121">content-type 为"text/plain"。</span><span class="sxs-lookup"><span data-stu-id="9ef20-121">The content-type is "text/plain."</span></span> <span data-ttu-id="9ef20-122">若要在这些情况下保留原始邮件的段落换行符，请遵循封装文本中的以下约定。</span><span class="sxs-lookup"><span data-stu-id="9ef20-122">To preserve the original message's paragraph breaks under these circumstances, observe the following conventions in the wrapped text.</span></span> <span data-ttu-id="9ef20-123">结束一行文本有三种可能的原因，每个文本都有其自己的字符序列：</span><span class="sxs-lookup"><span data-stu-id="9ef20-123">There are three possible reasons for ending a line of text, each with its own character sequence:</span></span>
  
- <span data-ttu-id="9ef20-124">换行符。</span><span class="sxs-lookup"><span data-stu-id="9ef20-124">Line-break.</span></span> <span data-ttu-id="9ef20-125">原始文本包含用户在段落标记 (输入的) 。</span><span class="sxs-lookup"><span data-stu-id="9ef20-125">The original text contained a newline entered by the user (paragraph mark).</span></span> <span data-ttu-id="9ef20-126">在传输中，这会映射到没有前面的空值的新行。</span><span class="sxs-lookup"><span data-stu-id="9ef20-126">In the transport, this maps to a newline with no preceding blanks.</span></span> <span data-ttu-id="9ef20-127">如果用户在空行的前面输入了一条新行，应去除空白。</span><span class="sxs-lookup"><span data-stu-id="9ef20-127">If the user enters a newline preceded by blanks, the blanks should be stripped out.</span></span>
    
- <span data-ttu-id="9ef20-128">换行符。</span><span class="sxs-lookup"><span data-stu-id="9ef20-128">Line-nobreak.</span></span> <span data-ttu-id="9ef20-129">原始文本包含的单词太长，无法容纳在邮件的一行上。</span><span class="sxs-lookup"><span data-stu-id="9ef20-129">The original text contained a word too long to fit on a single line of the message.</span></span> <span data-ttu-id="9ef20-130">在传输中，这会映射到前面有两个空白的新行。</span><span class="sxs-lookup"><span data-stu-id="9ef20-130">In the transport, this maps to a newline preceded by two blanks.</span></span>
    
- <span data-ttu-id="9ef20-131">换行。</span><span class="sxs-lookup"><span data-stu-id="9ef20-131">Line-wrap.</span></span> <span data-ttu-id="9ef20-132">原始文本未包含换行符，文本太长，无法容纳在邮件的一行上，但可以在两个单词之间断开。</span><span class="sxs-lookup"><span data-stu-id="9ef20-132">The original text contained no newline, the text is too long to fit on a single line of the message, but it can be broken between two words.</span></span> <span data-ttu-id="9ef20-133">在传输中，这会映射到前面有一个空白的新行。</span><span class="sxs-lookup"><span data-stu-id="9ef20-133">In the transport, this maps to a newline preceded by a single blank.</span></span>
    

