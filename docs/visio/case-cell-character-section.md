---
title: Case 单元格（“Character”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251250
localization_priority: Normal
ms.assetid: cf063c05-5789-e037-700b-1e70df00e254
description: 确定形状文本的大小写。全部大写字母 (1) 和首字母大写字母 (2) 都不会更改以全部大写字母输入的文本的外观。只有文本是以小写字母输入时，这些选项才有效。
ms.openlocfilehash: 50ceaa1188caded40d36b8837c346fbbba2e14d2
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33434345"
---
# <a name="case-cell-character-section"></a><span data-ttu-id="96e15-105">Case 单元格（“Character”内容）</span><span class="sxs-lookup"><span data-stu-id="96e15-105">Case Cell (Character Section)</span></span>

<span data-ttu-id="96e15-p102">确定形状文本的大小写。全部大写字母 (1) 和首字母大写字母 (2) 都不会更改以全部大写字母输入的文本的外观。只有文本是以小写字母输入时，这些选项才有效。</span><span class="sxs-lookup"><span data-stu-id="96e15-p102">Determines the case of a shape's text. All capital (uppercase) letters (1) and initial capital letters (2) do not change the appearance of text that was entered in all capital letters. The text must be entered in lowercase letters for these options to show an effect.</span></span>
  
|<span data-ttu-id="96e15-109">**值**</span><span class="sxs-lookup"><span data-stu-id="96e15-109">**Value**</span></span>|<span data-ttu-id="96e15-110">**说明**</span><span class="sxs-lookup"><span data-stu-id="96e15-110">**Description**</span></span>|<span data-ttu-id="96e15-111">**自动常量**</span><span class="sxs-lookup"><span data-stu-id="96e15-111">**Automation constant**</span></span>|
|:-----|:-----|:-----|
| <span data-ttu-id="96e15-112">0</span><span class="sxs-lookup"><span data-stu-id="96e15-112">0</span></span>  <br/> | <span data-ttu-id="96e15-113">普通大小写</span><span class="sxs-lookup"><span data-stu-id="96e15-113">Normal case</span></span>  <br/> |<span data-ttu-id="96e15-114">**visCaseNormal**</span><span class="sxs-lookup"><span data-stu-id="96e15-114">**visCaseNormal**</span></span> <br/> |
| <span data-ttu-id="96e15-115">1</span><span class="sxs-lookup"><span data-stu-id="96e15-115">1</span></span>  <br/> | <span data-ttu-id="96e15-116">全部大写字母</span><span class="sxs-lookup"><span data-stu-id="96e15-116">All capital (uppercase) letters</span></span>  <br/> |<span data-ttu-id="96e15-117">**visCaseAllCaps**</span><span class="sxs-lookup"><span data-stu-id="96e15-117">**visCaseAllCaps**</span></span> <br/> |
| <span data-ttu-id="96e15-118">2</span><span class="sxs-lookup"><span data-stu-id="96e15-118">2</span></span>  <br/> | <span data-ttu-id="96e15-119">仅首字母大写字母</span><span class="sxs-lookup"><span data-stu-id="96e15-119">Initial capital letters only</span></span>  <br/> |<span data-ttu-id="96e15-120">**visCaseInitialCaps**</span><span class="sxs-lookup"><span data-stu-id="96e15-120">**visCaseInitialCaps**</span></span> <br/> |
   
## <a name="remarks"></a><span data-ttu-id="96e15-121">备注</span><span class="sxs-lookup"><span data-stu-id="96e15-121">Remarks</span></span>

<span data-ttu-id="96e15-122">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 Case 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="96e15-122">To get a reference to the Case cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="96e15-123">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="96e15-123">Cell name:</span></span>  <br/> | <span data-ttu-id="96e15-124">Char.Case[  *i*  ] 其中  *i*  = <1>，2， 3， ...</span><span class="sxs-lookup"><span data-stu-id="96e15-124">Char.Case[  *i*  ]            where  *i*  = <1>, 2, 3, ...</span></span>  <br/> |
   
<span data-ttu-id="96e15-125">要从某个程序按索引获取对 Case 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="96e15-125">To get a reference to the Case cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="96e15-126">内容索引：</span><span class="sxs-lookup"><span data-stu-id="96e15-126">Section index:</span></span>  <br/> |<span data-ttu-id="96e15-127">**visSectionCharacter**</span><span class="sxs-lookup"><span data-stu-id="96e15-127">**visSectionCharacter**</span></span> <br/> |
| <span data-ttu-id="96e15-128">行索引：</span><span class="sxs-lookup"><span data-stu-id="96e15-128">Row index:</span></span>  <br/> |<span data-ttu-id="96e15-129">**visRowCharacter**  +  *i* 其中 *i* = 0， 1， 2， ...</span><span class="sxs-lookup"><span data-stu-id="96e15-129">**visRowCharacter** +  *i*            where  *i*  = 0, 1, 2, ...</span></span>  <br/> |
| <span data-ttu-id="96e15-130">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="96e15-130">Cell index:</span></span>  <br/> |<span data-ttu-id="96e15-131">**visCharacterCase**</span><span class="sxs-lookup"><span data-stu-id="96e15-131">**visCharacterCase**</span></span> <br/> |
   

