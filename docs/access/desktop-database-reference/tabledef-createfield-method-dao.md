---
title: TableDef.CreateField 方法 (DAO)
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
localization_priority: Priority
ms.openlocfilehash: 713f2530369a824a6d7204655ded4333f7fe2765
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32308440"
---
# <a name="tabledefcreatefield-method-dao"></a><span data-ttu-id="eccc3-102">TableDef.CreateField 方法 (DAO)</span><span class="sxs-lookup"><span data-stu-id="eccc3-102">TableDef.CreateField method (DAO)</span></span>

<span data-ttu-id="eccc3-103">**适用于**：Access 2013 | Office 2013</span><span class="sxs-lookup"><span data-stu-id="eccc3-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="eccc3-104">创建一个新的 **[Field](field-object-dao.md)** 对象（仅适用于 Microsoft Access 工作区）。</span><span class="sxs-lookup"><span data-stu-id="eccc3-104">Creates a new **[Field](field-object-dao.md)** object (Microsoft Access workspaces only).</span></span>

## <a name="syntax"></a><span data-ttu-id="eccc3-105">语法</span><span class="sxs-lookup"><span data-stu-id="eccc3-105">Syntax</span></span>

<span data-ttu-id="eccc3-106">*表达式* .CreateField(_**Name**_, _**Type**_, _**Size**_)</span><span class="sxs-lookup"><span data-stu-id="eccc3-106">CreateField( Name ,  Type ,  Size )</span></span>

<span data-ttu-id="eccc3-107">*表达式* 一个表示 **TableDef** 对象的变量。</span><span class="sxs-lookup"><span data-stu-id="eccc3-107">*expression*  A variable that represents a **TableDef** object.</span></span>

## <a name="parameters"></a><span data-ttu-id="eccc3-108">参数</span><span class="sxs-lookup"><span data-stu-id="eccc3-108">Parameters</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="eccc3-109">名称</span><span class="sxs-lookup"><span data-stu-id="eccc3-109">Name</span></span></p></th>
<th><p><span data-ttu-id="eccc3-110">必需/可选</span><span class="sxs-lookup"><span data-stu-id="eccc3-110">Required/Optional</span></span></p></th>
<th><p><span data-ttu-id="eccc3-111">数据类型</span><span class="sxs-lookup"><span data-stu-id="eccc3-111">Data type</span></span></p></th>
<th><p><span data-ttu-id="eccc3-112">说明</span><span class="sxs-lookup"><span data-stu-id="eccc3-112">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="eccc3-113"><em>Name</em></span><span class="sxs-lookup"><span data-stu-id="eccc3-113"><em>Name</em></span></span></p></td>
<td><p><span data-ttu-id="eccc3-114">可选</span><span class="sxs-lookup"><span data-stu-id="eccc3-114">Optional</span></span></p></td>
<td><p><span data-ttu-id="eccc3-115"><strong>Variant</strong></span><span class="sxs-lookup"><span data-stu-id="eccc3-115"><strong>Variant</strong></span></span></p></td>
<td><p><span data-ttu-id="eccc3-116">一个字符串，用于唯一命名新的 <strong>Field</strong> 对象。</span><span class="sxs-lookup"><span data-stu-id="eccc3-116">A String that uniquely names the new <strong>Field</strong> object.</span></span> <span data-ttu-id="eccc3-117">有关有效 <strong>Field</strong> 名称的详细信息，请参阅 <strong><a href="connection-name-property-dao.md">Name</a></strong> 属性。</span><span class="sxs-lookup"><span data-stu-id="eccc3-117">See the <a href="connection-name-property-dao.md"><strong>Name</strong></a> property for details on valid <strong>Field</strong> names.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eccc3-118"><em>Type</em></span><span class="sxs-lookup"><span data-stu-id="eccc3-118"><em>Type</em></span></span></p></td>
<td><p><span data-ttu-id="eccc3-119">可选</span><span class="sxs-lookup"><span data-stu-id="eccc3-119">Optional</span></span></p></td>
<td><p><span data-ttu-id="eccc3-120"><strong>Variant</strong></span><span class="sxs-lookup"><span data-stu-id="eccc3-120"><strong>Variant</strong></span></span></p></td>
<td><p><span data-ttu-id="eccc3-121">一个常量，用于确定新的 <strong>Field</strong> 对象的数据类型。</span><span class="sxs-lookup"><span data-stu-id="eccc3-121">A constant that determines the data type of the new <strong>Field</strong> object.</span></span> <span data-ttu-id="eccc3-122">有关有效数据类型的信息，请参阅 <strong><a href="field-type-property-dao.md">Type</a></strong> 属性。</span><span class="sxs-lookup"><span data-stu-id="eccc3-122">See the <a href="field-type-property-dao.md"><strong>Type</strong></a> property for valid data types.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eccc3-123"><em>Size</em></span><span class="sxs-lookup"><span data-stu-id="eccc3-123"><em>Size</em></span></span></p></td>
<td><p><span data-ttu-id="eccc3-124">可选</span><span class="sxs-lookup"><span data-stu-id="eccc3-124">Optional</span></span></p></td>
<td><p><span data-ttu-id="eccc3-125"><strong>Variant</strong></span><span class="sxs-lookup"><span data-stu-id="eccc3-125"><strong>Variant</strong></span></span></p></td>
<td><p><span data-ttu-id="eccc3-126">一个整数，用于指示包含文本的 <strong>Field</strong> 对象的最大大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="eccc3-126">An Integer that indicates the maximum size, in bytes, of a <strong>Field</strong> object that contains text.</span></span> <span data-ttu-id="eccc3-127">有关有效 size 值的信息，请参阅 <strong><a href="field-size-property-dao.md">Size</a></strong> 属性。</span><span class="sxs-lookup"><span data-stu-id="eccc3-127">See the <a href="field-size-property-dao.md"><strong>Size</strong></a> property for valid size values.</span></span> <span data-ttu-id="eccc3-128">对于数值和固定宽度字段，将忽略此参数。</span><span class="sxs-lookup"><span data-stu-id="eccc3-128">This argument is ignored for numeric and fixed-width fields.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="return-value"></a><span data-ttu-id="eccc3-129">返回值</span><span class="sxs-lookup"><span data-stu-id="eccc3-129">Return value</span></span>

<span data-ttu-id="eccc3-130">Field</span><span class="sxs-lookup"><span data-stu-id="eccc3-130">Field</span></span>

## <a name="remarks"></a><span data-ttu-id="eccc3-131">说明</span><span class="sxs-lookup"><span data-stu-id="eccc3-131">Remarks</span></span>

<span data-ttu-id="eccc3-p104">可以使用 **CreateField** 方法创建新的字段，以及指定字段的名称、数据类型和大小。如果使用 **CreateField** 时省略了一个或多个可选部分，则可以在将新对象追加到集合之前，使用适当的赋值语句设置或重置相应的属性。追加新对象后，可以改动此对象的某些（但不是所有）属性设置。有关详细信息，请参阅各个属性主题。</span><span class="sxs-lookup"><span data-stu-id="eccc3-p104">You can use the **CreateField** method to create a new field, as well as specify the name, data type, and size of the field. If you omit one or more of the optional parts when you use **CreateField**, you can use an appropriate assignment statement to set or reset the corresponding property before you append the new object to a collection. After you append the new object, you can alter some but not all of its property settings. See the individual property topics for more details.</span></span>

<span data-ttu-id="eccc3-136">type 和 Size 参数只适用于 **TableDef** 对象中的 **Field** 对象。</span><span class="sxs-lookup"><span data-stu-id="eccc3-136">The  type and  size arguments apply only to Field objects in a TableDef object.</span></span> <span data-ttu-id="eccc3-137">当 **Field** 对象与 **Index** 或 **Relation** 对象关联时，将忽略这些参数。</span><span class="sxs-lookup"><span data-stu-id="eccc3-137">These arguments are ignored when a **Field** object is associated with an **Index** or **Relation** object.</span></span>

<span data-ttu-id="eccc3-138">如果 Name 引用了一个已经是集合成员的对象，那么在使用 **[Append](fields-append-method-dao.md)** 方法时将发生运行时错误。</span><span class="sxs-lookup"><span data-stu-id="eccc3-138">If  name refers to an object that is already a member of the collection, a run-time error occurs when you use the  Append  method.</span></span>

<span data-ttu-id="eccc3-p106">要从 **Fields** 集合中删除 **Field** 对象，请对集合使用 **[Delete](fields-delete-method-dao.md)** 方法。创建了一个引用字段的索引后，不能从 **TableDef** 对象的 **Fields** 集合中删除 **Field** 对象。</span><span class="sxs-lookup"><span data-stu-id="eccc3-p106">To remove a **Field** object from a **Fields** collection, use the **[Delete](fields-delete-method-dao.md)** method on the collection. You can't delete a **Field** object from a **TableDef** object's **Fields** collection after you create an index that references the field.</span></span>

<span data-ttu-id="eccc3-141">**链接提供者：**[UtterAccess](https://www.utteraccess.com) 社区。</span><span class="sxs-lookup"><span data-stu-id="eccc3-141">**Link provided by:** The [UtterAccess](https://www.utteraccess.com) community</span></span> <span data-ttu-id="eccc3-142">UtterAccess 是主要的 Microsoft Access Wiki 和帮助论坛。</span><span class="sxs-lookup"><span data-stu-id="eccc3-142">UtterAccess is the premier Microsoft Access wiki and help forum.</span></span>

- [<span data-ttu-id="eccc3-143">使用 DAO 将超链接字段添加到现有表</span><span class="sxs-lookup"><span data-stu-id="eccc3-143">Adding a hyperlink field to an existing table with DAO</span></span>](https://www.utteraccess.com/wiki/index.php/adding_a_hyperlink_field_to_an_existing_table_with_dao)

## <a name="example"></a><span data-ttu-id="eccc3-144">示例</span><span class="sxs-lookup"><span data-stu-id="eccc3-144">Example</span></span>

<span data-ttu-id="eccc3-145">以下示例显示了如何创建计算字段。</span><span class="sxs-lookup"><span data-stu-id="eccc3-145">The following example shows how to create a calculated field.</span></span> <span data-ttu-id="eccc3-146">CreateField 方法将创建名为 **FullName** 的字段。</span><span class="sxs-lookup"><span data-stu-id="eccc3-146">The CreateField method creates a field named **FullName**.</span></span> <span data-ttu-id="eccc3-147">Expression 属性随后将被设为用于计算字段值的表达式。</span><span class="sxs-lookup"><span data-stu-id="eccc3-147">The Expression property is then set to the expression that calculates the value of the field.</span></span>

<span data-ttu-id="eccc3-148">**示例代码提供方：**[Microsoft Access 2010 程序员参考](https://www.amazon.com/Microsoft-Access-2010-Programmers-Reference/dp/8126528125)。</span><span class="sxs-lookup"><span data-stu-id="eccc3-148">**Sample code provided by** the [Microsoft Access 2010 Programmer’s Reference](https://www.amazon.com/Microsoft-Access-2010-Programmers-Reference/dp/8126528125).</span></span>

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

