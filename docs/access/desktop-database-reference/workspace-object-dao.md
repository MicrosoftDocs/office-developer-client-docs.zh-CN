---
title: Workspace Object (DAO)
TOCTitle: Workspace Object
ms:assetid: bf3ab863-5e9a-4842-1f82-2ccf958d9779
ms:mtpsurl: https://msdn.microsoft.com/library/Ff822782(v=office.15)
ms:contentKeyID: 48547481
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 86631fb15da775c3c5740dce704c519e2912ffba
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25467509"
---
# <a name="workspace-object-dao"></a><span data-ttu-id="ba0e0-102">Workspace Object (DAO)</span><span class="sxs-lookup"><span data-stu-id="ba0e0-102">Workspace Object (DAO)</span></span>

<span data-ttu-id="ba0e0-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="ba0e0-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="ba0e0-p101">**Workspace** 对象可以为用户定义一个命名的会话。该对象包含打开的数据库，并为同步事务处理提供机制，在 Microsoft Access 工作区中，它可以提供启用安全措施的工作组支持。</span><span class="sxs-lookup"><span data-stu-id="ba0e0-p101">A **Workspace** object defines a named session for a user. It contains open databases and provides mechanisms for simultaneous transactions and, in Microsoft Access workspaces, secure workgroup support.</span></span>

## <a name="remarks"></a><span data-ttu-id="ba0e0-106">注解</span><span class="sxs-lookup"><span data-stu-id="ba0e0-106">Remarks</span></span>

<span data-ttu-id="ba0e0-p102">**Workspace** 为非永久对象，可定义应用程序通过使用 Microsoft Access 数据库引擎与数据进行交互的方式。使用 **Workspace** 对象可以管理当前会话或启动其他会话。在会话中，可以打开多个数据库或连接，并管理事务。例如，您可以进行下列操作：</span><span class="sxs-lookup"><span data-stu-id="ba0e0-p102">A **Workspace** is a non-persistent object that defines how your application interacts with data by using the Microsoft Access database engine. Use the **Workspace** object to manage the current session or to start an additional session. In a session, you can open multiple databases or connections, and manage transactions. For example, you can:</span></span>

- <span data-ttu-id="ba0e0-p103">使用 **Name**、 **UserName** 和 **Type** 属性建立命名会话。该会话将创建一个范围，可以在其中打开多个数据库，以及处理嵌套事务的一个实例。</span><span class="sxs-lookup"><span data-stu-id="ba0e0-p103">Use the **Name**, **UserName**, and **Type** properties to establish a named session. The session creates a scope in which you can open multiple databases and conduct one instance of nested transactions.</span></span>

- <span data-ttu-id="ba0e0-113">使用 **Close** 方法终止会话。</span><span class="sxs-lookup"><span data-stu-id="ba0e0-113">Use the **Close** method to terminate a session.</span></span>

- <span data-ttu-id="ba0e0-114">使用 **OpenDatabase** 方法打开 **Workspace** 上的一个或多个现有数据库。</span><span class="sxs-lookup"><span data-stu-id="ba0e0-114">Use the **OpenDatabase** method to open one or more existing databases on a **Workspace**.</span></span>

- <span data-ttu-id="ba0e0-115">使用 **BeginTrans**、 **CommitTrans** 和 **Rollback** 方法管理 **Workspace** 中的嵌套事务处理，并使用多个 **Workspace** 对象处理多个同步且重叠的事务。</span><span class="sxs-lookup"><span data-stu-id="ba0e0-115">Use the **BeginTrans**, **CommitTrans**, and **Rollback** methods to manage nested transaction processing within a **Workspace** and use several **Workspace** objects to conduct multiple, simultaneous, and overlapping transactions.</span></span>

<span data-ttu-id="ba0e0-116">当您首次引用，或者使用**Workspace**对象时，您将自动创建默认工作区，DBEngine.Workspaces(0)。</span><span class="sxs-lookup"><span data-stu-id="ba0e0-116">When you first refer to or use a **Workspace** object, you automatically create the default workspace, DBEngine.Workspaces(0).</span></span> <span data-ttu-id="ba0e0-117">默认工作区的**名称**和**UserName**属性的设置"\#默认工作区\#"和"Admin，"分别。</span><span class="sxs-lookup"><span data-stu-id="ba0e0-117">The settings of the **Name** and **UserName** properties of the default workspace are "\#Default Workspace\#" and "Admin," respectively.</span></span> <span data-ttu-id="ba0e0-118">如果启用了安全性，则 **UserName** 属性设置就是登录用户的名称。</span><span class="sxs-lookup"><span data-stu-id="ba0e0-118">If security is enabled, the **UserName** property setting is the name of the user who logged on.</span></span>

<span data-ttu-id="ba0e0-p105">使用事务后，指定的 **Workspace** 中的所有数据库都将受到影响 - 即使在 **Workspace** 中打开了多个 **Database** 对象也是如此。例如，您使用 **BeginTrans** 方法更新某个数据库中的多条记录，然后删除另一个数据库中的记录。如果随后再使用 **Rollback** 方法，则更新和删除操作都将被取消和回滚。可以创建额外的 **Workspace** 对象来跨 **Database** 对象对事务进行独立管理。</span><span class="sxs-lookup"><span data-stu-id="ba0e0-p105">When you use transactions, all databases in the specified **Workspace** are affected— even if multiple **Database** objects are opened in the **Workspace**. For example, you use a **BeginTrans** method, update several records in a database, and then delete records in another database. If you then use the **Rollback** method, both the update and delete operations are canceled and rolled back. You can create additional **Workspace** objects to manage transactions independently across **Database** objects.</span></span>

<span data-ttu-id="ba0e0-p106">可以使用 **CreateWorkspace** 方法创建 **Workspace** 对象。创建新的 **Workspace** 对象后，如果需要从 **Workspaces** 集合引用该对象，则必须将其追加到 **Workspaces** 集合。</span><span class="sxs-lookup"><span data-stu-id="ba0e0-p106">You can create **Workspace** objects with the **CreateWorkspace** method. After you create a new **Workspace** object, you must append it to the **Workspaces** collection if you need to refer to it from the **Workspaces** collection.</span></span>

<span data-ttu-id="ba0e0-p107">可以使用新建的 **Workspace** 对象，且不需要将其追加到 **Workspaces** 集合。但是，必须通过为该集合分配的对象变量来对其进行引用。</span><span class="sxs-lookup"><span data-stu-id="ba0e0-p107">You can use a newly created **Workspace** object without appending it to the **Workspaces** collection. However, you must refer to it by the object variable to which you have assigned it.</span></span>

<span data-ttu-id="ba0e0-127">若要按照序号或 **Name** 属性设置来引用集合中的 **Workspace** 对象，可以使用下列任何一种语法形式：</span><span class="sxs-lookup"><span data-stu-id="ba0e0-127">To refer to a **Workspace** object in a collection by its ordinal number or by its **Name** property setting, use any of the following syntax forms:</span></span>

<span data-ttu-id="ba0e0-128">**DBEngine**。**工作区**(0)</span><span class="sxs-lookup"><span data-stu-id="ba0e0-128">**DBEngine**.**Workspaces**(0)</span></span>

<span data-ttu-id="ba0e0-129">**DBEngine**。**工作区**("name")</span><span class="sxs-lookup"><span data-stu-id="ba0e0-129">**DBEngine**.**Workspaces**("name")</span></span>

<span data-ttu-id="ba0e0-130">**DBEngine**。**工作区**\!\[名称\]</span><span class="sxs-lookup"><span data-stu-id="ba0e0-130">**DBEngine**.**Workspaces**\!\[name\]</span></span>

> [!NOTE]
> <span data-ttu-id="ba0e0-131">Microsoft Access 2013 中不支持适用于 ODBCDirect 工作区。</span><span class="sxs-lookup"><span data-stu-id="ba0e0-131">ODBCDirect workspaces are not supported in Microsoft Access 2013.</span></span> <span data-ttu-id="ba0e0-132">如果要在不使用 Microsoft Access 数据库引擎的情况下访问外部数据源，请使用 ADO。</span><span class="sxs-lookup"><span data-stu-id="ba0e0-132">Use ADO if you want to access external data sources without using the Microsoft Access database engine.</span></span>


## <a name="example"></a><span data-ttu-id="ba0e0-133">示例</span><span class="sxs-lookup"><span data-stu-id="ba0e0-133">Example</span></span>

<span data-ttu-id="ba0e0-p109">该示例创建一个新的 Microsoft Access 工作区对象并将其追加到 **Workspaces** 集合。然后，该示例枚举 **Workspaces** 集合和 **Workspace** 对象的 **Properties** 集合。</span><span class="sxs-lookup"><span data-stu-id="ba0e0-p109">This example creates a new Microsoft Access Workspace object and appends it to the **Workspaces** collection. It then enumerates the **Workspaces** collections and the **Properties** collection of the **Workspace** object.</span></span>

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
            If prpLoop <> "" Then Debug.Print "  " & _ 
               prpLoop.Name & " = " & prpLoop 
            On Error GoTo 0 
         Next prpLoop 
      End With 
   Next wrkLoop 
 
   wrkNewAcc.Close 
End Sub 
```

<br/>

<span data-ttu-id="ba0e0-p110">该示例使用 **CreateWorkspace** 方法创建一个 Microsoft Access 工作区，然后列出该工作区的属性。</span><span class="sxs-lookup"><span data-stu-id="ba0e0-p110">This example uses the **CreateWorkspace** method to create a Microsoft Access workspace. It then lists the properties of theworkspace.</span></span>

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
      Debug.Print "  " & wrkLoop.Name 
   Next wrkLoop 
 
   With wrkAcc 
      ' Enumerate Properties collection of Microsoft Access  
      ' workspace. 
      Debug.Print _ 
         "Properties of unnamed Microsoft Access workspace" 
      On Error Resume Next 
      For Each prpLoop In .Properties 
         Debug.Print "  " & prpLoop.Name & " = " & prpLoop 
      Next prpLoop 
      On Error GoTo 0 
   End With 
 
   wrkAcc.Close 
 
End Sub 
```

<br/>

<span data-ttu-id="ba0e0-138">下面的示例演示如何使用数据访问对象 (DAO) 工作区中的事务处理。</span><span class="sxs-lookup"><span data-stu-id="ba0e0-138">The following example shows how to use a transaction in a Data Access Objects (DAO) workspace.</span></span>

<span data-ttu-id="ba0e0-139">**示例代码提供者** [Microsoft Access 2010 Programmer's Reference](https://www.amazon.com/Microsoft-Access-2010-Programmers-Reference/dp/8126528125)。</span><span class="sxs-lookup"><span data-stu-id="ba0e0-139">**Sample code provided by** the [Microsoft Access 2010 Programmer’s Reference](https://www.amazon.com/Microsoft-Access-2010-Programmers-Reference/dp/8126528125).</span></span>


```vb
    Public Sub TransferFunds()
        Dim wrk As DAO.Workspace
        Dim dbC As DAO.Database
        Dim dbX As DAO.Database
        
        Set wrk = DBEngine(0)
        Set dbC = CurrentDb
        Set dbX = wrk.OpenDatabase("e:\books\acc2007vba\myDB.accdb")
        
        On Error GoTo trans_Err
        
        'Begin the transaction
        
        wrk.BeginTrans
        
        'Withdraw funds from one account table
        dbC.Execute "INSERT INTO tblAccounts ( Amount, Txn, TxnDate ) SELECT -20, 'DEBIT', Date()", dbFailOnError
    
        'Deposit funds into another account table
        dbX.Execute "INSERT INTO tblAccounts ( Amount, Txn, TxnDate ) SELECT 20, 'CREDIT', Date()", dbFailOnError
        
        'Commit the transaction
        wrk.CommitTrans dbForceOSFlush
        
    trans_Exit:
        'Clean up
        wrk.Close
        Set dbC = Nothing
        Set dbX = Nothing
        Set wrk = Nothing
        Exit Sub
        
    trans_Err:
        'Roll back the transaction
        wrk.Rollback
        Resume trans_Exit
        
    End Sub
```
