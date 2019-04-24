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
description: 删除位图图像中的杂色（颜色级别随机分布的像素）。 默认值是 0%。
ms.openlocfilehash: f970fde22e864239ea3f3f9bcb704e7f4692e9cc
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32360247"
---
# <a name="denoise-cell-image-properties-section"></a><span data-ttu-id="494ea-104">Denoise 单元格（“Image Properties”内容）</span><span class="sxs-lookup"><span data-stu-id="494ea-104">Denoise Cell (Image Properties Section)</span></span>

<span data-ttu-id="494ea-105">删除位图图像中的杂色（颜色级别随机分布的像素）。</span><span class="sxs-lookup"><span data-stu-id="494ea-105">Removes noise (pixels with randomly distributed color levels) from a bitmap image.</span></span> <span data-ttu-id="494ea-106">默认值是 0%。</span><span class="sxs-lookup"><span data-stu-id="494ea-106">The default value is 0%.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="494ea-107">注解</span><span class="sxs-lookup"><span data-stu-id="494ea-107">Remarks</span></span>

<span data-ttu-id="494ea-108">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 Denoise 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="494ea-108">To get a reference to the Denoise cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="494ea-109">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="494ea-109">Cell name:</span></span>  <br/> | <span data-ttu-id="494ea-110">Denoise</span><span class="sxs-lookup"><span data-stu-id="494ea-110">Denoise</span></span>  <br/> |
   
<span data-ttu-id="494ea-111">要从某个程序按索引获取对 Denoise 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="494ea-111">To get a reference to the Denoise cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="494ea-112">内容索引：</span><span class="sxs-lookup"><span data-stu-id="494ea-112">Section index:</span></span>  <br/> |<span data-ttu-id="494ea-113">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="494ea-113">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="494ea-114">行索引：</span><span class="sxs-lookup"><span data-stu-id="494ea-114">Row index:</span></span>  <br/> |<span data-ttu-id="494ea-115">**visRowImage**</span><span class="sxs-lookup"><span data-stu-id="494ea-115">**visRowImage**</span></span> <br/> |
| <span data-ttu-id="494ea-116">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="494ea-116">Cell index:</span></span>  <br/> |<span data-ttu-id="494ea-117">**visImageDenoise**</span><span class="sxs-lookup"><span data-stu-id="494ea-117">**visImageDenoise**</span></span> <br/> |
   

