---
title: 将呈现信息添加到格式化文本
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 790180f9-8864-47d4-97fb-35fe16b957c0
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: a67fc7cbb3be5c7a23cb85e60dc33d853614cda2
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32331120"
---
# <a name="adding-rendering-information-to-formatted-text"></a><span data-ttu-id="ac9f5-103">将呈现信息添加到格式化文本</span><span class="sxs-lookup"><span data-stu-id="ac9f5-103">Adding Rendering Information to Formatted Text</span></span>

  
  
<span data-ttu-id="ac9f5-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="ac9f5-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="ac9f5-105">若要指示呈现附件的格式化文本中的位置, 必须在邮件的**PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) 属性中插入占位符字符序列。</span><span class="sxs-lookup"><span data-stu-id="ac9f5-105">To indicate the location in formatted text where an attachment is rendered, you must insert a sequence of placeholder characters in the message's **PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) property.</span></span> <span data-ttu-id="ac9f5-106">占位符序列由以下字符组成: `\objattph`。</span><span class="sxs-lookup"><span data-stu-id="ac9f5-106">The placeholder sequence is made up of the following characters:  `\objattph`.</span></span>
  
 <span data-ttu-id="ac9f5-107">**将呈现信息添加到格式化的邮件文本中**</span><span class="sxs-lookup"><span data-stu-id="ac9f5-107">**To add rendering information to formatted message text**</span></span>
  
- <span data-ttu-id="ac9f5-108">将文本流写入邮件的**PR_RTF_COMPRESSED**属性时, 请在应呈现附件的位置插入占位符序列和空格字符。</span><span class="sxs-lookup"><span data-stu-id="ac9f5-108">When writing the stream of text to the message's **PR_RTF_COMPRESSED** property, insert the placeholder sequence and a space character at the position where the attachment should be rendered.</span></span> 
    
- <span data-ttu-id="ac9f5-109">将每个附件的**PR_RENDERING_POSITION** ([PidTagRenderingPosition](pidtagrenderingposition-canonical-property.md)) 属性设置为一个数字值。</span><span class="sxs-lookup"><span data-stu-id="ac9f5-109">Set the **PR_RENDERING_POSITION** ([PidTagRenderingPosition](pidtagrenderingposition-canonical-property.md)) property of each attachment to a numeric value.</span></span> <span data-ttu-id="ac9f5-110">应将最低值分配给首个附件的**PR_RENDERING_POSITION**属性, 以显示在格式化文本中;最后一个附件的最大值。</span><span class="sxs-lookup"><span data-stu-id="ac9f5-110">The lowest value should be assigned to the **PR_RENDERING_POSITION** property of the first attachment to appear in the formatted text; the highest value to the last attachment.</span></span> 
    

