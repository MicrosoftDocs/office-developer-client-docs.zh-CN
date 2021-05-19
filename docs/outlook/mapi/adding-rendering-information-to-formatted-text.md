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
# <a name="adding-rendering-information-to-formatted-text"></a>向格式化文本添加呈现信息

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
若要指示呈现附件的格式文本中的位置，必须在邮件的 PR_RTF_COMPRESSED ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) 插入一系列占位符字符。 占位符序列由下列字符组成  `\objattph` ：。
  
 **向格式化邮件文本添加呈现信息**
  
- 将文本流写入邮件的 PR_RTF_COMPRESSED **属性时** ，在应呈现附件的位置插入占位符序列和空格字符。 
    
- 将 **PR_RENDERING_POSITION (** [PidTagRenderingPosition](pidtagrenderingposition-canonical-property.md)) 属性设置为数值。 应为要显示在格式化文本的第一个附件的 **PR_RENDERING_POSITION** 属性分配最低值;最后一个附件的最高级别。 
    

