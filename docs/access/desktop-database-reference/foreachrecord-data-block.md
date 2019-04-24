---
title: ForEachRecord 数据块
TOCTitle: ForEachRecord data block
ms:assetid: be369196-230e-1f92-e36b-667048eef2be
ms:mtpsurl: https://msdn.microsoft.com/library/Ff822743(v=office.15)
ms:contentKeyID: 48547455
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 84ab685b946e390645027790e5b1402561527ab6
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32292326"
---
# <a name="foreachrecord-data-block"></a><span data-ttu-id="a0765-102">ForEachRecord 数据块</span><span class="sxs-lookup"><span data-stu-id="a0765-102">ForEachRecord data block</span></span>

<span data-ttu-id="a0765-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="a0765-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="a0765-104">**ForEachRecord**数据块为域中的每条记录重复一组语句。</span><span class="sxs-lookup"><span data-stu-id="a0765-104">A **ForEachRecord** data block repeats a set of statements for each record in a domain.</span></span>

> [!NOTE]
> <span data-ttu-id="a0765-105">**ForEachRecord** 数据块仅适用于数据宏。</span><span class="sxs-lookup"><span data-stu-id="a0765-105">The **ForEachRecord** data block is available only in Data Macros.</span></span>

## <a name="setting"></a><span data-ttu-id="a0765-106">Setting</span><span class="sxs-lookup"><span data-stu-id="a0765-106">Setting</span></span>

<span data-ttu-id="a0765-107">**ForEachRecord** 操作具有以下参数。</span><span class="sxs-lookup"><span data-stu-id="a0765-107">The **ForEachRecord** action has the following arguments.</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="a0765-108">参数</span><span class="sxs-lookup"><span data-stu-id="a0765-108">Argument</span></span></p></th>
<th><p><span data-ttu-id="a0765-109">必需</span><span class="sxs-lookup"><span data-stu-id="a0765-109">Required</span></span></p></th>
<th><p><span data-ttu-id="a0765-110">说明</span><span class="sxs-lookup"><span data-stu-id="a0765-110">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a0765-111"><strong>实时</strong></span><span class="sxs-lookup"><span data-stu-id="a0765-111"><strong>In</strong></span></span></p></td>
<td><p><span data-ttu-id="a0765-112">是</span><span class="sxs-lookup"><span data-stu-id="a0765-112">Yes</span></span></p></td>
<td><p><span data-ttu-id="a0765-113">一个用于标识要对其执行操作的记录域的字符串。</span><span class="sxs-lookup"><span data-stu-id="a0765-113">A string that identifies the domain of records to operate on.</span></span> <span data-ttu-id="a0765-114"><em>In</em>参数可以包含表、选择查询或 SQL 语句的名称。</span><span class="sxs-lookup"><span data-stu-id="a0765-114">The <em>In</em> argument can contain the name of the table, a select query, or a SQL statement.</span></span></p><p><span data-ttu-id="a0765-115"><strong>注意</strong>: 指定的域不能包含存储在链接表或 ODBC 数据源中的数据。</span><span class="sxs-lookup"><span data-stu-id="a0765-115"><strong>NOTE</strong>: The specified domain cannot include data stored in a linked table or ODBC data source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a0765-116"><strong>Where 条件</strong></span><span class="sxs-lookup"><span data-stu-id="a0765-116"><strong>Where Condition</strong></span></span></p></td>
<td><p><span data-ttu-id="a0765-117">否</span><span class="sxs-lookup"><span data-stu-id="a0765-117">No</span></span></p></td>
<td><p><span data-ttu-id="a0765-118">一个字符串表达式, 用于限制要对其执行<strong>ForEachRecord</strong>数据块的数据的范围。</span><span class="sxs-lookup"><span data-stu-id="a0765-118">A string expression used to restrict the range of data on which the <strong>ForEachRecord</strong> data block is performed.</span></span> <span data-ttu-id="a0765-119">例如，条件通常相当于 SQL 表达式中的 WHERE 子句（无单词 WHERE）。</span><span class="sxs-lookup"><span data-stu-id="a0765-119">For example, criteria is often equivalent to the WHERE clause in an SQL expression, without the word WHERE.</span></span> <span data-ttu-id="a0765-120">如果省略条件, 则<strong>ForEachRecord</strong>数据块在由<em>In</em>参数指定的整个域上运行。</span><span class="sxs-lookup"><span data-stu-id="a0765-120">If criteria is omitted, the <strong>ForEachRecord</strong> data block operates on the entire domain specified by the <em>In</em> argument.</span></span> <span data-ttu-id="a0765-121">条件中包括的所有字段还必须是 <em>In</em> 中的字段。</span><span class="sxs-lookup"><span data-stu-id="a0765-121">Any field that is included in criteria must also be a field in <em>In</em>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a0765-122"><strong>Alias</strong></span><span class="sxs-lookup"><span data-stu-id="a0765-122"><strong>Alias</strong></span></span></p></td>
<td><p><span data-ttu-id="a0765-123">否</span><span class="sxs-lookup"><span data-stu-id="a0765-123">No</span></span></p></td>
<td><p><span data-ttu-id="a0765-124">为<em>In</em>参数指定的域提供备用名称的字符串。</span><span class="sxs-lookup"><span data-stu-id="a0765-124">A string that provides an alternative name for the domain specified by the <em>In</em> argument.</span></span> <span data-ttu-id="a0765-125">通常用于缩短后续引用的表名称, 以防止可能的不明确引用。如果未指定<em>alias</em> , 则表或查询名称将用作别名。</span><span class="sxs-lookup"><span data-stu-id="a0765-125">Often used to shorten the table name for subsequent references to prevent possible ambiguous references.If <em>Alias</em> is not specified, the table or query name will be used as the alias.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="a0765-126">注解</span><span class="sxs-lookup"><span data-stu-id="a0765-126">Remarks</span></span>

<span data-ttu-id="a0765-127">使用 **[ExitForEachRecord](exitforeachrecord-macro-action.md)** 操作可立即退出 **ForEachRecord** 数据块。</span><span class="sxs-lookup"><span data-stu-id="a0765-127">Use the **[ExitForEachRecord](exitforeachrecord-macro-action.md)** action to exit a **ForEachRecord** data block immediately.</span></span>

