---
title: Recordset2 属性 (DAO)
TOCTitle: Sort Property
ms:assetid: 523a8c29-46e2-564f-205d-03c214f277fe
ms:mtpsurl: https://msdn.microsoft.com/library/Ff193917(v=office.15)
ms:contentKeyID: 48544842
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: a5784054ce195a1a2ea516d4f6a3417c5a8db71c
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32309267"
---
# <a name="recordset2sort-property-dao"></a>Recordset2 属性 (DAO)

**适用于**：Access 2013、Office 2013 

设置或返回 **[Recordset](recordset-object-dao.md)** 对象中的记录的排序次序（仅适用于 Microsoft Access 工作区）。

## <a name="syntax"></a>语法

*表达式*。排序

*表达式*一个代表**Recordset2**对象的变量。

## <a name="remarks"></a>注解

可以将 **Sort** 属性用于动态集类型和快照类型的 **Recordset** 对象。

如果为某对象设置了该属性，当从该对象创建后续 **Recordset** 对象时会进行排序。 **Sort** 属性设置重写为 **[QueryDef](querydef-object-dao.md)** 对象指定的任何排序次序。

默认的排序次序是升序（A 到 Z，0 到 100）。

**Sort**属性不适用于表或仅向前类型的**Recordset**对象。 若要对 table 类型的**Recordset**对象进行排序, 请使用**[Index](recordset2-index-property-dao.md)** 属性。

> [!NOTE]
> [!注释] 在许多情况下，使用包含排序条件的 SQL 语句打开新的 **Recordset** 对象会快一些。

## <a name="example"></a>示例

以下示例通过更改 **Sort** 属性的值和创建新的 **Recordset** 来演示该属性。若要使该过程运行，需要使用 SortOutput 函数。

```vb
    Sub SortX() 
     
     Dim dbsNorthwind As Database 
     Dim rstEmployees As Recordset2 
     Dim rstSortEmployees As Recordset2 
     
     Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
     Set rstEmployees = _ 
     dbsNorthwind.OpenRecordset("Employees", _ 
     dbOpenDynaset) 
     
     With rstEmployees 
     SortOutput "Original Recordset:", rstEmployees 
     .Sort = "LastName, FirstName" 
     ' Print report showing Sort property and record order. 
     SortOutput _ 
     "Recordset after changing Sort property:", _ 
     rstEmployees 
     ' Open new Recordset from current one. 
     Set rstSortEmployees = .OpenRecordset 
     ' Print report showing Sort property and record order. 
     SortOutput "New Recordset:", rstSortEmployees 
     rstSortEmployees.Close 
     .Close 
     End With 
     
     dbsNorthwind.Close 
     
    End Sub 
     
    Function SortOutput(strTemp As String, _ 
     rstTemp As Recordset) 
     
     With rstTemp 
     Debug.Print strTemp 
     Debug.Print " Sort = " & _ 
     IIf(.Sort <> "", .Sort, "[Empty]") 
     .MoveFirst 
     
     ' Enumerate Recordset. 
     Do While Not .EOF 
     Debug.Print " " & !LastName & _ 
     ", " & !FirstName 
     .MoveNext 
     Loop 
     
     End With 
     
    End Function 
```

<br/>

如果知道要选择的数据，通过 SQL 语句创建 **Recordset** 通常效率更高。以下示例演示如何仅创建一个 **Recordset** 就获得与上例一样的结果。

```vb
    Sub SortX2() 
     
     Dim dbsNorthwind As Database 
     Dim rstEmployees As Recordset 
     
     Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
     ' Open a Recordset from an SQL statement that specifies a 
     ' sort order. 
     Set rstEmployees = _ 
     dbsNorthwind.OpenRecordset("SELECT * " & _ 
     "FROM Employees ORDER BY LastName, FirstName", _ 
     dbOpenDynaset) 
     
     dbsNorthwind.Close 
     
    End Sub
```
