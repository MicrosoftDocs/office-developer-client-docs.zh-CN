---
title: IsTextEditTarget 单元格（“Group Properties”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251627
localization_priority: Normal
ms.assetid: 355cef8b-9213-479a-af95-b591f4bc51ad
description: 确定组合的文本分配。
ms.openlocfilehash: 78a70dc0398745765bca12a1e768390b35fce8ce
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33432644"
---
# <a name="istextedittarget-cell-group-properties-section"></a><span data-ttu-id="85cbd-103">IsTextEditTarget 单元格（“Group Properties”内容）</span><span class="sxs-lookup"><span data-stu-id="85cbd-103">IsTextEditTarget Cell (Group Properties Section)</span></span>

<span data-ttu-id="85cbd-104">确定组合的文本分配。</span><span class="sxs-lookup"><span data-stu-id="85cbd-104">Determines text assignment for a group.</span></span>
  
|<span data-ttu-id="85cbd-105">**值**</span><span class="sxs-lookup"><span data-stu-id="85cbd-105">**Value**</span></span>|<span data-ttu-id="85cbd-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="85cbd-106">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="85cbd-107">TRUE</span><span class="sxs-lookup"><span data-stu-id="85cbd-107">TRUE</span></span>  <br/> |<span data-ttu-id="85cbd-108">文本被添加到组合形状中。</span><span class="sxs-lookup"><span data-stu-id="85cbd-108">Text is added to the group shape.</span></span>  <br/> |
|<span data-ttu-id="85cbd-109">FALSE</span><span class="sxs-lookup"><span data-stu-id="85cbd-109">FALSE</span></span>  <br/> |<span data-ttu-id="85cbd-110">文本被添加到位于堆放顺序顶端的组合的形状中。</span><span class="sxs-lookup"><span data-stu-id="85cbd-110">Text is added to the shape in the group at the top of the stacking order.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="85cbd-111">备注</span><span class="sxs-lookup"><span data-stu-id="85cbd-111">Remarks</span></span>

<span data-ttu-id="85cbd-112">您还可以采用以下方法设置此值：选择该组合，在 [“开发工具”](run-in-developer-mode-display-the-developer-tab.md)选项卡上单击 **“行为”**，然后选中 **“编辑组合文本”** 复选框。</span><span class="sxs-lookup"><span data-stu-id="85cbd-112">You can also set this value by selecting the group, clicking **Behavior** on the [Developer](run-in-developer-mode-display-the-developer-tab.md) tab, and then selecting the **Edit text of group** check box.</span></span> 
  
<span data-ttu-id="85cbd-p101">在低于 Visio 2000 的版本中创建的组合的默认值为 FALSE。从 Visio 2000 版起，默认值为 TRUE。</span><span class="sxs-lookup"><span data-stu-id="85cbd-p101">Groups created in versions earlier than Visio 2000 have a default value of FALSE. Beginning with Visio version 2000, the default value is TRUE.</span></span> 
  
<span data-ttu-id="85cbd-115">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 IsTextEditTarget 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="85cbd-115">To get a reference to the IsTextEditTarget cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="85cbd-116">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="85cbd-116">Cell name:</span></span>  <br/> |<span data-ttu-id="85cbd-117">IsTextEditTarget</span><span class="sxs-lookup"><span data-stu-id="85cbd-117">IsTextEditTarget</span></span>  <br/> |
   
<span data-ttu-id="85cbd-118">若要从某个程序按索引获取对 IsTextEditTarget 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="85cbd-118">To get a reference to the IsTextEditTarget cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="85cbd-119">内容索引：</span><span class="sxs-lookup"><span data-stu-id="85cbd-119">Section index:</span></span>  <br/> |<span data-ttu-id="85cbd-120">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="85cbd-120">**visSectionObject**</span></span> <br/> |
|<span data-ttu-id="85cbd-121">行索引：</span><span class="sxs-lookup"><span data-stu-id="85cbd-121">Row index:</span></span>  <br/> |<span data-ttu-id="85cbd-122">**visRowGroup**</span><span class="sxs-lookup"><span data-stu-id="85cbd-122">**visRowGroup**</span></span> <br/> |
|<span data-ttu-id="85cbd-123">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="85cbd-123">Cell index:</span></span>  <br/> |<span data-ttu-id="85cbd-124">**visGroupIsTextEditTarget**</span><span class="sxs-lookup"><span data-stu-id="85cbd-124">**visGroupIsTextEditTarget**</span></span> <br/> |
   

