---
title: Sharpen 单元格（“Image Properties”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm910
localization_priority: Normal
ms.assetid: aa2bebfc-a6bb-a6b3-3ae9-8553f96b5738
description: 锐化位图图像。默认值是 0%。通过增加相邻像素的对比度来锐化图像可以使图像更鲜明。
ms.openlocfilehash: fbc66f8c88cde67ad1f259f8392f6d3bd0457be7
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781314"
---
# <a name="sharpen-cell-image-properties-section"></a><span data-ttu-id="fc36d-105">Sharpen 单元格（“Image Properties”部分）</span><span class="sxs-lookup"><span data-stu-id="fc36d-105">Sharpen Cell (Image Properties Section)</span></span>

<span data-ttu-id="fc36d-p102">锐化位图图像。默认值是 0%。通过增加相邻像素的对比度来锐化图像可以使图像更鲜明。</span><span class="sxs-lookup"><span data-stu-id="fc36d-p102">Sharpens a bitmap image. The default value is 0%. Sharpening an image focuses it by increasing the contrast of adjacent pixels.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="fc36d-109">注释</span><span class="sxs-lookup"><span data-stu-id="fc36d-109">Remarks</span></span>

<span data-ttu-id="fc36d-110">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 Sharpen 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="fc36d-110">To get a reference to the Sharpen cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="fc36d-111">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="fc36d-111">Cell name:</span></span>  <br/> | <span data-ttu-id="fc36d-112">Sharpen</span><span class="sxs-lookup"><span data-stu-id="fc36d-112">Sharpen</span></span>  <br/> |
   
<span data-ttu-id="fc36d-113">要从某个程序按索引获取对 Sharpen 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="fc36d-113">To get a reference to the Sharpen cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="fc36d-114">内容索引：</span><span class="sxs-lookup"><span data-stu-id="fc36d-114">Section index:</span></span>  <br/> |<span data-ttu-id="fc36d-115">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="fc36d-115">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="fc36d-116">行索引：</span><span class="sxs-lookup"><span data-stu-id="fc36d-116">Row index:</span></span>  <br/> |<span data-ttu-id="fc36d-117">**visRowImage**</span><span class="sxs-lookup"><span data-stu-id="fc36d-117">**visRowImage**</span></span> <br/> |
| <span data-ttu-id="fc36d-118">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="fc36d-118">Cell index:</span></span>  <br/> |<span data-ttu-id="fc36d-119">**visImageSharpen**</span><span class="sxs-lookup"><span data-stu-id="fc36d-119">**visImageSharpen**</span></span> <br/> |
   

