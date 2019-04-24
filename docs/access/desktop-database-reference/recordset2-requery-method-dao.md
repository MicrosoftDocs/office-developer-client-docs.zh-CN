---
title: Recordset2 方法 (DAO)
TOCTitle: Requery Method
ms:assetid: d063c1e0-2fb7-b5cf-4d98-6f77a5a13cec
ms:mtpsurl: https://msdn.microsoft.com/library/Ff834712(v=office.15)
ms:contentKeyID: 48547837
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1052940
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: 44f573d179c26677fc801dac82e0deecc3874fb1
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32307208"
---
# <a name="recordset2requery-method-dao"></a>Recordset2 方法 (DAO)

**适用于**：Access 2013、Office 2013

通过重新执行对象所基于的查询，更新 **[Recordset](recordset-object-dao.md)** 对象中的数据。

## <a name="syntax"></a>语法

*表达式*。Requery (***NewQueryDef***)

*表达式*一个代表**Recordset2**对象的变量。

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
<td><p><em>NewQueryDef</em></p></td>
<td><p>可选</p></td>
<td><p><strong>Variant</strong></p></td>
<td><p>表示 <strong><a href="querydef-object-dao.md">QueryDef</a></strong> 对象的 <strong>Name</strong> 属性值</p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>注解

使用此方法可确保 **Recordset** 包含最新的数据。 此方法通过使用当前查询参数或 (在 Microsoft Access 工作区中) newquerydef 参数所提供的新查询参数来重新填充当前**Recordset** 。

如果不指定 newquerydef 参数，将根据最初用于填充 **Recordset** 的相同查询定义和参数重新填充 **Recordset**。 在此重新填充期间，将反映对基础数据所做的任何更改。 如果没有使用 **QueryDef** 创建 **Recordset**，将从头重新创建 **Recordset**。

如果在 newquerydef 参数中指定原始**QueryDef** , 则使用**QueryDef**指定的参数重新查询**Recordset** 。 在此重新填充期间，将反映对基础数据所做的任何更改。 若要反映对**Recordset**中的查询参数值所做的任何更改, 必须提供 newquerydef 参数。

如果指定的与最初用来创建 **Recordset** 的 **QueryDef** 不相同，将从头重新创建 **Recordset**。

如果使用 **Requery**， **Recordset** 中的第一条记录将成为当前记录。

不能对 **[Restartable](recordset2-restartable-property-dao.md)** 属性设置为 **False** 的动态集类型或快照类型的 **Recordset** 对象使用 **Requery** 方法。 但是，如果提供了可选的 newquerydef 参数，将忽略 **Restartable** 属性。

如果在使用**Requery**方法后**recordset**对象的**[BOF](recordset2-bof-property-dao.md)** 和**[EOF](recordset2-eof-property-dao.md)** 属性设置均为**True** , 则查询不会返回任何记录, 并且**Recordset**不包含任何数据。

## <a name="example"></a>示例

以下示例演示如何在更改基础数据之后，使用 **Requery** 方法刷新查询。

```vb
    Sub RequeryX() 
     
     Dim dbsNorthwind As Database 
     Dim qdfTemp As QueryDef 
     Dim rstView As Recordset2 
     Dim rstChange As Recordset2 
     
     Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
     Set qdfTemp = dbsNorthwind.CreateQueryDef("", _ 
     "PARAMETERS ViewCountry Text; " & _ 
     "SELECT FirstName, LastName, Country FROM " & _ 
     "Employees WHERE Country = [ViewCountry] " & _ 
     "ORDER BY LastName") 
     
     qdfTemp.Parameters!ViewCountry = "USA" 
     Debug.Print "Data after initial query, " & _ 
     [ViewCountry] = USA" 
     Set rstView = qdfTemp.OpenRecordset 
     Do While Not rstView.EOF 
     Debug.Print " " & rstView!FirstName & " " & _ 
     rstView!LastName & ", " & rstView!Country 
     rstView.MoveNext 
     Loop 
     
     ' Change underlying data. 
     Set rstChange = dbsNorthwind.OpenRecordset("Employees") 
     rstChange.AddNew 
     rstChange!FirstName = "Nina" 
     rstChange!LastName = "Roberts" 
     rstChange!Country = "USA" 
     rstChange.Update 
     
     rstView.Requery 
     Debug.Print "Requery after changing underlying data" 
     Set rstView = qdfTemp.OpenRecordset 
     Do While Not rstView.EOF 
     Debug.Print " " & rstView!FirstName & " " & _ 
     rstView!LastName & ", " & rstView!Country 
     rstView.MoveNext 
     Loop 
     
     ' Restore original data because this is only a 
     ' demonstration. 
     rstChange.Bookmark = rstChange.LastModified 
     rstChange.Delete 
     rstChange.Close 
     
     rstView.Close 
     dbsNorthwind.Close 
     
    End Sub 
```

<br/>

以下示例演示如何在更改查询参数后，使用 **Requery** 方法刷新查询。

```vb
Sub RequeryX2() 
 
 Dim dbsNorthwind As Database 
 Dim qdfTemp As QueryDef 
 Dim prmCountry As Parameter 
 Dim rstView As Recordset2 
 
 Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
 Set qdfTemp = dbsNorthwind.CreateQueryDef("", _ 
 "PARAMETERS ViewCountry Text; " & _ 
 "SELECT FirstName, LastName, Country FROM " & _ 
 "Employees WHERE Country = [ViewCountry] " & _ 
 "ORDER BY LastName") 
 Set prmCountry = qdfTemp.Parameters!ViewCountry 
 
 qdfTemp.Parameters!ViewCountry = "USA" 
 Debug.Print "Data after initial query, " & _ 
 [ViewCountry] = USA" 
 Set rstView = qdfTemp.OpenRecordset 
 Do While Not rstView.EOF 
 Debug.Print " " & rstView!FirstName & " " & _ 
 rstView!LastName & ", " & rstView!Country 
 rstView.MoveNext 
 Loop 
 
 ' Change query parameter. 
 qdfTemp.Parameters!ViewCountry = "UK" 
 ' QueryDef argument must be included so that the 
 ' resulting Recordset reflects the change in the query 
 ' parameter. 
 rstView.Requery qdfTemp 
 Debug.Print "Requery after changing parameter, " & _ 
 "[ViewCountry] = UK" 
 Do While Not rstView.EOF 
 Debug.Print " " & rstView!FirstName & " " & _ 
 rstView!LastName & ", " & rstView!Country 
 rstView.MoveNext 
 Loop 
 
 rstView.Close 
 dbsNorthwind.Close 
 
End Sub 
 
```

