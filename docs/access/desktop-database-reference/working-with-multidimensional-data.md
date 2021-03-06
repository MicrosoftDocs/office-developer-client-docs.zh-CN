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
# <a name="working-with-multidimensional-data"></a>处理多维数据

**适用于**：Access 2013、Office 2013

*单元格集*是对多维数据进行查询的结果。它由一个轴集合组成，该集合中包含轴的通常不超过四个（通常是两到三个）。*轴*是来自一个或多个维的成员的集合，用于定位或筛选多维数据集中的特定值。

*位置*是轴上的点。对于包含一个维的轴，这些位置是维成员的子集。如果一个轴包含多个维，则每个位置是一个具有 *n* 部分的复合实体（此处的 *n* 是沿该轴方向展开的维的数目）。位置的每个部分都是来自某个构成维的成员。

例如，如果来自包含销售数据的多维数据集的 Geography 和 Product 维沿单元格集的 X 轴方向展开，则该轴上的位置可能包含成员“USA”和“Computers”。在此示例中，确定 X 轴上的位置要求来自每个维的成员沿该轴方向展开。

*单元格*是位于坐标轴交点处的对象。每个单元格具有多条与之关联的信息（包括数据自身）、一个格式字符串（单元格数据的可显示形式）和单元格序号值。（每个单元格是单元格集中的唯一序号值。单元格集中第一个单元格的序号值为零，而包含八列的单元格集中第二行最左侧的单元格应具有序号值八。）

例如，某个多维数据集具有以下六个维（注意，此多维数据集架构与[多维架构和数据概述](overview-of-multidimensional-schemas-and-data.md)中给出的示例稍有不同）：

- Salesperson
- Geography（自然层次结构）- Continents、Countries、States 等等
- Quarters - Quarters、Months、Days
- Years
- Measures - Sales、PercentChange、BudgetedSales
- Products

> [!NOTE]
> 该示例中的单元格值可以视为轴位置序号的有序对，其中第一个数字代表 X 轴位置，第二个数字代表 Y 轴位置。

此单元格集的特征如下所示：

- 轴维：Quarters、Salesperson、Geography

- 筛选器维：Measures、Years、Products

- 两个轴：COLUMN（X 或轴 0）和 ROW（Y 或轴 1）

- X 轴：两个嵌套维，即 Salesperson 和 Geography

- Y 轴：Quarters 维

X 轴具有两个嵌套维：Salesperson 和 Geography。从 Geography 维中选择了四个成员：Seattle、Boston、USA-South 和 Japan。从 Salesperson 维中选择了两个成员：Valentine 和 Nash。这就在此轴上共产生了八个位置 (8 = 4\*2)。

每个坐标都表示为一个具有两个成员的位置 - 一个成员来自 Salesperson 维，另一个成员来自 Geography 维：

```vb 
 
(Valentine, Seattle), (Valentine, Boston), (Valentine, USA_North), 
(Valentine, Japan), (Nash, Seattle), (Nash, Boston), (Nash, USA_North), 
(Nash, Japan) 
```

Y 轴仅具有一个维，其中包含以下八个位置：

```vb 
 
Jan, Feb, Mar, Qtr2, Qtr3, Oct, Nov, Dec 
```

单元格集、单元格、轴和位置在 ADO MD 中都由相应的对象表示：[Cellset](cellset-object-ado-md.md)、[Cell](cell-object-ado-md.md)、[Axis](axis-object-ado-md.md) 和 [Position](position-object-ado-md.md)。

