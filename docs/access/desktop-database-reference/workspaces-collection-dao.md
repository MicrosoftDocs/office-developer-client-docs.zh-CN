---
title: Workspaces 集合 (DAO)
TOCTitle: Workspaces Collection
ms:assetid: 88b851ce-4180-964f-582e-bc9571bf554c
ms:mtpsurl: https://msdn.microsoft.com/library/Ff197057(v=office.15)
ms:contentKeyID: 48546142
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 4c615be9e92a936486c15377514c2b695f68bb5b
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28698412"
---
# <a name="workspaces-collection-dao"></a>Workspaces 集合 (DAO)


**适用于**： Access 2013、 Office 2013

**Workspaces** 集合包含 **DBEngine** 对象的所有活动、未隐藏的 **Workspace** 对象。（隐藏的 **Workspace** 对象并不追加到集合中，而是通过它们分配到的变量进行引用）。

## <a name="remarks"></a>注解

使用 **Workspace** 对象可以管理当前会话或启动其他会话。

当您首次引用，或者使用**Workspace**对象时，您将自动创建默认工作区，DBEngine.Workspaces(0)。 默认工作区的**名称**和**UserName**属性的设置"\#默认工作区\#"和"Admin，"分别。 如果启用了安全性，则 **UserName** 属性设置就是登录用户的名称。

您可以使用 [**CreateWorkspace**](dbengine-createworkspace-method-dao.md) 方法创建新的 **Workspace** 对象。创建新的 **Workspace** 对象后，如果需要从 **Workspaces** 集合引用该对象，则必须将其追加到 **Workspaces** 集合。不过，您无需将新创建的 **Workspace** 对象追加到 **Workspaces** 集合，便可以使用该对象。

若要按照序号或 **Name** 属性设置来引用集合中的 **Workspace** 对象，可以使用下列任何一种语法形式：

**DBEngine**。**工作区**(0)

**DBEngine**。**工作区**("name")

**DBEngine**。**工作区**\!\[名称\]


> [!NOTE]
> Microsoft Access 2013 中不支持适用于 ODBCDirect 工作区。 如果要在不使用 Microsoft Access 数据库引擎的情况下访问外部数据源，请使用 ADO。



## <a name="example"></a>示例

该示例创建一个新的 Microsoft Access 工作区对象并将其追加到 **Workspaces** 集合。然后，该示例枚举 **Workspaces** 集合和 **Workspace** 对象的 **Properties** 集合。

```vb 
Sub WorkspaceX() 
 
 Dim wrkNewAcc As Workspace 
 Dim wrkLoop As Workspace 
 Dim prpLoop As Property 
 
 ' Create a new Microsoft Access workspace. 
 Set wrkNewAcc = CreateWorkspace("NewAccessWorkspace", _ 
 "admin", "", dbUseJet) 
 Workspaces.Append wrkNewAcc 
 
 ' Enumerate the Workspaces collection. 
 For Each wrkLoop In Workspaces 
 With wrkLoop 
 Debug.Print "Properties of " & .Name 
 ' Enumerate the Properties collection of the new 
 ' Workspace object. 
 For Each prpLoop In .Properties 
 On Error Resume Next 
 If prpLoop <> "" Then Debug.Print " " & _ 
 prpLoop.Name & " = " & prpLoop 
 On Error GoTo 0 
 Next prpLoop 
 End With 
 Next wrkLoop 
 
 wrkNewAcc.Close 
End Sub 
```

<br/>

该示例使用 **CreateWorkspace** 方法创建一个 Microsoft Access 工作区，然后列出该工作区的属性。

```vb 
Sub CreateWorkspaceX() 
 
 Dim wrkAcc As Workspace 
 Dim wrkLoop As Workspace 
 Dim prpLoop As Property 
 
 
 DefaultType = dbUseJet 
 ' Create an unnamed Workspace object of the type 
 ' specified by the DefaultType property of DBEngine 
 ' (dbUseJet). 
 Set wrkAcc = CreateWorkspace("", "admin", "") 
 
 ' Enumerate Workspaces collection. 
 Debug.Print "Workspace objects in Workspaces collection:" 
 For Each wrkLoop In Workspaces 
 Debug.Print " " & wrkLoop.Name 
 Next wrkLoop 
 
 With wrkAcc 
 ' Enumerate Properties collection of Microsoft Access 
 ' workspace. 
 Debug.Print _ 
 "Properties of unnamed Microsoft Access workspace" 
 On Error Resume Next 
 For Each prpLoop In .Properties 
 Debug.Print " " & prpLoop.Name & " = " & prpLoop 
 Next prpLoop 
 On Error GoTo 0 
 End With 
 
 wrkAcc.Close 
 
End Sub 
 
```

