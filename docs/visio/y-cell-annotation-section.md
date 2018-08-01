---
title: Y 单元格（“Annotation”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm60095
localization_priority: Normal
ms.assetid: 527a4615-2013-a4b4-81cd-7f5d71c1803c
description: Y-坐标的页坐标中注释标记。
ms.openlocfilehash: cc2399de7919512796a39ca39c705c214f4c51a2
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781694"
---
# <a name="y-cell-annotation-section"></a>Y 单元格（“Annotation”部分）

*Y* -坐标的页坐标中注释标记。 
  
> [!NOTE]
> 此单元格用于跟踪注释，仅当打开 Microsoft Visio 2013 中的.vsd 文件或.vsd 文件格式保存.vsdx 文件时。 它不用于跟踪.vsdx Visio 2013 中的文档中的注释。 
  
## <a name="remarks"></a>说明

要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 Y 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | Annotation.Y [ *i* ] 其中*i* = < 1 >，2，3...  <br/> |
   
要从某个程序按索引获取对 Y 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionAnnotation** <br/> |
| 行索引：  <br/> |**visRowAnnotation** +  *i*其中*i* = 0、 1、 2...  <br/> |
| 单元格索引：  <br/> |**visAnnotationY** <br/> |
   

