---
title: 写入未压缩的格式化文本
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: c78d4d00-bc31-4d0b-8af0-dd0b8f3febfe
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 7ad12fbc9671d0a21c6c6e6d4615b45a17a72fce
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32325751"
---
# <a name="writing-uncompressed-formatted-text"></a><span data-ttu-id="ae6f5-103">写入未压缩的格式化文本</span><span class="sxs-lookup"><span data-stu-id="ae6f5-103">Writing Uncompressed Formatted Text</span></span>

  
  
<span data-ttu-id="ae6f5-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="ae6f5-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="ae6f5-105">准备发送带格式文本的邮件时, 请将邮件的**PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) 属性设置为 "已压缩" 或 "未压缩文本"。</span><span class="sxs-lookup"><span data-stu-id="ae6f5-105">When preparing to send a message with formatted text, either set the message's **PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) property to compressed or uncompressed text.</span></span> <span data-ttu-id="ae6f5-106">在**PR_RTF_COMPRESSED**属性中写入压缩的文本是一项非常耗费 CPU 的操作, 可能会严重影响性能。</span><span class="sxs-lookup"><span data-stu-id="ae6f5-106">Writing compressed text in the **PR_RTF_COMPRESSED** property is a very CPU intensive operation and can dramatically affect performance.</span></span> 
  
<span data-ttu-id="ae6f5-107">若要提高发送格式化邮件的性能, 请执行以下操作之一:</span><span class="sxs-lookup"><span data-stu-id="ae6f5-107">To improve the performance of sending formatted messages, either:</span></span>
  
- <span data-ttu-id="ae6f5-108">升级 CPU, 这是一种并非始终 plausible 的解决方案。</span><span class="sxs-lookup"><span data-stu-id="ae6f5-108">Upgrade the CPU, a solution that is not always plausible.</span></span>
    
    - <span data-ttu-id="ae6f5-109">和</span><span class="sxs-lookup"><span data-stu-id="ae6f5-109">Or -</span></span>
    
- <span data-ttu-id="ae6f5-110">在**PR_RTF_COMPRESSED**属性中写入未压缩的文本。</span><span class="sxs-lookup"><span data-stu-id="ae6f5-110">Write uncompressed text in the **PR_RTF_COMPRESSED** property.</span></span> 
    
<span data-ttu-id="ae6f5-111">使用未压缩的文本设置**PR_RTF_COMPRESSED**的过程与使用压缩的文本设置它的过程相同, 但有一个例外。</span><span class="sxs-lookup"><span data-stu-id="ae6f5-111">The procedure for setting **PR_RTF_COMPRESSED** with uncompressed text is the same as for setting it with compressed text, with one exception.</span></span> <span data-ttu-id="ae6f5-112">调用[WrapCompressedRTFStream](wrapcompressedrtfstream.md)时, 请在_ulFlags_参数中设置 STORE_UNCOMPRESSED_RTF 标志。</span><span class="sxs-lookup"><span data-stu-id="ae6f5-112">When calling [WrapCompressedRTFStream](wrapcompressedrtfstream.md), set the STORE_UNCOMPRESSED_RTF flag in the  _ulFlags_ parameter.</span></span> <span data-ttu-id="ae6f5-113">设置未压缩的文本的缺点在于它会增加邮件大小。</span><span class="sxs-lookup"><span data-stu-id="ae6f5-113">Setting uncompressed text has the disadvantage in that it increases the size of messages.</span></span> 
  

