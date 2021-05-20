---
title: ShapeFixedCode 单元格（“Shape Layout”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm880
localization_priority: Normal
ms.assetid: a1736a5c-421c-2bdb-b164-76a8cd06cc3d
description: 指定可放置形状的放置行为。
ms.openlocfilehash: eae44a0579129fbe8da1c0cc8c37318beb024563
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33431741"
---
# <a name="shapefixedcode-cell-shape-layout-section"></a>ShapeFixedCode 单元格（“Shape Layout”内容）

指定可放置形状的放置行为。
  
|**值**|**选择方式**|**自动常量**|
|:-----|:-----|:-----|
|&amp;H1  <br/> |使用"配置布局"对话框布置形状时，不要 **移动** 此形状。  <br/> |**visSLOFixedPlacement** <br/> |
|&amp;H2  <br/> |不移动该形状，并且不允许将绘制的形状放置在它的上面。  <br/> |**visSLOFixedPlow** <br/> |
|&amp;H4  <br/> |不移动该形状，但允许将绘制的形状放置在它的上面。  <br/> |**visSLOFixedPermeablePlow** <br/> |
|&amp;H20 (32)   <br/> |在排列时忽略连接点位置。  <br/> |**visSLOFixedConnPtsIgnore** <br/> |
|&amp;H40 (64)   <br/> |仅允许排列到具有连接点的面上。  <br/> |**visSLOFixedConnPtsOnly** <br/> |
|&amp;H80 (128)   <br/> |不粘附到该形状的周界上，而是粘附到该形状的对齐框上。  <br/> |**visSLOFixedNoFoldToShape** <br/> |
   
## <a name="remarks"></a>备注

您还可以在"行为"对话框的"放置"选项卡上设置此单元格的值 (其中选择了一个形状;在"开发工具"[](run-in-developer-mode-display-the-developer-tab.md)选项卡上的"形状设计"组中，单击"行为"，然后单击"放置"选项卡) 。   
  
您可以为此单元格设置这些值的任意组合。 例如，您可以输入值 3 (H3) ，这样，当您使用"设计"选项卡上的"配置布局"对话框 (布局形状时，在"布局"组中单击"重新布局页面"，然后单击"其他布局选项 &amp; ) "，以及当其他可放置形状放置在形状上或形状附近时，这可消除移动。 
  
在 Visio 2000 之前的版本中，您可以使用“Miscellaneous”内容中的 ObjInteract 单元格设置此行为。 
  
若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 ShapeFixedCode 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |ShapeFixedCode  <br/> |
   
若要从某个程序按索引获取对 ShapeFixedCode 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionObject** <br/> |
|行索引：  <br/> |**visRowShapeLayout** <br/> |
|单元格索引：  <br/> |**visSLOFixedCode** <br/> |
   

