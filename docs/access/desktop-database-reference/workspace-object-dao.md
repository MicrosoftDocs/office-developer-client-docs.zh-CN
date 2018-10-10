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
# <a name="workspace-object-dao"></a>Workspace Object (DAO)

**适用于**： Access 2013 |Office 2013

**Workspace** 对象可以为用户定义一个命名的会话。该对象包含打开的数据库，并为同步事务处理提供机制，在 Microsoft Access 工作区中，它可以提供启用安全措施的工作组支持。

## <a name="remarks"></a>注解

**Workspace** 为非永久对象，可定义应用程序通过使用 Microsoft Access 数据库引擎与数据进行交互的方式。使用 **Workspace** 对象可以管理当前会话或启动其他会话。在会话中，可以打开多个数据库或连接，并管理事务。例如，您可以进行下列操作：

- 使用 **Name**、 **UserName** 和 **Type** 属性建立命名会话。该会话将创建一个范围，可以在其中打开多个数据库，以及处理嵌套事务的一个实例。

- 使用 **Close** 方法终止会话。

- 使用 **OpenDatabase** 方法打开 **Workspace** 上的一个或多个现有数据库。

- 使用 **BeginTrans**、 **CommitTrans** 和 **Rollback** 方法管理 **Workspace** 中的嵌套事务处理，并使用多个 **Workspace** 对象处理多个同步且重叠的事务。

当您首次引用，或者使用**Workspace**对象时，您将自动创建默认工作区，DBEngine.Workspaces(0)。 默认工作区的**名称**和**UserName**属性的设置"\#默认工作区\#"和"Admin，"分别。 如果启用了安全性，则 **UserName** 属性设置就是登录用户的名称。

使用事务后，指定的 **Workspace** 中的所有数据库都将受到影响 - 即使在 **Workspace** 中打开了多个 **Database** 对象也是如此。例如，您使用 **BeginTrans** 方法更新某个数据库中的多条记录，然后删除另一个数据库中的记录。如果随后再使用 **Rollback** 方法，则更新和删除操作都将被取消和回滚。可以创建额外的 **Workspace** 对象来跨 **Database** 对象对事务进行独立管理。

可以使用 **CreateWorkspace** 方法创建 **Workspace** 对象。创建新的 **Workspace** 对象后，如果需要从 **Workspaces** 集合引用该对象，则必须将其追加到 **Workspaces** 集合。

可以使用新建的 **Workspace** 对象，且不需要将其追加到 **Workspaces** 集合。但是，必须通过为该集合分配的对象变量来对其进行引用。

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

下面的示例演示如何使用数据访问对象 (DAO) 工作区中的事务处理。

**示例代码提供者** [Microsoft Access 2010 Programmer's Reference](https://www.amazon.com/Microsoft-Access-2010-Programmers-Reference/dp/8126528125)。


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
