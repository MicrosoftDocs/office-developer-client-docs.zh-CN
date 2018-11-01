---
title: Recordset.Restartable Property (DAO)
TOCTitle: Restartable Property
ms:assetid: 00def49d-ea7e-6cd5-2f4a-914a1ddcdd51
ms:mtpsurl: https://msdn.microsoft.com/library/Ff844737(v=office.15)
ms:contentKeyID: 48542919
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1052926
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 782008e1fcad427a8d47a143dab0a54bc3b9e041
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25874641"
---
# <a name="recordsetrestartable-property-dao"></a>Recordset.Restartable Property (DAO)


**适用于**： Access 2013、 Office 2013

返回一个值，该值表示 **[Recordset](recordset-object-dao.md)** 对象是否支持 **[Requery](recordset-requery-method-dao.md)** 方法，该方法重新执行 **Recordset** 对象所基于的查询。

## <a name="syntax"></a>语法

*表达式*。可重新启动

*表达式*一个表示**Recordset**对象的变量。

## <a name="remarks"></a>注解

表类型 **Recordset** 对象始终返回 **False**。

在对 **Recordset** 对象使用 **Requery** 方法之前，检查 **Restartable** 属性。如果该对象的 **Restartable** 属性设置为 **False**，则对基础 **[QueryDef](connection-openrecordset-method-dao.md)** 对象使用 **[OpenRecordset](querydef-object-dao.md)** 方法，以重新执行查询。

## <a name="example"></a>示例

以下示例使用不同的 **Recordset** 对象演示 **Restartable** 属性。

```vb
    Sub RestartableX() 
     
     Dim dbsNorthwind As Database 
     Dim rstTemp As Recordset 
     
     Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
     
     With dbsNorthwind 
     ' Open a table-type Recordset and print its 
     ' Restartable property. 
     Set rstTemp = .OpenRecordset("Employees", dbOpenTable) 
     Debug.Print _ 
     "Table-type recordset from Employees table" 
     Debug.Print " Restartable = " & rstTemp.Restartable 
     rstTemp.Close 
     
     ' Open a Recordset from an SQL statement and print its 
     ' Restartable property. 
     Set rstTemp = _ 
     .OpenRecordset("SELECT * FROM Employees") 
     Debug.Print "Recordset based on SQL statement" 
     Debug.Print " Restartable = " & rstTemp.Restartable 
     rstTemp.Close 
     
     ' Open a Recordset from a saved QueryDef object and 
     ' print its Restartable property. 
     Set rstTemp = .OpenRecordset("Current Product List") 
     Debug.Print _ 
     "Recordset based on permanent QueryDef (" & _ 
     rstTemp.Name & ")" 
     Debug.Print " Restartable = " & rstTemp.Restartable 
     rstTemp.Close 
     
     .Close 
     End With 
     
    End Sub
```
