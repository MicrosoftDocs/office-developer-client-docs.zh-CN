---
title: TagName 单元格（“Actions”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm60087
localization_priority: Normal
ms.assetid: e593e95d-f975-481d-69cd-619049d4427d
description: 包含此动作所关联的动作标记的名称。
ms.openlocfilehash: e7bf5db940934d168ac2adb86d05b0374b0fd265
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32332387"
---
# <a name="tagname-cell-actions-section"></a><span data-ttu-id="4e050-103">TagName 单元格（“Actions”内容）</span><span class="sxs-lookup"><span data-stu-id="4e050-103">TagName Cell (Actions Section)</span></span>

<span data-ttu-id="4e050-104">包含此动作所关联的动作标记的名称。</span><span class="sxs-lookup"><span data-stu-id="4e050-104">Contains the name of the action tag that this action is associated with.</span></span>
  
> [!NOTE]
> <span data-ttu-id="4e050-105">在以前版本的 Microsoft Visio 中，动作标记称为“智能标记”。</span><span class="sxs-lookup"><span data-stu-id="4e050-105">In previous versions of Microsoft Visio, action tags are called smart tags.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="4e050-106">注解</span><span class="sxs-lookup"><span data-stu-id="4e050-106">Remarks</span></span>

<span data-ttu-id="4e050-107">“Actions”内容中的 TagName 单元格与“Action Tags”内容中的 TagName 单元格结合使用，可以将某个动作标记与其动作相关联。</span><span class="sxs-lookup"><span data-stu-id="4e050-107">The TagName cell in the Actions section works together with the TagName cell in the Action Tags section to associate an action tag with its actions.</span></span> 
  
- <span data-ttu-id="4e050-108">如果操作行中的 TagName 单元格为空, 则该操作将显示在快捷菜单上, 而不是动作标记菜单上。</span><span class="sxs-lookup"><span data-stu-id="4e050-108">If the TagName cell in an Actions row is blank, the action appears on a shortcut menu, not on an action tag menu.</span></span>
    
- <span data-ttu-id="4e050-109">如果 "操作" 行中的 tagname 单元格值与 "智能标记" 行中的 tagname 单元格值相匹配, 则操作将显示在 "操作标记" 菜单上。</span><span class="sxs-lookup"><span data-stu-id="4e050-109">If a TagName cell value in the Actions row matches the TagName cell value in a Smart Tags row, the action appears on the action tag menu.</span></span>
    
- <span data-ttu-id="4e050-110">如果操作的 TagName 单元格具有值, 但它与任何形状标记行中的 TagName 值不匹配, 则该操作不会显示在任何动作标记菜单或快捷菜单上。</span><span class="sxs-lookup"><span data-stu-id="4e050-110">If an action's TagName cell has a value but it does not match the TagName value in any shape tag row, that action does not appear on any action tag menus or shortcut menus.</span></span>
    
- <span data-ttu-id="4e050-111">如果几个智能标记行具有相同的 TagName 值，它们将显示相同的动作。</span><span class="sxs-lookup"><span data-stu-id="4e050-111">If several smart tag rows have the same TagName value, they will all show the same actions.</span></span>
    
<span data-ttu-id="4e050-112">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 TagName 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="4e050-112">To get a reference to the TagName cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="4e050-113">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="4e050-113">Cell name:</span></span>  <br/> |<span data-ttu-id="4e050-114">操作.</span><span class="sxs-lookup"><span data-stu-id="4e050-114">Actions.</span></span> <span data-ttu-id="4e050-115">*名称*。TagNamewhere 操作。</span><span class="sxs-lookup"><span data-stu-id="4e050-115">*name*  .TagNamewhere Actions.</span></span>  <span data-ttu-id="4e050-116">*name*是操作行的名称</span><span class="sxs-lookup"><span data-stu-id="4e050-116">*name*  is the name of the Actions row</span></span>  <br/> |
   
<span data-ttu-id="4e050-117">要从某个程序按索引获取对 TagName 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="4e050-117">To get a reference to the TagName cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="4e050-118">内容索引：</span><span class="sxs-lookup"><span data-stu-id="4e050-118">Section index:</span></span>  <br/> |<span data-ttu-id="4e050-119">**visSectionAction**</span><span class="sxs-lookup"><span data-stu-id="4e050-119">**visSectionAction**</span></span> <br/> |
|<span data-ttu-id="4e050-120">行索引：</span><span class="sxs-lookup"><span data-stu-id="4e050-120">Row index:</span></span>  <br/> |<span data-ttu-id="4e050-121">**visRowAction** +  *i* = \*\* 0、1、2 .。。</span><span class="sxs-lookup"><span data-stu-id="4e050-121">**visRowAction** +  *i*  where  *i*  = 0, 1, 2...</span></span>  <br/> |
|<span data-ttu-id="4e050-122">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="4e050-122">Cell index:</span></span>  <br/> |<span data-ttu-id="4e050-123">**visActionTagName**</span><span class="sxs-lookup"><span data-stu-id="4e050-123">**visActionTagName**</span></span> <br/> |
   

