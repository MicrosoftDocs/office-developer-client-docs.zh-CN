---
title: Database.CreateRelation 方法 (DAO)
TOCTitle: CreateRelation Method
ms:assetid: e240c7e3-c293-5e19-afcc-34d9a5549c64
ms:mtpsurl: https://msdn.microsoft.com/library/Ff835692(v=office.15)
ms:contentKeyID: 48548279
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1052969
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: 365835bc579a431d34b65cd27ed4de4e12bca309
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28716878"
---
# <a name="databasecreaterelation-method-dao"></a><span data-ttu-id="09d97-102">Database.CreateRelation 方法 (DAO)</span><span class="sxs-lookup"><span data-stu-id="09d97-102">Database.CreateRelation method (DAO)</span></span>

<span data-ttu-id="09d97-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="09d97-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="09d97-p101">创建一个新的 **[Relation](relation-object-dao.md)** 对象（仅适用于 Microsoft Access 工作区）。</span><span class="sxs-lookup"><span data-stu-id="09d97-p101">Creates a new **[Relation](relation-object-dao.md)** object (Microsoft Access workspaces only). .</span></span>

## <a name="syntax"></a><span data-ttu-id="09d97-106">语法</span><span class="sxs-lookup"><span data-stu-id="09d97-106">Syntax</span></span>

<span data-ttu-id="09d97-107">*表达式*。CreateRelation （***名称***、***表***、 ***ForeignTable***、***属性***）</span><span class="sxs-lookup"><span data-stu-id="09d97-107">*expression* .CreateRelation(***Name***, ***Table***, ***ForeignTable***, ***Attributes***)</span></span>

<span data-ttu-id="09d97-108">*表达式*一个代表**Database**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="09d97-108">*expression* A variable that represents a **Database** object.</span></span>

## <a name="parameters"></a><span data-ttu-id="09d97-109">Parameters</span><span class="sxs-lookup"><span data-stu-id="09d97-109">Parameters</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="09d97-110">Name</span><span class="sxs-lookup"><span data-stu-id="09d97-110">Name</span></span></p></th>
<th><p><span data-ttu-id="09d97-111">必需/可选</span><span class="sxs-lookup"><span data-stu-id="09d97-111">Required/optional</span></span></p></th>
<th><p><span data-ttu-id="09d97-112">数据类型</span><span class="sxs-lookup"><span data-stu-id="09d97-112">Data type</span></span></p></th>
<th><p><span data-ttu-id="09d97-113">说明</span><span class="sxs-lookup"><span data-stu-id="09d97-113">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="09d97-114"><em>Name</em></span><span class="sxs-lookup"><span data-stu-id="09d97-114"><em>Name</em></span></span></p></td>
<td><p><span data-ttu-id="09d97-115">可选</span><span class="sxs-lookup"><span data-stu-id="09d97-115">Optional</span></span></p></td>
<td><p><span data-ttu-id="09d97-116"><strong>Variant</strong></span><span class="sxs-lookup"><span data-stu-id="09d97-116"><strong>Variant</strong></span></span></p></td>
<td><p><span data-ttu-id="09d97-p102">一个 <strong>Variant</strong>（<strong>String</strong> 子类型），用于对新的 <strong>Relation</strong> 对象进行唯一命名。有关有效 <strong>Relation</strong> 名称的详细信息，请参阅 <strong><a href="connection-name-property-dao.md">Name</a></strong> 属性。</span><span class="sxs-lookup"><span data-stu-id="09d97-p102">A <strong>Variant</strong> (<strong>String</strong> subtype) that uniquely names the new <strong>Relation</strong> object. See the <strong><a href="connection-name-property-dao.md">Name</a></strong> property for details on valid <strong>Relation</strong> names.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="09d97-119"><em>Table</em></span><span class="sxs-lookup"><span data-stu-id="09d97-119"><em>Table</em></span></span></p></td>
<td><p><span data-ttu-id="09d97-120">可选</span><span class="sxs-lookup"><span data-stu-id="09d97-120">Optional</span></span></p></td>
<td><p><span data-ttu-id="09d97-121"><strong>Variant</strong></span><span class="sxs-lookup"><span data-stu-id="09d97-121"><strong>Variant</strong></span></span></p></td>
<td><p><span data-ttu-id="09d97-p103">一个 <strong>Variant</strong>（<strong>String</strong> 子类型），用于命名关系中的主表。如果在追加 <strong>Relation</strong> 对象之前该表不存在，将发生运行时错误。</span><span class="sxs-lookup"><span data-stu-id="09d97-p103">A <strong>Variant</strong> (<strong>String</strong> subtype) that names the primary table in the relation. If the table doesn't exist before you append the <strong>Relation</strong> object, a run-time error occurs.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="09d97-124"><em>ForeignTable</em></span><span class="sxs-lookup"><span data-stu-id="09d97-124"><em>ForeignTable</em></span></span></p></td>
<td><p><span data-ttu-id="09d97-125">可选</span><span class="sxs-lookup"><span data-stu-id="09d97-125">Optional</span></span></p></td>
<td><p><span data-ttu-id="09d97-126"><strong>Variant</strong></span><span class="sxs-lookup"><span data-stu-id="09d97-126"><strong>Variant</strong></span></span></p></td>
<td><p><span data-ttu-id="09d97-p104">一个 <strong>Variant</strong>（<strong>String</strong> 子类型），用于命名关系中的外表。如果在追加 <strong>Relation</strong> 对象之前该表不存在，将发生运行时错误。</span><span class="sxs-lookup"><span data-stu-id="09d97-p104">A <strong>Variant</strong> (<strong>String</strong> subtype) that names the foreign table in the relation. If the table doesn't exist before you append the <strong>Relation</strong> object, a run-time error occurs.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="09d97-129"><em>Attributes</em></span><span class="sxs-lookup"><span data-stu-id="09d97-129"><em>Attributes</em></span></span></p></td>
<td><p><span data-ttu-id="09d97-130">可选</span><span class="sxs-lookup"><span data-stu-id="09d97-130">Optional</span></span></p></td>
<td><p><span data-ttu-id="09d97-131"><strong>Variant</strong></span><span class="sxs-lookup"><span data-stu-id="09d97-131"><strong>Variant</strong></span></span></p></td>
<td><p><span data-ttu-id="09d97-p105">一个常量或常量组合，包含有关关系类型的信息。有关详细信息，请参阅 <strong><a href="field-attributes-property-dao.md">Attributes</a></strong> 属性。</span><span class="sxs-lookup"><span data-stu-id="09d97-p105">A constant or combination of constants that contains information about the relationship type. See the <strong><a href="field-attributes-property-dao.md">Attributes</a></strong> property for details.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="return-value"></a><span data-ttu-id="09d97-134">返回值</span><span class="sxs-lookup"><span data-stu-id="09d97-134">Return value</span></span>

<span data-ttu-id="09d97-135">Relation</span><span class="sxs-lookup"><span data-stu-id="09d97-135">Relation</span></span>

## <a name="remarks"></a><span data-ttu-id="09d97-136">注解</span><span class="sxs-lookup"><span data-stu-id="09d97-136">Remarks</span></span>

<span data-ttu-id="09d97-p106">**Relation** 对象向 Microsoft Access 数据库引擎提供有关两个 **[TableDef](tabledef-object-dao.md)** 对象或 **[QueryDef](querydef-object-dao.md)** 对象中的字段之间的关系的信息。可以通过使用 **Attributes** 属性来实现参照完整性。</span><span class="sxs-lookup"><span data-stu-id="09d97-p106">The **Relation** object provides information to the Microsoft Access database engine about the relationship between fields in two **[TableDef](tabledef-object-dao.md)** or **[QueryDef](querydef-object-dao.md)** objects. You can implement referential integrity by using the **Attributes** property.</span></span>

<span data-ttu-id="09d97-p107">如果使用 **CreateRelation** 方法时省略了一个或多个可选部分，则可以在将新对象追加到集合之前，使用适当的赋值语句设置或重置相应的属性。追加对象后，不能改动此对象的任何属性设置。有关详细信息，请参阅各个属性主题。</span><span class="sxs-lookup"><span data-stu-id="09d97-p107">If you omit one or more of the optional parts when you use the **CreateRelation** method, you can use an appropriate assignment statement to set or reset the corresponding property before you append the new object to a collection. After you append the object, you can't alter any of its property settings. See the individual property topics for more details.</span></span>

<span data-ttu-id="09d97-142">对 [Relation](fields-append-method-dao.md) 对象使用 \*\*\*\*Append\*\*\*\* 方法之前，必须追加相应的 **[Field](field-object-dao.md)** 对象以定义主键和外键关系表。</span><span class="sxs-lookup"><span data-stu-id="09d97-142">Before you can use the **[Append](fields-append-method-dao.md)** method on a **Relation** object, you must append the appropriate **[Field](field-object-dao.md)** objects to define the primary and foreign key relationship tables.</span></span>

<span data-ttu-id="09d97-143">如果 name 引用已经是集合成员的对象或提供的从属**Fields**集合中的**Field**对象名称均无效，当您使用**Append**方法时，发生此事件运行时错误。</span><span class="sxs-lookup"><span data-stu-id="09d97-143">If name refers to an object that is already a member of the collection or if the **Field** object names provided in the subordinate **Fields** collection are invalid, a run-time error occurs when you use the **Append** method.</span></span>

<span data-ttu-id="09d97-144">不能在复制表和本地表之间建立或维持关系。</span><span class="sxs-lookup"><span data-stu-id="09d97-144">You can't establish or maintain a relationship between a replicated table and a local table.</span></span>

<span data-ttu-id="09d97-145">若要从 [**Relations**](relations-collection-dao.md) 集合中删除 **Relation** 对象，请对集合使用 **[Delete](fields-delete-method-dao.md)** 方法。</span><span class="sxs-lookup"><span data-stu-id="09d97-145">To remove a **Relation** object from the **[Relations](relations-collection-dao.md)** collection, use the **[Delete](fields-delete-method-dao.md)** method on the collection.</span></span>

## <a name="example"></a><span data-ttu-id="09d97-146">示例</span><span class="sxs-lookup"><span data-stu-id="09d97-146">Example</span></span>

<span data-ttu-id="09d97-p108">以下示例使用 **CreateRelation** 方法在 Employees **TableDef** 和名为 Departments 的新的 **TableDef** 之间创建一个 **Relation**。该示例还演示创建新的 **Relation** 将如何同时在外部表中创建任何需要的 **Indexes**（Employees 表中的 DepartmentsEmployees 索引）。</span><span class="sxs-lookup"><span data-stu-id="09d97-p108">This example uses the **CreateRelation** method to create a **Relation** between the Employees **TableDef** and a new **TableDef** called Departments. This example also demonstrates how creating a new **Relation** will also create any necessary **Indexes** in the foreign table (the DepartmentsEmployees Index in the Employees table).</span></span>

```vb
    Sub CreateRelationX() 
     
     Dim dbsNorthwind As Database 
     Dim tdfEmployees As TableDef 
     Dim tdfNew As TableDef 
     Dim idxNew As Index 
     Dim relNew As Relation 
     Dim idxLoop As Index 
     
     Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
     
     With dbsNorthwind 
     ' Add new field to Employees table. 
     Set tdfEmployees = .TableDefs!Employees 
     tdfEmployees.Fields.Append _ 
     tdfEmployees.CreateField("DeptID", dbInteger, 2) 
     
     ' Create new Departments table. 
     Set tdfNew = .CreateTableDef("Departments") 
     
     With tdfNew 
     ' Create and append Field objects to Fields 
     ' collection of the new TableDef object. 
     .Fields.Append .CreateField("DeptID", dbInteger, 2) 
     .Fields.Append .CreateField("DeptName", dbText, 20) 
     
     ' Create Index object for Departments table. 
     Set idxNew = .CreateIndex("DeptIDIndex") 
     ' Create and append Field object to Fields 
     ' collection of the new Index object. 
     idxNew.Fields.Append idxNew.CreateField("DeptID") 
     ' The index in the primary table must be Unique in 
     ' order to be part of a Relation. 
     idxNew.Unique = True 
     .Indexes.Append idxNew 
     End With 
     
     .TableDefs.Append tdfNew 
     
     ' Create EmployeesDepartments Relation object, using 
     ' the names of the two tables in the relation. 
     Set relNew = .CreateRelation("EmployeesDepartments", _ 
     tdfNew.Name, tdfEmployees.Name, _ 
     dbRelationUpdateCascade) 
     
     ' Create Field object for the Fields collection of the 
     ' new Relation object. Set the Name and ForeignName 
     ' properties based on the fields to be used for the 
     ' relation. 
     relNew.Fields.Append relNew.CreateField("DeptID") 
     relNew.Fields!DeptID.ForeignName = "DeptID" 
     .Relations.Append relNew 
     
     ' Print report. 
     Debug.Print "Properties of " & relNew.Name & _ 
     " Relation" 
     Debug.Print " Table = " & relNew.Table 
     Debug.Print " ForeignTable = " & _ 
     relNew.ForeignTable 
     Debug.Print "Fields of " & relNew.Name & " Relation" 
     
     With relNew.Fields!DeptID 
     Debug.Print " " & .Name 
     Debug.Print " Name = " & .Name 
     Debug.Print " ForeignName = " & .ForeignName 
     End With 
     
     Debug.Print "Indexes in " & tdfEmployees.Name & _ 
     " TableDef" 
     For Each idxLoop In tdfEmployees.Indexes 
     Debug.Print " " & idxLoop.Name & _ 
     ", Foreign = " & idxLoop.Foreign 
     Next idxLoop 
     
     ' Delete new objects because this is a demonstration. 
     .Relations.Delete relNew.Name 
     .TableDefs.Delete tdfNew.Name 
     tdfEmployees.Fields.Delete "DeptID" 
     .Close 
     End With 
     
    End Sub
```
