---
title: Recordset.Filter 属性 (DAO)
TOCTitle: Filter Property
ms:assetid: feffa23b-c348-9718-ba4b-65db0f739789
ms:mtpsurl: https://msdn.microsoft.com/library/Ff837300(v=office.15)
ms:contentKeyID: 48548953
ms.date: 06/04/2019
mtps_version: v=office.15
localization_priority: Priority
ms.openlocfilehash: 43afbfda8c560eafb90e6a53d85207e19e5b1170
ms.sourcegitcommit: 4a570873914c58dd4cdbe97b5d9ec41866dc797c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/03/2019
ms.locfileid: "34675748"
---
# <a name="recordsetfilter-property-dao"></a>Recordset.Filter 属性 (DAO)

**适用于**：Access 2013、Office 2013

设置或返回一个值，该值确定在随后打开的 **Recordset** 对象中包括的记录（仅适用于 Microsoft Access 工作区）。 读/写 **String**。

## <a name="syntax"></a>语法

*表达式*.**Filter**

*表达式* 一个返回 **Recordset** 对象的表达式。

## <a name="remarks"></a>说明

设置或返回值是一个 String 数据类型，它包含不带保留字 WHERE 的 SQL 语句的 WHERE 子句。

使用 **Filter** 属性可以对动态集类型、快照类型或仅向前类型的 **Recordset** 对象应用筛选器。

可以使用 **Filter** 属性限制当基于现有 **Recordset** 对象打开新的 **Recordset** 对象时从现有对象返回的记录。

即使您不使用美国版本的 Microsoft Access 数据库引擎，在筛选包含日期的字段时，也需要使用美国日期格式（月-日-年）（在此情况下，必须通过连接字符串来组合任何日期，例如 strMonth & "-" & strDay & "-" & strYear）。 否则，日期数据可能不按您期望的方式进行筛选。

在许多情况下，使用包含 WHERE 子句的 SQL 语句打开新的 **Recordset** 对象会快一些。

如果将该属性设置为连接了非整数值的字符串，并且系统参数指定了诸如逗号的非美国格式小数字符（例如 strFilter = "PRICE \> " & lngPrice 和 lngPrice = 125,50），那么在尝试打开下一个 **Recordset** 时会发生错误。 这是因为在连接过程中，需要使用系统的默认小数字符将数字转换为字符串，并且 Microsoft Access SQL 只接受美国格式的小数字符。

## <a name="example"></a>示例

以下示例说明如何使用 Filter 属性确定要包含在随后打开的 Recordset 中的记录。

**示例代码提供方：**[Microsoft Access 2010 程序员参考](https://www.amazon.com/Microsoft-Access-2010-Programmers-Reference/dp/8126528125)。

```vb
    Dim dbs As DAO.Database
    Dim rst As DAO.Recordset
    Dim rstFiltered As DAO.Recordset
    Dim strCity As String
    
    Set dbs = CurrentDb
    
    'Create the first filtered Recordset, returning customer records
    'for those visited between 30-60 days ago.
    Set rst = dbs.OpenRecordset(_ 
        "SELECT * FROM Customers WHERE LastVisitDate BETWEEN Date()-60 " & _
        "AND Date()-30 ORDER BY LastVisitDate DESC")
    
    'Begin row processing
    Do While Not rst.EOF
        
        'Retrieve the name of the first city in the selected rows
        strCity = rst!City
    
        'Now filter the Recordset to return only the customers from that city
        rst.Filter = "City = '" & strCity & "'"
        Set rstFiltered = rst.OpenRecordset
    
        'Process the rows
        Do While Not rstFiltered.EOF
            rstFiltered.Edit
            rstFiltered!ToBeVisited = True
            rstFiltered.Update
            rstFiltered.MoveNext
        Loop
    
        'We've done what was needed. Now exit
        Exit Do
        rst.MoveNext
       
    Loop
    
    'Cleanup
    rstFiltered.Close
    rst.Close
    
    Set rstFiltered = Nothing
    Set rst = Nothing
```
