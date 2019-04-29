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
# <a name="message-text"></a><span data-ttu-id="69171-103">消息文本</span><span class="sxs-lookup"><span data-stu-id="69171-103">Message Text</span></span>

  
  
<span data-ttu-id="69171-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="69171-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="69171-105">对于 MIME 模式下的出站邮件, 内容类型取决于是否存在附件以及邮件文本的外观。</span><span class="sxs-lookup"><span data-stu-id="69171-105">For outbound messages in MIME mode, the content-type depends on whether there are attachments and what the message text looks like.</span></span> <span data-ttu-id="69171-106">如果存在附件, 则内容类型为_多部分/混合的;_ 邮件文本和每个附件将成为邮件内容的一个单独部分, 每个附件都有其自己的内容类型。</span><span class="sxs-lookup"><span data-stu-id="69171-106">If there are attachments, the Content-type is  _multipart/mixed;_ the message text and each attachment become a separate part of the message content, each with its own content-type.</span></span> <span data-ttu-id="69171-107">如果没有附件, 则邮件的内容类型为_text/纯文本_, 并且只有一个部件。</span><span class="sxs-lookup"><span data-stu-id="69171-107">If there are no attachments, the content-type of the message is  _text/plain_ and there is only one part.</span></span> 
  
<span data-ttu-id="69171-108">除非某个行的长度超过140个字符, 否则邮件文本不会换行。</span><span class="sxs-lookup"><span data-stu-id="69171-108">The message text is not line-wrapped unless some line exceeds 140 characters in length.</span></span> <span data-ttu-id="69171-109">如果有, 则整个文本将被包装为76列, 可使用_带引号的可打印_编码来保留换行符。</span><span class="sxs-lookup"><span data-stu-id="69171-109">If one does, the entire text is wrapped to 76 columns and the  _quoted-printable_ encoding is used to preserve line breaks.</span></span> <span data-ttu-id="69171-110">内容类型取决于在邮件文本中找到的字符, 如下所示:</span><span class="sxs-lookup"><span data-stu-id="69171-110">The content-type depends on what characters are found in the message text, as follows:</span></span> 
  
- <span data-ttu-id="69171-111">如果仅找到7位字符, 并且没有任何行的长度超过140个字符, 则该邮件为 ASCII 文本。</span><span class="sxs-lookup"><span data-stu-id="69171-111">If only 7-bit characters are found and no line exceeds 140 characters in length, the message is ASCII text.</span></span> <span data-ttu-id="69171-112">_Content-type: text/普通; 字符集 = us-ascii_(假定为 "内容传输-编码 = 7bit"。)</span><span class="sxs-lookup"><span data-stu-id="69171-112">_Content-type: text/plain; charset=us-ascii_ (Content-Transfer-Encoding=7bit is assumed.)</span></span> 
    
- <span data-ttu-id="69171-113">如果找到长行或8位字符, 则邮件为文本, 字符集由区域设置决定。</span><span class="sxs-lookup"><span data-stu-id="69171-113">If long lines or 8-bit characters are found, the message is text and the character set is determined by the locale.</span></span> <span data-ttu-id="69171-114">应从 ISO standard 8859 定义的字符集中选择此设置。</span><span class="sxs-lookup"><span data-stu-id="69171-114">It should be chosen from the character sets defined by ISO standard 8859.</span></span> <span data-ttu-id="69171-115">_Content-type: text/普通; 字符集 = iso-8859-1_(或其他有效的字符集)</span><span class="sxs-lookup"><span data-stu-id="69171-115">_Content-type: text/plain; charset=iso-8859-1_ (or another valid charset)</span></span> 
    
     <span data-ttu-id="69171-116">_Content-Transfer-Encoding: quoted-printable_</span><span class="sxs-lookup"><span data-stu-id="69171-116">_Content-Transfer-Encoding: quoted-printable_</span></span>
    
<span data-ttu-id="69171-117">对于入站 MIME 邮件, 如果第一个邮件内容部件包含_content type: text/\* _ (即任何文本类型), 并识别其字符集, 则将其映射到**PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md))。</span><span class="sxs-lookup"><span data-stu-id="69171-117">For inbound MIME messages, if the first message content part has  _Content-type: text/\*_ (that is, any text type) and its character set is recognized, it is mapped to **PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)).</span></span> <span data-ttu-id="69171-118">未满足此条件的第一个邮件内容部件将成为附件。</span><span class="sxs-lookup"><span data-stu-id="69171-118">A first message content part not meeting this criterion becomes an attachment.</span></span> <span data-ttu-id="69171-119">任何后续部件也会变成附件。</span><span class="sxs-lookup"><span data-stu-id="69171-119">Any subsequent parts also become attachments.</span></span>
  
<span data-ttu-id="69171-120">在 uuencode 模式下, 出站邮件中的邮件文本被自动换行为78列, 如 MS Mail 3。</span><span class="sxs-lookup"><span data-stu-id="69171-120">In uuencode mode, message text in outbound messages is line-wrapped to 78 columns, as for MS Mail 3.x.</span></span> <span data-ttu-id="69171-121">内容类型为 "text/普通"。</span><span class="sxs-lookup"><span data-stu-id="69171-121">The content-type is "text/plain."</span></span> <span data-ttu-id="69171-122">若要在这些情况下保留原始邮件的段落换行, 请在换行文本中遵循以下约定。</span><span class="sxs-lookup"><span data-stu-id="69171-122">To preserve the original message's paragraph breaks under these circumstances, observe the following conventions in the wrapped text.</span></span> <span data-ttu-id="69171-123">有三个可能的原因: 结束一行文本, 每个原因都有其自己的字符序列:</span><span class="sxs-lookup"><span data-stu-id="69171-123">There are three possible reasons for ending a line of text, each with its own character sequence:</span></span>
  
- <span data-ttu-id="69171-124">换行符。</span><span class="sxs-lookup"><span data-stu-id="69171-124">Line-break.</span></span> <span data-ttu-id="69171-125">原始文本包含用户输入的换行符 (段落标记)。</span><span class="sxs-lookup"><span data-stu-id="69171-125">The original text contained a newline entered by the user (paragraph mark).</span></span> <span data-ttu-id="69171-126">在传输中, 这会映射到不带前空白的换行符。</span><span class="sxs-lookup"><span data-stu-id="69171-126">In the transport, this maps to a newline with no preceding blanks.</span></span> <span data-ttu-id="69171-127">如果用户输入的前带空格的换行符, 则应去除空白。</span><span class="sxs-lookup"><span data-stu-id="69171-127">If the user enters a newline preceded by blanks, the blanks should be stripped out.</span></span>
    
- <span data-ttu-id="69171-128">行-nobreak。</span><span class="sxs-lookup"><span data-stu-id="69171-128">Line-nobreak.</span></span> <span data-ttu-id="69171-129">原始文本包含的词太长, 不能在邮件的一行中显示。</span><span class="sxs-lookup"><span data-stu-id="69171-129">The original text contained a word too long to fit on a single line of the message.</span></span> <span data-ttu-id="69171-130">在传输中, 此方法映射到前有两个空格的换行符。</span><span class="sxs-lookup"><span data-stu-id="69171-130">In the transport, this maps to a newline preceded by two blanks.</span></span>
    
- <span data-ttu-id="69171-131">换行。</span><span class="sxs-lookup"><span data-stu-id="69171-131">Line-wrap.</span></span> <span data-ttu-id="69171-132">原始文本不包含任何行, 文本太长, 不能在邮件的一行中显示, 但可以在两个单词之间断线。</span><span class="sxs-lookup"><span data-stu-id="69171-132">The original text contained no newline, the text is too long to fit on a single line of the message, but it can be broken between two words.</span></span> <span data-ttu-id="69171-133">在传输中, 这会映射到前跟一个空白的换行符。</span><span class="sxs-lookup"><span data-stu-id="69171-133">In the transport, this maps to a newline preceded by a single blank.</span></span>
    

