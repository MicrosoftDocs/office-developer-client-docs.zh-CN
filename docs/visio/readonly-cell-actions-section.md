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
ms.openlocfilehash: f45f22001a4d7275bb9367414c8b04ea3c0d9c6e
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32359988"
---
# <a name="readonly-cell-actions-section"></a><span data-ttu-id="42622-103">ReadOnly 单元格（“Actions”内容）</span><span class="sxs-lookup"><span data-stu-id="42622-103">ReadOnly Cell (Actions Section)</span></span>

<span data-ttu-id="42622-104">控制动作标记菜单或快捷菜单上的动作是否为只读。</span><span class="sxs-lookup"><span data-stu-id="42622-104">Controls whether the action on an action tag or shortcut menu is read-only.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="42622-105">在以前版本的 Microsoft Visio 中，动作标记称为“智能标记”。</span><span class="sxs-lookup"><span data-stu-id="42622-105">In previous versions of Microsoft Visio, action tags are called smart tags.</span></span> 
  
|<span data-ttu-id="42622-106">**Value**</span><span class="sxs-lookup"><span data-stu-id="42622-106">**Value**</span></span>|<span data-ttu-id="42622-107">**说明**</span><span class="sxs-lookup"><span data-stu-id="42622-107">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="42622-108">TRUE</span><span class="sxs-lookup"><span data-stu-id="42622-108">TRUE</span></span>  <br/> |<span data-ttu-id="42622-109">动作在菜单上显示，但为只读的。</span><span class="sxs-lookup"><span data-stu-id="42622-109">The action appears on the menu but is read-only.</span></span>  <br/> |
|<span data-ttu-id="42622-110">FALSE</span><span class="sxs-lookup"><span data-stu-id="42622-110">FALSE</span></span>  <br/> |<span data-ttu-id="42622-111">动作在菜单上显示并且可以选择（默认值）。</span><span class="sxs-lookup"><span data-stu-id="42622-111">The action appears on the menu and can be selected (the default).</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="42622-112">注解</span><span class="sxs-lookup"><span data-stu-id="42622-112">Remarks</span></span>

<span data-ttu-id="42622-113">如果显示在动作标记或快捷菜单上的某个动作是只读的，便不能选取它。</span><span class="sxs-lookup"><span data-stu-id="42622-113">When an action is read-only, it appears on the action tag or shortcut menu but you cannot select it.</span></span> <span data-ttu-id="42622-114">它不会灰显而是背景呈彩色，类似标签。</span><span class="sxs-lookup"><span data-stu-id="42622-114">It is not dimmed but rather appears on a colored background, like a label.</span></span> <span data-ttu-id="42622-115">若要使菜单项灰显，请使用 Disabled 单元格。</span><span class="sxs-lookup"><span data-stu-id="42622-115">To make the menu item appear dimmed, use the Disabled cell.</span></span> 
  
<span data-ttu-id="42622-116">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 ReadOnly 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="42622-116">To get a reference to the ReadOnly cell by name from another formula, or from a program by using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="42622-117">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="42622-117">Cell name:</span></span>  <br/> |<span data-ttu-id="42622-118">操作.</span><span class="sxs-lookup"><span data-stu-id="42622-118">Actions.</span></span> <span data-ttu-id="42622-119">*名称*。ReadOnlywhere 操作。</span><span class="sxs-lookup"><span data-stu-id="42622-119">*name*  .ReadOnlywhere Actions.</span></span>  <span data-ttu-id="42622-120">*name*是操作行的名称</span><span class="sxs-lookup"><span data-stu-id="42622-120">*name*  is the name of the Actions row</span></span>  <br/> |
   
<span data-ttu-id="42622-121">若要从某个程序按索引获取对 ReadOnly 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="42622-121">To get a reference to the ReadOnly cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="42622-122">内容索引：</span><span class="sxs-lookup"><span data-stu-id="42622-122">Section index:</span></span>  <br/> |<span data-ttu-id="42622-123">**visSectionAction**</span><span class="sxs-lookup"><span data-stu-id="42622-123">**visSectionAction**</span></span> <br/> |
|<span data-ttu-id="42622-124">行索引：</span><span class="sxs-lookup"><span data-stu-id="42622-124">Row index:</span></span>  <br/> |<span data-ttu-id="42622-125">**visRowAction** +  *i* = \*\* 0、1、2 .。。</span><span class="sxs-lookup"><span data-stu-id="42622-125">**visRowAction** +  *i*  where  *i*  = 0, 1, 2...</span></span>  <br/> |
|<span data-ttu-id="42622-126">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="42622-126">Cell index:</span></span>  <br/> |<span data-ttu-id="42622-127">**visActionReadOnly**</span><span class="sxs-lookup"><span data-stu-id="42622-127">**visActionReadOnly**</span></span> <br/> |
   

