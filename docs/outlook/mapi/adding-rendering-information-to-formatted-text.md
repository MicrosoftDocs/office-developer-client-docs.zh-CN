---
title: 将生成的信息添加到格式化文本
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 790180f9-8864-47d4-97fb-35fe16b957c0
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: b912d81c1413fb40b6ddccc2f54bc393a6b67857
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774511"
---
# <a name="adding-rendering-information-to-formatted-text"></a><span data-ttu-id="8c1ce-103">将生成的信息添加到格式化文本</span><span class="sxs-lookup"><span data-stu-id="8c1ce-103">Adding Rendering Information to Formatted Text</span></span>

  
  
<span data-ttu-id="8c1ce-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="8c1ce-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="8c1ce-105">指示附件呈现的位置中带格式的文本的位置，则必须将占位符字符序列的插入消息的**PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) 属性中。</span><span class="sxs-lookup"><span data-stu-id="8c1ce-105">To indicate the location in formatted text where an attachment is rendered, you must insert a sequence of placeholder characters in the message's **PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) property.</span></span> <span data-ttu-id="8c1ce-106">占位符序列构成下列字符： `\objattph`。</span><span class="sxs-lookup"><span data-stu-id="8c1ce-106">The placeholder sequence is made up of the following characters:  `\objattph`.</span></span>
  
 <span data-ttu-id="8c1ce-107">**将呈现信息添加到带格式的消息文本**</span><span class="sxs-lookup"><span data-stu-id="8c1ce-107">**To add rendering information to formatted message text**</span></span>
  
- <span data-ttu-id="8c1ce-108">时的文本流写入消息的**PR_RTF_COMPRESSED**属性，来呈现附件的位置的位置插入占位符序列和空格字符。</span><span class="sxs-lookup"><span data-stu-id="8c1ce-108">When writing the stream of text to the message's **PR_RTF_COMPRESSED** property, insert the placeholder sequence and a space character at the position where the attachment should be rendered.</span></span> 
    
- <span data-ttu-id="8c1ce-109">设置为数值的每个附件的**PR_RENDERING_POSITION** ([PidTagRenderingPosition](pidtagrenderingposition-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="8c1ce-109">Set the **PR_RENDERING_POSITION** ([PidTagRenderingPosition](pidtagrenderingposition-canonical-property.md)) property of each attachment to a numeric value.</span></span> <span data-ttu-id="8c1ce-110">最小值应分配给第一个附件的**PR_RENDERING_POSITION**属性，显示中的格式化文本;最高的值，到最后一个附件。</span><span class="sxs-lookup"><span data-stu-id="8c1ce-110">The lowest value should be assigned to the **PR_RENDERING_POSITION** property of the first attachment to appear in the formatted text; the highest value to the last attachment.</span></span> 
    

