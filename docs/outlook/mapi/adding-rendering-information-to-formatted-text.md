---
title: 向格式化文本添加呈现信息
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 790180f9-8864-47d4-97fb-35fe16b957c0
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: a67fc7cbb3be5c7a23cb85e60dc33d853614cda2
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33420610"
---
# <a name="adding-rendering-information-to-formatted-text"></a><span data-ttu-id="13162-103">向格式化文本添加呈现信息</span><span class="sxs-lookup"><span data-stu-id="13162-103">Adding Rendering Information to Formatted Text</span></span>

  
  
<span data-ttu-id="13162-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="13162-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="13162-105">若要指示呈现附件的格式文本中的位置，必须在邮件的 PR_RTF_COMPRESSED ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) 插入一系列占位符字符。</span><span class="sxs-lookup"><span data-stu-id="13162-105">To indicate the location in formatted text where an attachment is rendered, you must insert a sequence of placeholder characters in the message's **PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) property.</span></span> <span data-ttu-id="13162-106">占位符序列由下列字符组成  `\objattph` ：。</span><span class="sxs-lookup"><span data-stu-id="13162-106">The placeholder sequence is made up of the following characters:  `\objattph`.</span></span>
  
 <span data-ttu-id="13162-107">**向格式化邮件文本添加呈现信息**</span><span class="sxs-lookup"><span data-stu-id="13162-107">**To add rendering information to formatted message text**</span></span>
  
- <span data-ttu-id="13162-108">将文本流写入邮件的 PR_RTF_COMPRESSED **属性时** ，在应呈现附件的位置插入占位符序列和空格字符。</span><span class="sxs-lookup"><span data-stu-id="13162-108">When writing the stream of text to the message's **PR_RTF_COMPRESSED** property, insert the placeholder sequence and a space character at the position where the attachment should be rendered.</span></span> 
    
- <span data-ttu-id="13162-109">将 **PR_RENDERING_POSITION (** [PidTagRenderingPosition](pidtagrenderingposition-canonical-property.md)) 属性设置为数值。</span><span class="sxs-lookup"><span data-stu-id="13162-109">Set the **PR_RENDERING_POSITION** ([PidTagRenderingPosition](pidtagrenderingposition-canonical-property.md)) property of each attachment to a numeric value.</span></span> <span data-ttu-id="13162-110">应为要显示在格式化文本的第一个附件的 **PR_RENDERING_POSITION** 属性分配最低值;最后一个附件的最高级别。</span><span class="sxs-lookup"><span data-stu-id="13162-110">The lowest value should be assigned to the **PR_RENDERING_POSITION** property of the first attachment to appear in the formatted text; the highest value to the last attachment.</span></span> 
    

