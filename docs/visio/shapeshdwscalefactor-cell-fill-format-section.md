---
title: ShapeShdwScaleFactor 单元格（“Fill Format”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm1033175
localization_priority: Normal
ms.assetid: 94ec06c5-8d2f-dd27-1eed-1abaf93daba8
description: 指定形状阴影可放大或缩小的百分比。
ms.openlocfilehash: 5862b61ca1f5df25ca97bf8742b9e20bf45091a9
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32349159"
---
# <a name="shapeshdwscalefactor-cell-fill-format-section"></a><span data-ttu-id="37569-103">ShapeShdwScaleFactor 单元格（“Fill Format”内容）</span><span class="sxs-lookup"><span data-stu-id="37569-103">ShapeShdwScaleFactor Cell (Fill Format Section)</span></span>

<span data-ttu-id="37569-104">指定形状阴影可放大或缩小的百分比。</span><span class="sxs-lookup"><span data-stu-id="37569-104">Specifies the percentage by which the shadow of a shape can be enlarged or reduced.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="37569-105">注解</span><span class="sxs-lookup"><span data-stu-id="37569-105">Remarks</span></span>

<span data-ttu-id="37569-106">每个阴影都有一个阴影的固定位置, 这是阴影上与形状的旋转点相对应的点。</span><span class="sxs-lookup"><span data-stu-id="37569-106">Each shadow has a shadowed pin location, which is a point on the shadow that corresponds to the shape's pin.</span></span> <span data-ttu-id="37569-107">例如, 如果形状的旋转中心位于形状的中心, 则阴影的固定位置将成为阴影中心的点。</span><span class="sxs-lookup"><span data-stu-id="37569-107">For example, if a shape's pin is in the center of the shape, then the shadowed pin location would be the point in the center of the shadow.</span></span> <span data-ttu-id="37569-108">将 "缩放" 应用于简单阴影时, 放大率以阴影的固定位置为中心。将缩放比例应用到倾斜阴影时, 将以倾斜方向应用放大率。</span><span class="sxs-lookup"><span data-stu-id="37569-108">When applying scale to simple shadows, magnification is centered at the shadowed pin location; when applying scale to oblique shadows, magnification is applied in the oblique direction.</span></span> 
  
<span data-ttu-id="37569-109">要设置一页中所有形状的这个值，请使用“Page Properties”内容中的 ShdwScaleFactor 单元格。</span><span class="sxs-lookup"><span data-stu-id="37569-109">To set this value for all the shapes on a page, use the ShdwScaleFactor cell in the Page Properties section.</span></span>
  
<span data-ttu-id="37569-110">此值对应于 **“阴影”** 对话框（在 **“开始”** 选项卡上的 **“形状”** 组中，单击 **“阴影”**，然后单击 **“阴影选项”**）中的 **“缩放”** 设置的值。</span><span class="sxs-lookup"><span data-stu-id="37569-110">This value corresponds to the value of the **Magnification** setting in the **Shadow** dialog box (on the **Home** tab, in the **Shape** group, click **Shadow**, and then click **Shadow Options**).</span></span>
  
<span data-ttu-id="37569-111">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 ShapeShdwScaleFactor 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="37569-111">To get a reference to the ShapeShdwScaleFactor cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="37569-112">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="37569-112">Cell name:</span></span>  <br/> |<span data-ttu-id="37569-113">ShapeShdwScaleFactor</span><span class="sxs-lookup"><span data-stu-id="37569-113">ShapeShdwScaleFactor</span></span>  <br/> |
   
<span data-ttu-id="37569-114">若要从某个程序按索引获取对 ShapeShdwScaleFactor 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="37569-114">To get a reference to the ShapeShdwScaleFactor cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="37569-115">内容索引：</span><span class="sxs-lookup"><span data-stu-id="37569-115">Section index:</span></span>  <br/> |<span data-ttu-id="37569-116">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="37569-116">**visSectionObject**</span></span> <br/> |
|<span data-ttu-id="37569-117">行索引：</span><span class="sxs-lookup"><span data-stu-id="37569-117">Row index:</span></span>  <br/> |<span data-ttu-id="37569-118">**visRowFill**</span><span class="sxs-lookup"><span data-stu-id="37569-118">**visRowFill**</span></span> <br/> |
|<span data-ttu-id="37569-119">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="37569-119">Cell index:</span></span>  <br/> |<span data-ttu-id="37569-120">**visFillShdwScaleFactor**</span><span class="sxs-lookup"><span data-stu-id="37569-120">**visFillShdwScaleFactor**</span></span> <br/> |
   

