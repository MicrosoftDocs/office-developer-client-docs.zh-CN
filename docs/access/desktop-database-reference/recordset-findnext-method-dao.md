---
title: Recordset.FindNext Method (DAO)
TOCTitle: FindNext Method
ms:assetid: 5457dfc8-e561-5624-74d0-34278ba2e7cb
ms:mtpsurl: https://msdn.microsoft.com/library/Ff194099(v=office.15)
ms:contentKeyID: 48544893
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 9d9e4651b2fb5fa9f0ef8569b9f4b28d4c031e87
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25885295"
---
# <a name="recordsetfindnext-method-dao"></a>Recordset.FindNext Method (DAO)

**适用于**： Access 2013、 Office 2013

在动态集类型或快照类型**[Recordset](recordset-object-dao.md)** 对象符合指定的条件，并使该记录成为当前记录 （仅限 Microsoft Access 工作区） 中查找下一个记录。

## <a name="syntax"></a>语法

*表达式*。FindNext （***标准***）

*表达式*一个表示**Recordset**对象的变量。

### <a name="parameters"></a>参数

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
<td><p>条件</p></td>
<td><p>必需</p></td>
<td><p><strong>字符串</strong></p></td>
<td><p>用于查找记录的字符串。它类似于 SQL 语句中的 WHERE 子句，但不包括单词 WHERE。</p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>注解

如果要在搜索中包括所有记录（而不仅仅是符合特定条件的记录），请使用 **Move** 方法在记录之间移动。若要在表类型的 **Recordset** 中查找记录，请使用 **Seek** 方法。

如果未找到与条件匹配的记录，当前记录指针将是未知的，同时 **NoMatch** 属性将设置为 **True**。 如果 recordset 中包含多个记录满足条件， **FindFirst**查找第一个匹配项， **FindNext**查找下一个匹配项，依此类推。

每个 **Find** 方法都按下表中指定的方向，从该表指定的位置开始搜索。

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Find 方法</p></th>
<th><p>开始搜索的位置</p></th>
<th><p>搜索方向</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>FindFirst</strong></p></td>
<td><p>记录集开头</p></td>
<td><p>记录集末尾</p></td>
</tr>
<tr class="even">
<td><p><strong>FindLast</strong></p></td>
<td><p>记录集末尾</p></td>
<td><p>记录集开头</p></td>
</tr>
<tr class="odd">
<td><p><strong>FindNext</strong></p></td>
<td><p>当前记录</p></td>
<td><p>记录集末尾</p></td>
</tr>
<tr class="even">
<td><p><strong>FindPrevious</strong></p></td>
<td><p>当前记录</p></td>
<td><p>记录集开头</p></td>
</tr>
</tbody>
</table>


但是，使用 **Find** 方法之一与使用 **Move** 方法不同，后者只是将第一条、最后一条、下一条或上一条记录设置为当前记录，而不会指定条件。可以在 Find 操作后面跟随一个 Move 操作。

始终检查 **NoMatch** 属性的值，以确定 Find 操作是否已成功。如果搜索成功，则 **NoMatch** 为 **False**。如果搜索失败，则 **NoMatch** 为 **True**，并且不定义当前记录。在这种情况下，必须将当前记录指针往回定位到有效的记录。

如果将 **Find** 方法用于 Microsoft Access 数据库引擎连接的 ODBC 访问记录集，效率可能较低。 您可能会发现，通过您的条件来查找特定记录缩小范围的速度更快，尤其是当处理大型记录集。

在 ODBCDirect 工作区中， **Find** 和 **Seek** 方法并不是对任何类型的 **Recordset** 对象可用，因为在网络上通过 ODBC 连接执行 **Find** 或 **Seek** 不是十分有效。 而是应设计查询 （即正在使用**OpenRecordset**方法的 source 参数之后） 与适当的 WHERE 子句，返回的记录仅限于满足条件的使用中的**查找**或**Seek**方法。

在处理 Microsoft Access 数据库引擎连接的 ODBC 数据库以及大型动态集类型 v 对象时，可能会发现使用 **Find** 方法或使用 **Sort** 或 **Filter** 属性都比较慢。若要改善性能，请将 SQL 查询与自定义的 ORDER BY 或 WHERE 子句、参数查询或检索特定索引记录的 **QueryDef** 对象一起使用。

在搜索包含日期的字段时，即使使用的不是美国版本的 Microsoft Access 数据库引擎，也应使用美国日期格式（月-日-年）；否则将无法找到数据。使用 Visual Basic **Format** 函数转换日期。例如：

```vb
    rstEmployees.FindFirst "HireDate > #" _ 
        & Format(mydate, 'm-d-yy' ) & "#" 
```

如果条件组成的字符串串联非整数值，并且系统参数指定非美国十进制字符，例如逗号分隔 (例如，strSQL ="价格\>"& lngPrice，和 lngPrice = 125,50)，当您尝试出错调用方法。 这是因为在连接过程中，需要使用系统的默认小数字符将数字转换为字符串，并且 Microsoft Access SQL 只接受美国格式的小数字符。

> [!NOTE]
> - 为了获得最佳性能，*条件*应在窗体"*字段* = *值*"*字段*中的基础表或"*字段*LIKE*前缀"其中*字段*是*为索引的字段的其中索引的字段中的基础表和*前缀*为前缀搜索字符串 （例如，"画 *"）。
> 
> - 一般而言，作为等效的搜索类型， **Seek** 方法的性能优于 **Find** 方法。这假定表类型的 **Recordset** 对象可单独满足您的需求。


## <a name="example"></a>示例

下面的示例演示如何使用 FindFirst 和 FindNext 方法在记录集中查找记录。

**示例代码提供者** [Microsoft Access 2010 Programmer's Reference](https://www.amazon.com/Microsoft-Access-2010-Programmers-Reference/dp/8126528125)。


```vb
    Sub FindOrgName()
    
        Dim dbs As DAO.Database
        Dim rst As DAO.Recordset
        
        'Get the database and Recordset
        Set dbs = CurrentDb
        Set rst = dbs.OpenRecordset("tblCustomers")
    
        'Search for the first matching record   
        rst.FindFirst "[OrgName] LIKE '*parts*'"
        
        'Check the result
        If rst.NoMatch Then
            MsgBox "Record not found."
            GotTo Cleanup
        Else
            Do While Not rst.NoMatch
                MsgBox "Customer name: " & rst!CustName
                rst.FindNext "[OrgName] LIKE '*parts*'"
            Loop
    
            'Search for the next matching record
            rst.FindNext "[OrgName] LIKE '*parts*'"
        End If
       
        Cleanup:
            rst.Close
            Set rst = Nothing
            Set dbs = Nothing
    
    End Sub
```
