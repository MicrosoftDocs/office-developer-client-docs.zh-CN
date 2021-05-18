---
title: ConLineJumpCode 单元格（“Shape Layout”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251652
localization_priority: Normal
ms.assetid: af85588e-8e83-5168-7a8c-d7e8b4af5c27
description: 确定连接线何时跨线。
ms.openlocfilehash: 28bf506b8d3729fefec438d259746661fd28586e
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33421618"
---
# <a name="conlinejumpcode-cell-shape-layout-section"></a><span data-ttu-id="8f675-103">ConLineJumpCode 单元格（“Shape Layout”内容）</span><span class="sxs-lookup"><span data-stu-id="8f675-103">ConLineJumpCode Cell (Shape Layout Section)</span></span>

<span data-ttu-id="8f675-104">确定连接线何时跨线。</span><span class="sxs-lookup"><span data-stu-id="8f675-104">Determines when a connector jumps.</span></span>
  
|<span data-ttu-id="8f675-105">**值**</span><span class="sxs-lookup"><span data-stu-id="8f675-105">**Value**</span></span>|<span data-ttu-id="8f675-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="8f675-106">**Description**</span></span>|<span data-ttu-id="8f675-107">**自动常量**</span><span class="sxs-lookup"><span data-stu-id="8f675-107">**Automation constant**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="8f675-108">0</span><span class="sxs-lookup"><span data-stu-id="8f675-108">0</span></span>  <br/> |<span data-ttu-id="8f675-109">按照页面上指定的那样：在 **“设计”** 选项卡上，单击 **“页面设置”** 组中的箭头，然后单击 **“布局与排列”** 选项卡，查看页面规格</span><span class="sxs-lookup"><span data-stu-id="8f675-109">As page specifies; on the **Design** tab, click the arrow in the **Page Setup** group, and then click the **Layout and Routing** tab to see the page specifications</span></span>  <br/> |<span data-ttu-id="8f675-110">**visSLOJumpDefault**</span><span class="sxs-lookup"><span data-stu-id="8f675-110">**visSLOJumpDefault**</span></span> <br/> |
|<span data-ttu-id="8f675-111">1</span><span class="sxs-lookup"><span data-stu-id="8f675-111">1</span></span>  <br/> |<span data-ttu-id="8f675-112">永不</span><span class="sxs-lookup"><span data-stu-id="8f675-112">Never</span></span>  <br/> |<span data-ttu-id="8f675-113">**visSLOJumpNever**</span><span class="sxs-lookup"><span data-stu-id="8f675-113">**visSLOJumpNever**</span></span> <br/> |
|<span data-ttu-id="8f675-114">2</span><span class="sxs-lookup"><span data-stu-id="8f675-114">2</span></span>  <br/> |<span data-ttu-id="8f675-115">始终</span><span class="sxs-lookup"><span data-stu-id="8f675-115">Always</span></span>  <br/> |<span data-ttu-id="8f675-116">**visSLOJumpAlways**</span><span class="sxs-lookup"><span data-stu-id="8f675-116">**visSLOJumpAlways**</span></span> <br/> |
|<span data-ttu-id="8f675-117">3</span><span class="sxs-lookup"><span data-stu-id="8f675-117">3</span></span>  <br/> |<span data-ttu-id="8f675-118">其他连接线跨线</span><span class="sxs-lookup"><span data-stu-id="8f675-118">Other connector jumps</span></span>  <br/> |<span data-ttu-id="8f675-119">**visSLOJumpOther**</span><span class="sxs-lookup"><span data-stu-id="8f675-119">**visSLOJumpOther**</span></span> <br/> |
|<span data-ttu-id="8f675-120">4 </span><span class="sxs-lookup"><span data-stu-id="8f675-120">4</span></span>  <br/> |<span data-ttu-id="8f675-121">两条连接线都不跨线</span><span class="sxs-lookup"><span data-stu-id="8f675-121">Neither connector jumps</span></span>  <br/> |<span data-ttu-id="8f675-122">**visSLOJumpNeither**</span><span class="sxs-lookup"><span data-stu-id="8f675-122">**visSLOJumpNeither**</span></span> <br/> |
   
## <a name="remarks"></a><span data-ttu-id="8f675-123">备注</span><span class="sxs-lookup"><span data-stu-id="8f675-123">Remarks</span></span>

<span data-ttu-id="8f675-124">您还可以通过选择动态连接线、单击"开发工具"选项卡上的"形状设计"组中的行为，然后单击"连接 [](run-in-developer-mode-display-the-developer-tab.md)线"选项卡来设置此 **单元格** 的值。 </span><span class="sxs-lookup"><span data-stu-id="8f675-124">You can also set the value of this cell by selecting a dynamic connector, clicking **Behavior** in the **Shape Design** group on the [Developer](run-in-developer-mode-display-the-developer-tab.md) tab, and then clicking the **Connector** tab.</span></span> 
  
<span data-ttu-id="8f675-125">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 ConLineJumpCode 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="8f675-125">To get a reference to the ConLineJumpCode cell by name from another formula, or from a program by using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="8f675-126">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="8f675-126">Cell name:</span></span>  <br/> |<span data-ttu-id="8f675-127">ConLineJumpCode</span><span class="sxs-lookup"><span data-stu-id="8f675-127">ConLineJumpCode</span></span>  <br/> |
   
<span data-ttu-id="8f675-128">若要从某个程序按索引获取对 ConLineJumpCode 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="8f675-128">To get a reference to the ConLineJumpCode cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="8f675-129">内容索引：</span><span class="sxs-lookup"><span data-stu-id="8f675-129">Section index:</span></span>  <br/> |<span data-ttu-id="8f675-130">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="8f675-130">**visSectionObject**</span></span> <br/> |
|<span data-ttu-id="8f675-131">行索引：</span><span class="sxs-lookup"><span data-stu-id="8f675-131">Row index:</span></span>  <br/> |<span data-ttu-id="8f675-132">**visRowShapeLayout**</span><span class="sxs-lookup"><span data-stu-id="8f675-132">**visRowShapeLayout**</span></span> <br/> |
|<span data-ttu-id="8f675-133">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="8f675-133">Cell index:</span></span>  <br/> |<span data-ttu-id="8f675-134">**visSLOJumpCode**</span><span class="sxs-lookup"><span data-stu-id="8f675-134">**visSLOJumpCode**</span></span> <br/> |
   

