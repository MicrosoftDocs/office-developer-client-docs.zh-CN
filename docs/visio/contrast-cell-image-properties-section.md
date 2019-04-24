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
ms.openlocfilehash: f0a27090ea1ec96bf11726ae641ff918dd581e2f
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32319017"
---
# <a name="contrast-cell-image-properties-section"></a><span data-ttu-id="62c62-105">Contrast 单元格（“Image Properties”内容）</span><span class="sxs-lookup"><span data-stu-id="62c62-105">Contrast Cell (Image Properties Section)</span></span>

<span data-ttu-id="62c62-p102">调整位图图像的对比度。输入 0% 到 49% 之间的值，可以减小图像的对比度；输入 51% 到 100% 之间的值，可以增加图像的对比度。默认值是 50%。</span><span class="sxs-lookup"><span data-stu-id="62c62-p102">Adjusts the contrast of a bitmap image. Decrease the contrast of an image by entering a value between 0% and 49%, or increase the contrast by entering a value between 51% and 100%. The default value is 50%.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="62c62-109">注解</span><span class="sxs-lookup"><span data-stu-id="62c62-109">Remarks</span></span>

<span data-ttu-id="62c62-110">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 Contrast 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="62c62-110">To get a reference to the Contrast cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="62c62-111">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="62c62-111">Cell name:</span></span>  <br/> | <span data-ttu-id="62c62-112">对比度</span><span class="sxs-lookup"><span data-stu-id="62c62-112">Contrast</span></span>  <br/> |
   
<span data-ttu-id="62c62-113">要从某个程序按索引获取对 Contrast 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="62c62-113">To get a reference to the Contrast cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="62c62-114">内容索引：</span><span class="sxs-lookup"><span data-stu-id="62c62-114">Section index:</span></span>  <br/> |<span data-ttu-id="62c62-115">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="62c62-115">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="62c62-116">行索引：</span><span class="sxs-lookup"><span data-stu-id="62c62-116">Row index:</span></span>  <br/> |<span data-ttu-id="62c62-117">**visRowImage**</span><span class="sxs-lookup"><span data-stu-id="62c62-117">**visRowImage**</span></span> <br/> |
| <span data-ttu-id="62c62-118">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="62c62-118">Cell index:</span></span>  <br/> |<span data-ttu-id="62c62-119">**visImageContrast**</span><span class="sxs-lookup"><span data-stu-id="62c62-119">**visImageContrast**</span></span> <br/> |
   

