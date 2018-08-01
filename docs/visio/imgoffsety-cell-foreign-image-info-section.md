---
title: ImgOffsetY 单元格（“Foreign Image Info”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm455
localization_priority: Normal
ms.assetid: 3b2991aa-4722-fe3b-39c5-02d38c4c7efc
description: 确定对象垂直偏离对象边框的原点的距离。默认值为 0。使用“剪裁”工具扫视对象将更改该值。
ms.openlocfilehash: 2930aa092a2b776ceb0c9c4677f7e5da7f5dcdda
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780435"
---
# <a name="imgoffsety-cell-foreign-image-info-section"></a><span data-ttu-id="2726b-105">ImgOffsetY 单元格（“Foreign Image Info”部分）</span><span class="sxs-lookup"><span data-stu-id="2726b-105">ImgOffsetY Cell (Foreign Image Info Section)</span></span>

<span data-ttu-id="2726b-p102">确定对象垂直偏离对象边框的原点的距离。默认值为 0。使用 **“剪裁”** 工具扫视对象将更改该值。</span><span class="sxs-lookup"><span data-stu-id="2726b-p102">Determines the distance the object is offset vertically from the origin of the object's border. The default is 0. Panning the object with the **Crop** tool changes this value.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="2726b-109">说明</span><span class="sxs-lookup"><span data-stu-id="2726b-109">Remarks</span></span>

<span data-ttu-id="2726b-110">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 ImgOffsetY 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="2726b-110">To get a reference to the ImgOffsetY cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="2726b-111">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="2726b-111">Cell name:</span></span>  <br/> | <span data-ttu-id="2726b-112">ImgOffsetY</span><span class="sxs-lookup"><span data-stu-id="2726b-112">ImgOffsetY</span></span>  <br/> |
   
<span data-ttu-id="2726b-113">要从某个程序按索引获取对 ImgOffsetY 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="2726b-113">To get a reference to the ImgOffsetY cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="2726b-114">内容索引：</span><span class="sxs-lookup"><span data-stu-id="2726b-114">Section index:</span></span>  <br/> |<span data-ttu-id="2726b-115">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="2726b-115">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="2726b-116">行索引：</span><span class="sxs-lookup"><span data-stu-id="2726b-116">Row index:</span></span>  <br/> |<span data-ttu-id="2726b-117">**visRowForeign**</span><span class="sxs-lookup"><span data-stu-id="2726b-117">**visRowForeign**</span></span> <br/> |
| <span data-ttu-id="2726b-118">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="2726b-118">Cell index:</span></span>  <br/> |<span data-ttu-id="2726b-119">**visFrgnImgOffsetY**</span><span class="sxs-lookup"><span data-stu-id="2726b-119">**visFrgnImgOffsetY**</span></span> <br/> |
   

