---
title: Recordset.Bookmarkable Property (DAO)
TOCTitle: Bookmarkable Property
ms:assetid: 6323f162-75c4-7cfe-c918-0b9454560f97
ms:mtpsurl: https://msdn.microsoft.com/library/Ff194950(v=office.15)
ms:contentKeyID: 48545257
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 42c7b8a95eecd055e6a4581bd8d8f3a6c4693168
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25467813"
---
# <a name="recordsetbookmarkable-property-dao"></a>Recordset.Bookmarkable Property (DAO)


**适用于**： Access 2013 |Office 2013

返回一个值，该值表示 **Recordset** 对象是否支持书签（可以使用 **[Bookmark](recordset-bookmark-property-dao.md)** 属性来设置书签）。

## <a name="syntax"></a>语法

*表达式*。Bookmarkable

*表达式*一个表示**Recordset**对象的变量。

## <a name="remarks"></a>注解

在尝试设置或检查 **Bookmark** 属性之前，请检查 **Recordset** 对象的 **Bookmarkable** 属性设置。

对于**Recordset**对象完全基于 Microsoft Access 数据库引擎表， **Bookmarkable**属性的值为 True，并可以使用书签。 但是，其他数据库产品可能不支持书签。 例如，在基于 Paradox 链接表（没有主键）的任何 **Recordset** 对象中，都不能使用书签。

## <a name="example"></a>示例

以下示例使用 **Bookmark** 和 **Bookmarkable** 属性，让用户对 **Recordset** 中的记录做上标记，稍后再返回到此记录。

```vb
    Sub BookmarkX() 
     
     Dim dbsNorthwind As Database 
     Dim rstCategories As Recordset 
     Dim strMessage As String 
     Dim intCommand As Integer 
     Dim varBookmark As Variant 
     
     Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
     Set rstCategories = _ 
     dbsNorthwind.OpenRecordset("Categories", _ 
     dbOpenSnapshot) 
     
     With rstCategories 
     
     If .Bookmarkable = False Then 
     Debug.Print "Recordset is not Bookmarkable!" 
     Else 
     ' Populate Recordset. 
     .MoveLast 
     .MoveFirst 
     
     Do While True 
     ' Show information about current record and get 
     ' user input. 
     strMessage = "Category: " & !CategoryName & _ 
     " (record " & (.AbsolutePosition + 1) & _ 
     " of " & .RecordCount & ")" & vbCr & _ 
     "Enter command:" & vbCr & _ 
     "[1 - next / 2 - previous /" & vbCr & _ 
     "3 - set bookmark / 4 - go to bookmark]" 
     intCommand = Val(InputBox(strMessage)) 
     
     Select Case intCommand 
     ' Move forward or backward, trapping for BOF 
     ' or EOF. 
     Case 1 
     .MoveNext 
     If .EOF Then .MoveLast 
     Case 2 
     .MovePrevious 
     If .BOF Then .MoveFirst 
     
     ' Store the bookmark of the current record. 
     Case 3 
     varBookmark = .Bookmark 
     
     ' Go to the record indicated by the stored 
     ' bookmark. 
     Case 4 
     If IsEmpty(varBookmark) Then 
     MsgBox "No Bookmark set!" 
     Else 
     .Bookmark = varBookmark 
     End If 
     
     Case Else 
     Exit Do 
     End Select 
     
     Loop 
     
     End If 
     
     .Close 
     End With 
     
     dbsNorthwind.Close 
     
    End Sub
```
