---
title: DBEngine 方法 (DAO)
TOCTitle: Idle Method
ms:assetid: c90b565e-626e-139d-102a-0386601ce0c8
ms:mtpsurl: https://msdn.microsoft.com/library/Ff823202(v=office.15)
ms:contentKeyID: 48547666
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1052978
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: 7a84e3cc4b35886a12b2e6b4cf92b7483fea293a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32294328"
---
# <a name="dbengineidle-method-dao"></a>DBEngine 方法 (DAO)

**适用于**：Access 2013、Office 2013

挂起数据处理，使 Microsoft Access 数据库引擎完成任何待定任务，例如内存优化或页面超时（仅适用于 Microsoft Access 工作区）。

## <a name="syntax"></a>语法

*表达式*。空闲 (***操作***)

*表达式*一个代表**DBEngine**对象的变量。

## <a name="parameters"></a>参数

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
<td><p><em>Action</em></p></td>
<td><p>可选</p></td>
<td><p><strong>Variant</strong></p></td>
<td><p>指定要执行的操作。 可以是<strong><a href="idleenum-enumeration-dao.md">IdleEnum</a></strong>常量之一。</p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>注解

**Idle** 方法允许 Microsoft Access 数据库引擎执行由于密集的数据处理而不再处于最新状态的后台任务。在多用户、多任务环境中，由于没有足够的后台处理时间使 **[Recordset](recordset-object-dao.md)** 中的所有记录成为当前状态，因此这种情况经常出现。

通常，仅当没有其他操作（包括鼠标移动）发生时，才会取消读取锁定，并更新本地动态集类型 **Recordset** 对象中的数据。如果定期使用 **Idle** 方法，Microsoft Access 数据库引擎可通过解除不需要的读取锁定来结束后台处理任务。

如果指定可选的 **dbRefreshCache** 参数，将只使用数据库中的最新数据刷新内存。

在单一用户环境中，除非应用程序的多个实例正在运行，否则不需要使用此方法。在多用户环境中， **Idle** 方法可提高性能，因为它会强制数据库引擎将数据写入磁盘，同时解除内存的锁定。


> [!NOTE]
> [!注释] 还可以通过将操作指定为事务处理的一部分来解除读取锁定。

## <a name="example"></a>示例

以下示例使用 **Idle** 方法确保输出过程访问数据库中可用的最新数据。若要使该过程运行，需要使用 IdleOutput 过程。

```vb 
Sub IdleX() 
 
 Dim dbsNorthwind As Database 
 Dim strCountry As String 
 Dim strSQL As String 
 Dim rstOrders As Recordset 
 
 Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
 
 ' Get name of country from user and build SQL statement 
 ' with it. 
 strCountry = Trim(InputBox("Enter country:")) 
 strSQL = "SELECT * FROM Orders WHERE ShipCountry = '" & _ 
 strCountry & "' ORDER BY OrderID" 
 
 ' Open Recordset object with SQL statement. 
 Set rstOrders = dbsNorthwind.OpenRecordset(strSQL) 
 
 ' Display contents of Recordset object. 
 IdleOutput rstOrders, strCountry 
 
 rstOrders.Close 
 dbsNorthwind.Close 
 
End Sub 
 
Sub IdleOutput(rstTemp As Recordset, strTemp As String) 
 
 ' Call the Idle method to release unneeded locks, force 
 ' pending writes, and refresh the memory with the current 
 ' data in the .mdb file. 
 DBEngine.Idle dbRefreshCache 
 
 ' Enumerate the Recordset object. 
 With rstTemp 
 Debug.Print "Orders from " & strTemp & ":" 
 Debug.Print , "OrderID", "CustomerID", "OrderDate" 
 Do While Not .EOF 
 Debug.Print , !OrderID, !CustomerID, !OrderDate 
 .MoveNext 
 Loop 
 End With 
 
End Sub 
 
```

