---
title: UseGroupGradient 单元格（“Gradient Properties”部分）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: f1dcf0ec-8b4a-4ee1-9208-b1c84e30d37b
description: 确定当形状以 Boolean 的形式进行分组以及其他形状时, 是否将形状承担渐变。 UseGroupGradient 单元格的值影响的形状填充。
ms.openlocfilehash: ca11ad1c54097b4883bb5348583c6cf39127e4e5
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781605"
---
# <a name="usegroupgradient-cell-gradient-properties-section"></a><span data-ttu-id="9a0b2-104">UseGroupGradient 单元格（“Gradient Properties”部分）</span><span class="sxs-lookup"><span data-stu-id="9a0b2-104">UseGroupGradient Cell (Gradient Properties Section)</span></span>

<span data-ttu-id="9a0b2-105">确定当形状以 Boolean 的形式进行分组以及其他形状时, 是否将形状承担渐变。</span><span class="sxs-lookup"><span data-stu-id="9a0b2-105">Determines whether the shape takes on a gradient when the shape is grouped together with other shapes, as a Boolean.</span></span> <span data-ttu-id="9a0b2-106">**UseGroupGradient**单元格的值影响的形状填充。</span><span class="sxs-lookup"><span data-stu-id="9a0b2-106">The value of **UseGroupGradient** cell affects the shape fill only.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="9a0b2-107">说明</span><span class="sxs-lookup"><span data-stu-id="9a0b2-107">Remarks</span></span>

<span data-ttu-id="9a0b2-108">要从另一个公式，由**N** **单元格**元素的属性的值或使用**CellsU**属性从某个程序按名称获取对**UseGroupGradient**单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="9a0b2-108">To get a reference to the **UseGroupGradient** cell by name from another formula, by value of the **N** attribute of a **Cell** element, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="9a0b2-109">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="9a0b2-109">Cell name:</span></span>  <br/> | <span data-ttu-id="9a0b2-110">UseGroupGradient</span><span class="sxs-lookup"><span data-stu-id="9a0b2-110">UseGroupGradient</span></span>  <br/> |
   
<span data-ttu-id="9a0b2-111">若要从某个程序按索引获取对**UseGroupGradient**单元格的引用，请使用带下列参数的**CellsSRC**属性：</span><span class="sxs-lookup"><span data-stu-id="9a0b2-111">To get a reference to the **UseGroupGradient** cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="9a0b2-112">内容索引：</span><span class="sxs-lookup"><span data-stu-id="9a0b2-112">Section index:</span></span>  <br/> |<span data-ttu-id="9a0b2-113">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="9a0b2-113">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="9a0b2-114">行索引：</span><span class="sxs-lookup"><span data-stu-id="9a0b2-114">Row index:</span></span>  <br/> |<span data-ttu-id="9a0b2-115">**visRowGradientProperties**</span><span class="sxs-lookup"><span data-stu-id="9a0b2-115">**visRowGradientProperties**</span></span> <br/> |
| <span data-ttu-id="9a0b2-116">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="9a0b2-116">Cell index:</span></span>  <br/> |<span data-ttu-id="9a0b2-117">* * visUseGroupGradient * *</span><span class="sxs-lookup"><span data-stu-id="9a0b2-117">**visUseGroupGradient **</span></span> <br/> |
   

