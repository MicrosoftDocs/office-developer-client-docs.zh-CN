---
title: FlipY 单元格（“Shape Transform”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251198
localization_priority: Normal
ms.assetid: 062022ff-e243-2540-becd-d9b969ce83ce
description: 指出形状是否已经垂直翻转。
ms.openlocfilehash: 44ea0341cda3655e8acc69e82e89acddac69b80d
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33417446"
---
# <a name="flipy-cell-shape-transform-section"></a><span data-ttu-id="8dea2-103">FlipY 单元格（“Shape Transform”内容）</span><span class="sxs-lookup"><span data-stu-id="8dea2-103">FlipY Cell (Shape Transform Section)</span></span>

<span data-ttu-id="8dea2-104">指出形状是否已经垂直翻转。</span><span class="sxs-lookup"><span data-stu-id="8dea2-104">Indicates whether the shape has been flipped vertically.</span></span>
  
|<span data-ttu-id="8dea2-105">**值**</span><span class="sxs-lookup"><span data-stu-id="8dea2-105">**Value**</span></span>|<span data-ttu-id="8dea2-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="8dea2-106">**Description**</span></span>|
|:-----|:-----|
| <span data-ttu-id="8dea2-107">TRUE</span><span class="sxs-lookup"><span data-stu-id="8dea2-107">TRUE</span></span>  <br/> | <span data-ttu-id="8dea2-108">形状已经垂直翻转。</span><span class="sxs-lookup"><span data-stu-id="8dea2-108">The shape has been flipped vertically.</span></span>  <br/> |
| <span data-ttu-id="8dea2-109">FALSE</span><span class="sxs-lookup"><span data-stu-id="8dea2-109">FALSE</span></span>  <br/> | <span data-ttu-id="8dea2-110">形状尚未垂直翻转。</span><span class="sxs-lookup"><span data-stu-id="8dea2-110">The shape has not been flipped vertically.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="8dea2-111">备注</span><span class="sxs-lookup"><span data-stu-id="8dea2-111">Remarks</span></span>

<span data-ttu-id="8dea2-112">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 FlipY 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="8dea2-112">To get a reference to the FlipY cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="8dea2-113">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="8dea2-113">Cell name:</span></span>  <br/> | <span data-ttu-id="8dea2-114">FlipY</span><span class="sxs-lookup"><span data-stu-id="8dea2-114">FlipY</span></span>  <br/> |
   
<span data-ttu-id="8dea2-115">要从某个程序按索引获取对 FlipY 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="8dea2-115">To get a reference to the FlipY cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="8dea2-116">内容索引：</span><span class="sxs-lookup"><span data-stu-id="8dea2-116">Section index:</span></span>  <br/> |<span data-ttu-id="8dea2-117">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="8dea2-117">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="8dea2-118">行索引：</span><span class="sxs-lookup"><span data-stu-id="8dea2-118">Row index:</span></span>  <br/> |<span data-ttu-id="8dea2-119">**visRowXFormOut**</span><span class="sxs-lookup"><span data-stu-id="8dea2-119">**visRowXFormOut**</span></span> <br/> |
| <span data-ttu-id="8dea2-120">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="8dea2-120">Cell index:</span></span>  <br/> |<span data-ttu-id="8dea2-121">**visXFormFlipY**</span><span class="sxs-lookup"><span data-stu-id="8dea2-121">**visXFormFlipY**</span></span> <br/> |
   

