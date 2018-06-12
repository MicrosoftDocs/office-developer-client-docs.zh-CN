---
title: SortKey 单元格（“Actions”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm1027286
localization_priority: Normal
ms.assetid: c0c4b668-f31b-336f-4434-e94a4804ff7c
description: 确定动作在快捷菜单或动作标记菜单上显示的顺序的数字。
ms.openlocfilehash: 5a5db1276d1f2544b5b2b76301c30a2bedd4be63
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781431"
---
# <a name="sortkey-cell-actions-section"></a><span data-ttu-id="fd811-103">SortKey 单元格（“Actions”内容）</span><span class="sxs-lookup"><span data-stu-id="fd811-103">SortKey Cell (Actions Section)</span></span>

<span data-ttu-id="fd811-104">确定动作在快捷菜单或动作标记菜单上显示的顺序的数字。</span><span class="sxs-lookup"><span data-stu-id="fd811-104">A number that determines the order of actions that appear on a shortcut or action tag menu.</span></span>
  
> [!NOTE]
> <span data-ttu-id="fd811-105">在以前版本的 Microsoft Visio 中，动作标记称为“智能标记”。</span><span class="sxs-lookup"><span data-stu-id="fd811-105">In previous versions of Microsoft Visio, action tags are called smart tags.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="fd811-106">注解</span><span class="sxs-lookup"><span data-stu-id="fd811-106">Remarks</span></span>

<span data-ttu-id="fd811-p101">动作按照从低到高的顺序在动作标记菜单或快捷菜单上显示，最低的数字显示在菜单的顶部。如果两个动作行具有相同的 SortKey 单元格值，则顺序由物理行顺序确定。默认值为 0（零）。</span><span class="sxs-lookup"><span data-stu-id="fd811-p101">The actions on an action tag or shortcut menu appear on the menu sorted from lowest to highest, with lower numbers appearing at the top of the menu. If two action rows have the same SortKey cell value, the order is determined by physical row order. The default is 0 (zero).</span></span>
  
<span data-ttu-id="fd811-110">若要获取对 SortKey 单元格的引用按名称从另一个公式或从程序使用**CellsU**属性，请使用：</span><span class="sxs-lookup"><span data-stu-id="fd811-110">To get a reference to the SortKey cell by name from another formula, or from a program by using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="fd811-111">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="fd811-111">Cell name:</span></span>  <br/> |<span data-ttu-id="fd811-112">操作。</span><span class="sxs-lookup"><span data-stu-id="fd811-112">Actions.</span></span> <span data-ttu-id="fd811-113">*名称*。SortKeywhere 操作。</span><span class="sxs-lookup"><span data-stu-id="fd811-113">*name*  .SortKeywhere Actions.</span></span>  <span data-ttu-id="fd811-114">*name*是 Actions 行的名称</span><span class="sxs-lookup"><span data-stu-id="fd811-114">*name*  is the name of the Actions row</span></span>  <br/> |
   
<span data-ttu-id="fd811-115">若要从某个程序按索引获取对 SortKey 单元格的引用，请使用带下列参数的**CellsSRC**属性：</span><span class="sxs-lookup"><span data-stu-id="fd811-115">To get a reference to the SortKey cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="fd811-116">内容索引：</span><span class="sxs-lookup"><span data-stu-id="fd811-116">Section index:</span></span>  <br/> |<span data-ttu-id="fd811-117">**visSectionAction**</span><span class="sxs-lookup"><span data-stu-id="fd811-117">**visSectionAction**</span></span> <br/> |
|<span data-ttu-id="fd811-118">行索引：</span><span class="sxs-lookup"><span data-stu-id="fd811-118">Row index:</span></span>  <br/> |<span data-ttu-id="fd811-119">**visRowAction** +  *i*其中*i* = 0、 1、 2...</span><span class="sxs-lookup"><span data-stu-id="fd811-119">**visRowAction** +  *i*  where  *i*  = 0, 1, 2...</span></span>  <br/> |
|<span data-ttu-id="fd811-120">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="fd811-120">Cell index:</span></span>  <br/> |<span data-ttu-id="fd811-121">**visActionSortKey**</span><span class="sxs-lookup"><span data-stu-id="fd811-121">**visActionSortKey**</span></span> <br/> |
   

