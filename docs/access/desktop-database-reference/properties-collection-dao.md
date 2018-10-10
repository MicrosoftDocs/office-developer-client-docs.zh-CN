---
title: Properties Collection (DAO)
TOCTitle: Properties Collection
ms:assetid: cd07184a-a261-29c9-542f-bc2eff6f4af6
ms:mtpsurl: https://msdn.microsoft.com/library/Ff834455(v=office.15)
ms:contentKeyID: 48547753
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 45c36e12ab5d646e225690711d035ba8d36f4cc1
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25466172"
---
# <a name="properties-collection-dao"></a>Properties Collection (DAO)


**适用于**： Access 2013 |Office 2013

**Properties** 集合包含对象的特定实例的所有 **[Property](property-object-dao.md)** 对象。

## <a name="remarks"></a>注解

每个 DAO 对象（ **Connection** 和 **Error** 对象除外）都包含一个 **Properties** 集合，该集合具有某些内置的 **Property** 对象。这些 **Property** 对象（通常就称为属性）唯一地描述了对象的该实例。

除了内部属性，还可以创建并添加您自己的用户定义的属性。若要向对象的现有实例添加用户定义的属性，请首先使用 **CreateProperty** 方法定义该实例的特征，然后使用 **Append** 方法将该实例添加到集合中。如果引用尚未追加到 **Properties** 集合的用户定义的 **Property** 对象，则会发生错误；如果将用户定义的 **Property** 对象追加到包含同名 **Property** 对象的 **Properties** 集合中，也会发生错误。

可以使用 **Delete** 方法从 **Properties** 集合中删除用户定义的属性，但不能删除内置属性。


> [!NOTE]
> <P>[!注释] 一个用户定义的 <STRONG>Property</STRONG> 对象只与一个对象的特定实例相关联。属性并不是为选定类型的对象的所有实例定义的。</P>



若要按照序号或 **Name** 属性设置来引用集合中的内置 **Property** 对象，可以使用下列任何一种语法形式：

对象。**属性**(0)

对象。**属性**("name")

对象。**属性**\!\[名称\]

对于内置属性，还可以使用以下语法：

object.name


> [!NOTE]
> <P>对于用户定义的属性，您必须使用完整的对象。<STRONG>属性</STRONG>("name") 语法。</P>



使用同样的语法格式，还可以引用 **Property** 对象的 **Value** 属性。引用的上下文将确定是引用 **Property** 对象自身，还是引用 **Property** 对象的 **Value** 属性。

## <a name="example"></a>示例

以下示例为当前数据库创建用户定义的属性，设置该属性的 **Type** 和 **Value** 属性，并将该属性追加到数据库的 **Properties** 集合中。然后，该示例枚举数据库中的所有属性。

```vb
    Sub PropertyX() 
     
     Dim dbsNorthwind As Database 
     Dim prpNew As Property 
     Dim prpLoop As Property 
     
     Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
     
     With dbsNorthwind 
     ' Create and append user-defined property. 
     Set prpNew = .CreateProperty() 
     prpNew.Name = "UserDefined" 
     prpNew.Type = dbText 
     prpNew.Value = "This is a user-defined property." 
     .Properties.Append prpNew 
     
     ' Enumerate all properties of current database. 
     Debug.Print "Properties of " & .Name 
     For Each prpLoop In .Properties 
     With prpLoop 
     Debug.Print " " & .Name 
     Debug.Print " Type: " & .Type 
     Debug.Print " Value: " & .Value 
     Debug.Print " Inherited: " & _ 
     .Inherited 
     End With 
     Next prpLoop 
     
     ' Delete new property because this is a 
     ' demonstration. 
     .Properties.Delete "UserDefined" 
     End With 
     
    End Sub 
```

<br/>

以下示例尝试设置用户定义的属性的值。如果该属性不存在，则使用 **CreateProperty** 方法创建一个新属性并设置其值。若要使该过程运行，需要使用 SetProperty 过程。

```vb
    Sub CreatePropertyX() 
     
     Dim dbsNorthwind As Database 
     Dim prpLoop As Property 
     
     Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
     
     ' Set the Archive property to True. 
     SetProperty dbsNorthwind, "Archive", True 
     
     With dbsNorthwind 
     Debug.Print "Properties of " & .Name 
     
     ' Enumerate Properties collection of the Northwind 
     ' database. 
     For Each prpLoop In .Properties 
     If prpLoop <> "" Then Debug.Print " " & _ 
     prpLoop.Name & " = " & prpLoop 
     Next prpLoop 
     
     ' Delete the new property since this is a 
     ' demonstration. 
     .Properties.Delete "Archive" 
     
     .Close 
     End With 
     
    End Sub 
     
    Sub SetProperty(dbsTemp As Database, strName As String, _ 
     booTemp As Boolean) 
     
     Dim prpNew As Property 
     Dim errLoop As Error 
     
     ' Attempt to set the specified property. 
     On Error GoTo Err_Property 
     dbsTemp.Properties("strName") = booTemp 
     On Error GoTo 0 
     
     Exit Sub 
     
    Err_Property: 
     
     ' Error 3270 means that the property was not found. 
     If DBEngine.Errors(0).Number = 3270 Then 
     ' Create property, set its value, and append it to the 
     ' Properties collection. 
     Set prpNew = dbsTemp.CreateProperty(strName, _ 
     dbBoolean, booTemp) 
     dbsTemp.Properties.Append prpNew 
     Resume Next 
     Else 
     ' If different error has occurred, display message. 
     For Each errLoop In DBEngine.Errors 
     MsgBox "Error number: " & errLoop.Number & vbCr & _ 
     errLoop.Description 
     Next errLoop 
     End 
     End If 
     
    End Sub
```
