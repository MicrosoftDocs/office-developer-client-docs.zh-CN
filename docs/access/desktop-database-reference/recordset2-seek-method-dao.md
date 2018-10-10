---
title: Recordset2.Seek Method (DAO)
TOCTitle: Seek Method
ms:assetid: 9871619b-a303-c97d-54c0-defc8d9b87f5
ms:mtpsurl: https://msdn.microsoft.com/library/Ff197940(v=office.15)
ms:contentKeyID: 48546489
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: b1fe810516f5c9b79897267650e757bbf856b4ac
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25468317"
---
# <a name="recordset2seek-method-dao"></a><span data-ttu-id="2c285-102">Recordset2.Seek Method (DAO)</span><span class="sxs-lookup"><span data-stu-id="2c285-102">Recordset2.Seek Method (DAO)</span></span>


<span data-ttu-id="2c285-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="2c285-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="2c285-104">在已建立索引的表类型 **Recordset** 对象中查找符合当前索引的指定条件的记录，并使该记录成为当前记录（仅适用于 Microsoft Access 工作区）。</span><span class="sxs-lookup"><span data-stu-id="2c285-104">Locates the record in an indexed table-type **Recordset** object that satisfies the specified criteria for the current index and makes that record the current record (Microsoft Access workspaces only).</span></span>

## <a name="syntax"></a><span data-ttu-id="2c285-105">语法</span><span class="sxs-lookup"><span data-stu-id="2c285-105">Syntax</span></span>

<span data-ttu-id="2c285-106">*表达式*。Seek （***比较*** ***Key1***、 ***Key2***、 ***Key3***、 ***Key4***、 ***Key5***、 ***Key6***、 ***Key7***、 ***Key8***、 ***Key9***、 ***Key10***、 ***Key11***、 ***Key12***、 ***Key13***）</span><span class="sxs-lookup"><span data-stu-id="2c285-106">*expression* .Seek(***Comparison***, ***Key1***, ***Key2***, ***Key3***, ***Key4***, ***Key5***, ***Key6***, ***Key7***, ***Key8***, ***Key9***, ***Key10***, ***Key11***, ***Key12***, ***Key13***)</span></span>

<span data-ttu-id="2c285-107">*表达式*一个表示**Recordset2**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="2c285-107">*expression* A variable that represents a **Recordset2** object.</span></span>

### <a name="parameters"></a><span data-ttu-id="2c285-108">参数</span><span class="sxs-lookup"><span data-stu-id="2c285-108">Parameters</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="2c285-109">名称</span><span class="sxs-lookup"><span data-stu-id="2c285-109">Name</span></span></p></th>
<th><p><span data-ttu-id="2c285-110">必需/可选</span><span class="sxs-lookup"><span data-stu-id="2c285-110">Required/Optional</span></span></p></th>
<th><p><span data-ttu-id="2c285-111">数据类型</span><span class="sxs-lookup"><span data-stu-id="2c285-111">Data Type</span></span></p></th>
<th><p><span data-ttu-id="2c285-112">说明</span><span class="sxs-lookup"><span data-stu-id="2c285-112">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2c285-113">Comparison</span><span class="sxs-lookup"><span data-stu-id="2c285-113">Comparison</span></span></p></td>
<td><p><span data-ttu-id="2c285-114">必需</span><span class="sxs-lookup"><span data-stu-id="2c285-114">Required</span></span></p></td>
<td><p><span data-ttu-id="2c285-115"><strong>字符串</strong></span><span class="sxs-lookup"><span data-stu-id="2c285-115"><strong>String</strong></span></span></p></td>
<td><p><span data-ttu-id="2c285-116">下列字符串表达式之一： &lt;， &lt;=、 =、 &gt;=，或&gt;。</span><span class="sxs-lookup"><span data-stu-id="2c285-116">One of the following string expressions: &lt;, &lt;=, =, &gt;=, or &gt;.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2c285-117">Key1，Key2...Key13</span><span class="sxs-lookup"><span data-stu-id="2c285-117">Key1, Key2...Key13</span></span></p></td>
<td><p><span data-ttu-id="2c285-118">必需</span><span class="sxs-lookup"><span data-stu-id="2c285-118">Required</span></span></p></td>
<td><p><span data-ttu-id="2c285-119"><strong>Variant</strong></span><span class="sxs-lookup"><span data-stu-id="2c285-119"><strong>Variant</strong></span></span></p></td>
<td><p><span data-ttu-id="2c285-p101">与 <strong>Recordset</strong> 对象当前索引中的字段对应的一个或多个值，该索引由它的 <strong>Index</strong> 属性设置指定。最多可使用 13 个 key 参数。</span><span class="sxs-lookup"><span data-stu-id="2c285-p101">One or more values corresponding to fields in the <strong>Recordset</strong> object's current index, as specified by its <strong>Index</strong> property setting. You can use up to 13 key arguments.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="2c285-122">注解</span><span class="sxs-lookup"><span data-stu-id="2c285-122">Remarks</span></span>

<span data-ttu-id="2c285-p102">在使用 **Seek** 之前，必须使用 **Index** 属性设置当前索引。如果索引标识了一个非唯一的键字段， **Seek** 将查找第一个符合条件的记录。</span><span class="sxs-lookup"><span data-stu-id="2c285-p102">You must set the current index with the **Index** property before you use **Seek**. If the index identifies a nonunique key field, **Seek** locates the first record that satisfies the criteria.</span></span>

<span data-ttu-id="2c285-125">**Seek**方法通过指定的键字段搜索，并查找满足指定相比较的条件和 key1 的第一个记录。</span><span class="sxs-lookup"><span data-stu-id="2c285-125">The **Seek** method searches through the specified key fields and locates the first record that satisfies the criteria specified by comparison and key1.</span></span> <span data-ttu-id="2c285-126">一旦找到，它就会使该记录成为当前记录，同时将 **NoMatch** 属性设置为 **False**。</span><span class="sxs-lookup"><span data-stu-id="2c285-126">Once found, it makes that record current and sets the **NoMatch** property to **False**.</span></span> <span data-ttu-id="2c285-127">如果 **Seek** 方法未能找到匹配项， **NoMatch** 属性将设置为 **True**，并且当前记录不确定。</span><span class="sxs-lookup"><span data-stu-id="2c285-127">If the **Seek** method fails to locate a match, the **NoMatch** property is set to **True**, and the current record is undefined.</span></span>

<span data-ttu-id="2c285-128">如果 comparison 是等于 （=），大于或等于 (\>=)，或大于 (\>)、 从索引的开头开始**Seek**和向前搜索。</span><span class="sxs-lookup"><span data-stu-id="2c285-128">If comparison is equal (=), greater than or equal (\>=), or greater than (\>), **Seek** starts at the beginning of the index and searches forward.</span></span>

<span data-ttu-id="2c285-129">如果 comparison 是小于 (\<) 或小于或等于 (\<=)， **Seek**启动末尾的索引和往回搜索。</span><span class="sxs-lookup"><span data-stu-id="2c285-129">If comparison is less than (\<) or less than or equal (\<=), **Seek** starts at the end of the index and searches backward.</span></span> <span data-ttu-id="2c285-130">但是，如果索引的末尾有重复的索引项， **Seek** 将从重复项中的任一项开始往后搜索。</span><span class="sxs-lookup"><span data-stu-id="2c285-130">However, if there are duplicate index entries at the end of the index, **Seek** starts at an arbitrary entry among the duplicates and then searches backward.</span></span>

<span data-ttu-id="2c285-131">必须为索引中定义的所有字段指定值。</span><span class="sxs-lookup"><span data-stu-id="2c285-131">You must specify values for all fields defined in the index.</span></span> <span data-ttu-id="2c285-132">如果将 **Seek** 用于多列索引，并且没有为索引中的每个字段指定 comparison 值，则无法在 comparison 中使用等于 (=) 运算符。</span><span class="sxs-lookup"><span data-stu-id="2c285-132">If you use **Seek** with a multiple-column index, and you don't specify a comparison value for every field in the index, then you cannot use the equal (=) operator in the comparison.</span></span> <span data-ttu-id="2c285-133">这是因为某些条件字段 （key2、 key3，等等） 将默认为 Null，可能不匹配。</span><span class="sxs-lookup"><span data-stu-id="2c285-133">That's because some of the criteria fields (key2, key3, and so on) will default to Null, which will probably not match.</span></span> <span data-ttu-id="2c285-134">因此，仅当除查找的键字段外，所有字段均为 **null** 的记录时，等于运算符才能正常工作。</span><span class="sxs-lookup"><span data-stu-id="2c285-134">Therefore, the equal operator will work correctly only if you have a record which is all **null** except the key you're looking for.</span></span> <span data-ttu-id="2c285-135">建议您使用大于或等于 (\>=) 运算符相反。</span><span class="sxs-lookup"><span data-stu-id="2c285-135">It's recommended that you use the greater than or equal (\>=) operator instead.</span></span>

<span data-ttu-id="2c285-136">在 key1 参数必须是当前索引中的对应字段的字段数据类型相同。</span><span class="sxs-lookup"><span data-stu-id="2c285-136">The key1 argument must be of the same field data type as the corresponding field in the current index.</span></span> <span data-ttu-id="2c285-137">例如，如果当前索引引用 （如雇员 ID) 的数字字段，key1 必须为数字。</span><span class="sxs-lookup"><span data-stu-id="2c285-137">For example, if the current index refers to a number field (such as Employee ID), key1 must be numeric.</span></span> <span data-ttu-id="2c285-138">同样，如果当前索引引用 （如姓氏） 的文本字段，key1 必须是字符串。</span><span class="sxs-lookup"><span data-stu-id="2c285-138">Similarly, if the current index refers to a Text field (such as Last Name), key1 must be a string.</span></span>

<span data-ttu-id="2c285-139">使用 **Seek** 时不一定要有当前记录。</span><span class="sxs-lookup"><span data-stu-id="2c285-139">There doesn't have to be a current record when you use **Seek**.</span></span>

<span data-ttu-id="2c285-140">可以使用 **[Indexes](indexes-collection-dao.md)** 集合枚举现有索引。</span><span class="sxs-lookup"><span data-stu-id="2c285-140">You can use the **[Indexes](indexes-collection-dao.md)** collection to enumerate the existing indexes.</span></span>

<span data-ttu-id="2c285-p107">要在动态集类型或快照类型的 **Recordset** 中查找一个符合特定条件且没有被现有索引覆盖的记录，请使用 **[Find](recordset2-findfirst-method-dao.md)** 方法。要包括所有记录而不仅仅是符合特定条件的那些记录，请使用 **[Move](recordset-movefirst-method-dao.md)** 方法在记录间移动。</span><span class="sxs-lookup"><span data-stu-id="2c285-p107">To locate a record in a dynaset- or snapshot-type **Recordset** that satisfies a specific condition that is not covered by existing indexes, use the **[Find](recordset2-findfirst-method-dao.md)** methods. To include all records, not just those that satisfy a specific condition, use the **[Move](recordset-movefirst-method-dao.md)** methods to move from record to record.</span></span>

<span data-ttu-id="2c285-p108">不能对链接表使用 **Seek** 方法，原因是不能将链接表打开为表类型 **Recordset** 对象。但是，如果使用 **[OpenDatabase](dbengine-opendatabase-method-dao.md)** 方法直接打开一个可安装的 ISAM（非 ODBC）数据库，则可以对该数据库中的表使用 **Seek**。</span><span class="sxs-lookup"><span data-stu-id="2c285-p108">You can't use the **Seek** method on a linked table because you can't open linked tables as table-type **Recordset** objects. However, if you use the **[OpenDatabase](dbengine-opendatabase-method-dao.md)** method to directly open an installable ISAM (non-ODBC) database, you can use **Seek** on tables in that database.</span></span>

## <a name="example"></a><span data-ttu-id="2c285-145">示例</span><span class="sxs-lookup"><span data-stu-id="2c285-145">Example</span></span>

<span data-ttu-id="2c285-146">以下示例通过允许用户根据 ID 编号搜索产品，来演示 **Seek** 方法。</span><span class="sxs-lookup"><span data-stu-id="2c285-146">This example demonstrates the **Seek** method by allowing the user to search for a product based on an ID number.</span></span>

```vb
    Sub SeekX() 
     
     Dim dbsNorthwind As Database 
     Dim rstProducts As Recordset2 
     Dim intFirst As Integer 
     Dim intLast As Integer 
     Dim strMessage As String 
     Dim strSeek As String 
     Dim varBookmark As Variant 
     
     Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
     ' You must open a table-type Recordset to use an index, 
     ' and hence the Seek method. 
     Set rstProducts = _ 
     dbsNorthwind.OpenRecordset("Products", dbOpenTable) 
     
     With rstProducts 
     ' Set the index. 
     .Index = "PrimaryKey" 
     
     ' Get the lowest and highest product IDs. 
     .MoveLast 
     intLast = !ProductID 
     .MoveFirst 
     intFirst = !ProductID 
     
     Do While True 
     ' Display current record information and ask user 
     ' for ID number. 
     strMessage = "Product ID: " & !ProductID & vbCr & _ 
     "Name: " & !ProductName & vbCr & vbCr & _ 
     "Enter a product ID between " & intFirst & _ 
     " and " & intLast & "." 
     strSeek = InputBox(strMessage) 
     
     If strSeek = "" Then Exit Do 
     
     ' Store current bookmark in case the Seek fails. 
     varBookmark = .Bookmark 
     
     .Seek "=", Val(strSeek) 
     
     ' Return to the current record if the Seek fails. 
     If .NoMatch Then 
     MsgBox "ID not found!" 
     .Bookmark = varBookmark 
     End If 
     Loop 
     
     .Close 
     End With 
     
     dbsNorthwind.Close 
     
    End Sub 
```

<br/>

<span data-ttu-id="2c285-p109">以下示例使用 **NoMatch** 属性确定 **Seek** 和 **FindFirst** 是否成功，如果未成功，则提供相应的反馈。若要使该过程运行，需要使用 SeekMatch 和 FindMatch 过程。</span><span class="sxs-lookup"><span data-stu-id="2c285-p109">This example uses the **NoMatch** property to determine whether a **Seek** and a **FindFirst** were successful, and if not, to give appropriate feedback. The SeekMatch and FindMatch procedures are required for this procedure to run.</span></span>

```vb
    Sub NoMatchX() 
     
     Dim dbsNorthwind As Database 
     Dim rstProducts As Recordset2 
     Dim rstCustomers As Recordset2 
     Dim strMessage As String 
     Dim strSeek As String 
     Dim strCountry As String 
     Dim varBookmark As Variant 
     
     Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
     ' Default is dbOpenTable; required if Index property will 
     ' be used. 
     Set rstProducts = dbsNorthwind.OpenRecordset("Products") 
     
     With rstProducts 
     .Index = "PrimaryKey" 
     
     Do While True 
     ' Show current record information; ask user for 
     ' input. 
     strMessage = "NoMatch with Seek method" & vbCr & _ 
     "Product ID: " & !ProductID & vbCr & _ 
     "Product Name: " & !ProductName & vbCr & _ 
     "NoMatch = " & .NoMatch & vbCr & vbCr & _ 
     "Enter a product ID." 
     strSeek = InputBox(strMessage) 
     If strSeek = "" Then Exit Do 
     
     ' Call procedure that seeks for a record based on 
     ' the ID number supplied by the user. 
     SeekMatch rstProducts, Val(strSeek) 
     Loop 
     
     .Close 
     End With 
     
     Set rstCustomers = dbsNorthwind.OpenRecordset( _ 
     "SELECT CompanyName, Country FROM Customers " & _ 
     "ORDER BY CompanyName", dbOpenSnapshot) 
     
     With rstCustomers 
     
     Do While True 
     ' Show current record information; ask user for 
     ' input. 
     strMessage = "NoMatch with FindFirst method" & _ 
     vbCr & "Customer Name: " & !CompanyName & _ 
     vbCr & "Country: " & !Country & vbCr & _ 
     "NoMatch = " & .NoMatch & vbCr & vbCr & _ 
     "Enter country on which to search." 
     strCountry = Trim(InputBox(strMessage)) 
     If strCountry = "" Then Exit Do 
     
     ' Call procedure that finds a record based on 
     ' the country name supplied by the user. 
     FindMatch rstCustomers, _ 
     "Country = '" & strCountry & "'" 
     Loop 
     
     .Close 
     End With 
     
     dbsNorthwind.Close 
     
    End Sub 
     
    Sub SeekMatch(rstTemp As Recordset, _ 
     intSeek As Integer) 
     
     Dim varBookmark As Variant 
     Dim strMessage As String 
     
     With rstTemp 
     ' Store current record location. 
     varBookmark = .Bookmark 
     .Seek "=", intSeek 
     
     ' If Seek method fails, notify user and return to the 
     ' last current record. 
     If .NoMatch Then 
     strMessage = _ 
     "Not found! Returning to current record." & _ 
     vbCr & vbCr & "NoMatch = " & .NoMatch 
     MsgBox strMessage 
     .Bookmark = varBookmark 
     End If 
     
     End With 
     
    End Sub 
     
    Sub FindMatch(rstTemp As Recordset, _ 
     strFind As String) 
     
     Dim varBookmark As Variant 
     Dim strMessage As String 
     
     With rstTemp 
     ' Store current record location. 
     varBookmark = .Bookmark 
     .FindFirst strFind 
     
     ' If Find method fails, notify user and return to the 
     ' last current record. 
     If .NoMatch Then 
     strMessage = _ 
     "Not found! Returning to current record." & _ 
     vbCr & vbCr & "NoMatch = " & .NoMatch 
     MsgBox strMessage 
     .Bookmark = varBookmark 
     End If 
     
     End With 
     
    End Sub
```
