---
title: Recordset.Clone 方法 (DAO)
TOCTitle: Clone Method
ms:assetid: 50cbc011-7e72-4dee-488d-96e681618e8e
ms:mtpsurl: https://msdn.microsoft.com/library/Ff193824(v=office.15)
ms:contentKeyID: 48544802
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1052909
f1_categories:
- Office.Version=v15
ms.openlocfilehash: aa5a04ec08136dda637aabff15d89f81be6ecde8
ms.sourcegitcommit: 1dd744993ecb4bed241ace874ad26edaef1778b8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/06/2018
ms.locfileid: "25998572"
---
# <a name="recordsetclone-method-dao"></a>Recordset.Clone 方法 (DAO)

**适用于**： Access 2013、 Office 2013

创建一个引用原始 [Recordset](recordset-object-dao.md) 对象的复制 ****Recordset**** 对象。

## <a name="syntax"></a>语法

*表达式*。克隆

*表达式*一个表示**Recordset**对象的变量。

## <a name="return-value"></a>返回值

Recordset

## <a name="remarks"></a>注解

使用 **Clone** 方法可以创建多个重复的 **Recordset** 对象。每个 **Recordset** 都可以具有其自身的当前记录。使用 **Clone** 自身并不会更改对象中的数据或对象基础结构中的数据。使用 **Clone** 方法时，可以在两个或更多个 **Recordset** 对象之间共享书签，因为这些对象的书签是可以交换的。

如果要对需要多个当前记录的 **Recordset** 执行操作，可使用 **Clone** 方法。这样比打开第二个 **Recordset** 更加快速和高效。使用 **Clone** 方法创建了 **Recordset** 后，该记录集最初会缺少一个当前记录。若要在使用 **Recordset** 克隆之前使某记录成为当前记录，必须设置 **[Bookmark](recordset-bookmark-property-dao.md)** 属性，或使用 **[Move](recordset-movefirst-method-dao.md)** 方法之一、 **[Find](recordset-findfirst-method-dao.md)** 方法之一或 **[Seek](recordset-seek-method-dao.md)** 方法。

无论是对原始对象还是对复制对象使用 **[Close](connection-close-method-dao.md)** 方法，都不会影响其他对象。例如，对原始 **Recordset** 使用 **Close** 不会关闭克隆。

> [!NOTE]
> - 在待定事务中关闭克隆 Recordset 将导致隐式 **Rollback** 操作。
> - 在 Microsoft Access 工作区中克隆表类型的 **Recordset** 对象时，不会将 **[Index](recordset2-index-property-dao.md)** 属性设置克隆到 Recordset 的新副本上。必须手动复制 **Index** 属性设置。

## <a name="example"></a>示例

以下示例使用 **Clone** 方法创建 **Recordset** 的副本，然后让用户单独定位每个副本的记录指针。

```vb
    Sub CloneX() 
     
       Dim dbsNorthwind As Database 
       Dim arstProducts(1 To 3) As Recordset 
       Dim intLoop As Integer 
       Dim strMessage As String 
       Dim strFind As String 
     
       Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
     
       ' If the following SQL statement will be used often,  
       ' creating a permanent QueryDef will result in better 
       ' performance. 
       Set arstProducts(1) = dbsNorthwind.OpenRecordset( _ 
          "SELECT ProductName FROM Products " & _ 
          "ORDER BY ProductName", dbOpenSnapshot) 
     
       ' Create two clones of the original Recordset. 
       Set arstProducts(2) = arstProducts(1).Clone 
       Set arstProducts(3) = arstProducts(1).Clone 
     
       Do While True 
     
          ' Loop through the array so that on each pass, the  
          ' user is searching a different copy of the same  
          ' Recordset. 
          For intLoop = 1 To 3 
     
             ' Ask for search string while showing where the 
             ' current record pointer is for each Recordset. 
             strMessage = _ 
                "Recordsets from Products table:" & vbCr & _ 
                "  1 - Original - Record pointer at " & _ 
                arstProducts(1)!ProductName & vbCr & _ 
                "  2 - Clone - Record pointer at " & _ 
                arstProducts(2)!ProductName & vbCr & _ 
                "  3 - Clone - Record pointer at " & _ 
                arstProducts(3)!ProductName & vbCr & _ 
                "Enter search string for #" & intLoop & ":" 
             strFind = Trim(InputBox(strMessage)) 
             If strFind = "" Then Exit Do 
     
             ' Find the search string; if there's no match, jump 
             ' to the last record. 
             With arstProducts(intLoop) 
                .FindFirst "ProductName >= '" & strFind & "'" 
                If .NoMatch Then .MoveLast 
             End With 
     
          Next intLoop 
     
       Loop 
     
       arstProducts(1).Close 
       arstProducts(2).Close 
       arstProducts(3).Close 
       dbsNorthwind.Close 
     
    End Sub
```
