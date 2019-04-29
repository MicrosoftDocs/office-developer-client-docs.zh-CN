---
title: DisplayMode 单元格（“Group Properties”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251623
localization_priority: Normal
ms.assetid: e6d72529-aa03-e94b-130c-79ed04336299
description: 确定组合形状及其成员的显示方式。
ms.openlocfilehash: a49d7a38eac75a2845de0ca3ad22f7cbf79a63df
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33413183"
---
# <a name="displaymode-cell-group-properties-section"></a><span data-ttu-id="c6bdd-103">DisplayMode 单元格（“Group Properties”内容）</span><span class="sxs-lookup"><span data-stu-id="c6bdd-103">DisplayMode Cell (Group Properties Section)</span></span>

<span data-ttu-id="c6bdd-104">确定组合形状及其成员的显示方式。</span><span class="sxs-lookup"><span data-stu-id="c6bdd-104">Determines how the group shape and its members are displayed.</span></span>
  
|<span data-ttu-id="c6bdd-105">**值**</span><span class="sxs-lookup"><span data-stu-id="c6bdd-105">**Value**</span></span>|<span data-ttu-id="c6bdd-106">**显示模式**</span><span class="sxs-lookup"><span data-stu-id="c6bdd-106">**Display Mode**</span></span>|<span data-ttu-id="c6bdd-107">**自动常量**</span><span class="sxs-lookup"><span data-stu-id="c6bdd-107">**Automation constant**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c6bdd-108">0</span><span class="sxs-lookup"><span data-stu-id="c6bdd-108">0</span></span>  <br/> |<span data-ttu-id="c6bdd-109">隐藏组合形状和文本。</span><span class="sxs-lookup"><span data-stu-id="c6bdd-109">Hides the group shape and text.</span></span>  <br/> |<span data-ttu-id="c6bdd-110">**visGrpDispModeNone**</span><span class="sxs-lookup"><span data-stu-id="c6bdd-110">**visGrpDispModeNone**</span></span> <br/> |
|<span data-ttu-id="c6bdd-111">1</span><span class="sxs-lookup"><span data-stu-id="c6bdd-111">1</span></span>  <br/> |<span data-ttu-id="c6bdd-112">将组合形状显示在成员形状后面。</span><span class="sxs-lookup"><span data-stu-id="c6bdd-112">Displays the group shape behind member shapes.</span></span>  <br/> |<span data-ttu-id="c6bdd-113">**visGrpDispModeBack**</span><span class="sxs-lookup"><span data-stu-id="c6bdd-113">**visGrpDispModeBack**</span></span> <br/> |
|<span data-ttu-id="c6bdd-114">双面</span><span class="sxs-lookup"><span data-stu-id="c6bdd-114">2</span></span>  <br/> |<span data-ttu-id="c6bdd-115">将组合形状显示在成员形状的前面。</span><span class="sxs-lookup"><span data-stu-id="c6bdd-115">Displays the group shape in front of member shapes.</span></span>  <br/> |<span data-ttu-id="c6bdd-116">**visGrpDispModeFront**</span><span class="sxs-lookup"><span data-stu-id="c6bdd-116">**visGrpDispModeFront**</span></span> <br/> |
   
## <a name="remarks"></a><span data-ttu-id="c6bdd-117">说明</span><span class="sxs-lookup"><span data-stu-id="c6bdd-117">Remarks</span></span>

<span data-ttu-id="c6bdd-118">您还可以通过以下方法设置此值: 选择该组合, 在 "[开发工具](run-in-developer-mode-display-the-developer-tab.md)" 选项卡上的 "**形状设计**" 组中单击 "**行为**", 然后从 "**组数据**" 列表中选择一种显示模式。</span><span class="sxs-lookup"><span data-stu-id="c6bdd-118">You can also set this value by selecting the group, clicking **Behavior** on the **Shape Design** group on the [Developer](run-in-developer-mode-display-the-developer-tab.md) tab, and then selecting a display mode from the **Group data** list.</span></span> 
  
<span data-ttu-id="c6bdd-119">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 DisplayMode 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="c6bdd-119">To get a reference to the DisplayMode cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="c6bdd-120">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="c6bdd-120">Cell name:</span></span>  <br/> |<span data-ttu-id="c6bdd-121">DisplayMode</span><span class="sxs-lookup"><span data-stu-id="c6bdd-121">DisplayMode</span></span>  <br/> |
   
<span data-ttu-id="c6bdd-122">要从某个程序按索引获取对 DisplayMode 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="c6bdd-122">To get a reference to the DisplayMode cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="c6bdd-123">内容索引：</span><span class="sxs-lookup"><span data-stu-id="c6bdd-123">Section index:</span></span>  <br/> |<span data-ttu-id="c6bdd-124">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="c6bdd-124">**visSectionObject**</span></span> <br/> |
|<span data-ttu-id="c6bdd-125">行索引：</span><span class="sxs-lookup"><span data-stu-id="c6bdd-125">Row index:</span></span>  <br/> |<span data-ttu-id="c6bdd-126">**visRowGroup**</span><span class="sxs-lookup"><span data-stu-id="c6bdd-126">**visRowGroup**</span></span> <br/> |
|<span data-ttu-id="c6bdd-127">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="c6bdd-127">Cell index:</span></span>  <br/> |<span data-ttu-id="c6bdd-128">**visGroupDisplayMode**</span><span class="sxs-lookup"><span data-stu-id="c6bdd-128">**visGroupDisplayMode**</span></span> <br/> |
   

