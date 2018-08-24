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
ms.openlocfilehash: a6018c05d1191211242066425e4ae546c1618094
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22594556"
---
# <a name="adding-rendering-information-to-formatted-text"></a>将生成的信息添加到格式化文本

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
指示附件呈现的位置中带格式的文本的位置，则必须将占位符字符序列的插入消息的**PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) 属性中。 占位符序列构成下列字符： `\objattph`。
  
 **将呈现信息添加到带格式的消息文本**
  
- 时的文本流写入消息的**PR_RTF_COMPRESSED**属性，来呈现附件的位置的位置插入占位符序列和空格字符。 
    
- 设置为数值的每个附件的**PR_RENDERING_POSITION** ([PidTagRenderingPosition](pidtagrenderingposition-canonical-property.md)) 属性。 最小值应分配给第一个附件的**PR_RENDERING_POSITION**属性，显示中的格式化文本;最高的值，到最后一个附件。 
    

