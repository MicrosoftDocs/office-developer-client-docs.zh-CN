---
title: 第 9 章：数据成型
TOCTitle: 'Chapter 9: Data Shaping'
ms:assetid: f66a319f-1b3d-c4a3-50b3-af1a47540832
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250253(v=office.15)
ms:contentKeyID: 48548739
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 988766f71fd57505693683d54a15b13409ae6960
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25875873"
---
# <a name="chapter-9-data-shaping"></a><span data-ttu-id="428be-102">第 9 章：数据成型</span><span class="sxs-lookup"><span data-stu-id="428be-102">Chapter 9: Data Shaping</span></span>


<span data-ttu-id="428be-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="428be-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="428be-104">*数据定形*提供一种查询数据源，并返回[Recordset](recordset-object-ado.md)表示两个或多个逻辑实体 （层次结构） 之间的父子关系。</span><span class="sxs-lookup"><span data-stu-id="428be-104">*Data shaping* provides a way to query a data source and return a [Recordset](recordset-object-ado.md) that represents a parent-child relationship between two or more logical entities (a hierarchy).</span></span> <span data-ttu-id="428be-105">分层关系的典型示例是客户和订单。</span><span class="sxs-lookup"><span data-stu-id="428be-105">A classic example of a hierarchical relationship is customers and orders.</span></span> <span data-ttu-id="428be-106">对于数据库中的每个顾客来说，可以有零个或更多个订单。</span><span class="sxs-lookup"><span data-stu-id="428be-106">For every customer in a database, there can be zero or more orders.</span></span> <span data-ttu-id="428be-107">常规 SQL 可以使用 JOIN 语法检索数据，但是，对于给定的父子关系，冗余的父数据会在每个返回的记录中重复出现，因此这种方式可能效率低且不实用。</span><span class="sxs-lookup"><span data-stu-id="428be-107">Regular SQL provides a means of retrieving the data using JOIN syntax, but this can be inefficient and unwieldy because redundant parent data is repeated in each record returned for a given parent-child relationship.</span></span> <span data-ttu-id="428be-108">数据定形可以使父 **Recordset** 中的单个父记录与子 **Recordset** 中的多个子记录相关，从而避免了 JOIN 发生冗余。</span><span class="sxs-lookup"><span data-stu-id="428be-108">Data shaping can relate a single parent record in the parent **Recordset** to multiple child records in the child **Recordset**, avoiding the redundancy of a JOIN.</span></span> <span data-ttu-id="428be-109">很多人都会发现父子多 **Recordset** 编程模型比单个 **Recordset** JOIN 模型更简单且更容易使用。</span><span class="sxs-lookup"><span data-stu-id="428be-109">Most people find the parent-child multiple **Recordset** programming model more natural and easier to work with than the single **Recordset** JOIN model.</span></span>

<span data-ttu-id="428be-p102">数据定形语法还提供了其他功能。开发人员可以通过使用 NEW 关键字来描述父和子 **Recordsets** 的字段，即可在没有基础数据源的情况下创建新的 **Recordset** 对象。新的 **Recordset** 对象可以用数据进行填充，并进行永久存储。开发人员还可以对子字段执行各种计算或聚合（如 SUM、AVG 和 MAX）。数据定形还可以通过子 **Recordset** 创建父 **Recordset** ，方法是将子记录集中的记录分组，并对应于子记录集的每个组在父记录集中放置一行。</span><span class="sxs-lookup"><span data-stu-id="428be-p102">The data shaping syntax also provides other capabilities. Developers can create new **Recordset** objects without an underlying data source by using the NEW keyword to describe the fields of the parent and child **Recordsets**. The new **Recordset** object can be populated with data and persistently stored. Developers can also perform various calculations or aggregations (for example, SUM, AVG, and MAX) on child fields. Data shaping can also create a parent **Recordset** from a child **Recordset** by grouping records in the child and placing one row in the parent for each group in the child.</span></span>

<span data-ttu-id="428be-115">有关数据定形的详细信息，请参阅以下主题：</span><span class="sxs-lookup"><span data-stu-id="428be-115">See the following topics to learn more about data shaping:</span></span>

- [<span data-ttu-id="428be-116">数据定形必需的提供程序</span><span class="sxs-lookup"><span data-stu-id="428be-116">Required Providers for Data Shaping</span></span>](required-providers-for-data-shaping.md)

- [<span data-ttu-id="428be-117">Shape Compute 子句</span><span class="sxs-lookup"><span data-stu-id="428be-117">Shape Compute Clause</span></span>](shape-compute-clause.md)

- [<span data-ttu-id="428be-118">构造分层记录集</span><span class="sxs-lookup"><span data-stu-id="428be-118">Fabricating Hierarchical Recordsets</span></span>](fabricating-hierarchical-recordsets.md)

- [<span data-ttu-id="428be-119">访问分层记录集中的行</span><span class="sxs-lookup"><span data-stu-id="428be-119">Accessing Rows in a Hierarchical Recordset</span></span>](accessing-rows-in-a-hierarchical-recordset.md)

- [<span data-ttu-id="428be-120">正式 Shape 语法</span><span class="sxs-lookup"><span data-stu-id="428be-120">Formal Shape Grammar</span></span>](formal-shape-grammar.md)

- [<span data-ttu-id="428be-121">Visual Basic for Applications 函数</span><span class="sxs-lookup"><span data-stu-id="428be-121">Visual Basic for Applications functions</span></span>](visual-basic-for-applications-functions.md)

- [<span data-ttu-id="428be-122">Shape Append Clause (ADO)</span><span class="sxs-lookup"><span data-stu-id="428be-122">Shape Append Clause (ADO)</span></span>](shape-append-clause.md)

- [<span data-ttu-id="428be-123">数据定形 (ADO)</span><span class="sxs-lookup"><span data-stu-id="428be-123">Data Shaping (ADO)</span></span>](data-shaping.md)

- [<span data-ttu-id="428be-124">Shape Commands in General (ADO)</span><span class="sxs-lookup"><span data-stu-id="428be-124">Shape Commands in General (ADO)</span></span>](shape-commands-in-general.md)

