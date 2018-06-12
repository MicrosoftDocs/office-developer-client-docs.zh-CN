---
title: IsDropTarget 单元格（“Group Properties”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm495
localization_priority: Normal
ms.assetid: 8140fc7b-b99c-54bb-7af3-7de6fcdae7d3
description: 确定组合是否允许您通过将形状放在该组合上来添加形状。
ms.openlocfilehash: 326ead15bcdc72797853daee797d8f08d459a638
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780480"
---
# <a name="isdroptarget-cell-group-properties-section"></a><span data-ttu-id="92d22-103">IsDropTarget 单元格（“Group Properties”内容）</span><span class="sxs-lookup"><span data-stu-id="92d22-103">IsDropTarget Cell (Group Properties Section)</span></span>

<span data-ttu-id="92d22-104">确定组合是否允许您通过将形状放在该组合上来添加形状。</span><span class="sxs-lookup"><span data-stu-id="92d22-104">Determines whether the group allows you to add a shape to it by dropping it on the group.</span></span>
  
|<span data-ttu-id="92d22-105">**值**</span><span class="sxs-lookup"><span data-stu-id="92d22-105">**Value**</span></span>|<span data-ttu-id="92d22-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="92d22-106">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="92d22-107">TRUE</span><span class="sxs-lookup"><span data-stu-id="92d22-107">TRUE</span></span>  <br/> |<span data-ttu-id="92d22-108">可以通过将形状放在组合上来将形状添加到其中。</span><span class="sxs-lookup"><span data-stu-id="92d22-108">Can add a shape to the group by dropping it onto the group.</span></span>  <br/> |
|<span data-ttu-id="92d22-109">FALSE</span><span class="sxs-lookup"><span data-stu-id="92d22-109">FALSE</span></span>  <br/> |<span data-ttu-id="92d22-110">不能将形状拖放在组合上。</span><span class="sxs-lookup"><span data-stu-id="92d22-110">Cannot drop shape onto the group.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="92d22-111">注解</span><span class="sxs-lookup"><span data-stu-id="92d22-111">Remarks</span></span>

<span data-ttu-id="92d22-112">您可以通过选择的组中，单击**行为**[开发人员](run-in-developer-mode-display-the-developer-tab.md)选项卡，然后选择**接受放下的形状**复选框来设置此值。</span><span class="sxs-lookup"><span data-stu-id="92d22-112">You can also set this value by selecting the group, clicking **Behavior** on the [Developer](run-in-developer-mode-display-the-developer-tab.md) tab, and then selecting the **Accept dropped shapes** check box.</span></span> 
  
<span data-ttu-id="92d22-113">删除组，将其添加到一组形状，还必须启用类似的形状行为。</span><span class="sxs-lookup"><span data-stu-id="92d22-113">To add a shape to a group by dropping it on the group, you must also enable similar shape behavior.</span></span> <span data-ttu-id="92d22-114">您必须选择的形状，在[开发人员](run-in-developer-mode-display-the-developer-tab.md)选项卡上，单击**行为**，然后选择**添加到下拉组合形状**复选框。</span><span class="sxs-lookup"><span data-stu-id="92d22-114">You must select the shape, click **Behavior** on the [Developer](run-in-developer-mode-display-the-developer-tab.md) tab, and then select the **Add shape to groups on drop** check box.</span></span> <span data-ttu-id="92d22-115">此值存储在杂项部分的 IsDropSource 单元格。</span><span class="sxs-lookup"><span data-stu-id="92d22-115">This value is stored in the IsDropSource cell in the Miscellaneous section.</span></span> 
  
<span data-ttu-id="92d22-116">要从另一个公式或使用**CellsU**属性从某个程序按名称获取对 IsDropTarget 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="92d22-116">To get a reference to the IsDropTarget cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="92d22-117">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="92d22-117">Cell name:</span></span>  <br/> |<span data-ttu-id="92d22-118">IsDropTarget</span><span class="sxs-lookup"><span data-stu-id="92d22-118">IsDropTarget</span></span>  <br/> |
   
<span data-ttu-id="92d22-119">若要从某个程序按索引获取对 IsDropTarget 单元格的引用，请使用带下列参数的**CellsSRC**属性：</span><span class="sxs-lookup"><span data-stu-id="92d22-119">To get a reference to the IsDropTarget cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="92d22-120">内容索引：</span><span class="sxs-lookup"><span data-stu-id="92d22-120">Section index:</span></span>  <br/> |<span data-ttu-id="92d22-121">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="92d22-121">**visSectionObject**</span></span> <br/> |
|<span data-ttu-id="92d22-122">行索引：</span><span class="sxs-lookup"><span data-stu-id="92d22-122">Row index:</span></span>  <br/> |<span data-ttu-id="92d22-123">**visRowGroup**</span><span class="sxs-lookup"><span data-stu-id="92d22-123">**visRowGroup**</span></span> <br/> |
|<span data-ttu-id="92d22-124">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="92d22-124">Cell index:</span></span>  <br/> |<span data-ttu-id="92d22-125">**visGroupIsDropTarget**</span><span class="sxs-lookup"><span data-stu-id="92d22-125">**visGroupIsDropTarget**</span></span> <br/> |
   

