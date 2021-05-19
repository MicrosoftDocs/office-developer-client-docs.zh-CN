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
ms.openlocfilehash: e519cf6e5a168b64b4bc8aa083843163a47525ba
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33415920"
---
# <a name="sharpen-cell-image-properties-section"></a><span data-ttu-id="a5afc-105">Sharpen 单元格（“Image Properties”内容）</span><span class="sxs-lookup"><span data-stu-id="a5afc-105">Sharpen Cell (Image Properties Section)</span></span>

<span data-ttu-id="a5afc-p102">锐化位图图像。默认值是 0%。通过增加相邻像素的对比度来锐化图像可以使图像更鲜明。</span><span class="sxs-lookup"><span data-stu-id="a5afc-p102">Sharpens a bitmap image. The default value is 0%. Sharpening an image focuses it by increasing the contrast of adjacent pixels.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="a5afc-109">备注</span><span class="sxs-lookup"><span data-stu-id="a5afc-109">Remarks</span></span>

<span data-ttu-id="a5afc-110">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 Sharpen 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="a5afc-110">To get a reference to the Sharpen cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="a5afc-111">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="a5afc-111">Cell name:</span></span>  <br/> | <span data-ttu-id="a5afc-112">Sharpen</span><span class="sxs-lookup"><span data-stu-id="a5afc-112">Sharpen</span></span>  <br/> |
   
<span data-ttu-id="a5afc-113">要从某个程序按索引获取对 Sharpen 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="a5afc-113">To get a reference to the Sharpen cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="a5afc-114">内容索引：</span><span class="sxs-lookup"><span data-stu-id="a5afc-114">Section index:</span></span>  <br/> |<span data-ttu-id="a5afc-115">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="a5afc-115">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="a5afc-116">行索引：</span><span class="sxs-lookup"><span data-stu-id="a5afc-116">Row index:</span></span>  <br/> |<span data-ttu-id="a5afc-117">**visRowImage**</span><span class="sxs-lookup"><span data-stu-id="a5afc-117">**visRowImage**</span></span> <br/> |
| <span data-ttu-id="a5afc-118">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="a5afc-118">Cell index:</span></span>  <br/> |<span data-ttu-id="a5afc-119">**visImageSharpen**</span><span class="sxs-lookup"><span data-stu-id="a5afc-119">**visImageSharpen**</span></span> <br/> |
   

