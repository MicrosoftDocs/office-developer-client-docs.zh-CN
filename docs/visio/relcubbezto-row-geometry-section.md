---
title: RelCubBezTo 行（“Geometry”部分）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 77777dd4-5a2c-4048-9ea4-9bd876862963
description: 包含 x 和 y 坐标的终结点的相对于形状的宽度和高度，x 三次贝赛尔曲线-和 y 坐标的位于曲线的相对于形状的宽度和高度和 x 开头的控制点-和 y-坐标控制l 曲线相对于形状的宽度和高度的结束点。
ms.openlocfilehash: 918701c19e36753dcbf1a210dda2234d1e540d6d
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781052"
---
# <a name="relcubbezto-row-geometry-section"></a>RelCubBezTo 行（“Geometry”部分）

包含*x*和*y*坐标的终结点的相对于形状的宽度和高度， *x*三次贝赛尔曲线-和*y* -的位于曲线的相对于形状的宽度和高度，开头的控制点的坐标和*x*和*y* -曲线相对于形状的宽度和高度的结束的控制点的坐标。 
  
> [!NOTE]
> **RelCubBezTo**行仅可保持在.vsdx、.vsdm、.vstx、.vstm、.vssx 和.vssm 文件格式。 为 Visio 2003 2010年格式保存文件后， **RelCubBezTo**行转换为某一[NURBSTo](nurbsto-row-geometry-section.md)行。 
  
**RelCubBezTo**行包含以下单元格。 
  
|**Cell**|**说明**|
|:-----|:-----|
|[X](x-cell-geometry-section.md) <br/> |*X* -相对于形状的宽度的立方贝赛尔曲线终顶点的坐标。  <br/> |
|[Y](y-cell-geometry-section.md) <br/> |*Y* -相对于形状的高度的立方贝赛尔曲线终顶点的坐标。  <br/> |
|[A](a-cell-geometry-section.md) <br/> |*X* -曲线的坐标的开始控制点相对于形状的宽度;弧形上某个点。最佳位于之间的开始和终顶点的弧的控制点。  <br/> |
|[B](b-cell-geometry-section.md) <br/> |*Y* -曲线的坐标的开始控制点相对于形状的高度。  <br/> |
|[C](c-cell-geometry-section.md) <br/> |*X* -曲线的坐标的结束控制点相对于形状的宽度;弧形上某个点。弧的起点控件点和结束顶点之间最佳位于控制点。  <br/> |
|[D](d-cell-geometry-section.md) <br/> |*Y* -曲线的坐标的结束控制点相对于形状的高度。  <br/> |
   

