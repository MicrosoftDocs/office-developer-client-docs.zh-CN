---
title: ShdwScaleFactor 单元格（“Page Properties”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm60083
localization_priority: Normal
ms.assetid: 10979706-6dfe-5241-e862-3f94716d14fa
description: 指定放大或缩小形状阴影的百分比。
ms.openlocfilehash: 9175e9a1148779524fdce96ff18eac22fe8dd421
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33429003"
---
# <a name="shdwscalefactor-cell-page-properties-section"></a><span data-ttu-id="4588b-103">ShdwScaleFactor 单元格（“Page Properties”内容）</span><span class="sxs-lookup"><span data-stu-id="4588b-103">ShdwScaleFactor Cell (Page Properties Section)</span></span>

<span data-ttu-id="4588b-104">指定放大或缩小形状阴影的百分比。</span><span class="sxs-lookup"><span data-stu-id="4588b-104">Specifies the percentage to enlarge or reduce a shape's shadow.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="4588b-105">备注</span><span class="sxs-lookup"><span data-stu-id="4588b-105">Remarks</span></span>

<span data-ttu-id="4588b-106">每个阴影都有一个阴影的图钉位置，该位置是阴影上对应于形状的图钉的点。</span><span class="sxs-lookup"><span data-stu-id="4588b-106">Each shadow has a shadowed pin location, which is a point on the shadow that corresponds to the shape's pin.</span></span> <span data-ttu-id="4588b-107">例如，如果形状的固定位于形状的中心，则阴影的固定位置将是阴影的中心点。</span><span class="sxs-lookup"><span data-stu-id="4588b-107">For example, if a shape's pin is in the center of the shape, then the shadowed pin location would be the point in the center of the shadow.</span></span> <span data-ttu-id="4588b-108">将缩放应用于简单阴影时，缩放以阴影的图钉位置为中心;当将缩放应用于倾斜阴影时，缩放将应用于倾斜方向。</span><span class="sxs-lookup"><span data-stu-id="4588b-108">When applying scale to simple shadows, magnification is centered at the shadowed pin location; when applying scale to oblique shadows, magnification is applied in the oblique direction.</span></span> 
  
 <span data-ttu-id="4588b-109">当形状的阴影类型设置为"页面默认值"时， (ShapeShdwType 单元格等于 \*\* visFSTPageDefault \*\* ) 。</span><span class="sxs-lookup"><span data-stu-id="4588b-109">This percentage is used when the shadow type for a shape is set to Page Default (ShapeShdwType cell equals \*\* visFSTPageDefault \*\* ).</span></span> 
  
<span data-ttu-id="4588b-110">若要为单个形状设置此行为，请使用“Fill Format”内容中的 ShapeShdwScaleFactor 单元格。</span><span class="sxs-lookup"><span data-stu-id="4588b-110">To set this behavior for an individual shape, use the ShapeShdwScaleFactor cell in the Fill Format section.</span></span>
  
<span data-ttu-id="4588b-111">此值对应于 **“页面设置”** 对话框（在 **“设计”** 选项卡上，单击 **“页面设计”** 箭头）中 **“阴影”** 选项卡上的 **“缩放”** 框中的值。</span><span class="sxs-lookup"><span data-stu-id="4588b-111">This value corresponds to the value in the **Magnification** box on the **Shadows** tab in the **Page Setup** dialog box (on the **Design** tab, click the **Page Setup** arrow).</span></span> 
  
<span data-ttu-id="4588b-112">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 ShdwScaleFactor 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="4588b-112">To get a reference to the ShdwScaleFactor cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="4588b-113">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="4588b-113">Cell name:</span></span>  <br/> | <span data-ttu-id="4588b-114">ShdwScaleFactor</span><span class="sxs-lookup"><span data-stu-id="4588b-114">ShdwScaleFactor</span></span>  <br/> |
   
<span data-ttu-id="4588b-115">若要从某个程序按索引获取对 ShdwScaleFactor 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="4588b-115">To get a reference to the ShdwScaleFactor cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="4588b-116">内容索引：</span><span class="sxs-lookup"><span data-stu-id="4588b-116">Section index:</span></span>  <br/> |<span data-ttu-id="4588b-117">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="4588b-117">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="4588b-118">行索引：</span><span class="sxs-lookup"><span data-stu-id="4588b-118">Row index:</span></span>  <br/> |<span data-ttu-id="4588b-119">**visRowPage**</span><span class="sxs-lookup"><span data-stu-id="4588b-119">**visRowPage**</span></span> <br/> |
| <span data-ttu-id="4588b-120">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="4588b-120">Cell index:</span></span>  <br/> |<span data-ttu-id="4588b-121">**visPageShdwScaleFactor**</span><span class="sxs-lookup"><span data-stu-id="4588b-121">**visPageShdwScaleFactor**</span></span> <br/> |
   

