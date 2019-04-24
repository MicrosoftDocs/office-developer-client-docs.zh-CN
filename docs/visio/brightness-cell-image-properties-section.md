---
title: Brightness 单元格（“Image Properties”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251608
localization_priority: Normal
ms.assetid: 5bb1cc81-f3fd-a835-1449-233dbd1a62b6
description: 调整位图图像的亮度。输入 0% 到 49% 之间的值，可以减小图像的亮度；输入 51% 到 100% 之间的值，可以增加图像的亮度。默认值是 50%。
ms.openlocfilehash: ae1390d2db3adad86a8afcbeaff88172a841d030
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32338022"
---
# <a name="brightness-cell-image-properties-section"></a><span data-ttu-id="ab3e5-105">Brightness 单元格（“Image Properties”内容）</span><span class="sxs-lookup"><span data-stu-id="ab3e5-105">Brightness Cell (Image Properties Section)</span></span>

<span data-ttu-id="ab3e5-p102">调整位图图像的亮度。输入 0% 到 49% 之间的值，可以减小图像的亮度；输入 51% 到 100% 之间的值，可以增加图像的亮度。默认值是 50%。</span><span class="sxs-lookup"><span data-stu-id="ab3e5-p102">Adjusts the brightness of a bitmap image. Decrease brightness of an image by entering a value between 0% and 49%, or increase brightness by entering a value between 51% and 100%. The default value is 50%.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="ab3e5-109">注解</span><span class="sxs-lookup"><span data-stu-id="ab3e5-109">Remarks</span></span>

<span data-ttu-id="ab3e5-110">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 Brightness 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="ab3e5-110">To get a reference to the Brightness cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="ab3e5-111">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="ab3e5-111">Cell name:</span></span>  <br/> | <span data-ttu-id="ab3e5-112">亮度</span><span class="sxs-lookup"><span data-stu-id="ab3e5-112">Brightness</span></span>  <br/> |
   
<span data-ttu-id="ab3e5-113">要从某个程序按索引获取对 Brightness 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="ab3e5-113">To get a reference to the Brightness cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="ab3e5-114">内容索引：</span><span class="sxs-lookup"><span data-stu-id="ab3e5-114">Section index:</span></span>  <br/> |<span data-ttu-id="ab3e5-115">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="ab3e5-115">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="ab3e5-116">行索引：</span><span class="sxs-lookup"><span data-stu-id="ab3e5-116">Row index:</span></span>  <br/> |<span data-ttu-id="ab3e5-117">**visRowImage**</span><span class="sxs-lookup"><span data-stu-id="ab3e5-117">**visRowImage**</span></span> <br/> |
| <span data-ttu-id="ab3e5-118">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="ab3e5-118">Cell index:</span></span>  <br/> |<span data-ttu-id="ab3e5-119">**visImageBrightness**</span><span class="sxs-lookup"><span data-stu-id="ab3e5-119">**visImageBrightness**</span></span> <br/> |
   

