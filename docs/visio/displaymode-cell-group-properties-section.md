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
ms.openlocfilehash: 086685b47d8eaf170a8722f7cd00545230541e79
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780100"
---
# <a name="displaymode-cell-group-properties-section"></a><span data-ttu-id="97654-103">DisplayMode 单元格（“Group Properties”部分）</span><span class="sxs-lookup"><span data-stu-id="97654-103">DisplayMode Cell (Group Properties Section)</span></span>

<span data-ttu-id="97654-104">确定组合形状及其成员的显示方式。</span><span class="sxs-lookup"><span data-stu-id="97654-104">Determines how the group shape and its members are displayed.</span></span>
  
|<span data-ttu-id="97654-105">**值**</span><span class="sxs-lookup"><span data-stu-id="97654-105">**Value**</span></span>|<span data-ttu-id="97654-106">**显示模式**</span><span class="sxs-lookup"><span data-stu-id="97654-106">**Display Mode**</span></span>|<span data-ttu-id="97654-107">**自动常量**</span><span class="sxs-lookup"><span data-stu-id="97654-107">**Automation constant**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="97654-108">0</span><span class="sxs-lookup"><span data-stu-id="97654-108">0</span></span>  <br/> |<span data-ttu-id="97654-109">隐藏组合形状和文本。</span><span class="sxs-lookup"><span data-stu-id="97654-109">Hides the group shape and text.</span></span>  <br/> |<span data-ttu-id="97654-110">**visGrpDispModeNone**</span><span class="sxs-lookup"><span data-stu-id="97654-110">**visGrpDispModeNone**</span></span> <br/> |
|<span data-ttu-id="97654-111">1</span><span class="sxs-lookup"><span data-stu-id="97654-111">1</span></span>  <br/> |<span data-ttu-id="97654-112">将组合形状显示在成员形状后面。</span><span class="sxs-lookup"><span data-stu-id="97654-112">Displays the group shape behind member shapes.</span></span>  <br/> |<span data-ttu-id="97654-113">**visGrpDispModeBack**</span><span class="sxs-lookup"><span data-stu-id="97654-113">**visGrpDispModeBack**</span></span> <br/> |
|<span data-ttu-id="97654-114">2</span><span class="sxs-lookup"><span data-stu-id="97654-114">2</span></span>  <br/> |<span data-ttu-id="97654-115">将组合形状显示在成员形状的前面。</span><span class="sxs-lookup"><span data-stu-id="97654-115">Displays the group shape in front of member shapes.</span></span>  <br/> |<span data-ttu-id="97654-116">**visGrpDispModeFront**</span><span class="sxs-lookup"><span data-stu-id="97654-116">**visGrpDispModeFront**</span></span> <br/> |
   
## <a name="remarks"></a><span data-ttu-id="97654-117">说明</span><span class="sxs-lookup"><span data-stu-id="97654-117">Remarks</span></span>

<span data-ttu-id="97654-118">您还可以设置此值选择该组合，单击**行为**在[开发人员](run-in-developer-mode-display-the-developer-tab.md)选项卡上的**形状设计**组，然后从**组数据**列表中选择的显示模式。</span><span class="sxs-lookup"><span data-stu-id="97654-118">You can also set this value by selecting the group, clicking **Behavior** on the **Shape Design** group on the [Developer](run-in-developer-mode-display-the-developer-tab.md) tab, and then selecting a display mode from the **Group data** list.</span></span> 
  
<span data-ttu-id="97654-119">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 DisplayMode 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="97654-119">To get a reference to the DisplayMode cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="97654-120">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="97654-120">Cell name:</span></span>  <br/> |<span data-ttu-id="97654-121">DisplayMode</span><span class="sxs-lookup"><span data-stu-id="97654-121">DisplayMode</span></span>  <br/> |
   
<span data-ttu-id="97654-122">若要从某个程序按索引获取对 DisplayMode 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="97654-122">To get a reference to the DisplayMode cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="97654-123">内容索引：</span><span class="sxs-lookup"><span data-stu-id="97654-123">Section index:</span></span>  <br/> |<span data-ttu-id="97654-124">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="97654-124">**visSectionObject**</span></span> <br/> |
|<span data-ttu-id="97654-125">行索引：</span><span class="sxs-lookup"><span data-stu-id="97654-125">Row index:</span></span>  <br/> |<span data-ttu-id="97654-126">**visRowGroup**</span><span class="sxs-lookup"><span data-stu-id="97654-126">**visRowGroup**</span></span> <br/> |
|<span data-ttu-id="97654-127">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="97654-127">Cell index:</span></span>  <br/> |<span data-ttu-id="97654-128">**visGroupDisplayMode**</span><span class="sxs-lookup"><span data-stu-id="97654-128">**visGroupDisplayMode**</span></span> <br/> |
   

