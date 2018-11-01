---
title: Database Object (DAO)
TOCTitle: Database Object
ms:assetid: 6cf2ddf8-3957-a15e-5eeb-85f81c1e415e
ms:mtpsurl: https://msdn.microsoft.com/library/Ff195520(v=office.15)
ms:contentKeyID: 48545482
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm0
f1_categories:
- Office.Version=v15
ms.openlocfilehash: ca0538f07f25ffe41288d15fd3737e08eb58f491
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25886751"
---
# <a name="database-object-dao"></a>Database Object (DAO)

**适用于**： Access 2013、 Office 2013

**Database** 对象代表打开的数据库。

## <a name="remarks"></a>注解

可使用 **Database** 对象及其方法和属性处理打开的数据库。在任何类型的数据库中，您可以进行下列操作：

  - 使用 **Execute** 方法运行动作查询。

  - 设置 **Connect** 属性建立与 ODBC 数据源的连接。

  - 设置 **QueryTimeout** 属性以限制对 ODBC 数据源执行查询时等待的时间长度。

  - 使用 **RecordsAffected** 属性确定动作查询更改了多少记录。

  - 使用 **OpenRecordset** 方法执行选择查询并创建 **Recordset** 对象。

  - 使用 **Version** 属性确定数据库是用哪个版本的数据库引擎创建的。

对于 Microsoft Access 数据库引擎数据库，还可以使用其他方法、属性和集合处理 **Database** 对象，以及创建、修改或获取与该对象的表、查询和关系有关的信息。例如，您可以进行下列操作：

  - 分别使用 **CreateTableDef** 和 **CreateRelation** 方法创建表和关系。

  - 使用 **CreateProperty** 方法定义新的 **Database** 属性。

  - 使用 **CreateQueryDef** 方法创建永久或临时的查询定义。

  - 使用 **MakeReplica**、 **Synchronize** 和 **PopulatePartial** 方法创建和同步数据库的整个或部分副本。

  - 设置 **CollatingOrder** 属性以便为使用不同语言的基于字符的字段确定字母排序次序。

使用 **CreateDatabase** 方法创建一个永久的 **Database** 对象，该对象会自动追加到 **Databases** 集合，从而可保存到磁盘上。

使用 **OpenDatabase** 方法时不需要指定 **DBEngine** 对象。

打开一个包含链接表的数据库不会自动建立指向指定的外部文件的链接。必须引用表的 **TableDef** 或 **Field** 对象，或打开 **Recordset** 对象。如果无法建立指向这些表的链接，将发生可捕获的错误。您可能还需要具有访问数据库的权限，或者，另一个用户可能以独占方式打开了数据库。在上述情况下，将发生可捕获的错误。

如果已执行声明 **Database** 对象的过程，本地 **Database** 对象将连同任何打开的 **Recordset** 对象一起关闭。任何待定的更新都会丢失，同时任何待定的事务都将回滚，但是不发生可捕获的错误。应显式完成任何待定的事务或编辑，再关闭 **Recordset** 对象和 **Database** 对象，然后退出在本地声明这些对象变量的过程。

如果对 **Workspace** 对象使用事务方法（**BeginTrans**、**CommitTrans** 或 **Rollback**）之一，那么这些事务可应用到在 **Workspace**（从其中打开了 **Database** 对象）上打开的所有数据库。如果需要使用独立的事务，首先必须打开一个额外的 **Workspace** 对象，然后打开该 **Workspace** 对象中的另一个 **Database** 对象。


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
 
 Set wrkAcc = CreateWorkspace("AccessWorkspace", "admin", _ 
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
