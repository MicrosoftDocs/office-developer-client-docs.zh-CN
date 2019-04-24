---
title: Documents 集合 (DAO)
TOCTitle: Documents Collection
ms:assetid: ae2fef58-34e7-eea6-ca51-d3903432c7f5
ms:mtpsurl: https://msdn.microsoft.com/library/Ff821742(v=office.15)
ms:contentKeyID: 48547063
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 2f6edd02c316fdff3f64b8a09c1504c46c9812a3
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32293747"
---
# <a name="documents-collection-dao"></a>Documents 集合 (DAO)


**适用于**：Access 2013、Office 2013

**Documents** 集合包含特定类型对象的所有 **Document** 对象（仅适用于 Microsoft Access 数据库引擎数据库）。

## <a name="remarks"></a>注解

每个 **Container** 对象具有一个 **Documents** 集合，该集合包含对 **Container** 所指定的内置对象类型的实例进行描述的 **Document** 对象。

若要按照序号或 **Name** 属性设置来引用集合中的 **Document** 对象，可以使用下列任何一种语法形式：

  - **Documents**(0)

  - **文档**("*名称*")

  - ****\!文档\[*名称*\]

## <a name="example"></a>示例

以下示例枚举 Tables 容器的 **Documents** 集合，然后枚举该集合中第一个 **Document** 对象的 **Properties** 集合。

```vb 
Sub DocumentX() 
 
 Dim dbsNorthwind As Database 
 Dim docLoop As Document 
 Dim prpLoop As Property 
 
 Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
 
 With dbsNorthwind.Containers!Tables 
 Debug.Print "Documents in " & .Name & " container" 
 ' Enumerate the Documents collection of the Tables 
 ' container. 
 For Each docLoop In .Documents 
 Debug.Print " " & docLoop.Name 
 Next docLoop 
 With .Documents(0) 
 ' Enumerate the Properties collection of the first. 
 ' Document object of the Tables container. 
 Debug.Print "Properties of " & .Name & " document" 
 On Error Resume Next 
 For Each prpLoop In .Properties 
 Debug.Print " " & prpLoop.Name & " = " & _ 
 prpLoop 
 Next prpLoop 
 On Error GoTo 0 
 End With 
 End With 
 
 dbsNorthwind.Close 
 
End Sub 
 
```

