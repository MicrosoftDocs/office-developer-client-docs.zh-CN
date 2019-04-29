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
ms.openlocfilehash: a530c48156043bec0cd58d79aead1a403c17ddce
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33422619"
---
# <a name="ctrlasinput-cell-page-layout-section"></a><span data-ttu-id="cabe0-104">CtrlAsInput 单元格（“Page Layout”内容）</span><span class="sxs-lookup"><span data-stu-id="cabe0-104">CtrlAsInput Cell (Page Layout Section)</span></span>

<span data-ttu-id="cabe0-p102">确定使用带有控制手柄的形状时哪个形状是父级。该单元格设置绘图页上所有形状的行为。</span><span class="sxs-lookup"><span data-stu-id="cabe0-p102">Determines which shape is the parent when using shapes with control handles. This cell sets the behavior for all the shapes on the drawing page.</span></span>
  
|<span data-ttu-id="cabe0-107">**值**</span><span class="sxs-lookup"><span data-stu-id="cabe0-107">**Value**</span></span>|<span data-ttu-id="cabe0-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="cabe0-108">**Description**</span></span>|
|:-----|:-----|
| <span data-ttu-id="cabe0-109">TRUE</span><span class="sxs-lookup"><span data-stu-id="cabe0-109">TRUE</span></span>  <br/> | <span data-ttu-id="cabe0-110">将控制手柄连接到的形状设置为父级。</span><span class="sxs-lookup"><span data-stu-id="cabe0-110">Set the shape that the control handle is connected to as the parent.</span></span>  <br/> |
| <span data-ttu-id="cabe0-111">FALSE</span><span class="sxs-lookup"><span data-stu-id="cabe0-111">FALSE</span></span>  <br/> | <span data-ttu-id="cabe0-p103">默认值。将包含控制手柄的形状设置为父级。</span><span class="sxs-lookup"><span data-stu-id="cabe0-p103">The default. Set shape that contains the control handle as the parent.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="cabe0-114">说明</span><span class="sxs-lookup"><span data-stu-id="cabe0-114">Remarks</span></span>

<span data-ttu-id="cabe0-115">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 CtrlAsInput 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="cabe0-115">To get a reference to the CtrlAsInput cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="cabe0-116">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="cabe0-116">Cell name:</span></span>  <br/> | <span data-ttu-id="cabe0-117">CtrlAsInput</span><span class="sxs-lookup"><span data-stu-id="cabe0-117">CtrlAsInput</span></span>  <br/> |
   
<span data-ttu-id="cabe0-118">要从某个程序按索引获取对 CtrlAsInput 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="cabe0-118">To get a reference to the CtrlAsInput cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="cabe0-119">内容索引：</span><span class="sxs-lookup"><span data-stu-id="cabe0-119">Section index:</span></span>  <br/> |<span data-ttu-id="cabe0-120">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="cabe0-120">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="cabe0-121">行索引：</span><span class="sxs-lookup"><span data-stu-id="cabe0-121">Row index:</span></span>  <br/> |<span data-ttu-id="cabe0-122">**visRowPageLayout**</span><span class="sxs-lookup"><span data-stu-id="cabe0-122">**visRowPageLayout**</span></span> <br/> |
| <span data-ttu-id="cabe0-123">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="cabe0-123">Cell index:</span></span>  <br/> |<span data-ttu-id="cabe0-124">**visPLOCtrlAsInput**</span><span class="sxs-lookup"><span data-stu-id="cabe0-124">**visPLOCtrlAsInput**</span></span> <br/> |
   

