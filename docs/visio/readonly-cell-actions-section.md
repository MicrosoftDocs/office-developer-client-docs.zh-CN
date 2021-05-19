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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33434233"
---
# <a name="readonly-cell-actions-section"></a><span data-ttu-id="2dba8-103">ReadOnly 单元格（“Actions”内容）</span><span class="sxs-lookup"><span data-stu-id="2dba8-103">ReadOnly Cell (Actions Section)</span></span>

<span data-ttu-id="2dba8-104">控制动作标记菜单或快捷菜单上的动作是否为只读。</span><span class="sxs-lookup"><span data-stu-id="2dba8-104">Controls whether the action on an action tag or shortcut menu is read-only.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="2dba8-105">在以前版本的 Microsoft Visio 中，动作标记称为“智能标记”。</span><span class="sxs-lookup"><span data-stu-id="2dba8-105">In previous versions of Microsoft Visio, action tags are called smart tags.</span></span> 
  
|<span data-ttu-id="2dba8-106">**值**</span><span class="sxs-lookup"><span data-stu-id="2dba8-106">**Value**</span></span>|<span data-ttu-id="2dba8-107">**说明**</span><span class="sxs-lookup"><span data-stu-id="2dba8-107">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="2dba8-108">TRUE</span><span class="sxs-lookup"><span data-stu-id="2dba8-108">TRUE</span></span>  <br/> |<span data-ttu-id="2dba8-109">动作在菜单上显示，但为只读的。</span><span class="sxs-lookup"><span data-stu-id="2dba8-109">The action appears on the menu but is read-only.</span></span>  <br/> |
|<span data-ttu-id="2dba8-110">FALSE</span><span class="sxs-lookup"><span data-stu-id="2dba8-110">FALSE</span></span>  <br/> |<span data-ttu-id="2dba8-111">动作在菜单上显示并且可以选择（默认值）。</span><span class="sxs-lookup"><span data-stu-id="2dba8-111">The action appears on the menu and can be selected (the default).</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="2dba8-112">备注</span><span class="sxs-lookup"><span data-stu-id="2dba8-112">Remarks</span></span>

<span data-ttu-id="2dba8-113">如果显示在动作标记或快捷菜单上的某个动作是只读的，便不能选取它。</span><span class="sxs-lookup"><span data-stu-id="2dba8-113">When an action is read-only, it appears on the action tag or shortcut menu but you cannot select it.</span></span> <span data-ttu-id="2dba8-114">它不会灰显而是背景呈彩色，类似标签。</span><span class="sxs-lookup"><span data-stu-id="2dba8-114">It is not dimmed but rather appears on a colored background, like a label.</span></span> <span data-ttu-id="2dba8-115">若要使菜单项灰显，请使用 Disabled 单元格。</span><span class="sxs-lookup"><span data-stu-id="2dba8-115">To make the menu item appear dimmed, use the Disabled cell.</span></span> 
  
<span data-ttu-id="2dba8-116">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 ReadOnly 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="2dba8-116">To get a reference to the ReadOnly cell by name from another formula, or from a program by using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="2dba8-117">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="2dba8-117">Cell name:</span></span>  <br/> |<span data-ttu-id="2dba8-118">操作。</span><span class="sxs-lookup"><span data-stu-id="2dba8-118">Actions.</span></span> <span data-ttu-id="2dba8-119">*name*  .ReadOnlywhere Actions.</span><span class="sxs-lookup"><span data-stu-id="2dba8-119">*name*  .ReadOnlywhere Actions.</span></span>  <span data-ttu-id="2dba8-120">*name*  是 Actions 行的名称</span><span class="sxs-lookup"><span data-stu-id="2dba8-120">*name*  is the name of the Actions row</span></span>  <br/> |
   
<span data-ttu-id="2dba8-121">若要从某个程序按索引获取对 ReadOnly 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="2dba8-121">To get a reference to the ReadOnly cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="2dba8-122">内容索引：</span><span class="sxs-lookup"><span data-stu-id="2dba8-122">Section index:</span></span>  <br/> |<span data-ttu-id="2dba8-123">**visSectionAction**</span><span class="sxs-lookup"><span data-stu-id="2dba8-123">**visSectionAction**</span></span> <br/> |
|<span data-ttu-id="2dba8-124">行索引：</span><span class="sxs-lookup"><span data-stu-id="2dba8-124">Row index:</span></span>  <br/> |<span data-ttu-id="2dba8-125">**visRowAction**  +  *i* 其中 *i* = 0、1、2...</span><span class="sxs-lookup"><span data-stu-id="2dba8-125">**visRowAction** +  *i*  where  *i*  = 0, 1, 2...</span></span>  <br/> |
|<span data-ttu-id="2dba8-126">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="2dba8-126">Cell index:</span></span>  <br/> |<span data-ttu-id="2dba8-127">**visActionReadOnly**</span><span class="sxs-lookup"><span data-stu-id="2dba8-127">**visActionReadOnly**</span></span> <br/> |
   

