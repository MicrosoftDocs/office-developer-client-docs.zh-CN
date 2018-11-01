---
title: Database.OpenRecordset 方法 (DAO)
TOCTitle: OpenRecordset Method
ms:assetid: a243bc79-cac4-fe12-768d-d3d017954e78
ms:mtpsurl: https://msdn.microsoft.com/library/Ff820966(v=office.15)
ms:contentKeyID: 48546753
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1052939
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 0bc6cc78d932b6735b231d86347512d1c0a4b25d
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25868285"
---
# <a name="databaseopenrecordset-method-dao"></a><span data-ttu-id="e5de0-102">Database.OpenRecordset 方法 (DAO)</span><span class="sxs-lookup"><span data-stu-id="e5de0-102">Database.OpenRecordset Method (DAO)</span></span>

<span data-ttu-id="e5de0-103">**适用于：** Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="e5de0-103">**Applies to:** Access 2013 | Office 2013</span></span>

<span data-ttu-id="e5de0-104">创建一个新的 **[Recordset](recordset-object-dao.md)** 对象，并将其追加到 **Recordsets** 集合。</span><span class="sxs-lookup"><span data-stu-id="e5de0-104">Creates a new **[Recordset](recordset-object-dao.md)** object and appends it to the **Recordsets** collection.</span></span>

## <a name="syntax"></a><span data-ttu-id="e5de0-105">语法</span><span class="sxs-lookup"><span data-stu-id="e5de0-105">Syntax</span></span>

<span data-ttu-id="e5de0-106">*表达式*。OpenRecordset （_**名称**_、_**类型**_、_**选项**_、 _**LockEdit**_）</span><span class="sxs-lookup"><span data-stu-id="e5de0-106">*expression* .OpenRecordset(_**Name**_, _**Type**_, _**Options**_, _**LockEdit**_)</span></span>

<span data-ttu-id="e5de0-107">*表达式*一个代表**Database**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="e5de0-107">*expression* A variable that represents a **Database** object.</span></span>

### <a name="parameters"></a><span data-ttu-id="e5de0-108">参数</span><span class="sxs-lookup"><span data-stu-id="e5de0-108">Parameters</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="e5de0-109">名称</span><span class="sxs-lookup"><span data-stu-id="e5de0-109">Name</span></span></p></th>
<th><p><span data-ttu-id="e5de0-110">必需/可选</span><span class="sxs-lookup"><span data-stu-id="e5de0-110">Required/Optional</span></span></p></th>
<th><p><span data-ttu-id="e5de0-111">数据类型</span><span class="sxs-lookup"><span data-stu-id="e5de0-111">Data Type</span></span></p></th>
<th><p><span data-ttu-id="e5de0-112">说明</span><span class="sxs-lookup"><span data-stu-id="e5de0-112">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e5de0-113">名称</span><span class="sxs-lookup"><span data-stu-id="e5de0-113">Name</span></span></p></td>
<td><p><span data-ttu-id="e5de0-114">必需</span><span class="sxs-lookup"><span data-stu-id="e5de0-114">Required</span></span></p></td>
<td><p><span data-ttu-id="e5de0-115"><strong>String</strong></span><span class="sxs-lookup"><span data-stu-id="e5de0-115"><strong>String</strong></span></span></p></td>
<td><p><span data-ttu-id="e5de0-p101">新的 <strong>Recordset</strong> 的记录源。该源可能是表名、查询名或返回记录的 SQL 语句。对于 Microsoft Access 数据库引擎数据库中的表类型 <strong>Recordset</strong> 对象，该源只能是表名。  </span><span class="sxs-lookup"><span data-stu-id="e5de0-p101">The source of the records for the new <strong>Recordset</strong>. The source can be a table name, a query name, or an SQL statement that returns records. For table-type <strong>Recordset</strong> objects in Microsoft Access database engine databases, the source can only be a table name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5de0-119">类型</span><span class="sxs-lookup"><span data-stu-id="e5de0-119">Type</span></span></p></td>
<td><p><span data-ttu-id="e5de0-120">可选</span><span class="sxs-lookup"><span data-stu-id="e5de0-120">Optional</span></span></p></td>
<td><p><span data-ttu-id="e5de0-121"><strong>Variant</strong></span><span class="sxs-lookup"><span data-stu-id="e5de0-121"><strong>Variant</strong></span></span></p></td>
<td><p><span data-ttu-id="e5de0-122"><strong><a href="recordsettypeenum-enumeration-dao.md">RecordsetTypeEnum</a></strong> 常量，可指示要打开的 <strong>Recordset</strong> 的类型。</span><span class="sxs-lookup"><span data-stu-id="e5de0-122">A <strong><a href="recordsettypeenum-enumeration-dao.md">RecordsetTypeEnum</a></strong> constant that indicates the type of <strong>Recordset</strong> to open.</span></span></p>

> [!NOTE]
> <span data-ttu-id="e5de0-p102">如果您在 Microsoft Access 工作区中打开了一个 **Recordset** 但未指定类型，**OpenRecordset** 将创建一个表类型 **Recordset**（如果可能）。如果您指定一个链接表或查询，**OpenRecordset** 将创建一个 dynaset 类型 **Recordset**。</span><span class="sxs-lookup"><span data-stu-id="e5de0-p102">If you open a **Recordset** in a Microsoft Access workspace and you don't specify a type, **OpenRecordset** creates a table-type **Recordset**, if possible. If you specify a linked table or query, **OpenRecordset** creates a dynaset-type **Recordset**.</span></span>


</td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5de0-125">选项</span><span class="sxs-lookup"><span data-stu-id="e5de0-125">Options</span></span></p></td>
<td><p><span data-ttu-id="e5de0-126">可选</span><span class="sxs-lookup"><span data-stu-id="e5de0-126">Optional</span></span></p></td>
<td><p><span data-ttu-id="e5de0-127"><strong>Variant</strong></span><span class="sxs-lookup"><span data-stu-id="e5de0-127"><strong>Variant</strong></span></span></p></td>
<td><p><span data-ttu-id="e5de0-128"><strong><a href="recordsetoptionenum-enumeration-dao.md">RecordsetOptionEnum</a></strong> 常量的组合，可指定新 <strong>Recordset</strong> 的特性。</span><span class="sxs-lookup"><span data-stu-id="e5de0-128">A combination of <strong><a href="recordsetoptionenum-enumeration-dao.md">RecordsetOptionEnum</a></strong> constants that specify characteristics of the new <strong>Recordset</strong>.</span></span></p>

> [!NOTE]
> <span data-ttu-id="e5de0-p103">常量 **dbConsistent** 和 **dbInconsistent** 相互排斥，同时使用两者会产生错误。当 Options 使用 **dbReadOnly** 常量时，若提供一个 LockEdit 参数，也会产生错误。</span><span class="sxs-lookup"><span data-stu-id="e5de0-p103">The constants **dbConsistent** and **dbInconsistent** are mutually exclusive, and using both causes an error. Supplying a LockEdit argument when Options uses the **dbReadOnly** constant also causes an error.</span></span>


</td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5de0-131">LockEdit</span><span class="sxs-lookup"><span data-stu-id="e5de0-131">LockEdit</span></span></p></td>
<td><p><span data-ttu-id="e5de0-132">可选</span><span class="sxs-lookup"><span data-stu-id="e5de0-132">Optional</span></span></p></td>
<td><p><span data-ttu-id="e5de0-133"><strong>Variant</strong></span><span class="sxs-lookup"><span data-stu-id="e5de0-133"><strong>Variant</strong></span></span></p></td>
<td><p><span data-ttu-id="e5de0-134"><strong><a href="locktypeenum-enumeration-dao.md">LockTypeEnum</a></strong> 常量，可确定 <strong>Recordset</strong> 是否锁定。</span><span class="sxs-lookup"><span data-stu-id="e5de0-134">A <strong><a href="locktypeenum-enumeration-dao.md">LockTypeEnum</a></strong> constant that determines the locking for the <strong>Recordset</strong>.</span></span></p>

> [!NOTE]
> <span data-ttu-id="e5de0-p104">您可以在 Options 参数或 LockedEdit 参数中使用 **dbReadOnly**，但不能同时在两个参数中使用。如果您将其同时用于两个参数，将发生运行时错误。</span><span class="sxs-lookup"><span data-stu-id="e5de0-p104">You can use **dbReadOnly** in either the Options argument or the LockedEdit argument, but not both. If you use it for both arguments, a run-time error occurs.</span></span>


</td>
</tr>
</tbody>
</table>


### <a name="return-value"></a><span data-ttu-id="e5de0-137">返回值</span><span class="sxs-lookup"><span data-stu-id="e5de0-137">Return value</span></span>

<span data-ttu-id="e5de0-138">Recordset</span><span class="sxs-lookup"><span data-stu-id="e5de0-138">Recordset</span></span>

## <a name="remarks"></a><span data-ttu-id="e5de0-139">注解</span><span class="sxs-lookup"><span data-stu-id="e5de0-139">Remarks</span></span>

<span data-ttu-id="e5de0-p105">通常，如果用户在更新记录时接收到此错误，代码应刷新字段的内容，然后检索最近修改的值。如果在删除记录时出错，代码应向用户显示新记录数据，同时显示一则消息，指示最近更改了数据。此时，代码可能会请求确认用户是否仍要删除记录。</span><span class="sxs-lookup"><span data-stu-id="e5de0-p105">Typically, if the user gets this error while updating a record, your code should refresh the contents of the fields and retrieve the newly modified values. If the error occurs while deleting a record, your code could display the new record data to the user and a message indicating that the data has recently changed. At this point, your code can request a confirmation that the user still wants to delete the record.</span></span>

<span data-ttu-id="e5de0-143">如果在 Microsoft Access 数据库引擎连接的 ODBC 工作区中，对包含 IDENTITY 列的 Microsoft SQL Server 6.0（或更新版本）表打开了 **Recordset**，则还应该使用 **dbSeeChanges** 常量，否则会导致出错。</span><span class="sxs-lookup"><span data-stu-id="e5de0-143">You should also use the **dbSeeChanges** constant if you open a **Recordset** in a Microsoft Access database engine-connected ODBC workspace against a Microsoft SQL Server 6.0 (or later) table that has an IDENTITY column, otherwise an error may result.</span></span>

<span data-ttu-id="e5de0-p106">对一个 ODBC 数据源打开多个 **Recordset** 可能会失败，因为连接正被 **OpenRecordset** 调用占用。解决此问题的一种方法是在打开 **Recordset** 后立即使用 **MoveLast** 方法，以完全填充 **Recordset**。</span><span class="sxs-lookup"><span data-stu-id="e5de0-p106">Opening more than one **Recordset** on an ODBC data source may fail because the connection is busy with a prior **OpenRecordset** call. One way around this is to fully populate the **Recordset** by using the **MoveLast** method as soon as the **Recordset** is opened.</span></span>

<span data-ttu-id="e5de0-146">使用 [**Close**](connection-close-method-dao.md) 方法关闭 **Recordset** 会自动从 **Recordsets** 集合中将其删除。</span><span class="sxs-lookup"><span data-stu-id="e5de0-146">Closing a **Recordset** with the **[Close](connection-close-method-dao.md)** method automatically deletes it from the **Recordsets** collection.</span></span>


> [!NOTE]
> <span data-ttu-id="e5de0-147">如果*源*是指的 SQL 语句组成非整数值时，连接字符串和系统参数指定非美国十进制字符，例如逗号分隔 (例如，strSQL ="价格&gt;" &amp; lngPrice，和 lngPrice =125,50)，当您尝试打开**Recordset**时就会出错。</span><span class="sxs-lookup"><span data-stu-id="e5de0-147">If *source* refers to an SQL statement composed of a string concatenated with a non-integer value, and the system parameters specify a non-U.S. decimal character such as a comma (for example, strSQL = "PRICE &gt; " &amp; lngPrice, and lngPrice = 125,50), an error occurs when you try to open the **Recordset**.</span></span> <span data-ttu-id="e5de0-148">这是因为在连接过程中，需要使用系统的默认小数字符将数字转换为字符串，并且 SQL 只接受美国格式的小数字符。</span><span class="sxs-lookup"><span data-stu-id="e5de0-148">This is because during concatenation, the number will be converted to a string using your system's default decimal character, and SQL only accepts U.S. decimal characters.</span></span>

<span data-ttu-id="e5de0-149">**链接提供** [UtterAccess](https://www.utteraccess.com)社区。</span><span class="sxs-lookup"><span data-stu-id="e5de0-149">**Link provided by** the [UtterAccess](https://www.utteraccess.com) community.</span></span> <span data-ttu-id="e5de0-150">UtterAccess 是主要的 Microsoft Access Wiki 和帮助论坛。</span><span class="sxs-lookup"><span data-stu-id="e5de0-150">UtterAccess is the premier Microsoft Access wiki and help forum.</span></span>

- [<span data-ttu-id="e5de0-151">将数据从 Access 传输到 Excel</span><span class="sxs-lookup"><span data-stu-id="e5de0-151">Transfer data from Access to Excel</span></span>](https://www.utteraccess.com/forum/transfer-data-access-ex-t1672619.html)

## <a name="example"></a><span data-ttu-id="e5de0-152">示例</span><span class="sxs-lookup"><span data-stu-id="e5de0-152">Example</span></span>

<span data-ttu-id="e5de0-153">以下示例说明如何打开基于参数查询的 Recordset。</span><span class="sxs-lookup"><span data-stu-id="e5de0-153">The following example shows how to open a Recordset that is based on a parameter query.</span></span>

<span data-ttu-id="e5de0-154">**示例代码提供者** [Microsoft Access 2010 Programmer's Reference](https://www.amazon.com/Microsoft-Access-2010-Programmers-Reference/dp/8126528125)。</span><span class="sxs-lookup"><span data-stu-id="e5de0-154">**Sample code provided by** the [Microsoft Access 2010 Programmer’s Reference](https://www.amazon.com/Microsoft-Access-2010-Programmers-Reference/dp/8126528125).</span></span>

```vb
    Dim dbs As DAO.Database
    Dim qdf As DAO.QueryDef
    Dim rst As DAO.Recordset
    
    Set dbs = CurrentDb
    
    'Get the parameter query
    Set qfd = dbs.QueryDefs("qryMyParameterQuery")
    
    'Supply the parameter value
    qdf.Parameters("EnterStartDate") = Date
    qdf.Parameters("EnterEndDate") = Date + 7
    
    'Open a Recordset based on the parameter query
    Set rst = qdf.OpenRecordset()
```

<br/>

<span data-ttu-id="e5de0-155">以下示例说明如何打开基于表或查询的 Recordset。</span><span class="sxs-lookup"><span data-stu-id="e5de0-155">The following example shows how to open a Recordset based on a table or a query.</span></span>

```vb 
    Dim dbs As DAO.Database
    Dim rsTable As DAO.Recordset
    Dim rsQuery As DAO.Recordset
    
    Set dbs = CurrentDb
    
    'Open a table-type Recordset
    Set rsTable = dbs.OpenRecordset("Table1", dbOpenTable)
    
    'Open a dynaset-type Recordset using a saved query
    Set rsQuery = dbs.OpenRecordset("qryMyQuery", dbOpenDynaset)
```

<br/>

<span data-ttu-id="e5de0-156">以下示例说明如何打开基于结构化查询语言 (SQL) 语句的 Recordset。</span><span class="sxs-lookup"><span data-stu-id="e5de0-156">The following example shows how to open a Recordset based on a Structured Query Language (SQL) statement.</span></span>

```vb
    Dim dbs As DAO.Database
    Dim rsSQL As DAO.Recordset
    Dim strSQL As String
    
    Set dbs = CurrentDb
    
    'Open a snapshot-type Recordset based on an SQL statement
    strSQL = "SELECT * FROM Table1 WHERE Field2 = 33"
    Set rsSQL = dbs.OpenRecordset(strSQL, dbOpenSnapshot)
```

<br/>

<span data-ttu-id="e5de0-157">以下示例说明如何使用 Filter 属性确定要包含在稍后打开的 Recordset 中的记录。</span><span class="sxs-lookup"><span data-stu-id="e5de0-157">The following sample shows how to use the Filter property to determine the records to be included in a subsequently opened Recordset.</span></span>

```vb
    Dim dbs As DAO.Database
    Dim rst As DAO.Recordset
    Dim rstFiltered As DAO.Recordset
    Dim strCity As String
    
    Set dbs = CurrentDb
    
    'Create the first filtered Recordset, returning customer records
    'for those visited between 30-60 days ago.
    Set rest = dbs.OpenRecordset(_ 
        "SELECT * FROM Customers WHERE LastVisitDate BETWEEN Date()-60 " & _
        "AND Date()-30 ORDER BY LastVisitDate DESC")
    
    'Begin row processing
    Do While Not rst.EOF
        
        'Retrieve the name of the first city in the selected rows
        strCity = rst!City
    
        'Now filter the Recordset to return only the customers from that city
        rst.Filter = "City = '" & strCity & "'"
        Set rstFiltered = rst.OpenRecordset
    
        'Process the rows
        Do While Not rstFiltered.EOF
            rstFiltered.Edit
            rstFiltered!ToBeVisited = True
            rstFiltered.Update
            rstFiltered.MoveNext
        Loop
    
        'We've done what was needed. Now exit
        Exit Do
        rst.MoveNext
       
    Loop
    
    'Cleanup
    rstFiltered.Close
    rst.Close
    
    Set rstFiltered = Nothing
    Set rst = Nothing
```



