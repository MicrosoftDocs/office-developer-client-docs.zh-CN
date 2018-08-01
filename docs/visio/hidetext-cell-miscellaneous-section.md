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
ms.openlocfilehash: e2d220e9d7874382f2aaeade5488bd4809f3a9dd
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780405"
---
# <a name="hidetext-cell-miscellaneous-section"></a><span data-ttu-id="8a9e0-104">HideText 单元格（“Miscellaneous”部分）</span><span class="sxs-lookup"><span data-stu-id="8a9e0-104">HideText Cell (Miscellaneous Section)</span></span>

<span data-ttu-id="8a9e0-p102">隐藏形状的文本。您可以查看文本块中的文本、编辑属性并将样式应用到文本，但是所做的更改需要等到您将 HideText 重置为 FALSE (0) 之后才会显现。</span><span class="sxs-lookup"><span data-stu-id="8a9e0-p102">Hides the text for a shape. You can view text, edit properties, and apply styles to the text in the text block, although the changes will not appear until you reset HideText to FALSE (0).</span></span>
  
|<span data-ttu-id="8a9e0-107">**值**</span><span class="sxs-lookup"><span data-stu-id="8a9e0-107">**Value**</span></span>|<span data-ttu-id="8a9e0-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="8a9e0-108">**Description**</span></span>|
|:-----|:-----|
| <span data-ttu-id="8a9e0-109">TRUE</span><span class="sxs-lookup"><span data-stu-id="8a9e0-109">TRUE</span></span>  <br/> | <span data-ttu-id="8a9e0-110">隐藏文本且不能打印。</span><span class="sxs-lookup"><span data-stu-id="8a9e0-110">Text is hidden and does not print.</span></span>  <br/> |
| <span data-ttu-id="8a9e0-111">FALSE</span><span class="sxs-lookup"><span data-stu-id="8a9e0-111">FALSE</span></span>  <br/> | <span data-ttu-id="8a9e0-112">不隐藏文本。</span><span class="sxs-lookup"><span data-stu-id="8a9e0-112">Text is not hidden.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="8a9e0-113">注释</span><span class="sxs-lookup"><span data-stu-id="8a9e0-113">Remarks</span></span>

<span data-ttu-id="8a9e0-114">要从另一个公式或使用**CellsU**属性从某个程序按名称获取对 HideText 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="8a9e0-114">To get a reference to the HideText cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="8a9e0-115">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="8a9e0-115">Cell name:</span></span>  <br/> | <span data-ttu-id="8a9e0-116">HideText</span><span class="sxs-lookup"><span data-stu-id="8a9e0-116">HideText</span></span>  <br/> |
   
<span data-ttu-id="8a9e0-117">若要从某个程序按索引获取对 HideText 单元格的引用，请使用带下列参数的**CellsSRC**属性：</span><span class="sxs-lookup"><span data-stu-id="8a9e0-117">To get a reference to the HideText cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="8a9e0-118">内容索引：</span><span class="sxs-lookup"><span data-stu-id="8a9e0-118">Section index:</span></span>  <br/> |<span data-ttu-id="8a9e0-119">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="8a9e0-119">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="8a9e0-120">行索引：</span><span class="sxs-lookup"><span data-stu-id="8a9e0-120">Row index:</span></span>  <br/> |<span data-ttu-id="8a9e0-121">**visRowMisc**</span><span class="sxs-lookup"><span data-stu-id="8a9e0-121">**visRowMisc**</span></span> <br/> |
| <span data-ttu-id="8a9e0-122">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="8a9e0-122">Cell index:</span></span>  <br/> |<span data-ttu-id="8a9e0-123">**visHideText**</span><span class="sxs-lookup"><span data-stu-id="8a9e0-123">**visHideText**</span></span> <br/> |
   

