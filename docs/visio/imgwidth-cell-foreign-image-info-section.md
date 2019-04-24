---
title: ImgWidth 单元格（“Foreign Image Info”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm460
localization_priority: Normal
ms.assetid: b57fb962-0b3e-f2e5-3b88-3edf33e40496
description: 确定对象的图像在其边框内的宽度。 默认公式为：
ms.openlocfilehash: 9da5e06a7fbf6ae77a49fb0410aefb406e2afecb
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32344721"
---
# <a name="imgwidth-cell-foreign-image-info-section"></a><span data-ttu-id="a3fcf-104">ImgWidth 单元格（“Foreign Image Info”内容）</span><span class="sxs-lookup"><span data-stu-id="a3fcf-104">ImgWidth Cell (Foreign Image Info Section)</span></span>

<span data-ttu-id="a3fcf-105">确定对象的图像在其边框内的宽度。</span><span class="sxs-lookup"><span data-stu-id="a3fcf-105">Determines the width of the object's image within its border.</span></span> <span data-ttu-id="a3fcf-106">默认公式为：</span><span class="sxs-lookup"><span data-stu-id="a3fcf-106">The default formula is:</span></span>
  
<span data-ttu-id="a3fcf-107">= Width \* 1</span><span class="sxs-lookup"><span data-stu-id="a3fcf-107">= Width \* 1</span></span>
  
<span data-ttu-id="a3fcf-108">剪裁对象将更改与 Width 相乘的乘数。</span><span class="sxs-lookup"><span data-stu-id="a3fcf-108">Cropping the object changes the factor by which Width is multiplied.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="a3fcf-109">注解</span><span class="sxs-lookup"><span data-stu-id="a3fcf-109">Remarks</span></span>

<span data-ttu-id="a3fcf-110">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 ImgWidth 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="a3fcf-110">To get a reference to the ImgWidth cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="a3fcf-111">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="a3fcf-111">Cell name:</span></span>  <br/> | <span data-ttu-id="a3fcf-112">ImgWidth</span><span class="sxs-lookup"><span data-stu-id="a3fcf-112">ImgWidth</span></span>  <br/> |
   
<span data-ttu-id="a3fcf-113">要从某个程序按索引获取对 ImgWidth 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="a3fcf-113">To get a reference to the ImgWidth cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="a3fcf-114">内容索引：</span><span class="sxs-lookup"><span data-stu-id="a3fcf-114">Section index:</span></span>  <br/> |<span data-ttu-id="a3fcf-115">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="a3fcf-115">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="a3fcf-116">行索引：</span><span class="sxs-lookup"><span data-stu-id="a3fcf-116">Row index:</span></span>  <br/> |<span data-ttu-id="a3fcf-117">**visRowForeign**</span><span class="sxs-lookup"><span data-stu-id="a3fcf-117">**visRowForeign**</span></span> <br/> |
| <span data-ttu-id="a3fcf-118">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="a3fcf-118">Cell index:</span></span>  <br/> |<span data-ttu-id="a3fcf-119">**visFrgnImgWidth**</span><span class="sxs-lookup"><span data-stu-id="a3fcf-119">**visFrgnImgWidth**</span></span> <br/> |
   

