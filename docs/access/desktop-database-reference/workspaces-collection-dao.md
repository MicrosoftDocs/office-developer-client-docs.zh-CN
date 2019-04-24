---
title: workspace 集合 (DAO)
TOCTitle: Workspaces Collection
ms:assetid: 88b851ce-4180-964f-582e-bc9571bf554c
ms:mtpsurl: https://msdn.microsoft.com/library/Ff197057(v=office.15)
ms:contentKeyID: 48546142
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 4c615be9e92a936486c15377514c2b695f68bb5b
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32308321"
---
# <a name="workspaces-collection-dao"></a><span data-ttu-id="98934-102">workspace 集合 (DAO)</span><span class="sxs-lookup"><span data-stu-id="98934-102">Workspaces collection (DAO)</span></span>


<span data-ttu-id="98934-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="98934-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="98934-p101">**Workspaces** 集合包含 **DBEngine** 对象的所有活动、未隐藏的 **Workspace** 对象。（隐藏的 **Workspace** 对象并不追加到集合中，而是通过它们分配到的变量进行引用）。</span><span class="sxs-lookup"><span data-stu-id="98934-p101">A **Workspaces** collection contains all active, unhidden **Workspace** objects of the **DBEngine** object. (Hidden **Workspace** objects are not appended to the collection and referenced by the variable to which they are assigned.)</span></span>

## <a name="remarks"></a><span data-ttu-id="98934-106">注解</span><span class="sxs-lookup"><span data-stu-id="98934-106">Remarks</span></span>

<span data-ttu-id="98934-107">使用 **Workspace** 对象可以管理当前会话或启动其他会话。</span><span class="sxs-lookup"><span data-stu-id="98934-107">Use the **Workspace** object to manage the current session or to start an additional session.</span></span>

<span data-ttu-id="98934-108">当您首次引用或使用**Workspace**对象时, 将自动创建默认的工作区 DBEngine (0)。</span><span class="sxs-lookup"><span data-stu-id="98934-108">When you first refer to or use a **Workspace** object, you automatically create the default workspace, DBEngine.Workspaces(0).</span></span> <span data-ttu-id="98934-109">默认工作区的 "**名称**" 和 "**用户名**" 属性的设置\#分别为\#"默认工作区" 和 "管理员"。</span><span class="sxs-lookup"><span data-stu-id="98934-109">The settings of the **Name** and **UserName** properties of the default workspace are "\#Default Workspace\#" and "Admin," respectively.</span></span> <span data-ttu-id="98934-110">如果启用了安全性，则 **UserName** 属性设置就是登录用户的名称。</span><span class="sxs-lookup"><span data-stu-id="98934-110">If security is enabled, the **UserName** property setting is the name of the user who logged on.</span></span>

<span data-ttu-id="98934-p103">您可以使用 [**CreateWorkspace**](dbengine-createworkspace-method-dao.md) 方法创建新的 **Workspace** 对象。创建新的 **Workspace** 对象后，如果需要从 **Workspaces** 集合引用该对象，则必须将其追加到 **Workspaces** 集合。不过，您无需将新创建的 **Workspace** 对象追加到 **Workspaces** 集合，便可以使用该对象。</span><span class="sxs-lookup"><span data-stu-id="98934-p103">You can create new **Workspace** objects with the **[CreateWorkspace](dbengine-createworkspace-method-dao.md)** method. After you create a new **Workspace** object, you must append it to the **Workspaces** collection if you need to refer to it from the **Workspaces** collection. You can, however, use a newly created **Workspace** object without appending it to the **Workspaces** collection.</span></span>

<span data-ttu-id="98934-114">若要按照序号或 **Name** 属性设置来引用集合中的 **Workspace** 对象，可以使用下列任何一种语法形式：</span><span class="sxs-lookup"><span data-stu-id="98934-114">To refer to a **Workspace** object in a collection by its ordinal number or by its **Name** property setting, use any of the following syntax forms:</span></span>

<span data-ttu-id="98934-115">**DBEngine**。**工作区**0</span><span class="sxs-lookup"><span data-stu-id="98934-115">**DBEngine**.**Workspaces**(0)</span></span>

<span data-ttu-id="98934-116">**DBEngine**。**工作区**("名称")</span><span class="sxs-lookup"><span data-stu-id="98934-116">**DBEngine**.**Workspaces**("name")</span></span>

<span data-ttu-id="98934-117">**DBEngine**。**工作区**\! \[名称\]</span><span class="sxs-lookup"><span data-stu-id="98934-117">**DBEngine**.**Workspaces**\!\[name\]</span></span>


> [!NOTE]
> <span data-ttu-id="98934-118">Microsoft Access 2013 中不支持 ODBCDirect 工作区。</span><span class="sxs-lookup"><span data-stu-id="98934-118">ODBCDirect workspaces are not supported in Microsoft Access 2013.</span></span> <span data-ttu-id="98934-119">如果要在不使用 Microsoft Access 数据库引擎的情况下访问外部数据源，请使用 ADO。</span><span class="sxs-lookup"><span data-stu-id="98934-119">Use ADO if you want to access external data sources without using the Microsoft Access database engine.</span></span>



## <a name="example"></a><span data-ttu-id="98934-120">示例</span><span class="sxs-lookup"><span data-stu-id="98934-120">Example</span></span>

<span data-ttu-id="98934-p105">该示例创建一个新的 Microsoft Access 工作区对象并将其追加到 **Workspaces** 集合。然后，该示例枚举 **Workspaces** 集合和 **Workspace** 对象的 **Properties** 集合。</span><span class="sxs-lookup"><span data-stu-id="98934-p105">This example creates a new Microsoft Access Workspace object and appends it to the **Workspaces** collection. It then enumerates the **Workspaces** collections and the **Properties** collection of the **Workspace** object.</span></span>

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

<span data-ttu-id="98934-p106">该示例使用 **CreateWorkspace** 方法创建一个 Microsoft Access 工作区，然后列出该工作区的属性。</span><span class="sxs-lookup"><span data-stu-id="98934-p106">This example uses the **CreateWorkspace** method to create a Microsoft Access workspace. It then lists the properties of theworkspace.</span></span>

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

