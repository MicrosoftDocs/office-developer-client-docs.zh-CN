---
title: E 单元格（“Geometry”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251761
localization_priority: Normal
ms.assetid: bc0154b1-6930-1fe0-655c-05eab2d60230
description: 包含非均匀有理 B 样条 (NURBS) 公式。
ms.openlocfilehash: 5c9b3cbf96e2a218a8ed790d3a5615843360c95e
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33423564"
---
# <a name="e-cell-geometry-section"></a>E 单元格（“Geometry”内容）

包含非均匀有理 B 样条 (NURBS) 公式。
  
## <a name="remarks"></a>备注

要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 E 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | Geometry  *i*  .E  *j*            其中  *i*  和  *j*  = <1>、2、3...  <br/> |
   
要从某个程序按索引获取对 E 单元格，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionFirstComponent**  +  *i* 其中 *i* = 0、1、2...  <br/> |
| 行索引：  <br/> |**visRowVertex**  +  *j* 其中 *j* = 0、1、2...  <br/> |
| 单元格索引：  <br/> |**visNURBSData** <br/> |
   

