---
title: ReplaceLockText 单元格（“Change Shape Behavior”部分）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 31f43ebe-3758-4fd9-83b5-775041c5890f
description: 指示在主控形状中的指定单元格的值是否覆盖形状替换操作期间要替换的形状 （包括本地值） 的值。 ReplaceLockText 确定是否显示母版上的文本将覆盖要替换的形状的文本。
ms.openlocfilehash: 75fb0831e7361345f04d7912eb0a55959d9417cd
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781104"
---
# <a name="replacelocktext-cell-change-shape-behavior-section"></a><span data-ttu-id="5c552-104">ReplaceLockText 单元格（“Change Shape Behavior”部分）</span><span class="sxs-lookup"><span data-stu-id="5c552-104">ReplaceLockText Cell (Change Shape Behavior Section)</span></span>

<span data-ttu-id="5c552-105">指示在主控形状中的指定单元格的值是否覆盖形状替换操作期间要替换的形状 （包括本地值） 的值。</span><span class="sxs-lookup"><span data-stu-id="5c552-105">Indicates whether the values of specified cells in a master shape overwrite the values (including local values) of a shape being replaced during a shape replacement operation.</span></span> <span data-ttu-id="5c552-106">**ReplaceLockText**确定是否显示母版上的文本将覆盖要替换的形状的文本。</span><span class="sxs-lookup"><span data-stu-id="5c552-106">The **ReplaceLockText** determines whether the text displayed on the Master overwrites the text of the shape being replaced.</span></span> 
  
|<span data-ttu-id="5c552-107">**值**</span><span class="sxs-lookup"><span data-stu-id="5c552-107">**Value**</span></span>|<span data-ttu-id="5c552-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="5c552-108">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="5c552-109">TRUE</span><span class="sxs-lookup"><span data-stu-id="5c552-109">TRUE</span></span>  <br/> | <span data-ttu-id="5c552-110">主控形状上的文本将覆盖旧形状上的文本。</span><span class="sxs-lookup"><span data-stu-id="5c552-110">The text on the master shape overwrites the text on the old shape.</span></span> <span data-ttu-id="5c552-111">此外，主控形状的形状替换操作期间覆盖以下各节中的单元格的值：</span><span class="sxs-lookup"><span data-stu-id="5c552-111">In addition, the master shape overwrites the values of the cells in the following sections during a shape replacement operation:</span></span>  <br/> <span data-ttu-id="5c552-112">**文本域**部分</span><span class="sxs-lookup"><span data-stu-id="5c552-112">**Text Fields** section</span></span>  <br/> <span data-ttu-id="5c552-113">**文本块格式**部分</span><span class="sxs-lookup"><span data-stu-id="5c552-113">**Text Block Format** section</span></span>  <br/> |
|<span data-ttu-id="5c552-114">FALSE</span><span class="sxs-lookup"><span data-stu-id="5c552-114">FALSE</span></span>  <br/> |<span data-ttu-id="5c552-115">替代形状包含任何文本、 文本域或从旧形状其他已添加到形状的文本属性。</span><span class="sxs-lookup"><span data-stu-id="5c552-115">The replacement shape contains any text, text fields, or other text properties from the old shape that have been added to the shape.</span></span>  <br/> <span data-ttu-id="5c552-116">替代形状包含文本的旧的形状的属性，替换形状也值从旧的形状的**字符**和**段落**部分，如果有拥有多个行。</span><span class="sxs-lookup"><span data-stu-id="5c552-116">When the replacement shape contains text properties from the old shape, the replacement shape also has the values from the **Character** and **Paragraph** sections of the old shape if they have more than one row.</span></span>  <br/> |
   
<span data-ttu-id="5c552-117">如果设置为 TRUE (1)，该形状的主控形状的值替换为以下要替换的形状上的值：</span><span class="sxs-lookup"><span data-stu-id="5c552-117">If set to TRUE (1), the values of the shape Master replaces the values of the following on the shape being replaced:</span></span>
  
- [<span data-ttu-id="5c552-118">TheText Cell (Events Section)</span><span class="sxs-lookup"><span data-stu-id="5c552-118">TheText Cell (Events Section)</span></span>](thetext-cell-events-section.md)
    
- <span data-ttu-id="5c552-119">[Character 内容](character-section.md)中的单元格</span><span class="sxs-lookup"><span data-stu-id="5c552-119">Cells in the [Character Section](character-section.md)</span></span>
    
- <span data-ttu-id="5c552-120">[Paragraph 内容](paragraph-section.md)中的单元格</span><span class="sxs-lookup"><span data-stu-id="5c552-120">Cells in the [Paragraph Section](paragraph-section.md)</span></span>
    
- <span data-ttu-id="5c552-121">[Tabs 内容](tabs-section.md)中的单元格</span><span class="sxs-lookup"><span data-stu-id="5c552-121">Cells in the [Tabs Section](tabs-section.md)</span></span>
    
## <a name="remarks"></a><span data-ttu-id="5c552-122">说明</span><span class="sxs-lookup"><span data-stu-id="5c552-122">Remarks</span></span>

<span data-ttu-id="5c552-123">要从另一个公式，由**N** **单元格**元素的属性的值或使用**CellsU**属性从某个程序按名称获取对**ReplaceLockText**单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="5c552-123">To get a reference to the **ReplaceLockText** cell by name from another formula, by value of the **N** attribute of a **Cell** element, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="5c552-124">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="5c552-124">Cell name:</span></span>  <br/> | <span data-ttu-id="5c552-125">ReplaceLockText</span><span class="sxs-lookup"><span data-stu-id="5c552-125">ReplaceLockText</span></span>  <br/> |
   
<span data-ttu-id="5c552-126">若要从某个程序按索引获取对**ReplaceLockText**单元格的引用，请使用带下列参数的**CellsSRC**属性：</span><span class="sxs-lookup"><span data-stu-id="5c552-126">To get a reference to the **ReplaceLockText** cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="5c552-127">内容索引：</span><span class="sxs-lookup"><span data-stu-id="5c552-127">Section index:</span></span>  <br/> |<span data-ttu-id="5c552-128">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="5c552-128">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="5c552-129">行索引：</span><span class="sxs-lookup"><span data-stu-id="5c552-129">Row index:</span></span>  <br/> |<span data-ttu-id="5c552-130">**visRowReplaceBehaviors**</span><span class="sxs-lookup"><span data-stu-id="5c552-130">**visRowReplaceBehaviors**</span></span> <br/> |
| <span data-ttu-id="5c552-131">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="5c552-131">Cell index:</span></span>  <br/> |<span data-ttu-id="5c552-132">**visReplaceLockText**</span><span class="sxs-lookup"><span data-stu-id="5c552-132">**visReplaceLockText**</span></span> <br/> |
   

