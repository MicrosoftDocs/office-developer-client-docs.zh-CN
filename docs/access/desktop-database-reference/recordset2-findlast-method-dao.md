---
title: Recordset2.FindLast 方法 (DAO)
TOCTitle: FindLast Method
ms:assetid: 6a31dd00-8e05-6226-ebd8-703d2562b5c7
ms:mtpsurl: https://msdn.microsoft.com/library/Ff195400(v=office.15)
ms:contentKeyID: 48545428
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: e358459c1737cd6fff1484d1562dad02a7585337
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28717004"
---
# <a name="recordset2findlast-method-dao"></a><span data-ttu-id="e0490-102">Recordset2.FindLast 方法 (DAO)</span><span class="sxs-lookup"><span data-stu-id="e0490-102">Recordset2.FindLast method (DAO)</span></span>

<span data-ttu-id="e0490-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="e0490-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="e0490-104">在动态集类型或快照类型的 **[Recordset](recordset-object-dao.md)** 对象中查找符合指定条件的最后一条记录，并且使该记录成为当前记录（仅适用于 Microsoft Access 工作区）。</span><span class="sxs-lookup"><span data-stu-id="e0490-104">Locates the last record in a dynaset- or snapshot-type **[Recordset](recordset-object-dao.md)** object that satisfies the specified criteria and makes that record the current record (Microsoft Access workspaces only).</span></span>

## <a name="syntax"></a><span data-ttu-id="e0490-105">语法</span><span class="sxs-lookup"><span data-stu-id="e0490-105">Syntax</span></span>

<span data-ttu-id="e0490-106">*表达式*。FindLast （***标准***）</span><span class="sxs-lookup"><span data-stu-id="e0490-106">*expression* .FindLast(***Criteria***)</span></span>

<span data-ttu-id="e0490-107">*表达式*一个表示**Recordset2**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="e0490-107">*expression* A variable that represents a **Recordset2** object.</span></span>

## <a name="parameters"></a><span data-ttu-id="e0490-108">Parameters</span><span class="sxs-lookup"><span data-stu-id="e0490-108">Parameters</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="e0490-109">Name</span><span class="sxs-lookup"><span data-stu-id="e0490-109">Name</span></span></p></th>
<th><p><span data-ttu-id="e0490-110">必需/可选</span><span class="sxs-lookup"><span data-stu-id="e0490-110">Required/optional</span></span></p></th>
<th><p><span data-ttu-id="e0490-111">数据类型</span><span class="sxs-lookup"><span data-stu-id="e0490-111">Data type</span></span></p></th>
<th><p><span data-ttu-id="e0490-112">说明</span><span class="sxs-lookup"><span data-stu-id="e0490-112">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e0490-113"><em>条件</em></span><span class="sxs-lookup"><span data-stu-id="e0490-113"><em>Criteria</em></span></span></p></td>
<td><p><span data-ttu-id="e0490-114">必需</span><span class="sxs-lookup"><span data-stu-id="e0490-114">Required</span></span></p></td>
<td><p><span data-ttu-id="e0490-115"><strong>String</strong></span><span class="sxs-lookup"><span data-stu-id="e0490-115"><strong>String</strong></span></span></p></td>
<td><p><span data-ttu-id="e0490-p101">用于查找记录的字符串。它类似于 SQL 语句中的 WHERE 子句，但不包括单词 WHERE。</span><span class="sxs-lookup"><span data-stu-id="e0490-p101">A String used to locate the record. It is like the WHERE clause in an SQL statement, but without the word WHERE.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="e0490-118">注解</span><span class="sxs-lookup"><span data-stu-id="e0490-118">Remarks</span></span>

<span data-ttu-id="e0490-p102">如果要在搜索中包括所有记录（而不仅仅是符合特定条件的记录），请使用 **Move** 方法在记录之间移动。若要在表类型的 **Recordset** 中查找记录，请使用 **Seek** 方法。</span><span class="sxs-lookup"><span data-stu-id="e0490-p102">If you want to include all the records in your search — not just those that meet a specific condition — use the **Move** methods to move from record to record. To locate a record in a table-type **Recordset**, use the **Seek** method.</span></span>

<span data-ttu-id="e0490-121">如果未找到与条件匹配的记录，当前记录指针将是未知的，同时 **NoMatch** 属性将设置为 **True**。</span><span class="sxs-lookup"><span data-stu-id="e0490-121">If a record matching the criteria isn't located, the current record pointer is unknown, and the **NoMatch** property is set to **True**.</span></span> <span data-ttu-id="e0490-122">如果 recordset 中包含多个记录满足条件， **FindFirst**查找第一个匹配项， **FindNext**查找下一个匹配项，依此类推。</span><span class="sxs-lookup"><span data-stu-id="e0490-122">If recordset contains more than one record that satisfies the criteria, **FindFirst** locates the first occurrence, **FindNext** locates the next occurrence, and so on.</span></span>

<span data-ttu-id="e0490-123">每个 **Find** 方法都按下表中指定的方向，从该表指定的位置开始搜索。</span><span class="sxs-lookup"><span data-stu-id="e0490-123">Each of the **Find** methods begins its search from the location and in the direction specified in the following table.</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="e0490-124">Find 方法</span><span class="sxs-lookup"><span data-stu-id="e0490-124">Find method</span></span></p></th>
<th><p><span data-ttu-id="e0490-125">开始搜索的位置</span><span class="sxs-lookup"><span data-stu-id="e0490-125">Begins searching at</span></span></p></th>
<th><p><span data-ttu-id="e0490-126">搜索方向</span><span class="sxs-lookup"><span data-stu-id="e0490-126">Search direction</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e0490-127"><strong>FindFirst</strong></span><span class="sxs-lookup"><span data-stu-id="e0490-127"><strong>FindFirst</strong></span></span></p></td>
<td><p><span data-ttu-id="e0490-128">记录集开头</span><span class="sxs-lookup"><span data-stu-id="e0490-128">Beginning of recordset</span></span></p></td>
<td><p><span data-ttu-id="e0490-129">记录集末尾</span><span class="sxs-lookup"><span data-stu-id="e0490-129">End of recordset</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0490-130"><strong>FindLast</strong></span><span class="sxs-lookup"><span data-stu-id="e0490-130"><strong>FindLast</strong></span></span></p></td>
<td><p><span data-ttu-id="e0490-131">记录集末尾</span><span class="sxs-lookup"><span data-stu-id="e0490-131">End of recordset</span></span></p></td>
<td><p><span data-ttu-id="e0490-132">记录集开头</span><span class="sxs-lookup"><span data-stu-id="e0490-132">Beginning of recordset</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0490-133"><strong>FindNext</strong></span><span class="sxs-lookup"><span data-stu-id="e0490-133"><strong>FindNext</strong></span></span></p></td>
<td><p><span data-ttu-id="e0490-134">当前记录</span><span class="sxs-lookup"><span data-stu-id="e0490-134">Current record</span></span></p></td>
<td><p><span data-ttu-id="e0490-135">记录集末尾</span><span class="sxs-lookup"><span data-stu-id="e0490-135">End of recordset</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0490-136"><strong>FindPrevious</strong></span><span class="sxs-lookup"><span data-stu-id="e0490-136"><strong>FindPrevious</strong></span></span></p></td>
<td><p><span data-ttu-id="e0490-137">当前记录</span><span class="sxs-lookup"><span data-stu-id="e0490-137">Current record</span></span></p></td>
<td><p><span data-ttu-id="e0490-138">记录集开头</span><span class="sxs-lookup"><span data-stu-id="e0490-138">Beginning of recordset</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="e0490-139">当使用 **FindLast** 方法时，Microsoft Access 数据库引擎将在开始搜索之前完全填充您的 **Recordset**（如果尚未搜索）。</span><span class="sxs-lookup"><span data-stu-id="e0490-139">When you use the **FindLast** method, the Microsoft Access database engine fully populates your **Recordset** before beginning the search, if this hasn't already happened.</span></span>

<span data-ttu-id="e0490-p104">但是，使用 **Find** 方法之一与使用 **Move** 方法不同，后者只是将第一条、最后一条、下一条或上一条记录设置为当前记录，而不会指定条件。可以在 Find 操作后面跟随一个 Move 操作。</span><span class="sxs-lookup"><span data-stu-id="e0490-p104">Using one of the **Find** methods isn't the same as using a **Move** method, however, which simply makes the first, last, next, or previous record current without specifying a condition. You can follow a Find operation with a Move operation.</span></span>

<span data-ttu-id="e0490-p105">始终检查 **NoMatch** 属性的值，以确定 Find 操作是否已成功。如果搜索成功，则 **NoMatch** 为 **False**。如果搜索失败，则 **NoMatch** 为 **True**，并且不定义当前记录。在这种情况下，必须将当前记录指针往回定位到有效的记录。</span><span class="sxs-lookup"><span data-stu-id="e0490-p105">Always check the value of the **NoMatch** property to determine whether the Find operation has succeeded. If the search succeeds, **NoMatch** is **False**. If it fails, **NoMatch** is **True** and the current record isn't defined. In this case, you must position the current record pointer back to a valid record.</span></span>

<span data-ttu-id="e0490-146">如果将 **Find** 方法用于 Microsoft Access 数据库引擎连接的 ODBC 访问记录集，效率可能较低。</span><span class="sxs-lookup"><span data-stu-id="e0490-146">Using the **Find** methods with Microsoft Access database engine-connected ODBC-accessed recordsets can be inefficient.</span></span> <span data-ttu-id="e0490-147">您可能会发现，通过您的条件来查找特定记录缩小范围的速度更快，尤其是当处理大型记录集。</span><span class="sxs-lookup"><span data-stu-id="e0490-147">You may find that rephrasing your criteria to locate a specific record is faster, especially when working with large recordsets.</span></span>

<span data-ttu-id="e0490-p107">在处理 Microsoft Access 数据库引擎连接的 ODBC 数据库以及大型动态集类型 **Recordset** 对象时，可能会发现使用 **Find** 方法或使用 **Sort** 或 **Filter** 属性都比较慢。若要改善性能，请将 SQL 查询与自定义的 ORDER BY 或 WHERE 子句、参数查询或检索特定索引记录的 **QueryDef** 对象一起使用。</span><span class="sxs-lookup"><span data-stu-id="e0490-p107">When working with Microsoft Access database engine-connected ODBC databases and large dynaset-type **Recordset** objects, you might discover that using the **Find** methods or using the **Sort** or **Filter** property is slow. To improve performance, use SQL queries with customized ORDER BY or WHERE clauses, parameter queries, or **QueryDef** objects that retrieve specific indexed records.</span></span>

<span data-ttu-id="e0490-p108">在搜索包含日期的字段时，即使使用的不是美国版本的 Microsoft Access 数据库引擎，也应使用美国日期格式（月-日-年）；否则将无法找到数据。使用 Visual Basic **Format** 函数转换日期。例如：</span><span class="sxs-lookup"><span data-stu-id="e0490-p108">You should use the U.S. date format (month-day-year) when you search for fields containing dates, even if you're not using the U.S. version of the Microsoft Access database engine; otherwise, the data may not be found. Use the Visual Basic **Format** function to convert the date. For example:</span></span>

```vb
rstEmployees.FindFirst "HireDate > #" _ 
        & Format(mydate, 'm-d-yy' ) & "#" 
```

> [!NOTE]
> <span data-ttu-id="e0490-153">如果条件组成的字符串串联非整数值，并且系统参数指定非美国十进制字符，例如逗号分隔 (例如，strSQL ="价格\>"& lngPrice 和 lngPrice = 125,50)，当您尝试出错调用方法。</span><span class="sxs-lookup"><span data-stu-id="e0490-153">If criteria is composed of a string concatenated with a non-integer value, and the system parameters specify a non-U.S. decimal character such as a comma (for example, strSQL = "PRICE \> " & lngPrice, and lngPrice = 125,50), an error occurs when you try to call the method.</span></span> <span data-ttu-id="e0490-154">这是因为在连接过程中，需要使用系统的默认小数字符将数字转换为字符串，并且 Microsoft Access SQL 只接受美国格式的小数字符。</span><span class="sxs-lookup"><span data-stu-id="e0490-154">This is because during concatenation, the number will be converted to a string using your system's default decimal character, and Microsoft Access SQL only accepts U.S. decimal characters.</span></span>

> [!NOTE]
> - <span data-ttu-id="e0490-155">为了获得最佳性能，*条件*\* 应在窗体"*字段* = *值*"*字段*中的基础表或"*字段*LIKE*前缀"其中*字段*是*为索引的字段的其中索引的字段中的基础表和*前缀*为前缀搜索字符串 （例如，"画 \*"）。</span><span class="sxs-lookup"><span data-stu-id="e0490-155">For best performance, the *criteria*\* should be in either the form "*field* = *value*" where *field* is an indexed field in the underlying base table, or "*field* LIKE *prefix*" where *field* is an indexed field in the underlying base table and *prefix* is a prefix search string (for example, "ART\*").</span></span>
> - <span data-ttu-id="e0490-p110">一般而言，作为等效的搜索类型， **Seek** 方法的性能优于 **Find** 方法。这假定表类型的 **Recordset** 对象可单独满足您的需求。</span><span class="sxs-lookup"><span data-stu-id="e0490-p110">In general, for equivalent types of searches, the **Seek** method provides better performance than the **Find** methods. This assumes that table-type **Recordset** objects alone can satisfy your needs.</span></span>


