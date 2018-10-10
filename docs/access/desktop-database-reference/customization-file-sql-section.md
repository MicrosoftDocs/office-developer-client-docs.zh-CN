---
title: 自定义文件 SQL 节
TOCTitle: Customization File SQL Section
ms:assetid: 002c544f-fe1b-6aeb-ba9a-97b1e1159516
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248776(v=office.15)
ms:contentKeyID: 48542901
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 09be671ba15727e3612ade78c5b54af12b1d1c57
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25465870"
---
# <a name="customization-file-sql-section"></a><span data-ttu-id="691d8-102">自定义文件 SQL 节</span><span class="sxs-lookup"><span data-stu-id="691d8-102">Customization File SQL Section</span></span>


<span data-ttu-id="691d8-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="691d8-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="691d8-p101">**sql** 节可以包含新的 SQL 字符串，该字符串用于替换客户端命令字符串。如果节中没有 SQL 字符串，将忽略该节。</span><span class="sxs-lookup"><span data-stu-id="691d8-p101">The **sql** section can contain a new SQL string that replaces the client command string. If there is no SQL string in the section, the section will be ignored.</span></span>

<span data-ttu-id="691d8-p102">新的 SQL 字符串可能是*参数化的*。就是说，**sql** 节 SQL 字符串（由“?”字符指定）中的参数可以替换为客户端命令字符串（由括号中的以逗号分隔的列表指定）中的 *identifier* 中的相应参数。标识符和参数列表的行为类似函数调用。</span><span class="sxs-lookup"><span data-stu-id="691d8-p102">The new SQL string may be *parameterized*. That is, parameters in the **sql** section SQL string (designated by the '?' character) can be replaced by corresponding arguments in an *identifier* in the client command string (designated by a comma-delimited list in parentheses). The identifier and argument list behave like a function call.</span></span>

<span data-ttu-id="691d8-109">例如，假定客户端命令字符串为"CustomerByID(4)"，SQL 节标头为\[SQL CustomerByID\] ，和新的 SQL 节字符串是"选择\*FROM Customers WHERE CustomerID = ?"。</span><span class="sxs-lookup"><span data-stu-id="691d8-109">For example, assume the client command string is "CustomerByID(4)" , the SQL section header is \[SQL CustomerByID\] , and the new SQL section string is "SELECT \* FROM Customers WHERE CustomerID = ?".</span></span> <span data-ttu-id="691d8-110">处理程序将生成、 SQL 节标头是\[SQL CustomerByID\] ，和新的 SQL 节字符串是"选择\*FROM Customers WHERE CustomerID = ?"。</span><span class="sxs-lookup"><span data-stu-id="691d8-110">The Handler will generate , the SQL section header is \[SQL CustomerByID\] , and the new SQL section string is "SELECT \* FROM Customers WHERE CustomerID = ?".</span></span> <span data-ttu-id="691d8-111">处理程序将生成"选择\*FROM Customers WHERE CustomerID = 4"并使用该字符串来查询数据源。</span><span class="sxs-lookup"><span data-stu-id="691d8-111">The Handler will generate "SELECT \* FROM Customers WHERE CustomerID = 4" and use that string to query the data source.</span></span>

<span data-ttu-id="691d8-112">如果新的 SQL 语句是空字符串 ("")，将忽略该节。</span><span class="sxs-lookup"><span data-stu-id="691d8-112">If the new SQL statement is the null string (""), then the section is ignored.</span></span>

<span data-ttu-id="691d8-p104">如果新的 SQL 语句字符串无效，则语句的执行将失败。实际上会忽略客户端参数。您可以有意这样做，以便"关闭"所有客户端 SQL 命令，如下所示：</span><span class="sxs-lookup"><span data-stu-id="691d8-p104">If the new SQL statement string is not valid, then the execution of the statement will fail. The client parameter is effectively ignored. You can do this intentionally to "turn off" all client SQL commands by specifying:</span></span>

```sql 
 
[SQL default] 
SQL = " " 
```

## <a name="syntax"></a><span data-ttu-id="691d8-116">语法</span><span class="sxs-lookup"><span data-stu-id="691d8-116">Syntax</span></span>

<span data-ttu-id="691d8-117">替换 SQL 字符串项的格式为：</span><span class="sxs-lookup"><span data-stu-id="691d8-117">A replacement SQL string entry is of the form:</span></span>

<span data-ttu-id="691d8-118">**SQL = \* sqlString**\*</span><span class="sxs-lookup"><span data-stu-id="691d8-118">**SQL=\*sqlString**\*</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="691d8-119">部分</span><span class="sxs-lookup"><span data-stu-id="691d8-119">Part</span></span></p></th>
<th><p><span data-ttu-id="691d8-120">说明</span><span class="sxs-lookup"><span data-stu-id="691d8-120">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="691d8-121"><strong>SQL</strong></span><span class="sxs-lookup"><span data-stu-id="691d8-121"><strong>SQL</strong></span></span></p></td>
<td><p><span data-ttu-id="691d8-122">字面字符串，用于指示这是 SQL 节项。</span><span class="sxs-lookup"><span data-stu-id="691d8-122">A literal string that indicates this is an SQL section entry.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="691d8-123"><strong><em>sqlString</em></strong></span><span class="sxs-lookup"><span data-stu-id="691d8-123"><strong><em>sqlString</em></strong></span></span></p></td>
<td><p><span data-ttu-id="691d8-124">SQL 字符串，用于替换客户端字符串。</span><span class="sxs-lookup"><span data-stu-id="691d8-124">An SQL string that replaces the client string.</span></span></p></td>
</tr>
</tbody>
</table>

