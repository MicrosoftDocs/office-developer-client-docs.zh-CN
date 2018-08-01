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
ms.openlocfilehash: d64e7b3c7cf30f0a657ede57b227acefd4b10101
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781141"
---
# <a name="routestyle-cell-page-layout-section"></a>RouteStyle 单元格（“Page Layout”部分）

在没有本地排列样式的绘图页上确定所有连接线的排列样式和方向。
  
|**值**|**排列样式**|**Direction**|**自动常量**|
|:-----|:-----|:-----|:-----|
|0  <br/> |默认值：直角  <br/> |无  <br/> |**visLORouteDefault** <br/> |
|1  <br/> |直角  <br/> |无  <br/> |**visLORouteRightAngle** <br/> |
|2  <br/> |直线  <br/> |无  <br/> |**visLORouteStraight** <br/> |
|3  <br/> |组织结构图  <br/> |从上到下  <br/> |**visLORouteOrgChartNS** <br/> |
|4  <br/> |组织结构图  <br/> |从左到右  <br/> |**visLORouteOrgChartWE** <br/> |
|5  <br/> |流程图  <br/> |从上到下  <br/> |**visLORouteFlowchartNS** <br/> |
|6  <br/> |流程图  <br/> |从左到右  <br/> |**visLORouteFlowchartWE** <br/> |
|7  <br/> |树  <br/> |从上到下  <br/> |**visLORouteTreeNS** <br/> |
|8  <br/> |树  <br/> |从左到右  <br/> |**visLORouteTreeWE** <br/> |
|9  <br/> |网络  <br/> |无  <br/> |**visLORouteNetwork** <br/> |
|10  <br/> |组织结构图  <br/> |从下到上  <br/> |**visLORouteOrgChartSN** <br/> |
|11  <br/> |组织结构图  <br/> |从右到左  <br/> |**visLORouteOrgChartEW** <br/> |
|12  <br/> |流程图  <br/> |从下到上  <br/> |**visLORouteFlowchartSN** <br/> |
|13  <br/> |流程图  <br/> |从右到左  <br/> |**visLORouteFlowchartEW** <br/> |
|14  <br/> |树  <br/> |从下到上  <br/> |**visLORouteTreeSN** <br/> |
|15  <br/> |树  <br/> |从右到左  <br/> |**visLORouteTreeEW** <br/> |
|16  <br/> |从中心到中心  <br/> |无  <br/> |**visLORouteCenterToCenter** <br/> |
|17  <br/> |简单  <br/> |从上到下  <br/> |**visLORouteSimpleNS** <br/> |
|18  <br/> |简单  <br/> |从左到右  <br/> |**visLORouteSimpleWE** <br/> |
|19  <br/> |简单  <br/> |从下到上  <br/> |**visLORouteSimpleSN** <br/> |
|20  <br/> |简单  <br/> |从右到左  <br/> |**visLORouteSimpleEW** <br/> |
|21  <br/> |简单水平 - 垂直  <br/> |无  <br/> |**visLORouteSimpleHV** <br/> |
|22  <br/> |简单垂直 - 水平  <br/> |无  <br/> |**visLORouteSimpleVH** <br/> |
   
## <a name="remarks"></a>说明

您还可以在**页面设置**对话框中**布局和路由**选项卡上设置此单元格的值 （**设计**选项卡中，单击**页面设置**箭头，单击**布局和路由**，然后单击**间距**）。 
  
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
   

