---
title: ConLineJumpDirY 单元格（“Shape Layout”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251654
localization_priority: Normal
ms.assetid: 93f82ae0-3442-fac1-9906-b84afef85f5c
description: 确定出现在形状的垂直动态连接线上的跨线的跨线方向。
ms.openlocfilehash: 2d0c0964b52c9afbccc9cb507024825434702b6d
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779938"
---
# <a name="conlinejumpdiry-cell-shape-layout-section"></a>ConLineJumpDirY 单元格（“Shape Layout”内容）

确定出现在形状的垂直动态连接线上的跨线的跨线方向。
  
|**值**|**跨线方向**|**自动化常量**|
|:-----|:-----|:-----|
| 0  <br/> | 页面默认值  <br/> |**visLOJumpDirYDefault** <br/> |
| 1  <br/> | 左侧  <br/> |**visLOJumpDirYLeft** <br/> |
| 2  <br/> | 右侧  <br/> |**visLOJumpDirYRight** <br/> |
   
## <a name="remarks"></a>备注

设置默认垂直方向*所有*连接器的跨线的页上，使用 Page Layout 内容中的 PageLineJumpDirY 单元格。 
  
要从另一个公式或使用**CellsU**属性从某个程序按名称获取对 ConLineJumpDirY 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | ConLineJumpDirY  <br/> |
   
若要从某个程序按索引获取对 ConLineJumpDirY 单元格的引用，请使用带下列参数的**CellsSRC**属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowShapeLayout** <br/> |
| 单元格索引：  <br/> |**visSLOJumpDirY** <br/> |
   

