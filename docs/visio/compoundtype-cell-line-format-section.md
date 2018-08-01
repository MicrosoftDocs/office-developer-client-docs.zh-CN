---
title: CompoundType 单元格（“Line Format”部分）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 3e2a88ad-d92c-4550-8da3-fa7fdd032e73
description: 确定形状的行的复合类型。
ms.openlocfilehash: 663b683030251c8b57324f1d2bdf492463c50eef
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779923"
---
# <a name="compoundtype-cell-line-format-section"></a><span data-ttu-id="51dcd-103">CompoundType 单元格（“Line Format”部分）</span><span class="sxs-lookup"><span data-stu-id="51dcd-103">CompoundType Cell (Line Format Section)</span></span>

<span data-ttu-id="51dcd-104">确定形状的行的复合类型。</span><span class="sxs-lookup"><span data-stu-id="51dcd-104">Determines the compound type of the line of a shape.</span></span> 
  
|<span data-ttu-id="51dcd-105">**值**</span><span class="sxs-lookup"><span data-stu-id="51dcd-105">**Value**</span></span>|<span data-ttu-id="51dcd-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="51dcd-106">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="51dcd-107">0</span><span class="sxs-lookup"><span data-stu-id="51dcd-107">0</span></span>  <br/> |<span data-ttu-id="51dcd-108">简单</span><span class="sxs-lookup"><span data-stu-id="51dcd-108">Simple</span></span>  <br/> |
|<span data-ttu-id="51dcd-109">1</span><span class="sxs-lookup"><span data-stu-id="51dcd-109">1</span></span>  <br/> |<span data-ttu-id="51dcd-110">双精度数</span><span class="sxs-lookup"><span data-stu-id="51dcd-110">Double</span></span>  <br/> |
|<span data-ttu-id="51dcd-111">2</span><span class="sxs-lookup"><span data-stu-id="51dcd-111">2</span></span>  <br/> |<span data-ttu-id="51dcd-112">Thick 细</span><span class="sxs-lookup"><span data-stu-id="51dcd-112">Thick thin</span></span>  <br/> |
|<span data-ttu-id="51dcd-113">3</span><span class="sxs-lookup"><span data-stu-id="51dcd-113">3</span></span>  <br/> |<span data-ttu-id="51dcd-114">细粗</span><span class="sxs-lookup"><span data-stu-id="51dcd-114">Thin thick</span></span>  <br/> |
|<span data-ttu-id="51dcd-115">4</span><span class="sxs-lookup"><span data-stu-id="51dcd-115">4</span></span>  <br/> |<span data-ttu-id="51dcd-116">Triple</span><span class="sxs-lookup"><span data-stu-id="51dcd-116">Triple</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="51dcd-117">说明</span><span class="sxs-lookup"><span data-stu-id="51dcd-117">Remarks</span></span>

<span data-ttu-id="51dcd-118">要从另一个公式，由**N** **单元格**元素的属性的值或使用**CellsU**属性从某个程序按名称获取对**CompoundType**单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="51dcd-118">To get a reference to the **CompoundType** cell by name from another formula, by value of the **N** attribute of a **Cell** element, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="51dcd-119">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="51dcd-119">Cell name:</span></span>  <br/> | <span data-ttu-id="51dcd-120">CompoundType</span><span class="sxs-lookup"><span data-stu-id="51dcd-120">CompoundType</span></span>  <br/> |
   
<span data-ttu-id="51dcd-121">若要从某个程序按索引获取对**CompoundType**单元格的引用，请使用带下列参数的**CellsSRC**属性：</span><span class="sxs-lookup"><span data-stu-id="51dcd-121">To get a reference to the **CompoundType** cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="51dcd-122">内容索引：</span><span class="sxs-lookup"><span data-stu-id="51dcd-122">Section index:</span></span>  <br/> |<span data-ttu-id="51dcd-123">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="51dcd-123">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="51dcd-124">行索引：</span><span class="sxs-lookup"><span data-stu-id="51dcd-124">Row index:</span></span>  <br/> |<span data-ttu-id="51dcd-125">**visRowLine**</span><span class="sxs-lookup"><span data-stu-id="51dcd-125">**visRowLine**</span></span> <br/> |
| <span data-ttu-id="51dcd-126">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="51dcd-126">Cell index:</span></span>  <br/> |<span data-ttu-id="51dcd-127">**visCompoundType**</span><span class="sxs-lookup"><span data-stu-id="51dcd-127">**visCompoundType**</span></span> <br/> |
   

