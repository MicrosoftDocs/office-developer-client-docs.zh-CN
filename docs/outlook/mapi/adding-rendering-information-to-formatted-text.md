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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33420610"
---
# <a name="adding-rendering-information-to-formatted-text"></a>将呈现信息添加到格式化文本

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
若要指示呈现附件的格式化文本中的位置, 必须在邮件的**PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) 属性中插入占位符字符序列。 占位符序列由以下字符组成: `\objattph`。
  
 **将呈现信息添加到格式化的邮件文本中**
  
- 将文本流写入邮件的**PR_RTF_COMPRESSED**属性时, 请在应呈现附件的位置插入占位符序列和空格字符。 
    
- 将每个附件的**PR_RENDERING_POSITION** ([PidTagRenderingPosition](pidtagrenderingposition-canonical-property.md)) 属性设置为一个数字值。 应将最低值分配给首个附件的**PR_RENDERING_POSITION**属性, 以显示在格式化文本中;最后一个附件的最大值。 
    

