---
title: Connection.Database Property (DAO)
TOCTitle: Database Property
ms:assetid: cf871353-0ea4-f995-6e0e-812af443daf9
ms:mtpsurl: https://msdn.microsoft.com/library/Ff834675(v=office.15)
ms:contentKeyID: 48547809
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1053581
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 9627e5413e362baad505bfdf98092044499986c4
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25466934"
---
# <a name="connectiondatabase-property-dao"></a><span data-ttu-id="357ba-102">Connection.Database Property (DAO)</span><span class="sxs-lookup"><span data-stu-id="357ba-102">Connection.Database Property (DAO)</span></span>


<span data-ttu-id="357ba-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="357ba-103">**Applies to**: Access 2013 | Office 2013</span></span>



## <a name="syntax"></a><span data-ttu-id="357ba-104">语法</span><span class="sxs-lookup"><span data-stu-id="357ba-104">Syntax</span></span>

<span data-ttu-id="357ba-105">*表达式*。数据库</span><span class="sxs-lookup"><span data-stu-id="357ba-105">*expression* .Database</span></span>

<span data-ttu-id="357ba-106">*表达式*代表**Connection**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="357ba-106">*expression* A variable that represents a **Connection** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="357ba-107">注解</span><span class="sxs-lookup"><span data-stu-id="357ba-107">Remarks</span></span>

<span data-ttu-id="357ba-p101">对于 **[Connection](connection-object-dao.md)** 对象，使用 **Database** 属性可以获取指向对应于 **Connection** 的 **Database** 对象的引用。在 DAO 中， **Connection** 对象及其对应的 **Database** 对象只是指向相同对象的两个不同的对象变量引用。使用 **Connection** 对象的 **Database** 属性和 [Database](database-connection-property-dao.md) 对象的 \*\*\*\*Connection\*\*\*\* 属性可以更轻松地将通过 Microsoft Access 数据库引擎与 ODBC 数据源建立的连接更改为使用 ODBCDirect。</span><span class="sxs-lookup"><span data-stu-id="357ba-p101">On a **[Connection](connection-object-dao.md)** object, use the **Database** property to obtain a reference to a **Database** object that corresponds to the **Connection**. In DAO, a **Connection** object and its corresponding **Database** object are simply two different object variable references to the same object. The **Database** property of a **Connection** object and the **[Connection](database-connection-property-dao.md)** property of a **Database** object make it easier to change connections to an ODBC data source through the Microsoft Access database engine to use ODBCDirect.</span></span>

## <a name="example"></a><span data-ttu-id="357ba-111">示例</span><span class="sxs-lookup"><span data-stu-id="357ba-111">Example</span></span>

<span data-ttu-id="357ba-112">以下示例使用 **Database** 属性演示如何将通过 Microsoft Access 数据库引擎访问 ODBC 数据时使用的代码转换为使用 ODBCDirect 连接对象。</span><span class="sxs-lookup"><span data-stu-id="357ba-112">This example uses the **Database** property to show how code that used to access ODBC data through the Microsoft Access database engine can be converted to use ODBCDirect Connection objects.</span></span>

<span data-ttu-id="357ba-113">OldDatabaseCode 过程使用 Microsoft Access 数据库引擎连接的数据源访问 ODBC 数据库。</span><span class="sxs-lookup"><span data-stu-id="357ba-113">The OldDatabaseCode procedure uses a Microsoft Access database engine-connected data source to access an ODBC database.</span></span>

```vb
    Sub OldDatabaseCode() 
     
     Dim wrkMain As Workspace 
     Dim dbsPubs As Database 
     Dim prpLoop As Property 
     
     ' Create a Workspace object. 
     Set wrkMain = CreateWorkspace("", "admin", "", dbUseJet) 
     
     ' Open a Database object based on information in 
     ' the connect string. 
     
     'Note: The DSN referenced below must be configured to 
     ' use Microsoft Windows NT Authentication Mode to 
     ' authorize user access to the Microsoft SQL Server. 
     Set dbsPubs = wrkMain.OpenDatabase("Publishers", _ 
     dbDriverNoPrompt, False, _ 
     "ODBC;DATABASE=pubs;DSN=Publishers") 
     
     ' Enumerate the Properties collection of the Database 
     ' object. 
     With dbsPubs 
     Debug.Print "Database properties for " & _ 
     .Name & ":" 
     
     On Error Resume Next 
     For Each prpLoop In .Properties 
     If prpLoop.Name = "Connection" Then 
     ' Property actually returns a Connection object. 
     Debug.Print " Connection[.Name] = " & _ 
     .Connection.Name 
     Else 
     Debug.Print " " & prpLoop.Name & " = " & _ 
     prpLoop 
     End If 
     Next prpLoop 
     On Error GoTo 0 
     
     End With 
     
     dbsPubs.Close 
     wrkMain.Close 
     
    End Sub 
```

<span data-ttu-id="357ba-p102">NewDatabaseCode 示例将打开 ODBCDirect 工作区中的一个 **Connection** 对象。然后将 **Connection** 对象的 **Database** 属性分配给与旧过程中的数据源具有相同名称的对象变量。只要后续代码不使用特定于 Microsoft Access 工作区的任何功能，就不必更改此代码。</span><span class="sxs-lookup"><span data-stu-id="357ba-p102">The NewDatabaseCode example opens a **Connection** object in an ODBCDirect workspace. It then assigns the **Database** property of the **Connection** object to an object variable with the same name as the data source in the old procedure. None of the subsequent code has to be changed as long as it doesn't use any features specific to Microsoft Access workspaces.</span></span>

```vb 
Sub NewDatabaseCode() 
 
 Dim wrkMain As Workspace 
 Dim conPubs As Connection 
 Dim dbsPubs As Database 
 Dim prpLoop As Property 
 
 ' Create ODBCDirect Workspace object instead of Microsoft 
 ' Access Workspace object. 
 Set wrkMain = CreateWorkspace("", "admin", "", dbUseODBC) 
 
 ' Open Connection object based on information in 
 ' the connect string. 
 ' Note: The DSN referenced below must be configured to 
 ' use Microsoft Windows NT Authentication Mode to 
 ' authorize user access to the Microsoft SQL Server. 
 Set conPubs = wrkMain.OpenConnection("Publishers", _ 
 dbDriverNoPrompt, False, _ 
 "ODBC;DATABASE=pubs;DSN=Publishers") 
 ' Assign the Database property to the same object 
 ' variable as in the old code. 
 Set dbsPubs = conPubs.Database 
 
 ' Enumerate the Properties collection of the Database 
 ' object. From this point on, the code is the same as the 
 ' old example. 
 With dbsPubs 
 Debug.Print "Database properties for " & _ 
 .Name & ":" 
 
 On Error Resume Next 
 For Each prpLoop In .Properties 
 If prpLoop.Name = "Connection" Then 
 ' Property actually returns a Connection object. 
 Debug.Print " Connection[.Name] = " & _ 
 .Connection.Name 
 Else 
 Debug.Print " " & prpLoop.Name & " = " & _ 
 prpLoop 
 End If 
 Next prpLoop 
 On Error GoTo 0 
 
 End With 
 
 dbsPubs.Close 
 wrkMain.Close 
 
End Sub 
 
```
