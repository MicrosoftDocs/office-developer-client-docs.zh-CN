---
title: LineJumpStyle 单元格（“Page Layout”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251646
localization_priority: Normal
ms.assetid: 89f16674-ee1f-f5f9-9830-7bcc52e3a068
description: 确定在没有本地跨线样式的绘图页上，所有连接线的跨线样式。
ms.openlocfilehash: 066c96f659061290b825684a479432e6d71f518c
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33427239"
---
# <a name="linejumpstyle-cell-page-layout-section"></a>LineJumpStyle 单元格（“Page Layout”内容）

确定在没有本地跨线样式的绘图页上，所有连接线的跨线样式。
  
|**值**|**跨线样式**|**自动常量**|
|:-----|:-----|:-----|
|0  <br/> |Arc  <br/> |**visLOJumpStyleDefault** <br/> |
|1  <br/> |Arc  <br/> |**visLOJumpStyleArc** <br/> |
|双面  <br/> |间隙  <br/> |**visLOJumpStyleGap** <br/> |
|第三章  <br/> |正方形  <br/> |**visLOJumpStyleSquare** <br/> |
|4  <br/> |双面  <br/> |**visLOJumpStyleTriangle** <br/> |
|5  <br/> |三个面  <br/> |**visLOJumpStyle2Point** <br/> |
|型  <br/> |四个面  <br/> |**visLOJumpStyle3Point** <br/> |
|步  <br/> |五个面  <br/> |**visLOJumpStyle4Point** <br/> |
|utf-8  <br/> |六个面  <br/> |**visLOJumpStyle5Point** <br/> |
|第  <br/> |七个面  <br/> |**visLOJumpStyle6Point** <br/> |
   
## <a name="remarks"></a>说明

还可以在 **“页面设置”** 对话框中的 **“布局与排列”** 选项卡（在 **“设计”** 选项卡上，单击 **“页面设置”** 箭头，然后单击 **“布局与排列”**）上设置此单元格的值。
  
若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 LineJumpStyle 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |LineJumpStyle  <br/> |
   
若要从某个程序按索引获取对 LineJumpStyle 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionObject** <br/> |
|行索引：  <br/> |**visRowPageLayout** <br/> |
|单元格索引：  <br/> |**visPLOJumpStyle** <br/> |
   

