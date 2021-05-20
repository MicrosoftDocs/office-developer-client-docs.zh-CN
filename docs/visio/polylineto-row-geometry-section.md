---
title: PolylineTo 行（“Geometry”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251757
localization_priority: Normal
ms.assetid: b78a993f-4165-438d-39cf-9461b2877f17
description: 包含折线和折线公式的最后一个点的 x 坐标和 y 坐标。
ms.openlocfilehash: 13e5bd7138103094f0f00ad0512e33e9e6ad5e7f
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33439462"
---
# <a name="polylineto-row-geometry-section"></a>PolylineTo 行（“Geometry”内容）

包含  *折*  线和折线公式的最后一个点的 x 坐标和  *y*  坐标。 
  
PolylineTo 行包含以下单元格。
  
|**Cell**|**说明**|
|:-----|:-----|
|[X](x-cell-geometry-section.md) <br/> |折线终顶点的  *x*  坐标。  <br/> |
|[Y](y-cell-geometry-section.md) <br/> |折线终顶点的  *y*  坐标。  <br/> |
|[A](a-cell-geometry-section.md) <br/> |折线公式。  <br/> |
   
## <a name="remarks"></a>备注

表示为 Polyline 行的线条等价于表示为 LineTo 行序列的线条，而 Polyline 行更加有效。您可将 PolylineTo 行更改为 LineTo 行，从而方便地查看形状的几何图形。若要将 PolylineTo 行更改为 LineTo 行，请右击 PolylineTo 行，然后单击快捷菜单上的 **“扩展行”**。 
  
若要更改 PolylineTo 行的行类型，请右击该行，然后单击快捷菜单上的 **“更改行类型”**。 
  

