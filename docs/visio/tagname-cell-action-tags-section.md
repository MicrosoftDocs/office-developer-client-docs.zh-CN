---
title: TagName 单元格（“Action Tags”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm60088
localization_priority: Normal
ms.assetid: 28d1cd60-4fb6-9feb-1a13-0962798ac1ad
description: 用作将动作标记与其动作相关联的关键字的动作标记的名称。
ms.openlocfilehash: dbac3d4dff9d2ffd18bba75db56cafc08f5e0ee8
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781472"
---
# <a name="tagname-cell-action-tags-section"></a><span data-ttu-id="abe89-103">TagName 单元格（“Action Tags”内容）</span><span class="sxs-lookup"><span data-stu-id="abe89-103">TagName Cell (Action Tags Section)</span></span>

<span data-ttu-id="abe89-104">用作将动作标记与其动作相关联的关键字的动作标记的名称。</span><span class="sxs-lookup"><span data-stu-id="abe89-104">Name of the action tag that is used as a key to associate the action tag with its actions.</span></span>
  
> [!NOTE]
> <span data-ttu-id="abe89-105">在以前版本的 Microsoft Visio 中，动作标记称为“智能标记”。</span><span class="sxs-lookup"><span data-stu-id="abe89-105">In previous versions of Microsoft Visio, action tags are called smart tags.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="abe89-106">注释</span><span class="sxs-lookup"><span data-stu-id="abe89-106">Remarks</span></span>

 <span data-ttu-id="abe89-107">在动作标记部分中的 TagName 单元格结合使用，在操作部分，若要将某个动作标记与其动作相关联的 TagName 单元格。</span><span class="sxs-lookup"><span data-stu-id="abe89-107">The TagName cell in the Action Tags section works together with the TagName cell in the Actions section to associate an action tag with its actions.</span></span> <span data-ttu-id="abe89-108">在操作部分中的行还具有 TagName 单元格，并且具有相同的 TagName 单元格值作为此单元格的行定义要为此动作标记执行的操作。</span><span class="sxs-lookup"><span data-stu-id="abe89-108">Rows in the Actions section also have a TagName cell, and those rows with the same TagName cell value as this cell define actions to take for this action tag.</span></span> 
  
<span data-ttu-id="abe89-109">若要获取对 TagName 单元格的引用按名称从另一个公式或从程序使用**CellsU**属性，请使用：</span><span class="sxs-lookup"><span data-stu-id="abe89-109">To get a reference to the TagName cell by name from another formula, or from a program by using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="abe89-110">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="abe89-110">Cell name:</span></span>  <br/> | <span data-ttu-id="abe89-111">智能标记。</span><span class="sxs-lookup"><span data-stu-id="abe89-111">SmartTags.</span></span>  <span data-ttu-id="abe89-112">*名称*。TagName 其中智能标记。</span><span class="sxs-lookup"><span data-stu-id="abe89-112">*name*  .TagName           where SmartTags.</span></span> <span data-ttu-id="abe89-113">*name*是动作标记行的名称</span><span class="sxs-lookup"><span data-stu-id="abe89-113">*name*  is the name of the action tag row</span></span>  <br/> |
   
<span data-ttu-id="abe89-114">若要从某个程序按索引获取对 TagName 单元格的引用，请使用带下列参数的**CellsSRC**属性：</span><span class="sxs-lookup"><span data-stu-id="abe89-114">To get a reference to the TagName cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="abe89-115">内容索引：</span><span class="sxs-lookup"><span data-stu-id="abe89-115">Section index:</span></span>  <br/> |<span data-ttu-id="abe89-116">**visSectionSmartTag**</span><span class="sxs-lookup"><span data-stu-id="abe89-116">**visSectionSmartTag**</span></span> <br/> |
| <span data-ttu-id="abe89-117">行索引：</span><span class="sxs-lookup"><span data-stu-id="abe89-117">Row index:</span></span>  <br/> |<span data-ttu-id="abe89-118">**visRowSmartTag** +  *i*其中*i* = 0、 1、 2...</span><span class="sxs-lookup"><span data-stu-id="abe89-118">**visRowSmartTag** +  *i*            where  *i*  = 0, 1, 2...</span></span>  <br/> |
| <span data-ttu-id="abe89-119">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="abe89-119">Cell index:</span></span>  <br/> |<span data-ttu-id="abe89-120">**visSmartTagName**</span><span class="sxs-lookup"><span data-stu-id="abe89-120">**visSmartTagName**</span></span> <br/> |
   

