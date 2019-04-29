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
ms.openlocfilehash: d4eb98055f199f603003b068dca9fa7b4e377e52
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33419658"
---
# <a name="sortkey-cell-actions-section"></a><span data-ttu-id="a9a0a-103">SortKey 单元格（“Actions”内容）</span><span class="sxs-lookup"><span data-stu-id="a9a0a-103">SortKey Cell (Actions Section)</span></span>

<span data-ttu-id="a9a0a-104">确定动作在快捷菜单或动作标记菜单上显示的顺序的数字。</span><span class="sxs-lookup"><span data-stu-id="a9a0a-104">A number that determines the order of actions that appear on a shortcut or action tag menu.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a9a0a-105">在以前版本的 Microsoft Visio 中，动作标记称为“智能标记”。</span><span class="sxs-lookup"><span data-stu-id="a9a0a-105">In previous versions of Microsoft Visio, action tags are called smart tags.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="a9a0a-106">说明</span><span class="sxs-lookup"><span data-stu-id="a9a0a-106">Remarks</span></span>

<span data-ttu-id="a9a0a-p101">动作按照从低到高的顺序在动作标记菜单或快捷菜单上显示，最低的数字显示在菜单的顶部。如果两个动作行具有相同的 SortKey 单元格值，则顺序由物理行顺序确定。默认值为 0（零）。</span><span class="sxs-lookup"><span data-stu-id="a9a0a-p101">The actions on an action tag or shortcut menu appear on the menu sorted from lowest to highest, with lower numbers appearing at the top of the menu. If two action rows have the same SortKey cell value, the order is determined by physical row order. The default is 0 (zero).</span></span>
  
<span data-ttu-id="a9a0a-110">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 SortKey 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="a9a0a-110">To get a reference to the SortKey cell by name from another formula, or from a program by using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="a9a0a-111">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="a9a0a-111">Cell name:</span></span>  <br/> |<span data-ttu-id="a9a0a-112">操作.</span><span class="sxs-lookup"><span data-stu-id="a9a0a-112">Actions.</span></span> <span data-ttu-id="a9a0a-113">*名称*。SortKeywhere 操作。</span><span class="sxs-lookup"><span data-stu-id="a9a0a-113">*name*  .SortKeywhere Actions.</span></span>  <span data-ttu-id="a9a0a-114">*name*是操作行的名称</span><span class="sxs-lookup"><span data-stu-id="a9a0a-114">*name*  is the name of the Actions row</span></span>  <br/> |
   
<span data-ttu-id="a9a0a-115">若要从某个程序按索引获取对 SortKey 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="a9a0a-115">To get a reference to the SortKey cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="a9a0a-116">内容索引：</span><span class="sxs-lookup"><span data-stu-id="a9a0a-116">Section index:</span></span>  <br/> |<span data-ttu-id="a9a0a-117">**visSectionAction**</span><span class="sxs-lookup"><span data-stu-id="a9a0a-117">**visSectionAction**</span></span> <br/> |
|<span data-ttu-id="a9a0a-118">行索引：</span><span class="sxs-lookup"><span data-stu-id="a9a0a-118">Row index:</span></span>  <br/> |<span data-ttu-id="a9a0a-119">**visRowAction** +  *i* = \*\* 0、1、2 .。。</span><span class="sxs-lookup"><span data-stu-id="a9a0a-119">**visRowAction** +  *i*  where  *i*  = 0, 1, 2...</span></span>  <br/> |
|<span data-ttu-id="a9a0a-120">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="a9a0a-120">Cell index:</span></span>  <br/> |<span data-ttu-id="a9a0a-121">**visActionSortKey**</span><span class="sxs-lookup"><span data-stu-id="a9a0a-121">**visActionSortKey**</span></span> <br/> |
   

