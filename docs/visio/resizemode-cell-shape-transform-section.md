---
title: ResizeMode 单元格（“Shape Transform”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251203
localization_priority: Normal
ms.assetid: 49816e46-fa83-3ee4-1451-9c85fbd0f519
description: 显示形状的当前调整大小行为设置。
ms.openlocfilehash: 7e9080fcd4604e2dbdc1dae31992f05e5b512213
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33421961"
---
# <a name="resizemode-cell-shape-transform-section"></a><span data-ttu-id="16738-103">ResizeMode 单元格（“Shape Transform”内容）</span><span class="sxs-lookup"><span data-stu-id="16738-103">ResizeMode Cell (Shape Transform Section)</span></span>

<span data-ttu-id="16738-104">显示形状的当前调整大小行为设置。</span><span class="sxs-lookup"><span data-stu-id="16738-104">Shows the current resize behavior setting for the shape.</span></span>
  
|<span data-ttu-id="16738-105">**值**</span><span class="sxs-lookup"><span data-stu-id="16738-105">**Value**</span></span>|<span data-ttu-id="16738-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="16738-106">**Description**</span></span>|<span data-ttu-id="16738-107">**自动常量**</span><span class="sxs-lookup"><span data-stu-id="16738-107">**Automation constant**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="16738-108">0</span><span class="sxs-lookup"><span data-stu-id="16738-108">0</span></span>  <br/> |<span data-ttu-id="16738-109">使用组合的设置。</span><span class="sxs-lookup"><span data-stu-id="16738-109">Use group's setting.</span></span>  <br/> |<span data-ttu-id="16738-110">**visXFormResizeDontCare**</span><span class="sxs-lookup"><span data-stu-id="16738-110">**visXFormResizeDontCare**</span></span> <br/> |
|<span data-ttu-id="16738-111">1</span><span class="sxs-lookup"><span data-stu-id="16738-111">1</span></span>  <br/> |<span data-ttu-id="16738-112">仅重定位。</span><span class="sxs-lookup"><span data-stu-id="16738-112">Reposition only.</span></span>  <br/> |<span data-ttu-id="16738-113">**visXFormResizeSpread**</span><span class="sxs-lookup"><span data-stu-id="16738-113">**visXFormResizeSpread**</span></span> <br/> |
|<span data-ttu-id="16738-114">2</span><span class="sxs-lookup"><span data-stu-id="16738-114">2</span></span>  <br/> |<span data-ttu-id="16738-115">和组合一起缩放。</span><span class="sxs-lookup"><span data-stu-id="16738-115">Scale with group.</span></span>  <br/> |<span data-ttu-id="16738-116">**visXFormResizeScale**</span><span class="sxs-lookup"><span data-stu-id="16738-116">**visXFormResizeScale**</span></span> <br/> |
   
## <a name="remarks"></a><span data-ttu-id="16738-117">备注</span><span class="sxs-lookup"><span data-stu-id="16738-117">Remarks</span></span>

<span data-ttu-id="16738-118">您还可以在"开发工具"选项卡上"行为" ("行为"选项卡上的"形状设计"[](run-in-developer-mode-display-the-developer-tab.md)**组中，单击**"行为") 。  </span><span class="sxs-lookup"><span data-stu-id="16738-118">You can also set this value on the **Behavior** tab in the **Behavior** dialog box (on the [Developer](run-in-developer-mode-display-the-developer-tab.md)tab, in the **Shape Design** group, click **Behavior**).</span></span> <span data-ttu-id="16738-119">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 ResizeMode 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="16738-119">To get a reference to the ResizeMode cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="16738-120">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="16738-120">Cell name:</span></span>  <br/> |<span data-ttu-id="16738-121">ResizeMode</span><span class="sxs-lookup"><span data-stu-id="16738-121">ResizeMode</span></span>  <br/> |
   
<span data-ttu-id="16738-122">若要从某个程序按索引获取对 ResizeMode 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="16738-122">To get a reference to the ResizeMode cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="16738-123">内容索引：</span><span class="sxs-lookup"><span data-stu-id="16738-123">Section index:</span></span>  <br/> |<span data-ttu-id="16738-124">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="16738-124">**visSectionObject**</span></span> <br/> |
|<span data-ttu-id="16738-125">行索引：</span><span class="sxs-lookup"><span data-stu-id="16738-125">Row index:</span></span>  <br/> |<span data-ttu-id="16738-126">**visRowXFormOut**</span><span class="sxs-lookup"><span data-stu-id="16738-126">**visRowXFormOut**</span></span> <br/> |
|<span data-ttu-id="16738-127">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="16738-127">Cell index:</span></span>  <br/> |<span data-ttu-id="16738-128">**visXFormResizeMode**</span><span class="sxs-lookup"><span data-stu-id="16738-128">**visXFormResizeMode**</span></span> <br/> |
   

