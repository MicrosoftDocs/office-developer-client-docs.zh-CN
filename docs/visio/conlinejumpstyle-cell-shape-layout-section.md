---
title: ConLineJumpStyle 单元格（“Shape Layout”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251655
localization_priority: Normal
ms.assetid: baa05a50-97d0-3769-635e-0ea20317d59a
description: 确定动态连接线上的跨线的跨线样式。
ms.openlocfilehash: ae8af4e326a6c895b3617a4869f98eaf0db68db1
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33415990"
---
# <a name="conlinejumpstyle-cell-shape-layout-section"></a>ConLineJumpStyle 单元格（“Shape Layout”内容）

确定动态连接线上的跨线的跨线样式。
  
|**值**|**跨线样式**|**自动常量**|
|:-----|:-----|:-----|
|0  <br/> |页面默认值  <br/> |**visLOJumpStyleDefault** <br/> |
|1  <br/> |Arc  <br/> |**visLOJumpStyleArc** <br/> |
|2  <br/> |间隙  <br/> |**visLOJumpStyleGap** <br/> |
|3  <br/> |正方形  <br/> |**visLOJumpStyleSquare** <br/> |
|4   <br/> |三角形  <br/> |**visLOJumpStyleTriangle** <br/> |
|5   <br/> |三个面  <br/> |**visLOJumpStyle2Point** <br/> |
|6   <br/> |四个面  <br/> |**visLOJumpStyle3Point** <br/> |
|7   <br/> |五个面  <br/> |**visLOJumpStyle4Point** <br/> |
|8   <br/> |六个面  <br/> |**visLOJumpStyle5Point** <br/> |
|9   <br/> |七个面  <br/> |**visLOJumpStyle6Point** <br/> |
   
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionObject** <br/> |
|行索引：  <br/> |**visRowShapeLayout** <br/> |
|单元格索引：  <br/> |**visSLOJumpStyle** <br/> |
   
## <a name="remarks"></a>备注

您还可以通过选择动态连接线、单击"开发工具"选项卡上的"形状设计"组中的行为，然后单击"连接 [](run-in-developer-mode-display-the-developer-tab.md)线"选项卡来设置此 **单元格** 的值。  
  
若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 ConLineJumpStyle 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |ConLineJumpStyle  <br/> |
   
若要从某个程序按索引获取对 ConLineJumpStyle 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  

