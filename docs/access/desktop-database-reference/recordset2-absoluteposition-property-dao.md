---
title: Recordset2.AbsolutePosition 属性 (DAO)
TOCTitle: AbsolutePosition Property
ms:assetid: 91ca203f-0c80-67f4-e180-415b6af05030
ms:mtpsurl: https://msdn.microsoft.com/library/Ff197637(v=office.15)
ms:contentKeyID: 48546358
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1053074
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 76137608ed5de0fbd2b841fba3101d70209c7a6d
ms.sourcegitcommit: 1dd744993ecb4bed241ace874ad26edaef1778b8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/06/2018
ms.locfileid: "25998753"
---
# <a name="recordset2absoluteposition-property-dao"></a>Recordset2.AbsolutePosition 属性 (DAO)

**适用于**： Access 2013、 Office 2013

设置或返回 **Recordset2** 对象的当前记录的相对记录编号。

## <a name="syntax"></a>语法

*表达式*。AbsolutePosition

*表达式*一个表示**Recordset2**对象的变量。

## <a name="remarks"></a>注解

可以根据特定记录在动态集类型或快照类型 **Recordset2** 对象中的序号位置，使用 **AbsolutePosition** 属性将当前记录指针定位到该特定记录。还可以通过检查 **AbsolutePosition** 属性设置来确定当前记录编号。

由于 **AbsolutePosition** 属性值从零开始（即设置 0 引用 **Recordset2** 对象中的第一条记录），因此您不能将其设置为大于或等于填充记录数的值；如果这样做，会导致可捕获的错误。您可以通过检查 **RecordCount** 属性设置来确定 **Recordset2** 对象中填充的记录数。 **AbsolutePosition** 属性的最大允许设置为 **RecordCount** 属性的值减 1。

如果没有当前记录，作为**Recordset2**对象中任何记录时， **AbsolutePosition**返回-1。 如果删除了当前记录，则 **AbsolutePosition** 属性值将是不确定的，并且，当引用该记录时将会发生可捕获的错误。 新记录将添加到序列的末尾。

不应将该属性用作代理记录编号。仍然建议采用书签保留和返回到给定位置，而且这是在所有类型的 **Recordset2** 对象之间定位当前记录的唯一方法。特别是，当某记录之前的一条或多条记录被删除时，该记录的位置就会更改。如果再次重新创建 **Recordset2** 对象，也无法保证记录具有相同的绝对位置，这是因为除非使用带有 ORDER BY 子句的 SQL 语句来创建 **Recordset** 对象，否则该对象中的各个记录的顺序将是无法保证的。

> [!NOTE]
> - 对于新打开但尚未填充的 **Recordset2** 对象，如果将 **AbsolutePosition** 属性设置为大于零的值，则会导致可捕获的错误。请首先使用 **MoveLast** 方法填充 **Recordset2** 对象。
> - 仅向前类型**Recordset2**对象，或者对于从针对 Microsoft Access 数据库引擎连接的 ODBC 数据库的传递查询打开的**Recordset2**对象， **AbsolutePosition**属性不可用。

## <a name="example"></a>示例

以下示例使用 **AbsolutePosition** 属性跟踪枚举 **Recordset2** 的所有记录的循环的进度。

```vb
    Sub AbsolutePositionX() 
     
       Dim dbsNorthwind As Database 
       Dim rstEmployees As Recordset2 
       Dim strMessage As String 
     
       Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
       ' AbsolutePosition only works with dynasets or snapshots. 
       Set rstEmployees = _ 
          dbsNorthwind.OpenRecordset("Employees", _ 
          dbOpenSnapshot) 
     
       With rstEmployees 
          ' Populate Recordset. 
          .MoveLast 
          .MoveFirst 
     
          ' Enumerate Recordset. 
          Do While Not .EOF 
             ' Display current record information. Add 1 to  
             ' AbsolutePosition value because it is zero-based. 
             strMessage = "Employee: " & !LastName & vbCr & _ 
                "(record " & (.AbsolutePosition + 1) & _ 
                " of " & .RecordCount & ")" 
             If MsgBox(strMessage, vbOKCancel) = vbCancel _ 
                Then Exit Do 
             .MoveNext 
          Loop 
     
          .Close 
       End With 
     
       dbsNorthwind.Close 
     
    End Sub
```
