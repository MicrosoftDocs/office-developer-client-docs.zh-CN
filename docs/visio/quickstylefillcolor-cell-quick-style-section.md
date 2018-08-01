---
title: QuickStyleFillColor 单元格（“Quick Style”部分）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 41250e47-404c-40e7-99be-9bb8c1ed5ba2
description: 确定形状的填充使用，为从 0 到 7 的整数的主题颜色
ms.openlocfilehash: dcbb974947821327e7cff6634fd9435f5e5845bf
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781007"
---
# <a name="quickstylefillcolor-cell-quick-style-section"></a><span data-ttu-id="f82f3-103">QuickStyleFillColor 单元格（“Quick Style”部分）</span><span class="sxs-lookup"><span data-stu-id="f82f3-103">QuickStyleFillColor Cell (Quick Style Section)</span></span>

<span data-ttu-id="f82f3-104">确定形状的填充使用，为从 0 到 7 的整数的主题颜色</span><span class="sxs-lookup"><span data-stu-id="f82f3-104">Determines which theme color that a shape's fill uses, as an integer from 0 to 7</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="f82f3-105">值</span><span class="sxs-lookup"><span data-stu-id="f82f3-105">Value</span></span>  <br/> |<span data-ttu-id="f82f3-106">说明</span><span class="sxs-lookup"><span data-stu-id="f82f3-106">Description</span></span>  <br/> |
|<span data-ttu-id="f82f3-107">0</span><span class="sxs-lookup"><span data-stu-id="f82f3-107">0</span></span>  <br/> |<span data-ttu-id="f82f3-108">形状的填充颜色继承自深主题颜色。</span><span class="sxs-lookup"><span data-stu-id="f82f3-108">The shape fill color inherits from the Dark theme color.</span></span>  <br/> |
|<span data-ttu-id="f82f3-109">1</span><span class="sxs-lookup"><span data-stu-id="f82f3-109">1</span></span>  <br/> |<span data-ttu-id="f82f3-110">形状的填充颜色继承自浅主题颜色。</span><span class="sxs-lookup"><span data-stu-id="f82f3-110">The shape fill color inherits from the Light theme color.</span></span>  <br/> |
|<span data-ttu-id="f82f3-111">2</span><span class="sxs-lookup"><span data-stu-id="f82f3-111">2</span></span>  <br/> |<span data-ttu-id="f82f3-112">形状的填充颜色继承自强调文字颜色 1 主题颜色</span><span class="sxs-lookup"><span data-stu-id="f82f3-112">The shape fill color inherits from the Accent 1 theme color</span></span>  <br/> |
|<span data-ttu-id="f82f3-113">3</span><span class="sxs-lookup"><span data-stu-id="f82f3-113">3</span></span>  <br/> |<span data-ttu-id="f82f3-114">形状的填充颜色继承自强调文字颜色 2 主题颜色</span><span class="sxs-lookup"><span data-stu-id="f82f3-114">The shape fill color inherits from the Accent 2 theme color</span></span>  <br/> |
|<span data-ttu-id="f82f3-115">4</span><span class="sxs-lookup"><span data-stu-id="f82f3-115">4</span></span>  <br/> |<span data-ttu-id="f82f3-116">形状的填充颜色继承自强调文字颜色 3 主题颜色</span><span class="sxs-lookup"><span data-stu-id="f82f3-116">The shape fill color inherits from the Accent 3 theme color</span></span>  <br/> |
|<span data-ttu-id="f82f3-117">5</span><span class="sxs-lookup"><span data-stu-id="f82f3-117">5</span></span>  <br/> |<span data-ttu-id="f82f3-118">形状的填充颜色继承自强调文字颜色 4 主题颜色</span><span class="sxs-lookup"><span data-stu-id="f82f3-118">The shape fill color inherits from the Accent 4 theme color</span></span>  <br/> |
|<span data-ttu-id="f82f3-119">6</span><span class="sxs-lookup"><span data-stu-id="f82f3-119">6</span></span>  <br/> |<span data-ttu-id="f82f3-120">形状的填充颜色继承自强调文字颜色 5 主题颜色</span><span class="sxs-lookup"><span data-stu-id="f82f3-120">The shape fill color inherits from the Accent 5 theme color</span></span>  <br/> |
|<span data-ttu-id="f82f3-121">7</span><span class="sxs-lookup"><span data-stu-id="f82f3-121">7</span></span>  <br/> |<span data-ttu-id="f82f3-122">形状的填充颜色继承自强调文字颜色 6 主题颜色</span><span class="sxs-lookup"><span data-stu-id="f82f3-122">The shape fill color inherits from the Accent 6 theme color</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="f82f3-123">说明</span><span class="sxs-lookup"><span data-stu-id="f82f3-123">Remarks</span></span>

<span data-ttu-id="f82f3-124">要从另一个公式，由**N** **单元格**元素的属性的值或使用**CellsU**属性从某个程序按名称获取对**QuickStyleFillColor**单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="f82f3-124">To get a reference to the **QuickStyleFillColor** cell by name from another formula, by value of the **N** attribute of a **Cell** element, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="f82f3-125">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="f82f3-125">Cell name:</span></span>  <br/> | <span data-ttu-id="f82f3-126">QuickStyleFillColor</span><span class="sxs-lookup"><span data-stu-id="f82f3-126">QuickStyleFillColor</span></span>  <br/> |
   
<span data-ttu-id="f82f3-127">若要从某个程序按索引获取对**QuickStyleFillColor**单元格的引用，请使用带下列参数的**CellsSRC**属性：</span><span class="sxs-lookup"><span data-stu-id="f82f3-127">To get a reference to the **QuickStyleFillColor** cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="f82f3-128">内容索引：</span><span class="sxs-lookup"><span data-stu-id="f82f3-128">Section index:</span></span>  <br/> |<span data-ttu-id="f82f3-129">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="f82f3-129">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="f82f3-130">行索引：</span><span class="sxs-lookup"><span data-stu-id="f82f3-130">Row index:</span></span>  <br/> |<span data-ttu-id="f82f3-131">**visRowQuickStyleProperties**</span><span class="sxs-lookup"><span data-stu-id="f82f3-131">**visRowQuickStyleProperties**</span></span> <br/> |
| <span data-ttu-id="f82f3-132">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="f82f3-132">Cell index:</span></span>  <br/> |<span data-ttu-id="f82f3-133">**visQuickStyleFillColor**</span><span class="sxs-lookup"><span data-stu-id="f82f3-133">**visQuickStyleFillColor**</span></span> <br/> |
   

