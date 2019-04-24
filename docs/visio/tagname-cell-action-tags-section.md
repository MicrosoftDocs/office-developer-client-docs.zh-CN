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
ms.openlocfilehash: 777d6c1098888c9835c1ad367bb70926b835180b
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32332394"
---
# <a name="tagname-cell-action-tags-section"></a><span data-ttu-id="9de3a-103">TagName 单元格（“Action Tags”内容）</span><span class="sxs-lookup"><span data-stu-id="9de3a-103">TagName Cell (Action Tags Section)</span></span>

<span data-ttu-id="9de3a-104">用作将动作标记与其动作相关联的关键字的动作标记的名称。</span><span class="sxs-lookup"><span data-stu-id="9de3a-104">Name of the action tag that is used as a key to associate the action tag with its actions.</span></span>
  
> [!NOTE]
> <span data-ttu-id="9de3a-105">在以前版本的 Microsoft Visio 中，动作标记称为“智能标记”。</span><span class="sxs-lookup"><span data-stu-id="9de3a-105">In previous versions of Microsoft Visio, action tags are called smart tags.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="9de3a-106">注解</span><span class="sxs-lookup"><span data-stu-id="9de3a-106">Remarks</span></span>

 <span data-ttu-id="9de3a-107">“Action Tags”内容中的 TagName 单元格与“Actions”内容中的 TagName 单元格结合使用，可以将某个动作标记与其动作相关联。</span><span class="sxs-lookup"><span data-stu-id="9de3a-107">The TagName cell in the Action Tags section works together with the TagName cell in the Actions section to associate an action tag with its actions.</span></span> <span data-ttu-id="9de3a-108">"操作" 部分中的行还具有 tagname 单元格, 并且这些具有与此单元格相同的 tagname 单元格值的行定义要对此操作标记执行的操作。</span><span class="sxs-lookup"><span data-stu-id="9de3a-108">Rows in the Actions section also have a TagName cell, and those rows with the same TagName cell value as this cell define actions to take for this action tag.</span></span> 
  
<span data-ttu-id="9de3a-109">若要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 TagName 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="9de3a-109">To get a reference to the TagName cell by name from another formula, or from a program by using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="9de3a-110">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="9de3a-110">Cell name:</span></span>  <br/> | <span data-ttu-id="9de3a-111">SmartTags.</span><span class="sxs-lookup"><span data-stu-id="9de3a-111">SmartTags.</span></span>  <span data-ttu-id="9de3a-112">*名称*。智能标记所在的 TagName。</span><span class="sxs-lookup"><span data-stu-id="9de3a-112">*name*  .TagName           where SmartTags.</span></span> <span data-ttu-id="9de3a-113">*name*是操作标记行的名称</span><span class="sxs-lookup"><span data-stu-id="9de3a-113">*name*  is the name of the action tag row</span></span>  <br/> |
   
<span data-ttu-id="9de3a-114">要从某个程序按索引获取对 TagName 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="9de3a-114">To get a reference to the TagName cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="9de3a-115">内容索引：</span><span class="sxs-lookup"><span data-stu-id="9de3a-115">Section index:</span></span>  <br/> |<span data-ttu-id="9de3a-116">**visSectionSmartTag**</span><span class="sxs-lookup"><span data-stu-id="9de3a-116">**visSectionSmartTag**</span></span> <br/> |
| <span data-ttu-id="9de3a-117">行索引：</span><span class="sxs-lookup"><span data-stu-id="9de3a-117">Row index:</span></span>  <br/> |<span data-ttu-id="9de3a-118">**visRowSmartTag** +  *i* = \*\* 0、1、2 .。。</span><span class="sxs-lookup"><span data-stu-id="9de3a-118">**visRowSmartTag** +  *i*            where  *i*  = 0, 1, 2...</span></span>  <br/> |
| <span data-ttu-id="9de3a-119">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="9de3a-119">Cell index:</span></span>  <br/> |<span data-ttu-id="9de3a-120">**visSmartTagName**</span><span class="sxs-lookup"><span data-stu-id="9de3a-120">**visSmartTagName**</span></span> <br/> |
   

