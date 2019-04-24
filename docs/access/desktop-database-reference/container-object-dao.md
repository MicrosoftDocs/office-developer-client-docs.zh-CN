---
title: 容器对象 (DAO)
TOCTitle: Container Object
ms:assetid: 22e487cd-e966-fe68-fff3-c680b460cbeb
ms:mtpsurl: https://msdn.microsoft.com/library/Ff191764(v=office.15)
ms:contentKeyID: 48543720
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: c9ebbeae35387f4fd59c39d4c20df6033edb06b0
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32295630"
---
# <a name="container-object-dao"></a>容器对象 (DAO)

**适用于**：Access 2013、Office 2013

**Container** 对象可将相似类型的 **Document** 对象组合在一起。

## <a name="remarks"></a>注解

每个 **Database** 对象都具有一个由内置 **Container** 对象组成的 **Containers** 集合。应用程序可以定义其自身的文档类型和相应的容器（仅适用于 Microsoft Access 数据库引擎数据库）；但是，不一定总能通过 DAO 支持这些对象。

这些 **Container** 对象中的一部分是由 Microsoft Access 数据库引擎定义的，而其余部分可能是由其他应用程序定义的。下表列出由 Microsoft Access 数据库引擎定义的每个 **Container** 对象的名称，以及该名称包含的信息类型。

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>容器名称</p></th>
<th><p>包含何类信息</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Databases</p></td>
<td><p>保存的数据库</p></td>
</tr>
<tr class="even">
<td><p>Tables</p></td>
<td><p>保存的表和查询</p></td>
</tr>
<tr class="odd">
<td><p>Relations</p></td>
<td><p>保存的关系</p></td>
</tr>
</tbody>
</table>

> [!NOTE]
> [!注释] 不要将上表列出的 **Container** 对象与带有相同名称的集合相混淆。Databases **Container** 对象引用所有保存的数据库对象，但是 **Databases** 集合只引用在特定工作区中打开的数据库对象。

每个 **Container** 对象具有一个 **Documents** 集合，该集合包含对 **Container** 所指定的内置对象类型的实例进行描述的 **Document** 对象。通常，可以将 **Container** 对象用作指向 **Document** 对象中的信息的中间链接。还可以使用 **Containers** 集合设置给定类型的所有 **Document** 对象的安全性。

对于现有的 **Container** 对象，您可以进行下列操作：

- 使用 **Name** 属性返回 **Container** 对象的预定义名称。

- 使用 **Owner** 属性设置或返回 **Container** 对象的所有者。要设置 **Owner** 属性，必须对 **Container** 对象具有写入权限，并且必须将属性设置为现有的 **User** 或 **Group** 对象的名称。

- 使用 **Permissions** 和 **UserName** 属性设置对 **Container** 对象的访问权限；在 **Container** 对象的 **Documents** 集合中创建的任何 **Document** 对象将继承这些访问权限设置。

因为 **Container** 对象是内置，所以不能创建新的 **Container** 对象，或删除现有的此类对象。

若要按照序号或 **Name** 属性设置来引用集合中的 **Container** 对象，可以使用下列任何一种语法形式：

- **容器**0

- **容器**("*名称*")

- ****\!容器\[*名称*\]

## <a name="example"></a>示例

以下示例枚举 Northwind 数据库的 **Containers** 集合以及该集合中每个 **Container** 对象的 **Properties** 集合。

```vb
    Sub ContainerObjectX() 
     
     Dim dbsNorthwind As Database 
     Dim ctrLoop As Container 
     Dim prpLoop As Property 
     
     Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
     
     With dbsNorthwind 
     
     ' Enumerate Containers collection. 
     For Each ctrLoop In .Containers 
     Debug.Print "Properties of " & ctrLoop.Name _ 
     & " container" 
     
     ' Enumerate Properties collection of each 
     ' Container object. 
     For Each prpLoop In ctrLoop.Properties 
     Debug.Print " " & prpLoop.Name _ 
     & " = " prpLoop 
     Next prpLoop 
     
     Next ctrLoop 
     
     .Close 
     End With 
     
    End Sub
```
