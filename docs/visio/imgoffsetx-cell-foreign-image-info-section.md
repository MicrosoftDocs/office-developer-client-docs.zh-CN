---
title: ImgOffsetX 单元格（“Foreign Image Info”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251308
localization_priority: Normal
ms.assetid: c079fb10-4db7-4657-75d2-2fb953c86670
description: 确定对象水平偏离对象边框的原点的距离。 默认值为 0。 使用“剪裁”工具扫视对象将更改该值。
ms.openlocfilehash: d9b3e97a07bc1cadc0276905c4199861ab0590ca
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33405231"
---
# <a name="imgoffsetx-cell-foreign-image-info-section"></a><span data-ttu-id="e6b57-105">ImgOffsetX 单元格（“Foreign Image Info”内容）</span><span class="sxs-lookup"><span data-stu-id="e6b57-105">ImgOffsetX Cell (Foreign Image Info Section)</span></span>

<span data-ttu-id="e6b57-p102">确定对象水平偏离对象边框的原点的距离。默认值为 0。使用 **“剪裁”** 工具扫视对象将更改该值。</span><span class="sxs-lookup"><span data-stu-id="e6b57-p102">Determines the distance the object is offset horizontally from the origin of the object's border. The default is 0. Panning the object with the **Crop** tool changes this value.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="e6b57-109">说明</span><span class="sxs-lookup"><span data-stu-id="e6b57-109">Remarks</span></span>

<span data-ttu-id="e6b57-110">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 ImgOffsetX 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="e6b57-110">To get a reference to the ImgOffsetX cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="e6b57-111">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="e6b57-111">Cell name:</span></span>  <br/> | <span data-ttu-id="e6b57-112">ImgOffsetX</span><span class="sxs-lookup"><span data-stu-id="e6b57-112">ImgOffsetX</span></span>  <br/> |
   
<span data-ttu-id="e6b57-113">要从某个程序按索引获取对 ImgOffsetX 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="e6b57-113">To get a reference to the ImgOffsetX cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="e6b57-114">内容索引：</span><span class="sxs-lookup"><span data-stu-id="e6b57-114">Section index:</span></span>  <br/> |<span data-ttu-id="e6b57-115">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="e6b57-115">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="e6b57-116">行索引：</span><span class="sxs-lookup"><span data-stu-id="e6b57-116">Row index:</span></span>  <br/> |<span data-ttu-id="e6b57-117">**visRowForeign**</span><span class="sxs-lookup"><span data-stu-id="e6b57-117">**visRowForeign**</span></span> <br/> |
| <span data-ttu-id="e6b57-118">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="e6b57-118">Cell index:</span></span>  <br/> |<span data-ttu-id="e6b57-119">**visFrgnImgOffsetX**</span><span class="sxs-lookup"><span data-stu-id="e6b57-119">**visFrgnImgOffsetX**</span></span> <br/> |
   

