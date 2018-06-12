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
ms.openlocfilehash: e1495a34769cbcfdd687491855d1f9c761de2b4e
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781488"
---
# <a name="tagname-cell-actions-section"></a><span data-ttu-id="57617-103">TagName 单元格（“Actions”内容）</span><span class="sxs-lookup"><span data-stu-id="57617-103">TagName Cell (Actions Section)</span></span>

<span data-ttu-id="57617-104">包含此动作所关联的动作标记的名称。</span><span class="sxs-lookup"><span data-stu-id="57617-104">Contains the name of the action tag that this action is associated with.</span></span>
  
> [!NOTE]
> <span data-ttu-id="57617-105">在以前版本的 Microsoft Visio 中，动作标记称为“智能标记”。</span><span class="sxs-lookup"><span data-stu-id="57617-105">In previous versions of Microsoft Visio, action tags are called smart tags.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="57617-106">注解</span><span class="sxs-lookup"><span data-stu-id="57617-106">Remarks</span></span>

<span data-ttu-id="57617-107">“Actions”内容中的 TagName 单元格与“Action Tags”内容中的 TagName 单元格结合使用，可以将某个动作标记与其动作相关联。</span><span class="sxs-lookup"><span data-stu-id="57617-107">The TagName cell in the Actions section works together with the TagName cell in the Action Tags section to associate an action tag with its actions.</span></span> 
  
- <span data-ttu-id="57617-108">如果 Actions 行中的 TagName 单元格为空，该动作将显示在快捷菜单中，不在动作标记菜单上。</span><span class="sxs-lookup"><span data-stu-id="57617-108">If the TagName cell in an Actions row is blank, the action appears on a shortcut menu, not on an action tag menu.</span></span>
    
- <span data-ttu-id="57617-109">如果 Actions 行中的 TagName 单元格值与 Smart Tags 行中的 TagName 单元格值匹配，则该动作将显示在动作标记菜单。</span><span class="sxs-lookup"><span data-stu-id="57617-109">If a TagName cell value in the Actions row matches the TagName cell value in a Smart Tags row, the action appears on the action tag menu.</span></span>
    
- <span data-ttu-id="57617-110">如果该操作的 TagName 单元格包含一个值，但不匹配任何形状标记行中的 TagName 值，该操作未显示在任何动作标记菜单或快捷菜单。</span><span class="sxs-lookup"><span data-stu-id="57617-110">If an action's TagName cell has a value but it does not match the TagName value in any shape tag row, that action does not appear on any action tag menus or shortcut menus.</span></span>
    
- <span data-ttu-id="57617-111">如果几个智能标记行具有相同的 TagName 值，它们将显示相同的动作。</span><span class="sxs-lookup"><span data-stu-id="57617-111">If several smart tag rows have the same TagName value, they will all show the same actions.</span></span>
    
<span data-ttu-id="57617-112">要从另一个公式或使用**CellsU**属性从某个程序按名称获取对 TagName 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="57617-112">To get a reference to the TagName cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="57617-113">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="57617-113">Cell name:</span></span>  <br/> |<span data-ttu-id="57617-114">操作。</span><span class="sxs-lookup"><span data-stu-id="57617-114">Actions.</span></span> <span data-ttu-id="57617-115">*名称*。TagNamewhere 操作。</span><span class="sxs-lookup"><span data-stu-id="57617-115">*name*  .TagNamewhere Actions.</span></span>  <span data-ttu-id="57617-116">*name*是 Actions 行的名称</span><span class="sxs-lookup"><span data-stu-id="57617-116">*name*  is the name of the Actions row</span></span>  <br/> |
   
<span data-ttu-id="57617-117">若要从某个程序按索引获取对 TagName 单元格的引用，请使用带下列参数的**CellsSRC**属性：</span><span class="sxs-lookup"><span data-stu-id="57617-117">To get a reference to the TagName cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="57617-118">内容索引：</span><span class="sxs-lookup"><span data-stu-id="57617-118">Section index:</span></span>  <br/> |<span data-ttu-id="57617-119">**visSectionAction**</span><span class="sxs-lookup"><span data-stu-id="57617-119">**visSectionAction**</span></span> <br/> |
|<span data-ttu-id="57617-120">行索引：</span><span class="sxs-lookup"><span data-stu-id="57617-120">Row index:</span></span>  <br/> |<span data-ttu-id="57617-121">**visRowAction** +  *i*其中*i* = 0、 1、 2...</span><span class="sxs-lookup"><span data-stu-id="57617-121">**visRowAction** +  *i*  where  *i*  = 0, 1, 2...</span></span>  <br/> |
|<span data-ttu-id="57617-122">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="57617-122">Cell index:</span></span>  <br/> |<span data-ttu-id="57617-123">**visActionTagName**</span><span class="sxs-lookup"><span data-stu-id="57617-123">**visActionTagName**</span></span> <br/> |
   

