---
title: ShapeRouteStyle 单元格（“Shape Layout”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm905
localization_priority: Normal
ms.assetid: a5dcd2e0-e343-5ee2-2b63-2a1312437901
description: 确定绘图页上所选连接线的排列样式和方向。
ms.openlocfilehash: e5725d461a71dad4623161d99134a20250abe724
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33425027"
---
# <a name="shaperoutestyle-cell-shape-layout-section"></a>ShapeRouteStyle 单元格（“Shape Layout”内容）

确定绘图页上所选连接线的排列样式和方向。
  
|**值**|**排列样式**|**方向**|**自动常量**|
|:-----|:-----|:-----|:-----|
|0  <br/> |使用页默认值  <br/> |无  <br/> |**visLORouteDefault** <br/> |
|1  <br/> |直角  <br/> |无  <br/> |**visLORouteRightAngle** <br/> |
|2  <br/> |直  <br/> |无  <br/> |**visLORouteStraight** <br/> |
|3  <br/> |组织结构图  <br/> |从上到下  <br/> |**visLORouteOrgChartNS** <br/> |
|4   <br/> |组织结构图  <br/> |从左到右  <br/> |**visLORouteOrgChartWE** <br/> |
|5   <br/> |流程图  <br/> |从上到下  <br/> |**visLORouteFlowchartNS** <br/> |
|6   <br/> |流程图  <br/> |从左到右  <br/> |**visLORouteFlowchartWE** <br/> |
|7   <br/> |树  <br/> |从上到下  <br/> |**visLORouteTreeNS** <br/> |
|8   <br/> |树  <br/> |从左到右  <br/> |**visLORouteTreeWE** <br/> |
|9   <br/> |网络  <br/> |无  <br/> |**visLORouteNetwork** <br/> |
|10    <br/> |组织结构图  <br/> |从下到上  <br/> |**visLORouteOrgChartSN** <br/> |
|11  <br/> |组织结构图  <br/> |从右到左  <br/> |**visLORouteOrgChartEW** <br/> |
|12   <br/> |流程图  <br/> |从下到上  <br/> |**visLORouteFlowchartSN** <br/> |
|13  <br/> |流程图  <br/> |从右到左  <br/> |**visLORouteFlowchartEW** <br/> |
|14   <br/> |树  <br/> |从下到上  <br/> |**visLORouteTreeSN** <br/> |
|15  <br/> |树  <br/> |从右到左  <br/> |**visLORouteTreeEW** <br/> |
|16   <br/> |从中心到中心  <br/> |无  <br/> |**visLORouteCenterToCenter** <br/> |
|17   <br/> |简单  <br/> |从上到下  <br/> |**visLORouteSimpleNS** <br/> |
|18   <br/> |简单  <br/> |从左到右  <br/> |**visLORouteSimpleWE** <br/> |
|19  <br/> |简单  <br/> |从下到上  <br/> |**visLORouteSimpleSN** <br/> |
|20  <br/> |简单  <br/> |从右到左  <br/> |**visLORouteSimpleEW** <br/> |
| 21  <br/> |简单水平 - 垂直  <br/> |无  <br/> |**visLORouteSimpleHV** <br/> |
|22  <br/> |简单垂直 - 水平  <br/> |无  <br/> |**visLORouteSimpleVH** <br/> |
   
## <a name="remarks"></a>备注

还可以在"行为"对话框中的"连接器"选项卡上设置此单元格的值，该单元格位于"行为"对话框中 (选择了连接器，单击"开发工具"选项卡[](run-in-developer-mode-display-the-developer-tab.md)上的"行为"，然后单击"连接器"选项卡) 。  
  
若要为页面上  *的所有*  连接线设置此行为，请使用"页面布局"部分中的 RouteStyle 单元格。 
  
在 Visio 2000 之前的版本中，您可以使用“Miscellaneous”内容中的 ObjBehavior 单元格设置此行为。
  
若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 ShapeRouteStyle 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |ShapeRouteStyle  <br/> |
   
若要从某个程序按索引获取对 ShapeRouteStyle 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionObject** <br/> |
|行索引：  <br/> |**visRowShapeLayout** <br/> |
|单元格索引：  <br/> |**visSLORouteStyle** <br/> |
   

