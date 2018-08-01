---
title: RelQuadBezTo 行（“Geometry”部分）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 5ae57707-5a50-43f0-8c78-516790b5034e
description: 包含 x 和 y 坐标的终点相对于形状的宽度和高度和 x 二次贝塞尔曲线的-和 y-曲线相对于形状的宽度和高度的控制点的坐标。
ms.openlocfilehash: 99796e85a857fd320598cb48993fc29bdfa4964d
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781100"
---
# <a name="relquadbezto-row-geometry-section"></a>RelQuadBezTo 行（“Geometry”部分）

包含*x*和*y*坐标的终点相对于形状的宽度和高度和*x*二次贝塞尔曲线的-和*y* -曲线相对于形状的宽度和高度的控制点的坐标。 
  
> [!NOTE]
> **RelQuadBezTo**行仅可保持在.vsdx、.vsdm、.vstx、.vstm、.vssx 和.vssm 文件格式。 为 Visio 2003 2010年格式保存文件后， **RelQuadBezTo**行转换为某一[NURBSTo](nurbsto-row-geometry-section.md)行。 
  
**RelQuadBezTo**行包含以下单元格。 
  
|**Cell**|**说明**|
|:-----|:-----|
|[X](x-cell-geometry-section.md) <br/> |*X* -相对于形状的宽度二次贝塞尔曲线终顶点的坐标。  <br/> |
|[Y](y-cell-geometry-section.md) <br/> |*Y* -相对于形状的高度二次贝塞尔曲线终顶点的坐标。  <br/> |
|[A](a-cell-geometry-section.md) <br/> |*X* -相对于形状的宽度; 曲线的控制点的坐标弧形上某个点。是最好位于之间的开始和结束顶点的一半的控制点。  <br/> |
|[B](b-cell-geometry-section.md) <br/> |*Y* -相对于形状的高度曲线的控制点的坐标。  <br/> |
   

