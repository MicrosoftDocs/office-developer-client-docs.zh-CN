---
title: Recordset。可重新启动属性 (DAO)
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
localization_priority: Normal
ms.openlocfilehash: 5142d0d47be37ca8c2e1c6b89462c05b7d41d302
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32307572"
---
# <a name="recordsetrestartable-property-dao"></a>Recordset。可重新启动属性 (DAO)


**适用于**：Access 2013、Office 2013

返回一个值，该值表示 **[Recordset](recordset-object-dao.md)** 对象是否支持 **[Requery](recordset-requery-method-dao.md)** 方法，该方法重新执行 **Recordset** 对象所基于的查询。

## <a name="syntax"></a>语法

*表达式*。合用

*表达式*一个代表**Recordset**对象的变量。

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
