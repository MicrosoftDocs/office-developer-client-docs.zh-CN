---
title: Field2.ValidationRule 属性 (DAO)
TOCTitle: ValidationRule Property
ms:assetid: 5464d2de-f3d7-5d6b-4fc5-66df6a5540cb
ms:mtpsurl: https://msdn.microsoft.com/library/Ff194105(v=office.15)
ms:contentKeyID: 48544896
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: cf640597405205987040d95033b2eb1ceee13867
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25922711"
---
# <a name="field2validationrule-property-dao"></a><span data-ttu-id="65d3f-102">Field2.ValidationRule 属性 (DAO)</span><span class="sxs-lookup"><span data-stu-id="65d3f-102">Field2.ValidationRule property (DAO)</span></span>


<span data-ttu-id="65d3f-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="65d3f-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="65d3f-p101">设置或返回一个值，当字段中的数据发生更改或被添加到表中时，该值将会验证该数据（仅适用于 Microsoft Access 工作区）。可读写 **String**。</span><span class="sxs-lookup"><span data-stu-id="65d3f-p101">Sets or returns a value that validates the data in a field as it's changed or added to a table (Microsoft Access workspaces only). Read/write **String**.</span></span>

## <a name="syntax"></a><span data-ttu-id="65d3f-106">语法</span><span class="sxs-lookup"><span data-stu-id="65d3f-106">Syntax</span></span>

<span data-ttu-id="65d3f-107">*表达式*。ValidationRule</span><span class="sxs-lookup"><span data-stu-id="65d3f-107">*expression* .ValidationRule</span></span>

<span data-ttu-id="65d3f-108">*表达式*一个返回**Field2**对象的表达式。</span><span class="sxs-lookup"><span data-stu-id="65d3f-108">*expression* An expression that returns a **Field2** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="65d3f-109">注解</span><span class="sxs-lookup"><span data-stu-id="65d3f-109">Remarks</span></span>

<span data-ttu-id="65d3f-p102">设置或返回值是一个 String，用于描述以不含 WHERE 保留字的 SQL WHERE 子句形式进行的比较。对于尚未追加到 **[Fields](fields-collection-dao.md)** 集合中的对象，该属性是可读写的。</span><span class="sxs-lookup"><span data-stu-id="65d3f-p102">The settings or return values is a String that describes a comparison in the form of an SQL WHERE clause without the WHERE reserved word. For an object not yet appended to the **[Fields](fields-collection-dao.md)** collection, this property is read/write.</span></span>

<span data-ttu-id="65d3f-p103">**ValidationRule** 属性确定字段是否包含有效数据。如果数据无效，则会发生可捕获的运行时错误。返回的错误消息是 **ValidationText** 属性的文本，或者是 **ValidationRule** 指定的表达式的文本（如果已指定）。</span><span class="sxs-lookup"><span data-stu-id="65d3f-p103">The **ValidationRule** property determines whether or not a field contains valid data. If the data is not valid, a trappable run-time error occurs. The returned error message is the text of the **ValidationText** property, if specified, or the text of the expression specified by **ValidationRule**.</span></span>

<span data-ttu-id="65d3f-115">对于 **Field2** 对象， **ValidationRule** 属性的用法取决于包含 **Field2** 对象所追加到的 **Fields** 集合的对象。</span><span class="sxs-lookup"><span data-stu-id="65d3f-115">For a **Field2** object, use of the **ValidationRule** property depends on the object that contains the **Fields** collection to which the **Field2** object is appended.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="65d3f-116">对象追加到</span><span class="sxs-lookup"><span data-stu-id="65d3f-116">Object appended to</span></span></p></th>
<th><p><span data-ttu-id="65d3f-117">用法</span><span class="sxs-lookup"><span data-stu-id="65d3f-117">Usage</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="65d3f-118"><strong>Index</strong></span><span class="sxs-lookup"><span data-stu-id="65d3f-118"><strong>Index</strong></span></span></p></td>
<td><p><span data-ttu-id="65d3f-119">不支持</span><span class="sxs-lookup"><span data-stu-id="65d3f-119">Not supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="65d3f-120"><strong>QueryDef</strong></span><span class="sxs-lookup"><span data-stu-id="65d3f-120"><strong>QueryDef</strong></span></span></p></td>
<td><p><span data-ttu-id="65d3f-121">只读</span><span class="sxs-lookup"><span data-stu-id="65d3f-121">Read-only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="65d3f-122"><strong>Recordset</strong></span><span class="sxs-lookup"><span data-stu-id="65d3f-122"><strong>Recordset</strong></span></span></p></td>
<td><p><span data-ttu-id="65d3f-123">只读</span><span class="sxs-lookup"><span data-stu-id="65d3f-123">Read-only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="65d3f-124"><strong>Relation</strong></span><span class="sxs-lookup"><span data-stu-id="65d3f-124"><strong>Relation</strong></span></span></p></td>
<td><p><span data-ttu-id="65d3f-125">不支持</span><span class="sxs-lookup"><span data-stu-id="65d3f-125">Not supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="65d3f-126"><strong>TableDef</strong></span><span class="sxs-lookup"><span data-stu-id="65d3f-126"><strong>TableDef</strong></span></span></p></td>
<td><p><span data-ttu-id="65d3f-127">可读写</span><span class="sxs-lookup"><span data-stu-id="65d3f-127">Read/write</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="65d3f-128">只对使用 Microsoft Access 数据库引擎的数据库支持验证。</span><span class="sxs-lookup"><span data-stu-id="65d3f-128">Validation is supported only for databases that use the Microsoft Access database engine.</span></span>

<span data-ttu-id="65d3f-p104">**Field2** 对象的 **ValidationRule** 属性所指定的字符串表达式只能引用该 **Field2**。该表达式不能引用用户定义的函数、SQL 聚合函数或查询。若要在 **Field2** 对象的 **ValidateOnSet** 属性设置为 **True** 时设置其 **ValidationRule** 属性，表达式必须成功分析（将字段名称作为隐含的操作数）且计算结果为 **True**。如果其 **ValidateOnSet** 属性设置为 **False**，则忽略 **ValidationRule** 属性设置。</span><span class="sxs-lookup"><span data-stu-id="65d3f-p104">The string expression specified by the **ValidationRule** property of a **Field2** object can refer only to that **Field2**. The expression can't refer to user-defined functions, SQL aggregate functions, or queries. To set a **Field2** object's **ValidationRule** property when its **ValidateOnSet** property setting is **True**, the expression must successfully parse (with the field name as an implied operand) and evaluate to **True**. If its **ValidateOnSet** property setting is **False**, the **ValidationRule** property setting is ignored.</span></span>


> [!NOTE]
> <P><span data-ttu-id="65d3f-133">如果属性设置为非整数值时，连接字符串和系统参数指定非美国十进制字符，例如逗号分隔 (例如，strRule ="价格&gt;" &amp; lngPrice，和 lngPrice = 125,50)，将导致错误时您的代码，尝试进行验证的任何数据。</span><span class="sxs-lookup"><span data-stu-id="65d3f-133">If you set the property to a string concatenated with a non-integer value, and the system parameters specify a non-U.S. decimal character such as a comma (for example, strRule = "PRICE &gt; " &amp; lngPrice, and lngPrice = 125,50), an error will result when your code attempts to validate any data.</span></span> <span data-ttu-id="65d3f-134">这是因为在连接过程中，将使用系统的默认小数字符，将数字转换为字符串，并且 Microsoft Access 数据库引擎 SQL 只接受美国格式小数字符。</span><span class="sxs-lookup"><span data-stu-id="65d3f-134">This is because during concatenation, the number will be converted to a string using your system's default decimal character, and Microsoft Access database engine SQL only accepts U.S. decimal characters.</span></span></P>


