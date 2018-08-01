---
title: ConLineJumpDirX 单元格（“Shape Layout”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm185
localization_priority: Normal
ms.assetid: f0671835-8d48-907a-eca6-43953658f800
description: 确定出现在形状的水平动态连接线上的跨线的方向。
ms.openlocfilehash: 396830d0da22c15f036f95808b3a94c33e9dc5bb
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779950"
---
# <a name="conlinejumpdirx-cell-shape-layout-section"></a>ConLineJumpDirX 单元格（“Shape Layout”部分）

确定出现在形状的水平动态连接线上的跨线的方向。
  
|**值**|**跨线方向**|**自动常量**|
|:-----|:-----|:-----|
| 0  <br/> | 页面默认值  <br/> |**visLOJumpDirXDefault** <br/> |
| 1  <br/> | 向上  <br/> |**visLOJumpDirXUp** <br/> |
| 2  <br/> | 向下  <br/> |**visLOJumpDirXDown** <br/> |
   
## <a name="remarks"></a>说明

设置默认水平方向*所有*连接器的跨线的页上，使用 Page Layout 内容中的 PageLineJumpDirX 单元格。 
  
要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 ConLineJumpDirX 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | ConLineJumpDirX  <br/> |
   
要从某个程序按索引获取对 ConLineJumpDirX 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowShapeLayout** <br/> |
| 单元格索引：  <br/> |**visSLOJumpDirX** <br/> |
   

