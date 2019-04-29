---
title: RelQuadBezTo 行 ("Geometry" 部分)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 5ae57707-5a50-43f0-8c78-516790b5034e
description: 包含相对于形状的宽度和高度以及曲线相对形状的宽度和高度的控制点的 x 坐标和 y 坐标的二次贝塞尔曲线端点的 x 坐标和 y 坐标。
ms.openlocfilehash: f517fa006c6630a26e9162adfbb1be2139487e63
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33423354"
---
# <a name="relquadbezto-row-geometry-section"></a>RelQuadBezTo 行 ("Geometry" 部分)

包含相对于形状的宽度和高度以及曲线相对形状的宽度和高度的控制点的*x*坐标和*y*坐标的二次贝塞尔曲线端点的*x*坐标和*y*坐标。 
  
> [!NOTE]
> **RelQuadBezTo**行只能在 .vsdx、.vsdm、.vstx、.vstm、.vssx 和. .vssm 文件格式中持久化。 将文件保存为 Visio 2003-2010 格式时, **RelQuadBezTo**行将转换为[NURBSTo](nurbsto-row-geometry-section.md)行。 
  
**RelQuadBezTo**行包含以下单元格。 
  
|**单元格**|**说明**|
|:-----|:-----|
|[X](x-cell-geometry-section.md) <br/> |一条二次贝塞尔曲线终顶点相对于形状宽度的*x*坐标。  <br/> |
|[Y](y-cell-geometry-section.md) <br/> |一条二次贝塞尔曲线终顶点的*y*坐标 (相对于形状的高度)。  <br/> |
|[A](a-cell-geometry-section.md) <br/> |曲线的控制点相对于形状宽度的*x*坐标;弧形上的一点。控制点最适合弧的起始和结束顶点之间的中间点。  <br/> |
|[黑白](b-cell-geometry-section.md) <br/> |曲线的控制点相对于形状高度的*y*轴坐标值。  <br/> |
   

