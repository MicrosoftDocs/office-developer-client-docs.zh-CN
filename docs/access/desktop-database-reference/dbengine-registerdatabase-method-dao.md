---
title: DBEngine.RegisterDatabase 方法 (DAO)
TOCTitle: RegisterDatabase Method
ms:assetid: ed87a694-2c89-0a78-5d8b-0cc7e09fadff
ms:mtpsurl: https://msdn.microsoft.com/library/Ff836347(v=office.15)
ms:contentKeyID: 48548541
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1052938
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: 632f6e10d79d74dfef295b34a52ce62f1690101b
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28715604"
---
# <a name="dbengineregisterdatabase-method-dao"></a><span data-ttu-id="541d9-102">DBEngine.RegisterDatabase 方法 (DAO)</span><span class="sxs-lookup"><span data-stu-id="541d9-102">DBEngine.RegisterDatabase method (DAO)</span></span>

<span data-ttu-id="541d9-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="541d9-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="541d9-p101">在 Windows 注册表中输入 ODBC 数据源的连接信息。在会话期间如果 ODBC 数据源已打开，则 ODBC 驱动程序需要连接信息。</span><span class="sxs-lookup"><span data-stu-id="541d9-p101">Enters connection information for an ODBC data source in the Windows Registry. The ODBC driver needs connection information when the ODBC data source is opened during a session.</span></span>

## <a name="syntax"></a><span data-ttu-id="541d9-106">语法</span><span class="sxs-lookup"><span data-stu-id="541d9-106">Syntax</span></span>

<span data-ttu-id="541d9-107">*表达式*。RegisterDatabase （***Dsn***、***驱动程序***、***无提示***、***属性***）</span><span class="sxs-lookup"><span data-stu-id="541d9-107">*expression* .RegisterDatabase(***Dsn***, ***Driver***, ***Silent***, ***Attributes***)</span></span>

<span data-ttu-id="541d9-108">*表达式*一个代表**DBEngine**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="541d9-108">*expression* A variable that represents a **DBEngine** object.</span></span>

## <a name="parameters"></a><span data-ttu-id="541d9-109">Parameters</span><span class="sxs-lookup"><span data-stu-id="541d9-109">Parameters</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="541d9-110">Name</span><span class="sxs-lookup"><span data-stu-id="541d9-110">Name</span></span></p></th>
<th><p><span data-ttu-id="541d9-111">必需/可选</span><span class="sxs-lookup"><span data-stu-id="541d9-111">Required/optional</span></span></p></th>
<th><p><span data-ttu-id="541d9-112">数据类型</span><span class="sxs-lookup"><span data-stu-id="541d9-112">Data type</span></span></p></th>
<th><p><span data-ttu-id="541d9-113">说明</span><span class="sxs-lookup"><span data-stu-id="541d9-113">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="541d9-114"><em>Dsn</em></span><span class="sxs-lookup"><span data-stu-id="541d9-114"><em>Dsn</em></span></span></p></td>
<td><p><span data-ttu-id="541d9-115">必需</span><span class="sxs-lookup"><span data-stu-id="541d9-115">Required</span></span></p></td>
<td><p><span data-ttu-id="541d9-116"><strong>String</strong></span><span class="sxs-lookup"><span data-stu-id="541d9-116"><strong>String</strong></span></span></p></td>
<td><p><span data-ttu-id="541d9-p102"><strong><a href="dbengine-opendatabase-method-dao.md">OpenDatabase</a></strong> 方法中使用的名称。该名称引用与数据源有关的描述性信息块。例如，如果数据源为 ODBC 远程数据库，则该名称可能是服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="541d9-p102">the name used in the <strong><a href="dbengine-opendatabase-method-dao.md">OpenDatabase</a></strong> method. It refers to a block of descriptive information about the data source. For example, if the data source is an ODBC remote database, it could be the name of the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="541d9-120"><em>Driver</em></span><span class="sxs-lookup"><span data-stu-id="541d9-120"><em>Driver</em></span></span></p></td>
<td><p><span data-ttu-id="541d9-121">必需</span><span class="sxs-lookup"><span data-stu-id="541d9-121">Required</span></span></p></td>
<td><p><span data-ttu-id="541d9-122"><strong>String</strong></span><span class="sxs-lookup"><span data-stu-id="541d9-122"><strong>String</strong></span></span></p></td>
<td><p><span data-ttu-id="541d9-p103">ODBC 驱动程序的名称。这不是 ODBC 驱动程序 DLL 文件的名称。</span><span class="sxs-lookup"><span data-stu-id="541d9-p103">The name of the ODBC driver. This isn't the name of the ODBC driver DLL file.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="541d9-125"><em>无提示</em></span><span class="sxs-lookup"><span data-stu-id="541d9-125"><em>Silent</em></span></span></p></td>
<td><p><span data-ttu-id="541d9-126">必需</span><span class="sxs-lookup"><span data-stu-id="541d9-126">Required</span></span></p></td>
<td><p><span data-ttu-id="541d9-127"><strong>Boolean</strong></span><span class="sxs-lookup"><span data-stu-id="541d9-127"><strong>Boolean</strong></span></span></p></td>
<td><p><span data-ttu-id="541d9-128"><strong>True</strong>如果您不想要显示提示驱动程序特定信息; ODBC 驱动程序对话框或<strong>False</strong>如果您想要显示 ODBC 驱动程序对话框。</span><span class="sxs-lookup"><span data-stu-id="541d9-128"><strong>True</strong> if you don't want to display the ODBC driver dialog boxes that prompt for driver-specific information; or <strong>False</strong> if you want to display the ODBC driver dialog boxes.</span></span> <span data-ttu-id="541d9-129">如果无提示是<strong>True</strong>、 属性必须包含所有必需的驱动程序特定信息或仍然显示的对话框。</span><span class="sxs-lookup"><span data-stu-id="541d9-129">If silent is <strong>True</strong>, attributes must contain all the necessary driver-specific information or the dialog boxes are displayed anyway.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="541d9-130"><em>Attributes</em></span><span class="sxs-lookup"><span data-stu-id="541d9-130"><em>Attributes</em></span></span></p></td>
<td><p><span data-ttu-id="541d9-131">必需</span><span class="sxs-lookup"><span data-stu-id="541d9-131">Required</span></span></p></td>
<td><p><span data-ttu-id="541d9-132"><strong>String</strong></span><span class="sxs-lookup"><span data-stu-id="541d9-132"><strong>String</strong></span></span></p></td>
<td><p><span data-ttu-id="541d9-p105">要添加到 Windows 注册表的关键字列表。这些关键字是由回车符分隔的字符串。</span><span class="sxs-lookup"><span data-stu-id="541d9-p105">A list of keywords to be added to the Windows Registry. The keywords are in a carriage-return–delimited string.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="541d9-135">注解</span><span class="sxs-lookup"><span data-stu-id="541d9-135">Remarks</span></span>

<span data-ttu-id="541d9-136">如果在使用 **RegisterDatabase** 方法时，已经在 Windows 注册表中注册了数据库（已输入了连接信息），则会更新连接信息。</span><span class="sxs-lookup"><span data-stu-id="541d9-136">If the database is already registered (connection information is already entered) in the Windows Registry when you use the **RegisterDatabase** method, the connection information is updated.</span></span>

<span data-ttu-id="541d9-137">如果出于任何原因 **RegisterDatabase** 方法失败，则不会对 Windows 注册表进行更改，同时会发生错误。</span><span class="sxs-lookup"><span data-stu-id="541d9-137">If the **RegisterDatabase** method fails for any reason, no changes are made to the Windows Registry, and an error occurs.</span></span>

<span data-ttu-id="541d9-138">有关 ODBC 驱动程序（例如 SQL Server）的详细信息，请参阅随驱动程序提供的"帮助"文件。</span><span class="sxs-lookup"><span data-stu-id="541d9-138">For more information about ODBC drivers such as SQL Server, see the Help file provided with the driver.</span></span>

## <a name="example"></a><span data-ttu-id="541d9-139">示例</span><span class="sxs-lookup"><span data-stu-id="541d9-139">Example</span></span>

<span data-ttu-id="541d9-140">以下示例使用 **RegisterDatabase** 方法在 Windows 注册表中注册名称为"Publishers"的 Microsoft SQL Server 数据源。</span><span class="sxs-lookup"><span data-stu-id="541d9-140">This example uses the **RegisterDatabase** method to register a Microsoft SQL Server data source named Publishers in the Windows Registry.</span></span>

```vb 
Sub RegisterDatabaseX() 
 
 Dim dbsRegister As Database 
 Dim strDescription As String 
 Dim strAttributes As String 
 Dim errLoop As Error 
 
 ' Build keywords string. 
 strDescription = InputBox( "Enter a description " & _ 
 "for the database to be registered.") 
 strAttributes = "Database=pubs" & _ 
 vbCr & "Description=" & strDescription & _ 
 vbCr & "OemToAnsi=No" & _ 
 vbCr & "Server=Server1" 
 
 ' Update Windows Registry. 
 On Error GoTo Err_Register 
 DBEngine.RegisterDatabase "Publishers", "SQL Server", _ 
 True, strAttributes 
 On Error GoTo 0 
 
 MsgBox "Use regedit.exe to view changes: " & _ 
 "HKEY_CURRENT_USER\" & _ 
 "Software\ODBC\ODBC.INI" 
 
 Exit Sub 
 
Err_Register: 
 
 ' Notify user of any errors that result from 
 ' the invalid data. 
 If DBEngine.Errors.Count > 0 Then 
 For Each errLoop In DBEngine.Errors 
 MsgBox "Error number: " & errLoop.Number & _ 
 vbCr & errLoop.Description 
 Next errLoop 
 End If 
 
 Resume Next 
 
End Sub 
 
```

