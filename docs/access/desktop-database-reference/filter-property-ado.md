---
title: Filter 属性 (ADO)
TOCTitle: Filter property (ADO)
ms:assetid: 5abc528a-a6ee-34de-5d44-a3249194b0a0
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249314(v=office.15)
ms:contentKeyID: 48545053
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 193cf5db350fdf0b30fe19da9a61026d1cd39aa9
ms.sourcegitcommit: 45feafb3b55de0402dddf5548c0c1c43a0eabafd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2018
ms.locfileid: "26026468"
---
# <a name="filter-property-ado"></a><span data-ttu-id="bce9c-102">Filter 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="bce9c-102">Filter property (ADO)</span></span>


<span data-ttu-id="bce9c-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="bce9c-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="bce9c-104">指示 [Recordset](recordset-object-ado.md) 中数据的筛选条件。</span><span class="sxs-lookup"><span data-stu-id="bce9c-104">Indicates a filter for data in a [Recordset](recordset-object-ado.md).</span></span>

## <a name="settings-and-return-values"></a><span data-ttu-id="bce9c-105">设置和返回值</span><span class="sxs-lookup"><span data-stu-id="bce9c-105">Settings and return values</span></span>

<span data-ttu-id="bce9c-106">设置或返回一个 **Variant** 值，该值可包含以下内容之一：</span><span class="sxs-lookup"><span data-stu-id="bce9c-106">Sets or returns a **Variant** value, which can contain one of the following:</span></span>

  - <span data-ttu-id="bce9c-107">**条件字符串**  由一个或多个用 **AND** 或 **OR** 运算符连接的子句组成的字符串。</span><span class="sxs-lookup"><span data-stu-id="bce9c-107">**Criteria string** — a string made up of one or more individual clauses concatenated with **AND** or **OR** operators.</span></span>

  - <span data-ttu-id="bce9c-108">**书签数组**  指向 **Recordset** 对象中的记录的唯一书签值数组。</span><span class="sxs-lookup"><span data-stu-id="bce9c-108">**Array of bookmarks** — an array of unique bookmark values that point to records in the **Recordset** object.</span></span>

  - <span data-ttu-id="bce9c-109">一个 [FilterGroupEnum](filtergroupenum.md) 值。</span><span class="sxs-lookup"><span data-stu-id="bce9c-109">A [FilterGroupEnum](filtergroupenum.md) value.</span></span>

## <a name="remarks"></a><span data-ttu-id="bce9c-110">备注</span><span class="sxs-lookup"><span data-stu-id="bce9c-110">Remarks</span></span>

<span data-ttu-id="bce9c-p101">使用 **Filter** 属性可以有选择地屏蔽 **Recordset** 对象中的记录。经过筛选的 **Recordset** 成为当前游标。这将影响基于当前游标返回值的其他属性，如 [AbsolutePosition](absoluteposition-property-ado.md)、[AbsolutePage](absolutepage-property-ado.md)、[RecordCount](recordcount-property-ado.md) 和 [PageCount](pagecount-property-ado.md)。因为将 **Filter** 属性设置为特定值将移动当前记录使其成为满足新值的第一条记录。</span><span class="sxs-lookup"><span data-stu-id="bce9c-p101">Use the **Filter** property to selectively screen out records in a **Recordset** object. The filtered **Recordset** becomes the current cursor. Other properties that return values based on the current cursor are affected, such as [AbsolutePosition](absoluteposition-property-ado.md), [AbsolutePage](absolutepage-property-ado.md), [RecordCount](recordcount-property-ado.md), and [PageCount](pagecount-property-ado.md). This is because setting the **Filter** property to a specific value will move the current record to the first record that satisfies the new value.</span></span>

<span data-ttu-id="bce9c-115">条件字符串由*FieldName 运算符值*形式的子句组成 (例如，"LastName = 'Smith'")。</span><span class="sxs-lookup"><span data-stu-id="bce9c-115">The criteria string is made up of clauses in the form *FieldName-Operator-Value* (for example, "LastName = 'Smith'").</span></span> <span data-ttu-id="bce9c-116">您可以通过将单个子句与**和**创建复合子句 (例如，"LastName = 'Smith' 和 FirstName = John") 或**OR** (例如，")。</span><span class="sxs-lookup"><span data-stu-id="bce9c-116">You can create compound clauses by concatenating individual clauses with **AND** (for example, "LastName = 'Smith' AND FirstName = 'John'") or **OR** (for example, ").</span></span> <span data-ttu-id="bce9c-117">您可以通过将单个子句与**和**创建复合子句 (例如，"LastName = 'Smith' 和 FirstName = John") 或**OR** (例如，"LastName = 'Smith' 或姓氏 = Jones")。</span><span class="sxs-lookup"><span data-stu-id="bce9c-117">You can create compound clauses by concatenating individual clauses with **AND** (for example, "LastName = 'Smith' AND FirstName = 'John'") or **OR** (for example, "LastName = 'Smith' OR LastName = 'Jones'").</span></span> <span data-ttu-id="bce9c-118">对条件字符串使用以下准则：</span><span class="sxs-lookup"><span data-stu-id="bce9c-118">Use the following guidelines for criteria strings:</span></span>

  - <span data-ttu-id="bce9c-119">*FieldName*必须是有效的字段名称从**记录集**。</span><span class="sxs-lookup"><span data-stu-id="bce9c-119">*FieldName* must be a valid field name from the **Recordset**.</span></span> <span data-ttu-id="bce9c-120">如果字段名中包含空格，则必须用方括号将字段名括起来。</span><span class="sxs-lookup"><span data-stu-id="bce9c-120">If the field name contains spaces, you must enclose the name in square brackets.</span></span>

  - <span data-ttu-id="bce9c-121">*Operator*必须是以下项之一： \<， \>， \<= \>= \< \>，=，或**类似**。</span><span class="sxs-lookup"><span data-stu-id="bce9c-121">*Operator* must be one of the following: \<, \>, \<=, \>=, \<\>, =, or **LIKE**.</span></span>

  - <span data-ttu-id="bce9c-122">*值*是将与其比较的字段值的值 (例如，'Smith'， \#8/24/95\#，12.345 或 $50.00)。</span><span class="sxs-lookup"><span data-stu-id="bce9c-122">*Value* is the value with which you will compare the field values (for example, 'Smith', \#8/24/95\#, 12.345, or $50.00).</span></span> <span data-ttu-id="bce9c-123">单引号使用字符串和井号 (\#) 与日期。</span><span class="sxs-lookup"><span data-stu-id="bce9c-123">Use single quotes with strings and pound signs (\#) with dates.</span></span> <span data-ttu-id="bce9c-124">对于数字，可以使用小数点、美元符号和科学记数法。</span><span class="sxs-lookup"><span data-stu-id="bce9c-124">For numbers, you can use decimal points, dollar signs, and scientific notation.</span></span> <span data-ttu-id="bce9c-125">如果*运算符\***类似**，*值\*可以使用通配符。</span><span class="sxs-lookup"><span data-stu-id="bce9c-125">If *Operator* is **LIKE**, *Value* can use wildcards.</span></span> <span data-ttu-id="bce9c-126">仅星号 (\*) 和百分号 （%） 允许使用通配符，并且它们必须在字符串中的最后一个字符。</span><span class="sxs-lookup"><span data-stu-id="bce9c-126">Only the asterisk (\*) and percent sign (%) wild cards are allowed, and they must be the last character in the string.</span></span> <span data-ttu-id="bce9c-127">*值*不能为 null。</span><span class="sxs-lookup"><span data-stu-id="bce9c-127">*Value* cannot be null.</span></span>

    > [!NOTE]
    > <span data-ttu-id="bce9c-p105">[!注释] 若要在筛选值中包含单引号 (')，则用两个单引号表示一个单引号。例如，若要筛选 O'Malley，则条件字符串应为 "col1 = 'O''Malley'"。若要在筛选值的开始和末尾均包含单引号，则使用井号 (#) 包围该字符串。例如，若要筛选 '1'，则条件字符串应为 "col1 = #'1'#"。</span><span class="sxs-lookup"><span data-stu-id="bce9c-p105">To include single quotation marks (') in the filter Value, use two single quotation marks to represent one. For example, to filter on O'Malley, the criteria string should be "col1 = 'O''Malley'". To include single quotation marks at both the beginning and the end of the filter value, enclose the string with pound signs (#). For example, to filter on '1', the criteria string should be "col1 = #'1'#".</span></span>

  - <span data-ttu-id="bce9c-p106">**AND** 和 **OR** 之间并没有优先级的区别。可以使用圆括号将子句分组。但是不能先将由 **OR** 连接的子句分组然后通过 **AND** 将该组与其他子句连接，如下所示：</span><span class="sxs-lookup"><span data-stu-id="bce9c-p106">There is no precedence between **AND** and **OR**. Clauses can be grouped within parentheses. However, you cannot group clauses joined by an **OR** and then join the group to another clause with an **AND**, like this:</span></span>

  - <span data-ttu-id="bce9c-135">可以按如下方法构造此筛选条件</span><span class="sxs-lookup"><span data-stu-id="bce9c-135">Instead, you would construct this filter as</span></span>

  - <span data-ttu-id="bce9c-136">在**LIKE**子句，您可以使用的开头和模式的末尾使用通配符 (例如，LastName Like '\*mit\*)，也可以只在模式的结尾 (例如，LastName Like' Smit\*)。</span><span class="sxs-lookup"><span data-stu-id="bce9c-136">In a **LIKE** clause, you can use a wildcard at the beginning and end of the pattern (for example, LastName Like '\*mit\*'), or only at the end of the pattern (for example, LastName Like 'Smit\*').</span></span>

<span data-ttu-id="bce9c-137">通过仅允许查看，例如仅允许查看上次调用 [UpdateBatch](updatebatch-method-ado.md) 方法的过程中涉及到的记录，筛选常量更便于解决批更新模式中的各个记录冲突。</span><span class="sxs-lookup"><span data-stu-id="bce9c-137">The filter constants make it easier to resolve individual record conflicts during batch update mode by allowing you to view, for example, only those records that were affected during the last [UpdateBatch](updatebatch-method-ado.md) method call.</span></span>

<span data-ttu-id="bce9c-p107">如果与基础数据冲突（例如，其他用户已经删除该记录），则不能成功设置 **Filter** 属性本身。此时，提供程序将向 [Errors](errors-collection-ado.md) 集合返回警告，但不会中断程序执行。只有所有请求的记录均存在冲突时才会产生运行时错误。使用 [Status](status-property-ado-recordset.md) 属性可定位发生冲突的记录。</span><span class="sxs-lookup"><span data-stu-id="bce9c-p107">Setting the **Filter** property itself may fail because of a conflict with the underlying data (for example, a record has already been deleted by another user). In such a case, the provider returns warnings to the [Errors](errors-collection-ado.md) collection but does not halt program execution. A run-time error occurs only if there are conflicts on all the requested records. Use the [Status](status-property-ado-recordset.md) property to locate records with conflicts.</span></span>

<span data-ttu-id="bce9c-142">将 **Filter** 属性设置为零长度字符串 ("") 与使用 **adFilterNone** 常量具有相同效果。</span><span class="sxs-lookup"><span data-stu-id="bce9c-142">Setting the **Filter** property to a zero-length string ("") has the same effect as using the **adFilterNone** constant.</span></span>

<span data-ttu-id="bce9c-p108">一旦设置了 **Filter** 属性，当前记录位置就会移至 **Recordset** 中已筛选记录子集的首条记录。同样，如果清除 **Filter** 属性，则当前记录位置将移至 **Recordset** 中的首条记录。</span><span class="sxs-lookup"><span data-stu-id="bce9c-p108">Whenever the **Filter** property is set, the current record position moves to the first record in the filtered subset of records in the **Recordset**. Similarly, when the **Filter** property is cleared, the current record position moves to the first record in the **Recordset**.</span></span>

<span data-ttu-id="bce9c-145">有关可与 [Filter](bookmark-property-ado.md) 属性一起用来生成数组的书签值的说明，请参阅 **Bookmark** 属性。</span><span class="sxs-lookup"><span data-stu-id="bce9c-145">See the [Bookmark](bookmark-property-ado.md) property for an explanation of bookmark values from which you can build an array to use with the **Filter** property.</span></span>

<span data-ttu-id="bce9c-146">仅**筛选器**条件字符串的形式 (如订购日期\>"12/31/1999年 ') 影响**Recordset**的内容。</span><span class="sxs-lookup"><span data-stu-id="bce9c-146">Only **Filters** in the form of Criteria Strings (e.g. OrderDate \> '12/31/1999') affect the contents of a persisted **Recordset**.</span></span> <span data-ttu-id="bce9c-147">通过 **Bookmark** 数组或使用 **FilterGroupEnum** 中的值创建的 **Filter** 不会影响持久 Recordset 的内容。</span><span class="sxs-lookup"><span data-stu-id="bce9c-147">**Filters** created with an Array of **Bookmarks** or using a value from the **FilterGroupEnum** will not affect the contents of the persisted Recordset.</span></span> <span data-ttu-id="bce9c-148">这些规则适用于通过客户端或服务器端游标创建的 **Recordset** 。</span><span class="sxs-lookup"><span data-stu-id="bce9c-148">These rules apply to **Recordsets** created with either client-side or server-side cursors.</span></span>

> [!NOTE]
> <span data-ttu-id="bce9c-p110">[!注释] 在批更新模式下，将 **adFilterPendingRecords** 标记应用于筛选和修改的 **Recordset** 时，如果筛选是基于单键表的键字段并且对该键字段值进行修改，则得到的 **Recordset** 将为空。如果满足以下条件之一，得到的 **Recordset** 就不为空：</span><span class="sxs-lookup"><span data-stu-id="bce9c-p110">When you apply the **adFilterPendingRecords** flag to a filtered and modified **Recordset** in the batch update mode, the resultant **Recordset** is empty if the filtering was based on the key field of a single-keyed table and the modification was made on the key field values. The resultant **Recordset** will be non-empty if one of the following is true:</span></span>
> - <span data-ttu-id="bce9c-151">基于单键表中的非键字段的筛选。</span><span class="sxs-lookup"><span data-stu-id="bce9c-151">The filtering was based on non-key fields in a single-keyed table.</span></span>
> - <span data-ttu-id="bce9c-152">基于多键表中的任何字段的筛选。</span><span class="sxs-lookup"><span data-stu-id="bce9c-152">The filtering was based on any fields in a multiple-keyed table.</span></span>
> - <span data-ttu-id="bce9c-153">对单键表中的非键字段进行修改。</span><span class="sxs-lookup"><span data-stu-id="bce9c-153">Modifications were made on non-key fields in a single-keyed table.</span></span>
> - <span data-ttu-id="bce9c-154">对多键表中的任何字段进行修改。</span><span class="sxs-lookup"><span data-stu-id="bce9c-154">Modifications were made on any fields in a multiple-keyed table.</span></span>

<span data-ttu-id="bce9c-p111">下表总结了在不同的筛选和修改方式组合下 **adFilterPendingRecords** 所产生的效果。左边的列显示的是可能的修改方式：可对任何非键字段、单键表中的键字段、或多键表中的任何键字段进行修改。最上面的行显示的是筛选条件：可以根据任何非键字段、单键表中的键字段、或多键表中的任何键字段进行筛选。交叉单元显示的是结果：+ 表示使用 **adFilterPendingRecords** 产生非空 **Recordset** ； **-** 表示空 **Recordset** 。</span><span class="sxs-lookup"><span data-stu-id="bce9c-p111">The following table summarizes the effects of **adFilterPendingRecords** in different combinations of filtering and modifications. The left column shows the possible modifications; modifications can be made on any of the non-keyed fields, on the key field in a single-keyed table, or on any of the key fields in a multiple-keyed table. The top row shows the filtering criterion; filtering can be based on any of the non-keyed fields, the key field in a single-keyed table, or any of the key fields in a multiple-keyed table. The intersecting cells show the results: + means that applying **adFilterPendingRecords** results in a non-empty **Recordset**; **-** means an empty **Recordset**.</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p><br />
</p></th>
<th><p><span data-ttu-id="bce9c-159">非键</span><span class="sxs-lookup"><span data-stu-id="bce9c-159">Non keys</span></span></p></th>
<th><p><span data-ttu-id="bce9c-160">单键</span><span class="sxs-lookup"><span data-stu-id="bce9c-160">Single Key</span></span></p></th>
<th><p><span data-ttu-id="bce9c-161">多键</span><span class="sxs-lookup"><span data-stu-id="bce9c-161">Multiple Keys</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bce9c-162">非键</span><span class="sxs-lookup"><span data-stu-id="bce9c-162">Non keys</span></span></p></td>
<td><p>+</p></td>
<td><p>+</p></td>
<td><p>+</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bce9c-163">单键</span><span class="sxs-lookup"><span data-stu-id="bce9c-163">Single Key</span></span></p></td>
<td><p>+</p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="bce9c-164">N/A</span><span class="sxs-lookup"><span data-stu-id="bce9c-164">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bce9c-165">多键</span><span class="sxs-lookup"><span data-stu-id="bce9c-165">Multiple Keys</span></span></p></td>
<td><p>+</p></td>
<td><p><span data-ttu-id="bce9c-166">N/A</span><span class="sxs-lookup"><span data-stu-id="bce9c-166">N/A</span></span></p></td>
<td><p>+</p></td>
</tr>
</tbody>
</table>

