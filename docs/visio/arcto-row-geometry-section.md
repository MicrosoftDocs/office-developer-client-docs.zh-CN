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
# <a name="arcto-row-geometry-section"></a><span data-ttu-id="33511-103">ArcTo 行（“Geometry”内容）</span><span class="sxs-lookup"><span data-stu-id="33511-103">ArcTo Row (Geometry Section)</span></span>

<span data-ttu-id="33511-104">包含*x*坐标和*y*坐标以及圆弧的凸起。</span><span class="sxs-lookup"><span data-stu-id="33511-104">Contains the  *x*  - and  *y*  -coordinates and bow of a circular arc.</span></span> 
  
<span data-ttu-id="33511-105">ArcTo 行包含以下单元格。</span><span class="sxs-lookup"><span data-stu-id="33511-105">An ArcTo row contains the following cells.</span></span>
  
|<span data-ttu-id="33511-106">**单元格**</span><span class="sxs-lookup"><span data-stu-id="33511-106">**Cell**</span></span>|<span data-ttu-id="33511-107">**说明**</span><span class="sxs-lookup"><span data-stu-id="33511-107">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="33511-108">X</span><span class="sxs-lookup"><span data-stu-id="33511-108">X</span></span>](x-cell-geometry-section.md) <br/> |<span data-ttu-id="33511-109">弧形终顶点的*x*坐标。</span><span class="sxs-lookup"><span data-stu-id="33511-109">The  *x*  -coordinate of the ending vertex of an arc.</span></span>  <br/> |
|[<span data-ttu-id="33511-110">Y</span><span class="sxs-lookup"><span data-stu-id="33511-110">Y</span></span>](y-cell-geometry-section.md) <br/> |<span data-ttu-id="33511-111">弧形终顶点的*y*坐标。</span><span class="sxs-lookup"><span data-stu-id="33511-111">The  *y*  -coordinate of the ending vertex of an arc.</span></span>  <br/> |
|[<span data-ttu-id="33511-112">A</span><span class="sxs-lookup"><span data-stu-id="33511-112">A</span></span>](a-cell-geometry-section.md) <br/> |<span data-ttu-id="33511-113">从弧形的中点到对应的弦的中点的距离。</span><span class="sxs-lookup"><span data-stu-id="33511-113">The distance from the arc's midpoint to the midpoint of its chord.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="33511-114">说明</span><span class="sxs-lookup"><span data-stu-id="33511-114">Remarks</span></span>

<span data-ttu-id="33511-p101">在 Visio 中绘制的弧形是椭圆弧，即使它们基于圆形也不例外。默认情况下，所绘制的弧形是用 ShapeSheet 窗口中的 EllipticalArcTo 行表示的。若要在 ShapeSheet 窗口中显示 ArcTo 行，必须先绘制一个弧形，然后将 EllipticalArcTo 行类型更改为 ArcTo 行类型；这时实际已将椭圆弧更改为圆弧了。</span><span class="sxs-lookup"><span data-stu-id="33511-p101">Arcs drawn in Visio are elliptical arcs, even if they are based on a circle. By default, drawn arcs are represented by an EllipticalArcTo row in a ShapeSheet window. To show an ArcTo row in a ShapeSheet window, you must draw an arc, and then change the EllipticalArcTo row type to an ArcTo row type; in effect you are changing an elliptical arc to a circular arc.</span></span>
  
<span data-ttu-id="33511-118">若要更改行类型，请右击某一行，然后单击快捷菜单上的 **“更改行类型”**。</span><span class="sxs-lookup"><span data-stu-id="33511-118">To change a row type, right-click a row, and then click **Change Row Type** on the shortcut menu.</span></span> 
  

