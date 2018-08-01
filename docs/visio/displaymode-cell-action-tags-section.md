---
title: DisplayMode 单元格（“Action Tags”部分）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm60039
localization_priority: Normal
ms.assetid: 0dfad40b-f97e-0c4a-2102-7344d1317b82
description: 确定动作标记是否显示用户将指针移到标记上时，选择形状后，或所有的时间。
ms.openlocfilehash: 4cb0666ca8de28247309de4fc0d2ff23e8b37d8a
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780088"
---
# <a name="displaymode-cell-action-tags-section"></a><span data-ttu-id="6a8b1-103">DisplayMode 单元格（“Action Tags”部分）</span><span class="sxs-lookup"><span data-stu-id="6a8b1-103">DisplayMode Cell (Action Tags Section)</span></span>

<span data-ttu-id="6a8b1-104">确定动作标记是否显示用户将指针移到标记上时，选择形状后，或所有的时间。</span><span class="sxs-lookup"><span data-stu-id="6a8b1-104">Determines whether the action tag appears when the user moves the pointer over the tag, when the shape is selected, or all the time.</span></span>
  
> [!NOTE]
> <span data-ttu-id="6a8b1-105">在以前版本的 Microsoft Visio 中，动作标记称为“智能标记”。</span><span class="sxs-lookup"><span data-stu-id="6a8b1-105">In previous versions of Microsoft Visio, action tags are called smart tags.</span></span> 
  
|<span data-ttu-id="6a8b1-106">**值**</span><span class="sxs-lookup"><span data-stu-id="6a8b1-106">**Value**</span></span>|<span data-ttu-id="6a8b1-107">**显示模式**</span><span class="sxs-lookup"><span data-stu-id="6a8b1-107">**Display Mode**</span></span>|<span data-ttu-id="6a8b1-108">**自动常量**</span><span class="sxs-lookup"><span data-stu-id="6a8b1-108">**Automation constant**</span></span>|
|:-----|:-----|:-----|
| <span data-ttu-id="6a8b1-109">0</span><span class="sxs-lookup"><span data-stu-id="6a8b1-109">0</span></span>  <br/> | <span data-ttu-id="6a8b1-110">鼠标悬停标记 （默认值） 时出现。</span><span class="sxs-lookup"><span data-stu-id="6a8b1-110">Appears when the mouse is paused over the tag (the default).</span></span>  <br/> |<span data-ttu-id="6a8b1-111">**visSmartTagDispModeMouseOver**</span><span class="sxs-lookup"><span data-stu-id="6a8b1-111">**visSmartTagDispModeMouseOver**</span></span> <br/> |
| <span data-ttu-id="6a8b1-112">1</span><span class="sxs-lookup"><span data-stu-id="6a8b1-112">1</span></span>  <br/> | <span data-ttu-id="6a8b1-113">选择形状后显示。</span><span class="sxs-lookup"><span data-stu-id="6a8b1-113">Appears while the shape is selected.</span></span>  <br/> |<span data-ttu-id="6a8b1-114">**visSmartTagDispModeShapeSelected**</span><span class="sxs-lookup"><span data-stu-id="6a8b1-114">**visSmartTagDispModeShapeSelected**</span></span> <br/> |
| <span data-ttu-id="6a8b1-115">2</span><span class="sxs-lookup"><span data-stu-id="6a8b1-115">2</span></span>  <br/> | <span data-ttu-id="6a8b1-116">始终显示。</span><span class="sxs-lookup"><span data-stu-id="6a8b1-116">Appears all the time.</span></span>  <br/> |<span data-ttu-id="6a8b1-117">**visSmartTagDispModeAlways**</span><span class="sxs-lookup"><span data-stu-id="6a8b1-117">**visSmartTagDispModeAlways**</span></span> <br/> |
   
## <a name="remarks"></a><span data-ttu-id="6a8b1-118">注解</span><span class="sxs-lookup"><span data-stu-id="6a8b1-118">Remarks</span></span>

<span data-ttu-id="6a8b1-119">打印输出或发布输出上不显示动作标记。</span><span class="sxs-lookup"><span data-stu-id="6a8b1-119">Action tags do not appear on printed or published output.</span></span> 
  
<span data-ttu-id="6a8b1-120">如果为某一页定义了动作标记，并且此单元格包含值 1，则此标记永远也不会显示，因为不能选择页。</span><span class="sxs-lookup"><span data-stu-id="6a8b1-120">If an action tag is defined for a page, and this cell contains a value of 1, the tag never appears because a page cannot be selected.</span></span> 
  
<span data-ttu-id="6a8b1-121">若要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 DisplayMode 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="6a8b1-121">To get a reference to the DisplayMode cell by name from another formula, or from a program by using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="6a8b1-122">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="6a8b1-122">Cell name:</span></span>  <br/> | <span data-ttu-id="6a8b1-123">智能标记。</span><span class="sxs-lookup"><span data-stu-id="6a8b1-123">SmartTags.</span></span>  <span data-ttu-id="6a8b1-124">*名称*。DisplayMode 其中智能标记。</span><span class="sxs-lookup"><span data-stu-id="6a8b1-124">*name*  .DisplayMode           where SmartTags.</span></span> <span data-ttu-id="6a8b1-125">*name*是动作标记行的名称</span><span class="sxs-lookup"><span data-stu-id="6a8b1-125">*name*  is the name of the action tag row</span></span>  <br/> |
   
<span data-ttu-id="6a8b1-126">若要从某个程序按索引获取对 DisplayMode 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="6a8b1-126">To get a reference to the DisplayMode cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="6a8b1-127">内容索引：</span><span class="sxs-lookup"><span data-stu-id="6a8b1-127">Section index:</span></span>  <br/> |<span data-ttu-id="6a8b1-128">**visSectionSmartTag**</span><span class="sxs-lookup"><span data-stu-id="6a8b1-128">**visSectionSmartTag**</span></span> <br/> |
| <span data-ttu-id="6a8b1-129">行索引：</span><span class="sxs-lookup"><span data-stu-id="6a8b1-129">Row index:</span></span>  <br/> |<span data-ttu-id="6a8b1-130">**visRowSmartTag** +  *i*其中*i* = 0、 1、 2...</span><span class="sxs-lookup"><span data-stu-id="6a8b1-130">**visRowSmartTag** +  *i*            where  *i*  = 0, 1, 2...</span></span>  <br/> |
| <span data-ttu-id="6a8b1-131">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="6a8b1-131">Cell index:</span></span>  <br/> |<span data-ttu-id="6a8b1-132">**visSmartTagDisplayMode**</span><span class="sxs-lookup"><span data-stu-id="6a8b1-132">**visSmartTagDisplayMode**</span></span> <br/> |
   

