---
title: X Justify 单元格（“Action Tags”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm1026936
localization_priority: Normal
ms.assetid: a8995020-3eaa-2b2c-eca0-dd475de4d06f
description: 动作标记按钮相对于由 x 单元格和 Y 单元格定义的点的 x 轴偏移量。
ms.openlocfilehash: f8542d2f3a22b12794d999323d202d7a5bece20b
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32284970"
---
# <a name="x-justify-cell-action-tags-section"></a><span data-ttu-id="08ee6-103">X Justify 单元格（“Action Tags”内容）</span><span class="sxs-lookup"><span data-stu-id="08ee6-103">X Justify Cell (Action Tags Section)</span></span>

<span data-ttu-id="08ee6-104">动作标记按钮相对于由 x 单元格和 Y 单元格定义的点的*x*轴偏移量。</span><span class="sxs-lookup"><span data-stu-id="08ee6-104">The  *x*  -offset of the action tag button relative to the point defined by the X and Y cells.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="08ee6-105">在以前版本的 Microsoft Visio 中，动作标记称为“智能标记”。</span><span class="sxs-lookup"><span data-stu-id="08ee6-105">In previous versions of Microsoft Visio, action tags are called smart tags.</span></span> 
  
|<span data-ttu-id="08ee6-106">**Value**</span><span class="sxs-lookup"><span data-stu-id="08ee6-106">**Value**</span></span>|<span data-ttu-id="08ee6-107">**说明**</span><span class="sxs-lookup"><span data-stu-id="08ee6-107">**Description**</span></span>|<span data-ttu-id="08ee6-108">**自动常量**</span><span class="sxs-lookup"><span data-stu-id="08ee6-108">**Automation constant**</span></span>|
|:-----|:-----|:-----|
| <span data-ttu-id="08ee6-109">0</span><span class="sxs-lookup"><span data-stu-id="08ee6-109">0</span></span>  <br/> | <span data-ttu-id="08ee6-110">左对齐（默认值）。</span><span class="sxs-lookup"><span data-stu-id="08ee6-110">Left justified (the default).</span></span>  <br/> |<span data-ttu-id="08ee6-111">**visSmartTagXJustifyLeft**</span><span class="sxs-lookup"><span data-stu-id="08ee6-111">**visSmartTagXJustifyLeft**</span></span> <br/> |
| <span data-ttu-id="08ee6-112">1</span><span class="sxs-lookup"><span data-stu-id="08ee6-112">1</span></span>  <br/> | <span data-ttu-id="08ee6-113">居中。</span><span class="sxs-lookup"><span data-stu-id="08ee6-113">Centered.</span></span>  <br/> |<span data-ttu-id="08ee6-114">**visSmartTagXJustifyCenter**</span><span class="sxs-lookup"><span data-stu-id="08ee6-114">**visSmartTagXJustifyCenter**</span></span> <br/> |
| <span data-ttu-id="08ee6-115">双面</span><span class="sxs-lookup"><span data-stu-id="08ee6-115">2</span></span>  <br/> | <span data-ttu-id="08ee6-116">右对齐。</span><span class="sxs-lookup"><span data-stu-id="08ee6-116">Right justified.</span></span>  <br/> |<span data-ttu-id="08ee6-117">**visSmartTagXJustifyRight**</span><span class="sxs-lookup"><span data-stu-id="08ee6-117">**visSmartTagXJustifyRight**</span></span> <br/> |
   
## <a name="remarks"></a><span data-ttu-id="08ee6-118">注解</span><span class="sxs-lookup"><span data-stu-id="08ee6-118">Remarks</span></span>

<span data-ttu-id="08ee6-119">x 两端对齐和 y 调整单元格确定操作标记按钮相对于 X 和 Y 单元格定义的点的放置位置。</span><span class="sxs-lookup"><span data-stu-id="08ee6-119">The X Justify and Y Justify cells determine where the action tag button is placed in relation to the point defined in the X and Y cells.</span></span> 
  
<span data-ttu-id="08ee6-120">若要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 X Justify 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="08ee6-120">To get a reference to the X Justify cell by name from another formula, or from a program by using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="08ee6-121">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="08ee6-121">Cell name:</span></span>  <br/> | <span data-ttu-id="08ee6-122">SmartTags.</span><span class="sxs-lookup"><span data-stu-id="08ee6-122">SmartTags.</span></span>  <span data-ttu-id="08ee6-123">*名称*。XJustify 其中的智能标记。</span><span class="sxs-lookup"><span data-stu-id="08ee6-123">*name*  .XJustify           where SmartTags.</span></span> <span data-ttu-id="08ee6-124">*name*是操作标记行的名称</span><span class="sxs-lookup"><span data-stu-id="08ee6-124">*name*  is the name of the action tag row</span></span>  <br/> |
   
<span data-ttu-id="08ee6-125">要从某个程序按索引获取对 X Justify 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="08ee6-125">To get a reference to the X Justify cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="08ee6-126">内容索引：</span><span class="sxs-lookup"><span data-stu-id="08ee6-126">Section index:</span></span>  <br/> |<span data-ttu-id="08ee6-127">**visSectionSmartTag**</span><span class="sxs-lookup"><span data-stu-id="08ee6-127">**visSectionSmartTag**</span></span> <br/> |
| <span data-ttu-id="08ee6-128">行索引：</span><span class="sxs-lookup"><span data-stu-id="08ee6-128">Row index:</span></span>  <br/> |<span data-ttu-id="08ee6-129">**visRowSmartTag** +  *i* = \*\* 0、1、2 .。。</span><span class="sxs-lookup"><span data-stu-id="08ee6-129">**visRowSmartTag** +  *i*            where  *i*  = 0, 1, 2...</span></span>  <br/> |
| <span data-ttu-id="08ee6-130">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="08ee6-130">Cell index:</span></span>  <br/> |<span data-ttu-id="08ee6-131">**visSmartTagXJustify**</span><span class="sxs-lookup"><span data-stu-id="08ee6-131">**visSmartTagXJustify**</span></span> <br/> |
   

