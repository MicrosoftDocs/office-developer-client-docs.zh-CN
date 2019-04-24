---
title: SelectMode 单元格（“Group Properties”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm875
localization_priority: Normal
ms.assetid: 5ba68e05-f394-d7b7-390d-f0a9fdad011e
description: 确定如何选择组合形状及其组成部分。
ms.openlocfilehash: 82f9e2806d1131a0acfd064f585c681fef0f209f
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32326010"
---
# <a name="selectmode-cell-group-properties-section"></a><span data-ttu-id="23a42-103">SelectMode 单元格（“Group Properties”内容）</span><span class="sxs-lookup"><span data-stu-id="23a42-103">SelectMode Cell (Group Properties Section)</span></span>

<span data-ttu-id="23a42-104">确定如何选择组合形状及其组成部分。</span><span class="sxs-lookup"><span data-stu-id="23a42-104">Determines how you select a group shape and its members.</span></span>
  
|<span data-ttu-id="23a42-105">**值**</span><span class="sxs-lookup"><span data-stu-id="23a42-105">**Value**</span></span>|<span data-ttu-id="23a42-106">**选择方式**</span><span class="sxs-lookup"><span data-stu-id="23a42-106">**Selection mode**</span></span>|<span data-ttu-id="23a42-107">**自动常量**</span><span class="sxs-lookup"><span data-stu-id="23a42-107">**Automation constant**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="23a42-108">0</span><span class="sxs-lookup"><span data-stu-id="23a42-108">0</span></span>  <br/> |<span data-ttu-id="23a42-109">仅选择组合形状。</span><span class="sxs-lookup"><span data-stu-id="23a42-109">Select the group shape only.</span></span>  <br/> |<span data-ttu-id="23a42-110">**visGrpSelModeGroupOnly**</span><span class="sxs-lookup"><span data-stu-id="23a42-110">**visGrpSelModeGroupOnly**</span></span> <br/> |
|<span data-ttu-id="23a42-111">1</span><span class="sxs-lookup"><span data-stu-id="23a42-111">1</span></span>  <br/> |<span data-ttu-id="23a42-112">首先选择组合形状。</span><span class="sxs-lookup"><span data-stu-id="23a42-112">Select the group shape first.</span></span>  <br/> |<span data-ttu-id="23a42-113">**visGrpSelModeGroup1st**</span><span class="sxs-lookup"><span data-stu-id="23a42-113">**visGrpSelModeGroup1st**</span></span> <br/> |
|<span data-ttu-id="23a42-114">双面</span><span class="sxs-lookup"><span data-stu-id="23a42-114">2</span></span>  <br/> |<span data-ttu-id="23a42-115">首先选择组合的组成部分。</span><span class="sxs-lookup"><span data-stu-id="23a42-115">Select the members of the group first.</span></span>  <br/> |<span data-ttu-id="23a42-116">**visGrpSelModeMembers1st**</span><span class="sxs-lookup"><span data-stu-id="23a42-116">**visGrpSelModeMembers1st**</span></span> <br/> |
   
## <a name="remarks"></a><span data-ttu-id="23a42-117">注解</span><span class="sxs-lookup"><span data-stu-id="23a42-117">Remarks</span></span>

<span data-ttu-id="23a42-118">您还可以在 "**行为**" 对话框中设置此值 (在 "组" 形状处于选中状态的 "[开发工具](run-in-developer-mode-display-the-developer-tab.md)" 选项卡上的 "**形状设计**" 组中, 单击 "**行为**", 然后单击 "组" 下**选择**列表中的模式**行为**)。</span><span class="sxs-lookup"><span data-stu-id="23a42-118">You can also set this value in the **Behavior** dialog box (with the group shape selected, on the [Developer](run-in-developer-mode-display-the-developer-tab.md) tab, in the **Shape Design** group, click **Behavior**, and then click a mode in the **Selection** list under **Group Behavior** ).</span></span> 
  
<span data-ttu-id="23a42-119">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 SelectMode 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="23a42-119">To get a reference to the SelectMode cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="23a42-120">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="23a42-120">Cell name:</span></span>  <br/> |<span data-ttu-id="23a42-121">SelectMode</span><span class="sxs-lookup"><span data-stu-id="23a42-121">SelectMode</span></span>  <br/> |
   
<span data-ttu-id="23a42-122">若要从某个程序按索引获取对 SelectMode 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="23a42-122">To get a reference to the SelectMode cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="23a42-123">内容索引：</span><span class="sxs-lookup"><span data-stu-id="23a42-123">Section index:</span></span>  <br/> |<span data-ttu-id="23a42-124">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="23a42-124">**visSectionObject**</span></span> <br/> |
|<span data-ttu-id="23a42-125">行索引：</span><span class="sxs-lookup"><span data-stu-id="23a42-125">Row index:</span></span>  <br/> |<span data-ttu-id="23a42-126">**visRowGroup**</span><span class="sxs-lookup"><span data-stu-id="23a42-126">**visRowGroup**</span></span> <br/> |
|<span data-ttu-id="23a42-127">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="23a42-127">Cell index:</span></span>  <br/> |<span data-ttu-id="23a42-128">**visGroupSelectMode**</span><span class="sxs-lookup"><span data-stu-id="23a42-128">**visGroupSelectMode**</span></span> <br/> |
   

