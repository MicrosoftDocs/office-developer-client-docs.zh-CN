---
title: Denoise 单元格（“Image Properties”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm225
localization_priority: Normal
ms.assetid: e305585f-f0d8-0494-91d4-0c76929dc170
description: 删除位图图像中的杂色（颜色级别随机分布的像素）。默认值是 0%。
ms.openlocfilehash: f08d09126a24935c0dd4dcda5e88fdd559c8d176
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780097"
---
# <a name="denoise-cell-image-properties-section"></a><span data-ttu-id="599e7-104">Denoise 单元格（“Image Properties”部分）</span><span class="sxs-lookup"><span data-stu-id="599e7-104">Denoise Cell (Image Properties Section)</span></span>

<span data-ttu-id="599e7-p102">删除位图图像中的杂色（颜色级别随机分布的像素）。默认值是 0%。</span><span class="sxs-lookup"><span data-stu-id="599e7-p102">Removes noise (pixels with randomly distributed color levels) from a bitmap image. The default value is 0%.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="599e7-107">注释</span><span class="sxs-lookup"><span data-stu-id="599e7-107">Remarks</span></span>

<span data-ttu-id="599e7-108">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 Denoise 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="599e7-108">To get a reference to the Denoise cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="599e7-109">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="599e7-109">Cell name:</span></span>  <br/> | <span data-ttu-id="599e7-110">Denoise</span><span class="sxs-lookup"><span data-stu-id="599e7-110">Denoise</span></span>  <br/> |
   
<span data-ttu-id="599e7-111">要从某个程序按索引获取对 Denoise 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="599e7-111">To get a reference to the Denoise cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="599e7-112">内容索引：</span><span class="sxs-lookup"><span data-stu-id="599e7-112">Section index:</span></span>  <br/> |<span data-ttu-id="599e7-113">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="599e7-113">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="599e7-114">行索引：</span><span class="sxs-lookup"><span data-stu-id="599e7-114">Row index:</span></span>  <br/> |<span data-ttu-id="599e7-115">**visRowImage**</span><span class="sxs-lookup"><span data-stu-id="599e7-115">**visRowImage**</span></span> <br/> |
| <span data-ttu-id="599e7-116">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="599e7-116">Cell index:</span></span>  <br/> |<span data-ttu-id="599e7-117">**visImageDenoise**</span><span class="sxs-lookup"><span data-stu-id="599e7-117">**visImageDenoise**</span></span> <br/> |
   

