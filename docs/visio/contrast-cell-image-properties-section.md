---
title: Contrast 单元格（“Image Properties”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm200
localization_priority: Normal
ms.assetid: f0e4c644-c646-9649-c697-82feb02f5e29
description: 调整位图图像的对比度。输入 0% 到 49% 之间的值，可以减小图像的对比度；输入 51% 到 100% 之间的值，可以增加图像的对比度。默认值是 50%。
ms.openlocfilehash: 74a82fd9be49fcb9126c2b52bfcf25e0deb0e782
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779981"
---
# <a name="contrast-cell-image-properties-section"></a><span data-ttu-id="b6ce9-105">Contrast 单元格（“Image Properties”部分）</span><span class="sxs-lookup"><span data-stu-id="b6ce9-105">Contrast Cell (Image Properties Section)</span></span>

<span data-ttu-id="b6ce9-p102">调整位图图像的对比度。输入 0% 到 49% 之间的值，可以减小图像的对比度；输入 51% 到 100% 之间的值，可以增加图像的对比度。默认值是 50%。</span><span class="sxs-lookup"><span data-stu-id="b6ce9-p102">Adjusts the contrast of a bitmap image. Decrease the contrast of an image by entering a value between 0% and 49%, or increase the contrast by entering a value between 51% and 100%. The default value is 50%.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="b6ce9-109">注释</span><span class="sxs-lookup"><span data-stu-id="b6ce9-109">Remarks</span></span>

<span data-ttu-id="b6ce9-110">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 Contrast 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="b6ce9-110">To get a reference to the Contrast cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="b6ce9-111">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="b6ce9-111">Cell name:</span></span>  <br/> | <span data-ttu-id="b6ce9-112">Contrast</span><span class="sxs-lookup"><span data-stu-id="b6ce9-112">Contrast</span></span>  <br/> |
   
<span data-ttu-id="b6ce9-113">要从某个程序按索引获取对 Contrast 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="b6ce9-113">To get a reference to the Contrast cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="b6ce9-114">内容索引：</span><span class="sxs-lookup"><span data-stu-id="b6ce9-114">Section index:</span></span>  <br/> |<span data-ttu-id="b6ce9-115">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="b6ce9-115">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="b6ce9-116">行索引：</span><span class="sxs-lookup"><span data-stu-id="b6ce9-116">Row index:</span></span>  <br/> |<span data-ttu-id="b6ce9-117">**visRowImage**</span><span class="sxs-lookup"><span data-stu-id="b6ce9-117">**visRowImage**</span></span> <br/> |
| <span data-ttu-id="b6ce9-118">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="b6ce9-118">Cell index:</span></span>  <br/> |<span data-ttu-id="b6ce9-119">**visImageContrast**</span><span class="sxs-lookup"><span data-stu-id="b6ce9-119">**visImageContrast**</span></span> <br/> |
   

