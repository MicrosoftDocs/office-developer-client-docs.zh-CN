---
title: CompoundType 单元格 ("Line Format" 内容)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 3e2a88ad-d92c-4550-8da3-fa7fdd032e73
description: 确定形状的线条的复合类型。
ms.openlocfilehash: 120975e419656234266cb8151b2fa37ef19602e5
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32359365"
---
# <a name="compoundtype-cell-line-format-section"></a><span data-ttu-id="e09a0-103">CompoundType 单元格 ("Line Format" 内容)</span><span class="sxs-lookup"><span data-stu-id="e09a0-103">CompoundType Cell (Line Format Section)</span></span>

<span data-ttu-id="e09a0-104">确定形状的线条的复合类型。</span><span class="sxs-lookup"><span data-stu-id="e09a0-104">Determines the compound type of the line of a shape.</span></span> 
  
|<span data-ttu-id="e09a0-105">**Value**</span><span class="sxs-lookup"><span data-stu-id="e09a0-105">**Value**</span></span>|<span data-ttu-id="e09a0-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="e09a0-106">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e09a0-107">0</span><span class="sxs-lookup"><span data-stu-id="e09a0-107">0</span></span>  <br/> |<span data-ttu-id="e09a0-108">简单</span><span class="sxs-lookup"><span data-stu-id="e09a0-108">Simple</span></span>  <br/> |
|<span data-ttu-id="e09a0-109">1</span><span class="sxs-lookup"><span data-stu-id="e09a0-109">1</span></span>  <br/> |<span data-ttu-id="e09a0-110">双精度</span><span class="sxs-lookup"><span data-stu-id="e09a0-110">Double</span></span>  <br/> |
|<span data-ttu-id="e09a0-111">双面</span><span class="sxs-lookup"><span data-stu-id="e09a0-111">2</span></span>  <br/> |<span data-ttu-id="e09a0-112">粗细</span><span class="sxs-lookup"><span data-stu-id="e09a0-112">Thick thin</span></span>  <br/> |
|<span data-ttu-id="e09a0-113">第三章</span><span class="sxs-lookup"><span data-stu-id="e09a0-113">3</span></span>  <br/> |<span data-ttu-id="e09a0-114">细厚</span><span class="sxs-lookup"><span data-stu-id="e09a0-114">Thin thick</span></span>  <br/> |
|<span data-ttu-id="e09a0-115">4</span><span class="sxs-lookup"><span data-stu-id="e09a0-115">4</span></span>  <br/> |<span data-ttu-id="e09a0-116">Triple</span><span class="sxs-lookup"><span data-stu-id="e09a0-116">Triple</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="e09a0-117">注解</span><span class="sxs-lookup"><span data-stu-id="e09a0-117">Remarks</span></span>

<span data-ttu-id="e09a0-118">若要从另一个公式按名称获取对**CompoundType**单元格的引用、 **cell**元素的**N**属性值, 或从使用**CellsU**属性的某个程序获取对该单元格的引用, 请使用:</span><span class="sxs-lookup"><span data-stu-id="e09a0-118">To get a reference to the **CompoundType** cell by name from another formula, by value of the **N** attribute of a **Cell** element, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="e09a0-119">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="e09a0-119">Cell name:</span></span>  <br/> | <span data-ttu-id="e09a0-120">CompoundType</span><span class="sxs-lookup"><span data-stu-id="e09a0-120">CompoundType</span></span>  <br/> |
   
<span data-ttu-id="e09a0-121">若要从某个程序按索引获取对**CompoundType**单元格的引用, 请使用带下列参数的**CellsSRC**属性:</span><span class="sxs-lookup"><span data-stu-id="e09a0-121">To get a reference to the **CompoundType** cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="e09a0-122">内容索引：</span><span class="sxs-lookup"><span data-stu-id="e09a0-122">Section index:</span></span>  <br/> |<span data-ttu-id="e09a0-123">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="e09a0-123">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="e09a0-124">行索引：</span><span class="sxs-lookup"><span data-stu-id="e09a0-124">Row index:</span></span>  <br/> |<span data-ttu-id="e09a0-125">**visRowLine**</span><span class="sxs-lookup"><span data-stu-id="e09a0-125">**visRowLine**</span></span> <br/> |
| <span data-ttu-id="e09a0-126">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="e09a0-126">Cell index:</span></span>  <br/> |<span data-ttu-id="e09a0-127">**visCompoundType**</span><span class="sxs-lookup"><span data-stu-id="e09a0-127">**visCompoundType**</span></span> <br/> |
   

