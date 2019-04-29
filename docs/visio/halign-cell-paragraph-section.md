---
title: HAlign 单元格（“Paragraph”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm425
localization_priority: Normal
ms.assetid: a8d6b622-60b3-e43f-b6a1-55db561204ed
description: 确定形状的文本块中文本的水平对齐方式。
ms.openlocfilehash: a48619e2531c0a69ad63af3b88ae9f019019b1fe
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33414737"
---
# <a name="halign-cell-paragraph-section"></a>HAlign 单元格（“Paragraph”内容）

确定形状的文本块中文本的水平对齐方式。
  
|**值**|**说明**|**自动常量**|
|:-----|:-----|:-----|
| 0  <br/> | 左对齐  <br/> |**visHorzLeft** <br/> |
| 1  <br/> | 居中  <br/> |**visHorzCenter** <br/> |
| 双面  <br/> | 右对齐  <br/> |**visHorzRight** <br/> |
| 第三章  <br/> | Justify  <br/> |**visHorzJustify** <br/> |
| 4  <br/> | 强制对齐  <br/> |**visHorzForce** <br/> |
   
## <a name="remarks"></a>说明

两端对齐就是在段落中每一行（最后一行除外）的字与字之间添加空格，以便文本的左右两端都与边缘对齐。
  
强制对齐就是将段落中每一行（包括最后一行）的两端对齐。
  
要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 HAlign 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | HorzAlign [ *i* ] 其中*i* = <1>, 2, 3 .。。  <br/> |
   
要从某个程序按索引获取对 HAlign 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionParagraph** <br/> |
| 行索引：  <br/> |**visRowParagraph** +  *i* = ** 0、1、2 .。。  <br/> |
| 单元格索引：  <br/> |**visHorzAlign** <br/> |
   

