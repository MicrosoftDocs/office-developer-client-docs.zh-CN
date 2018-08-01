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
# <a name="arcto-row-geometry-section"></a><span data-ttu-id="7ff7e-103">ArcTo 行（“Geometry”部分）</span><span class="sxs-lookup"><span data-stu-id="7ff7e-103">ArcTo Row (Geometry Section)</span></span>

<span data-ttu-id="7ff7e-104">包含*x*和*y* -坐标和弓圆弧。</span><span class="sxs-lookup"><span data-stu-id="7ff7e-104">Contains the  *x*  - and  *y*  -coordinates and bow of a circular arc.</span></span> 
  
<span data-ttu-id="7ff7e-105">ArcTo 行包含以下单元格。</span><span class="sxs-lookup"><span data-stu-id="7ff7e-105">An ArcTo row contains the following cells.</span></span>
  
|<span data-ttu-id="7ff7e-106">**Cell**</span><span class="sxs-lookup"><span data-stu-id="7ff7e-106">**Cell**</span></span>|<span data-ttu-id="7ff7e-107">**说明**</span><span class="sxs-lookup"><span data-stu-id="7ff7e-107">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="7ff7e-108">X</span><span class="sxs-lookup"><span data-stu-id="7ff7e-108">X</span></span>](x-cell-geometry-section.md) <br/> |<span data-ttu-id="7ff7e-109">*X* -弧形终顶点的坐标。</span><span class="sxs-lookup"><span data-stu-id="7ff7e-109">The  *x*  -coordinate of the ending vertex of an arc.</span></span>  <br/> |
|[<span data-ttu-id="7ff7e-110">Y</span><span class="sxs-lookup"><span data-stu-id="7ff7e-110">Y</span></span>](y-cell-geometry-section.md) <br/> |<span data-ttu-id="7ff7e-111">*Y* -弧形终顶点的坐标。</span><span class="sxs-lookup"><span data-stu-id="7ff7e-111">The  *y*  -coordinate of the ending vertex of an arc.</span></span>  <br/> |
|[<span data-ttu-id="7ff7e-112">A</span><span class="sxs-lookup"><span data-stu-id="7ff7e-112">A</span></span>](a-cell-geometry-section.md) <br/> |<span data-ttu-id="7ff7e-113">从弧形的中点到对应的弦的中点的距离。</span><span class="sxs-lookup"><span data-stu-id="7ff7e-113">The distance from the arc's midpoint to the midpoint of its chord.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="7ff7e-114">注解</span><span class="sxs-lookup"><span data-stu-id="7ff7e-114">Remarks</span></span>

<span data-ttu-id="7ff7e-p101">在 Visio 中绘制的弧形是椭圆弧，即使它们基于圆形也不例外。默认情况下，所绘制的弧形是用 ShapeSheet 窗口中的 EllipticalArcTo 行表示的。若要在 ShapeSheet 窗口中显示 ArcTo 行，必须先绘制一个弧形，然后将 EllipticalArcTo 行类型更改为 ArcTo 行类型；这时实际已将椭圆弧更改为圆弧了。</span><span class="sxs-lookup"><span data-stu-id="7ff7e-p101">Arcs drawn in Visio are elliptical arcs, even if they are based on a circle. By default, drawn arcs are represented by an EllipticalArcTo row in a ShapeSheet window. To show an ArcTo row in a ShapeSheet window, you must draw an arc, and then change the EllipticalArcTo row type to an ArcTo row type; in effect you are changing an elliptical arc to a circular arc.</span></span>
  
<span data-ttu-id="7ff7e-118">若要更改行类型，请右击某一行，然后单击快捷菜单上的 **“更改行类型”**。</span><span class="sxs-lookup"><span data-stu-id="7ff7e-118">To change a row type, right-click a row, and then click **Change Row Type** on the shortcut menu.</span></span> 
  

