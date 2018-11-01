---
title: 使用 Recordset
TOCTitle: Working with Recordsets
ms:assetid: 9cd52866-2738-8150-381c-eee0b8a6cd36
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249711(v=office.15)
ms:contentKeyID: 48546608
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: d57f05905aa0f79c1a72638e70ede8bdabf73b8f
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25883685"
---
# <a name="working-with-recordsets"></a>使用记录集


**适用于**： Access 2013、 Office 2013 

使用 **Recordset** 对象中的内置功能，可以对结果集内的数据重新排序，可以基于所提供的条件搜索特定记录，甚至还可以使用索引来优化这些搜索操作。这些功能是否可用取决于提供程序，在某些情况下，诸如 [Index](index-property-ado.md) 属性的功能等取决于数据源本身的结构。

## <a name="arranging-data"></a>排列数据

通常，对 **Recordset** 中的数据进行排序的最有效方式是：在用来向记录集返回结果的 SQL 命令中指定一个 ORDER BY 子句。但是，您可能需要更改已创建的 **Recordset** 中数据的顺序。可以使用 **Sort** 属性建立对 **Recordset** 中的行进行浏览的顺序。而且， **Filter** 属性确定在浏览行时可以访问哪些行。

**Sort** 属性设置或返回一个 **字符串型** 值，该值指示要作为排序依据的 **Recordset** 中的字段名称。名称之间用逗号隔开，名称后面可以后跟一个空格和关键字 **ASC** （按升序对字段进行排序）或 **DESC** （按降序对字段进行排序）。默认情况下，如果未指定关键字，则按升序对字段进行排序。

排序操作的效率非常高，因为数据并不实际重新排列，而只是按照由索引指定的顺序进行访问。

**Sort** 属性要求将 [CursorLocation](cursorlocation-property-ado.md) 属性设置为 **adUseClient** 。如果索引不存在，则会为 **Sort** 属性中指定的每个字段创建一个临时索引。

如果将 **Sort** 属性设置为一个空字符串，则会将行重置为其初始顺序并删除临时索引。现有的索引不会被删除。

假设某个 **Recordset** 包含名为 *firstName*、*middleInitial* 和 *lastName* 的三个字段。请将 **Sort** 属性设置为字符串 ""，这将按姓氏以降序对 **Recordset** 排列，然后按名字以升序排列。中间名将被忽略。

不能将排序条件字符串中引用的字段命名为"ASC"或"DESC"，因为这些名称与关键字 **ASC** 和 **DESC** 冲突。在返回 **Recordset** 的查询中，可以使用 **AS** 关键字为具有冲突名称的字段指定一个别名。

有关 **Recordset** 筛选的更多详细信息，请参阅本主题中稍后介绍的"对结果进行筛选"。

## <a name="finding-a-specific-record"></a>查找特定记录

ADO 提供了用来在 [Recordset](find-method-ado.md) 中查找特定记录的 [Find](seek-method-ado.md) 和 **Seek** 方法。 **Find** 方法受多种提供程序支持，但是仅限于单个搜索条件。 **Seek** 方法支持按多个条件进行搜索，但是能够支持它的提供程序不太多。

字段的索引可以大大增强 **Recordset** 对象的 **Find** 方法、 **Sort** 属性和 **Filter** 属性的性能。对于 **Field** 对象，可以通过设置 [Optimize](optimize-property-dynamic-ado.md) 动态属性来为其创建内部索引。当您将 **CursorLocation** 属性设置为 **adUseClient** 时，这个动态属性会添加到 [Field](cursorlocation-property-ado.md) 对象的 **Properties** 集合中。请记住，这个索引是 ADO 的内部索引，您不能获取对它的访问或者将其用于任何其他目的。而且，这个索引不同于 **Recordset** 对象的 [Index](index-property-ado.md) 属性。

**Find** 方法可在 **Recordset** 的列（字段）中快速查找值。通常，可以使用 **Optimize** 属性为列创建索引，从而提高对于列执行 **Find** 方法的速度。

**Find** 方法将搜索限制为一个字段的内容。 **Seek** 方法要求有索引和其他限制。如果您需要搜索不作为索引基础的多个字段，或者您的提供程序不支持索引，则可以使用 **Recordset** 对象的 **Filter** 属性来限制结果。

## <a name="find"></a>Find

**Find** 方法在 **Recordset** 中搜索满足指定条件的行。还可以指定搜索方向、起始行以及与起始行的偏移量。如果满足条件，则当前行的位置将设置到找到的记录上；否则，当前行的位置将设置到 **Recordset** 的末尾（或开头），具体取决于搜索方向。

只能为搜索条件指定一个单列名称。换言之，此方法不支持多列搜索。

比较运算符条件可能"**\>**"（大于），"**\<**"（小于），"="（等于），"\>="（大于或等于），"\<="（小于或等于），"\<\>"（不等于），或"LIKE"（模式匹配）。

条件值可以是字符串、浮点数或日期。 用单引号分隔字符串值或"\#"（数字标记） 标记 (例如，"状态 WA ="或"状态 = \#WA\#")。 日期值分隔与"\#"（数字标记） 标记 (例如，"启动\_日期\> \#97-7-22\#")。

如果比较运算符是"like"，则字符串值中可以包含星号 (\*)，以查找一次或多次出现的任何字符或子字符串。例如，"state like 'M\*'"与 Maine 和 Massachusetts 相匹配。还可以使用前导和尾随星号来查找包含在值中的子字符串。例如，"state like '\*as\*'"与 Alaska、Arkansas 和 Massachusetts 相匹配。

星号只能用在条件字符串的末尾或者与条件字符串的开头和末尾处的字符一起使用，如上所示。不能将星号用作前导通配符 ('\*str') 或嵌入通配符 ('s\*r')，否则将导致错误。

## <a name="seek-and-index"></a>Seek 和 Index

如果基础提供程序支持 **Recordset** 对象的索引，则可以将 **Seek** 方法与 **Index** 属性一起使用。使用 [Supports](supports-method-ado.md)**(adSeek)** 方法可以确定基础提供程序是否支持 **Seek**，使用 **Supports(adIndex)** 方法可以确定提供程序是否支持索引。（例如，[OLE DB Provider for Microsoft Jet](microsoft-ole-db-provider-for-microsoft-jet.md) 支持 **Seek** 和 **Index**。）

如果 **Seek** 找不到所需的行，不会发生错误，只是将该行置于 **Recordset** 的末尾。将 **Index** 属性设置为所需索引，然后执行此方法。

只有服务器端游标才支持此方法。当 **Recordset** 对象的 [CursorLocation](cursorlocation-property-ado.md) 属性值为 **adUseClient** 时，不支持 Seek。

只有当 **Recordset** 对象是用 [adCmdTableDirect](commandtypeenum.md) 的 **CommandTypeEnum** 值打开时，才能使用 Seek 方法。

## <a name="filtering-the-results"></a>对结果进行筛选

**Find** 方法将搜索限制为一个字段的内容。 **Seek** 方法要求有索引和其他限制。如果您需要搜索不作为索引基础的多个字段，或者您的提供程序不支持索引，则可以使用 **Recordset** 对象的 **Filter** 属性来限制结果。

使用 **Filter** 属性，可以有选择地筛选出 **Recordset** 对象中的记录。所筛选的 **Recordset** 将成为当前游标，这意味着不满足 **Filter** 条件的记录在 **Recordset** 中将不可用，直到删除 **Filter** 。其他基于当前游标返回值的属性（如 **AbsolutePosition** 、 **AbsolutePage** 、 **RecordCount** 和 **PageCount** ）也会受到影响。这是因为如果将 **Filter** 属性设置为特定值，会将当前的记录移到满足新值的第一个记录。

**Filter** 属性采用变量型参数。此值表示使用 **Filter** 属性的三种方法之一：条件字符串、 **FilterGroupEnum** 常量或书签数组。有关详细信息，请参阅本主题中稍后介绍的"用条件字符串筛选"、"用常量筛选"和"用书签筛选"。


> [!NOTE]
> <P>[!注释] 如果您知道要选择哪些数据，那么，与依赖于 <STRONG>Filter</STRONG> 属性相比，使用能够有效筛选结果集的 SQL 语句来打开 <STRONG>Recordset</STRONG> 通常效率更高。</P>



若要从 **Recordset** 中删除筛选，请使用 **adFilterNone** 常量。将 **Filter** 属性设置为零长度字符串 ("") 与使用 **adFilterNone** 常量等效。

## <a name="filtering-with-a-criteria-string"></a>用条件字符串筛选

条件字符串由*FieldName 运算符值*形式的子句组成 (例如，"LastName = 'Smith'")。 您可以通过将单个子句与创建复合子句 AND (例如，"LastName = 'Smith' 和 FirstName = John") 和或 （例如，）。 您可以通过将单个子句与创建复合子句 AND (例如，"LastName = 'Smith' 和 FirstName = John") 和或 (例如，"LastName = 'Smith' 或姓氏 = Jones")。 对条件字符串使用以下准则：

  - *FieldName*必须是有效的字段名称从**记录集**。 如果字段名中包含空格，则必须用方括号将字段名括起来。

  - *Operator*必须是以下项之一： \<， \>， \<= \>= \< \>、 = 或 LIKE。

  - *值*是将与其比较的字段值的值 (例如，'Smith'， \#8/24/95\#，12.345 或 $50.00)。 使用字符串单引号 （'） 和井号 (\#) 与日期。 对于数字，可以使用小数点、美元符号和科学记数法。 如果*运算符*是像*值*可以使用通配符。 仅星号 (\*) 和百分号 （%），允许使用通配符，并且它们必须在字符串中的最后一个字符。 *值*不能为 null。
    

    > [!NOTE]
    > <P>若要在筛选器<EM>值</EM>包括单引号 （'），请使用两个单引号来表示一个。 例如，要进行筛选<EM>O'Malley</EM>，criteria 字符串应为"第 1 列 = 'O' Malley'"。 若要包括单引号开头和筛选器值的末尾，将字符串中井号 （#）。 例如， <EM>"1"</EM>的筛选器，则条件字符串应为"第 1 列 ="1"# #"。</P>



AND 和 OR 之间并没有优先级的区别。可以使用圆括号将子句分组。但是不能先将由 OR 连接的子句分组然后通过 AND 将该组与其他子句连接，如下所示：

```vb 
 
(LastName = 'Smith' OR LastName = 'Jones') AND FirstName = 'John' 
```

而是应当按如下方式构造此筛选：

```vb 
 
(LastName = 'Smith' AND FirstName = 'John') OR (LastName = 'Jones' AND FirstName = 'John') 
```

在 LIKE 子句中，您可以使用的开头和模式的末尾使用通配符 (例如，LastName Like '\*mit\*) 仅在模式的末尾 （例如，） 或仅在模式的结尾 (例如，LastName Like' Smit\*)。

## <a name="filtering-with-a-constant"></a>用常量筛选

可以使用下列常量来筛选 **Recordset** 。

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>常量</p></th>
<th><p>说明</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>adFilterAffectedRecords</strong></p></td>
<td><p>用于仅查看受上一次 <strong>Delete</strong> 、 <strong>Resync</strong> 、 <strong>UpdateBatch</strong> 或 <strong>CancelBatch</strong> 调用影响的记录的筛选器。</p></td>
</tr>
<tr class="even">
<td><p><strong>adFilterConflictingRecords</strong></p></td>
<td><p>用于查看使上一次批更新失败的记录的筛选器。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adFilterFetchedRecords</strong></p></td>
<td><p>用于查看当前缓存中的记录（即，上一次从数据库检索记录的调用的结果）的筛选器。</p></td>
</tr>
<tr class="even">
<td><p><strong>adFilterNone</strong></p></td>
<td><p>删除当前的筛选并还原所有的记录以进行查看。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adFilterPendingRecords</strong></p></td>
<td><p>用于仅查看已更改但尚未发送到服务器的记录的筛选器。仅适用于批更新模式。</p></td>
</tr>
</tbody>
</table>


使用筛选常量，更便于解决批更新模式下的个别记录冲突问题，例如，允许您只查看上次调用 **UpdateBatch** 方法过程中受影响的记录，如以下示例所示：

```vb 
 
'BeginDeleteGroup 
    'add some bogus records 
    With objRs1 
        For i = 0 To 8 
            .AddNew 
            .Fields("CompanyName") = "Shipper Number " & i + 1 
            .Fields("Phone") = "(425) 555-000" & (i + 1) 
            .Update 
        Next i 
         
    're-connect & update 
        .ActiveConnection = GetNewConnection 
        .UpdateBatch 
         
    'filter on newly added records 
        .Filter = adFilterAffectedRecords 
        Debug.Print "Deleting the " & .RecordCount & _ 
                    " records you just added." 
         
    'delete the newly added bogus records 
        .Delete adAffectGroup 
        .Filter = adFilterNone 
        Debug.Print .RecordCount & " records remain." 
         
        .Close 
    End With 
'EndDeleteGroup 
```

## <a name="filtering-with-bookmarks"></a>用书签筛选

最后，您可以将书签的 variant 数组传递给**Filter**属性。 生成光标将只包含的记录其书签传递给属性。 下面的代码示例创建从其*ProductName*字段中具有"B" **Recordset**中记录的书签数组。 然后将该数组传递给**筛选器**属性，并显示生成的已筛选**记录集**的信息。

```vb 
 
'BeginFilterBkmk 
    Dim vBkmkArray() As Variant 
    Dim i As Integer 
 
    'Recordset created using "SELECT * FROM Products" as command. 
    'So, we will check to see if ProductName has a capital B, and 
    'if so, add to the array. 
    i = 0 
    Do While Not objRs.EOF 
        If InStr(1, objRs("ProductName"), "B") Then 
            ReDim Preserve vBkmkArray(i) 
            vBkmkArray(i) = objRs.Bookmark 
            i = i + 1 
            Debug.Print objRs("ProductName") 
        End If 
        objRs.MoveNext 
    Loop 
     
    'Filter using the array of bookmarks. 
    objRs.Filter = vBkmkArray 
     
    objRs.MoveFirst 
    Do While Not objRs.EOF 
        Debug.Print objRs("ProductName") 
        objRs.MoveNext 
    Loop 
    'EndFilterBkmk 
```

## <a name="creating-a-clone-of-a-recordset"></a>创建记录集的副本

可以使用 **Clone** 方法创建多个重复的 **Recordset** 对象，尤其是要在给定记录集中保留多个当前记录时。使用 **Clone** 方法比采用与原始对象相同的定义创建和打开一个新的 **Recordset** 对象效率更高。

新建副本的当前记录最初设置为第一个记录。所克隆的 **Recordset** 中当前记录的指针不能与初始记录集同步，反之亦然。可以在每个 **Recordset** 中单独导航。

无论游标类型是什么，对一个 **Recordset** 对象所做的更改可以在该对象的所有副本中体现出来。但是，对原始 [Recordset](requery-method-ado.md) 对象执行 **Requery** 后，副本将不再与原始对象同步。

关闭原始 **Recordset** 不会关闭其副本，同样，关闭副本也不会关闭原始对象或其他任何副本。

只有当 **Recordset** 对象支持书签时，才能克隆该对象。书签值是可以互换的；即，一个 **Recordset** 对象中的书签引用可以引用其任何副本中的同一个记录。

