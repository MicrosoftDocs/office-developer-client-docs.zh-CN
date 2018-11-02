---
title: Database.CreateTableDef 方法 (DAO)
TOCTitle: CreateTableDef Method
ms:assetid: d919b44e-ffae-dc4a-f1cc-d01df49987a3
ms:mtpsurl: https://msdn.microsoft.com/library/Ff835094(v=office.15)
ms:contentKeyID: 48548046
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1052968
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 59e5cc34eb6325b6151ab053f9c870a999bd94aa
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25927891"
---
# <a name="databasecreatetabledef-method-dao"></a><span data-ttu-id="72d42-102">Database.CreateTableDef 方法 (DAO)</span><span class="sxs-lookup"><span data-stu-id="72d42-102">Database.CreateTableDef method (DAO)</span></span>

<span data-ttu-id="72d42-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="72d42-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="72d42-p101">创建一个新的 **[TableDef](tabledef-object-dao.md)** 对象（仅适用于 Microsoft Access 工作区）。</span><span class="sxs-lookup"><span data-stu-id="72d42-p101">Creates a new **[TableDef](tabledef-object-dao.md)** object (Microsoft Access workspaces only). .</span></span>

## <a name="syntax"></a><span data-ttu-id="72d42-106">语法</span><span class="sxs-lookup"><span data-stu-id="72d42-106">Syntax</span></span>

<span data-ttu-id="72d42-107">*表达式*。CreateTableDef （***名称***、***属性***、 ***SourceTableName***、***连接***）</span><span class="sxs-lookup"><span data-stu-id="72d42-107">*expression* .CreateTableDef(***Name***, ***Attributes***, ***SourceTableName***, ***Connect***)</span></span>

<span data-ttu-id="72d42-108">*表达式*一个代表**Database**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="72d42-108">*expression* A variable that represents a **Database** object.</span></span>

### <a name="parameters"></a><span data-ttu-id="72d42-109">参数</span><span class="sxs-lookup"><span data-stu-id="72d42-109">Parameters</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="72d42-110">名称</span><span class="sxs-lookup"><span data-stu-id="72d42-110">Name</span></span></p></th>
<th><p><span data-ttu-id="72d42-111">必需/可选</span><span class="sxs-lookup"><span data-stu-id="72d42-111">Required/Optional</span></span></p></th>
<th><p><span data-ttu-id="72d42-112">数据类型</span><span class="sxs-lookup"><span data-stu-id="72d42-112">Data Type</span></span></p></th>
<th><p><span data-ttu-id="72d42-113">说明</span><span class="sxs-lookup"><span data-stu-id="72d42-113">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="72d42-114">名称</span><span class="sxs-lookup"><span data-stu-id="72d42-114">Name</span></span></p></td>
<td><p><span data-ttu-id="72d42-115">可选</span><span class="sxs-lookup"><span data-stu-id="72d42-115">Optional</span></span></p></td>
<td><p><span data-ttu-id="72d42-116"><strong>Variant</strong></span><span class="sxs-lookup"><span data-stu-id="72d42-116"><strong>Variant</strong></span></span></p></td>
<td><p><span data-ttu-id="72d42-p102">一个 <strong>Variant</strong>（<strong>String</strong> 子类型），用于对新的 <strong>TableDef</strong> 对象进行唯一命名。有关有效 <strong>TableDef</strong> 名称的详细信息，请参阅 <strong><a href="tabledef-name-property-dao.md">Name</a></strong> 属性。</span><span class="sxs-lookup"><span data-stu-id="72d42-p102">A <strong>Variant</strong> (<strong>String</strong> subtype) that uniquely names the new <strong>TableDef</strong> object. See the <strong><a href="tabledef-name-property-dao.md">Name</a></strong> property for details on valid <strong>TableDef</strong> names.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="72d42-119">Attributes</span><span class="sxs-lookup"><span data-stu-id="72d42-119">Attributes</span></span></p></td>
<td><p><span data-ttu-id="72d42-120">可选</span><span class="sxs-lookup"><span data-stu-id="72d42-120">Optional</span></span></p></td>
<td><p><span data-ttu-id="72d42-121"><strong>Variant</strong></span><span class="sxs-lookup"><span data-stu-id="72d42-121"><strong>Variant</strong></span></span></p></td>
<td><p><span data-ttu-id="72d42-p103">一个常量或常量组合，指示新的 <strong>TableDef</strong> 对象的一个或多个特征。有关详细信息，请参阅 <strong><a href="tabledef-attributes-property-dao.md">Attributes</a></strong> 属性。</span><span class="sxs-lookup"><span data-stu-id="72d42-p103">A constant or combination of constants that indicates one or more characteristics of the new <strong>TableDef</strong> object. See the <strong><a href="tabledef-attributes-property-dao.md">Attributes</a></strong> property for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="72d42-124">SourceTableName</span><span class="sxs-lookup"><span data-stu-id="72d42-124">SourceTableName</span></span></p></td>
<td><p><span data-ttu-id="72d42-125">可选</span><span class="sxs-lookup"><span data-stu-id="72d42-125">Optional</span></span></p></td>
<td><p><span data-ttu-id="72d42-126"><strong>Variant</strong></span><span class="sxs-lookup"><span data-stu-id="72d42-126"><strong>Variant</strong></span></span></p></td>
<td><p><span data-ttu-id="72d42-p104">一个 <strong>Variant</strong>（<strong>String</strong> 子类型），包含作为数据原始来源的外部数据库中的表名。source 字符串成为新的 <strong>TableDef</strong> 对象的 <strong><a href="tabledef-sourcetablename-property-dao.md">SourceTableName</a></strong> 属性设置。</span><span class="sxs-lookup"><span data-stu-id="72d42-p104">A <strong>Variant</strong> (<strong>String</strong> subtype) containing the name of a table in an external database that is the original source of the data. The source string becomes the <strong><a href="tabledef-sourcetablename-property-dao.md">SourceTableName</a></strong> property setting of the new <strong>TableDef</strong> object.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="72d42-129">在浏览器中</span><span class="sxs-lookup"><span data-stu-id="72d42-129">Connect</span></span></p></td>
<td><p><span data-ttu-id="72d42-130">可选</span><span class="sxs-lookup"><span data-stu-id="72d42-130">Optional</span></span></p></td>
<td><p><span data-ttu-id="72d42-131"><strong>Variant</strong></span><span class="sxs-lookup"><span data-stu-id="72d42-131"><strong>Variant</strong></span></span></p></td>
<td><p><span data-ttu-id="72d42-p105">一个 <strong>Variant</strong>（<strong>String</strong> 子类型），包含有关打开数据库（在传递查询或链接表中使用的数据库）的源的信息。有关有效的连接字符串的详细信息，请参阅 <strong><a href="tabledef-connect-property-dao.md">Connect</a></strong> 属性。</span><span class="sxs-lookup"><span data-stu-id="72d42-p105">A <strong>Variant</strong> (<strong>String</strong> subtype) containing information about the source of an open database, a database used in a pass-through query, or a linked table. See the <strong><a href="tabledef-connect-property-dao.md">Connect</a></strong> property for more information about valid connection strings.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="return-value"></a><span data-ttu-id="72d42-134">返回值</span><span class="sxs-lookup"><span data-stu-id="72d42-134">Return value</span></span>

<span data-ttu-id="72d42-135">TableDef</span><span class="sxs-lookup"><span data-stu-id="72d42-135">TableDef</span></span>

## <a name="remarks"></a><span data-ttu-id="72d42-136">注解</span><span class="sxs-lookup"><span data-stu-id="72d42-136">Remarks</span></span>

<span data-ttu-id="72d42-p106">如果使用 **CreateTableDef** 方法时省略了一个或多个可选部分，则可以在将新对象追加到集合之前，使用适当的赋值语句设置或重置相应的属性。追加对象后，可以改动此对象的某些（但不是所有）属性。有关详细信息，请参阅各个属性主题。</span><span class="sxs-lookup"><span data-stu-id="72d42-p106">If you omit one or more of the optional parts when you use the **CreateTableDef** method, you can use an appropriate assignment statement to set or reset the corresponding property before you append the new object to a collection. After you append the object, you can alter some but not all of its properties. See the individual property topics for more details.</span></span>

<span data-ttu-id="72d42-140">如果名称引用已经是集合成员的对象或要追加的**TableDef**或**[Field](field-object-dao.md)** 对象中指定无效的属性，当您使用**[Append](tabledefs-append-method-dao.md)** 方法时，发生此事件运行时错误。</span><span class="sxs-lookup"><span data-stu-id="72d42-140">If name refers to an object that is already a member of the collection, or you specify an invalid property in the **TableDef** or **[Field](field-object-dao.md)** object you're appending, a run-time error occurs when you use the **[Append](tabledefs-append-method-dao.md)** method.</span></span> <span data-ttu-id="72d42-141">另外，除非为 **TableDef** 对象定义了至少一个 **Field**，否则不能将 **TableDef** 对象追加到 **TableDefs** 集合。</span><span class="sxs-lookup"><span data-stu-id="72d42-141">Also, you can't append a **TableDef** object to the **TableDefs** collection until you define at least one **Field** for the **TableDef** object.</span></span>

<span data-ttu-id="72d42-142">若要从 [**TableDefs**](tabledefs-collection-dao.md) 集合中删除 **TableDef** 对象，请对集合使用 **[Delete](tabledefs-delete-method-dao.md)** 方法。</span><span class="sxs-lookup"><span data-stu-id="72d42-142">To remove a **TableDef** object from the **[TableDefs](tabledefs-collection-dao.md)** collection, use the **[Delete](tabledefs-delete-method-dao.md)** method on the collection.</span></span>

## <a name="example"></a><span data-ttu-id="72d42-143">示例</span><span class="sxs-lookup"><span data-stu-id="72d42-143">Example</span></span>

<span data-ttu-id="72d42-144">以下示例在 Northwind 数据库中创建一个新的 **TableDef** 对象。</span><span class="sxs-lookup"><span data-stu-id="72d42-144">This example creates a new **TableDef** object in the Northwind database.</span></span>

```vb
    Sub CreateTableDefX() 
     
     Dim dbsNorthwind As Database 
     Dim tdfNew As TableDef 
     Dim prpLoop As Property 
     
     Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
     
     ' Create a new TableDef object. 
     Set tdfNew = dbsNorthwind.CreateTableDef("Contacts") 
     
     With tdfNew 
     ' Create fields and append them to the new TableDef 
     ' object. This must be done before appending the 
     ' TableDef object to the TableDefs collection of the 
     ' Northwind database. 
     .Fields.Append .CreateField("FirstName", dbText) 
     .Fields.Append .CreateField("LastName", dbText) 
     .Fields.Append .CreateField("Phone", dbText) 
     .Fields.Append .CreateField("Notes", dbMemo) 
     
     Debug.Print "Properties of new TableDef object " & _ 
     "before appending to collection:" 
     
     ' Enumerate Properties collection of new TableDef 
     ' object. 
     For Each prpLoop In .Properties 
     On Error Resume Next 
     If prpLoop <> "" Then Debug.Print " " & _ 
     prpLoop.Name & " = " & prpLoop 
     On Error GoTo 0 
     Next prpLoop 
     
     ' Append the new TableDef object to the Northwind 
     ' database. 
     dbsNorthwind.TableDefs.Append tdfNew 
     
     Debug.Print "Properties of new TableDef object " & _ 
     "after appending to collection:" 
     
     ' Enumerate Properties collection of new TableDef 
     ' object. 
     For Each prpLoop In .Properties 
     On Error Resume Next 
     If prpLoop <> "" Then Debug.Print " " & _ 
     prpLoop.Name & " = " & prpLoop 
     On Error GoTo 0 
     Next prpLoop 
     
     End With 
     
     ' Delete new TableDef object since this is a 
     ' demonstration. 
     dbsNorthwind.TableDefs.Delete "Contacts" 
     
     dbsNorthwind.Close 
     
    End Sub 
```

<br/>

<span data-ttu-id="72d42-p108">以下示例使用 **CreateTableDef** 和 **FillCache** 方法以及 **CacheSize**、 **CacheStart** 和 **SourceTableName** 属性两次枚举链接表中的记录，再使用存有 50 条记录的缓存两次枚举这些记录，然后通过链接表显示未缓存运行和缓存运行的性能统计。</span><span class="sxs-lookup"><span data-stu-id="72d42-p108">This example uses the **CreateTableDef** and **FillCache** methods and the **CacheSize**, **CacheStart** and **SourceTableName** properties to enumerate the records in a linked table twice. Then it enumerates the records twice with a 50-record cache. The example then displays the performance statistics for the uncached and cached runs through the linked table.</span></span>

```vb
    Sub ClientServerX3() 
     
     Dim dbsCurrent As Database 
     Dim tdfRoyalties As TableDef 
     Dim rstRemote As Recordset 
     Dim sngStart As Single 
     Dim sngEnd As Single 
     Dim sngNoCache As Single 
     Dim sngCache As Single 
     Dim intLoop As Integer 
     Dim strTemp As String 
     Dim intRecords As Integer 
     
     ' Open a database to which a linked table can be 
     ' appended. 
     Set dbsCurrent = OpenDatabase("DB1.mdb") 
     
     ' Create a linked table that connects to a Microsoft SQL 
     ' Server database. 
     Set tdfRoyalties = _ 
     dbsCurrent.CreateTableDef("Royalties") 
     ' Note: The DSN referenced below must be set to 
     ' use Microsoft Windows NT Authentication Mode to 
     ' authorize user access to the Microsoft SQL Server. 
     tdfRoyalties.Connect = _ 
     "ODBC;DATABASE=pubs;DSN=Publishers" 
     tdfRoyalties.SourceTableName = "roysched" 
     dbsCurrent.TableDefs.Append tdfRoyalties 
     Set rstRemote = _ 
     dbsCurrent.OpenRecordset("Royalties") 
     
     With rstRemote 
     ' Enumerate the Recordset object twice and record 
     ' the elapsed time. 
     sngStart = Timer 
     
     For intLoop = 1 To 2 
     .MoveFirst 
     Do While Not .EOF 
     ' Execute a simple operation for the 
     ' performance test. 
     strTemp = !title_id 
     .MoveNext 
     Loop 
     Next intLoop 
     
     sngEnd = Timer 
     sngNoCache = sngEnd - sngStart 
     
     ' Cache the first 50 records. 
     .MoveFirst 
     .CacheSize = 50 
     .FillCache 
     sngStart = Timer 
     
     ' Enumerate the Recordset object twice and record 
     ' the elapsed time. 
     For intLoop = 1 To 2 
     intRecords = 0 
     .MoveFirst 
     Do While Not .EOF 
     ' Execute a simple operation for the 
     ' performance test. 
     strTemp = !title_id 
     ' Count the records. If the end of the 
     ' cache is reached, reset the cache to the 
     ' next 50 records. 
     intRecords = intRecords + 1 
     .MoveNext 
     If intRecords Mod 50 = 0 Then 
     .CacheStart = .Bookmark 
     .FillCache 
     End If 
     Loop 
     Next intLoop 
     
     sngEnd = Timer 
     sngCache = sngEnd - sngStart 
     
     ' Display performance results. 
     MsgBox "Caching Performance Results:" & vbCr & _ 
     " No cache: " & Format(sngNoCache, _ 
     "##0.000") & " seconds" & vbCr & _ 
     " 50-record cache: " & Format(sngCache, _ 
     "##0.000") & " seconds" 
     .Close 
     End With 
     
     ' Delete linked table because this is a demonstration. 
     dbsCurrent.TableDefs.Delete tdfRoyalties.Name 
     dbsCurrent.Close 
     
    End Sub
```
