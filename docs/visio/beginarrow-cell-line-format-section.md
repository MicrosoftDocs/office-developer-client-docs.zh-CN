---
title: BeginArrow 单元格（“Line Format”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm51105
localization_priority: Normal
ms.assetid: 0ab4044e-2d77-1fbe-ef20-5d029bc064ba
description: 指明线条的第一个顶点是否有箭头或其他线端格式。 输入介于 0 到 45 之间的数字或带有自定义线端名的 USE 函数，或使用“线条”对话框。
ms.openlocfilehash: cf5a512dabd0e6296b83fa7bfd2a2a6134143d50
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33410292"
---
# <a name="beginarrow-cell-line-format-section"></a><span data-ttu-id="44976-104">BeginArrow 单元格（“Line Format”内容）</span><span class="sxs-lookup"><span data-stu-id="44976-104">BeginArrow Cell (Line Format Section)</span></span>

<span data-ttu-id="44976-p102">指明线条的第一个顶点是否有箭头或其他线端格式。输入介于 0 到 45 之间的数字或带有自定义线端名的 USE 函数，或使用 **“线条”** 对话框。</span><span class="sxs-lookup"><span data-stu-id="44976-p102">Indicates whether a line has an arrowhead or other line end format at its first vertex. Enter a number from 0 to 45 or the USE function with the name of a custom line end, or use the **Line** dialog box.</span></span> 
  
|<span data-ttu-id="44976-107">**值**</span><span class="sxs-lookup"><span data-stu-id="44976-107">**Value**</span></span>|<span data-ttu-id="44976-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="44976-108">**Description**</span></span>|
|:-----|:-----|
| <span data-ttu-id="44976-109">0</span><span class="sxs-lookup"><span data-stu-id="44976-109">0</span></span>  <br/> | <span data-ttu-id="44976-110">无箭头。</span><span class="sxs-lookup"><span data-stu-id="44976-110">No arrowhead.</span></span>  <br/> |
| <span data-ttu-id="44976-111">1 - 45</span><span class="sxs-lookup"><span data-stu-id="44976-111">1 - 45</span></span>  <br/> | <span data-ttu-id="44976-112">各种类型的箭头样式，与 **“线条”** 对话框中的索引项相对应。</span><span class="sxs-lookup"><span data-stu-id="44976-112">Assorted arrowhead styles that correspond to indexed entries in the **Line** dialog box.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="44976-113">说明</span><span class="sxs-lookup"><span data-stu-id="44976-113">Remarks</span></span>

<span data-ttu-id="44976-114">箭头的大小在 BeginArrowSize 单元格中设置。</span><span class="sxs-lookup"><span data-stu-id="44976-114">The size of the arrowhead is set in the BeginArrowSize cell.</span></span>
  
<span data-ttu-id="44976-115">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 BeginArrow 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="44976-115">To get a reference to the BeginArrow cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="44976-116">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="44976-116">Cell name:</span></span>  <br/> | <span data-ttu-id="44976-117">BeginArrow</span><span class="sxs-lookup"><span data-stu-id="44976-117">BeginArrow</span></span>  <br/> |
   
<span data-ttu-id="44976-118">要从某个程序按索引获取对 BeginArrow 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="44976-118">To get a reference to the BeginArrow cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="44976-119">内容索引：</span><span class="sxs-lookup"><span data-stu-id="44976-119">Section index:</span></span>  <br/> |<span data-ttu-id="44976-120">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="44976-120">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="44976-121">行索引：</span><span class="sxs-lookup"><span data-stu-id="44976-121">Row index:</span></span>  <br/> |<span data-ttu-id="44976-122">**visRowLine**</span><span class="sxs-lookup"><span data-stu-id="44976-122">**visRowLine**</span></span> <br/> |
| <span data-ttu-id="44976-123">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="44976-123">Cell index:</span></span>  <br/> |<span data-ttu-id="44976-124">**visLineBeginArrow**</span><span class="sxs-lookup"><span data-stu-id="44976-124">**visLineBeginArrow**</span></span> <br/> |
   

