---
title: DynamicsOff 单元格（“Page Layout”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251641
localization_priority: Normal
ms.assetid: 055764aa-9681-ffb0-83ce-fdd612fe37af
description: 确定是否移动可放置的形状并让连接线围绕绘图页上的其他形状和连接线重排。
ms.openlocfilehash: d1075ab1b0512d5db1c7b7a5f2895305318dae7d
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32315717"
---
# <a name="dynamicsoff-cell-page-layout-section"></a><span data-ttu-id="a985c-103">DynamicsOff 单元格（“Page Layout”内容）</span><span class="sxs-lookup"><span data-stu-id="a985c-103">DynamicsOff Cell (Page Layout Section)</span></span>

<span data-ttu-id="a985c-104">确定是否移动可放置的形状并让连接线围绕绘图页上的其他形状和连接线重排。</span><span class="sxs-lookup"><span data-stu-id="a985c-104">Determines whether placeable shapes move and connectors reroute around other shapes and connectors on the drawing page.</span></span>
  
|<span data-ttu-id="a985c-105">**Value**</span><span class="sxs-lookup"><span data-stu-id="a985c-105">**Value**</span></span>|<span data-ttu-id="a985c-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="a985c-106">**Description**</span></span>|
|:-----|:-----|
| <span data-ttu-id="a985c-107">TRUE</span><span class="sxs-lookup"><span data-stu-id="a985c-107">TRUE</span></span>  <br/> | <span data-ttu-id="a985c-108">禁用动态特性。</span><span class="sxs-lookup"><span data-stu-id="a985c-108">Disable dynamics.</span></span>  <br/> |
| <span data-ttu-id="a985c-109">FALSE</span><span class="sxs-lookup"><span data-stu-id="a985c-109">FALSE</span></span>  <br/> | <span data-ttu-id="a985c-110">启用动态特性。</span><span class="sxs-lookup"><span data-stu-id="a985c-110">Enable dynamics.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="a985c-111">注解</span><span class="sxs-lookup"><span data-stu-id="a985c-111">Remarks</span></span>

<span data-ttu-id="a985c-p101">您可以禁用动态特性来提高解决方案的性能。例如，如果您的解决方案要将可放置的形状添加到绘图中，而您又不希望应用程序在每添加一个形状后都重排连接线和移动形状的位置，就可以禁用动态特性。在您的解决方案添加完所有形状之后，再重新启用动态特性。</span><span class="sxs-lookup"><span data-stu-id="a985c-p101">You can disable dynamics to increase your solution's performance. For example, if your solution adds placeable shapes to a drawing and you don't want the application to reroute connectors and reposition shapes each time you add a shape, you can disable dynamics. After your solution adds the shapes, re-enable dynamics.</span></span>
  
<span data-ttu-id="a985c-115">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 DynamicsOff 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="a985c-115">To get a reference to the DynamicsOff cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="a985c-116">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="a985c-116">Cell name:</span></span>  <br/> | <span data-ttu-id="a985c-117">DynamicsOff</span><span class="sxs-lookup"><span data-stu-id="a985c-117">DynamicsOff</span></span>  <br/> |
   
<span data-ttu-id="a985c-118">要从某个程序按索引获取对 DynamicsOff 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="a985c-118">To get a reference to the DynamicsOff cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="a985c-119">内容索引：</span><span class="sxs-lookup"><span data-stu-id="a985c-119">Section index:</span></span>  <br/> |<span data-ttu-id="a985c-120">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="a985c-120">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="a985c-121">行索引：</span><span class="sxs-lookup"><span data-stu-id="a985c-121">Row index:</span></span>  <br/> |<span data-ttu-id="a985c-122">**visRowPageLayout**</span><span class="sxs-lookup"><span data-stu-id="a985c-122">**visRowPageLayout**</span></span> <br/> |
| <span data-ttu-id="a985c-123">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="a985c-123">Cell index:</span></span>  <br/> |<span data-ttu-id="a985c-124">**visPLODynamicsOff**</span><span class="sxs-lookup"><span data-stu-id="a985c-124">**visPLODynamicsOff**</span></span> <br/> |
   

