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
# <a name="tabledefcreatefield-method-dao"></a>TableDef.CreateField 方法 (DAO)

**适用于**：Access 2013 | Office 2013

创建一个新的 **[Field](field-object-dao.md)** 对象（仅适用于 Microsoft Access 工作区）。

## <a name="syntax"></a>语法

*表达式* .CreateField(_**Name**_, _**Type**_, _**Size**_)

*表达式* 一个表示 **TableDef** 对象的变量。

## <a name="parameters"></a>参数

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p>名称</p></th>
<th><p>必需/可选</p></th>
<th><p>数据类型</p></th>
<th><p>说明</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><em>Name</em></p></td>
<td><p>可选</p></td>
<td><p><strong>Variant</strong></p></td>
<td><p>一个字符串，用于唯一命名新的 <strong>Field</strong> 对象。 有关有效 <strong>Field</strong> 名称的详细信息，请参阅 <strong><a href="connection-name-property-dao.md">Name</a></strong> 属性。</p></td>
</tr>
<tr class="even">
<td><p><em>Type</em></p></td>
<td><p>可选</p></td>
<td><p><strong>Variant</strong></p></td>
<td><p>一个常量，用于确定新的 <strong>Field</strong> 对象的数据类型。 有关有效数据类型的信息，请参阅 <strong><a href="field-type-property-dao.md">Type</a></strong> 属性。</p></td>
</tr>
<tr class="odd">
<td><p><em>Size</em></p></td>
<td><p>可选</p></td>
<td><p><strong>Variant</strong></p></td>
<td><p>一个整数，用于指示包含文本的 <strong>Field</strong> 对象的最大大小（以字节为单位）。 有关有效 size 值的信息，请参阅 <strong><a href="field-size-property-dao.md">Size</a></strong> 属性。 对于数值和固定宽度字段，将忽略此参数。</p></td>
</tr>
</tbody>
</table>


## <a name="return-value"></a>返回值

Field

## <a name="remarks"></a>说明

可以使用 **CreateField** 方法创建新的字段，以及指定字段的名称、数据类型和大小。如果使用 **CreateField** 时省略了一个或多个可选部分，则可以在将新对象追加到集合之前，使用适当的赋值语句设置或重置相应的属性。追加新对象后，可以改动此对象的某些（但不是所有）属性设置。有关详细信息，请参阅各个属性主题。

type 和 Size 参数只适用于 **TableDef** 对象中的 **Field** 对象。 当 **Field** 对象与 **Index** 或 **Relation** 对象关联时，将忽略这些参数。

如果 Name 引用了一个已经是集合成员的对象，那么在使用 **[Append](fields-append-method-dao.md)** 方法时将发生运行时错误。

要从 **Fields** 集合中删除 **Field** 对象，请对集合使用 **[Delete](fields-delete-method-dao.md)** 方法。创建了一个引用字段的索引后，不能从 **TableDef** 对象的 **Fields** 集合中删除 **Field** 对象。

**链接提供者：**[UtterAccess](https://www.utteraccess.com) 社区。 UtterAccess 是主要的 Microsoft Access Wiki 和帮助论坛。

- [使用 DAO 将超链接字段添加到现有表](https://www.utteraccess.com/wiki/index.php/adding_a_hyperlink_field_to_an_existing_table_with_dao)

## <a name="example"></a>示例

以下示例显示了如何创建计算字段。 CreateField 方法将创建名为 **FullName** 的字段。 Expression 属性随后将被设为用于计算字段值的表达式。

**示例代码提供方：**[Microsoft Access 2010 程序员参考](https://www.amazon.com/Microsoft-Access-2010-Programmers-Reference/dp/8126528125)。

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

