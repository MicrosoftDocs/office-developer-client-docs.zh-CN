---
title: Connections 集合 (DAO)
TOCTitle: Connections collection
ms:assetid: 65d073be-a84b-e3f2-cb43-b87ffa60e497
ms:mtpsurl: https://msdn.microsoft.com/library/Ff195178(v=office.15)
ms:contentKeyID: 48545330
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 66f122b7bdaa9069b839cd5884b5da5da48a15f9
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32295784"
---
# <a name="connections-collection-dao"></a><span data-ttu-id="accdf-102">Connections 集合 (DAO)</span><span class="sxs-lookup"><span data-stu-id="accdf-102">Connections collection (DAO)</span></span>

<span data-ttu-id="accdf-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="accdf-103">**Applies to**: Access 2013, Office 2013</span></span>

> [!NOTE]
> <span data-ttu-id="accdf-104">Microsoft Access 2013 中不支持 ODBCDirect 工作区。</span><span class="sxs-lookup"><span data-stu-id="accdf-104">ODBCDirect workspaces are not supported in Microsoft Access 2013.</span></span> <span data-ttu-id="accdf-105">如果要在不使用 Microsoft Access 数据库引擎的情况下访问外部数据源，请使用 ADO。</span><span class="sxs-lookup"><span data-stu-id="accdf-105">Use ADO if you want to access external data sources without using the Microsoft Access database engine.</span></span>

<span data-ttu-id="accdf-106">**Connections**集合包含**Workspace**对象的当前**Connection**对象。</span><span class="sxs-lookup"><span data-stu-id="accdf-106">A **Connections** collection contains the current **Connection** objects of a **Workspace** object.</span></span> <span data-ttu-id="accdf-107">一个 Connections 集合，包含 Workspace 对象的当前 Connection 对象（仅适用于 ODBCDirect 工作区）。</span><span class="sxs-lookup"><span data-stu-id="accdf-107">(ODBCDirect workspaces only).</span></span>

## <a name="remarks"></a><span data-ttu-id="accdf-108">注解</span><span class="sxs-lookup"><span data-stu-id="accdf-108">Remarks</span></span>

<span data-ttu-id="accdf-109">打开 **Connection** 对象时，该对象会自动追加到 **Workspace** 的 **Connections** 集合中。</span><span class="sxs-lookup"><span data-stu-id="accdf-109">When you open a **Connection** object, it is automatically appended to the **Connections** collection of the **Workspace**.</span></span> <span data-ttu-id="accdf-110">使用 **[Close](connection-close-method-dao.md)** 方法关闭 **Connection** 对象时，会从 **Connections** 集合中删除该对象。</span><span class="sxs-lookup"><span data-stu-id="accdf-110">When you close a **Connection** object with the **[Close](connection-close-method-dao.md)** method, it is removed from the **Connections** collection.</span></span> <span data-ttu-id="accdf-111">应先关闭**连接**中所有打开的**[Recordset](recordset-object-dao.md)** 对象, 然后再将其关闭。</span><span class="sxs-lookup"><span data-stu-id="accdf-111">You should close all open **[Recordset](recordset-object-dao.md)** objects within the **Connection** before closing it.</span></span>

<span data-ttu-id="accdf-112">打开 **Connection** 对象的同时，会创建一个相应的 **[Database](database-object-dao.md)** 对象，该对象追加到同一 **Workspace** 中的 **[Databases](databases-collection-dao.md)** 集合中，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="accdf-112">At the same time you open a **Connection** object, a corresponding **[Database](database-object-dao.md)** object is created and appended to the **[Databases](databases-collection-dao.md)** collection in the same **Workspace**, and vice versa.</span></span> <span data-ttu-id="accdf-113">同样，关闭 **Connection** 时，即从 **Databases** 集合中删除相应的 **Database**，依此类推。</span><span class="sxs-lookup"><span data-stu-id="accdf-113">Similarly, when you close the **Connection**, the corresponding **Database** is deleted from the **Databases** collection, and so on.</span></span>

<span data-ttu-id="accdf-p105">**Connection** 的 **Name** 属性设置是一个指定数据库文件路径的字符串。若要按照序号或 **Name** 属性设置来引用集合中的 **Connection** 对象，可以使用下列任何一种语法形式：</span><span class="sxs-lookup"><span data-stu-id="accdf-p105">The **Name** property setting of a **Connection** is a string that specifies the path of the database file. To refer to a **Connection** object in a collection by its ordinal number or by its **Name** property setting, use any of the following syntax forms:</span></span>

- <span data-ttu-id="accdf-116">**连接**0</span><span class="sxs-lookup"><span data-stu-id="accdf-116">**Connections**(0)</span></span>

- <span data-ttu-id="accdf-117">**连接**("*名称*")</span><span class="sxs-lookup"><span data-stu-id="accdf-117">**Connections**("*name*")</span></span>

- <span data-ttu-id="accdf-118">\*\*\*\*\!连接\[*名称*\]</span><span class="sxs-lookup"><span data-stu-id="accdf-118">**Connections**\!\[*name*\]</span></span>


> [!NOTE]
> <span data-ttu-id="accdf-p106">[!注释] 可以多次打开同一数据源，这样会在 **Connections** 集合中生成重复的名称。应当将 **Connection** 对象分配给对象变量，并通过变量名来引用它们。</span><span class="sxs-lookup"><span data-stu-id="accdf-p106">You can open the same data source more than once, creating duplicate names in the **Connections** collection. You should assign **Connection** objects to object variables and refer to them by variable name.</span></span>


## <a name="example"></a><span data-ttu-id="accdf-121">示例</span><span class="sxs-lookup"><span data-stu-id="accdf-121">Example</span></span>

<span data-ttu-id="accdf-122">以下示例通过打开一个 **Database** 对象和两个 ODBCDirect **Connection** 对象并列出可用于每个对象的属性，来演示 **Connection** 对象和 **Connections** 集合。</span><span class="sxs-lookup"><span data-stu-id="accdf-122">This example demonstrates the **Connection** object and **Connections** collection by opening a **Database** object and two ODBCDirect **Connection** objects and listing the properties available to each object.</span></span>

```vb 
Sub ConnectionObjectX() 
 
   Dim wrkAcc as Workspace 
   Dim dbsNorthwind As Database 
   Dim wrkODBC As Workspace 
   Dim conPubs As Connection 
   Dim conPubs2 As Connection 
   Dim conLoop As Connection 
   Dim prpLoop As Property 
 
   ' Open a Database object. 
   Set wrkAcc = CreateWorkspace("NewWorkspace", _ 
      "admin", "", dbUseJet) 
   Set dbsNorthwind = wrkAcc.OpenDatabase("Northwind.mdb") 
 
   ' Create ODBCDirect Workspace object and open Connection 
   ' objects. 
   Set wrkODBC = CreateWorkspace("NewODBCWorkspace", _ 
      "admin", "", dbUseODBC) 
       
   ' Note: The DSNs referenced below must be configured to  
   '       use Microsoft Windows NT Authentication Mode to  
   '       authorize user access to the Microsoft SQL Server. 
   Set conPubs = wrkODBC.OpenConnection("Connection1", , , _ 
      "ODBC;DATABASE=pubs;DSN=Publishers") 
       
   Set conPubs2 = wrkODBC.OpenConnection("Connection2", , _ 
      True, "ODBC;DATABASE=pubs;DSN=Publishers") 
 
   Debug.Print "Database properties:" 
 
   With dbsNorthwind 
      ' Enumerate Properties collection of Database object. 
      For Each prpLoop In .Properties 
         On Error Resume Next 
         Debug.Print "  " & prpLoop.Name & " = " & _ 
            prpLoop.Value 
         On Error GoTo 0 
      Next prpLoop 
   End With 
 
   ' Enumerate the Connections collection. 
   For Each conLoop In wrkODBC.Connections 
      Debug.Print "Connection properties for " & _ 
         conLoop.Name & ":" 
 
      With conLoop 
         ' Print property values by explicitly calling each 
         ' Property object; the Connection object does not 
         ' support a Properties collection. 
         Debug.Print "  Connect = " & .Connect 
         ' Property actually returns a Database object. 
         Debug.Print "  Database[.Name] = " & _ 
            .Database.Name 
         Debug.Print "  Name = " & .Name 
         Debug.Print "  QueryTimeout = " & .QueryTimeout 
         Debug.Print "  RecordsAffected = " & _ 
            .RecordsAffected 
         Debug.Print "  StillExecuting = " & _ 
            .StillExecuting 
         Debug.Print "  Transactions = " & .Transactions 
         Debug.Print "  Updatable = " & .Updatable 
      End With 
 
   Next conLoop 
 
   dbsNorthwind.Close 
   conPubs.Close 
   conPubs2.Close 
   wrkAcc.Close 
   wrkODBC.Close 
 
End Sub 
 
```

<br/>

<span data-ttu-id="accdf-123">以下示例使用采用不同参数的 **OpenConnection** 方法打开三个不同的 **Connection** 对象。</span><span class="sxs-lookup"><span data-stu-id="accdf-123">This example uses the **OpenConnection** method with different parameters to open three different **Connection** objects.</span></span>

```vb 
Sub OpenConnectionX() 
 
   Dim wrkODBC As Workspace 
   Dim conPubs As Connection 
   Dim conPubs2 As Connection 
   Dim conPubs3 As Connection 
   Dim conLoop As Connection 
 
   ' Create ODBCDirect Workspace object. 
   Set wrkODBC = CreateWorkspace("NewODBCWorkspace", _ 
      "admin", "", dbUseODBC) 
 
   ' Open Connection object using supplied information in  
   ' the connect string. If this information were  
   ' insufficient, you could trap for an error rather than  
   ' go to an ODBC Driver Manager dialog box. 
   MsgBox "Opening Connection1..." 
       
    ' Note: The DSN referenced below must be set to  
    '       use Microsoft Windows NT Authentication Mode to  
    '       authorize user access to the Microsoft SQL Server. 
    Set conPubs = wrkODBC.OpenConnection("Connection1", _ 
       dbDriverNoPrompt, , _ 
       "ODBC;DATABASE=pubs;DSN=Publishers") 
 
   ' Open read-only Connection object based on information  
   ' you enter in the ODBC Driver Manager dialog box. 
   MsgBox "Opening Connection2..." 
   Set conPubs2 = wrkODBC.OpenConnection("Connection2", _ 
      dbDriverPrompt, True, "ODBC;DSN=Publishers;") 
 
   ' Open read-only Connection object by entering only the  
   ' missing information in the ODBC Driver Manager dialog  
   ' box. 
   MsgBox "Opening Connection3..." 
   Set conPubs3 = wrkODBC.OpenConnection("Connection3", _ 
      dbDriverCompleteRequired, True, _ 
      "ODBC;DATABASE=pubs;DSN=Publishers;") 
 
   ' Enumerate the Connections collection. 
   For Each conLoop In wrkODBC.Connections 
      Debug.Print "Connection properties for " & _ 
         conLoop.Name & ":" 
 
      With conLoop 
         ' Print property values by explicitly calling each 
         ' Property object; the Connection object does not 
         ' support a Properties collection. 
         Debug.Print "  Connect = " & .Connect 
         ' Property actually returns a Database object. 
         Debug.Print "  Database[.Name] = " & _ 
            .Database.Name 
         Debug.Print "  Name = " & .Name 
         Debug.Print "  QueryTimeout = " & .QueryTimeout 
         Debug.Print "  RecordsAffected = " & _ 
            .RecordsAffected 
         Debug.Print "  StillExecuting = " & _ 
            .StillExecuting 
         Debug.Print "  Transactions = " & .Transactions 
         Debug.Print "  Updatable = " & .Updatable 
      End With 
 
   Next conLoop 
 
   conPubs.Close 
   conPubs2.Close 
   conPubs3.Close 
   wrkODBC.Close 
 
End Sub 
 
```

