---
title: Recordset.PercentPosition Property (DAO)
TOCTitle: PercentPosition Property
ms:assetid: aebbda44-ed72-7a6c-0cd5-28c8997d4d96
ms:mtpsurl: https://msdn.microsoft.com/library/Ff821751(v=office.15)
ms:contentKeyID: 48547077
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 5793d2b73e424726e91cf3bbb54b09db59123b92
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25467095"
---
# <a name="recordsetpercentposition-property-dao"></a>Recordset.PercentPosition Property (DAO)


**适用于**： Access 2013 |Office 2013

设置或返回一个值，用于根据 [Recordset](recordset-object-dao.md) 中的记录百分比指示 ****Recordset**** 对象中当前记录的大概位置。

## <a name="syntax"></a>语法

*表达式*。PercentPosition

*表达式*一个表示**Recordset**对象的变量。

## <a name="remarks"></a>注解

若要指示或更改 **Recordset** 对象中的当前记录的大概位置，可以检查或设置 **PercentPosition** 属性。当使用从基表直接打开的动态集类型或快照类型的 **Recordset** 对象时，在设置或检查 **PercentPosition** 属性之前，请首先通过移动到最后一条记录来填充 **Recordset** 对象。如果在完全填充 **Recordset** 对象之前使用 **PercentPosition** 属性，则移动量与 **[RecordCount](recordset-recordcount-property-dao.md)** 属性设置所指定的访问记录数相关。您可以使用 **[MoveLast](recordset-movelast-method-dao.md)** 方法来移动到最后一条记录。


> [!NOTE]
> <P>[!注释] 为什么不建议使用 <STRONG>PercentPosition</STRONG> 属性将当前记录移动到 <STRONG>Recordset</STRONG> 对象中的特定记录呢？这是因为 <STRONG><A href="recordset-bookmark-property-dao.md">Bookmark</A></STRONG> 属性更适合这项任务。</P>



一旦将 **PercentPosition** 属性设置为某个值，与该值对应的大概位置处的记录就成为当前记录，且 **PercentPosition** 属性重置为反映当前记录的大概位置的值。例如，如果 **Recordset** 对象只包含五条记录，而您将其 **PercentPosition** 属性值设置为 77，则从 **PercentPosition** 属性返回的值可能是 80，而不是 77。

**PercentPosition**属性应用于所有类型的**Recordset**对象，但仅向前类型**Recordset**对象或从针对远程数据库的传递查询打开的**Recordset**对象除外。

您可以将 **PercentPosition** 属性用于窗体或文本框上的滚动条，以指示 **Recordset** 对象中当前记录的位置。

## <a name="example"></a>示例

以下示例使用 **PercentPosition** 属性显示当前记录指针相对于 **Recordset** 起点的位置。

```vb
    Sub PercentPositionX() 
     
     Dim dbsNorthwind As Database 
     Dim rstProducts As Recordset 
     Dim strFind As String 
     Dim strMessage As String 
     
     Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
     ' PercentPosition only works with dynasets or snapshots. 
     Set rstProducts = dbsNorthwind.OpenRecordset( _ 
     "SELECT ProductName FROM Products " & _ 
     "ORDER BY ProductName", dbOpenSnapshot) 
     
     With rstProducts 
     ' Populate the Recordset. 
     .MoveLast 
     .MoveFirst 
     
     Do While True 
     ' Show current record information and ask user 
     ' for input. 
     strMessage = "Product: " & !ProductName & vbCr & _ 
     "The record pointer is " & _ 
     Format(.PercentPosition, "##0.0") & _ 
     "% from the " & vbCr & _ 
     "beginning of the Recordset." & vbCr & _ 
     "Please enter a character search string " & _ 
     "for a product name." 
     strFind = Trim(InputBox(strMessage)) 
     If strFind = "" Then Exit Do 
     
     ' Try to find a record matching the search string. 
     .FindFirst "ProductName >= '" & strFind & "'" 
     If .NoMatch Then .MoveLast 
     Loop 
     
     .Close 
     End With 
     
     dbsNorthwind.Close 
     
    End Sub
```
