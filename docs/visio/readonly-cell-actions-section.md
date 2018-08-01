---
title: ReadOnly 单元格（“Actions”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm60071
localization_priority: Normal
ms.assetid: 158b4188-570c-3817-bf34-8dc0c64befa5
description: 控制动作标记菜单或快捷菜单上的动作是否为只读。
ms.openlocfilehash: bf2d0f7e50a3126611662af8e068485986c26a13
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781014"
---
# <a name="readonly-cell-actions-section"></a><span data-ttu-id="fa59b-103">ReadOnly 单元格（“Actions”部分）</span><span class="sxs-lookup"><span data-stu-id="fa59b-103">ReadOnly Cell (Actions Section)</span></span>

<span data-ttu-id="fa59b-104">控制动作标记菜单或快捷菜单上的动作是否为只读。</span><span class="sxs-lookup"><span data-stu-id="fa59b-104">Controls whether the action on an action tag or shortcut menu is read-only.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="fa59b-105">在以前版本的 Microsoft Visio 中，动作标记称为“智能标记”。</span><span class="sxs-lookup"><span data-stu-id="fa59b-105">In previous versions of Microsoft Visio, action tags are called smart tags.</span></span> 
  
|<span data-ttu-id="fa59b-106">**值**</span><span class="sxs-lookup"><span data-stu-id="fa59b-106">**Value**</span></span>|<span data-ttu-id="fa59b-107">**说明**</span><span class="sxs-lookup"><span data-stu-id="fa59b-107">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="fa59b-108">TRUE</span><span class="sxs-lookup"><span data-stu-id="fa59b-108">TRUE</span></span>  <br/> |<span data-ttu-id="fa59b-109">动作在菜单上显示，但为只读的。</span><span class="sxs-lookup"><span data-stu-id="fa59b-109">The action appears on the menu but is read-only.</span></span>  <br/> |
|<span data-ttu-id="fa59b-110">FALSE</span><span class="sxs-lookup"><span data-stu-id="fa59b-110">FALSE</span></span>  <br/> |<span data-ttu-id="fa59b-111">动作在菜单上显示并且可以选择（默认值）。</span><span class="sxs-lookup"><span data-stu-id="fa59b-111">The action appears on the menu and can be selected (the default).</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="fa59b-112">注解</span><span class="sxs-lookup"><span data-stu-id="fa59b-112">Remarks</span></span>

<span data-ttu-id="fa59b-113">只读操作时，显示在动作标记菜单或快捷菜单上，但不是能选择它。</span><span class="sxs-lookup"><span data-stu-id="fa59b-113">When an action is read-only, it appears on the action tag or shortcut menu but you cannot select it.</span></span> <span data-ttu-id="fa59b-114">它不会灰显，但而不出现在彩色背景，像一个标签上。</span><span class="sxs-lookup"><span data-stu-id="fa59b-114">It is not dimmed but rather appears on a colored background, like a label.</span></span> <span data-ttu-id="fa59b-115">若要使变灰该菜单项，请使用 Disabled 单元格。</span><span class="sxs-lookup"><span data-stu-id="fa59b-115">To make the menu item appear dimmed, use the Disabled cell.</span></span> 
  
<span data-ttu-id="fa59b-116">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 ReadOnly 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="fa59b-116">To get a reference to the ReadOnly cell by name from another formula, or from a program by using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="fa59b-117">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="fa59b-117">Cell name:</span></span>  <br/> |<span data-ttu-id="fa59b-118">操作。</span><span class="sxs-lookup"><span data-stu-id="fa59b-118">Actions.</span></span> <span data-ttu-id="fa59b-119">*名称*。ReadOnlywhere 操作。</span><span class="sxs-lookup"><span data-stu-id="fa59b-119">*name*  .ReadOnlywhere Actions.</span></span>  <span data-ttu-id="fa59b-120">*name*是 Actions 行的名称</span><span class="sxs-lookup"><span data-stu-id="fa59b-120">*name*  is the name of the Actions row</span></span>  <br/> |
   
<span data-ttu-id="fa59b-121">若要从某个程序按索引获取对 ReadOnly 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="fa59b-121">To get a reference to the ReadOnly cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="fa59b-122">内容索引：</span><span class="sxs-lookup"><span data-stu-id="fa59b-122">Section index:</span></span>  <br/> |<span data-ttu-id="fa59b-123">**visSectionAction**</span><span class="sxs-lookup"><span data-stu-id="fa59b-123">**visSectionAction**</span></span> <br/> |
|<span data-ttu-id="fa59b-124">行索引：</span><span class="sxs-lookup"><span data-stu-id="fa59b-124">Row index:</span></span>  <br/> |<span data-ttu-id="fa59b-125">**visRowAction** +  *i*其中*i* = 0、 1、 2...</span><span class="sxs-lookup"><span data-stu-id="fa59b-125">**visRowAction** +  *i*  where  *i*  = 0, 1, 2...</span></span>  <br/> |
|<span data-ttu-id="fa59b-126">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="fa59b-126">Cell index:</span></span>  <br/> |<span data-ttu-id="fa59b-127">**visActionReadOnly**</span><span class="sxs-lookup"><span data-stu-id="fa59b-127">**visActionReadOnly**</span></span> <br/> |
   

