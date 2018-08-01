---
title: IsDropSource 单元格（“Miscellaneous”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm490
localization_priority: Normal
ms.assetid: 3b20e6ef-f1ac-5bb0-5ac3-4df3ae5e9bf9
description: 确定是否能通过将一个形状拖放到组合中的方法将形状添加到组合中。
ms.openlocfilehash: f2edfcb7cf9d21b2ecd97b335b07f30233903d5b
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780470"
---
# <a name="isdropsource-cell-miscellaneous-section"></a><span data-ttu-id="c6ff6-103">IsDropSource 单元格（“Miscellaneous”部分）</span><span class="sxs-lookup"><span data-stu-id="c6ff6-103">IsDropSource Cell (Miscellaneous Section)</span></span>

<span data-ttu-id="c6ff6-104">确定是否能通过将一个形状拖放到组合中的方法将形状添加到组合中。</span><span class="sxs-lookup"><span data-stu-id="c6ff6-104">Determines whether the shape can be added to a group by dropping it onto the group.</span></span>
  
|<span data-ttu-id="c6ff6-105">**值**</span><span class="sxs-lookup"><span data-stu-id="c6ff6-105">**Value**</span></span>|<span data-ttu-id="c6ff6-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="c6ff6-106">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c6ff6-107">TRUE</span><span class="sxs-lookup"><span data-stu-id="c6ff6-107">TRUE</span></span>  <br/> |<span data-ttu-id="c6ff6-108">可以通过将一个形状拖放到组合中的方法将形状添加到组合中。</span><span class="sxs-lookup"><span data-stu-id="c6ff6-108">Can add the shape to a group by dropping it onto the group.</span></span>  <br/> |
|<span data-ttu-id="c6ff6-109">FALSE</span><span class="sxs-lookup"><span data-stu-id="c6ff6-109">FALSE</span></span>  <br/> |<span data-ttu-id="c6ff6-110">不能将形状添加到组合中。</span><span class="sxs-lookup"><span data-stu-id="c6ff6-110">Cannot add the shape to a group.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="c6ff6-111">注解</span><span class="sxs-lookup"><span data-stu-id="c6ff6-111">Remarks</span></span>

<span data-ttu-id="c6ff6-112">您还可以采用以下方法设置此值：选择该形状，在[“开发工具”](run-in-developer-mode-display-the-developer-tab.md)选项卡上单击 **“行为”**，然后选中 **“放下时将形状添加到组合”** 复选框。</span><span class="sxs-lookup"><span data-stu-id="c6ff6-112">You can also set this value by selecting the shape, clicking **Behavior** on the [Developer](run-in-developer-mode-display-the-developer-tab.md) tab, and then selecting the **Add shape to groups on drop** check box.</span></span> 
  
<span data-ttu-id="c6ff6-p101">除了要为形状启用此行为，您还必须让组合可以接受拖入其中的形状。为此，请选择该组合，在[“开发工具”](run-in-developer-mode-display-the-developer-tab.md)选项卡上单击 **“行为”**，然后选中 **“接受放下的形状”** 复选框。此值将存储在“Group Properties”内容的 IsDropTarget 单元格中。</span><span class="sxs-lookup"><span data-stu-id="c6ff6-p101">In addition to enabling this behavior for a shape, you must also enable a group to accept shapes that are dragged into it. To do so, select the group, click **Behavior** on the [Developer](run-in-developer-mode-display-the-developer-tab.md) tab, and then select the **Accept dropped shapes** check box. This value is stored in the IsDropTarget cell in the Group Properties section.</span></span> 
  
<span data-ttu-id="c6ff6-116">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 IsDropSource 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="c6ff6-116">To get a reference to the IsDropSource cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="c6ff6-117">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="c6ff6-117">Cell name:</span></span>  <br/> |<span data-ttu-id="c6ff6-118">IsDropSource</span><span class="sxs-lookup"><span data-stu-id="c6ff6-118">IsDropSource</span></span>  <br/> |
   
<span data-ttu-id="c6ff6-119">若要从某个程序按索引获取对 IsDropSource 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="c6ff6-119">To get a reference to the IsDropSource cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="c6ff6-120">内容索引：</span><span class="sxs-lookup"><span data-stu-id="c6ff6-120">Section index:</span></span>  <br/> |<span data-ttu-id="c6ff6-121">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="c6ff6-121">**visSectionObject**</span></span> <br/> |
|<span data-ttu-id="c6ff6-122">行索引：</span><span class="sxs-lookup"><span data-stu-id="c6ff6-122">Row index:</span></span>  <br/> |<span data-ttu-id="c6ff6-123">**visRowMisc**</span><span class="sxs-lookup"><span data-stu-id="c6ff6-123">**visRowMisc**</span></span> <br/> |
|<span data-ttu-id="c6ff6-124">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="c6ff6-124">Cell index:</span></span>  <br/> |<span data-ttu-id="c6ff6-125">**visDropSource**</span><span class="sxs-lookup"><span data-stu-id="c6ff6-125">**visDropSource**</span></span> <br/> |
   

