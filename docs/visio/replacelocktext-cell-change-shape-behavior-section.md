---
title: ReplaceLockText 单元格 ("更改形状行为" 部分)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 31f43ebe-3758-4fd9-83b5-775041c5890f
description: 指示主控形状中指定单元格的值是否覆盖在形状替换操作过程中要替换的形状的值 (包括本地值)。 ReplaceLockText 确定主控形状上显示的文本是否覆盖正在替换的形状的文本。
ms.openlocfilehash: 299bd571ad935886879abb11108c3d0bd28e3183
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33411916"
---
# <a name="replacelocktext-cell-change-shape-behavior-section"></a><span data-ttu-id="b2ecf-104">ReplaceLockText 单元格 ("更改形状行为" 部分)</span><span class="sxs-lookup"><span data-stu-id="b2ecf-104">ReplaceLockText Cell (Change Shape Behavior Section)</span></span>

<span data-ttu-id="b2ecf-105">指示主控形状中指定单元格的值是否覆盖在形状替换操作过程中要替换的形状的值 (包括本地值)。</span><span class="sxs-lookup"><span data-stu-id="b2ecf-105">Indicates whether the values of specified cells in a master shape overwrite the values (including local values) of a shape being replaced during a shape replacement operation.</span></span> <span data-ttu-id="b2ecf-106">**ReplaceLockText**确定主控形状上显示的文本是否覆盖正在替换的形状的文本。</span><span class="sxs-lookup"><span data-stu-id="b2ecf-106">The **ReplaceLockText** determines whether the text displayed on the Master overwrites the text of the shape being replaced.</span></span> 
  
|<span data-ttu-id="b2ecf-107">**值**</span><span class="sxs-lookup"><span data-stu-id="b2ecf-107">**Value**</span></span>|<span data-ttu-id="b2ecf-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="b2ecf-108">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b2ecf-109">TRUE</span><span class="sxs-lookup"><span data-stu-id="b2ecf-109">TRUE</span></span>  <br/> | <span data-ttu-id="b2ecf-110">主控形状上的文本将覆盖旧形状上的文本。</span><span class="sxs-lookup"><span data-stu-id="b2ecf-110">The text on the master shape overwrites the text on the old shape.</span></span> <span data-ttu-id="b2ecf-111">此外, 主控形状替换操作过程中, 主控形状将覆盖以下各节中的单元格的值:</span><span class="sxs-lookup"><span data-stu-id="b2ecf-111">In addition, the master shape overwrites the values of the cells in the following sections during a shape replacement operation:</span></span>  <br/> <span data-ttu-id="b2ecf-112">"**文本字段**" 部分</span><span class="sxs-lookup"><span data-stu-id="b2ecf-112">**Text Fields** section</span></span>  <br/> <span data-ttu-id="b2ecf-113">"**文本块格式**" 部分</span><span class="sxs-lookup"><span data-stu-id="b2ecf-113">**Text Block Format** section</span></span>  <br/> |
|<span data-ttu-id="b2ecf-114">FALSE</span><span class="sxs-lookup"><span data-stu-id="b2ecf-114">FALSE</span></span>  <br/> |<span data-ttu-id="b2ecf-115">替换形状包含旧形状中已添加到形状中的任何文本、文本字段或其他文本属性。</span><span class="sxs-lookup"><span data-stu-id="b2ecf-115">The replacement shape contains any text, text fields, or other text properties from the old shape that have been added to the shape.</span></span>  <br/> <span data-ttu-id="b2ecf-116">当替换形状包含旧形状中的文本属性时, 如果旧形状的**字符**和**段落**部分中有多行, 则替换形状也具有这些值。</span><span class="sxs-lookup"><span data-stu-id="b2ecf-116">When the replacement shape contains text properties from the old shape, the replacement shape also has the values from the **Character** and **Paragraph** sections of the old shape if they have more than one row.</span></span>  <br/> |
   
<span data-ttu-id="b2ecf-117">如果设置为 TRUE (1), 则形状主控形状的值将替换要替换的形状上的以下值:</span><span class="sxs-lookup"><span data-stu-id="b2ecf-117">If set to TRUE (1), the values of the shape Master replaces the values of the following on the shape being replaced:</span></span>
  
- [<span data-ttu-id="b2ecf-118">TheText Cell (Events Section)</span><span class="sxs-lookup"><span data-stu-id="b2ecf-118">TheText Cell (Events Section)</span></span>](thetext-cell-events-section.md)
    
- <span data-ttu-id="b2ecf-119">"字符"[部分](character-section.md)中的单元格</span><span class="sxs-lookup"><span data-stu-id="b2ecf-119">Cells in the [Character Section](character-section.md)</span></span>
    
- <span data-ttu-id="b2ecf-120">"段落"[部分](paragraph-section.md)中的单元格</span><span class="sxs-lookup"><span data-stu-id="b2ecf-120">Cells in the [Paragraph Section](paragraph-section.md)</span></span>
    
- <span data-ttu-id="b2ecf-121">"[选项卡" 部分](tabs-section.md)中的单元格</span><span class="sxs-lookup"><span data-stu-id="b2ecf-121">Cells in the [Tabs Section](tabs-section.md)</span></span>
    
## <a name="remarks"></a><span data-ttu-id="b2ecf-122">说明</span><span class="sxs-lookup"><span data-stu-id="b2ecf-122">Remarks</span></span>

<span data-ttu-id="b2ecf-123">若要从另一个公式按名称获取对**ReplaceLockText**单元格的引用、 **cell**元素的**N**属性值, 或从使用**CellsU**属性的某个程序获取对该单元格的引用, 请使用:</span><span class="sxs-lookup"><span data-stu-id="b2ecf-123">To get a reference to the **ReplaceLockText** cell by name from another formula, by value of the **N** attribute of a **Cell** element, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="b2ecf-124">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="b2ecf-124">Cell name:</span></span>  <br/> | <span data-ttu-id="b2ecf-125">ReplaceLockText</span><span class="sxs-lookup"><span data-stu-id="b2ecf-125">ReplaceLockText</span></span>  <br/> |
   
<span data-ttu-id="b2ecf-126">若要从某个程序按索引获取对**ReplaceLockText**单元格的引用, 请使用带下列参数的**CellsSRC**属性:</span><span class="sxs-lookup"><span data-stu-id="b2ecf-126">To get a reference to the **ReplaceLockText** cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="b2ecf-127">内容索引：</span><span class="sxs-lookup"><span data-stu-id="b2ecf-127">Section index:</span></span>  <br/> |<span data-ttu-id="b2ecf-128">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="b2ecf-128">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="b2ecf-129">行索引：</span><span class="sxs-lookup"><span data-stu-id="b2ecf-129">Row index:</span></span>  <br/> |<span data-ttu-id="b2ecf-130">**visRowReplaceBehaviors**</span><span class="sxs-lookup"><span data-stu-id="b2ecf-130">**visRowReplaceBehaviors**</span></span> <br/> |
| <span data-ttu-id="b2ecf-131">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="b2ecf-131">Cell index:</span></span>  <br/> |<span data-ttu-id="b2ecf-132">**visReplaceLockText**</span><span class="sxs-lookup"><span data-stu-id="b2ecf-132">**visReplaceLockText**</span></span> <br/> |
   

