---
title: 处理多维数据
TOCTitle: Working with multidimensional data
ms:assetid: a0c9ac73-04da-cfdd-8787-15c8a53ff819
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249740(v=office.15)
ms:contentKeyID: 48546717
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 67b22219fdbbec8bf518b7be0fabd9a6adfbcf7f
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32306039"
---
# <a name="working-with-multidimensional-data"></a><span data-ttu-id="54480-102">处理多维数据</span><span class="sxs-lookup"><span data-stu-id="54480-102">Working with multidimensional data</span></span>

<span data-ttu-id="54480-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="54480-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="54480-p101">*单元格集*是对多维数据进行查询的结果。它由一个轴集合组成，该集合中包含轴的通常不超过四个（通常是两到三个）。*轴*是来自一个或多个维的成员的集合，用于定位或筛选多维数据集中的特定值。</span><span class="sxs-lookup"><span data-stu-id="54480-p101">A *cellset* is the result of a query on multidimensional data. It consists of a collection of axes, usually no more than four axes and typically only two or three. An *axis* is a collection of members from one or more dimensions, which is used to locate or filter specific values in a cube.</span></span>

<span data-ttu-id="54480-p102">*位置*是轴上的点。对于包含一个维的轴，这些位置是维成员的子集。如果一个轴包含多个维，则每个位置是一个具有 *n* 部分的复合实体（此处的 *n* 是沿该轴方向展开的维的数目）。位置的每个部分都是来自某个构成维的成员。</span><span class="sxs-lookup"><span data-stu-id="54480-p102">A *position* is a point along an axis. For an axis consisting of a single dimension, these positions are a subset of the dimension members. If an axis consists of more than one dimension, then each position is a compound entity, which has *n* parts where *n* is the number of dimensions oriented along that axis. Each part of the position is a member from one constituent dimension.</span></span>

<span data-ttu-id="54480-p103">例如，如果来自包含销售数据的多维数据集的 Geography 和 Product 维沿单元格集的 X 轴方向展开，则该轴上的位置可能包含成员“USA”和“Computers”。在此示例中，确定 X 轴上的位置要求来自每个维的成员沿该轴方向展开。</span><span class="sxs-lookup"><span data-stu-id="54480-p103">For example, if the Geography and Product dimensions from a cube containing sales data are oriented along the x-axis of a cellset, a position along this axis may contain the members "USA" and "Computers." In this example, determining a position along the x-axis requires that members from each dimension are oriented along the axis.</span></span>

<span data-ttu-id="54480-p104">*单元格*是位于坐标轴交点处的对象。每个单元格具有多条与之关联的信息（包括数据自身）、一个格式字符串（单元格数据的可显示形式）和单元格序号值。（每个单元格是单元格集中的唯一序号值。单元格集中第一个单元格的序号值为零，而包含八列的单元格集中第二行最左侧的单元格应具有序号值八。）</span><span class="sxs-lookup"><span data-stu-id="54480-p104">A *cell* is an object positioned at the intersection of axis coordinates. Each cell has multiple pieces of information associated with it, including the data itself, a formatted string (the displayable form of cell data), and the cell ordinal value. (Each cell is a unique ordinal value in the cellset. The ordinal value of the first cell in the cellset is zero, while the leftmost cell in the second row of a cellset with eight columns would have an ordinal value of eight.)</span></span>

<span data-ttu-id="54480-117">例如，某个多维数据集具有以下六个维（注意，此多维数据集架构与[多维架构和数据概述](overview-of-multidimensional-schemas-and-data.md)中给出的示例稍有不同）：</span><span class="sxs-lookup"><span data-stu-id="54480-117">For example, a cube has the following six dimensions (note that this cube schema differs slightly from the example given in [Overview of Multidimensional Schemas and Data](overview-of-multidimensional-schemas-and-data.md)):</span></span>

- <span data-ttu-id="54480-118">Salesperson</span><span class="sxs-lookup"><span data-stu-id="54480-118">Salesperson</span></span>
- <span data-ttu-id="54480-119">Geography（自然层次结构）- Continents、Countries、States 等等</span><span class="sxs-lookup"><span data-stu-id="54480-119">Geography (natural hierarchy) — Continents, Countries, States, and so on</span></span>
- <span data-ttu-id="54480-120">Quarters - Quarters、Months、Days</span><span class="sxs-lookup"><span data-stu-id="54480-120">Quarters — Quarters, Months, Days</span></span>
- <span data-ttu-id="54480-121">Years</span><span class="sxs-lookup"><span data-stu-id="54480-121">Years</span></span>
- <span data-ttu-id="54480-122">Measures - Sales、PercentChange、BudgetedSales</span><span class="sxs-lookup"><span data-stu-id="54480-122">Measures — Sales, PercentChange, BudgetedSales</span></span>
- <span data-ttu-id="54480-123">Products</span><span class="sxs-lookup"><span data-stu-id="54480-123">Products</span></span>

> [!NOTE]
> <span data-ttu-id="54480-124">该示例中的单元格值可以视为轴位置序号的有序对，其中第一个数字代表 X 轴位置，第二个数字代表 Y 轴位置。</span><span class="sxs-lookup"><span data-stu-id="54480-124">The cell values in the example can be viewed as ordered pairs of axis position ordinals where the first digit represents the x-axis position and the second digit the y-axis position.</span></span>

<span data-ttu-id="54480-125">此单元格集的特征如下所示：</span><span class="sxs-lookup"><span data-stu-id="54480-125">The characteristics of this cellset are as follows:</span></span>

- <span data-ttu-id="54480-126">轴维：Quarters、Salesperson、Geography</span><span class="sxs-lookup"><span data-stu-id="54480-126">Axis dimensions: Quarters, Salesperson, Geography</span></span>

- <span data-ttu-id="54480-127">筛选器维：Measures、Years、Products</span><span class="sxs-lookup"><span data-stu-id="54480-127">Filter dimensions: Measures, Years, Products</span></span>

- <span data-ttu-id="54480-128">两个轴：COLUMN（X 或轴 0）和 ROW（Y 或轴 1）</span><span class="sxs-lookup"><span data-stu-id="54480-128">Two axes: COLUMN (x, or Axis 0) and ROW (y, or Axis 1)</span></span>

- <span data-ttu-id="54480-129">X 轴：两个嵌套维，即 Salesperson 和 Geography</span><span class="sxs-lookup"><span data-stu-id="54480-129">x-axis: two nested dimensions, Salesperson and Geography</span></span>

- <span data-ttu-id="54480-130">Y 轴：Quarters 维</span><span class="sxs-lookup"><span data-stu-id="54480-130">y-axis: Quarters dimension</span></span>

<span data-ttu-id="54480-p105">X 轴具有两个嵌套维：Salesperson 和 Geography。从 Geography 维中选择了四个成员：Seattle、Boston、USA-South 和 Japan。从 Salesperson 维中选择了两个成员：Valentine 和 Nash。这就在此轴上共产生了八个位置 (8 = 4\*2)。</span><span class="sxs-lookup"><span data-stu-id="54480-p105">The x-axis has two nested dimensions: Salesperson and Geography. From Geography, four members are selected: Seattle, Boston, USA-South, and Japan. Two members are selected from Salesperson: Valentine and Nash. This yields a total of eight positions on this axis (8 = 4\*2).</span></span>

<span data-ttu-id="54480-135">每个坐标都表示为一个具有两个成员的位置 - 一个成员来自 Salesperson 维，另一个成员来自 Geography 维：</span><span class="sxs-lookup"><span data-stu-id="54480-135">Each coordinate is represented as a position with two members — one from the Salesperson dimension and another from the Geography dimension:</span></span>

```vb 
 
(Valentine, Seattle), (Valentine, Boston), (Valentine, USA_North), 
(Valentine, Japan), (Nash, Seattle), (Nash, Boston), (Nash, USA_North), 
(Nash, Japan) 
```

<span data-ttu-id="54480-136">Y 轴仅具有一个维，其中包含以下八个位置：</span><span class="sxs-lookup"><span data-stu-id="54480-136">The y-axis has only one dimension, containing the following eight positions:</span></span>

```vb 
 
Jan, Feb, Mar, Qtr2, Qtr3, Oct, Nov, Dec 
```

<span data-ttu-id="54480-137">单元格集、单元格、轴和位置在 ADO MD 中都由相应的对象表示：[Cellset](cellset-object-ado-md.md)、[Cell](cell-object-ado-md.md)、[Axis](axis-object-ado-md.md) 和 [Position](position-object-ado-md.md)。</span><span class="sxs-lookup"><span data-stu-id="54480-137">Cellsets, cells, axes, and positions are all represented in ADO MD by corresponding objects: [Cellset](cellset-object-ado-md.md), [Cell](cell-object-ado-md.md), [Axis](axis-object-ado-md.md), and [Position](position-object-ado-md.md).</span></span>

