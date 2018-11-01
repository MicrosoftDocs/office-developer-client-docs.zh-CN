---
title: Field.DefaultValue Property (DAO)
TOCTitle: DefaultValue Property
ms:assetid: 8a1c558b-c8f6-757d-c595-4e50b9b6ae3f
ms:mtpsurl: https://msdn.microsoft.com/library/Ff197092(v=office.15)
ms:contentKeyID: 48546185
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: c4a2710c714f22ad7ec1a27dc3e4750f56d6fac5
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/01/2018
ms.locfileid: "25891091"
---
# <a name="fielddefaultvalue-property-dao"></a><span data-ttu-id="5818c-102">Field.DefaultValue Property (DAO)</span><span class="sxs-lookup"><span data-stu-id="5818c-102">Field.DefaultValue Property (DAO)</span></span>


<span data-ttu-id="5818c-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="5818c-103">**Applies to**: Access 2013, Office 2013</span></span>


<span data-ttu-id="5818c-p101">设置或返回 **[Field](field-object-dao.md)** 对象的默认值。对于尚未追加到 [**Fields**](fields-collection-dao.md) 集合的 **Field** 对象，该属性是可读写的（仅适用于 Microsoft Access 工作区）。</span><span class="sxs-lookup"><span data-stu-id="5818c-p101">Sets or returns the default value of a **[Field](field-object-dao.md)** object. For a **Field** object not yet appended to the **[Fields](fields-collection-dao.md)** collection, this property is read/write (Microsoft Access workspaces only).</span></span>

## <a name="syntax"></a><span data-ttu-id="5818c-106">语法</span><span class="sxs-lookup"><span data-stu-id="5818c-106">Syntax</span></span>

<span data-ttu-id="5818c-107">*表达式*。DefaultValue</span><span class="sxs-lookup"><span data-stu-id="5818c-107">*expression* .DefaultValue</span></span>

<span data-ttu-id="5818c-108">*表达式*一个代表**Field**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="5818c-108">*expression* A variable that represents a **Field** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="5818c-109">注解</span><span class="sxs-lookup"><span data-stu-id="5818c-109">Remarks</span></span>

<span data-ttu-id="5818c-p102">设置值或返回值是一个最多包含 255 个字符的 **String** 数据类型。它可以是文本，也可以是表达式。如果该属性设置是表达式，则不能包含用户定义的函数、Microsoft Access 数据库引擎 SQL 聚合函数，或指向查询、窗体或其他 **Field** 对象的引用。</span><span class="sxs-lookup"><span data-stu-id="5818c-p102">The setting or return value is a **String** data type that can contain a maximum of 255 characters. It can be either text or an expression. If the property setting is an expression, it can't contain user-defined functions, Microsoft Access database engine SQL aggregate functions, or references to queries, forms, or other **Field** objects.</span></span>


> [!NOTE]
> <span data-ttu-id="5818c-p103">[!注释] 还可以将 \*\*\*\*TableDef\*\*\*\* 对象上的 [Field](tabledef-object-dao.md) 对象的 DefaultValue 属性设置为称作"GenUniqueID( )"的特殊值。这样，只要添加或创建了新记录，就会将一个随机数分配给该字段，因而可以给每条记录指定一个唯一标识符。该字段的 [Type](field-type-property-dao.md) 属性必须为 **Long** 类型。</span><span class="sxs-lookup"><span data-stu-id="5818c-p103">You can also set the **DefaultValue** property of a **Field** object on a [TableDef](tabledef-object-dao.md) object to a special value called "GenUniqueID( )". This causes a random number to be assigned to this field whenever a new record is added or created, thereby giving each record a unique identifier. The field's [Type](field-type-property-dao.md) property must be **Long**.</span></span>


<span data-ttu-id="5818c-116">**DefaultValue** 属性的可用性取决于包含 **Fields** 集合的对象，如下表所示。</span><span class="sxs-lookup"><span data-stu-id="5818c-116">The availability of the **DefaultValue** property depends on the object that contains the **Fields** collection, as shown in the following table.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="5818c-117">如果 Fields 集合属于</span><span class="sxs-lookup"><span data-stu-id="5818c-117">If the Fields collection belongs to an</span></span></p></th>
<th><p><span data-ttu-id="5818c-118">则 DefaultValue</span><span class="sxs-lookup"><span data-stu-id="5818c-118">Then DefaultValue is</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5818c-119">Index 对象</span><span class="sxs-lookup"><span data-stu-id="5818c-119">Index object</span></span></p></td>
<td><p><span data-ttu-id="5818c-120">不受支持</span><span class="sxs-lookup"><span data-stu-id="5818c-120">Not supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5818c-121">QueryDef 对象</span><span class="sxs-lookup"><span data-stu-id="5818c-121">QueryDef object</span></span></p></td>
<td><p><span data-ttu-id="5818c-122">只读</span><span class="sxs-lookup"><span data-stu-id="5818c-122">Read-only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5818c-123">Recordset 对象</span><span class="sxs-lookup"><span data-stu-id="5818c-123">Recordset object</span></span></p></td>
<td><p><span data-ttu-id="5818c-124">只读</span><span class="sxs-lookup"><span data-stu-id="5818c-124">Read-only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5818c-125">Relation 对象</span><span class="sxs-lookup"><span data-stu-id="5818c-125">Relation object</span></span></p></td>
<td><p><span data-ttu-id="5818c-126">不受支持</span><span class="sxs-lookup"><span data-stu-id="5818c-126">Not supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5818c-127">TableDef 对象</span><span class="sxs-lookup"><span data-stu-id="5818c-127">TableDef object</span></span></p></td>
<td><p><span data-ttu-id="5818c-128">可读写</span><span class="sxs-lookup"><span data-stu-id="5818c-128">Read/write</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="5818c-p104">创建一个新记录后，会自动将 **DefaultValue** 属性设置输入为字段值。可通过设置该字段的 **[Value](field-value-property-dao.md)** 属性更改字段值。</span><span class="sxs-lookup"><span data-stu-id="5818c-p104">When a new record is created, the **DefaultValue** property setting is automatically entered as the value for the field. You can change the field value by setting its **[Value](field-value-property-dao.md)** property.</span></span>

<span data-ttu-id="5818c-131">**DefaultValue** 属性不适用于 **AutoNumber** 和 **Long Binary** 字段。</span><span class="sxs-lookup"><span data-stu-id="5818c-131">The **DefaultValue** property doesn't apply to **AutoNumber** and **Long Binary** fields.</span></span>

## <a name="example"></a><span data-ttu-id="5818c-132">示例</span><span class="sxs-lookup"><span data-stu-id="5818c-132">Example</span></span>

<span data-ttu-id="5818c-p105">以下示例使用 **DefaultValue** 属性，在系统提示输入时，向用户发出有关字段正常值的警报。此外，该示例还演示了在缺少其他任何输入的情况下，如何使用 **DefaultValue** 填充新记录。若要使该过程运行，需要使用 DefaultPrompt 函数。</span><span class="sxs-lookup"><span data-stu-id="5818c-p105">This example uses the **DefaultValue** property to alert the user of a field's normal value while prompting for input. In addition, it demonstrates how new records will be filled using **DefaultValue** in the absence of any other input. The DefaultPrompt function is required for this procedure to run.</span></span>

```vb
    Sub DefaultValueX() 
     
     Dim dbsNorthwind As Database 
     Dim tdfEmployees As TableDef 
     Dim strOldDefault As String 
     Dim rstEmployees As Recordset 
     Dim strMessage As String 
     Dim strCode As String 
     
     Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
     Set tdfEmployees = dbsNorthwind.TableDefs!Employees 
     
     ' Store original DefaultValue information and set the 
     ' property to a new value. 
     strOldDefault = _ 
     tdfEmployees.Fields!PostalCode.DefaultValue 
     tdfEmployees.Fields!PostalCode.DefaultValue = "98052" 
     
     Set rstEmployees = _ 
     dbsNorthwind.OpenRecordset("Employees", _ 
     dbOpenDynaset) 
     
     With rstEmployees 
     ' Add a new record to the Recordset. 
     .AddNew 
     !FirstName = "Bruce" 
     !LastName = "Oberg" 
     
     ' Get user input. If user enters something, the field 
     ' will be filled with that data; otherwise, it will be 
     ' filled with the DefaultValue information. 
     strMessage = "Enter postal code for " & vbCr & _ 
     !FirstName & " " & !LastName & ":" 
     strCode = DefaultPrompt(strMessage, !PostalCode) 
     If strCode <> "" Then !PostalCode = strCode 
     .Update 
     
     ' Go to new record and print information. 
     .Bookmark = .LastModified 
     Debug.Print " FirstName = " & !FirstName 
     Debug.Print " LastName = " & !LastName 
     Debug.Print " PostalCode = " & !PostalCode 
     
     ' Delete new record because this is a demonstration. 
     .Delete 
     .Close 
     End With 
     
     ' Restore original DefaultValue property because this is a 
     ' demonstration. 
     tdfEmployees.Fields!PostalCode.DefaultValue = _ 
     strOldDefault 
     
     dbsNorthwind.Close 
     
    End Sub 
     
    Function DefaultPrompt(strPrompt As String, _ 
     fldTemp As Field) As String 
     
     Dim strFullPrompt As String 
     
     ' Ask user for new DefaultValue setting for the specified 
     ' Field object. 
     strFullPrompt = strPrompt & vbCr & _ 
     "[Default = " & fldTemp.DefaultValue & _ 
     ", Cancel - use default]" 
     DefaultPrompt = InputBox(strFullPrompt) 
     
    End Function
```
