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
ms.openlocfilehash: a32f5dbc935e85a49ab585073ca6a31215fd102a
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781130"
---
# <a name="resizemode-cell-shape-transform-section"></a><span data-ttu-id="47bc2-103">ResizeMode 单元格（“Shape Transform”内容）</span><span class="sxs-lookup"><span data-stu-id="47bc2-103">ResizeMode Cell (Shape Transform Section)</span></span>

<span data-ttu-id="47bc2-104">显示形状的当前调整大小行为设置。</span><span class="sxs-lookup"><span data-stu-id="47bc2-104">Shows the current resize behavior setting for the shape.</span></span>
  
|<span data-ttu-id="47bc2-105">**值**</span><span class="sxs-lookup"><span data-stu-id="47bc2-105">**Value**</span></span>|<span data-ttu-id="47bc2-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="47bc2-106">**Description**</span></span>|<span data-ttu-id="47bc2-107">**自动化常量**</span><span class="sxs-lookup"><span data-stu-id="47bc2-107">**Automation constant**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="47bc2-108">0</span><span class="sxs-lookup"><span data-stu-id="47bc2-108">0</span></span>  <br/> |<span data-ttu-id="47bc2-109">使用组合的设置。</span><span class="sxs-lookup"><span data-stu-id="47bc2-109">Use group's setting.</span></span>  <br/> |<span data-ttu-id="47bc2-110">**visXFormResizeDontCare**</span><span class="sxs-lookup"><span data-stu-id="47bc2-110">**visXFormResizeDontCare**</span></span> <br/> |
|<span data-ttu-id="47bc2-111">1</span><span class="sxs-lookup"><span data-stu-id="47bc2-111">1</span></span>  <br/> |<span data-ttu-id="47bc2-112">仅重定位。</span><span class="sxs-lookup"><span data-stu-id="47bc2-112">Reposition only.</span></span>  <br/> |<span data-ttu-id="47bc2-113">**visXFormResizeSpread**</span><span class="sxs-lookup"><span data-stu-id="47bc2-113">**visXFormResizeSpread**</span></span> <br/> |
|<span data-ttu-id="47bc2-114">2</span><span class="sxs-lookup"><span data-stu-id="47bc2-114">2</span></span>  <br/> |<span data-ttu-id="47bc2-115">和组合一起缩放。</span><span class="sxs-lookup"><span data-stu-id="47bc2-115">Scale with group.</span></span>  <br/> |<span data-ttu-id="47bc2-116">**visXFormResizeScale**</span><span class="sxs-lookup"><span data-stu-id="47bc2-116">**visXFormResizeScale**</span></span> <br/> |
   
## <a name="remarks"></a><span data-ttu-id="47bc2-117">备注</span><span class="sxs-lookup"><span data-stu-id="47bc2-117">Remarks</span></span>

<span data-ttu-id="47bc2-118">您可以在**行为**对话框中的**行为**选项卡上设置此值 （在[开发人员](run-in-developer-mode-display-the-developer-tab.md)选项卡的**形状设计**组中，单击**行为**）。</span><span class="sxs-lookup"><span data-stu-id="47bc2-118">You can also set this value on the **Behavior** tab in the **Behavior** dialog box (on the [Developer](run-in-developer-mode-display-the-developer-tab.md)tab, in the **Shape Design** group, click **Behavior**).</span></span> <span data-ttu-id="47bc2-119">要从另一个公式或使用**CellsU**属性从某个程序按名称获取对 ResizeMode 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="47bc2-119">To get a reference to the ResizeMode cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="47bc2-120">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="47bc2-120">Cell name:</span></span>  <br/> |<span data-ttu-id="47bc2-121">ResizeMode</span><span class="sxs-lookup"><span data-stu-id="47bc2-121">ResizeMode</span></span>  <br/> |
   
<span data-ttu-id="47bc2-122">若要从某个程序按索引获取对 ResizeMode 单元格的引用，请使用带下列参数的**CellsSRC**属性：</span><span class="sxs-lookup"><span data-stu-id="47bc2-122">To get a reference to the ResizeMode cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="47bc2-123">内容索引：</span><span class="sxs-lookup"><span data-stu-id="47bc2-123">Section index:</span></span>  <br/> |<span data-ttu-id="47bc2-124">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="47bc2-124">**visSectionObject**</span></span> <br/> |
|<span data-ttu-id="47bc2-125">行索引：</span><span class="sxs-lookup"><span data-stu-id="47bc2-125">Row index:</span></span>  <br/> |<span data-ttu-id="47bc2-126">**visRowXFormOut**</span><span class="sxs-lookup"><span data-stu-id="47bc2-126">**visRowXFormOut**</span></span> <br/> |
|<span data-ttu-id="47bc2-127">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="47bc2-127">Cell index:</span></span>  <br/> |<span data-ttu-id="47bc2-128">**visXFormResizeMode**</span><span class="sxs-lookup"><span data-stu-id="47bc2-128">**visXFormResizeMode**</span></span> <br/> |
   

