---
title: ForEachRecord 数据块
TOCTitle: ForEachRecord data block
ms:assetid: be369196-230e-1f92-e36b-667048eef2be
ms:mtpsurl: https://msdn.microsoft.com/library/Ff822743(v=office.15)
ms:contentKeyID: 48547455
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 09a09a80773adecf760ae4610df30bbd5f36f3d6
ms.sourcegitcommit: 38d0db57580cc5f4a0231c27b1643f8db5431ca3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25937524"
---
# <a name="foreachrecord-data-block"></a><span data-ttu-id="40a4d-102">ForEachRecord 数据块</span><span class="sxs-lookup"><span data-stu-id="40a4d-102">ForEachRecord data block</span></span>


<span data-ttu-id="40a4d-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="40a4d-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="40a4d-104">**ForEachRecord**数据块的域中的每个记录都重复一组语句。</span><span class="sxs-lookup"><span data-stu-id="40a4d-104">A **ForEachRecord** data block repeats a set of statements for each record in a domain.</span></span>

> [!NOTE]
> <span data-ttu-id="40a4d-105">[!注释] **ForEachRecord** 数据块仅适用于数据宏。</span><span class="sxs-lookup"><span data-stu-id="40a4d-105">The **ForEachRecord** data block is available only in Data Macros.</span></span>

## <a name="setting"></a><span data-ttu-id="40a4d-106">设置</span><span class="sxs-lookup"><span data-stu-id="40a4d-106">Setting</span></span>

<span data-ttu-id="40a4d-107">**ForEachRecord** 操作具有以下参数。</span><span class="sxs-lookup"><span data-stu-id="40a4d-107">The **ForEachRecord** action has the following arguments.</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="40a4d-108">参数</span><span class="sxs-lookup"><span data-stu-id="40a4d-108">Argument</span></span></p></th>
<th><p><span data-ttu-id="40a4d-109">是否必需</span><span class="sxs-lookup"><span data-stu-id="40a4d-109">Required</span></span></p></th>
<th><p><span data-ttu-id="40a4d-110">说明</span><span class="sxs-lookup"><span data-stu-id="40a4d-110">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="40a4d-111"><strong>In</strong></span><span class="sxs-lookup"><span data-stu-id="40a4d-111"><strong>In</strong></span></span></p></td>
<td><p><span data-ttu-id="40a4d-112">是</span><span class="sxs-lookup"><span data-stu-id="40a4d-112">Yes</span></span></p></td>
<td><p><span data-ttu-id="40a4d-113">一个字符串，标识的记录执行操作的域。</span><span class="sxs-lookup"><span data-stu-id="40a4d-113">A string that identifies the domain of records to operate on.</span></span> <span data-ttu-id="40a4d-114"><em>在</em>参数可以包含表、 选择查询或 SQL 语句的名称。</span><span class="sxs-lookup"><span data-stu-id="40a4d-114">The <em>In</em> argument can contain the name of the table, a select query, or a SQL statement.</span></span></p>

> [!NOTE]
> <span data-ttu-id="40a4d-115">指定域不能包括链接表或 ODBC 数据源中存储的数据。</span><span class="sxs-lookup"><span data-stu-id="40a4d-115">The specified domain cannot include data stored in a linked table or ODBC data source.</span></span>


<p></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="40a4d-116"><strong>Where Condition</strong></span><span class="sxs-lookup"><span data-stu-id="40a4d-116"><strong>Where Condition</strong></span></span></p></td>
<td><p><span data-ttu-id="40a4d-117">否</span><span class="sxs-lookup"><span data-stu-id="40a4d-117">No</span></span></p></td>
<td><p><span data-ttu-id="40a4d-118">执行字符串表达式，用来限制在其上的数据区域<strong>ForEachRecord</strong>数据块。</span><span class="sxs-lookup"><span data-stu-id="40a4d-118">A string expression used to restrict the range of data on which the <strong>ForEachRecord</strong> data block is performed.</span></span> <span data-ttu-id="40a4d-119">例如，criteria通常是相当于 SQL 表达式中的 WHERE 子句位置，但是不使用 WHERE一词。</span><span class="sxs-lookup"><span data-stu-id="40a4d-119">For example, criteria is often equivalent to the WHERE clause in an SQL expression, without the word WHERE.</span></span> <span data-ttu-id="40a4d-120">如果省略条件，则<strong>ForEachRecord</strong>数据块运行上指定<em>中</em>参数的整个域。</span><span class="sxs-lookup"><span data-stu-id="40a4d-120">If criteria is omitted, the <strong>ForEachRecord</strong> data block operates on the entire domain specified by the <em>In</em> argument.</span></span> <span data-ttu-id="40a4d-121">条件中包括的任何字段必须同时是<em>中</em>的字段。</span><span class="sxs-lookup"><span data-stu-id="40a4d-121">Any field that is included in criteria must also be a field in <em>In</em>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="40a4d-122"><strong>Alias</strong></span><span class="sxs-lookup"><span data-stu-id="40a4d-122"><strong>Alias</strong></span></span></p></td>
<td><p><span data-ttu-id="40a4d-123">否</span><span class="sxs-lookup"><span data-stu-id="40a4d-123">No</span></span></p></td>
<td><p><span data-ttu-id="40a4d-124">提供<em>在</em>参数指定的域的替代名称的字符串。</span><span class="sxs-lookup"><span data-stu-id="40a4d-124">A string that provides an alternative name for the domain specified by the <em>In</em> argument.</span></span> <span data-ttu-id="40a4d-125">通常用于缩短后续参考，以防止可能出现的不明确引用的表名称。如果未指定<em>别名</em>，则表或查询名称将用作别名。</span><span class="sxs-lookup"><span data-stu-id="40a4d-125">Often used to shorten the table name for subsequent references to prevent possible ambiguous references.If <em>Alias</em> is not specified, the table or query name will be used as the alias.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="40a4d-126">注释</span><span class="sxs-lookup"><span data-stu-id="40a4d-126">Remarks</span></span>

<span data-ttu-id="40a4d-127">使用 **[ExitForEachRecord](exitforeachrecord-macro-action.md)** 操作可立即退出 **ForEachRecord** 数据块。</span><span class="sxs-lookup"><span data-stu-id="40a4d-127">Use the **[ExitForEachRecord](exitforeachrecord-macro-action.md)** action to exit a **ForEachRecord** data block immediately.</span></span>

