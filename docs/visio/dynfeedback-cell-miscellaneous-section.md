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
ms.openlocfilehash: 858d98c8ee55eb49f58bbe98491ddc8752e75504
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780167"
---
# <a name="dynfeedback-cell-miscellaneous-section"></a><span data-ttu-id="193de-105">DynFeedback 单元格（“Miscellaneous”部分）</span><span class="sxs-lookup"><span data-stu-id="193de-105">DynFeedback Cell (Miscellaneous Section)</span></span>

<span data-ttu-id="193de-p102">更改当用户拖动连接线时所感受到的视觉反馈类型。松开鼠标按钮后，相应而生的连接线形状并不受此设置的影响。此设置不应用于可穿绕的连接线。</span><span class="sxs-lookup"><span data-stu-id="193de-p102">Changes the type of visual feedback provided to users when they drag a connector. When the mouse button is released, the resulting connector shape is not affected by this setting. This setting does not apply to routable connectors.</span></span>
  
|<span data-ttu-id="193de-109">**值**</span><span class="sxs-lookup"><span data-stu-id="193de-109">**Value**</span></span>|<span data-ttu-id="193de-110">**说明**</span><span class="sxs-lookup"><span data-stu-id="193de-110">**Description**</span></span>|<span data-ttu-id="193de-111">**自动常量**</span><span class="sxs-lookup"><span data-stu-id="193de-111">**Automation constant**</span></span>|
|:-----|:-----|:-----|
| <span data-ttu-id="193de-112">0</span><span class="sxs-lookup"><span data-stu-id="193de-112">0</span></span>  <br/> | <span data-ttu-id="193de-113">保持直线（无引线）。</span><span class="sxs-lookup"><span data-stu-id="193de-113">Remains straight (no legs).</span></span>  <br/> |<span data-ttu-id="193de-114">**visDynFBDefault**</span><span class="sxs-lookup"><span data-stu-id="193de-114">**visDynFBDefault**</span></span> <br/> |
| <span data-ttu-id="193de-115">1</span><span class="sxs-lookup"><span data-stu-id="193de-115">1</span></span>  <br/> | <span data-ttu-id="193de-116">拖动时显示三条引线。</span><span class="sxs-lookup"><span data-stu-id="193de-116">Shows three legs when dragged.</span></span>  <br/> |<span data-ttu-id="193de-117">**visDynFBUCon3Leg**</span><span class="sxs-lookup"><span data-stu-id="193de-117">**visDynFBUCon3Leg**</span></span> <br/> |
| <span data-ttu-id="193de-118">2</span><span class="sxs-lookup"><span data-stu-id="193de-118">2</span></span>  <br/> | <span data-ttu-id="193de-119">拖动时显示五条引线。</span><span class="sxs-lookup"><span data-stu-id="193de-119">Shows five legs when dragged.</span></span>  <br/> |<span data-ttu-id="193de-120">**visDynFBUCon5Leg**</span><span class="sxs-lookup"><span data-stu-id="193de-120">**visDynFBUCon5Leg**</span></span> <br/> |
   
## <a name="remarks"></a><span data-ttu-id="193de-121">说明</span><span class="sxs-lookup"><span data-stu-id="193de-121">Remarks</span></span>

<span data-ttu-id="193de-122">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 DynFeedback 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="193de-122">To get a reference to the DynFeedback cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="193de-123">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="193de-123">Cell name:</span></span>  <br/> | <span data-ttu-id="193de-124">DynFeedback</span><span class="sxs-lookup"><span data-stu-id="193de-124">DynFeedback</span></span>  <br/> |
   
<span data-ttu-id="193de-125">要从某个程序按索引获取对 DynFeedback 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="193de-125">To get a reference to the DynFeedback cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="193de-126">内容索引：</span><span class="sxs-lookup"><span data-stu-id="193de-126">Section index:</span></span>  <br/> |<span data-ttu-id="193de-127">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="193de-127">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="193de-128">行索引：</span><span class="sxs-lookup"><span data-stu-id="193de-128">Row index:</span></span>  <br/> |<span data-ttu-id="193de-129">**visRowMisc**</span><span class="sxs-lookup"><span data-stu-id="193de-129">**visRowMisc**</span></span> <br/> |
| <span data-ttu-id="193de-130">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="193de-130">Cell index:</span></span>  <br/> |<span data-ttu-id="193de-131">**visDynFeedback**</span><span class="sxs-lookup"><span data-stu-id="193de-131">**visDynFeedback**</span></span> <br/> |
   

