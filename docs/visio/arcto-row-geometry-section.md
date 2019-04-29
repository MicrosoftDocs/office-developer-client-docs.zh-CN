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
description: 包含 x 坐标和 y 坐标以及圆弧的凸起。
ms.openlocfilehash: 222edea250be794adc964345384f2c08a7798f2f
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33430040"
---
# <a name="arcto-row-geometry-section"></a>ArcTo 行（“Geometry”内容）

包含*x*坐标和*y*坐标以及圆弧的凸起。 
  
ArcTo 行包含以下单元格。
  
|**单元格**|**说明**|
|:-----|:-----|
|[X](x-cell-geometry-section.md) <br/> |弧形终顶点的*x*坐标。  <br/> |
|[Y](y-cell-geometry-section.md) <br/> |弧形终顶点的*y*坐标。  <br/> |
|[A](a-cell-geometry-section.md) <br/> |从弧形的中点到对应的弦的中点的距离。  <br/> |
   
## <a name="remarks"></a>说明

在 Visio 中绘制的弧形是椭圆弧，即使它们基于圆形也不例外。默认情况下，所绘制的弧形是用 ShapeSheet 窗口中的 EllipticalArcTo 行表示的。若要在 ShapeSheet 窗口中显示 ArcTo 行，必须先绘制一个弧形，然后将 EllipticalArcTo 行类型更改为 ArcTo 行类型；这时实际已将椭圆弧更改为圆弧了。
  
若要更改行类型，请右击某一行，然后单击快捷菜单上的 **“更改行类型”**。 
  

