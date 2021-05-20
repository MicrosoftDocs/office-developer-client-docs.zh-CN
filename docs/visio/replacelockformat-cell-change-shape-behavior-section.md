---
title: 'ReplaceLockFormat Cell (Change Shape Behavior Section) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 6973e2e6-7e7f-48ba-95b3-37c959f6ffb1
description: 指示主控形状中指定单元格的值是否覆盖形状 (替换操作) 替换的形状的本地值。 如果主控形状的 ReplaceLockFormat 单元格设置为 TRUE (1) ，则主控形状的格式值将覆盖要由主控形状替换的形状的所有相应值。
ms.openlocfilehash: 88af22accb7a80640e7553338dae1af48934f246
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33427232"
---
# <a name="replacelockformat-cell-change-shape-behavior-section"></a><span data-ttu-id="7e4b6-104">ReplaceLockFormat Cell (Change Shape Behavior Section) </span><span class="sxs-lookup"><span data-stu-id="7e4b6-104">ReplaceLockFormat Cell (Change Shape Behavior Section)</span></span>

<span data-ttu-id="7e4b6-105">指示主控形状中指定单元格的值是否覆盖形状 (替换操作) 替换的形状的本地值。</span><span class="sxs-lookup"><span data-stu-id="7e4b6-105">Indicates whether the values of specified cells in a master shape overwrite the values (including local values) of a shape being replaced during a shape replacement operation.</span></span> <span data-ttu-id="7e4b6-106">如果主控形状的 **ReplaceLockFormat** 单元格设置为 TRUE (1) ，则主控形状的格式设置值将覆盖要由主控形状替换的形状的所有相应值。</span><span class="sxs-lookup"><span data-stu-id="7e4b6-106">If the **ReplaceLockFormat** cell of a master shape is set to TRUE (1), the formatting values of the master overwrite all corresponding values of a shape being replaced by the master.</span></span> 
  
|<span data-ttu-id="7e4b6-107">**值**</span><span class="sxs-lookup"><span data-stu-id="7e4b6-107">**Value**</span></span>|<span data-ttu-id="7e4b6-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="7e4b6-108">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="7e4b6-109">TRUE</span><span class="sxs-lookup"><span data-stu-id="7e4b6-109">TRUE</span></span>  <br/> |<span data-ttu-id="7e4b6-110">如果 **主控形状的 ReplaceLockFormat** 单元格设置为 TRUE，则主控形状的格式值将覆盖要由主控形状替换的形状的所有相应值。</span><span class="sxs-lookup"><span data-stu-id="7e4b6-110">If the **ReplaceLockFormat** cell of a master shape is set to TRUE, the formatting values of the master overwrite all corresponding values of a shape being replaced by the master.</span></span>  <br/> |
|<span data-ttu-id="7e4b6-111">FALSE</span><span class="sxs-lookup"><span data-stu-id="7e4b6-111">FALSE</span></span>  <br/> |<span data-ttu-id="7e4b6-112">如果主 **控形状的 ReplaceLockFormat** 单元格设置为 FALSE，则替换形状在替换操作后包含旧形状中的本地格式值。</span><span class="sxs-lookup"><span data-stu-id="7e4b6-112">If the **ReplaceLockFormat** cell of a master shape is set to FALSE, the replacement shape contains the local formatting values from the old shape after the replacement operation.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="7e4b6-113">备注</span><span class="sxs-lookup"><span data-stu-id="7e4b6-113">Remarks</span></span>

<span data-ttu-id="7e4b6-114">**ReplaceLockFormat** 单元格确定主控形状在形状替换操作期间是否覆盖以下各节中单元格的本地格式值：</span><span class="sxs-lookup"><span data-stu-id="7e4b6-114">The **ReplaceLockFormat** cell determines whether the master shape overwrites the local formatting values of the cells in the following sections during a shape replacement operation:</span></span> 
  
- <span data-ttu-id="7e4b6-115">**"填充格式"** 部分</span><span class="sxs-lookup"><span data-stu-id="7e4b6-115">**Fill Format** section</span></span> 
    
- <span data-ttu-id="7e4b6-116">**"线条格式"** 部分</span><span class="sxs-lookup"><span data-stu-id="7e4b6-116">**Line Format** section</span></span> 
    
- <span data-ttu-id="7e4b6-117">**"快速样式"** 部分</span><span class="sxs-lookup"><span data-stu-id="7e4b6-117">**Quick Style** section</span></span> 
    
- <span data-ttu-id="7e4b6-118">**"主题属性"** 部分</span><span class="sxs-lookup"><span data-stu-id="7e4b6-118">**Theme Properties** section</span></span> 
    
- <span data-ttu-id="7e4b6-119">**"渐变属性"** 部分</span><span class="sxs-lookup"><span data-stu-id="7e4b6-119">**Gradient Properties** section</span></span> 
    
- <span data-ttu-id="7e4b6-120">**"斜面属性"** 部分</span><span class="sxs-lookup"><span data-stu-id="7e4b6-120">**Bevel Properties** section</span></span> 
    
- <span data-ttu-id="7e4b6-121">**"其他效果属性"** 部分</span><span class="sxs-lookup"><span data-stu-id="7e4b6-121">**Additional Effect Properties** section</span></span> 
    
- <span data-ttu-id="7e4b6-122">**"线条渐变停止点"** 部分</span><span class="sxs-lookup"><span data-stu-id="7e4b6-122">**Line Gradient Stops** section</span></span> 
    
- <span data-ttu-id="7e4b6-123">**"填充渐变停止点"** 部分</span><span class="sxs-lookup"><span data-stu-id="7e4b6-123">**Fill Gradient Stops** section</span></span> 
    
<span data-ttu-id="7e4b6-124">若要从另一个公式 **、Cell** 元素 **的 N** 属性值或使用 **CellsU** 属性从某个程序按名称获取对 **ReplaceLockFormat** 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="7e4b6-124">To get a reference to the **ReplaceLockFormat** cell by name from another formula, by value of the **N** attribute of a **Cell** element, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="7e4b6-125">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="7e4b6-125">Cell name:</span></span>  <br/> | <span data-ttu-id="7e4b6-126">ReplaceLockFormat</span><span class="sxs-lookup"><span data-stu-id="7e4b6-126">ReplaceLockFormat</span></span>  <br/> |
   
<span data-ttu-id="7e4b6-127">若要从程序按索引获取 **对 ReplaceLockFormat** 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="7e4b6-127">To get a reference to the **ReplaceLockFormat** cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="7e4b6-128">内容索引：</span><span class="sxs-lookup"><span data-stu-id="7e4b6-128">Section index:</span></span>  <br/> |<span data-ttu-id="7e4b6-129">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="7e4b6-129">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="7e4b6-130">行索引：</span><span class="sxs-lookup"><span data-stu-id="7e4b6-130">Row index:</span></span>  <br/> |<span data-ttu-id="7e4b6-131">**visRowReplaceBehaviors**</span><span class="sxs-lookup"><span data-stu-id="7e4b6-131">**visRowReplaceBehaviors**</span></span> <br/> |
| <span data-ttu-id="7e4b6-132">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="7e4b6-132">Cell index:</span></span>  <br/> |<span data-ttu-id="7e4b6-133">**visReplaceLockFormat**</span><span class="sxs-lookup"><span data-stu-id="7e4b6-133">**visReplaceLockFormat**</span></span> <br/> |
   

