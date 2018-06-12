---
title: CtrlAsInput 单元格（“Page Layout”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm1225
localization_priority: Normal
ms.assetid: c6fd0aba-7c33-b77f-207b-ba704b3e0756
description: 确定使用带有控制手柄的形状时哪个形状是父级。该单元格设置绘图页上所有形状的行为。
ms.openlocfilehash: a87ba7451d73af50de4a110ecdc12b3e23e14d5d
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780010"
---
# <a name="ctrlasinput-cell-page-layout-section"></a><span data-ttu-id="cc48e-104">CtrlAsInput 单元格（“Page Layout”内容）</span><span class="sxs-lookup"><span data-stu-id="cc48e-104">CtrlAsInput Cell (Page Layout Section)</span></span>

<span data-ttu-id="cc48e-p102">确定使用带有控制手柄的形状时哪个形状是父级。该单元格设置绘图页上所有形状的行为。</span><span class="sxs-lookup"><span data-stu-id="cc48e-p102">Determines which shape is the parent when using shapes with control handles. This cell sets the behavior for all the shapes on the drawing page.</span></span>
  
|<span data-ttu-id="cc48e-107">**值**</span><span class="sxs-lookup"><span data-stu-id="cc48e-107">**Value**</span></span>|<span data-ttu-id="cc48e-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="cc48e-108">**Description**</span></span>|
|:-----|:-----|
| <span data-ttu-id="cc48e-109">TRUE</span><span class="sxs-lookup"><span data-stu-id="cc48e-109">TRUE</span></span>  <br/> | <span data-ttu-id="cc48e-110">将控制手柄连接到的形状设置为父级。</span><span class="sxs-lookup"><span data-stu-id="cc48e-110">Set the shape that the control handle is connected to as the parent.</span></span>  <br/> |
| <span data-ttu-id="cc48e-111">FALSE</span><span class="sxs-lookup"><span data-stu-id="cc48e-111">FALSE</span></span>  <br/> | <span data-ttu-id="cc48e-p103">默认值。将包含控制手柄的形状设置为父级。</span><span class="sxs-lookup"><span data-stu-id="cc48e-p103">The default. Set shape that contains the control handle as the parent.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="cc48e-114">注释</span><span class="sxs-lookup"><span data-stu-id="cc48e-114">Remarks</span></span>

<span data-ttu-id="cc48e-115">要从另一个公式或使用**CellsU**属性从某个程序按名称获取对 CtrlAsInput 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="cc48e-115">To get a reference to the CtrlAsInput cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="cc48e-116">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="cc48e-116">Cell name:</span></span>  <br/> | <span data-ttu-id="cc48e-117">CtrlAsInput</span><span class="sxs-lookup"><span data-stu-id="cc48e-117">CtrlAsInput</span></span>  <br/> |
   
<span data-ttu-id="cc48e-118">若要从某个程序按索引获取对 CtrlAsInput 单元格的引用，请使用带下列参数的**CellsSRC**属性：</span><span class="sxs-lookup"><span data-stu-id="cc48e-118">To get a reference to the CtrlAsInput cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="cc48e-119">内容索引：</span><span class="sxs-lookup"><span data-stu-id="cc48e-119">Section index:</span></span>  <br/> |<span data-ttu-id="cc48e-120">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="cc48e-120">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="cc48e-121">行索引：</span><span class="sxs-lookup"><span data-stu-id="cc48e-121">Row index:</span></span>  <br/> |<span data-ttu-id="cc48e-122">**visRowPageLayout**</span><span class="sxs-lookup"><span data-stu-id="cc48e-122">**visRowPageLayout**</span></span> <br/> |
| <span data-ttu-id="cc48e-123">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="cc48e-123">Cell index:</span></span>  <br/> |<span data-ttu-id="cc48e-124">**visPLOCtrlAsInput**</span><span class="sxs-lookup"><span data-stu-id="cc48e-124">**visPLOCtrlAsInput**</span></span> <br/> |
   

