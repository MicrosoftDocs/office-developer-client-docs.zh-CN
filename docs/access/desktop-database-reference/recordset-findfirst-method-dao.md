---
title: Recordset.FindFirst 方法 (DAO)
TOCTitle: FindFirst Method
ms:assetid: 5fcf78cd-7d2c-2e47-14e5-996f2e14ff51
ms:mtpsurl: https://msdn.microsoft.com/library/Ff194787(v=office.15)
ms:contentKeyID: 48545170
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Priority
ms.openlocfilehash: b2e334dcad84d2a9c3441e76e6552c1cb04f8552
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32300530"
---
# <a name="recordsetfindfirst-method-dao"></a><span data-ttu-id="ba700-102">Recordset.FindFirst 方法 (DAO)</span><span class="sxs-lookup"><span data-stu-id="ba700-102">Recordset.FindFirst method (DAO)</span></span>

<span data-ttu-id="ba700-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="ba700-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="ba700-104">在动态集类型或快照类型的 **Recordset** 对象中查找符合指定条件的第一条记录，并使该记录成为当前记录（仅适用于 Microsoft Access 工作区）。</span><span class="sxs-lookup"><span data-stu-id="ba700-104">Locates the first record in a dynaset- or snapshot-type **Recordset** object that satisfies the specified criteria and makes that record the current record (Microsoft Access workspaces only).</span></span>

## <a name="syntax"></a><span data-ttu-id="ba700-105">语法</span><span class="sxs-lookup"><span data-stu-id="ba700-105">Syntax</span></span>

<span data-ttu-id="ba700-106">*表达式* .FindFirst(***Criteria***)</span><span class="sxs-lookup"><span data-stu-id="ba700-106">*expression* .FindFirst(***Criteria***)</span></span>

<span data-ttu-id="ba700-107">*表达式* 一个表示 **Recordset** 对象的变量。</span><span class="sxs-lookup"><span data-stu-id="ba700-107">*expression*  A variable that represents a **Recordset** object.</span></span>

## <a name="parameters"></a><span data-ttu-id="ba700-108">参数</span><span class="sxs-lookup"><span data-stu-id="ba700-108">Parameters</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="ba700-109">名称</span><span class="sxs-lookup"><span data-stu-id="ba700-109">Name</span></span></p></th>
<th><p><span data-ttu-id="ba700-110">必需/可选</span><span class="sxs-lookup"><span data-stu-id="ba700-110">Required/Optional</span></span></p></th>
<th><p><span data-ttu-id="ba700-111">数据类型</span><span class="sxs-lookup"><span data-stu-id="ba700-111">Data type</span></span></p></th>
<th><p><span data-ttu-id="ba700-112">说明</span><span class="sxs-lookup"><span data-stu-id="ba700-112">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ba700-113"><em>Criteria</em></span><span class="sxs-lookup"><span data-stu-id="ba700-113"><em>Criteria</em></span></span></p></td>
<td><p><span data-ttu-id="ba700-114">必需</span><span class="sxs-lookup"><span data-stu-id="ba700-114">Required</span></span></p></td>
<td><p><span data-ttu-id="ba700-115"><strong>String</strong></span><span class="sxs-lookup"><span data-stu-id="ba700-115"><strong>String</strong></span></span></p></td>
<td><p><span data-ttu-id="ba700-116">用于查找记录的字符串。</span><span class="sxs-lookup"><span data-stu-id="ba700-116">A String used to locate the record.</span></span> <span data-ttu-id="ba700-117">它类似于 SQL 语句中的 WHERE 子句，但不包括单词 WHERE。</span><span class="sxs-lookup"><span data-stu-id="ba700-117">It is like the WHERE clause in an SQL statement, but without the word WHERE.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="ba700-118">说明</span><span class="sxs-lookup"><span data-stu-id="ba700-118">Remarks</span></span>

<span data-ttu-id="ba700-p102">如果要在搜索中包括所有记录（而不仅仅是符合特定条件的记录），请使用 **Move** 方法在记录之间移动。若要在表类型的 **Recordset** 中查找记录，请使用 **Seek** 方法。</span><span class="sxs-lookup"><span data-stu-id="ba700-p102">If you want to include all the records in your search — not just those that meet a specific condition — use the **Move** methods to move from record to record. To locate a record in a table-type **Recordset**, use the **Seek** method.</span></span>

<span data-ttu-id="ba700-121">如果没找到条件匹配的记录，当前记录指针未知，且**NoMatch**属性设置为**True**。</span><span class="sxs-lookup"><span data-stu-id="ba700-121">If a record matching the criteria isn't located, the current record pointer is unknown, and the **NoMatch** property is set to **True**.</span></span> <span data-ttu-id="ba700-122">如果 recordset 包含多个符合条件的记录， **FindFirst** 将查找第一个出现的记录， **FindNext** 将查找下一个出现的记录，以此类推。</span><span class="sxs-lookup"><span data-stu-id="ba700-122">If  recordset contains more than one record that satisfies the criteria, **FindFirst** locates the first occurrence, **FindNext** locates the next occurrence, and so on.</span></span>

<span data-ttu-id="ba700-123">每个**Find**方法都从下表中指定的位置和方向开始搜索。</span><span class="sxs-lookup"><span data-stu-id="ba700-123">Each of the **Find** methods begins its search from the location and in the direction specified in the following table.</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="ba700-124">Find 方法</span><span class="sxs-lookup"><span data-stu-id="ba700-124">Find method</span></span></p></th>
<th><p><span data-ttu-id="ba700-125">开始搜索的位置</span><span class="sxs-lookup"><span data-stu-id="ba700-125">Begins searching at</span></span></p></th>
<th><p><span data-ttu-id="ba700-126">搜索方向</span><span class="sxs-lookup"><span data-stu-id="ba700-126">Search direction</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ba700-127"><strong>FindFirst</strong></span><span class="sxs-lookup"><span data-stu-id="ba700-127"><strong>FindFirst method</strong></span></span></p></td>
<td><p><span data-ttu-id="ba700-128">记录集开头</span><span class="sxs-lookup"><span data-stu-id="ba700-128">Beginning of recordset</span></span></p></td>
<td><p><span data-ttu-id="ba700-129">记录集结尾</span><span class="sxs-lookup"><span data-stu-id="ba700-129">End of recordset</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba700-130"><strong>FindLast</strong></span><span class="sxs-lookup"><span data-stu-id="ba700-130"><strong>FindLast method</strong></span></span></p></td>
<td><p><span data-ttu-id="ba700-131">记录集结尾</span><span class="sxs-lookup"><span data-stu-id="ba700-131">End of recordset</span></span></p></td>
<td><p><span data-ttu-id="ba700-132">记录集开头</span><span class="sxs-lookup"><span data-stu-id="ba700-132">Beginning of recordset</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba700-133"><strong>FindNext</strong></span><span class="sxs-lookup"><span data-stu-id="ba700-133"><strong>FindNext</strong></span></span></p></td>
<td><p><span data-ttu-id="ba700-134">当前记录</span><span class="sxs-lookup"><span data-stu-id="ba700-134">Current record</span></span></p></td>
<td><p><span data-ttu-id="ba700-135">记录集末尾</span><span class="sxs-lookup"><span data-stu-id="ba700-135">End of recordset</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba700-136"><strong>FindPrevious</strong></span><span class="sxs-lookup"><span data-stu-id="ba700-136"><strong>FindPrevious</strong></span></span></p></td>
<td><p><span data-ttu-id="ba700-137">当前记录</span><span class="sxs-lookup"><span data-stu-id="ba700-137">Current record</span></span></p></td>
<td><p><span data-ttu-id="ba700-138">记录集开头</span><span class="sxs-lookup"><span data-stu-id="ba700-138">Beginning of recordset</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="ba700-p104">但是，使用 **Find** 方法之一与使用 **Move** 方法不同，后者只是将第一条、最后一条、下一条或上一条记录设置为当前记录，而不会指定条件。可以在 Find 操作后面跟随一个 Move 操作。</span><span class="sxs-lookup"><span data-stu-id="ba700-p104">Using one of the **Find** methods isn't the same as using a **Move** method, however, which simply makes the first, last, next, or previous record current without specifying a condition. You can follow a Find operation with a Move operation.</span></span>

<span data-ttu-id="ba700-p105">始终检查 **NoMatch** 属性的值，以确定 Find 操作是否已成功。如果搜索成功，则 **NoMatch** 为 **False**。如果搜索失败，则 **NoMatch** 为 **True**，并且不定义当前记录。在这种情况下，必须将当前记录指针往回定位到有效的记录。</span><span class="sxs-lookup"><span data-stu-id="ba700-p105">Always check the value of the **NoMatch** property to determine whether the Find operation has succeeded. If the search succeeds, **NoMatch** is **False**. If it fails, **NoMatch** is **True** and the current record isn't defined. In this case, you must position the current record pointer back to a valid record.</span></span>

<span data-ttu-id="ba700-145">借助 Microsoft Access 数据库引擎连接 ODBC 访问记录集使用**Find**方法效率低下。</span><span class="sxs-lookup"><span data-stu-id="ba700-145">Using the **Find** methods with Microsoft Access database engine-connected ODBC-accessed recordsets can be inefficient.</span></span> <span data-ttu-id="ba700-146">你可能会发现，重新定义 criteria 来查找特定记录的速度将更快，尤其是在处理大型记录集时。</span><span class="sxs-lookup"><span data-stu-id="ba700-146">You may find that rephrasing your  criteria to locate a specific record is faster, especially when working with large recordsets.</span></span>

<span data-ttu-id="ba700-p107">在处理 Microsoft Access 数据库引擎连接的 ODBC 数据库以及大型动态集类型 **Recordset** 对象时，可能会发现使用 **Find** 方法或使用 **Sort** 或 **Filter** 属性都比较慢。若要改善性能，请将 SQL 查询与自定义的 ORDER BY 或 WHERE 子句、参数查询或检索特定索引记录的 **QueryDef** 对象一起使用。</span><span class="sxs-lookup"><span data-stu-id="ba700-p107">When working with Microsoft Access database engine-connected ODBC databases and large dynaset-type **Recordset** objects, you might discover that using the **Find** methods or using the **Sort** or **Filter** property is slow. To improve performance, use SQL queries with customized ORDER BY or WHERE clauses, parameter queries, or **QueryDef** objects that retrieve specific indexed records.</span></span>

<span data-ttu-id="ba700-p108">在搜索包含日期的字段时，即使使用的不是美国版本的 Microsoft Access 数据库引擎，也应使用美国日期格式（月-日-年）；否则将无法找到数据。使用 Visual Basic **Format** 函数转换日期。例如：</span><span class="sxs-lookup"><span data-stu-id="ba700-p108">You should use the U.S. date format (month-day-year) when you search for fields containing dates, even if you're not using the U.S. version of the Microsoft Access database engine; otherwise, the data may not be found. Use the Visual Basic **Format** function to convert the date. For example:</span></span>

```vb
    rstEmployees.FindFirst "HireDate > #" _ 
        & Format(mydate, 'm-d-yy' ) & "#" 
```

<span data-ttu-id="ba700-152">如果 criteria 由连接了非整数值的字符串组成，并且系统参数指定了诸如逗号的非美国格式小数字符（例如 strSQL = "PRICE \> " & lngPrice 和 lngPrice = 125,50），那么在尝试调用此方法时发生错误。</span><span class="sxs-lookup"><span data-stu-id="ba700-152">If criteria is composed of a string concatenated with a non-integer value, and the system parameters specify a non-U.S. decimal character such as a comma (for example, strSQL = "PRICE > " & lngPrice, and lngPrice = 125,50), an error occurs when you try to call the method.</span></span> <span data-ttu-id="ba700-153">这是因为在连接过程中，需要使用系统的默认小数字符将数字转换为字符串，并且 Microsoft Access SQL 只接受美国格式的小数字符。</span><span class="sxs-lookup"><span data-stu-id="ba700-153">This is because during concatenation, the number will be converted to a string using your system's default decimal character, and Microsoft Access SQL only accepts U.S. decimal characters.</span></span>


> [!NOTE]
> - <span data-ttu-id="ba700-154">为获得最佳性能，*criteria* 应该要么是 "*field* = *value*"（其中 *field* 为基础基表中的索引字段），要么是 "*field* LIKE *prefix*"（其中 *field* 是基础基表中的索引字段，而 *prefix* 是前缀搜索字符串（例如 "ART\*"））。</span><span class="sxs-lookup"><span data-stu-id="ba700-154">For best performance, the criteria should be in either the form "field = value" where field is an indexed field in the underlying base table, or "field LIKE prefix" where field is an indexed field in the underlying base table and prefix is a prefix search string (for example, "ART\*"
).</span></span>
> 
> - <span data-ttu-id="ba700-p110">一般而言，作为等效的搜索类型， **Seek** 方法的性能优于 **Find** 方法。这假定表类型的 **Recordset** 对象可单独满足您的需求。</span><span class="sxs-lookup"><span data-stu-id="ba700-p110">In general, for equivalent types of searches, the **Seek** method provides better performance than the **Find** methods. This assumes that table-type **Recordset** objects alone can satisfy your needs.</span></span>


## <a name="example"></a><span data-ttu-id="ba700-157">示例</span><span class="sxs-lookup"><span data-stu-id="ba700-157">Example</span></span>

<span data-ttu-id="ba700-158">以下示例说明如何使用 FindFirst 和 FindNext 方法在 Recordset 中查找记录。</span><span class="sxs-lookup"><span data-stu-id="ba700-158">The following example shows how to use the FindFirst and FindNext methods to find a record in a Recordset.</span></span>

<span data-ttu-id="ba700-159">**示例代码提供方：**[Microsoft Access 2010 程序员参考](https://www.amazon.com/Microsoft-Access-2010-Programmers-Reference/dp/8126528125)。</span><span class="sxs-lookup"><span data-stu-id="ba700-159">**Sample code provided by** the [Microsoft Access 2010 Programmer’s Reference](https://www.amazon.com/Microsoft-Access-2010-Programmers-Reference/dp/8126528125).</span></span>

```vb
    Sub FindOrgName()
    
        Dim dbs As DAO.Database
        Dim rst As DAO.Recordset
        
        'Get the database and Recordset
        Set dbs = CurrentDb
        Set rst = dbs.OpenRecordset("tblCustomers")
    
        'Search for the first matching record   
        rst.FindFirst "[OrgName] LIKE '*parts*'"
        
        'Check the result
        If rst.NoMatch Then
            MsgBox "Record not found."
            GotTo Cleanup
        Else
            Do While Not rst.NoMatch
                MsgBox "Customer name: " & rst!CustName
                rst.FindNext "[OrgName] LIKE '*parts*'"
            Loop
    
            'Search for the next matching record
            rst.FindNext "[OrgName] LIKE '*parts*'"
        End If
       
        Cleanup:
            rst.Close
            Set rst = Nothing
            Set dbs = Nothing
    
    End Sub
```
