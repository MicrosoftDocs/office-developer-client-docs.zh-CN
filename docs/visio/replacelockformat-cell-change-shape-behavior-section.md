---
title: ReplaceLockFormat 单元格 ("更改形状行为" 部分)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 6973e2e6-7e7f-48ba-95b3-37c959f6ffb1
description: 指示主控形状中指定单元格的值是否覆盖在形状替换操作过程中要替换的形状的值 (包括本地值)。 如果主控形状的 ReplaceLockFormat 单元格设置为 TRUE (1), 则主控形状的格式值将覆盖主控形状替换的形状的所有相应值。
ms.openlocfilehash: 88af22accb7a80640e7553338dae1af48934f246
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33427232"
---
# <a name="replacelockformat-cell-change-shape-behavior-section"></a><span data-ttu-id="34e59-104">ReplaceLockFormat 单元格 ("更改形状行为" 部分)</span><span class="sxs-lookup"><span data-stu-id="34e59-104">ReplaceLockFormat Cell (Change Shape Behavior Section)</span></span>

<span data-ttu-id="34e59-105">指示主控形状中指定单元格的值是否覆盖在形状替换操作过程中要替换的形状的值 (包括本地值)。</span><span class="sxs-lookup"><span data-stu-id="34e59-105">Indicates whether the values of specified cells in a master shape overwrite the values (including local values) of a shape being replaced during a shape replacement operation.</span></span> <span data-ttu-id="34e59-106">如果主控形状的**ReplaceLockFormat**单元格设置为 TRUE (1), 则主控形状的格式值将覆盖主控形状替换的形状的所有相应值。</span><span class="sxs-lookup"><span data-stu-id="34e59-106">If the **ReplaceLockFormat** cell of a master shape is set to TRUE (1), the formatting values of the master overwrite all corresponding values of a shape being replaced by the master.</span></span> 
  
|<span data-ttu-id="34e59-107">**值**</span><span class="sxs-lookup"><span data-stu-id="34e59-107">**Value**</span></span>|<span data-ttu-id="34e59-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="34e59-108">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="34e59-109">TRUE</span><span class="sxs-lookup"><span data-stu-id="34e59-109">TRUE</span></span>  <br/> |<span data-ttu-id="34e59-110">如果主控形状的**ReplaceLockFormat**单元格设置为 TRUE, 则主控形状的格式值将覆盖主控形状替换的所有形状的相应值。</span><span class="sxs-lookup"><span data-stu-id="34e59-110">If the **ReplaceLockFormat** cell of a master shape is set to TRUE, the formatting values of the master overwrite all corresponding values of a shape being replaced by the master.</span></span>  <br/> |
|<span data-ttu-id="34e59-111">FALSE</span><span class="sxs-lookup"><span data-stu-id="34e59-111">FALSE</span></span>  <br/> |<span data-ttu-id="34e59-112">如果主控形状的**ReplaceLockFormat**单元格设置为 FALSE, 则替换形状包含替换操作后旧形状中的本地格式值。</span><span class="sxs-lookup"><span data-stu-id="34e59-112">If the **ReplaceLockFormat** cell of a master shape is set to FALSE, the replacement shape contains the local formatting values from the old shape after the replacement operation.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="34e59-113">说明</span><span class="sxs-lookup"><span data-stu-id="34e59-113">Remarks</span></span>

<span data-ttu-id="34e59-114">**ReplaceLockFormat**单元格决定在形状替换操作过程中, 主控形状是否会覆盖以下各节中单元格的局部格式值:</span><span class="sxs-lookup"><span data-stu-id="34e59-114">The **ReplaceLockFormat** cell determines whether the master shape overwrites the local formatting values of the cells in the following sections during a shape replacement operation:</span></span> 
  
- <span data-ttu-id="34e59-115">"**填充格式**" 部分</span><span class="sxs-lookup"><span data-stu-id="34e59-115">**Fill Format** section</span></span> 
    
- <span data-ttu-id="34e59-116">"**线条格式**" 部分</span><span class="sxs-lookup"><span data-stu-id="34e59-116">**Line Format** section</span></span> 
    
- <span data-ttu-id="34e59-117">"**快速样式**" 部分</span><span class="sxs-lookup"><span data-stu-id="34e59-117">**Quick Style** section</span></span> 
    
- <span data-ttu-id="34e59-118">"**主题属性**" 部分</span><span class="sxs-lookup"><span data-stu-id="34e59-118">**Theme Properties** section</span></span> 
    
- <span data-ttu-id="34e59-119">"**渐变属性**" 部分</span><span class="sxs-lookup"><span data-stu-id="34e59-119">**Gradient Properties** section</span></span> 
    
- <span data-ttu-id="34e59-120">"**棱台属性**" 部分</span><span class="sxs-lookup"><span data-stu-id="34e59-120">**Bevel Properties** section</span></span> 
    
- <span data-ttu-id="34e59-121">"**其他效果属性**" 部分</span><span class="sxs-lookup"><span data-stu-id="34e59-121">**Additional Effect Properties** section</span></span> 
    
- <span data-ttu-id="34e59-122">"**线条梯度停止点**" 部分</span><span class="sxs-lookup"><span data-stu-id="34e59-122">**Line Gradient Stops** section</span></span> 
    
- <span data-ttu-id="34e59-123">**填充梯度停止点**部分</span><span class="sxs-lookup"><span data-stu-id="34e59-123">**Fill Gradient Stops** section</span></span> 
    
<span data-ttu-id="34e59-124">若要从另一个公式按名称获取对**ReplaceLockFormat**单元格的引用、 **cell**元素的**N**属性值, 或从使用**CellsU**属性的某个程序获取对该单元格的引用, 请使用:</span><span class="sxs-lookup"><span data-stu-id="34e59-124">To get a reference to the **ReplaceLockFormat** cell by name from another formula, by value of the **N** attribute of a **Cell** element, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="34e59-125">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="34e59-125">Cell name:</span></span>  <br/> | <span data-ttu-id="34e59-126">ReplaceLockFormat</span><span class="sxs-lookup"><span data-stu-id="34e59-126">ReplaceLockFormat</span></span>  <br/> |
   
<span data-ttu-id="34e59-127">若要从某个程序按索引获取对**ReplaceLockFormat**单元格的引用, 请使用带下列参数的**CellsSRC**属性:</span><span class="sxs-lookup"><span data-stu-id="34e59-127">To get a reference to the **ReplaceLockFormat** cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="34e59-128">内容索引：</span><span class="sxs-lookup"><span data-stu-id="34e59-128">Section index:</span></span>  <br/> |<span data-ttu-id="34e59-129">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="34e59-129">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="34e59-130">行索引：</span><span class="sxs-lookup"><span data-stu-id="34e59-130">Row index:</span></span>  <br/> |<span data-ttu-id="34e59-131">**visRowReplaceBehaviors**</span><span class="sxs-lookup"><span data-stu-id="34e59-131">**visRowReplaceBehaviors**</span></span> <br/> |
| <span data-ttu-id="34e59-132">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="34e59-132">Cell index:</span></span>  <br/> |<span data-ttu-id="34e59-133">**visReplaceLockFormat**</span><span class="sxs-lookup"><span data-stu-id="34e59-133">**visReplaceLockFormat**</span></span> <br/> |
   

