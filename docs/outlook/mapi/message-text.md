---
title: 邮件文本
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 4d1837f1-494f-481b-9e09-ab8249f1488c
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 9dba148646678f0740c5b2c338ae345ecd76dfac
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776508"
---
# <a name="message-text"></a><span data-ttu-id="7e9f1-103">邮件文本</span><span class="sxs-lookup"><span data-stu-id="7e9f1-103">Message Text</span></span>

  
  
<span data-ttu-id="7e9f1-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="7e9f1-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="7e9f1-105">对于在 MIME 模式下的出站邮件，内容类型取决于是否有附件和消息文本的外观。</span><span class="sxs-lookup"><span data-stu-id="7e9f1-105">For outbound messages in MIME mode, the content-type depends on whether there are attachments and what the message text looks like.</span></span> <span data-ttu-id="7e9f1-106">如果有附件，内容类型是_多部分/混合;_ 消息文本，每个附件成为单独消息内容，每个都有其自己的内容类型的部分。</span><span class="sxs-lookup"><span data-stu-id="7e9f1-106">If there are attachments, the Content-type is  _multipart/mixed;_ the message text and each attachment become a separate part of the message content, each with its own content-type.</span></span> <span data-ttu-id="7e9f1-107">如果不有任何附件，消息的内容类型为_text/plain_并且没有只有一个部件。</span><span class="sxs-lookup"><span data-stu-id="7e9f1-107">If there are no attachments, the content-type of the message is  _text/plain_ and there is only one part.</span></span> 
  
<span data-ttu-id="7e9f1-108">消息文本不会行-包装除非一些行超出 140 个字符的长度。</span><span class="sxs-lookup"><span data-stu-id="7e9f1-108">The message text is not line-wrapped unless some line exceeds 140 characters in length.</span></span> <span data-ttu-id="7e9f1-109">如果包含空格，在整个文本换到 76 列和_用引号括起来打印_编码用于保留换行符。</span><span class="sxs-lookup"><span data-stu-id="7e9f1-109">If one does, the entire text is wrapped to 76 columns and the  _quoted-printable_ encoding is used to preserve line breaks.</span></span> <span data-ttu-id="7e9f1-110">内容类型取决于，如下所示在消息文本中，找到哪些字符：</span><span class="sxs-lookup"><span data-stu-id="7e9f1-110">The content-type depends on what characters are found in the message text, as follows:</span></span> 
  
- <span data-ttu-id="7e9f1-111">如果只找到 7 位字符，并且没有行超过 140 个字符的长度，消息将为 ASCII 文本。</span><span class="sxs-lookup"><span data-stu-id="7e9f1-111">If only 7-bit characters are found and no line exceeds 140 characters in length, the message is ASCII text.</span></span> <span data-ttu-id="7e9f1-112">_Content-type: text/plain; charset = 我们 ascii_(内容传送编码 = 假定 7 位。)</span><span class="sxs-lookup"><span data-stu-id="7e9f1-112">_Content-type: text/plain; charset=us-ascii_ (Content-Transfer-Encoding=7bit is assumed.)</span></span> 
    
- <span data-ttu-id="7e9f1-113">如果找到较长的行或 8 位字符，邮件文本及字符集由区域设置。</span><span class="sxs-lookup"><span data-stu-id="7e9f1-113">If long lines or 8-bit characters are found, the message is text and the character set is determined by the locale.</span></span> <span data-ttu-id="7e9f1-114">从由 ISO 标准 8859 定义的字符集，应选择它。</span><span class="sxs-lookup"><span data-stu-id="7e9f1-114">It should be chosen from the character sets defined by ISO standard 8859.</span></span> <span data-ttu-id="7e9f1-115">_Content-type: text/plain; charset = iso-8859-1_（或其他有效字符集）</span><span class="sxs-lookup"><span data-stu-id="7e9f1-115">_Content-type: text/plain; charset=iso-8859-1_ (or another valid charset)</span></span> 
    
     <span data-ttu-id="7e9f1-116">_Content-Transfer-Encoding: quoted-printable_</span><span class="sxs-lookup"><span data-stu-id="7e9f1-116">_Content-Transfer-Encoding: quoted-printable_</span></span>
    
<span data-ttu-id="7e9f1-117">入站 MIME 邮件，如果第一条消息内容部件具有_内容类型： 文本 /\* _ （即，任何文本类型） 和识别其字符集，它被映射到**PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md))。</span><span class="sxs-lookup"><span data-stu-id="7e9f1-117">For inbound MIME messages, if the first message content part has  _Content-type: text/\*_ (that is, any text type) and its character set is recognized, it is mapped to **PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)).</span></span> <span data-ttu-id="7e9f1-118">不满足此条件的第一个邮件内容部件将成为附件。</span><span class="sxs-lookup"><span data-stu-id="7e9f1-118">A first message content part not meeting this criterion becomes an attachment.</span></span> <span data-ttu-id="7e9f1-119">任何后续部分还将变成附件。</span><span class="sxs-lookup"><span data-stu-id="7e9f1-119">Any subsequent parts also become attachments.</span></span>
  
<span data-ttu-id="7e9f1-120">在 uuencode 模式下，出站邮件中的消息文本是折行 78 列，与 MS Mail 3.x。</span><span class="sxs-lookup"><span data-stu-id="7e9f1-120">In uuencode mode, message text in outbound messages is line-wrapped to 78 columns, as for MS Mail 3.x.</span></span> <span data-ttu-id="7e9f1-121">内容类型为"text/plain。"</span><span class="sxs-lookup"><span data-stu-id="7e9f1-121">The content-type is "text/plain."</span></span> <span data-ttu-id="7e9f1-122">若要保留原始消息的分段符在这些情况下，观察换行文本中的以下约定。</span><span class="sxs-lookup"><span data-stu-id="7e9f1-122">To preserve the original message's paragraph breaks under these circumstances, observe the following conventions in the wrapped text.</span></span> <span data-ttu-id="7e9f1-123">有三个结束一行文本，每个都有其自己的字符序列的可能原因：</span><span class="sxs-lookup"><span data-stu-id="7e9f1-123">There are three possible reasons for ending a line of text, each with its own character sequence:</span></span>
  
- <span data-ttu-id="7e9f1-124">换行符。</span><span class="sxs-lookup"><span data-stu-id="7e9f1-124">Line-break.</span></span> <span data-ttu-id="7e9f1-125">原始文本包含新行输入的用户 （段落标记）。</span><span class="sxs-lookup"><span data-stu-id="7e9f1-125">The original text contained a newline entered by the user (paragraph mark).</span></span> <span data-ttu-id="7e9f1-126">在传输，这将映射到换行符不带上述空格。</span><span class="sxs-lookup"><span data-stu-id="7e9f1-126">In the transport, this maps to a newline with no preceding blanks.</span></span> <span data-ttu-id="7e9f1-127">如果用户输入新行前面由空格，则应去除空值。</span><span class="sxs-lookup"><span data-stu-id="7e9f1-127">If the user enters a newline preceded by blanks, the blanks should be stripped out.</span></span>
    
- <span data-ttu-id="7e9f1-128">行 nobreak。</span><span class="sxs-lookup"><span data-stu-id="7e9f1-128">Line-nobreak.</span></span> <span data-ttu-id="7e9f1-129">原始文本包含太长，以适应单行邮件上的单词。</span><span class="sxs-lookup"><span data-stu-id="7e9f1-129">The original text contained a word too long to fit on a single line of the message.</span></span> <span data-ttu-id="7e9f1-130">在传输，这将映射到新行前面两个空值。</span><span class="sxs-lookup"><span data-stu-id="7e9f1-130">In the transport, this maps to a newline preceded by two blanks.</span></span>
    
- <span data-ttu-id="7e9f1-131">换行。</span><span class="sxs-lookup"><span data-stu-id="7e9f1-131">Line-wrap.</span></span> <span data-ttu-id="7e9f1-132">原始文本包含任何换行符、 文本是太长，可根据单行邮件，但可以是两个字词之间断开。</span><span class="sxs-lookup"><span data-stu-id="7e9f1-132">The original text contained no newline, the text is too long to fit on a single line of the message, but it can be broken between two words.</span></span> <span data-ttu-id="7e9f1-133">在传输，这将映射到新行前面有一个空格。</span><span class="sxs-lookup"><span data-stu-id="7e9f1-133">In the transport, this maps to a newline preceded by a single blank.</span></span>
    

