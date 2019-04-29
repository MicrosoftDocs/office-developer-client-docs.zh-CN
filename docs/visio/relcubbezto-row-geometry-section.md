---
title: RelCubBezTo 行 ("Geometry" 部分)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 77777dd4-5a2c-4048-9ea4-9bd876862963
description: 包含相对于形状的宽度和高度的三次方贝塞尔曲线终结点的 x 坐标和 y 坐标、曲线相对形状的宽度和高度起始控制点的 x 坐标和 y 坐标以及 contro 的 x 坐标和 y 坐标。曲线相对形状的宽度和高度的结束点。
ms.openlocfilehash: cb886706c4c5cbb3488a95b57dcc84e0e45ee326
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33430327"
---
# <a name="relcubbezto-row-geometry-section"></a>RelCubBezTo 行 ("Geometry" 部分)

包含相对于形状的宽度和高度的三次方贝塞尔曲线终结点的*x*坐标和*y*坐标、曲线相对形状的宽度和高度起始点的*x*坐标和*y*坐标,以及曲线相对形状的宽度和高度的结束控制点的*x*坐标和*y*坐标。 
  
> [!NOTE]
> **RelCubBezTo**行只能在 .vsdx、.vsdm、.vstx、.vstm、.vssx 和. .vssm 文件格式中持久化。 将文件保存为 Visio 2003-2010 格式时, **RelCubBezTo**行将转换为[NURBSTo](nurbsto-row-geometry-section.md)行。 
  
**RelCubBezTo**行包含以下单元格。 
  
|**单元格**|**说明**|
|:-----|:-----|
|[X](x-cell-geometry-section.md) <br/> |一条立方贝塞尔曲线终顶点相对于形状宽度的*x*坐标。  <br/> |
|[Y](y-cell-geometry-section.md) <br/> |一条立方贝塞尔曲线终顶点的*y*坐标 (相对于形状的高度)。  <br/> |
|[A](a-cell-geometry-section.md) <br/> |曲线的起始控制点相对于形状宽度的*x*坐标;弧形上的一点。控制点最好位于弧形的起始和结束顶点之间。  <br/> |
|[黑白](b-cell-geometry-section.md) <br/> |相对于形状的高度的曲线起点的*y*轴坐标值。  <br/> |
|[lc](c-cell-geometry-section.md) <br/> |相对于形状宽度的曲线结束控制点的*x*坐标;弧形上的一点。控制点最适合在弧的起始控制点和结束顶点之间。  <br/> |
|[D](d-cell-geometry-section.md) <br/> |相对于形状高度的曲线终点的*y*轴坐标值。  <br/> |
   

