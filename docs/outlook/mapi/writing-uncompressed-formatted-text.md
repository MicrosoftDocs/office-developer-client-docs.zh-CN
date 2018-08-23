---
title: 编写未压缩的格式化文本
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: c78d4d00-bc31-4d0b-8af0-dd0b8f3febfe
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: d34168743926681ee7169a593e302755b193aae7
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22577042"
---
# <a name="writing-uncompressed-formatted-text"></a><span data-ttu-id="1de84-103">编写未压缩的格式化文本</span><span class="sxs-lookup"><span data-stu-id="1de84-103">Writing Uncompressed Formatted Text</span></span>

  
  
<span data-ttu-id="1de84-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="1de84-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="1de84-105">在准备要发送带格式的文本消息时，以下任意会设置为压缩或未压缩文本的消息的**PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="1de84-105">When preparing to send a message with formatted text, either set the message's **PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) property to compressed or uncompressed text.</span></span> <span data-ttu-id="1de84-106">**PR_RTF_COMPRESSED**属性中写入压缩的文本频繁的 CPU 密集型操作，可以显著影响性能。</span><span class="sxs-lookup"><span data-stu-id="1de84-106">Writing compressed text in the **PR_RTF_COMPRESSED** property is a very CPU intensive operation and can dramatically affect performance.</span></span> 
  
<span data-ttu-id="1de84-107">以提高性能的发送格式的邮件，或者：</span><span class="sxs-lookup"><span data-stu-id="1de84-107">To improve the performance of sending formatted messages, either:</span></span>
  
- <span data-ttu-id="1de84-108">升级 CPU，并不总是貌似合理的解决方案。</span><span class="sxs-lookup"><span data-stu-id="1de84-108">Upgrade the CPU, a solution that is not always plausible.</span></span>
    
    - <span data-ttu-id="1de84-109">或者-</span><span class="sxs-lookup"><span data-stu-id="1de84-109">Or -</span></span>
    
- <span data-ttu-id="1de84-110">写入**PR_RTF_COMPRESSED**属性中的未压缩的文本。</span><span class="sxs-lookup"><span data-stu-id="1de84-110">Write uncompressed text in the **PR_RTF_COMPRESSED** property.</span></span> 
    
<span data-ttu-id="1de84-111">设置**PR_RTF_COMPRESSED**未压缩文本的过程是相同设置压缩文本，有一个例外。</span><span class="sxs-lookup"><span data-stu-id="1de84-111">The procedure for setting **PR_RTF_COMPRESSED** with uncompressed text is the same as for setting it with compressed text, with one exception.</span></span> <span data-ttu-id="1de84-112">调用[WrapCompressedRTFStream](wrapcompressedrtfstream.md)时, _ulFlags_参数中设置 STORE_UNCOMPRESSED_RTF 标志。</span><span class="sxs-lookup"><span data-stu-id="1de84-112">When calling [WrapCompressedRTFStream](wrapcompressedrtfstream.md), set the STORE_UNCOMPRESSED_RTF flag in the  _ulFlags_ parameter.</span></span> <span data-ttu-id="1de84-113">设置未压缩的文本有缺点，它会增加邮件的大小。</span><span class="sxs-lookup"><span data-stu-id="1de84-113">Setting uncompressed text has the disadvantage in that it increases the size of messages.</span></span> 
  

