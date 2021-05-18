---
title: 'UseGroupGradient Cell (Gradient Properties Section) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: f1dcf0ec-8b4a-4ee1-9208-b1c84e30d37b
description: 确定形状与其他形状组合在一起时是否采用渐变，作为布尔值。 UseGroupGradient 单元格的值仅影响形状填充。
ms.openlocfilehash: a69b48095aec93705c686a5401051f1d1e368d18
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33411363"
---
# <a name="usegroupgradient-cell-gradient-properties-section"></a><span data-ttu-id="bca40-104">UseGroupGradient Cell (Gradient Properties Section) </span><span class="sxs-lookup"><span data-stu-id="bca40-104">UseGroupGradient Cell (Gradient Properties Section)</span></span>

<span data-ttu-id="bca40-105">确定形状与其他形状组合在一起时是否采用渐变，作为布尔值。</span><span class="sxs-lookup"><span data-stu-id="bca40-105">Determines whether the shape takes on a gradient when the shape is grouped together with other shapes, as a Boolean.</span></span> <span data-ttu-id="bca40-106">**UseGroupGradient** 单元格的值仅影响形状填充。</span><span class="sxs-lookup"><span data-stu-id="bca40-106">The value of **UseGroupGradient** cell affects the shape fill only.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="bca40-107">备注</span><span class="sxs-lookup"><span data-stu-id="bca40-107">Remarks</span></span>

<span data-ttu-id="bca40-108">若要从另一个公式 **、Cell** 元素 **的 N** 属性值或使用 **CellsU** 属性从某个程序按名称获取对 **UseGroupGradient** 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="bca40-108">To get a reference to the **UseGroupGradient** cell by name from another formula, by value of the **N** attribute of a **Cell** element, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="bca40-109">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="bca40-109">Cell name:</span></span>  <br/> | <span data-ttu-id="bca40-110">UseGroupGradient</span><span class="sxs-lookup"><span data-stu-id="bca40-110">UseGroupGradient</span></span>  <br/> |
   
<span data-ttu-id="bca40-111">若要从程序按索引获取对 **UseGroupGradient** 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="bca40-111">To get a reference to the **UseGroupGradient** cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="bca40-112">内容索引：</span><span class="sxs-lookup"><span data-stu-id="bca40-112">Section index:</span></span>  <br/> |<span data-ttu-id="bca40-113">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="bca40-113">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="bca40-114">行索引：</span><span class="sxs-lookup"><span data-stu-id="bca40-114">Row index:</span></span>  <br/> |<span data-ttu-id="bca40-115">**visRowGradientProperties**</span><span class="sxs-lookup"><span data-stu-id="bca40-115">**visRowGradientProperties**</span></span> <br/> |
| <span data-ttu-id="bca40-116">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="bca40-116">Cell index:</span></span>  <br/> |<span data-ttu-id="bca40-117">\*\*visUseGroupGradient \*\*</span><span class="sxs-lookup"><span data-stu-id="bca40-117">\*\*visUseGroupGradient \*\*</span></span> <br/> |
   

