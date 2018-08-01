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
description: 包含 x 和 y-折线以及折线公式的最后一个点的坐标。
ms.openlocfilehash: 56cecb2eeaa1702461b1096fe468974f2f0b1f52
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780880"
---
# <a name="polylineto-row-geometry-section"></a><span data-ttu-id="04d4c-103">PolylineTo 行（“Geometry”部分）</span><span class="sxs-lookup"><span data-stu-id="04d4c-103">PolylineTo Row (Geometry Section)</span></span>

<span data-ttu-id="04d4c-104">包含*x*和*y* -折线以及折线公式的最后一个点的坐标。</span><span class="sxs-lookup"><span data-stu-id="04d4c-104">Contains  *x*  - and  *y*  -coordinates of the last point of a polyline and a polyline formula.</span></span> 
  
<span data-ttu-id="04d4c-105">PolylineTo 行包含以下单元格。</span><span class="sxs-lookup"><span data-stu-id="04d4c-105">A PolylineTo row contains the following cells.</span></span>
  
|<span data-ttu-id="04d4c-106">**Cell**</span><span class="sxs-lookup"><span data-stu-id="04d4c-106">**Cell**</span></span>|<span data-ttu-id="04d4c-107">**说明**</span><span class="sxs-lookup"><span data-stu-id="04d4c-107">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="04d4c-108">X</span><span class="sxs-lookup"><span data-stu-id="04d4c-108">X</span></span>](x-cell-geometry-section.md) <br/> |<span data-ttu-id="04d4c-109">*X* -折线终顶点的坐标。</span><span class="sxs-lookup"><span data-stu-id="04d4c-109">The  *x*  -coordinate of the ending vertex of a polyline.</span></span>  <br/> |
|[<span data-ttu-id="04d4c-110">Y</span><span class="sxs-lookup"><span data-stu-id="04d4c-110">Y</span></span>](y-cell-geometry-section.md) <br/> |<span data-ttu-id="04d4c-111">*Y* -折线终顶点的坐标。</span><span class="sxs-lookup"><span data-stu-id="04d4c-111">The  *y*  -coordinate of the ending vertex of a polyline.</span></span>  <br/> |
|[<span data-ttu-id="04d4c-112">A</span><span class="sxs-lookup"><span data-stu-id="04d4c-112">A</span></span>](a-cell-geometry-section.md) <br/> |<span data-ttu-id="04d4c-113">折线公式。</span><span class="sxs-lookup"><span data-stu-id="04d4c-113">The polyline formula.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="04d4c-114">注解</span><span class="sxs-lookup"><span data-stu-id="04d4c-114">Remarks</span></span>

<span data-ttu-id="04d4c-p101">表示为 Polyline 行的线条等价于表示为 LineTo 行序列的线条，而 Polyline 行更加有效。您可将 PolylineTo 行更改为 LineTo 行，从而方便地查看形状的几何图形。若要将 PolylineTo 行更改为 LineTo 行，请右击 PolylineTo 行，然后单击快捷菜单上的 **“扩展行”**。</span><span class="sxs-lookup"><span data-stu-id="04d4c-p101">Lines represented as a Polyline row are equivalent to lines represented as a sequence of LineTo rows, but a Polyline row is more efficient. You can change a PolylineTo row to a LineTo row so you can easily see the shape geometry. To do this, right-click the PolylineTo row, and then click **Expand Row** on the shortcut menu.</span></span> 
  
<span data-ttu-id="04d4c-118">若要更改 PolylineTo 行的行类型，请右击该行，然后单击快捷菜单上的 **“更改行类型”**。</span><span class="sxs-lookup"><span data-stu-id="04d4c-118">To change a row type to a PolylineTo row, right-click the row, and then click **Change Row Type** on the shortcut menu.</span></span> 
  

