---
title: IndFirst 单元格（“Paragraph”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251254
localization_priority: Normal
ms.assetid: 0f2e362a-3ace-787d-6326-b5bf707f0727
description: 代表形状的文本块中每个段落的首行自该段落的左缩进始缩进的距离。此值与绘图比例无关。即使绘图比例进行调整，首行缩进仍保持不变。
ms.openlocfilehash: 03c34a0ccd1681d3523d743ebfc34af7b9dcfa87
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780438"
---
# <a name="indfirst-cell-paragraph-section"></a>IndFirst 单元格（“Paragraph”部分）

代表形状的文本块中每个段落的首行自该段落的左缩进始缩进的距离。此值与绘图比例无关。即使绘图比例进行调整，首行缩进仍保持不变。
  
## <a name="remarks"></a>注释

要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 IndFirst 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | Para.IndFirst [ *i* ] 其中*i* = < 1 >，2，3...  <br/> |
   
要从某个程序按索引获取对 IndFirst 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionParagraph** <br/> |
| 行索引：  <br/> |**visRowParagraph** +  *i*其中*i* = 0、 1、 2...  <br/> |
| 单元格索引：  <br/> |**visIndentFirst** <br/> |
   

