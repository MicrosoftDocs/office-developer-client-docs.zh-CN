---
title: QuickStyleVariation 单元格 ("快速样式" 部分)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: e3b58a19-9f1a-4f2b-9fe2-45cbb7ec6898
description: 确定是否使用与图表背景对比的颜色来替代文本、线条和填充颜色的公式和值 (或这些属性的组合)。 值为0、1、2、4和8的按位 "或"。
ms.openlocfilehash: 736e2287c00c24774ef8b677613235d642697f4b
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33433792"
---
# <a name="quickstylevariation-cell-quick-style-section"></a><span data-ttu-id="75332-104">QuickStyleVariation 单元格 ("快速样式" 部分)</span><span class="sxs-lookup"><span data-stu-id="75332-104">QuickStyleVariation Cell (Quick Style Section)</span></span>

<span data-ttu-id="75332-105">确定是否使用与图表背景对比的颜色来替代文本、线条和填充颜色的公式和值 (或这些属性的组合)。</span><span class="sxs-lookup"><span data-stu-id="75332-105">Determines whether to override the formulas and values of text, line, and fill color (or a combination of those properties) by using colors that contrast with the diagram background.</span></span> <span data-ttu-id="75332-106">值为0、1、2、4和8的按位 "或"。</span><span class="sxs-lookup"><span data-stu-id="75332-106">Value is a bitwise OR of 0, 1, 2, 4, and 8.</span></span>
  
|<span data-ttu-id="75332-107">**值**</span><span class="sxs-lookup"><span data-stu-id="75332-107">**Value**</span></span>|<span data-ttu-id="75332-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="75332-108">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="75332-109">0</span><span class="sxs-lookup"><span data-stu-id="75332-109">0</span></span>  <br/> |<span data-ttu-id="75332-110">请勿改变形状的文本、线条或填充颜色 (或这些属性的任何组合), 使其对给定的背景色保持可见。</span><span class="sxs-lookup"><span data-stu-id="75332-110">Do not alter a shape's text, line, or fill color (or any combination of those properties) to remain visible against a theme's given background color.</span></span>  <br/> |
|<span data-ttu-id="75332-111">1</span><span class="sxs-lookup"><span data-stu-id="75332-111">1</span></span>  <br/> |<span data-ttu-id="75332-112">请勿改变形状的文本、线条或填充颜色 (或这些属性的任何组合), 使其对给定的背景色保持可见。</span><span class="sxs-lookup"><span data-stu-id="75332-112">Do not alter a shape's text, line, or fill color (or any combination of those properties) to remain visible against a theme's given background color.</span></span>  <br/> |
|<span data-ttu-id="75332-113">双面</span><span class="sxs-lookup"><span data-stu-id="75332-113">2</span></span>  <br/> |<span data-ttu-id="75332-114">如有必要, 请更改形状的文本颜色, 使其对特定主题的背景色保持可见。</span><span class="sxs-lookup"><span data-stu-id="75332-114">Alter a shape's text color, if necessary, to remain visible against a theme's given background color.</span></span>  <br/> |
|<span data-ttu-id="75332-115">4</span><span class="sxs-lookup"><span data-stu-id="75332-115">4</span></span>  <br/> |<span data-ttu-id="75332-116">如有必要, 请改变形状的线条颜色, 以使其对特定主题的背景色保持可见。</span><span class="sxs-lookup"><span data-stu-id="75332-116">Alter a shape's line color, if necessary, to remain visible against a theme's given background color.</span></span>  <br/> |
|<span data-ttu-id="75332-117">utf-8</span><span class="sxs-lookup"><span data-stu-id="75332-117">8</span></span>  <br/> |<span data-ttu-id="75332-118">如有必要, 请更改形状的填充颜色, 以使其对特定主题的背景色保持可见。</span><span class="sxs-lookup"><span data-stu-id="75332-118">Alter a shape's fill color, if necessary, to remain visible against a theme's given background color.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="75332-119">说明</span><span class="sxs-lookup"><span data-stu-id="75332-119">Remarks</span></span>

<span data-ttu-id="75332-120">当文本或行位于任何可见的形状几何图形之外时 (例如, 在其 textbox 位于形状底部下方的形状中, 例如网络图中的形状), 使用 QuickStyleVariation 单元格保证可见性。</span><span class="sxs-lookup"><span data-stu-id="75332-120">Use the QuickStyleVariation cell to guarantee visibility in either text or lines when they are outside any visible shape geometry (for example, in a shape whose textbox is below the bottom of the shape, such as those in Network Diagrams).</span></span> <span data-ttu-id="75332-121">单元格的默认值为 0, 表示其行为处于非活动状态。</span><span class="sxs-lookup"><span data-stu-id="75332-121">The cell's default value is 0, which means that its behavior is inactive.</span></span> <span data-ttu-id="75332-122">任何其他值将触发单元格的行为。</span><span class="sxs-lookup"><span data-stu-id="75332-122">Any other value triggers the cell's behavior.</span></span>
  
<span data-ttu-id="75332-123">QuickStyleVariation 值将覆盖 THEMEVAL 函数驻留在 Color (Character)、FillForegnd 或 LineColor 单元格 (或通过直接引用通过 THEMEVAL 的这三个属性生成) 生成的值 ("CharacterColor ")、THEMEVAL (" FillColor ") 和 THEMEVAL (" LineColor "))。</span><span class="sxs-lookup"><span data-stu-id="75332-123">The QuickStyleVariation value overrides the value produced by the THEMEVAL function when it resides in the Color (Character Section), FillForegnd, or LineColor cells (or produced by direct references to these three properties by means of THEMEVAL("CharacterColor"), THEMEVAL("FillColor"), and THEMEVAL("LineColor")).</span></span>
  
<span data-ttu-id="75332-124">若要从另一个公式按名称获取对**QuickStyleVariation**单元格的引用, 通过获取**cell**元素的**N**属性的值, 或使用**CellsU**属性从某个程序获取对该单元格的引用, 请使用:</span><span class="sxs-lookup"><span data-stu-id="75332-124">To get a reference to the **QuickStyleVariation** cell by name from another formula, by getting the value of the **N** attribute of a **Cell** element, or from a program by using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="75332-125">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="75332-125">Cell name:</span></span>  <br/> |<span data-ttu-id="75332-126">QuickStyleVariation</span><span class="sxs-lookup"><span data-stu-id="75332-126">QuickStyleVariation</span></span>  <br/> |
   
<span data-ttu-id="75332-127">若要从某个程序按索引获取对**QuickStyleVariation**单元格的引用, 请使用带下列参数的**CellsSRC**属性:</span><span class="sxs-lookup"><span data-stu-id="75332-127">To get a reference to the **QuickStyleVariation** cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="75332-128">内容索引：</span><span class="sxs-lookup"><span data-stu-id="75332-128">Section index:</span></span>  <br/> |<span data-ttu-id="75332-129">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="75332-129">**visSectionObject**</span></span> <br/> |
|<span data-ttu-id="75332-130">行索引：</span><span class="sxs-lookup"><span data-stu-id="75332-130">Row index:</span></span>  <br/> |<span data-ttu-id="75332-131">**visRowQuickStyleProperties**</span><span class="sxs-lookup"><span data-stu-id="75332-131">**visRowQuickStyleProperties**</span></span> <br/> |
|<span data-ttu-id="75332-132">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="75332-132">Cell index:</span></span>  <br/> |<span data-ttu-id="75332-133">**visQuickStyleVariation**</span><span class="sxs-lookup"><span data-stu-id="75332-133">**visQuickStyleVariation**</span></span> <br/> |
   

