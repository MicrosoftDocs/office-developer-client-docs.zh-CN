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
ms.openlocfilehash: aa6d9fd14a40f4fe6b269d9750f603d8faf1d550
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33410320"
---
# <a name="indfirst-cell-paragraph-section"></a>IndFirst 单元格（“Paragraph”内容）

代表形状的文本块中每个段落的首行自该段落的左缩进始缩进的距离。此值与绘图比例无关。即使绘图比例进行调整，首行缩进仍保持不变。
  
## <a name="remarks"></a>说明

要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 IndFirst 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | IndFirst [ *i* ] 其中*i* = <1>, 2, 3 .。。  <br/> |
   
要从某个程序按索引获取对 IndFirst 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionParagraph** <br/> |
| 行索引：  <br/> |**visRowParagraph** +  *i* = ** 0、1、2 .。。  <br/> |
| 单元格索引：  <br/> |**visIndentFirst** <br/> |
   

