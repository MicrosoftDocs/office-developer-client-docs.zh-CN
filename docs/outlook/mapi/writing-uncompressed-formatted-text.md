---
title: 写入未压缩的格式文本
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: c78d4d00-bc31-4d0b-8af0-dd0b8f3febfe
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 7ad12fbc9671d0a21c6c6e6d4615b45a17a72fce
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33426322"
---
# <a name="writing-uncompressed-formatted-text"></a><span data-ttu-id="72000-103">写入未压缩的格式文本</span><span class="sxs-lookup"><span data-stu-id="72000-103">Writing Uncompressed Formatted Text</span></span>

  
  
<span data-ttu-id="72000-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="72000-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="72000-105">准备发送带格式文本的邮件时，请将邮件的 **PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) 属性设置为压缩文本或未压缩文本。</span><span class="sxs-lookup"><span data-stu-id="72000-105">When preparing to send a message with formatted text, either set the message's **PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) property to compressed or uncompressed text.</span></span> <span data-ttu-id="72000-106">在 PR_RTF_COMPRESSED **属性中** 写入压缩文本是一项占用大量 CPU 的操作，并且会显著影响性能。</span><span class="sxs-lookup"><span data-stu-id="72000-106">Writing compressed text in the **PR_RTF_COMPRESSED** property is a very CPU intensive operation and can dramatically affect performance.</span></span> 
  
<span data-ttu-id="72000-107">若要提高发送格式化邮件的性能，请执行以下任一操作：</span><span class="sxs-lookup"><span data-stu-id="72000-107">To improve the performance of sending formatted messages, either:</span></span>
  
- <span data-ttu-id="72000-108">升级 CPU，这是一种并不总是能实现的解决方案。</span><span class="sxs-lookup"><span data-stu-id="72000-108">Upgrade the CPU, a solution that is not always plausible.</span></span>
    
    - <span data-ttu-id="72000-109">或 -</span><span class="sxs-lookup"><span data-stu-id="72000-109">Or -</span></span>
    
- <span data-ttu-id="72000-110">在属性中写入 **未压缩PR_RTF_COMPRESSED** 文本。</span><span class="sxs-lookup"><span data-stu-id="72000-110">Write uncompressed text in the **PR_RTF_COMPRESSED** property.</span></span> 
    
<span data-ttu-id="72000-111">使用 **未压缩PR_RTF_COMPRESSED** 设置压缩文本的过程与使用压缩文本设置过程相同，只有一个例外。</span><span class="sxs-lookup"><span data-stu-id="72000-111">The procedure for setting **PR_RTF_COMPRESSED** with uncompressed text is the same as for setting it with compressed text, with one exception.</span></span> <span data-ttu-id="72000-112">调用 [WrapCompressedRTFStream](wrapcompressedrtfstream.md)时，在  _ulFlags_ STORE_UNCOMPRESSED_RTF设置值标记。</span><span class="sxs-lookup"><span data-stu-id="72000-112">When calling [WrapCompressedRTFStream](wrapcompressedrtfstream.md), set the STORE_UNCOMPRESSED_RTF flag in the  _ulFlags_ parameter.</span></span> <span data-ttu-id="72000-113">设置未压缩文本的缺点是增加邮件的大小。</span><span class="sxs-lookup"><span data-stu-id="72000-113">Setting uncompressed text has the disadvantage in that it increases the size of messages.</span></span> 
  

