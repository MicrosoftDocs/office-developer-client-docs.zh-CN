---
title: Workspace.OpenDatabase 方法 (DAO)
TOCTitle: OpenDatabase Method
ms:assetid: dbb93908-ec3e-f3ee-c4ea-cca48340b4d3
ms:mtpsurl: https://msdn.microsoft.com/library/Ff835343(v=office.15)
ms:contentKeyID: 48548108
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Priority
ms.openlocfilehash: ca2ccb4183a59c2b579fd4375f26aa4fd539532f
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28700953"
---
# <a name="workspaceopendatabase-method-dao"></a><span data-ttu-id="86104-102">Workspace.OpenDatabase 方法 (DAO)</span><span class="sxs-lookup"><span data-stu-id="86104-102">Workspace.OpenDatabase method (DAO)</span></span>

<span data-ttu-id="86104-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="86104-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="86104-104">打开 **[Workspace](workspace-object-dao.md)** 对象中的指定数据库，并返回一个指向代表该数据库的 **[Database](database-object-dao.md)** 对象的引用。</span><span class="sxs-lookup"><span data-stu-id="86104-104">Opens a specified database in a **[Workspace](workspace-object-dao.md)** object and returns a reference to the **[Database](database-object-dao.md)** object that represents it.</span></span>

## <a name="syntax"></a><span data-ttu-id="86104-105">语法</span><span class="sxs-lookup"><span data-stu-id="86104-105">Syntax</span></span>

<span data-ttu-id="86104-106">*表达式*。OpenDatabase （***名称***、***选项***、 ***ReadOnly***、***连接***）</span><span class="sxs-lookup"><span data-stu-id="86104-106">*expression* .OpenDatabase(***Name***, ***Options***, ***ReadOnly***, ***Connect***)</span></span>

<span data-ttu-id="86104-107">*表达式*一个代表**Workspace**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="86104-107">*expression* A variable that represents a **Workspace** object.</span></span>

## <a name="parameters"></a><span data-ttu-id="86104-108">Parameters</span><span class="sxs-lookup"><span data-stu-id="86104-108">Parameters</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="86104-109">Name</span><span class="sxs-lookup"><span data-stu-id="86104-109">Name</span></span></p></th>
<th><p><span data-ttu-id="86104-110">必需/可选</span><span class="sxs-lookup"><span data-stu-id="86104-110">Required/optional</span></span></p></th>
<th><p><span data-ttu-id="86104-111">数据类型</span><span class="sxs-lookup"><span data-stu-id="86104-111">Data type</span></span></p></th>
<th><p><span data-ttu-id="86104-112">说明</span><span class="sxs-lookup"><span data-stu-id="86104-112">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="86104-113"><em>Name</em></span><span class="sxs-lookup"><span data-stu-id="86104-113"><em>Name</em></span></span></p></td>
<td><p><span data-ttu-id="86104-114">必需</span><span class="sxs-lookup"><span data-stu-id="86104-114">Required</span></span></p></td>
<td><p><span data-ttu-id="86104-115"><strong>String</strong></span><span class="sxs-lookup"><span data-stu-id="86104-115"><strong>String</strong></span></span></p></td>
<td><p><span data-ttu-id="86104-p101">现有 Microsoft Access 数据库引擎数据库文件的名称，或者 ODBC 数据源的数据源名称 (DSN)。有关设置此值的详细信息，请参阅 <strong><a href="connection-name-property-dao.md">Name</a></strong> 属性。</span><span class="sxs-lookup"><span data-stu-id="86104-p101">the name of an existing Microsoft Access database engine database file, or the data source name (DSN) of an ODBC data source. See the <strong><a href="connection-name-property-dao.md">Name</a></strong> property for more information about setting this value.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86104-118"><em>Options</em></span><span class="sxs-lookup"><span data-stu-id="86104-118"><em>Options</em></span></span></p></td>
<td><p><span data-ttu-id="86104-119">可选</span><span class="sxs-lookup"><span data-stu-id="86104-119">Optional</span></span></p></td>
<td><p><span data-ttu-id="86104-120"><strong>Variant</strong></span><span class="sxs-lookup"><span data-stu-id="86104-120"><strong>Variant</strong></span></span></p></td>
<td><p><span data-ttu-id="86104-121">根据“说明”中的指定设置数据库的各个选项。</span><span class="sxs-lookup"><span data-stu-id="86104-121">Sets various options for the database, as specified in Remarks.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86104-122"><em>ReadOnly</em></span><span class="sxs-lookup"><span data-stu-id="86104-122"><em>ReadOnly</em></span></span></p></td>
<td><p><span data-ttu-id="86104-123">可选</span><span class="sxs-lookup"><span data-stu-id="86104-123">Optional</span></span></p></td>
<td><p><span data-ttu-id="86104-124"><strong>Variant</strong></span><span class="sxs-lookup"><span data-stu-id="86104-124"><strong>Variant</strong></span></span></p></td>
<td><p><span data-ttu-id="86104-125">						如果要使用只读访问权限打开数据库，此值为 <strong>True</strong>；如果要使用可读写访问权限打开数据库，此值为 <strong>False</strong>（默认值）。</span><span class="sxs-lookup"><span data-stu-id="86104-125"><strong>True</strong> if you want to open the database with read-only access, or <strong>False</strong> (default) if you want to open the database with read/write access.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86104-126"><em>Connect</em></span><span class="sxs-lookup"><span data-stu-id="86104-126"><em>Connect</em></span></span></p></td>
<td><p><span data-ttu-id="86104-127">可选</span><span class="sxs-lookup"><span data-stu-id="86104-127">Optional</span></span></p></td>
<td><p><span data-ttu-id="86104-128"><strong>Variant</strong></span><span class="sxs-lookup"><span data-stu-id="86104-128"><strong>Variant</strong></span></span></p></td>
<td><p><span data-ttu-id="86104-129">指定包括密码在内的各种连接信息。</span><span class="sxs-lookup"><span data-stu-id="86104-129">Specifies various connection information, including passwords.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="return-value"></a><span data-ttu-id="86104-130">返回值</span><span class="sxs-lookup"><span data-stu-id="86104-130">Return value</span></span>

<span data-ttu-id="86104-131">Database</span><span class="sxs-lookup"><span data-stu-id="86104-131">Database</span></span>

## <a name="remarks"></a><span data-ttu-id="86104-132">注解</span><span class="sxs-lookup"><span data-stu-id="86104-132">Remarks</span></span>

<span data-ttu-id="86104-133">可以为 options 参数使用以下值。</span><span class="sxs-lookup"><span data-stu-id="86104-133">You can use the following values for the options argument.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="86104-134">Setting</span><span class="sxs-lookup"><span data-stu-id="86104-134">Setting</span></span></p></th>
<th><p><span data-ttu-id="86104-135">说明</span><span class="sxs-lookup"><span data-stu-id="86104-135">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="86104-136"><strong>True</strong></span><span class="sxs-lookup"><span data-stu-id="86104-136"><strong>True</strong></span></span></p></td>
<td><p><span data-ttu-id="86104-137">以独占模式打开数据库。</span><span class="sxs-lookup"><span data-stu-id="86104-137">Opens the database in exclusive mode.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86104-138"><strong>False</strong></span><span class="sxs-lookup"><span data-stu-id="86104-138"><strong>False</strong></span></span></p></td>
<td><p><span data-ttu-id="86104-139">（默认值）以共享模式打开数据库。</span><span class="sxs-lookup"><span data-stu-id="86104-139">(Default) Opens the database in shared mode.</span></span></p></td>
</tr>
</tbody>
</table>

<br/>

<span data-ttu-id="86104-140">打开一个数据库后，该数据库将自动添加到 **Databases** 连接。</span><span class="sxs-lookup"><span data-stu-id="86104-140">When you open a database, it is automatically added to the **Databases** collection.</span></span>

<span data-ttu-id="86104-141">使用 dbname 时，一些事项：</span><span class="sxs-lookup"><span data-stu-id="86104-141">Some considerations apply when you use dbname:</span></span>

- <span data-ttu-id="86104-142">如果它引用了已打开以便由其他用户访问的数据库，则会发生错误。</span><span class="sxs-lookup"><span data-stu-id="86104-142">If it refers to a database that is already open for access by another user, an error occurs.</span></span>

- <span data-ttu-id="86104-143">如果它没有引用现有数据库或有效的 ODBC 数据源名称，则会发生错误。</span><span class="sxs-lookup"><span data-stu-id="86104-143">If it doesn't refer to an existing database or valid ODBC data source name, an error occurs.</span></span>

- <span data-ttu-id="86104-144">如果它是零长度字符串 ("") 并且*连接*是"ODBC;"，以便用户可以选择数据库，则显示一个对话框，列出所有已注册的 ODBC 数据源名称。</span><span class="sxs-lookup"><span data-stu-id="86104-144">If it's a zero-length string ("") and *connect* is "ODBC;" , a dialog box listing all registered ODBC data source names is displayed so the user can select a database.</span></span>

<span data-ttu-id="86104-145">若要关闭数据库，以便从 **Databases** 集合中删除 **Database** 对象，请对该对象使用 **[Close](connection-close-method-dao.md)** 方法。</span><span class="sxs-lookup"><span data-stu-id="86104-145">To close a database, and thus remove the **Database** object from the **Databases** collection, use the **[Close](connection-close-method-dao.md)** method on the object.</span></span>

> [!NOTE]
> <span data-ttu-id="86104-146">[!注释] 在访问 Microsoft Access 数据库引擎连接的 ODBC 数据源时，可通过打开连接到 ODBC 数据源的 **Database** 对象改善应用程序的性能，这样不需要将单个 **[TableDef](tabledef-object-dao.md)** 对象链接到 ODBC 数据源中的特定表。</span><span class="sxs-lookup"><span data-stu-id="86104-146">When you access a Microsoft access database engine-connected ODBC data source, you can improve your application's performance by opening a **Database** object connected to the ODBC data source, rather than by linking individual **[TableDef](tabledef-object-dao.md)** objects to specific tables in the ODBC data source.</span></span>

## <a name="example"></a><span data-ttu-id="86104-147">示例</span><span class="sxs-lookup"><span data-stu-id="86104-147">Example</span></span>

<span data-ttu-id="86104-148">以下示例使用 **OpenDatabase** 方法打开一个 Microsoft Access 数据库和两个连接到 Microsoft Access 数据库引擎的 ODBC 数据库。</span><span class="sxs-lookup"><span data-stu-id="86104-148">This example uses the **OpenDatabase** method to open one Microsoft Access database and two Microsoft Access database engine-connected ODBC databases.</span></span>

```vb 
Sub OpenDatabaseX() 
 
 Dim wrkAcc As Workspace 
 Dim dbsNorthwind As Database 
 Dim dbsPubs As Database 
 Dim dbsPubs2 As Database 
 Dim dbsLoop As Database 
 Dim prpLoop As Property 
 
 ' Create Microsoft Access Workspace object. 
 Set wrkAcc = CreateWorkspace("", "admin", "", dbUseJet) 
 
 ' Open Database object from saved Microsoft Access database 
 ' for exclusive use. 
 MsgBox "Opening Northwind..." 
 Set dbsNorthwind = wrkAcc.OpenDatabase("Northwind.mdb", _ 
 True) 
 
 ' Open read-only Database object based on information in 
 ' the connect string. 
 MsgBox "Opening pubs..." 
 
 ' Note: The DSN referenced below must be set to 
 ' use Microsoft Windows NT Authentication Mode to 
 ' authorize user access to the Microsoft SQL Server. 
 Set dbsPubs = wrkAcc.OpenDatabase("Publishers", _ 
 dbDriverNoPrompt, True, _ 
 "ODBC;DATABASE=pubs;DSN=Publishers") 
 
 ' Open read-only Database object by entering only the 
 ' missing information in the ODBC Driver Manager dialog 
 ' box. 
 MsgBox "Opening second copy of pubs..." 
 Set dbsPubs2 = wrkAcc.OpenDatabase("Publishers", _ 
 dbDriverCompleteRequired, True, _ 
 "ODBC;DATABASE=pubs;DSN=Publishers;") 
 
 ' Enumerate the Databases collection. 
 For Each dbsLoop In wrkAcc.Databases 
 Debug.Print "Database properties for " & _ 
 dbsLoop.Name & ":" 
 
 On Error Resume Next 
 ' Enumerate the Properties collection of each Database 
 ' object. 
 For Each prpLoop In dbsLoop.Properties 
 If prpLoop.Name = "Connection" Then 
 ' Property actually returns a Connection object. 
 Debug.Print " Connection[.Name] = " & _ 
 dbsLoop.Connection.Name 
 Else 
 Debug.Print " " & prpLoop.Name & " = " & _ 
 prpLoop 
 End If 
 Next prpLoop 
 On Error GoTo 0 
 
 Next dbsLoop 
 
 dbsNorthwind.Close 
 dbsPubs.Close 
 dbsPubs2.Close 
 wrkAcc.Close 
 
End Sub 
 
```

