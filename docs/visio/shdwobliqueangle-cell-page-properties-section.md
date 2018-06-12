---
title: ShdwObliqueAngle 单元格（“Page Properties”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm1033178
localization_priority: Normal
ms.assetid: 2e0b9754-3e3b-3a26-4e1a-e09102055c20
description: 包含指定应用默认页面阴影类型时的倾斜方向角度的数字。
ms.openlocfilehash: 4549ce7b5202b4649a925b04ea54c0d5df569599
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781343"
---
# <a name="shdwobliqueangle-cell-page-properties-section"></a><span data-ttu-id="a6e91-103">ShdwObliqueAngle 单元格（“Page Properties”内容）</span><span class="sxs-lookup"><span data-stu-id="a6e91-103">ShdwObliqueAngle Cell (Page Properties Section)</span></span>

<span data-ttu-id="a6e91-104">包含指定应用默认页面阴影类型时的倾斜方向角度的数字。</span><span class="sxs-lookup"><span data-stu-id="a6e91-104">Contains a number specifying the angle of oblique direction when applying the default page shadow type.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="a6e91-105">注释</span><span class="sxs-lookup"><span data-stu-id="a6e91-105">Remarks</span></span>

<span data-ttu-id="a6e91-106">此单元格中的值为零 (0) 时表示角度方向为垂直向上，并且按照顺时针度量。</span><span class="sxs-lookup"><span data-stu-id="a6e91-106">A value of zero (0) in this cell indicates that the angle direction is straight up and is measured moving clockwise.</span></span>
  
 <span data-ttu-id="a6e91-107">ShapeShdwType 单元格 （页上的形状的阴影类型） 设置为页面默认值 (**visFSTPageDefault** )，以及是倾斜的阴影类型使用此单元格中描述的角度。</span><span class="sxs-lookup"><span data-stu-id="a6e91-107">The angle described in this cell is used whenever the ShapeShdwType Cell (the shadow type for a shape on the page) is set to Page Default (**visFSTPageDefault** ), and the shadow type is oblique.</span></span> <span data-ttu-id="a6e91-108">ShdwType 单元格中定义的默认页面阴影类型。</span><span class="sxs-lookup"><span data-stu-id="a6e91-108">The default page shadow type is defined in the ShdwType cell.</span></span> 
  
<span data-ttu-id="a6e91-109">要为单个形状设置此行为，请使用“Fill Format”内容中的 ShapeShdwObliqueAngle 单元格。</span><span class="sxs-lookup"><span data-stu-id="a6e91-109">To set this behavior for an individual shape, use the ShapeShdwObliqueAngle cell in the Fill Format section.</span></span>
  
<span data-ttu-id="a6e91-110">要从另一个公式或使用**CellsU**属性从某个程序按名称获取对 ShdwObliqueAngle 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="a6e91-110">To get a reference to the ShdwObliqueAngle cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="a6e91-111">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="a6e91-111">Cell name:</span></span>  <br/> | <span data-ttu-id="a6e91-112">ShdwObliqueAngle</span><span class="sxs-lookup"><span data-stu-id="a6e91-112">ShdwObliqueAngle</span></span>  <br/> |
   
<span data-ttu-id="a6e91-113">若要从某个程序按索引获取对 ShdwObliqueAngle 单元格的引用，请使用带下列参数的**CellsSRC**属性：</span><span class="sxs-lookup"><span data-stu-id="a6e91-113">To get a reference to the ShdwObliqueAngle cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="a6e91-114">内容索引：</span><span class="sxs-lookup"><span data-stu-id="a6e91-114">Section index:</span></span>  <br/> |<span data-ttu-id="a6e91-115">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="a6e91-115">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="a6e91-116">行索引：</span><span class="sxs-lookup"><span data-stu-id="a6e91-116">Row index:</span></span>  <br/> |<span data-ttu-id="a6e91-117">**visRowPage**</span><span class="sxs-lookup"><span data-stu-id="a6e91-117">**visRowPage**</span></span> <br/> |
| <span data-ttu-id="a6e91-118">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="a6e91-118">Cell index:</span></span>  <br/> |<span data-ttu-id="a6e91-119">**visPageShdwObliqueAngle**</span><span class="sxs-lookup"><span data-stu-id="a6e91-119">**visPageShdwObliqueAngle**</span></span> <br/> |
   

