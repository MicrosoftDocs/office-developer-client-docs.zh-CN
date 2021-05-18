---
title: ShapeShdwObliqueAngle 单元格（“Fill Format”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm1033174
localization_priority: Normal
ms.assetid: bad4c512-e91f-d459-d65c-a4ab725c3c14
description: 指定形状阴影倾斜方向的角度。
ms.openlocfilehash: 005415e497a4d985d3fb8ec70d62ba40d9e80c91
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33414030"
---
# <a name="shapeshdwobliqueangle-cell-fill-format-section"></a><span data-ttu-id="5343a-103">ShapeShdwObliqueAngle 单元格（“Fill Format”内容）</span><span class="sxs-lookup"><span data-stu-id="5343a-103">ShapeShdwObliqueAngle Cell (Fill Format Section)</span></span>

<span data-ttu-id="5343a-104">指定形状阴影倾斜方向的角度。</span><span class="sxs-lookup"><span data-stu-id="5343a-104">Specifies the angle of oblique direction of a shape's shadow.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="5343a-105">备注</span><span class="sxs-lookup"><span data-stu-id="5343a-105">Remarks</span></span>

<span data-ttu-id="5343a-106">此单元格中的值为零 (0) 时表示角度方向为垂直向上，并且按照顺时针度量。</span><span class="sxs-lookup"><span data-stu-id="5343a-106">A value of zero (0) in this cell indicates that the angle direction is straight up and is measured moving clockwise.</span></span>
  
<span data-ttu-id="5343a-107">此值对应于 **“阴影”** 对话框（在 **“开始”** 选项卡上的 **“形状”** 组中，单击 **“阴影”**，然后单击 **“阴影选项”**）中的 **“方向”** 设置。</span><span class="sxs-lookup"><span data-stu-id="5343a-107">This value corresponds to the value of the **Direction** setting in the **Shadow** dialog box (on the **Home** tab, in the **Shape** group, click **Shadow**, and then click **Shadow Options**).</span></span>
  
<span data-ttu-id="5343a-108">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 ShapeShdwObliqueAngle 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="5343a-108">To get a reference to the ShapeShdwObliqueAngle cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="5343a-109">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="5343a-109">Cell name:</span></span>  <br/> | <span data-ttu-id="5343a-110">ShapeShdwObliqueAngle</span><span class="sxs-lookup"><span data-stu-id="5343a-110">ShapeShdwObliqueAngle</span></span>  <br/> |
   
<span data-ttu-id="5343a-111">若要从某个程序按索引获取对 ShapeShdwObliqueAngle 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="5343a-111">To get a reference to the ShapeShdwObliqueAngle cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="5343a-112">内容索引：</span><span class="sxs-lookup"><span data-stu-id="5343a-112">Section index:</span></span>  <br/> |<span data-ttu-id="5343a-113">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="5343a-113">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="5343a-114">行索引：</span><span class="sxs-lookup"><span data-stu-id="5343a-114">Row index:</span></span>  <br/> |<span data-ttu-id="5343a-115">**visRowFill**</span><span class="sxs-lookup"><span data-stu-id="5343a-115">**visRowFill**</span></span> <br/> |
| <span data-ttu-id="5343a-116">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="5343a-116">Cell index:</span></span>  <br/> |<span data-ttu-id="5343a-117">**visFillShdwObliqueAngle**</span><span class="sxs-lookup"><span data-stu-id="5343a-117">**visFillShdwObliqueAngle**</span></span> <br/> |
   

