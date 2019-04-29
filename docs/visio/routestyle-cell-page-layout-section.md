---
title: RouteStyle 单元格（“Page Layout”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251662
localization_priority: Normal
ms.assetid: 3a223dac-538b-cb5d-a32d-61395276f9da
description: 在没有本地排列样式的绘图页上确定所有连接线的排列样式和方向。
ms.openlocfilehash: 38de871460c155ee5d495599a239ebeb0ff1c33d
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33424782"
---
# <a name="routestyle-cell-page-layout-section"></a>RouteStyle 单元格（“Page Layout”内容）

在没有本地排列样式的绘图页上确定所有连接线的排列样式和方向。
  
|**值**|**排列样式**|**Direction**|**自动常量**|
|:-----|:-----|:-----|:-----|
|0  <br/> |默认值：直角  <br/> |无  <br/> |**visLORouteDefault** <br/> |
|1  <br/> |直角  <br/> |无  <br/> |**visLORouteRightAngle** <br/> |
|双面  <br/> |式  <br/> |无  <br/> |**visLORouteStraight** <br/> |
|第三章  <br/> |组织结构图  <br/> |从上到下  <br/> |**visLORouteOrgChartNS** <br/> |
|4  <br/> |组织结构图  <br/> |从左到右  <br/> |**visLORouteOrgChartWE** <br/> |
|5  <br/> |流程图  <br/> |从上到下  <br/> |**visLORouteFlowchartNS** <br/> |
|型  <br/> |流程图  <br/> |从左到右  <br/> |**visLORouteFlowchartWE** <br/> |
|步  <br/> |树  <br/> |从上到下  <br/> |**visLORouteTreeNS** <br/> |
|utf-8  <br/> |树  <br/> |从左到右  <br/> |**visLORouteTreeWE** <br/> |
|第  <br/> |网络  <br/> |无  <br/> |**visLORouteNetwork** <br/> |
|10   <br/> |组织结构图  <br/> |从下到上  <br/> |**visLORouteOrgChartSN** <br/> |
|11   <br/> |组织结构图  <br/> |从右到左  <br/> |**visLORouteOrgChartEW** <br/> |
|12   <br/> |流程图  <br/> |从下到上  <br/> |**visLORouteFlowchartSN** <br/> |
|13   <br/> |流程图  <br/> |从右到左  <br/> |**visLORouteFlowchartEW** <br/> |
|14   <br/> |树  <br/> |从下到上  <br/> |**visLORouteTreeSN** <br/> |
|15   <br/> |树  <br/> |从右到左  <br/> |**visLORouteTreeEW** <br/> |
|16   <br/> |从中心到中心  <br/> |无  <br/> |**visLORouteCenterToCenter** <br/> |
|×  <br/> |简单  <br/> |从上到下  <br/> |**visLORouteSimpleNS** <br/> |
|18  <br/> |简单  <br/> |从左到右  <br/> |**visLORouteSimpleWE** <br/> |
|合  <br/> |简单  <br/> |从下到上  <br/> |**visLORouteSimpleSN** <br/> |
|20  <br/> |简单  <br/> |从右到左  <br/> |**visLORouteSimpleEW** <br/> |
|不足  <br/> |简单水平 - 垂直  <br/> |无  <br/> |**visLORouteSimpleHV** <br/> |
|22  <br/> |简单垂直 - 水平  <br/> |无  <br/> |**visLORouteSimpleVH** <br/> |
   
## <a name="remarks"></a>说明

您还可以在 "**页面设置**" 对话框 (在 "**设计**" 选项卡上, 单击 "**页面设置**" 箭头, 单击 "**布局与排列**", 然后单击 "**间距**") 中的 "**布局与排列**" 选项卡上设置此单元格的值。 
  
您可以在“Shape Layout”内容的 ShapeRouteStyle 单元格中为连接线设置本地排列样式。 
  
若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 RouteStyle 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |RouteStyle  <br/> |
   
若要从某个程序按索引获取对 RouteStyle 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionObject** <br/> |
|行索引：  <br/> |**visRowPageLayout** <br/> |
|单元格索引：  <br/> |**visPLORouteStyle** <br/> |
   

