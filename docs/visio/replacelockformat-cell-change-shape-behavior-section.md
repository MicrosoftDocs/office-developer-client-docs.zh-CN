---
title: ReplaceLockFormat 单元格（“Change Shape Behavior”部分）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 6973e2e6-7e7f-48ba-95b3-37c959f6ffb1
description: 指示在主控形状中的指定单元格的值是否覆盖形状替换操作期间要替换的形状 （包括本地值） 的值。 如果主控形状的 ReplaceLockFormat 单元格设置为 TRUE (1)，主控形状的格式值覆盖由主控形状的形状的所有相应值。
ms.openlocfilehash: bf1e28353cc1e2d737a7d7a6dcd90caf14e19dc8
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781071"
---
# <a name="replacelockformat-cell-change-shape-behavior-section"></a><span data-ttu-id="8c8e4-104">ReplaceLockFormat 单元格（“Change Shape Behavior”部分）</span><span class="sxs-lookup"><span data-stu-id="8c8e4-104">ReplaceLockFormat Cell (Change Shape Behavior Section)</span></span>

<span data-ttu-id="8c8e4-105">指示在主控形状中的指定单元格的值是否覆盖形状替换操作期间要替换的形状 （包括本地值） 的值。</span><span class="sxs-lookup"><span data-stu-id="8c8e4-105">Indicates whether the values of specified cells in a master shape overwrite the values (including local values) of a shape being replaced during a shape replacement operation.</span></span> <span data-ttu-id="8c8e4-106">如果主控形状的**ReplaceLockFormat**单元格设置为 TRUE (1)，主控形状的格式值覆盖由主控形状的形状的所有相应值。</span><span class="sxs-lookup"><span data-stu-id="8c8e4-106">If the **ReplaceLockFormat** cell of a master shape is set to TRUE (1), the formatting values of the master overwrite all corresponding values of a shape being replaced by the master.</span></span> 
  
|<span data-ttu-id="8c8e4-107">**值**</span><span class="sxs-lookup"><span data-stu-id="8c8e4-107">**Value**</span></span>|<span data-ttu-id="8c8e4-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="8c8e4-108">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="8c8e4-109">TRUE</span><span class="sxs-lookup"><span data-stu-id="8c8e4-109">TRUE</span></span>  <br/> |<span data-ttu-id="8c8e4-110">如果主控形状的**ReplaceLockFormat**单元格设置为 TRUE，主控形状的格式值覆盖由主控形状的形状的所有相应值。</span><span class="sxs-lookup"><span data-stu-id="8c8e4-110">If the **ReplaceLockFormat** cell of a master shape is set to TRUE, the formatting values of the master overwrite all corresponding values of a shape being replaced by the master.</span></span>  <br/> |
|<span data-ttu-id="8c8e4-111">FALSE</span><span class="sxs-lookup"><span data-stu-id="8c8e4-111">FALSE</span></span>  <br/> |<span data-ttu-id="8c8e4-112">如果主控形状的**ReplaceLockFormat**单元格设置为 FALSE，替换形状在替换操作后包含旧的形状的本地格式值。</span><span class="sxs-lookup"><span data-stu-id="8c8e4-112">If the **ReplaceLockFormat** cell of a master shape is set to FALSE, the replacement shape contains the local formatting values from the old shape after the replacement operation.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="8c8e4-113">说明</span><span class="sxs-lookup"><span data-stu-id="8c8e4-113">Remarks</span></span>

<span data-ttu-id="8c8e4-114">**ReplaceLockFormat**单元格确定主控形状是否覆盖形状替换操作过程中的以下各节中的单元格的本地格式值：</span><span class="sxs-lookup"><span data-stu-id="8c8e4-114">The **ReplaceLockFormat** cell determines whether the master shape overwrites the local formatting values of the cells in the following sections during a shape replacement operation:</span></span> 
  
- <span data-ttu-id="8c8e4-115">**填充格式**部分</span><span class="sxs-lookup"><span data-stu-id="8c8e4-115">**Fill Format** section</span></span> 
    
- <span data-ttu-id="8c8e4-116">**行格式**部分</span><span class="sxs-lookup"><span data-stu-id="8c8e4-116">**Line Format** section</span></span> 
    
- <span data-ttu-id="8c8e4-117">**快速样式**部分</span><span class="sxs-lookup"><span data-stu-id="8c8e4-117">**Quick Style** section</span></span> 
    
- <span data-ttu-id="8c8e4-118">**主题属性**部分</span><span class="sxs-lookup"><span data-stu-id="8c8e4-118">**Theme Properties** section</span></span> 
    
- <span data-ttu-id="8c8e4-119">**渐变**properties</span><span class="sxs-lookup"><span data-stu-id="8c8e4-119">**Gradient Properties** section</span></span> 
    
- <span data-ttu-id="8c8e4-120">**凹凸效果属性**部分</span><span class="sxs-lookup"><span data-stu-id="8c8e4-120">**Bevel Properties** section</span></span> 
    
- <span data-ttu-id="8c8e4-121">**其他效果属性**部分</span><span class="sxs-lookup"><span data-stu-id="8c8e4-121">**Additional Effect Properties** section</span></span> 
    
- <span data-ttu-id="8c8e4-122">**行渐变光圈**部分</span><span class="sxs-lookup"><span data-stu-id="8c8e4-122">**Line Gradient Stops** section</span></span> 
    
- <span data-ttu-id="8c8e4-123">**填充的渐变光圈**部分</span><span class="sxs-lookup"><span data-stu-id="8c8e4-123">**Fill Gradient Stops** section</span></span> 
    
<span data-ttu-id="8c8e4-124">要从另一个公式，由**N** **单元格**元素的属性的值或使用**CellsU**属性从某个程序按名称获取对**ReplaceLockFormat**单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="8c8e4-124">To get a reference to the **ReplaceLockFormat** cell by name from another formula, by value of the **N** attribute of a **Cell** element, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="8c8e4-125">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="8c8e4-125">Cell name:</span></span>  <br/> | <span data-ttu-id="8c8e4-126">ReplaceLockFormat</span><span class="sxs-lookup"><span data-stu-id="8c8e4-126">ReplaceLockFormat</span></span>  <br/> |
   
<span data-ttu-id="8c8e4-127">若要从某个程序按索引获取对**ReplaceLockFormat**单元格的引用，请使用带下列参数的**CellsSRC**属性：</span><span class="sxs-lookup"><span data-stu-id="8c8e4-127">To get a reference to the **ReplaceLockFormat** cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="8c8e4-128">内容索引：</span><span class="sxs-lookup"><span data-stu-id="8c8e4-128">Section index:</span></span>  <br/> |<span data-ttu-id="8c8e4-129">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="8c8e4-129">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="8c8e4-130">行索引：</span><span class="sxs-lookup"><span data-stu-id="8c8e4-130">Row index:</span></span>  <br/> |<span data-ttu-id="8c8e4-131">**visRowReplaceBehaviors**</span><span class="sxs-lookup"><span data-stu-id="8c8e4-131">**visRowReplaceBehaviors**</span></span> <br/> |
| <span data-ttu-id="8c8e4-132">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="8c8e4-132">Cell index:</span></span>  <br/> |<span data-ttu-id="8c8e4-133">**visReplaceLockFormat**</span><span class="sxs-lookup"><span data-stu-id="8c8e4-133">**visReplaceLockFormat**</span></span> <br/> |
   

