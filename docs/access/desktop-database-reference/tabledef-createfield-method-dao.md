---
title: TableDef.CreateField Method (DAO)
TOCTitle: CreateField Method
ms:assetid: a83d797f-ea42-4a07-dd9e-b254755f0891
ms:mtpsurl: https://msdn.microsoft.com/library/Ff821396(v=office.15)
ms:contentKeyID: 48546897
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1052971
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 8fa642eb5351129f1763a5b3f24424ae95df073f
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25873927"
---
# <a name="tabledefcreatefield-method-dao"></a><span data-ttu-id="e82c8-102">TableDef.CreateField Method (DAO)</span><span class="sxs-lookup"><span data-stu-id="e82c8-102">TableDef.CreateField Method (DAO)</span></span>

<span data-ttu-id="e82c8-103">**适用于：** Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="e82c8-103">**Applies to:** Access 2013 | Office 2013</span></span>

<span data-ttu-id="e82c8-104">创建一个新的 **[Field](field-object-dao.md)** 对象（仅适用于 Microsoft Access 工作区）。</span><span class="sxs-lookup"><span data-stu-id="e82c8-104">Creates a new **[Field](field-object-dao.md)** object (Microsoft Access workspaces only).</span></span>

## <a name="syntax"></a><span data-ttu-id="e82c8-105">语法</span><span class="sxs-lookup"><span data-stu-id="e82c8-105">Syntax</span></span>

<span data-ttu-id="e82c8-106">*表达式*。CreateField （_**名称**_、_**类型**_，_**大小**_）</span><span class="sxs-lookup"><span data-stu-id="e82c8-106">*expression* .CreateField(_**Name**_, _**Type**_, _**Size**_)</span></span>

<span data-ttu-id="e82c8-107">*表达式*一个代表**TableDef**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="e82c8-107">*expression* A variable that represents a **TableDef** object.</span></span>

### <a name="parameters"></a><span data-ttu-id="e82c8-108">参数</span><span class="sxs-lookup"><span data-stu-id="e82c8-108">Parameters</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="e82c8-109">名称</span><span class="sxs-lookup"><span data-stu-id="e82c8-109">Name</span></span></p></th>
<th><p><span data-ttu-id="e82c8-110">必需/可选</span><span class="sxs-lookup"><span data-stu-id="e82c8-110">Required/Optional</span></span></p></th>
<th><p><span data-ttu-id="e82c8-111">数据类型</span><span class="sxs-lookup"><span data-stu-id="e82c8-111">Data Type</span></span></p></th>
<th><p><span data-ttu-id="e82c8-112">说明</span><span class="sxs-lookup"><span data-stu-id="e82c8-112">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e82c8-113">名称</span><span class="sxs-lookup"><span data-stu-id="e82c8-113">Name</span></span></p></td>
<td><p><span data-ttu-id="e82c8-114">可选</span><span class="sxs-lookup"><span data-stu-id="e82c8-114">Optional</span></span></p></td>
<td><p><span data-ttu-id="e82c8-115"><strong>Variant</strong></span><span class="sxs-lookup"><span data-stu-id="e82c8-115"><strong>Variant</strong></span></span></p></td>
<td><p><span data-ttu-id="e82c8-p101">一个 String 类型的值，用于对新的 <strong>Field</strong> 对象进行唯一命名。有关有效 <strong>Field</strong> 名称的详细信息，请参阅 <strong><a href="connection-name-property-dao.md">Name</a></strong> 属性。</span><span class="sxs-lookup"><span data-stu-id="e82c8-p101">A String that uniquely names the new <strong>Field</strong> object. See the <strong><a href="connection-name-property-dao.md">Name</a></strong> property for details on valid <strong>Field</strong> names.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e82c8-118">类型</span><span class="sxs-lookup"><span data-stu-id="e82c8-118">Type</span></span></p></td>
<td><p><span data-ttu-id="e82c8-119">可选</span><span class="sxs-lookup"><span data-stu-id="e82c8-119">Optional</span></span></p></td>
<td><p><span data-ttu-id="e82c8-120"><strong>Variant</strong></span><span class="sxs-lookup"><span data-stu-id="e82c8-120"><strong>Variant</strong></span></span></p></td>
<td><p><span data-ttu-id="e82c8-p102">一个确定新的 <strong>Field</strong> 对象的数据类型的常量。有关有效数据类型的信息，请参阅 <strong><a href="field-type-property-dao.md">Type</a></strong> 属性。</span><span class="sxs-lookup"><span data-stu-id="e82c8-p102">A constant that determines the data type of the new <strong>Field</strong> object. See the <strong><a href="field-type-property-dao.md">Type</a></strong> property for valid data types.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e82c8-123">Size</span><span class="sxs-lookup"><span data-stu-id="e82c8-123">Size</span></span></p></td>
<td><p><span data-ttu-id="e82c8-124">可选</span><span class="sxs-lookup"><span data-stu-id="e82c8-124">Optional</span></span></p></td>
<td><p><span data-ttu-id="e82c8-125"><strong>Variant</strong></span><span class="sxs-lookup"><span data-stu-id="e82c8-125"><strong>Variant</strong></span></span></p></td>
<td><p><span data-ttu-id="e82c8-p103">一个 Integer 类型的值，用于指示包含文本的 <strong>Field</strong> 对象的最大大小（以字节为单位）。有关有效 size 值的信息，请参阅 <strong><a href="field-size-property-dao.md">Size</a></strong> 属性。对于数值型字段和宽度固定的字段，将忽略此参数。</span><span class="sxs-lookup"><span data-stu-id="e82c8-p103">An Integer that indicates the maximum size, in bytes, of a <strong>Field</strong> object that contains text. See the <strong><a href="field-size-property-dao.md">Size</a></strong> property for valid size values. This argument is ignored for numeric and fixed-width fields.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="return-value"></a><span data-ttu-id="e82c8-129">返回值</span><span class="sxs-lookup"><span data-stu-id="e82c8-129">Return value</span></span>

<span data-ttu-id="e82c8-130">Field</span><span class="sxs-lookup"><span data-stu-id="e82c8-130">Field</span></span>

## <a name="remarks"></a><span data-ttu-id="e82c8-131">注解</span><span class="sxs-lookup"><span data-stu-id="e82c8-131">Remarks</span></span>

<span data-ttu-id="e82c8-p104">可以使用 **CreateField** 方法创建新的字段，以及指定字段的名称、数据类型和大小。如果使用 **CreateField** 时省略了一个或多个可选部分，则可以在将新对象追加到集合之前，使用适当的赋值语句设置或重置相应的属性。追加新对象后，可以改动此对象的某些（但不是所有）属性设置。有关详细信息，请参阅各个属性主题。</span><span class="sxs-lookup"><span data-stu-id="e82c8-p104">You can use the **CreateField** method to create a new field, as well as specify the name, data type, and size of the field. If you omit one or more of the optional parts when you use **CreateField**, you can use an appropriate assignment statement to set or reset the corresponding property before you append the new object to a collection. After you append the new object, you can alter some but not all of its property settings. See the individual property topics for more details.</span></span>

<span data-ttu-id="e82c8-136">类型和大小参数仅适用于**TableDef**对象中的**Field**对象。</span><span class="sxs-lookup"><span data-stu-id="e82c8-136">The type and Size arguments apply only to **Field** objects in a **TableDef** object.</span></span> <span data-ttu-id="e82c8-137">如果 **Field** 对象与 **Index** 或 **Relation** 对象关联，则会忽略这些参数。</span><span class="sxs-lookup"><span data-stu-id="e82c8-137">These arguments are ignored when a **Field** object is associated with an **Index** or **Relation** object.</span></span>

<span data-ttu-id="e82c8-138">如果 Name 引用对象的已经是集合的成员，使用**[Append](fields-append-method-dao.md)** 方法时，发生此事件运行时错误。</span><span class="sxs-lookup"><span data-stu-id="e82c8-138">If Name refers to an object that is already a member of the collection, a run-time error occurs when you use the **[Append](fields-append-method-dao.md)** method.</span></span>

<span data-ttu-id="e82c8-p106">要从 **Fields** 集合中删除 **Field** 对象，请对集合使用 **[Delete](fields-delete-method-dao.md)** 方法。创建了一个引用字段的索引后，不能从 **TableDef** 对象的 **Fields** 集合中删除 **Field** 对象。</span><span class="sxs-lookup"><span data-stu-id="e82c8-p106">To remove a **Field** object from a **Fields** collection, use the **[Delete](fields-delete-method-dao.md)** method on the collection. You can't delete a **Field** object from a **TableDef** object's **Fields** collection after you create an index that references the field.</span></span>

<span data-ttu-id="e82c8-141">**链接提供** [UtterAccess](https://www.utteraccess.com)社区。</span><span class="sxs-lookup"><span data-stu-id="e82c8-141">**Link provided by** the [UtterAccess](https://www.utteraccess.com) community.</span></span> <span data-ttu-id="e82c8-142">UtterAccess 是主要的 Microsoft Access Wiki 和帮助论坛。</span><span class="sxs-lookup"><span data-stu-id="e82c8-142">UtterAccess is the premier Microsoft Access wiki and help forum.</span></span>

- [<span data-ttu-id="e82c8-143">将超链接字段添加到现有表与 DAO</span><span class="sxs-lookup"><span data-stu-id="e82c8-143">Adding a hyperlink field to an existing table with DAO</span></span>](https://www.utteraccess.com/wiki/index.php/adding_a_hyperlink_field_to_an_existing_table_with_dao)

## <a name="example"></a><span data-ttu-id="e82c8-144">示例</span><span class="sxs-lookup"><span data-stu-id="e82c8-144">Example</span></span>

<span data-ttu-id="e82c8-145">下面的示例演示如何创建计算的字段。</span><span class="sxs-lookup"><span data-stu-id="e82c8-145">The following example shows how to create a calculated field.</span></span> <span data-ttu-id="e82c8-146">CreateField 方法创建一个名为**FullName**字段。</span><span class="sxs-lookup"><span data-stu-id="e82c8-146">The CreateField method creates a field named **FullName**.</span></span> <span data-ttu-id="e82c8-147">然后表达式属性设置为计算字段的值的表达式。</span><span class="sxs-lookup"><span data-stu-id="e82c8-147">The Expression property is then set to the expression that calculates the value of the field.</span></span>

<span data-ttu-id="e82c8-148">**示例代码提供者** [Microsoft Access 2010 Programmer's Reference](https://www.amazon.com/Microsoft-Access-2010-Programmers-Reference/dp/8126528125)。</span><span class="sxs-lookup"><span data-stu-id="e82c8-148">**Sample code provided by** the [Microsoft Access 2010 Programmer’s Reference](https://www.amazon.com/Microsoft-Access-2010-Programmers-Reference/dp/8126528125).</span></span>

```vb
    Sub CreateCalculatedField()
        Dim dbs As DAO.Database
        Dim tdf As DAO.TableDef
        Dim fld As DAO.Field2
        
        ' get the database
        Set dbs = CurrentDb()
        
        ' create the table
        Set tdf = dbs.CreateTableDef("tblContactsCalcField")
        
        ' create the fields: first name, last name
        tdf.Fields.Append tdf.CreateField("FirstName", dbText, 20)
        tdf.Fields.Append tdf.CreateField("LastName", dbText, 20)
        
        ' create the calculated field: full name
        Set fld = tdf.CreateField("FullName", dbText, 50)
        fld.Expression = "[FirstName] & "" "" & [LastName]"
        tdf.Fields.Append fld
        
        ' append the table and cleanup
        dbs.TableDefs.Append tdf
        
    Cleanup:
        Set fld = Nothing
        Set tdf = Nothing
        Set dbs = Nothing
    End Sub
```

