---
title: DynFeedback 单元格（“Miscellaneous”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251317
localization_priority: Normal
ms.assetid: 44017319-7146-3431-e476-fbb1a40341ca
description: 更改当用户拖动连接线时所感受到的视觉反馈类型。松开鼠标按钮后，相应而生的连接线形状并不受此设置的影响。此设置不应用于可穿绕的连接线。
ms.openlocfilehash: 823b8db4dc6afe94a5fdac1f62aaa48d7e1b0d80
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33404797"
---
# <a name="dynfeedback-cell-miscellaneous-section"></a><span data-ttu-id="c38c6-105">DynFeedback 单元格（“Miscellaneous”内容）</span><span class="sxs-lookup"><span data-stu-id="c38c6-105">DynFeedback Cell (Miscellaneous Section)</span></span>

<span data-ttu-id="c38c6-p102">更改当用户拖动连接线时所感受到的视觉反馈类型。松开鼠标按钮后，相应而生的连接线形状并不受此设置的影响。此设置不应用于可穿绕的连接线。</span><span class="sxs-lookup"><span data-stu-id="c38c6-p102">Changes the type of visual feedback provided to users when they drag a connector. When the mouse button is released, the resulting connector shape is not affected by this setting. This setting does not apply to routable connectors.</span></span>
  
|<span data-ttu-id="c38c6-109">**值**</span><span class="sxs-lookup"><span data-stu-id="c38c6-109">**Value**</span></span>|<span data-ttu-id="c38c6-110">**说明**</span><span class="sxs-lookup"><span data-stu-id="c38c6-110">**Description**</span></span>|<span data-ttu-id="c38c6-111">**自动常量**</span><span class="sxs-lookup"><span data-stu-id="c38c6-111">**Automation constant**</span></span>|
|:-----|:-----|:-----|
| <span data-ttu-id="c38c6-112">0</span><span class="sxs-lookup"><span data-stu-id="c38c6-112">0</span></span>  <br/> | <span data-ttu-id="c38c6-113">保持直线（无引线）。</span><span class="sxs-lookup"><span data-stu-id="c38c6-113">Remains straight (no legs).</span></span>  <br/> |<span data-ttu-id="c38c6-114">**visDynFBDefault**</span><span class="sxs-lookup"><span data-stu-id="c38c6-114">**visDynFBDefault**</span></span> <br/> |
| <span data-ttu-id="c38c6-115">1</span><span class="sxs-lookup"><span data-stu-id="c38c6-115">1</span></span>  <br/> | <span data-ttu-id="c38c6-116">拖动时显示三条引线。</span><span class="sxs-lookup"><span data-stu-id="c38c6-116">Shows three legs when dragged.</span></span>  <br/> |<span data-ttu-id="c38c6-117">**visDynFBUCon3Leg**</span><span class="sxs-lookup"><span data-stu-id="c38c6-117">**visDynFBUCon3Leg**</span></span> <br/> |
| <span data-ttu-id="c38c6-118">双面</span><span class="sxs-lookup"><span data-stu-id="c38c6-118">2</span></span>  <br/> | <span data-ttu-id="c38c6-119">拖动时显示五条引线。</span><span class="sxs-lookup"><span data-stu-id="c38c6-119">Shows five legs when dragged.</span></span>  <br/> |<span data-ttu-id="c38c6-120">**visDynFBUCon5Leg**</span><span class="sxs-lookup"><span data-stu-id="c38c6-120">**visDynFBUCon5Leg**</span></span> <br/> |
   
## <a name="remarks"></a><span data-ttu-id="c38c6-121">说明</span><span class="sxs-lookup"><span data-stu-id="c38c6-121">Remarks</span></span>

<span data-ttu-id="c38c6-122">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 DynFeedback 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="c38c6-122">To get a reference to the DynFeedback cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="c38c6-123">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="c38c6-123">Cell name:</span></span>  <br/> | <span data-ttu-id="c38c6-124">DynFeedback</span><span class="sxs-lookup"><span data-stu-id="c38c6-124">DynFeedback</span></span>  <br/> |
   
<span data-ttu-id="c38c6-125">要从某个程序按索引获取对 DynFeedback 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="c38c6-125">To get a reference to the DynFeedback cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="c38c6-126">内容索引：</span><span class="sxs-lookup"><span data-stu-id="c38c6-126">Section index:</span></span>  <br/> |<span data-ttu-id="c38c6-127">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="c38c6-127">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="c38c6-128">行索引：</span><span class="sxs-lookup"><span data-stu-id="c38c6-128">Row index:</span></span>  <br/> |<span data-ttu-id="c38c6-129">**visRowMisc**</span><span class="sxs-lookup"><span data-stu-id="c38c6-129">**visRowMisc**</span></span> <br/> |
| <span data-ttu-id="c38c6-130">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="c38c6-130">Cell index:</span></span>  <br/> |<span data-ttu-id="c38c6-131">**visDynFeedback**</span><span class="sxs-lookup"><span data-stu-id="c38c6-131">**visDynFeedback**</span></span> <br/> |
   

