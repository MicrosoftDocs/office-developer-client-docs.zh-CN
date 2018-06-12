---
title: ArcTo 行（“Geometry”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82253229
localization_priority: Normal
ms.assetid: 612b605d-a703-b08f-2e8e-7bc1624b5370
description: 包含 x 和 y-坐标和弓圆弧。
ms.openlocfilehash: 77ed0dcaee7ddefa8771d3e890776d4adfcc3b40
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779651"
---
# <a name="arcto-row-geometry-section"></a>ArcTo 行（“Geometry”内容）

包含*x*和*y* -坐标和弓圆弧。 
  
ArcTo 行包含以下单元格。
  
|**Cell**|**说明**|
|:-----|:-----|
|[X](x-cell-geometry-section.md) <br/> |*X* -弧形终顶点的坐标。  <br/> |
|[Y](y-cell-geometry-section.md) <br/> |*Y* -弧形终顶点的坐标。  <br/> |
|[A](a-cell-geometry-section.md) <br/> |从弧形的中点到对应的弦的中点的距离。  <br/> |
   
## <a name="remarks"></a>注解

在 Visio 中绘制的弧形是椭圆弧，即使它们基于圆形也不例外。默认情况下，所绘制的弧形是用 ShapeSheet 窗口中的 EllipticalArcTo 行表示的。若要在 ShapeSheet 窗口中显示 ArcTo 行，必须先绘制一个弧形，然后将 EllipticalArcTo 行类型更改为 ArcTo 行类型；这时实际已将椭圆弧更改为圆弧了。
  
若要更改行类型，右击该行，，，然后单击快捷菜单上的**更改行类型**。 
  

