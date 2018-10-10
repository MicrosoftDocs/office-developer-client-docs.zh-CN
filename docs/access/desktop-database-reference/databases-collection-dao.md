---
title: Databases Collection (DAO)
TOCTitle: Databases Collection
ms:assetid: 988ae6f5-ec15-cd1c-191d-f295624425f4
ms:mtpsurl: https://msdn.microsoft.com/library/Ff197944(v=office.15)
ms:contentKeyID: 48546493
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 23096391566f9d3f7649ef09839900e9ca009af6
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25468042"
---
# <a name="databases-collection-dao"></a>Databases Collection (DAO)

**适用于**： Access 2013 |Office 2013

**Databases** 集合包含在 **Workspace** 对象中打开或创建的所有打开的 **Database** 对象。

## <a name="remarks"></a>注解

从 **Workspace** 中打开现有 **Database** 对象或创建一个新对象时，该对象会自动追加到 **Databases** 集合中。使用 [**Close**](connection-close-method-dao.md) 方法关闭 **Database** 对象时，该对象即从 **Databases** 集合中删除，但并不从磁盘中删除。关闭 **Database** 对象之前，应关闭所有打开的 **Recordset** 对象。

在 Microsoft Access 工作区中，数据库的 **Name** 属性设置是一个指定数据库文件路径的字符串。

若要按照序号或 **Name** 属性设置来引用集合中的 **Database** 对象，可以使用下列任何一种语法形式：

- **Databases**(0)

- **数据库**（"*name*"）

- **数据库**\!\[*名称*\]

> [!NOTE]
> [!注释] 可以多次打开同一个数据源或数据库，这样会在 **Databases** 集合中创建重复的名称。应当将 **Database** 对象分配给对象变量，并通过变量名来引用它们。

## <a name="example"></a>示例

以下示例创建一个新的 **Database** 对象并打开默认 **Workspace** 对象中的一个现有 **Database** 对象。然后，该示例枚举 **Database** 集合以及每个 **Database** 对象的 **Properties** 集合。

```vb 
Sub DatabaseObjectX() 
 
 Dim wrkAcc As Workspace 
 Dim dbsNorthwind As Database 
 Dim dbsNew As Database 
 Dim dbsLoop As Database 
 Dim prpLoop As Property 
 
 Set wrkAcc = CreateWorkspace("AccWorkspace", "admin", _ 
 "", dbUseJet) 
 
 ' Make sure there isn't already a file with the name of 
 ' the new database. 
 If Dir("NewDB.mdb") <> "" Then Kill "NewDB.mdb" 
 
 ' Create a new database with the specified 
 ' collating order. 
 Set dbsNew = wrkAcc.CreateDatabase("NewDB.mdb", _ 
 dbLangGeneral) 
 Set dbsNorthwind = wrkAcc.OpenDatabase("Northwind.mdb") 
 
 ' Enumerate the Databases collection. 
 For Each dbsLoop In wrkAcc.Databases 
 With dbsLoop 
 Debug.Print "Properties of " & .Name 
 ' Enumerate the Properties collection of each 
 ' Database object. 
 For Each prpLoop In .Properties 
 If prpLoop <> "" Then Debug.Print " " & _ 
 prpLoop.Name & " = " & prpLoop 
 Next prpLoop 
 End With 
 Next dbsLoop 
 
 dbsNew.Close 
 dbsNorthwind.Close 
 wrkAcc.Close 
 
End Sub 
 
```

<br/>

以下示例使用 **CreateDatabase** 创建一个新的加密 **Database** 对象。

```vb
    Sub CreateDatabaseX() 
     
     Dim wrkDefault As Workspace 
     Dim dbsNew As DATABASE 
     Dim prpLoop As Property 
     
     ' Get default Workspace. 
     Set wrkDefault = DBEngine.Workspaces(0) 
     
     ' Make sure there isn't already a file with the name of 
     ' the new database. 
     If Dir("NewDB.mdb") <> "" Then Kill "NewDB.mdb" 
     
     ' Create a new encrypted database with the specified 
     ' collating order. 
     Set dbsNew = wrkDefault.CreateDatabase("NewDB.mdb", _ 
     dbLangGeneral, dbEncrypt) 
     
     With dbsNew 
     Debug.Print "Properties of " & .Name 
     ' Enumerate the Properties collection of the new 
     ' Database object. 
     For Each prpLoop In .Properties 
     If prpLoop <> "" Then Debug.Print " " & _ 
     prpLoop.Name & " = " & prpLoop 
     Next prpLoop 
     End With 
     
     dbsNew.Close 
     
    End Sub
```
