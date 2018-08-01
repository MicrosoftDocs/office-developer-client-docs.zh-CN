---
title: SpLine 单元格（“Paragraph”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm970
localization_priority: Normal
ms.assetid: 84f4e5f1-7c28-9e83-8644-28d117bb10a5
description: 确定一行文本和下一行文本之间的距离，用百分比表示，其中 100% 是文本行的高度。
ms.openlocfilehash: f2f290564d49a056bc3366707b25a7991f8c4401
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781418"
---
# <a name="spline-cell-paragraph-section"></a>SpLine 单元格（“Paragraph”部分）

确定一行文本和下一行文本之间的距离，用百分比表示，其中 100% 是文本行的高度。
  
|**值**|**说明**|
|:-----|:-----|
| \>0  <br/> | 绝对间距，与字体大小无关  <br/> |
| =0  <br/> | 设置纯色（间距 = 100% 的字体大小）  <br/> |
| \<0  <br/> | 字体大小的百分比（例如，-120% 生成 120% 间距）  <br/> |
   
## <a name="remarks"></a>注释

要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 SpLine 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | 段落。 样条 [ *i* ] 其中*i* = < 1 >，2，3...  <br/> |
   
要从某个程序按索引获取对 SpLine 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionParagraph** <br/> |
| 行索引：  <br/> |**visRowParagraph** +  *i*其中*i* = 0、 1、 2...  <br/> |
| 单元格索引：  <br/> |**visSpaceLine** <br/> |
   

