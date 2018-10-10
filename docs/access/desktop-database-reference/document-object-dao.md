---
title: Document Object (DAO)
TOCTitle: Document Object
ms:assetid: b51d4545-b157-4c7c-fdbe-16a25afffdb3
ms:mtpsurl: https://msdn.microsoft.com/library/Ff822082(v=office.15)
ms:contentKeyID: 48547247
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 60fe0519bc722e688630f13acdd6701b96beff05
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25466656"
---
# <a name="document-object-dao"></a>Document Object (DAO)


**适用于**： Access 2013 |Office 2013

**Document** 对象包含有关对象实例的信息。该对象可以是数据库、保存的表、查询或关系（仅适用于 Microsoft Access 数据库引擎数据库）。

## <a name="remarks"></a>注解

每个 **Container** 对象具有一个 **Documents** 集合，该集合包含对 **Container** 所指定的内置对象类型的实例进行描述的 **Document** 对象。下表列出了每个 **Document** 描述的对象的类型、其 **Container** 对象的名称以及 **Document** 包含的信息类型。

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Document</p></th>
<th><p>Container</p></th>
<th><p>包含何类信息</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Database</p></td>
<td><p>Databases</p></td>
<td><p>保存的数据库</p></td>
</tr>
<tr class="even">
<td><p>Table 或 Query</p></td>
<td><p>Tables</p></td>
<td><p>保存的表或查询</p></td>
</tr>
<tr class="odd">
<td><p>Relationship</p></td>
<td><p>Relations</p></td>
<td><p>保存的关系</p></td>
</tr>
</tbody>
</table>



> [!NOTE]
> <P>[!注释] 不要将上表列出的 <STRONG>Container</STRONG> 对象与带有相同名称的集合相混淆。Databases <STRONG>Container</STRONG> 对象引用所有保存的数据库对象，但是 <STRONG>Databases</STRONG> 集合只引用在特定工作区中打开的数据库对象。</P>



对于 **Document** 对象，您可以进行下列操作：

  - 使用 **Name** 属性返回在创建某个对象时用户或 Microsoft Access 数据库引擎为该对象指定的名称。

  - 使用 **Container** 属性返回包含 **Document** 对象的 **Container** 对象的名称。

  - 使用 **Owner** 属性设置或返回对象的所有者。要设置 **Owner** 属性，必须对 **Document** 对象具有写入权限，并且必须将属性设置为现有的 **User** 或 **Group** 对象的名称。

  - 使用 **UserName** 或 **Permissions** 属性设置或返回对象的用户或组的访问权限。要设置这些属性，必须具有对 **Document** 对象的写入权限，并且必须将 **UserName** 属性设置为现有的 **User** 或 **Group** 对象的名称。

  - 使用 **DateCreated** 和 **LastUpdated** 属性返回创建或上次修改 **Document** 对象时的日期和时间。

因为 **Document** 对象对应于现有对象，所以不能创建新的 **Document** 对象，或删除现有的此类对象。若要按照序号或 **Name** 属性设置来引用集合中的 **Document** 对象，可以使用下列任何一种语法形式：

  - **Documents**(0)

  - **文档**（"*name*"）

  - **文档**\!\[*名称*\]

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

以下示例使用 **Owner** 和 **SystemDB** 属性显示多种 **Document** 对象的所有者。

```vb 
Sub OwnerX() 
 
 ' Ensure that the Microsoft Access workgroup file is 
 ' available. 
 DBEngine.SystemDB = "system.mdw" 
 
 Dim dbsNorthwind As Database 
 Dim ctrLoop As Container 
 
 Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
 
 With dbsNorthwind 
 Debug.Print "Document owners:" 
 ' Enumerate Containers collection and show the owner 
 ' of the first Document in each container's Documents 
 ' collection. 
 For Each ctrLoop In .Containers 
 With ctrLoop 
 Debug.Print " [" & .Documents(0).Name & _ 
 "] in [" & .Name & _ 
 "] container owned by [" & _ 
 .Documents(0).Owner & "]" 
 End With 
 Next ctrLoop 
 
 .Close 
 End With 
 
End Sub 
 
```

