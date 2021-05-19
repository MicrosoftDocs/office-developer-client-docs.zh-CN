---
title: 'QuickStyleVariation Cell (Quick Style Section) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: e3b58a19-9f1a-4f2b-9fe2-45cbb7ec6898
description: 确定是替代文本、线条和填充颜色的公式和值 (还是使用与图表背景) 来替代这些属性的组合。 值是 0、1、2、4 和 8 的位 OR。
ms.openlocfilehash: 736e2287c00c24774ef8b677613235d642697f4b
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33433792"
---
# <a name="quickstylevariation-cell-quick-style-section"></a><span data-ttu-id="23cc5-104">QuickStyleVariation Cell (Quick Style Section) </span><span class="sxs-lookup"><span data-stu-id="23cc5-104">QuickStyleVariation Cell (Quick Style Section)</span></span>

<span data-ttu-id="23cc5-105">确定是替代文本、线条和填充颜色的公式和值 (还是使用与图表背景) 来替代这些属性的组合。</span><span class="sxs-lookup"><span data-stu-id="23cc5-105">Determines whether to override the formulas and values of text, line, and fill color (or a combination of those properties) by using colors that contrast with the diagram background.</span></span> <span data-ttu-id="23cc5-106">值是 0、1、2、4 和 8 的位 OR。</span><span class="sxs-lookup"><span data-stu-id="23cc5-106">Value is a bitwise OR of 0, 1, 2, 4, and 8.</span></span>
  
|<span data-ttu-id="23cc5-107">**值**</span><span class="sxs-lookup"><span data-stu-id="23cc5-107">**Value**</span></span>|<span data-ttu-id="23cc5-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="23cc5-108">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="23cc5-109">0</span><span class="sxs-lookup"><span data-stu-id="23cc5-109">0</span></span>  <br/> |<span data-ttu-id="23cc5-110">不要更改形状的文本、线条或填充颜色 (或这些属性的任意组合) 主题的给定背景色保持可见。</span><span class="sxs-lookup"><span data-stu-id="23cc5-110">Do not alter a shape's text, line, or fill color (or any combination of those properties) to remain visible against a theme's given background color.</span></span>  <br/> |
|<span data-ttu-id="23cc5-111">1</span><span class="sxs-lookup"><span data-stu-id="23cc5-111">1</span></span>  <br/> |<span data-ttu-id="23cc5-112">不要更改形状的文本、线条或填充颜色 (或这些属性的任意组合) 主题的给定背景色保持可见。</span><span class="sxs-lookup"><span data-stu-id="23cc5-112">Do not alter a shape's text, line, or fill color (or any combination of those properties) to remain visible against a theme's given background color.</span></span>  <br/> |
|<span data-ttu-id="23cc5-113">2</span><span class="sxs-lookup"><span data-stu-id="23cc5-113">2</span></span>  <br/> |<span data-ttu-id="23cc5-114">如有必要，请更改形状的文本颜色，以根据主题的给定背景色保持可见。</span><span class="sxs-lookup"><span data-stu-id="23cc5-114">Alter a shape's text color, if necessary, to remain visible against a theme's given background color.</span></span>  <br/> |
|<span data-ttu-id="23cc5-115">4 </span><span class="sxs-lookup"><span data-stu-id="23cc5-115">4</span></span>  <br/> |<span data-ttu-id="23cc5-116">如有必要，请更改形状的线条颜色，以便对主题的给定背景色保持可见。</span><span class="sxs-lookup"><span data-stu-id="23cc5-116">Alter a shape's line color, if necessary, to remain visible against a theme's given background color.</span></span>  <br/> |
|<span data-ttu-id="23cc5-117">8 </span><span class="sxs-lookup"><span data-stu-id="23cc5-117">8</span></span>  <br/> |<span data-ttu-id="23cc5-118">如有必要，请更改形状的填充颜色，以便根据主题的给定背景色保持可见。</span><span class="sxs-lookup"><span data-stu-id="23cc5-118">Alter a shape's fill color, if necessary, to remain visible against a theme's given background color.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="23cc5-119">备注</span><span class="sxs-lookup"><span data-stu-id="23cc5-119">Remarks</span></span>

<span data-ttu-id="23cc5-120">使用 QuickStyleVariation 单元格可保证文本或线条在任何可见形状几何图形 (例如，文本框位于形状底部下面的形状（如网络图) 中）的可见性。</span><span class="sxs-lookup"><span data-stu-id="23cc5-120">Use the QuickStyleVariation cell to guarantee visibility in either text or lines when they are outside any visible shape geometry (for example, in a shape whose textbox is below the bottom of the shape, such as those in Network Diagrams).</span></span> <span data-ttu-id="23cc5-121">单元格的默认值为 0，表示其行为处于非活动状态。</span><span class="sxs-lookup"><span data-stu-id="23cc5-121">The cell's default value is 0, which means that its behavior is inactive.</span></span> <span data-ttu-id="23cc5-122">任何其他值将触发单元格的行为。</span><span class="sxs-lookup"><span data-stu-id="23cc5-122">Any other value triggers the cell's behavior.</span></span>
  
<span data-ttu-id="23cc5-123">QuickStyleVariation 值替代 THEMEVAL 函数生成的值，该值位于 Color (Character Section) 、FillForegnd 或 LineColor 单元格 (中，或者由 THEMEVAL ("CharacterColor") 、THEMEVAL ("FillColor") 和 THEMEVAL ("LineColor") ) 直接引用生成的值。</span><span class="sxs-lookup"><span data-stu-id="23cc5-123">The QuickStyleVariation value overrides the value produced by the THEMEVAL function when it resides in the Color (Character Section), FillForegnd, or LineColor cells (or produced by direct references to these three properties by means of THEMEVAL("CharacterColor"), THEMEVAL("FillColor"), and THEMEVAL("LineColor")).</span></span>
  
<span data-ttu-id="23cc5-124">若要从另一个公式、通过获取 **Cell** 元素 **的 N** 属性值或使用 CellsU 属性从某个程序按名称获取对 **QuickStyleVariation** 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="23cc5-124">To get a reference to the **QuickStyleVariation** cell by name from another formula, by getting the value of the **N** attribute of a **Cell** element, or from a program by using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="23cc5-125">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="23cc5-125">Cell name:</span></span>  <br/> |<span data-ttu-id="23cc5-126">QuickStyleVariation</span><span class="sxs-lookup"><span data-stu-id="23cc5-126">QuickStyleVariation</span></span>  <br/> |
   
<span data-ttu-id="23cc5-127">若要从程序按索引获取对 **QuickStyleVariation** 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="23cc5-127">To get a reference to the **QuickStyleVariation** cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="23cc5-128">内容索引：</span><span class="sxs-lookup"><span data-stu-id="23cc5-128">Section index:</span></span>  <br/> |<span data-ttu-id="23cc5-129">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="23cc5-129">**visSectionObject**</span></span> <br/> |
|<span data-ttu-id="23cc5-130">行索引：</span><span class="sxs-lookup"><span data-stu-id="23cc5-130">Row index:</span></span>  <br/> |<span data-ttu-id="23cc5-131">**visRowQuickStyleProperties**</span><span class="sxs-lookup"><span data-stu-id="23cc5-131">**visRowQuickStyleProperties**</span></span> <br/> |
|<span data-ttu-id="23cc5-132">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="23cc5-132">Cell index:</span></span>  <br/> |<span data-ttu-id="23cc5-133">**visQuickStyleVariation**</span><span class="sxs-lookup"><span data-stu-id="23cc5-133">**visQuickStyleVariation**</span></span> <br/> |
   

