---
title: 数据定形 （访问桌面数据库参考 （英文）
TOCTitle: Data shaping
ms:assetid: 650571cc-6874-2cdb-dd76-0804d1cc4e38
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249390(v=office.15)
ms:contentKeyID: 48545305
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 96a5d7ad82c7cb9182f95b428ff17c9df60c47b3
ms.sourcegitcommit: 558d09fad81f8d80b5ad0edd21934fc09c098f2c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2018
ms.locfileid: "25947096"
---
# <a name="data-shaping"></a><span data-ttu-id="eb196-102">数据定形</span><span class="sxs-lookup"><span data-stu-id="eb196-102">Data shaping</span></span>

<span data-ttu-id="eb196-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="eb196-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="eb196-104">通过数据定形，可以定义定形 **Recordset** 的列、列所代表的实体之间的关系以及在 **Recordset** 中填充数据的方式。</span><span class="sxs-lookup"><span data-stu-id="eb196-104">Data shaping enables you to define the columns of a shaped **Recordset**, the relationships between the entities represented by the columns, and the manner in which the **Recordset** is populated with data.</span></span>

<span data-ttu-id="eb196-105">定形 **Recordset** 的列可能包含来自数据提供程序（如 Microsoft SQL Server）的数据、对其他 **Recordset** 的引用、从 **Recordset** 单行计算派生的值或从针对整个 **Recordset** 列的操作派生的值；这些列也可能是新创建的空列。</span><span class="sxs-lookup"><span data-stu-id="eb196-105">Columns of a shaped **Recordset** may contain data from a data provider such as Microsoft SQL Server, references to another **Recordset**, values derived from a calculation on a single row of a **Recordset**, values derived from an operation over a column of an entire **Recordset**; or they may be a newly fabricated, empty column.</span></span>

<span data-ttu-id="eb196-p101">在检索包含对其他 **Recordset** 的引用的列的值时，ADO 自动返回引用所表示的实际 **Recordset**。包含其他 **Recordset** 的 **Recordset** 称为分层记录集。分层记录集体现了*父子*关系，其中*父*是包含的记录集，而*子*是被包含的记录集。引用 **Recordset** 实际上是引用子记录集的子集，称为*章节*。单个父记录集可以引用多个子 **Recordset**。</span><span class="sxs-lookup"><span data-stu-id="eb196-p101">When you retrieve the value of a column that contains a reference to another **Recordset**, ADO automatically returns the actual **Recordset** represented by the reference. A **Recordset** that contains another **Recordset** is called a hierarchical recordset. Hierarchical recordsets exhibit a *parent-child* relationship, in which the *parent* is the containing recordset and the *child* is the contained recordset. The reference to a **Recordset** is actually a reference to a subset of the child, called a *chapter*. A single parent may reference more than one child **Recordset**.</span></span>

<span data-ttu-id="eb196-p102">通过 Shape 命令语法，可以通过编程方式创建定形 **Recordset** 。随后，可以通过编程方式或适当的可视控件访问 **Recordset** 的组件。Shape 命令的发布类似于其他所有 ADO 命令文本。</span><span class="sxs-lookup"><span data-stu-id="eb196-p102">The shape command syntax enables you to programmatically create a shaped **Recordset**. You can then access the components of the **Recordset** programmatically or through an appropriate visual control. A shape command is issued like any other ADO command text.</span></span>

<span data-ttu-id="eb196-p103">您可以通过两种方式使用 Shape 命令来生成分层 **Recordset** 对象。第一种方式是将子 **Recordset** 追加到父 **Recordset** 。通常，父记录集和子记录集至少共同具有一列：父记录集某行中该列的值与子记录集所有行中该列的值相等。</span><span class="sxs-lookup"><span data-stu-id="eb196-p103">You can make hierarchical **Recordset** objects in two ways with the shape command syntax. The first appends a child **Recordset** to a parent **Recordset**. The parent and child typically have at least one column in common: the value of the column in a row of the parent is the same as the value of the column in all rows of the child.</span></span>

<span data-ttu-id="eb196-p104">第二种方式是从子 **Recordset** 生成父 **Recordset** 。首先对子 **Recordset** 中的记录进行分组（通常使用 BY 子句），然后对于子记录集中生成的每个组，在父 **Recordset** 中添加一行。如果省略 BY 子句，则整个子 **Recordset** 为单个组，父 **Recordset** 将只包含一行。这可用于对整个子 **Recordset** 计算"总计"。</span><span class="sxs-lookup"><span data-stu-id="eb196-p104">The second way generates a parent **Recordset** from a child **Recordset**. The records in the child **Recordset** are grouped, typically using the BY clause, and one row is added to the parent **Recordset** for each resulting group in the child. If the BY clause is omitted, the child **Recordset** will form a single group and the parent **Recordset** will contain exactly one row. This is useful for computing "grand total" aggregates over the entire child **Recordset**.</span></span>

<span data-ttu-id="eb196-p105">无论父 **Recordset** 采用何种方式构成，都将包含"章节"列，用于将其与子 **Recordset** 关联。如果愿意，父 **Recordset** 中的列还可以包含对子记录集行进行运算的聚合函数（如 SUM、MIN、MAX 等）。父子 **Recordset** 中的列都可以包含针对 **Recordset** 中行的表达式，也可以是一开始为空的新列。</span><span class="sxs-lookup"><span data-stu-id="eb196-p105">Regardless of which way the parent **Recordset** is formed, it will contain a chapter column that is used to relate it to a child **Recordset**. If you wish, the parent **Recordset** may also have columns that contain aggregates (SUM, MIN, MAX, and so on) over the child rows. Both the parent and the child **Recordset** may have columns which contain an expression on the row in the **Recordset**, as well as columns which are new and initially empty.</span></span>

<span data-ttu-id="eb196-124">分层 **Recordset** 对象可以嵌套至任何深度（即，创建子 **Recordset** 对象的子 **Recordset** 对象，依此类推）。</span><span class="sxs-lookup"><span data-stu-id="eb196-124">You can nest hierarchical **Recordset** objects to any depth (that is, create child **Recordset** objects of child **Recordset** objects, and so on).</span></span>

<span data-ttu-id="eb196-125">可以通过编程方式或适当的可视控件访问定形 **Recordset** 的 **Recordset** 组件。</span><span class="sxs-lookup"><span data-stu-id="eb196-125">You can access the **Recordset** components of the shaped **Recordset** programmatically or through an appropriate visual control.</span></span>

<span data-ttu-id="eb196-126">有关 Shape 命令及生成的层次结构示例，请参阅"使用 Data Shaping Service for OLE DB：深入了解"。</span><span class="sxs-lookup"><span data-stu-id="eb196-126">For examples of shape commands and their resulting hierarchies, see Using the Data Shaping Service for OLE DB: A Closer Look.</span></span>

<span data-ttu-id="eb196-127">本节包括下列主题：</span><span class="sxs-lookup"><span data-stu-id="eb196-127">This section includes the following topics:</span></span>

- [<span data-ttu-id="eb196-128">重新构形</span><span class="sxs-lookup"><span data-stu-id="eb196-128">Reshaping</span></span>](reshaping.md)
- [<span data-ttu-id="eb196-129">孙聚合</span><span class="sxs-lookup"><span data-stu-id="eb196-129">Grandchild aggregates</span></span>](grandchild-aggregates.md)
- [<span data-ttu-id="eb196-130">参数化的命令与干扰 COMPUTE 命令</span><span class="sxs-lookup"><span data-stu-id="eb196-130">Parameterized commands with intervening COMPUTE commands</span></span>](parameterized-commands-with-intervening-compute-commands.md)
- [<span data-ttu-id="eb196-131">持久化分层记录集</span><span class="sxs-lookup"><span data-stu-id="eb196-131">Persisting hierarchical Recordsets</span></span>](persisting-hierarchical-recordsets.md)