---
title: 使用 Recordset
TOCTitle: Working with Recordsets
ms:assetid: 9cd52866-2738-8150-381c-eee0b8a6cd36
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249711(v=office.15)
ms:contentKeyID: 48546608
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 0d4b877b680c80a10067e19065facd4ce9e4819d
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32305970"
---
# <a name="working-with-recordsets"></a><span data-ttu-id="cf73f-102">使用记录集</span><span class="sxs-lookup"><span data-stu-id="cf73f-102">Working with Recordsets</span></span>

<span data-ttu-id="cf73f-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="cf73f-103">**Applies to**: Access 2013, Office 2013</span></span> 

<span data-ttu-id="cf73f-p101">使用 **Recordset** 对象中的内置功能，可以对结果集内的数据重新排序，可以基于所提供的条件搜索特定记录，甚至还可以使用索引来优化这些搜索操作。这些功能是否可用取决于提供程序，在某些情况下，诸如 [Index](index-property-ado.md) 属性的功能等取决于数据源本身的结构。</span><span class="sxs-lookup"><span data-stu-id="cf73f-p101">The **Recordset** object has built-in features that make it possible for you to rearrange the order of the data in the result set, to search for a specific record based on criteria that you supply, and even to optimize those search operations using indexes. Whether these features are available for use depends on the provider and in some cases — such as that of the [Index](index-property-ado.md) property — the structure of the data source itself.</span></span>

## <a name="arranging-data"></a><span data-ttu-id="cf73f-106">排列数据</span><span class="sxs-lookup"><span data-stu-id="cf73f-106">Arranging data</span></span>

<span data-ttu-id="cf73f-p102">通常，对 **Recordset** 中的数据进行排序的最有效方式是：在用来向记录集返回结果的 SQL 命令中指定一个 ORDER BY 子句。但是，您可能需要更改已创建的 **Recordset** 中数据的顺序。可以使用 **Sort** 属性建立对 **Recordset** 中的行进行浏览的顺序。而且， **Filter** 属性确定在浏览行时可以访问哪些行。</span><span class="sxs-lookup"><span data-stu-id="cf73f-p102">Often, the most efficient way to order the data in your **Recordset** is by specifying an ORDER BY clause in the SQL command used to return results to it. However, you might need to change the order of the data in a **Recordset** that has already been created. You can use the **Sort** property to establish the order in which rows of a **Recordset** are traversed. Furthermore, the **Filter** property determines which rows are accessible when traversing rows.</span></span>

<span data-ttu-id="cf73f-p103">**Sort** 属性设置或返回一个 **字符串型** 值，该值指示要作为排序依据的 **Recordset** 中的字段名称。名称之间用逗号隔开，名称后面可以后跟一个空格和关键字 **ASC** （按升序对字段进行排序）或 **DESC** （按降序对字段进行排序）。默认情况下，如果未指定关键字，则按升序对字段进行排序。</span><span class="sxs-lookup"><span data-stu-id="cf73f-p103">The **Sort** property sets or returns a **String** value that indicates the field names in the **Recordset** on which to sort. Each name is separated by a comma and is optionally followed by a space and the keyword **ASC** (which sorts the field in ascending order) or **DESC** (which sorts the field in descending order). By default, if no keyword is specified, the field is sorted in ascending order.</span></span>

<span data-ttu-id="cf73f-114">排序操作的效率非常高，因为数据并不实际重新排列，而只是按照由索引指定的顺序进行访问。</span><span class="sxs-lookup"><span data-stu-id="cf73f-114">The sort operation is efficient because data is not physically rearranged but is simply accessed in the order specified by an index.</span></span>

<span data-ttu-id="cf73f-p104">**Sort** 属性要求将 [CursorLocation](cursorlocation-property-ado.md) 属性设置为 **adUseClient** 。如果索引不存在，则会为 **Sort** 属性中指定的每个字段创建一个临时索引。</span><span class="sxs-lookup"><span data-stu-id="cf73f-p104">The **Sort** property requires the [CursorLocation](cursorlocation-property-ado.md) property to be set to **adUseClient**. A temporary index will be created for each field specified in the **Sort** property if an index does not already exist.</span></span>

<span data-ttu-id="cf73f-p105">如果将 **Sort** 属性设置为一个空字符串，则会将行重置为其初始顺序并删除临时索引。现有的索引不会被删除。</span><span class="sxs-lookup"><span data-stu-id="cf73f-p105">Setting the **Sort** property to an empty string will reset the rows to their original order and delete temporary indexes. Existing indexes will not be deleted.</span></span>

<span data-ttu-id="cf73f-p106">假设某个 **Recordset** 包含名为 *firstName*、*middleInitial* 和 *lastName* 的三个字段。请将 **Sort** 属性设置为字符串 ""，这将按姓氏以降序对 **Recordset** 排列，然后按名字以升序排列。中间名将被忽略。</span><span class="sxs-lookup"><span data-stu-id="cf73f-p106">Suppose a **Recordset** contains three fields named *firstName*, *middleInitial*, and *lastName*. Set the **Sort** property to the string "", which will order the **Recordset** by last name in descending order and then by first name in ascending order. The middle initial is ignored.</span></span>

<span data-ttu-id="cf73f-p107">不能将排序条件字符串中引用的字段命名为"ASC"或"DESC"，因为这些名称与关键字 **ASC** 和 **DESC** 冲突。在返回 **Recordset** 的查询中，可以使用 **AS** 关键字为具有冲突名称的字段指定一个别名。</span><span class="sxs-lookup"><span data-stu-id="cf73f-p107">No field referenced in a sort criteria string can be named "ASC" or "DESC" because those names conflict with the keywords **ASC** and **DESC**. Give a field with a conflicting name an alias by using the **AS** keyword in the query that returns the **Recordset**.</span></span>

<span data-ttu-id="cf73f-124">有关 **Recordset** 筛选的更多详细信息，请参阅本主题中稍后介绍的"对结果进行筛选"。</span><span class="sxs-lookup"><span data-stu-id="cf73f-124">For more details about **Recordset** filtering, see Filtering the Results later in this topic.</span></span>

## <a name="finding-a-specific-record"></a><span data-ttu-id="cf73f-125">查找特定记录</span><span class="sxs-lookup"><span data-stu-id="cf73f-125">Finding a specific record</span></span>

<span data-ttu-id="cf73f-p108">ADO 提供了用来在 [Recordset](find-method-ado.md) 中查找特定记录的 [Find](seek-method-ado.md) 和 **Seek** 方法。 **Find** 方法受多种提供程序支持，但是仅限于单个搜索条件。 **Seek** 方法支持按多个条件进行搜索，但是能够支持它的提供程序不太多。</span><span class="sxs-lookup"><span data-stu-id="cf73f-p108">ADO provides the [Find](find-method-ado.md) and [Seek](seek-method-ado.md) methods for locating a particular record in a **Recordset**. The **Find** method is supported by a variety of providers but is limited to a single search criterion. The **Seek** method supports searching on multiple criteria, but is not supported by many providers.</span></span>

<span data-ttu-id="cf73f-p109">字段的索引可以大大增强 **Recordset** 对象的 **Find** 方法、 **Sort** 属性和 **Filter** 属性的性能。对于 **Field** 对象，可以通过设置 [Optimize](optimize-property-dynamic-ado.md) 动态属性来为其创建内部索引。当您将 **CursorLocation** 属性设置为 **adUseClient** 时，这个动态属性会添加到 [Field](cursorlocation-property-ado.md) 对象的 **Properties** 集合中。请记住，这个索引是 ADO 的内部索引，您不能获取对它的访问或者将其用于任何其他目的。而且，这个索引不同于 **Recordset** 对象的 [Index](index-property-ado.md) 属性。</span><span class="sxs-lookup"><span data-stu-id="cf73f-p109">Indexes on fields can greatly enhance the performance of the **Recordset** object's **Find** method and **Sort** and **Filter** properties. You can create an internal index for a **Field** object by setting its dynamic [Optimize](optimize-property-dynamic-ado.md) property. This dynamic property is added to the **Field** object's **Properties** collection when you set the [CursorLocation](cursorlocation-property-ado.md) property to **adUseClient**. Remember that this index is internal to ADO — you cannot gain access to it or use it for any other purpose. Also, this index is distinct from the **Recordset** object's [Index](index-property-ado.md) property.</span></span>

<span data-ttu-id="cf73f-p110">**Find** 方法可在 **Recordset** 的列（字段）中快速查找值。通常，可以使用 **Optimize** 属性为列创建索引，从而提高对于列执行 **Find** 方法的速度。</span><span class="sxs-lookup"><span data-stu-id="cf73f-p110">The **Find** method quickly locates a value within a column (field) of a **Recordset**. You can often improve the speed of the **Find** method's operation on a column by using the **Optimize** property to create an index on it.</span></span>

<span data-ttu-id="cf73f-p111">**Find** 方法将搜索限制为一个字段的内容。 **Seek** 方法要求有索引和其他限制。如果您需要搜索不作为索引基础的多个字段，或者您的提供程序不支持索引，则可以使用 **Recordset** 对象的 **Filter** 属性来限制结果。</span><span class="sxs-lookup"><span data-stu-id="cf73f-p111">The **Find** method limits your search to the contents of one field. The **Seek** method requires that you have an index and has other limitations as well. If you need to search on multiple fields that aren't the basis of an index, or if your provider does not support indexes, you can limit your results using the **Filter** property of the **Recordset** object.</span></span>

### <a name="find"></a><span data-ttu-id="cf73f-139">Find</span><span class="sxs-lookup"><span data-stu-id="cf73f-139">Find</span></span>

<span data-ttu-id="cf73f-p112">**Find** 方法在 **Recordset** 中搜索满足指定条件的行。还可以指定搜索方向、起始行以及与起始行的偏移量。如果满足条件，则当前行的位置将设置到找到的记录上；否则，当前行的位置将设置到 **Recordset** 的末尾（或开头），具体取决于搜索方向。</span><span class="sxs-lookup"><span data-stu-id="cf73f-p112">The **Find** method searches a **Recordset** for the row that satisfies a specified criterion. Optionally, the direction of the search, starting row, and offset from the starting row may be specified. If the criterion is met, the current row position is set on the found record; otherwise, the position is set to the end (or start) of the **Recordset**, depending on search direction.</span></span>

<span data-ttu-id="cf73f-p113">只能为搜索条件指定一个单列名称。换言之，此方法不支持多列搜索。</span><span class="sxs-lookup"><span data-stu-id="cf73f-p113">Only a single-column name may be specified for the criterion. In other words, this method does not support multi-column searches.</span></span>

<span data-ttu-id="cf73f-145">条件的比较运算符可以**\>** 是 "" (大于)、**\<**"(小于号)、" = "(等)、"\>= "(大于或等于)、"\<= "(小于或等于)、" = "(小于或等于\<\>)、" "(不等于) 或" LIKE "(模式匹配)。</span><span class="sxs-lookup"><span data-stu-id="cf73f-145">The comparison operator for the criterion may be "**\>**" (greater than), "**\<**" (less than), "=" (equal), "\>=" (greater than or equal), "\<=" (less than or equal), "\<\>" (not equal), or "LIKE" (pattern matching).</span></span>

<span data-ttu-id="cf73f-146">条件值可以是字符串、浮点数或日期。</span><span class="sxs-lookup"><span data-stu-id="cf73f-146">The criterion value may be a string, floating-point number, or date.</span></span> <span data-ttu-id="cf73f-147">字符串值用单引号或 "\#" (数字符号) 标记分隔 (例如, "state = ' WA '" 或 "state = \#WA\#")。</span><span class="sxs-lookup"><span data-stu-id="cf73f-147">String values are delimited with single quotes or "\#" (number sign) marks (for example, "state = 'WA'" or "state = \#WA\#").</span></span> <span data-ttu-id="cf73f-148">日期值使用\#"" (数字符号) 标记 (例如, "开始\_日期\> \#7/22/97\#") 进行分隔。</span><span class="sxs-lookup"><span data-stu-id="cf73f-148">Date values are delimited with "\#" (number sign) marks (for example, "start\_date \> \#7/22/97\#").</span></span>

<span data-ttu-id="cf73f-p115">如果比较运算符是"like"，则字符串值中可以包含星号 (\*)，以查找一次或多次出现的任何字符或子字符串。例如，"state like 'M\*'"与 Maine 和 Massachusetts 相匹配。还可以使用前导和尾随星号来查找包含在值中的子字符串。例如，"state like '\*as\*'"与 Alaska、Arkansas 和 Massachusetts 相匹配。</span><span class="sxs-lookup"><span data-stu-id="cf73f-p115">If the comparison operator is "like", the string value may contain an asterisk (\*) to find one or more occurrences of any character or substring. For example, "state like 'M\*'" matches Maine and Massachusetts. You can also use leading and trailing asterisks to find a substring contained within the values. For example, "state like '\*as\*'" matches Alaska, Arkansas, and Massachusetts.</span></span>

<span data-ttu-id="cf73f-p116">星号只能用在条件字符串的末尾或者与条件字符串的开头和末尾处的字符一起使用，如上所示。不能将星号用作前导通配符 ('\*str') 或嵌入通配符 ('s\*r')，否则将导致错误。</span><span class="sxs-lookup"><span data-stu-id="cf73f-p116">Asterisks can be used only at the end of a criteria string or together at both the beginning and end of a criteria string, as shown above. You cannot use the asterisk as a leading wildcard ('\*str') or embedded wildcard ('s\*r'). This will cause an error.</span></span>

### <a name="seek-and-index"></a><span data-ttu-id="cf73f-156">Seek 和 Index</span><span class="sxs-lookup"><span data-stu-id="cf73f-156">Seek and Index</span></span>

<span data-ttu-id="cf73f-p117">如果基础提供程序支持 **Recordset** 对象的索引，则可以将 **Seek** 方法与 **Index** 属性一起使用。使用 [Supports](supports-method-ado.md)**(adSeek)** 方法可以确定基础提供程序是否支持 **Seek**，使用 **Supports(adIndex)** 方法可以确定提供程序是否支持索引。（例如，[OLE DB Provider for Microsoft Jet](microsoft-ole-db-provider-for-microsoft-jet.md) 支持 **Seek** 和 **Index**。）</span><span class="sxs-lookup"><span data-stu-id="cf73f-p117">Use the **Seek** method in conjunction with the **Index** property if the underlying provider supports indexes on the **Recordset** object. Use the [Supports](supports-method-ado.md)**(adSeek)** method to determine whether the underlying provider supports **Seek**, and the **Supports(adIndex)** method to determine whether the provider supports indexes. (For example, the [OLE DB Provider for Microsoft Jet](microsoft-ole-db-provider-for-microsoft-jet.md) supports **Seek** and **Index**.)</span></span>

<span data-ttu-id="cf73f-p118">如果 **Seek** 找不到所需的行，不会发生错误，只是将该行置于 **Recordset** 的末尾。将 **Index** 属性设置为所需索引，然后执行此方法。</span><span class="sxs-lookup"><span data-stu-id="cf73f-p118">If **Seek** does not find the desired row, no error occurs, and the row is positioned at the end of the **Recordset**. Set the **Index** property to the desired index before executing this method.</span></span>

<span data-ttu-id="cf73f-p119">只有服务器端游标才支持此方法。当 **Recordset** 对象的 [CursorLocation](cursorlocation-property-ado.md) 属性值为 **adUseClient** 时，不支持 Seek。</span><span class="sxs-lookup"><span data-stu-id="cf73f-p119">This method is supported only with server-side cursors. Seek is not supported when the **Recordset** object's [CursorLocation](cursorlocation-property-ado.md) property value is **adUseClient**.</span></span>

<span data-ttu-id="cf73f-164">只有当 **Recordset** 对象是用 [adCmdTableDirect](commandtypeenum.md) 的 **CommandTypeEnum** 值打开时，才能使用 Seek 方法。</span><span class="sxs-lookup"><span data-stu-id="cf73f-164">This method can be used only when the **Recordset** object has been opened with a [CommandTypeEnum](commandtypeenum.md) value of **adCmdTableDirect**.</span></span>

## <a name="filtering-the-results"></a><span data-ttu-id="cf73f-165">筛选结果</span><span class="sxs-lookup"><span data-stu-id="cf73f-165">Filtering the results</span></span>

<span data-ttu-id="cf73f-p120">**Find** 方法将搜索限制为一个字段的内容。 **Seek** 方法要求有索引和其他限制。如果您需要搜索不作为索引基础的多个字段，或者您的提供程序不支持索引，则可以使用 **Recordset** 对象的 **Filter** 属性来限制结果。</span><span class="sxs-lookup"><span data-stu-id="cf73f-p120">The **Find** method limits your search to the contents of one field. The **Seek** method requires that you have an index and has other limitations as well. If you need to search on multiple fields that are not the basis of an index or if your provider does not support indexes, you can limit your results using the **Filter** property of the **Recordset** object.</span></span>

<span data-ttu-id="cf73f-p121">使用 **Filter** 属性，可以有选择地筛选出 **Recordset** 对象中的记录。所筛选的 **Recordset** 将成为当前游标，这意味着不满足 **Filter** 条件的记录在 **Recordset** 中将不可用，直到删除 **Filter** 。其他基于当前游标返回值的属性（如 **AbsolutePosition** 、 **AbsolutePage** 、 **RecordCount** 和 **PageCount** ）也会受到影响。这是因为如果将 **Filter** 属性设置为特定值，会将当前的记录移到满足新值的第一个记录。</span><span class="sxs-lookup"><span data-stu-id="cf73f-p121">Use the **Filter** property to selectively screen out records in a **Recordset** object. The filtered **Recordset** becomes the current cursor, which means that records that do not satisfy the **Filter** criteria are not available in the **Recordset** until the **Filter** is removed. Other properties that return values based on the current cursor are affected, such as **AbsolutePosition**, **AbsolutePage**, **RecordCount**, and **PageCount**. This is because setting the **Filter** property to a specific value will move the current record to the first record that satisfies the new value.</span></span>

<span data-ttu-id="cf73f-p122">**Filter** 属性采用变量型参数。此值表示使用 **Filter** 属性的三种方法之一：条件字符串、 **FilterGroupEnum** 常量或书签数组。有关详细信息，请参阅本主题中稍后介绍的"用条件字符串筛选"、"用常量筛选"和"用书签筛选"。</span><span class="sxs-lookup"><span data-stu-id="cf73f-p122">The **Filter** property takes a variant argument. This value represents one of three methods for using the **Filter** property: a criteria string, a **FilterGroupEnum** constant, or an array of bookmarks. For more information, see Filtering with a Criteria String, Filtering with a Constant, and Filtering with Bookmarks later in this topic.</span></span>

> [!NOTE]
> <span data-ttu-id="cf73f-176">[!注释] 如果您知道要选择哪些数据，那么，与依赖于 **Filter** 属性相比，使用能够有效筛选结果集的 SQL 语句来打开 **Recordset** 通常效率更高。</span><span class="sxs-lookup"><span data-stu-id="cf73f-176">When you know the data you want to select, it is usually more efficient to open a **Recordset** with a SQL statement that effectively filters the result set, rather than relying on the **Filter** property.</span></span>

<span data-ttu-id="cf73f-p123">若要从 **Recordset** 中删除筛选，请使用 **adFilterNone** 常量。将 **Filter** 属性设置为零长度字符串 ("") 与使用 **adFilterNone** 常量等效。</span><span class="sxs-lookup"><span data-stu-id="cf73f-p123">To remove a filter from a **Recordset**, use the **adFilterNone** constant. Setting the **Filter** property to a zero-length string ("") has the same effect as using the **adFilterNone** constant.</span></span>

### <a name="filtering-with-a-criteria-string"></a><span data-ttu-id="cf73f-179">使用条件字符串进行筛选</span><span class="sxs-lookup"><span data-stu-id="cf73f-179">Filtering with a criteria string</span></span>

<span data-ttu-id="cf73f-180">条件字符串由*FieldName 运算符值*形式的子句组成 (例如, "LastName = ' Smith '")。</span><span class="sxs-lookup"><span data-stu-id="cf73f-180">The criteria string is made up of clauses in the form *FieldName Operator Value* (for example, "LastName = 'Smith'").</span></span> <span data-ttu-id="cf73f-181">您可以使用 AND（例如 "LastName = 'Smith' AND FirstName = 'John'"）和 OR 来连接各个子句。</span><span class="sxs-lookup"><span data-stu-id="cf73f-181">You can create compound clauses by concatenating individual clauses with AND (for example, "LastName = 'Smith' AND FirstName = 'John'") and OR (for example, ).</span></span> <span data-ttu-id="cf73f-182">您可以通过使用 AND（例如 "LastName = 'Smith' AND FirstName = 'John'"）和 OR（例如 "LastName = 'Smith' OR LastName = 'Jones'"）来连接各个子句，以创建复合子句。</span><span class="sxs-lookup"><span data-stu-id="cf73f-182">You can create compound clauses by concatenating individual clauses with AND (for example, "LastName = 'Smith' AND FirstName = 'John'") and OR (for example, "LastName = 'Smith' OR LastName = 'Jones'").</span></span> <span data-ttu-id="cf73f-183">条件字符串的使用准则如下：</span><span class="sxs-lookup"><span data-stu-id="cf73f-183">Use the following guidelines for criteria strings:</span></span>

- <span data-ttu-id="cf73f-p125">*FieldName* 必须是 **Recordset** 中的有效字段名。如果字段名中包含空格，则必须用方括号将字段名括起来。</span><span class="sxs-lookup"><span data-stu-id="cf73f-p125">*FieldName* must be a valid field name from the **Recordset**. If the field name contains spaces, you must enclose the name in square brackets.</span></span>

- <span data-ttu-id="cf73f-186">*运算符*必须为以下项\<之一:、 \>、 \<=、 \>=、 \< \>、= 或 LIKE。</span><span class="sxs-lookup"><span data-stu-id="cf73f-186">*Operator* must be one of the following: \<, \>, \<=, \>=, \<\>, =, or LIKE.</span></span>

- <span data-ttu-id="cf73f-187">*value*是用于比较字段值的值 (例如, "Smith"、 \#8/24/95\#、12.345 或 $50.00)。</span><span class="sxs-lookup"><span data-stu-id="cf73f-187">*Value* is the value with which you will compare the field values (for example, 'Smith', \#8/24/95\#, 12.345, or $50.00).</span></span> <span data-ttu-id="cf73f-188">对字符串使用单引号 ('), 并对日期使用井\#号 ()。</span><span class="sxs-lookup"><span data-stu-id="cf73f-188">Use single quotation marks (') with strings and pound signs (\#) with dates.</span></span> <span data-ttu-id="cf73f-189">对于数字，可以使用小数点、美元符号和科学记数法。</span><span class="sxs-lookup"><span data-stu-id="cf73f-189">For numbers, you can use decimal points, dollar signs, and scientific notation.</span></span> <span data-ttu-id="cf73f-190">如果 *Operator* 是 LIKE，则 *Value* 可以使用通配符。</span><span class="sxs-lookup"><span data-stu-id="cf73f-190">If *Operator* is LIKE, *Value* can use wildcards.</span></span> <span data-ttu-id="cf73f-191">仅星号 (\*) 和百分比符号 (%)允许使用通配符, 并且它们必须是字符串中的最后一个字符。</span><span class="sxs-lookup"><span data-stu-id="cf73f-191">Only the asterisk (\*) and percent sign (%) wildcards are allowed, and they must be the last character in the string.</span></span> <span data-ttu-id="cf73f-192">*Value* 不能是 null。</span><span class="sxs-lookup"><span data-stu-id="cf73f-192">*Value* cannot be null.</span></span>
    
  > [!NOTE]
  > <span data-ttu-id="cf73f-193">若要在筛选*值*中包含单引号 ('), 请使用两个单引号表示一个。</span><span class="sxs-lookup"><span data-stu-id="cf73f-193">To include single quotation marks (') in the filter *Value*, use two single quotation marks to represent one.</span></span> <span data-ttu-id="cf73f-194">例如, 若要在*O'Malley*上进行筛选, 则条件字符串应为 "col1 = ' O ' ' Malley '"。</span><span class="sxs-lookup"><span data-stu-id="cf73f-194">For example, to filter on *O'Malley*, the criteria string should be "col1 = 'O''Malley'".</span></span> 
  > 
  > <span data-ttu-id="cf73f-195">若要在筛选值的开头和结尾包含单引号, 请将字符串括在井号 (#) 中。</span><span class="sxs-lookup"><span data-stu-id="cf73f-195">To include single quotation marks at both the beginning and the end of the filter value, enclose the string in pound signs (#).</span></span> <span data-ttu-id="cf73f-196">例如, 若要筛选 *"1"*, 条件字符串应为 "col1 = # ' 1 ' #"。</span><span class="sxs-lookup"><span data-stu-id="cf73f-196">For example, to filter on *'1'*, the criteria string should be "col1 = #'1'#".</span></span>

<span data-ttu-id="cf73f-p129">AND 和 OR 之间并没有优先级的区别。可以使用圆括号将子句分组。但是不能先将由 OR 连接的子句分组然后通过 AND 将该组与其他子句连接，如下所示：</span><span class="sxs-lookup"><span data-stu-id="cf73f-p129">There is no precedence between AND and OR. Clauses can be grouped within parentheses. However, you cannot group clauses joined by an OR and then join the group to another clause with an AND, like this:</span></span>

```vb 
 
(LastName = 'Smith' OR LastName = 'Jones') AND FirstName = 'John' 
```

<span data-ttu-id="cf73f-200">而是应当按如下方式构造此筛选：</span><span class="sxs-lookup"><span data-stu-id="cf73f-200">Instead, you would construct this filter as:</span></span>

```vb 
 
(LastName = 'Smith' AND FirstName = 'John') OR (LastName = 'Jones' AND FirstName = 'John') 
```

<span data-ttu-id="cf73f-201">在 LIKE 子句中, 可以在模式的开头和结尾使用通配符 (例如, "我喜欢 '\*mit\*'"), 也可以在模式的结尾处使用通配符 (例如,), 或者仅在模式的结尾处使用通配符 (例如, lastname 类似于 "Smit\*")。</span><span class="sxs-lookup"><span data-stu-id="cf73f-201">In a LIKE clause, you can use a wildcard at the beginning and end of the pattern (for example, LastName Like '\*mit\*') or only at the end of the pattern (for example, ) or only at the end of the pattern (for example, LastName Like 'Smit\*').</span></span>

### <a name="filtering-with-a-constant"></a><span data-ttu-id="cf73f-202">使用常量进行筛选</span><span class="sxs-lookup"><span data-stu-id="cf73f-202">Filtering with a constant</span></span>

<span data-ttu-id="cf73f-203">可以使用下列常量来筛选 **Recordset**。</span><span class="sxs-lookup"><span data-stu-id="cf73f-203">The following constants are available for filtering **Recordsets**.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="cf73f-204">常量</span><span class="sxs-lookup"><span data-stu-id="cf73f-204">Constant</span></span></p></th>
<th><p><span data-ttu-id="cf73f-205">说明</span><span class="sxs-lookup"><span data-stu-id="cf73f-205">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cf73f-206"><strong>adFilterAffectedRecords</strong></span><span class="sxs-lookup"><span data-stu-id="cf73f-206"><strong>adFilterAffectedRecords</strong></span></span></p></td>
<td><p><span data-ttu-id="cf73f-207">用于仅查看受上一次 <strong>Delete</strong> 、 <strong>Resync</strong> 、 <strong>UpdateBatch</strong> 或 <strong>CancelBatch</strong> 调用影响的记录的筛选器。</span><span class="sxs-lookup"><span data-stu-id="cf73f-207">Filters for viewing only records effected by the last <strong>Delete</strong>, <strong>Resync</strong>, <strong>UpdateBatch</strong>, or <strong>CancelBatch</strong> call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cf73f-208"><strong>adFilterConflictingRecords</strong></span><span class="sxs-lookup"><span data-stu-id="cf73f-208"><strong>adFilterConflictingRecords</strong></span></span></p></td>
<td><p><span data-ttu-id="cf73f-209">用于查看使上一次批更新失败的记录的筛选器。</span><span class="sxs-lookup"><span data-stu-id="cf73f-209">Filters for viewing the records that failed the last batch update.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cf73f-210"><strong>adFilterFetchedRecords</strong></span><span class="sxs-lookup"><span data-stu-id="cf73f-210"><strong>adFilterFetchedRecords</strong></span></span></p></td>
<td><p><span data-ttu-id="cf73f-211">用于查看当前缓存中的记录（即，上一次从数据库检索记录的调用的结果）的筛选器。</span><span class="sxs-lookup"><span data-stu-id="cf73f-211">Filters for viewing the records in the current cache — that is, the results of the last call to retrieve records from the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cf73f-212"><strong>adFilterNone</strong></span><span class="sxs-lookup"><span data-stu-id="cf73f-212"><strong>adFilterNone</strong></span></span></p></td>
<td><p><span data-ttu-id="cf73f-213">删除当前的筛选并还原所有的记录以进行查看。</span><span class="sxs-lookup"><span data-stu-id="cf73f-213">Removes the current filter and restores all records for viewing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cf73f-214"><strong>adFilterPendingRecords</strong></span><span class="sxs-lookup"><span data-stu-id="cf73f-214"><strong>adFilterPendingRecords</strong></span></span></p></td>
<td><p><span data-ttu-id="cf73f-p130">用于仅查看已更改但尚未发送到服务器的记录的筛选器。仅适用于批更新模式。</span><span class="sxs-lookup"><span data-stu-id="cf73f-p130">Filters for viewing only records that have changed but have not yet been sent to the server. Applicable only for batch update mode.</span></span></p></td>
</tr>
</tbody>
</table>

<br/>

<span data-ttu-id="cf73f-217">使用筛选常量，更便于解决批更新模式下的个别记录冲突问题，例如，允许您只查看上次调用 **UpdateBatch** 方法过程中受影响的记录，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="cf73f-217">The filter constants make it easier to resolve individual record conflicts during batch update mode by allowing you to view, for example, only those records that were effected during the last **UpdateBatch** method call, as shown in the following example:</span></span>

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

### <a name="filtering-with-bookmarks"></a><span data-ttu-id="cf73f-218">使用书签进行筛选</span><span class="sxs-lookup"><span data-stu-id="cf73f-218">Filtering with bookmarks</span></span>

<span data-ttu-id="cf73f-p131">最后，可以将变量型书签数组传递给 **Filter** 属性。所得到的游标将只包含将书签传递给该属性的记录。以下代码示例从 **Recordset** 中 *ProductName* 字段中具有“B”的记录创建一个书签数组，然后将该数组传递给 **Filter** 属性，并显示有关所得到的筛选 **Recordset** 的信息。</span><span class="sxs-lookup"><span data-stu-id="cf73f-p131">Finally, you can pass a variant array of bookmarks to the **Filter** property. The resulting cursor will contain only those records whose bookmark was passed in to the property. The following code example creates an array of bookmarks from the records in a **Recordset** which have a "B" in the *ProductName* field. It then passes the array to the **Filter** property and displays information about the resulting filtered **Recordset**.</span></span>

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

## <a name="creating-a-clone-of-a-recordset"></a><span data-ttu-id="cf73f-223">创建 Recordset 的复本</span><span class="sxs-lookup"><span data-stu-id="cf73f-223">Creating a clone of a Recordset</span></span>

<span data-ttu-id="cf73f-p132">可以使用 **Clone** 方法创建多个重复的 **Recordset** 对象，尤其是要在给定记录集中保留多个当前记录时。使用 **Clone** 方法比采用与原始对象相同的定义创建和打开一个新的 **Recordset** 对象效率更高。</span><span class="sxs-lookup"><span data-stu-id="cf73f-p132">Use the **Clone** method to create multiple, duplicate **Recordset** objects, particularly if you want to maintain more than one current record in a given set of records. Using the **Clone** method is more efficient than creating and opening a new **Recordset** object with the same definition as the original.</span></span>

<span data-ttu-id="cf73f-p133">新建副本的当前记录最初设置为第一个记录。所克隆的 **Recordset** 中当前记录的指针不能与初始记录集同步，反之亦然。可以在每个 **Recordset** 中单独导航。</span><span class="sxs-lookup"><span data-stu-id="cf73f-p133">The current record of a newly created clone is originally set to the first record. The current record pointer in a cloned **Recordset** is not synchronized with the original or vice versa. You can navigate independently in each **Recordset**.</span></span>

<span data-ttu-id="cf73f-p134">无论游标类型是什么，对一个 **Recordset** 对象所做的更改可以在该对象的所有副本中体现出来。但是，对原始 [Recordset](requery-method-ado.md) 对象执行 **Requery** 后，副本将不再与原始对象同步。</span><span class="sxs-lookup"><span data-stu-id="cf73f-p134">Changes you make to one **Recordset** object are visible in all of its clones regardless of cursor type. However, after you execute [Requery](requery-method-ado.md) on the original **Recordset**, the clones will no longer be synchronized to the original.</span></span>

<span data-ttu-id="cf73f-231">关闭原始 **Recordset** 不会关闭其副本，同样，关闭副本也不会关闭原始对象或其他任何副本。</span><span class="sxs-lookup"><span data-stu-id="cf73f-231">Closing the original **Recordset** does not close its copies, nor does closing a copy close the original or any of the other copies.</span></span>

<span data-ttu-id="cf73f-p135">只有当 **Recordset** 对象支持书签时，才能克隆该对象。书签值是可以互换的；即，一个 **Recordset** 对象中的书签引用可以引用其任何副本中的同一个记录。</span><span class="sxs-lookup"><span data-stu-id="cf73f-p135">You can clone a **Recordset** object only if it supports bookmarks. Bookmark values are interchangeable; that is, a bookmark reference from one **Recordset** object refers to the same record in any of its clones.</span></span>

