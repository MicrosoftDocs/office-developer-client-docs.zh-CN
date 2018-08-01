---
title: LineGradientEnabled 单元格（“Gradient Properties”部分）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 276a661f-d14e-404a-a494-ae36601a8ce3
description: 确定是否将行渐变启用了线条或形状边框。
ms.openlocfilehash: d78a94a25c0290bd5e58522c9a45955868f31b32
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780562"
---
# <a name="linegradientenabled-cell-gradient-properties-section"></a><span data-ttu-id="67a78-103">LineGradientEnabled 单元格（“Gradient Properties”部分）</span><span class="sxs-lookup"><span data-stu-id="67a78-103">LineGradientEnabled Cell (Gradient Properties Section)</span></span>

<span data-ttu-id="67a78-104">确定是否将行渐变启用了线条或形状边框。</span><span class="sxs-lookup"><span data-stu-id="67a78-104">Determines whether a line gradient is enabled for a line or border of a shape.</span></span> 
  
|<span data-ttu-id="67a78-105">**值**</span><span class="sxs-lookup"><span data-stu-id="67a78-105">**Value**</span></span>|<span data-ttu-id="67a78-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="67a78-106">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="67a78-107">TRUE</span><span class="sxs-lookup"><span data-stu-id="67a78-107">TRUE</span></span>  <br/> |<span data-ttu-id="67a78-108">渐变的线条或形状边框上显示。</span><span class="sxs-lookup"><span data-stu-id="67a78-108">Gradient is displayed on the line or border of a shape.</span></span>  <br/> |
|<span data-ttu-id="67a78-109">FALSE</span><span class="sxs-lookup"><span data-stu-id="67a78-109">FALSE</span></span>  <br/> |<span data-ttu-id="67a78-110">行或形状边框上不显示渐变。</span><span class="sxs-lookup"><span data-stu-id="67a78-110">Gradients are not displayed on the line or border of a shape.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="67a78-111">说明</span><span class="sxs-lookup"><span data-stu-id="67a78-111">Remarks</span></span>

<span data-ttu-id="67a78-112">要从另一个公式，由**N** **单元格**元素的属性的值或使用**CellsU**属性从某个程序按名称获取对**LineGradientEnabled**单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="67a78-112">To get a reference to the **LineGradientEnabled** cell by name from another formula, by value of the **N** attribute of a **Cell** element, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="67a78-113">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="67a78-113">Cell name:</span></span>  <br/> | <span data-ttu-id="67a78-114">LineGradientEnabled</span><span class="sxs-lookup"><span data-stu-id="67a78-114">LineGradientEnabled</span></span>  <br/> |
   
<span data-ttu-id="67a78-115">若要从某个程序按索引获取对**LineGradientEnabled**单元格的引用，请使用带下列参数的**CellsSRC**属性：</span><span class="sxs-lookup"><span data-stu-id="67a78-115">To get a reference to the **LineGradientEnabled** cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="67a78-116">内容索引：</span><span class="sxs-lookup"><span data-stu-id="67a78-116">Section index:</span></span>  <br/> |<span data-ttu-id="67a78-117">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="67a78-117">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="67a78-118">行索引：</span><span class="sxs-lookup"><span data-stu-id="67a78-118">Row index:</span></span>  <br/> |<span data-ttu-id="67a78-119">**visRowGradientProperties**</span><span class="sxs-lookup"><span data-stu-id="67a78-119">**visRowGradientProperties**</span></span> <br/> |
| <span data-ttu-id="67a78-120">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="67a78-120">Cell index:</span></span>  <br/> |<span data-ttu-id="67a78-121">**visLineGradientEnabled**</span><span class="sxs-lookup"><span data-stu-id="67a78-121">**visLineGradientEnabled**</span></span> <br/> |
   

