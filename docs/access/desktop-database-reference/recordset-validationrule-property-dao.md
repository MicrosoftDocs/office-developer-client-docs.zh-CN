---
title: Recordset.ValidationRule Property (DAO)
TOCTitle: ValidationRule Property
ms:assetid: c9250c13-18fe-1ff7-7846-7872c49a1e3b
ms:mtpsurl: https://msdn.microsoft.com/library/Ff823208(v=office.15)
ms:contentKeyID: 48547671
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 8a70dc412cbca420ca689fbd956e56d5bcdea556
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25467162"
---
# <a name="recordsetvalidationrule-property-dao"></a><span data-ttu-id="c1e3f-102">Recordset.ValidationRule Property (DAO)</span><span class="sxs-lookup"><span data-stu-id="c1e3f-102">Recordset.ValidationRule Property (DAO)</span></span>


<span data-ttu-id="c1e3f-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="c1e3f-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="c1e3f-104">设置或返回一个值，当字段中的数据更改或添加到表中时，该值对这些数据进行验证（仅适用于 Microsoft Access 工作区）。可读写 **String**。</span><span class="sxs-lookup"><span data-stu-id="c1e3f-104">Sets or returns a value that validates the data in a field as it's changed or added to a table (Microsoft Access workspaces only).Read/write **String**.</span></span>

## <a name="syntax"></a><span data-ttu-id="c1e3f-105">语法</span><span class="sxs-lookup"><span data-stu-id="c1e3f-105">Syntax</span></span>

<span data-ttu-id="c1e3f-106">*表达式*。ValidationRule</span><span class="sxs-lookup"><span data-stu-id="c1e3f-106">*expression* .ValidationRule</span></span>

<span data-ttu-id="c1e3f-107">*表达式*一个表示**Recordset**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="c1e3f-107">*expression* A variable that represents a **Recordset** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="c1e3f-108">注解</span><span class="sxs-lookup"><span data-stu-id="c1e3f-108">Remarks</span></span>

<span data-ttu-id="c1e3f-p101">设置或返回值是一个 **String**，用于描述以不含 WHERE 保留字的 SQL WHERE 子句形式进行的比较。对于尚未追加到 **Fields** 集合中的对象，该属性是可读写的。</span><span class="sxs-lookup"><span data-stu-id="c1e3f-p101">The settings or return values is a **String** that describes a comparison in the form of an SQL WHERE clause without the WHERE reserved word. For an object not yet appended to the **Fields** collection, this property is read/write.</span></span>

<span data-ttu-id="c1e3f-p102">**ValidationRule** 属性确定字段是否包含有效数据。如果数据无效，则会发生可捕获的运行时错误。返回的错误消息是 **ValidationText** 属性的文本，或者是 **ValidationRule** 指定的表达式的文本（如果指定了该表达式）。</span><span class="sxs-lookup"><span data-stu-id="c1e3f-p102">The **ValidationRule** property determines whether or not a field contains valid data. If the data is not valid, a trappable run-time error occurs. The returned error message is the text of the **ValidationText** property, if specified, or the text of the expression specified by **ValidationRule**.</span></span>

<span data-ttu-id="c1e3f-p103">对于 **Recordset** 对象， **ValidationRule** 属性的用法是只读的。对于 **TableDef** 对象， **ValidationRule** 属性的用法取决于 **TableDef** 对象的状态，如下表所示。</span><span class="sxs-lookup"><span data-stu-id="c1e3f-p103">For a **Recordset** object, use of the **ValidationRule** property is read-only. For a **TableDef** object, use of the **ValidationRule** property depends on the status of the **TableDef** object, as the following table shows.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="c1e3f-116">TableDef</span><span class="sxs-lookup"><span data-stu-id="c1e3f-116">TableDef</span></span></p></th>
<th><p><span data-ttu-id="c1e3f-117">用法</span><span class="sxs-lookup"><span data-stu-id="c1e3f-117">Usage</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c1e3f-118">基表</span><span class="sxs-lookup"><span data-stu-id="c1e3f-118">Base table</span></span></p></td>
<td><p><span data-ttu-id="c1e3f-119">可读写</span><span class="sxs-lookup"><span data-stu-id="c1e3f-119">Read/write</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c1e3f-120">链接表</span><span class="sxs-lookup"><span data-stu-id="c1e3f-120">Linked table</span></span></p></td>
<td><p><span data-ttu-id="c1e3f-121">只读</span><span class="sxs-lookup"><span data-stu-id="c1e3f-121">Read-only</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="c1e3f-122">只对使用 Microsoft Access 数据库引擎的数据库支持验证。</span><span class="sxs-lookup"><span data-stu-id="c1e3f-122">Validation is supported only for databases that use the Microsoft Access database engine.</span></span>

<span data-ttu-id="c1e3f-p104">**Field** 对象的 **ValidationRule** 属性所指定的字符串表达式只能引用该 **Field**。该表达式不能引用用户定义的函数、SQL 聚合函数或查询。若要在 **Field** 对象的 **ValidateOnSet** 属性设置为 **True** 时设置其 **ValidationRule** 属性，表达式必须成功分析（将字段名称作为隐含的操作数）且计算为 **True**。如果其 **ValidateOnSet** 属性设置为 **False**，则忽略 **ValidationRule** 属性设置。</span><span class="sxs-lookup"><span data-stu-id="c1e3f-p104">The string expression specified by the **ValidationRule** property of a **Field** object can refer only to that **Field**. The expression can't refer to user-defined functions, SQL aggregate functions, or queries. To set a **Field** object's **ValidationRule** property when its **ValidateOnSet** property setting is **True**, the expression must successfully parse (with the field name as an implied operand) and evaluate to **True**. If its **ValidateOnSet** property setting is **False**, the **ValidationRule** property setting is ignored.</span></span>

<span data-ttu-id="c1e3f-p105">**Recordset** 或 **TableDef** 对象的 **ValidationRule** 属性可以引用该对象中的多个字段。本主题前面所述的对 **Field** 对象的限制在此适用。</span><span class="sxs-lookup"><span data-stu-id="c1e3f-p105">The **ValidationRule** property of a **Recordset** or **TableDef** object can refer to multiple fields in that object. The restrictions noted earlier in this topic for the **Field** object apply.</span></span>

<span data-ttu-id="c1e3f-129">对于表类型的 **Recordset** 对象， **ValidationRule** 属性继承您用于创建该表类型 **Recordset** 对象的 **TableDef** 对象的 **ValidationRule** 属性设置。</span><span class="sxs-lookup"><span data-stu-id="c1e3f-129">For a table-type **Recordset** object, the **ValidationRule** property inherits the **ValidationRule** property setting of the **TableDef** object that you use to create the table-type **Recordset** object.</span></span>


> [!NOTE]
> <P><span data-ttu-id="c1e3f-130">如果属性设置为非整数值时，连接字符串和系统参数指定非美国十进制字符，例如逗号分隔 (例如，strRule ="价格&gt;" &amp; lngPrice，和 lngPrice = 125,50)，将导致错误时您的代码，尝试进行验证的任何数据。</span><span class="sxs-lookup"><span data-stu-id="c1e3f-130">If you set the property to a string concatenated with a non-integer value, and the system parameters specify a non-U.S. decimal character such as a comma (for example, strRule = "PRICE &gt; " &amp; lngPrice, and lngPrice = 125,50), an error will result when your code attempts to validate any data.</span></span> <span data-ttu-id="c1e3f-131">这是因为在连接过程中，需要使用系统的默认小数字符将数字转换为字符串，并且 Microsoft Access SQL 只接受美国格式的小数字符。</span><span class="sxs-lookup"><span data-stu-id="c1e3f-131">This is because during concatenation, the number will be converted to a string using your system's default decimal character, and Microsoft Access SQL only accepts U.S. decimal characters.</span></span></P>

