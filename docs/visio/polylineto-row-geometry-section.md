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
description: 包含折线的最后一个点和折线公式的 x 坐标和 y 坐标。
ms.openlocfilehash: 13e5bd7138103094f0f00ad0512e33e9e6ad5e7f
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32359827"
---
# <a name="polylineto-row-geometry-section"></a><span data-ttu-id="41b1a-103">PolylineTo 行（“Geometry”内容）</span><span class="sxs-lookup"><span data-stu-id="41b1a-103">PolylineTo Row (Geometry Section)</span></span>

<span data-ttu-id="41b1a-104">包含折线的最后一个点和折线公式的*x*坐标和*y*坐标。</span><span class="sxs-lookup"><span data-stu-id="41b1a-104">Contains  *x*  - and  *y*  -coordinates of the last point of a polyline and a polyline formula.</span></span> 
  
<span data-ttu-id="41b1a-105">PolylineTo 行包含以下单元格。</span><span class="sxs-lookup"><span data-stu-id="41b1a-105">A PolylineTo row contains the following cells.</span></span>
  
|<span data-ttu-id="41b1a-106">**Cell**</span><span class="sxs-lookup"><span data-stu-id="41b1a-106">**Cell**</span></span>|<span data-ttu-id="41b1a-107">**Description**</span><span class="sxs-lookup"><span data-stu-id="41b1a-107">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="41b1a-108">X</span><span class="sxs-lookup"><span data-stu-id="41b1a-108">X</span></span>](x-cell-geometry-section.md) <br/> |<span data-ttu-id="41b1a-109">折线终顶点的*x*坐标。</span><span class="sxs-lookup"><span data-stu-id="41b1a-109">The  *x*  -coordinate of the ending vertex of a polyline.</span></span>  <br/> |
|[<span data-ttu-id="41b1a-110">Y</span><span class="sxs-lookup"><span data-stu-id="41b1a-110">Y</span></span>](y-cell-geometry-section.md) <br/> |<span data-ttu-id="41b1a-111">折线终顶点的*y*坐标。</span><span class="sxs-lookup"><span data-stu-id="41b1a-111">The  *y*  -coordinate of the ending vertex of a polyline.</span></span>  <br/> |
|[<span data-ttu-id="41b1a-112">A</span><span class="sxs-lookup"><span data-stu-id="41b1a-112">A</span></span>](a-cell-geometry-section.md) <br/> |<span data-ttu-id="41b1a-113">折线公式。</span><span class="sxs-lookup"><span data-stu-id="41b1a-113">The polyline formula.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="41b1a-114">注解</span><span class="sxs-lookup"><span data-stu-id="41b1a-114">Remarks</span></span>

<span data-ttu-id="41b1a-p101">表示为 Polyline 行的线条等价于表示为 LineTo 行序列的线条，而 Polyline 行更加有效。您可将 PolylineTo 行更改为 LineTo 行，从而方便地查看形状的几何图形。若要将 PolylineTo 行更改为 LineTo 行，请右击 PolylineTo 行，然后单击快捷菜单上的 **“扩展行”**。</span><span class="sxs-lookup"><span data-stu-id="41b1a-p101">Lines represented as a Polyline row are equivalent to lines represented as a sequence of LineTo rows, but a Polyline row is more efficient. You can change a PolylineTo row to a LineTo row so you can easily see the shape geometry. To do this, right-click the PolylineTo row, and then click **Expand Row** on the shortcut menu.</span></span> 
  
<span data-ttu-id="41b1a-118">若要更改 PolylineTo 行的行类型，请右击该行，然后单击快捷菜单上的 **“更改行类型”**。</span><span class="sxs-lookup"><span data-stu-id="41b1a-118">To change a row type to a PolylineTo row, right-click the row, and then click **Change Row Type** on the shortcut menu.</span></span> 
  

