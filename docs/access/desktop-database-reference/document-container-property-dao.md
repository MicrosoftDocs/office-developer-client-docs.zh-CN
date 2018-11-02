---
title: Document.Container 属性 (DAO)
TOCTitle: Container Property
ms:assetid: aa1ace1d-f0b8-e0b0-20b6-d3e296254c51
ms:mtpsurl: https://msdn.microsoft.com/library/Ff821451(v=office.15)
ms:contentKeyID: 48546940
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1053320
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 1fcccc6b4a8ddd1122d75d86075e9cd63bd8dd22
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25919036"
---
# <a name="documentcontainer-property-dao"></a>Document.Container 属性 (DAO)


**适用于**： Access 2013、 Office 2013

返回 [Document](container-object-dao.md) 对象所属的 ****Container**** 对象的名称（仅适用于 Microsoft Access 工作区）。

## <a name="syntax"></a>语法

*表达式*。容器

*表达式*一个代表**Document**对象的变量。

## <a name="example"></a>示例

以下示例显示各种 **Document** 对象的 **Container** 属性。

```vb 
Sub ContainerPropertyX() 
 
 Dim dbsNorthwind As Database 
 Dim ctrLoop As Container 
 
 Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
 
 ' Display the container name for the first Document 
 ' object in each Container object's Documents collection. 
 For Each ctrLoop In dbsNorthwind.Containers 
 Debug.Print "Document: " & ctrLoop.Documents(0).Name 
 Debug.Print " Container = " & _ 
 ctrLoop.Documents(0).Container 
 Next ctrLoop 
 
 dbsNorthwind.Close 
 
End Sub 
 
```

