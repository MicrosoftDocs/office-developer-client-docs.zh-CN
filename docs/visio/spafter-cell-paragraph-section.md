---
title: SpAfter 单元格（“Paragraph”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm960
localization_priority: Normal
ms.assetid: 2dd56ae5-300e-ba09-a73a-83c2b6c2a0ef
description: 确定除了在 SpLine 单元格（如果段落为文本块的最后一段，则由 BottomMargin 单元格指定）中指定的任何空间量外还需要在形状的文本块中每个段落后插入的空间量。
ms.openlocfilehash: 2b8fe7e2b0df09561d0db4367f917c8f4b71335d
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33439833"
---
# <a name="spafter-cell-paragraph-section"></a>SpAfter 单元格（“Paragraph”内容）

确定除了在 SpLine 单元格（如果段落为文本块的最后一段，则由 BottomMargin 单元格指定）中指定的任何空间量外还需要在形状的文本块中每个段落后插入的空间量。
  
## <a name="remarks"></a>说明

此值与绘图比例无关。即使绘图比例进行调整，“段后空间”设置仍保持不变。
  
要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 SpAfter 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | SpAfter [ *i* ] 其中*i* = <1>, 2, 3 .。。  <br/> |
   
要从某个程序按索引获取对 SpAfter 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionParagraph** <br/> |
| 行索引：  <br/> |**visRowParagraph** +  *i* = ** 0、1、2 .。。  <br/> |
| 单元格索引：  <br/> |**visSpaceAfter** <br/> |
   

