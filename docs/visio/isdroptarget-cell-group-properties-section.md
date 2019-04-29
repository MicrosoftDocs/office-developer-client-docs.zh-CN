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
ms.openlocfilehash: 50f545b3cbd4f7e1541a7f5e8ca32c34d0429c5e
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33410789"
---
# <a name="isdroptarget-cell-group-properties-section"></a><span data-ttu-id="e9423-103">IsDropTarget 单元格（“Group Properties”内容）</span><span class="sxs-lookup"><span data-stu-id="e9423-103">IsDropTarget Cell (Group Properties Section)</span></span>

<span data-ttu-id="e9423-104">确定组合是否允许您通过将形状放在该组合上来添加形状。</span><span class="sxs-lookup"><span data-stu-id="e9423-104">Determines whether the group allows you to add a shape to it by dropping it on the group.</span></span>
  
|<span data-ttu-id="e9423-105">**值**</span><span class="sxs-lookup"><span data-stu-id="e9423-105">**Value**</span></span>|<span data-ttu-id="e9423-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="e9423-106">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e9423-107">TRUE</span><span class="sxs-lookup"><span data-stu-id="e9423-107">TRUE</span></span>  <br/> |<span data-ttu-id="e9423-108">可以通过将形状放在组合上来将形状添加到其中。</span><span class="sxs-lookup"><span data-stu-id="e9423-108">Can add a shape to the group by dropping it onto the group.</span></span>  <br/> |
|<span data-ttu-id="e9423-109">FALSE</span><span class="sxs-lookup"><span data-stu-id="e9423-109">FALSE</span></span>  <br/> |<span data-ttu-id="e9423-110">不能将形状拖放在组合上。</span><span class="sxs-lookup"><span data-stu-id="e9423-110">Cannot drop shape onto the group.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="e9423-111">说明</span><span class="sxs-lookup"><span data-stu-id="e9423-111">Remarks</span></span>

<span data-ttu-id="e9423-112">您还可以采用以下方法设置此值：选择该组合，在[“开发工具”](run-in-developer-mode-display-the-developer-tab.md)选项卡上单击 **“行为”**，然后选中 **“接受放下的形状”** 复选框。</span><span class="sxs-lookup"><span data-stu-id="e9423-112">You can also set this value by selecting the group, clicking **Behavior** on the [Developer](run-in-developer-mode-display-the-developer-tab.md) tab, and then selecting the **Accept dropped shapes** check box.</span></span> 
  
<span data-ttu-id="e9423-p101">若要通过将形状拖放到组合中的方法将形状添加到组合中，您还必须启用类似的形状行为。您必须选择该形状，在[“开发工具”](run-in-developer-mode-display-the-developer-tab.md)选项卡上单击 **“行为”**，然后选中 **“放下时将形状添加到组合”** 复选框。此值将存储在“Miscellaneous”内容中的 IsDropSource 单元格中。</span><span class="sxs-lookup"><span data-stu-id="e9423-p101">To add a shape to a group by dropping it on the group, you must also enable similar shape behavior. You must select the shape, click **Behavior** on the [Developer](run-in-developer-mode-display-the-developer-tab.md) tab, and then select the **Add shape to groups on drop** check box. This value is stored in the IsDropSource cell in the Miscellaneous section.</span></span> 
  
<span data-ttu-id="e9423-116">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 IsDropTarget 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="e9423-116">To get a reference to the IsDropTarget cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="e9423-117">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="e9423-117">Cell name:</span></span>  <br/> |<span data-ttu-id="e9423-118">IsDropTarget</span><span class="sxs-lookup"><span data-stu-id="e9423-118">IsDropTarget</span></span>  <br/> |
   
<span data-ttu-id="e9423-119">若要从某个程序按索引获取对 IsDropTarget 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="e9423-119">To get a reference to the IsDropTarget cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="e9423-120">内容索引：</span><span class="sxs-lookup"><span data-stu-id="e9423-120">Section index:</span></span>  <br/> |<span data-ttu-id="e9423-121">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="e9423-121">**visSectionObject**</span></span> <br/> |
|<span data-ttu-id="e9423-122">行索引：</span><span class="sxs-lookup"><span data-stu-id="e9423-122">Row index:</span></span>  <br/> |<span data-ttu-id="e9423-123">**visRowGroup**</span><span class="sxs-lookup"><span data-stu-id="e9423-123">**visRowGroup**</span></span> <br/> |
|<span data-ttu-id="e9423-124">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="e9423-124">Cell index:</span></span>  <br/> |<span data-ttu-id="e9423-125">**visGroupIsDropTarget**</span><span class="sxs-lookup"><span data-stu-id="e9423-125">**visGroupIsDropTarget**</span></span> <br/> |
   

