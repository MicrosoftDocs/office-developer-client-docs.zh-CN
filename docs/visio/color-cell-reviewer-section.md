---
title: Color 单元格（“Reviewer”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm60032
localization_priority: Normal
ms.assetid: c1e3d7bf-e6b6-65f1-ae40-80c8ba4821cd
description: 一个代表分配给文档审阅者的标记的颜色的 RGB 值。
ms.openlocfilehash: a8771bb35cfc1b57990f24e1a0a3d677f9cffc0b
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779899"
---
# <a name="color-cell-reviewer-section"></a>Color 单元格（“Reviewer”内容）

一个代表分配给文档审阅者的标记的颜色的 RGB 值。 
  
## <a name="remarks"></a>注解

分配给审阅者的颜色顺序如下：红色、蓝色、绿色、紫色、橙色、青绿色、灰色。这些颜色循环分配给其余审阅者。 
  
无论在 Color 单元格中为审阅者分配的是何种颜色，在原始绘图页上输入的注释始终为黄色。 
  
要从另一个公式或使用**CellsU**属性从某个程序按名称获取对 Color 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | Reviewer.Color [ *i* ] 其中*i* = < 1 >，2，3...  <br/> |
   
若要从某个程序按索引获取对 Color 单元格的引用，请使用带下列参数的**CellsSRC**属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionReviewer** <br/> |
| 行索引：  <br/> |**visRowReviewer** +  *i*其中*i* = 0、 1、 2...  <br/> |
| 单元格索引：  <br/> |**visReviewerColor** <br/> |
   

