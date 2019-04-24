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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32360058"
---
# <a name="conlinejumpstyle-cell-shape-layout-section"></a>ConLineJumpStyle 单元格（“Shape Layout”内容）

确定动态连接线上的跨线的跨线样式。
  
|**值**|**跨线样式**|**自动常量**|
|:-----|:-----|:-----|
|0  <br/> |页面默认值  <br/> |**visLOJumpStyleDefault** <br/> |
|1  <br/> |Arc  <br/> |**visLOJumpStyleArc** <br/> |
|双面  <br/> |间隙  <br/> |**visLOJumpStyleGap** <br/> |
|第三章  <br/> |正方形  <br/> |**visLOJumpStyleSquare** <br/> |
|4  <br/> |标识  <br/> |**visLOJumpStyleTriangle** <br/> |
|5  <br/> |三个面  <br/> |**visLOJumpStyle2Point** <br/> |
|型  <br/> |四个面  <br/> |**visLOJumpStyle3Point** <br/> |
|步  <br/> |五个面  <br/> |**visLOJumpStyle4Point** <br/> |
|utf-8  <br/> |六个面  <br/> |**visLOJumpStyle5Point** <br/> |
|第  <br/> |七个面  <br/> |**visLOJumpStyle6Point** <br/> |
   
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionObject** <br/> |
|行索引：  <br/> |**visRowShapeLayout** <br/> |
|单元格索引：  <br/> |**visSLOJumpStyle** <br/> |
   
## <a name="remarks"></a>注解

您还可以通过以下方法设置此单元格的值: 选择动态连接线, 在 "[开发工具](run-in-developer-mode-display-the-developer-tab.md)" 选项卡上的 "**形状设计**" 组中单击 "**行为**", 然后单击 "**连接线**" 选项卡。 
  
若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 ConLineJumpStyle 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |ConLineJumpStyle  <br/> |
   
若要从某个程序按索引获取对 ConLineJumpStyle 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  

