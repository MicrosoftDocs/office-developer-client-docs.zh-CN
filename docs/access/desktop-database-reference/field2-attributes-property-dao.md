---
title: Field2 属性 (DAO)
TOCTitle: Attributes Property
ms:assetid: 08ae9b6b-21e4-9b7e-0852-cfc6639027a7
ms:mtpsurl: https://msdn.microsoft.com/library/Ff845025(v=office.15)
ms:contentKeyID: 48543102
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1052896
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: a655cfa5c6f0427b1a26a01f01e991564ab8e387
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32292886"
---
# <a name="field2attributes-property-dao"></a><span data-ttu-id="f1e55-102">Field2 属性 (DAO)</span><span class="sxs-lookup"><span data-stu-id="f1e55-102">Field2.Attributes property (DAO)</span></span>


<span data-ttu-id="f1e55-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="f1e55-103">**Applies to**: Access 2013, Office 2013</span></span>


<span data-ttu-id="f1e55-104">设置或返回一个值，该值指示 **Field2** 对象的一个或多个特征。</span><span class="sxs-lookup"><span data-stu-id="f1e55-104">Sets or returns a value that indicates one or more characteristics of a **Field2** object.</span></span> <span data-ttu-id="f1e55-105">**Long** 类型，可读写。</span><span class="sxs-lookup"><span data-stu-id="f1e55-105">Read/write **Long**.</span></span>

## <a name="syntax"></a><span data-ttu-id="f1e55-106">语法</span><span class="sxs-lookup"><span data-stu-id="f1e55-106">Syntax</span></span>

<span data-ttu-id="f1e55-107">*表达式*。诸如</span><span class="sxs-lookup"><span data-stu-id="f1e55-107">*expression* .Attributes</span></span>

<span data-ttu-id="f1e55-108">*表达式*一个代表**Field2**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="f1e55-108">*expression* A variable that represents a **Field2** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="f1e55-109">注解</span><span class="sxs-lookup"><span data-stu-id="f1e55-109">Remarks</span></span>

<span data-ttu-id="f1e55-110">此值指定 **Field2** 对象所代表的字段的特征，并且可以是这些常量的组合。</span><span class="sxs-lookup"><span data-stu-id="f1e55-110">The value specifies characteristics of the field represented by the **Field2** object and can be a combination of these constants.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="f1e55-111">常量</span><span class="sxs-lookup"><span data-stu-id="f1e55-111">Constant</span></span></p></th>
<th><p><span data-ttu-id="f1e55-112">说明</span><span class="sxs-lookup"><span data-stu-id="f1e55-112">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f1e55-113"><strong>dbAutoIncrField</strong></span><span class="sxs-lookup"><span data-stu-id="f1e55-113"><strong>dbAutoIncrField</strong></span></span></p></td>
<td><p><span data-ttu-id="f1e55-114">新记录的字段值将自动增加到无法更改的唯一 Long 类型整数（在 Microsoft Access 工作区中，只受 Microsoft Access 数据库引擎数据库表的支持）。</span><span class="sxs-lookup"><span data-stu-id="f1e55-114">The field value for new records is automatically incremented to a unique Long integer that can't be changed (in a Microsoft Access workspace, supported only for Microsoft Access database engine database tables).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f1e55-115"><strong>dbDescending</strong></span><span class="sxs-lookup"><span data-stu-id="f1e55-115"><strong>dbDescending</strong></span></span></p></td>
<td><p><span data-ttu-id="f1e55-116">字段按降序 (Z 到 A 或100到 0) 排序;此选项仅适用于<strong>Index</strong>对象的<strong>Fields</strong>集合中的<strong>Field2</strong>对象。</span><span class="sxs-lookup"><span data-stu-id="f1e55-116">The field is sorted in descending (Z to A or 100 to 0) order; this option applies only to a <strong>Field2</strong> object in a <strong>Fields</strong> collection of an <strong>Index</strong> object.</span></span> <span data-ttu-id="f1e55-117">如果省略此常量, 则将按升序 (A 到 Z 或0到 100) 顺序对字段进行排序。</span><span class="sxs-lookup"><span data-stu-id="f1e55-117">If you omit this constant, the field is sorted in ascending (A to Z or 0 to 100) order.</span></span> <span data-ttu-id="f1e55-118">这是<strong>Index</strong>和<strong>TableDef</strong>字段的默认值 (仅适用于 Microsoft Access 工作区)。。</span><span class="sxs-lookup"><span data-stu-id="f1e55-118">This is the default value for <strong>Index</strong> and <strong>TableDef</strong> fields (Microsoft Access workspaces only)..</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f1e55-119"><strong>dbFixedField</strong></span><span class="sxs-lookup"><span data-stu-id="f1e55-119"><strong>dbFixedField</strong></span></span></p></td>
<td><p><span data-ttu-id="f1e55-120">该字段大小是固定的（“数字”字段的默认值）。</span><span class="sxs-lookup"><span data-stu-id="f1e55-120">The field size is fixed (default for Numeric fields).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f1e55-121"><strong>dbHyperlinkField</strong></span><span class="sxs-lookup"><span data-stu-id="f1e55-121"><strong>dbHyperlinkField</strong></span></span></p></td>
<td><p><span data-ttu-id="f1e55-122">该字段包含超链接信息（仅适用于“备注”字段）。</span><span class="sxs-lookup"><span data-stu-id="f1e55-122">The field contains hyperlink information (Memo fields only).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f1e55-123"><strong>dbSystemField</strong></span><span class="sxs-lookup"><span data-stu-id="f1e55-123"><strong>dbSystemField</strong></span></span></p></td>
<td><p><span data-ttu-id="f1e55-124">该字段存储副本的复制信息；不能删除该字段类型（仅适用于 Microsoft Access 工作区）。</span><span class="sxs-lookup"><span data-stu-id="f1e55-124">The field stores replication information for replicas; you can't delete this type of field (Microsoft Access workspaces only).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f1e55-125"><strong>dbUpdatableField</strong></span><span class="sxs-lookup"><span data-stu-id="f1e55-125"><strong>dbUpdatableField</strong></span></span></p></td>
<td><p><span data-ttu-id="f1e55-126">可以更改该字段值。</span><span class="sxs-lookup"><span data-stu-id="f1e55-126">The field value can be changed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f1e55-127"><strong>dbVariableField</strong></span><span class="sxs-lookup"><span data-stu-id="f1e55-127"><strong>dbVariableField</strong></span></span></p></td>
<td><p><span data-ttu-id="f1e55-128">该字段大小可变（仅适用于“文本”字段）。</span><span class="sxs-lookup"><span data-stu-id="f1e55-128">The field size is variable (Text fields only).</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="f1e55-p103">对于尚未追加到集合中的对象，该属性是可读写的。对于已追加的 **Field2** 对象， **Attributes** 属性的可用性取决于包含 **Fields** 集合的对象。</span><span class="sxs-lookup"><span data-stu-id="f1e55-p103">For an object not yet appended to a collection, this property is read/write. For an appended **Field2** object, the availability of the **Attributes** property depends on the object that contains the **Fields** collection.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="f1e55-131">如果 Field 对象属于</span><span class="sxs-lookup"><span data-stu-id="f1e55-131">If the Field object belongs to an</span></span></p></th>
<th><p><span data-ttu-id="f1e55-132">则 Attributes</span><span class="sxs-lookup"><span data-stu-id="f1e55-132">Then Attributes is</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f1e55-133"><strong>Index</strong> 对象</span><span class="sxs-lookup"><span data-stu-id="f1e55-133"><strong>Index</strong> object</span></span></p></td>
<td><p><span data-ttu-id="f1e55-134">将 <strong>Index</strong> 所要追加到的 <strong>TableDef</strong> 对象追加到 <strong>Database</strong> 对象之前是可读写的；追加后，该属性是只读的。</span><span class="sxs-lookup"><span data-stu-id="f1e55-134">Read/write until the <strong>TableDef</strong> object that the <strong>Index</strong> object is appended to is appended to a <strong>Database</strong> object; then the property is read-only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f1e55-135"><strong>QueryDef</strong> 对象</span><span class="sxs-lookup"><span data-stu-id="f1e55-135"><strong>QueryDef</strong> object</span></span></p></td>
<td><p><span data-ttu-id="f1e55-136">只读</span><span class="sxs-lookup"><span data-stu-id="f1e55-136">Read-only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f1e55-137"><strong>Recordset</strong> 对象</span><span class="sxs-lookup"><span data-stu-id="f1e55-137"><strong>Recordset</strong> object</span></span></p></td>
<td><p><span data-ttu-id="f1e55-138">只读</span><span class="sxs-lookup"><span data-stu-id="f1e55-138">Read-only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f1e55-139"><strong>Relation</strong> 对象</span><span class="sxs-lookup"><span data-stu-id="f1e55-139"><strong>Relation</strong> object</span></span></p></td>
<td><p><span data-ttu-id="f1e55-140">不受支持</span><span class="sxs-lookup"><span data-stu-id="f1e55-140">Not supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f1e55-141"><strong>TableDef</strong> 对象</span><span class="sxs-lookup"><span data-stu-id="f1e55-141"><strong>TableDef</strong> object</span></span></p></td>
<td><p><span data-ttu-id="f1e55-142">读/写</span><span class="sxs-lookup"><span data-stu-id="f1e55-142">Read/write</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="f1e55-p104">设置多个属性时，可通过对相应的常量求和来组合这些属性。将忽略所有无效值，且不产生错误。</span><span class="sxs-lookup"><span data-stu-id="f1e55-p104">When you set multiple attributes, you can combine them by summing the appropriate constants. Any invalid values are ignored without producing an error.</span></span>

## <a name="example"></a><span data-ttu-id="f1e55-145">示例</span><span class="sxs-lookup"><span data-stu-id="f1e55-145">Example</span></span>

<span data-ttu-id="f1e55-146">以下示例显示 Northwind 数据库中的 **Field2**、 **Relation** 和 **TableDef** 对象的 **Attributes** 属性。</span><span class="sxs-lookup"><span data-stu-id="f1e55-146">This example displays the **Attributes** property for **Field2**, **Relation**, and **TableDef** objects in the Northwind database.</span></span>

```vb 
Sub AttributesX() 
 
 Dim dbsNorthwind As Database 
 Dim fldLoop As Field2 
 Dim relLoop As Relation 
 Dim tdfloop As TableDef 
 
 Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
 
 With dbsNorthwind 
 
 ' Display the attributes of a TableDef object's 
 ' fields. 
 Debug.Print "Attributes of fields in " & _ 
 .TableDefs(0).Name & " table:" 
 For Each fldLoop In .TableDefs(0).Fields 
 Debug.Print " " & fldLoop.Name & " = " & _ 
 fldLoop.Attributes 
 Next fldLoop 
 
 ' Display the attributes of the Northwind database's 
 ' relations. 
 Debug.Print "Attributes of relations in " & _ 
 .Name & ":" 
 For Each relLoop In .Relations 
 Debug.Print " " & relLoop.Name & " = " & _ 
 relLoop.Attributes 
 Next relLoop 
 
 ' Display the attributes of the Northwind database's 
 ' tables. 
 Debug.Print "Attributes of tables in " & .Name & ":" 
 For Each tdfloop In .TableDefs 
 Debug.Print " " & tdfloop.Name & " = " & _ 
 tdfloop.Attributes 
 Next tdfloop 
 
 .Close 
 End With 
 
End Sub 
 
```

