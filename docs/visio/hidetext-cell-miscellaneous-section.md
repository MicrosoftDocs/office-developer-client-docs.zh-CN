---
title: HideText 单元格（“Miscellaneous”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251323
localization_priority: Normal
ms.assetid: 3d23647a-e567-da71-50df-336a0f2f4071
description: 隐藏形状的文本。您可以查看文本块中的文本、编辑属性并将样式应用到文本，但是所做的更改需要等到您将 HideText 重置为 FALSE (0) 之后才会显现。
ms.openlocfilehash: 3e1be814984ed15247c451f5cd86d0f7a6dba71a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32329958"
---
# <a name="hidetext-cell-miscellaneous-section"></a><span data-ttu-id="491c1-104">HideText 单元格（“Miscellaneous”内容）</span><span class="sxs-lookup"><span data-stu-id="491c1-104">HideText Cell (Miscellaneous Section)</span></span>

<span data-ttu-id="491c1-p102">隐藏形状的文本。您可以查看文本块中的文本、编辑属性并将样式应用到文本，但是所做的更改需要等到您将 HideText 重置为 FALSE (0) 之后才会显现。</span><span class="sxs-lookup"><span data-stu-id="491c1-p102">Hides the text for a shape. You can view text, edit properties, and apply styles to the text in the text block, although the changes will not appear until you reset HideText to FALSE (0).</span></span>
  
|<span data-ttu-id="491c1-107">**Value**</span><span class="sxs-lookup"><span data-stu-id="491c1-107">**Value**</span></span>|<span data-ttu-id="491c1-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="491c1-108">**Description**</span></span>|
|:-----|:-----|
| <span data-ttu-id="491c1-109">TRUE</span><span class="sxs-lookup"><span data-stu-id="491c1-109">TRUE</span></span>  <br/> | <span data-ttu-id="491c1-110">隐藏文本且不能打印。</span><span class="sxs-lookup"><span data-stu-id="491c1-110">Text is hidden and does not print.</span></span>  <br/> |
| <span data-ttu-id="491c1-111">FALSE</span><span class="sxs-lookup"><span data-stu-id="491c1-111">FALSE</span></span>  <br/> | <span data-ttu-id="491c1-112">不隐藏文本。</span><span class="sxs-lookup"><span data-stu-id="491c1-112">Text is not hidden.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="491c1-113">注解</span><span class="sxs-lookup"><span data-stu-id="491c1-113">Remarks</span></span>

<span data-ttu-id="491c1-114">若要从另一个公式或从使用**CellsU**属性的某个程序按名称获取对 HideText 单元格的引用, 请使用:</span><span class="sxs-lookup"><span data-stu-id="491c1-114">To get a reference to the HideText cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="491c1-115">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="491c1-115">Cell name:</span></span>  <br/> | <span data-ttu-id="491c1-116">HideText</span><span class="sxs-lookup"><span data-stu-id="491c1-116">HideText</span></span>  <br/> |
   
<span data-ttu-id="491c1-117">若要从某个程序按索引获取对 HideText 单元格的引用, 请使用带下列参数的**CellsSRC**属性:</span><span class="sxs-lookup"><span data-stu-id="491c1-117">To get a reference to the HideText cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="491c1-118">内容索引：</span><span class="sxs-lookup"><span data-stu-id="491c1-118">Section index:</span></span>  <br/> |<span data-ttu-id="491c1-119">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="491c1-119">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="491c1-120">行索引：</span><span class="sxs-lookup"><span data-stu-id="491c1-120">Row index:</span></span>  <br/> |<span data-ttu-id="491c1-121">**visRowMisc**</span><span class="sxs-lookup"><span data-stu-id="491c1-121">**visRowMisc**</span></span> <br/> |
| <span data-ttu-id="491c1-122">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="491c1-122">Cell index:</span></span>  <br/> |<span data-ttu-id="491c1-123">**visHideText**</span><span class="sxs-lookup"><span data-stu-id="491c1-123">**visHideText**</span></span> <br/> |
   

