---
title: DisplayMode 单元格 ("Action Tags" 内容)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm60039
localization_priority: Normal
ms.assetid: 0dfad40b-f97e-0c4a-2102-7344d1317b82
description: 决定当用户将鼠标指针移到标记上时、选择形状时, 还是在所有时间都显示动作标记。
ms.openlocfilehash: 0254ad361c63dfdeddaf8a1c2173e99aa1c05398
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33415815"
---
# <a name="displaymode-cell-action-tags-section"></a><span data-ttu-id="89d3d-103">DisplayMode 单元格 ("Action Tags" 内容)</span><span class="sxs-lookup"><span data-stu-id="89d3d-103">DisplayMode Cell (Action Tags Section)</span></span>

<span data-ttu-id="89d3d-104">决定当用户将鼠标指针移到标记上时、选择形状时, 还是在所有时间都显示动作标记。</span><span class="sxs-lookup"><span data-stu-id="89d3d-104">Determines whether the action tag appears when the user moves the pointer over the tag, when the shape is selected, or all the time.</span></span>
  
> [!NOTE]
> <span data-ttu-id="89d3d-105">在以前版本的 Microsoft Visio 中，动作标记称为“智能标记”。</span><span class="sxs-lookup"><span data-stu-id="89d3d-105">In previous versions of Microsoft Visio, action tags are called smart tags.</span></span> 
  
|<span data-ttu-id="89d3d-106">**值**</span><span class="sxs-lookup"><span data-stu-id="89d3d-106">**Value**</span></span>|<span data-ttu-id="89d3d-107">**显示模式**</span><span class="sxs-lookup"><span data-stu-id="89d3d-107">**Display Mode**</span></span>|<span data-ttu-id="89d3d-108">**自动常量**</span><span class="sxs-lookup"><span data-stu-id="89d3d-108">**Automation constant**</span></span>|
|:-----|:-----|:-----|
| <span data-ttu-id="89d3d-109">0</span><span class="sxs-lookup"><span data-stu-id="89d3d-109">0</span></span>  <br/> | <span data-ttu-id="89d3d-110">当鼠标停留在标记上时显示 (默认值)。</span><span class="sxs-lookup"><span data-stu-id="89d3d-110">Appears when the mouse is paused over the tag (the default).</span></span>  <br/> |<span data-ttu-id="89d3d-111">**visSmartTagDispModeMouseOver**</span><span class="sxs-lookup"><span data-stu-id="89d3d-111">**visSmartTagDispModeMouseOver**</span></span> <br/> |
| <span data-ttu-id="89d3d-112">1</span><span class="sxs-lookup"><span data-stu-id="89d3d-112">1</span></span>  <br/> | <span data-ttu-id="89d3d-113">选择形状后显示。</span><span class="sxs-lookup"><span data-stu-id="89d3d-113">Appears while the shape is selected.</span></span>  <br/> |<span data-ttu-id="89d3d-114">**visSmartTagDispModeShapeSelected**</span><span class="sxs-lookup"><span data-stu-id="89d3d-114">**visSmartTagDispModeShapeSelected**</span></span> <br/> |
| <span data-ttu-id="89d3d-115">双面</span><span class="sxs-lookup"><span data-stu-id="89d3d-115">2</span></span>  <br/> | <span data-ttu-id="89d3d-116">始终显示。</span><span class="sxs-lookup"><span data-stu-id="89d3d-116">Appears all the time.</span></span>  <br/> |<span data-ttu-id="89d3d-117">**visSmartTagDispModeAlways**</span><span class="sxs-lookup"><span data-stu-id="89d3d-117">**visSmartTagDispModeAlways**</span></span> <br/> |
   
## <a name="remarks"></a><span data-ttu-id="89d3d-118">说明</span><span class="sxs-lookup"><span data-stu-id="89d3d-118">Remarks</span></span>

<span data-ttu-id="89d3d-119">打印输出或发布输出上不显示动作标记。</span><span class="sxs-lookup"><span data-stu-id="89d3d-119">Action tags do not appear on printed or published output.</span></span> 
  
<span data-ttu-id="89d3d-120">如果为某一页定义了动作标记，并且此单元格包含值 1，则此标记永远也不会显示，因为不能选择页。</span><span class="sxs-lookup"><span data-stu-id="89d3d-120">If an action tag is defined for a page, and this cell contains a value of 1, the tag never appears because a page cannot be selected.</span></span> 
  
<span data-ttu-id="89d3d-121">若要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 DisplayMode 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="89d3d-121">To get a reference to the DisplayMode cell by name from another formula, or from a program by using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="89d3d-122">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="89d3d-122">Cell name:</span></span>  <br/> | <span data-ttu-id="89d3d-123">SmartTags.</span><span class="sxs-lookup"><span data-stu-id="89d3d-123">SmartTags.</span></span>  <span data-ttu-id="89d3d-124">*名称*。DisplayMode 其中的智能标记。</span><span class="sxs-lookup"><span data-stu-id="89d3d-124">*name*  .DisplayMode           where SmartTags.</span></span> <span data-ttu-id="89d3d-125">*name*是操作标记行的名称</span><span class="sxs-lookup"><span data-stu-id="89d3d-125">*name*  is the name of the action tag row</span></span>  <br/> |
   
<span data-ttu-id="89d3d-126">要从某个程序按索引获取对 DisplayMode 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="89d3d-126">To get a reference to the DisplayMode cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="89d3d-127">内容索引：</span><span class="sxs-lookup"><span data-stu-id="89d3d-127">Section index:</span></span>  <br/> |<span data-ttu-id="89d3d-128">**visSectionSmartTag**</span><span class="sxs-lookup"><span data-stu-id="89d3d-128">**visSectionSmartTag**</span></span> <br/> |
| <span data-ttu-id="89d3d-129">行索引：</span><span class="sxs-lookup"><span data-stu-id="89d3d-129">Row index:</span></span>  <br/> |<span data-ttu-id="89d3d-130">**visRowSmartTag** +  *i* = \*\* 0、1、2 .。。</span><span class="sxs-lookup"><span data-stu-id="89d3d-130">**visRowSmartTag** +  *i*            where  *i*  = 0, 1, 2...</span></span>  <br/> |
| <span data-ttu-id="89d3d-131">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="89d3d-131">Cell index:</span></span>  <br/> |<span data-ttu-id="89d3d-132">**visSmartTagDisplayMode**</span><span class="sxs-lookup"><span data-stu-id="89d3d-132">**visSmartTagDisplayMode**</span></span> <br/> |
   

