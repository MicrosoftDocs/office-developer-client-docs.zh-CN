---
title: QuickStyleVariation 单元格（“Quick Style”部分）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: e3b58a19-9f1a-4f2b-9fe2-45cbb7ec6898
description: 确定是否覆盖的公式和的文本、 行和填充颜色 （或这些属性的组合） 通过使用颜色的值与图背景的对比度。 值为 0、 1、 2、 4、 8 的按位 OR。
ms.openlocfilehash: fe6462798b61a0713f98196974876144cf4606e7
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781009"
---
# <a name="quickstylevariation-cell-quick-style-section"></a><span data-ttu-id="c10ba-104">QuickStyleVariation 单元格（“Quick Style”部分）</span><span class="sxs-lookup"><span data-stu-id="c10ba-104">QuickStyleVariation Cell (Quick Style Section)</span></span>

<span data-ttu-id="c10ba-105">确定是否覆盖的公式和的文本、 行和填充颜色 （或这些属性的组合） 通过使用颜色的值与图背景的对比度。</span><span class="sxs-lookup"><span data-stu-id="c10ba-105">Determines whether to override the formulas and values of text, line, and fill color (or a combination of those properties) by using colors that contrast with the diagram background.</span></span> <span data-ttu-id="c10ba-106">值为 0、 1、 2、 4、 8 的按位 OR。</span><span class="sxs-lookup"><span data-stu-id="c10ba-106">Value is a bitwise OR of 0, 1, 2, 4, and 8.</span></span>
  
|<span data-ttu-id="c10ba-107">**值**</span><span class="sxs-lookup"><span data-stu-id="c10ba-107">**Value**</span></span>|<span data-ttu-id="c10ba-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="c10ba-108">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c10ba-109">0</span><span class="sxs-lookup"><span data-stu-id="c10ba-109">0</span></span>  <br/> |<span data-ttu-id="c10ba-110">不要更改形状的文本、 线条或填充颜色 （或这些属性的任意组合） 保持可见针对主题的给定的背景色。</span><span class="sxs-lookup"><span data-stu-id="c10ba-110">Do not alter a shape's text, line, or fill color (or any combination of those properties) to remain visible against a theme's given background color.</span></span>  <br/> |
|<span data-ttu-id="c10ba-111">1</span><span class="sxs-lookup"><span data-stu-id="c10ba-111">1</span></span>  <br/> |<span data-ttu-id="c10ba-112">不要更改形状的文本、 线条或填充颜色 （或这些属性的任意组合） 保持可见针对主题的给定的背景色。</span><span class="sxs-lookup"><span data-stu-id="c10ba-112">Do not alter a shape's text, line, or fill color (or any combination of those properties) to remain visible against a theme's given background color.</span></span>  <br/> |
|<span data-ttu-id="c10ba-113">2</span><span class="sxs-lookup"><span data-stu-id="c10ba-113">2</span></span>  <br/> |<span data-ttu-id="c10ba-114">如有必要，仍可见主题的针对给定的背景颜色更改形状的文本颜色。</span><span class="sxs-lookup"><span data-stu-id="c10ba-114">Alter a shape's text color, if necessary, to remain visible against a theme's given background color.</span></span>  <br/> |
|<span data-ttu-id="c10ba-115">4</span><span class="sxs-lookup"><span data-stu-id="c10ba-115">4</span></span>  <br/> |<span data-ttu-id="c10ba-116">如有必要，仍可见主题的针对给定的背景颜色更改形状的线条颜色。</span><span class="sxs-lookup"><span data-stu-id="c10ba-116">Alter a shape's line color, if necessary, to remain visible against a theme's given background color.</span></span>  <br/> |
|<span data-ttu-id="c10ba-117">8</span><span class="sxs-lookup"><span data-stu-id="c10ba-117">8</span></span>  <br/> |<span data-ttu-id="c10ba-118">如有必要，仍可见主题的针对给定的背景颜色更改形状的填充颜色。</span><span class="sxs-lookup"><span data-stu-id="c10ba-118">Alter a shape's fill color, if necessary, to remain visible against a theme's given background color.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="c10ba-119">说明</span><span class="sxs-lookup"><span data-stu-id="c10ba-119">Remarks</span></span>

<span data-ttu-id="c10ba-120">使用 QuickStyleVariation 单元格时 （例如，在其 textbox 是该形状，例如网络图表中的底形状） 的任何可见的形状几何图形外部保证文本或行中的可见性。</span><span class="sxs-lookup"><span data-stu-id="c10ba-120">Use the QuickStyleVariation cell to guarantee visibility in either text or lines when they are outside any visible shape geometry (for example, in a shape whose textbox is below the bottom of the shape, such as those in Network Diagrams).</span></span> <span data-ttu-id="c10ba-121">单元格的默认值为 0，表示其行为处于非活动状态。</span><span class="sxs-lookup"><span data-stu-id="c10ba-121">The cell's default value is 0, which means that its behavior is inactive.</span></span> <span data-ttu-id="c10ba-122">任何其他值触发单元格的行为。</span><span class="sxs-lookup"><span data-stu-id="c10ba-122">Any other value triggers the cell's behavior.</span></span>
  
<span data-ttu-id="c10ba-123">QuickStyleVariation 值将覆盖它驻留在颜色 （Character 内容）、 FillForegnd 或 LineColor 单元格时产生的 THEMEVAL 函数的值 (或通过 THEMEVAL 产生直接引用这三个属性 ("CharacterColor")，THEMEVAL("FillColor") 和 THEMEVAL("LineColor"))。</span><span class="sxs-lookup"><span data-stu-id="c10ba-123">The QuickStyleVariation value overrides the value produced by the THEMEVAL function when it resides in the Color (Character Section), FillForegnd, or LineColor cells (or produced by direct references to these three properties by means of THEMEVAL("CharacterColor"), THEMEVAL("FillColor"), and THEMEVAL("LineColor")).</span></span>
  
<span data-ttu-id="c10ba-124">要获取的**单元格**元素中，或从某个程序**N**属性的值使用**CellsU**属性获取按名称从另一个公式， **QuickStyleVariation**单元格的引用，使用：</span><span class="sxs-lookup"><span data-stu-id="c10ba-124">To get a reference to the **QuickStyleVariation** cell by name from another formula, by getting the value of the **N** attribute of a **Cell** element, or from a program by using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="c10ba-125">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="c10ba-125">Cell name:</span></span>  <br/> |<span data-ttu-id="c10ba-126">QuickStyleVariation</span><span class="sxs-lookup"><span data-stu-id="c10ba-126">QuickStyleVariation</span></span>  <br/> |
   
<span data-ttu-id="c10ba-127">若要从某个程序按索引获取对**QuickStyleVariation**单元格的引用，请使用带下列参数的**CellsSRC**属性：</span><span class="sxs-lookup"><span data-stu-id="c10ba-127">To get a reference to the **QuickStyleVariation** cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="c10ba-128">内容索引：</span><span class="sxs-lookup"><span data-stu-id="c10ba-128">Section index:</span></span>  <br/> |<span data-ttu-id="c10ba-129">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="c10ba-129">**visSectionObject**</span></span> <br/> |
|<span data-ttu-id="c10ba-130">行索引：</span><span class="sxs-lookup"><span data-stu-id="c10ba-130">Row index:</span></span>  <br/> |<span data-ttu-id="c10ba-131">**visRowQuickStyleProperties**</span><span class="sxs-lookup"><span data-stu-id="c10ba-131">**visRowQuickStyleProperties**</span></span> <br/> |
|<span data-ttu-id="c10ba-132">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="c10ba-132">Cell index:</span></span>  <br/> |<span data-ttu-id="c10ba-133">**visQuickStyleVariation**</span><span class="sxs-lookup"><span data-stu-id="c10ba-133">**visQuickStyleVariation**</span></span> <br/> |
   

