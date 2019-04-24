---
title: OpenConnection 方法 (DAO)
TOCTitle: OpenConnection Method
ms:assetid: 9d97f298-a2d5-3b91-2efd-57f06fbd4654
ms:mtpsurl: https://msdn.microsoft.com/library/Ff198249(v=office.15)
ms:contentKeyID: 48546628
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 70bdded6c149aa7aff405c769ba4462a46c20dfd
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32308335"
---
# <a name="workspaceopenconnection-method-dao"></a><span data-ttu-id="03c5d-102">OpenConnection 方法 (DAO)</span><span class="sxs-lookup"><span data-stu-id="03c5d-102">Workspace.OpenConnection method (DAO)</span></span>

<span data-ttu-id="03c5d-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="03c5d-103">**Applies to**: Access 2013, Office 2013</span></span>

## <a name="syntax"></a><span data-ttu-id="03c5d-104">语法</span><span class="sxs-lookup"><span data-stu-id="03c5d-104">Syntax</span></span>

<span data-ttu-id="03c5d-105">*表达式*。OpenConnection (***Name***、 ***Options***、 ***ReadOnly***、 ***Connect***)</span><span class="sxs-lookup"><span data-stu-id="03c5d-105">*expression* .OpenConnection(***Name***, ***Options***, ***ReadOnly***, ***Connect***)</span></span>

<span data-ttu-id="03c5d-106">*表达式*一个代表**Workspace**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="03c5d-106">*expression* A variable that represents a **Workspace** object.</span></span>

## <a name="parameters"></a><span data-ttu-id="03c5d-107">参数</span><span class="sxs-lookup"><span data-stu-id="03c5d-107">Parameters</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="03c5d-108">名称</span><span class="sxs-lookup"><span data-stu-id="03c5d-108">Name</span></span></p></th>
<th><p><span data-ttu-id="03c5d-109">必需/可选</span><span class="sxs-lookup"><span data-stu-id="03c5d-109">Required/optional</span></span></p></th>
<th><p><span data-ttu-id="03c5d-110">数据类型</span><span class="sxs-lookup"><span data-stu-id="03c5d-110">Data type</span></span></p></th>
<th><p><span data-ttu-id="03c5d-111">说明</span><span class="sxs-lookup"><span data-stu-id="03c5d-111">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="03c5d-112"><em>Name</em></span><span class="sxs-lookup"><span data-stu-id="03c5d-112"><em>Name</em></span></span></p></td>
<td><p><span data-ttu-id="03c5d-113">必需</span><span class="sxs-lookup"><span data-stu-id="03c5d-113">Required</span></span></p></td>
<td><p><span data-ttu-id="03c5d-114"><strong>String</strong></span><span class="sxs-lookup"><span data-stu-id="03c5d-114"><strong>String</strong></span></span></p></td>
<td><p><span data-ttu-id="03c5d-115">一个字符串表达式。</span><span class="sxs-lookup"><span data-stu-id="03c5d-115">A string expression.</span></span> <span data-ttu-id="03c5d-116">请参阅“说明”中的讨论。</span><span class="sxs-lookup"><span data-stu-id="03c5d-116">See the discussion under Remarks.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03c5d-117"><em>Options</em></span><span class="sxs-lookup"><span data-stu-id="03c5d-117"><em>Options</em></span></span></p></td>
<td><p><span data-ttu-id="03c5d-118">可选</span><span class="sxs-lookup"><span data-stu-id="03c5d-118">Optional</span></span></p></td>
<td><p><span data-ttu-id="03c5d-119"><strong>Variant</strong></span><span class="sxs-lookup"><span data-stu-id="03c5d-119"><strong>Variant</strong></span></span></p></td>
<td><p><span data-ttu-id="03c5d-p102">根据“说明”中的指定设置连接的各个选项。ODBC 驱动程序管理器根据此值向用户提示有关连接的信息，例如数据源名称 (DSN)、用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="03c5d-p102">sets various options for the connection, as specified in Remarks. Based on this value, the ODBC driver manager prompts the user for connection information such as data source name (DSN), user name, and password.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03c5d-122"><em>ReadOnly</em></span><span class="sxs-lookup"><span data-stu-id="03c5d-122"><em>ReadOnly</em></span></span></p></td>
<td><p><span data-ttu-id="03c5d-123">可选</span><span class="sxs-lookup"><span data-stu-id="03c5d-123">Optional</span></span></p></td>
<td><p><span data-ttu-id="03c5d-124"><strong>Variant</strong></span><span class="sxs-lookup"><span data-stu-id="03c5d-124"><strong>Variant</strong></span></span></p></td>
<td><p><span data-ttu-id="03c5d-125">
						如果连接针对只读访问权限打开，则为 <strong>True</strong>；如果连接针对读/写访问权限打开，则为 <strong>False</strong>（默认值）。</span><span class="sxs-lookup"><span data-stu-id="03c5d-125"><strong>True</strong> if the connection is to be opened for read-only access and <strong>False</strong> if the connection is to be opened for read/write access (default).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03c5d-126"><em>Connect</em></span><span class="sxs-lookup"><span data-stu-id="03c5d-126"><em>Connect</em></span></span></p></td>
<td><p><span data-ttu-id="03c5d-127">可选</span><span class="sxs-lookup"><span data-stu-id="03c5d-127">Optional</span></span></p></td>
<td><p><span data-ttu-id="03c5d-128"><strong>Variant</strong></span><span class="sxs-lookup"><span data-stu-id="03c5d-128"><strong>Variant</strong></span></span></p></td>
<td><p><span data-ttu-id="03c5d-129">一个 ODBC 连接字符串。</span><span class="sxs-lookup"><span data-stu-id="03c5d-129">An ODBC connection string.</span></span> <span data-ttu-id="03c5d-130">请参阅此字符串的特定元素和语法的<strong><a href="connection-connect-property-dao.md">Connect</a></strong>属性。</span><span class="sxs-lookup"><span data-stu-id="03c5d-130">See the <strong><a href="connection-connect-property-dao.md">Connect</a></strong> property for the specific elements and syntax of this string.</span></span> <span data-ttu-id="03c5d-131">预置&quot;的 ODBC;&quot;是必需的。</span><span class="sxs-lookup"><span data-stu-id="03c5d-131">A prepended &quot;ODBC;&quot; is required.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="return-value"></a><span data-ttu-id="03c5d-132">返回值</span><span class="sxs-lookup"><span data-stu-id="03c5d-132">Return value</span></span>

<span data-ttu-id="03c5d-133">Connection</span><span class="sxs-lookup"><span data-stu-id="03c5d-133">Connection</span></span>

## <a name="remarks"></a><span data-ttu-id="03c5d-134">注解</span><span class="sxs-lookup"><span data-stu-id="03c5d-134">Remarks</span></span>

<span data-ttu-id="03c5d-p104">使用 **OpenConnection** 方法可在 ODBCDirect 工作区中建立与 ODBC 数据源的连接。 **OpenConnection** 方法类似于 **OpenDatabase**，但不完全相同。主要差别在于 **OpenConnection** 只在 ODBCDirect 工作区中可用。</span><span class="sxs-lookup"><span data-stu-id="03c5d-p104">Use the **OpenConnection** method to establish a connection to an ODBC data source from an ODBCDirect workspace. The **OpenConnection** method is similar but not equivalent to **OpenDatabase**. The main difference is that **OpenConnection** is available only in an ODBCDirect workspace.</span></span>

<span data-ttu-id="03c5d-138">如果在 connect 参数中指定了已注册的 ODBC 数据源名称 (DSN), 则 name 参数可以是任何有效的字符串, 并且还将提供**Connection**对象的**name**属性。</span><span class="sxs-lookup"><span data-stu-id="03c5d-138">If you specify a registered ODBC data source name (DSN) in the connect argument, then the name argument can be any valid string, and will also provide the **Name** property for the **Connection** object.</span></span> <span data-ttu-id="03c5d-139">如果 connect 参数中不包含有效的 DSN, 则 name 必须引用有效的 ODBC DSN, 这也将是**name**属性。</span><span class="sxs-lookup"><span data-stu-id="03c5d-139">If a valid DSN is not included in the connect argument, then name must refer to a valid ODBC DSN, which will also be the **Name** property.</span></span> <span data-ttu-id="03c5d-140">如果 name 和 connect 都不包含有效的 DSN, 则可以通过 options 参数设置 ODBC 驱动程序管理器, 以提示用户输入所需的连接信息。</span><span class="sxs-lookup"><span data-stu-id="03c5d-140">If neither name nor connect contains a valid DSN, the ODBC driver manager can be set (via the options argument) to prompt the user for the required connection information.</span></span> <span data-ttu-id="03c5d-141">然后，通过提示而提供的 DSN 将会提供 **Name** 属性。</span><span class="sxs-lookup"><span data-stu-id="03c5d-141">The DSN supplied through the prompt then provides the **Name** property.</span></span>

<span data-ttu-id="03c5d-142">options 参数确定是否以及何时提示用户建立连接, 以及是否以异步方式打开连接。</span><span class="sxs-lookup"><span data-stu-id="03c5d-142">The options argument determines if and when to prompt the user to establish the connection, and whether or not to open the connection asynchronously.</span></span> <span data-ttu-id="03c5d-143">可以使用下列常量之一。</span><span class="sxs-lookup"><span data-stu-id="03c5d-143">You can use one of the following constants.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="03c5d-144">常量</span><span class="sxs-lookup"><span data-stu-id="03c5d-144">Constant</span></span></p></th>
<th><p><span data-ttu-id="03c5d-145">说明</span><span class="sxs-lookup"><span data-stu-id="03c5d-145">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="03c5d-146"><strong>dbDriverNoPrompt</strong></span><span class="sxs-lookup"><span data-stu-id="03c5d-146"><strong>dbDriverNoPrompt</strong></span></span></p></td>
<td><p><span data-ttu-id="03c5d-147">ODBC 驱动程序管理器使用 <em>dbname</em> 和 <em>connect</em> 中提供的连接字符串。</span><span class="sxs-lookup"><span data-stu-id="03c5d-147">The ODBC Driver Manager uses the connection string provided in <em>dbname</em> and <em>connect</em>.</span></span> <span data-ttu-id="03c5d-148">如果不提供足够的信息，将发生运行时错误。</span><span class="sxs-lookup"><span data-stu-id="03c5d-148">If you don't provide sufficient information, a run-time error occurs.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03c5d-149"><strong>dbDriverPrompt</strong></span><span class="sxs-lookup"><span data-stu-id="03c5d-149"><strong>dbDriverPrompt</strong></span></span></p></td>
<td><p><span data-ttu-id="03c5d-p108">ODBC 驱动程序管理器显示“ODBC 数据源”<strong></strong>对话框，其中显示 <em>dbname</em> 或 <em>connect</em> 中提供的所有相关信息。连接字符串由用户通过对话框选择的 DSN 组成。如果用户未指定 DSN，将使用默认 DSN。</span><span class="sxs-lookup"><span data-stu-id="03c5d-p108">The ODBC Driver Manager displays the <strong>ODBC Data Sources</strong> dialog box, which displays any relevant information supplied in <em>dbname</em> or <em>connect</em>. The connection string is made up of the DSN that the user selects via the dialog boxes, or, if the user doesn't specify a DSN, the default DSN is used.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03c5d-152"><strong>于 dbdrivercomplete</strong></span><span class="sxs-lookup"><span data-stu-id="03c5d-152"><strong>dbDriverComplete</strong></span></span></p></td>
<td><p><span data-ttu-id="03c5d-p109">默认值。如果 <em>connect</em> 参数包括完成连接所需的所有必要信息，ODBC 驱动程序管理器将使用 <em>connect</em> 中的字符串。否则，其表现与指定了 <strong>dbDriverPrompt</strong> 时相同。</span><span class="sxs-lookup"><span data-stu-id="03c5d-p109">Default. If the <em>connect</em> argument includes all the necessary information to complete a connection, the ODBC Driver Manager uses the string in <em>connect</em>. Otherwise it behaves as it does when you specify <strong>dbDriverPrompt</strong>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03c5d-156"><strong>dbDriverCompleteRequired</strong></span><span class="sxs-lookup"><span data-stu-id="03c5d-156"><strong>dbDriverCompleteRequired</strong></span></span></p></td>
<td><p><span data-ttu-id="03c5d-157">此选项的表现类似于 <strong>dbDriverComplete</strong>，不同之处在于，ODBC 驱动程序将禁止提示完成连接所不需要的任何信息。</span><span class="sxs-lookup"><span data-stu-id="03c5d-157">This option behaves like <strong>dbDriverComplete</strong> except the ODBC driver disables the prompts for any information not required to complete the connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03c5d-158"><strong>即用 dbrunasync</strong></span><span class="sxs-lookup"><span data-stu-id="03c5d-158"><strong>dbRunAsync</strong></span></span></p></td>
<td><p><span data-ttu-id="03c5d-159">异步执行方法。</span><span class="sxs-lookup"><span data-stu-id="03c5d-159">Execute the method asynchronously.</span></span> <span data-ttu-id="03c5d-160">此常量可以与其他任何 <em>options</em> 常量一起使用。</span><span class="sxs-lookup"><span data-stu-id="03c5d-160">This constant may be used with any of the other <em>options</em> constants.</span></span></p></td>
</tr>
</tbody>
</table>

<br/>

<span data-ttu-id="03c5d-p111">**OpenConnection** 返回包含有关连接的信息的 **Connection** 对象。 **Connection** 对象与 **[Database](database-object-dao.md)** 对象类似。主要差别在于 **Database** 对象通常代表数据库，尽管也可以使用它代表在 Microsoft Access 工作区中与 ODBC 数据源建立的连接。</span><span class="sxs-lookup"><span data-stu-id="03c5d-p111">**OpenConnection** returns a **Connection** object which contains information about the connection. The **Connection** object is similar to a **[Database](database-object-dao.md)** object. The principal difference is that a **Database** object usually represents a database, although it can be used to represent a connection to an ODBC data source from a Microsoft Access workspace.</span></span>

## <a name="example"></a><span data-ttu-id="03c5d-164">示例</span><span class="sxs-lookup"><span data-stu-id="03c5d-164">Example</span></span>

<span data-ttu-id="03c5d-165">以下示例使用采用不同参数的 **OpenConnection** 方法打开三个不同的 **Connection** 对象。</span><span class="sxs-lookup"><span data-stu-id="03c5d-165">This example uses the **OpenConnection** method with different parameters to open three different **Connection** objects.</span></span>

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
 ' use Microsoft Windows NT Authentication Mode to 
 ' authorize user access to the Microsoft SQL Server. 
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
 Debug.Print " Connect = " & .Connect 
 ' Property actually returns a Database object. 
 Debug.Print " Database[.Name] = " & _ 
 .Database.Name 
 Debug.Print " Name = " & .Name 
 Debug.Print " QueryTimeout = " & .QueryTimeout 
 Debug.Print " RecordsAffected = " & _ 
 .RecordsAffected 
 Debug.Print " StillExecuting = " & _ 
 .StillExecuting 
 Debug.Print " Transactions = " & .Transactions 
 Debug.Print " Updatable = " & .Updatable 
 End With 
 
 Next conLoop 
 
 conPubs.Close 
 conPubs2.Close 
 conPubs3.Close 
 wrkODBC.Close 
 
End Sub 
 
```

<br/>

<span data-ttu-id="03c5d-166">以下示例通过打开一个 Microsoft Access **Database** 对象和两个 ODBCDirect **Connection** 对象，并列出每个对象可用的属性，来演示 **Connection** 对象和 **Connections** 集合。</span><span class="sxs-lookup"><span data-stu-id="03c5d-166">This example demonstrates the **Connection** object and **Connections** collection by opening a Microsoft Access **Database** object and two ODBCDirect **Connection** objects and listing the properties available to each object.</span></span>

```vb 
Sub ConnectionObjectX() 
 
 Dim wrkAcc as Workspace 
 Dim dbsNorthwind As Database 
 Dim wrkODBC As Workspace 
 Dim conPubs As Connection 
 Dim conPubs2 As Connection 
 Dim conLoop As Connection 
 Dim prpLoop As Property 
 
 ' Open Microsoft Access Database object. 
 Set wrkAcc = CreateWorkspace("NewWorkspace", _ 
 "admin", "", dbUseJet) 
 Set dbsNorthwind = wrkAcc.OpenDatabase("Northwind.mdb") 
 
 ' Create ODBCDirect Workspace object and open Connection 
 ' objects. 
 Set wrkODBC = CreateWorkspace("NewODBCWorkspace", _ 
 "admin", "", dbUseODBC) 
 
 ' Note: The DSNs referenced below must be configured to 
 ' use Microsoft Windows NT Authentication Mode to 
 ' authorize user access to the Microsoft SQL Server. 
 Set conPubs = wrkODBC.OpenConnection("Connection1", , , _ 
 "ODBC;DATABASE=pubs;DSN=Publishers") 
 
 Set conPubs2 = wrkODBC.OpenConnection("Connection2", , _ 
 True, "ODBC;DATABASE=pubs;DSN=Publishers") 
 
 Debug.Print "Database properties:" 
 
 With dbsNorthwind 
 ' Enumerate Properties collection of Database object. 
 For Each prpLoop In .Properties 
 On Error Resume Next 
 Debug.Print " " & prpLoop.Name & " = " & _ 
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
 Debug.Print " Connect = " & .Connect 
 ' Property actually returns a Database object. 
 Debug.Print " Database[.Name] = " & _ 
 .Database.Name 
 Debug.Print " Name = " & .Name 
 Debug.Print " QueryTimeout = " & .QueryTimeout 
 Debug.Print " RecordsAffected = " & _ 
 .RecordsAffected 
 Debug.Print " StillExecuting = " & _ 
 .StillExecuting 
 Debug.Print " Transactions = " & .Transactions 
 Debug.Print " Updatable = " & .Updatable 
 End With 
 
 Next conLoop 
 
 dbsNorthwind.Close 
 conPubs.Close 
 conPubs2.Close 
 wrkAcc.Close 
 wrkODBC.Close 
 
End Sub 
 
```

