---
title: Database.Connect 属性 (DAO)
TOCTitle: Connect Property
ms:assetid: c3e511a6-baef-3758-cfb1-3459b0b19cf3
ms:mtpsurl: https://msdn.microsoft.com/library/Ff823048(v=office.15)
ms:contentKeyID: 48547578
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 3a6af1ee460cc06d37fe031fe5488badd8b56ad6
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25925756"
---
# <a name="databaseconnect-property-dao"></a><span data-ttu-id="ae114-102">Database.Connect 属性 (DAO)</span><span class="sxs-lookup"><span data-stu-id="ae114-102">Database.Connect property (DAO)</span></span>


<span data-ttu-id="ae114-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="ae114-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="ae114-p101">设置或返回一个值，该值提供与已打开数据库的源有关的信息。可读/写 **String** 类型。</span><span class="sxs-lookup"><span data-stu-id="ae114-p101">Sets or returns a value that provides information about the source an open database. Read/write **String**.</span></span>

## <a name="syntax"></a><span data-ttu-id="ae114-106">语法</span><span class="sxs-lookup"><span data-stu-id="ae114-106">Syntax</span></span>

<span data-ttu-id="ae114-107">*表达式*。连接</span><span class="sxs-lookup"><span data-stu-id="ae114-107">*expression* .Connect</span></span>

<span data-ttu-id="ae114-108">*表达式*一个代表**Database**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="ae114-108">*expression* A variable that represents a **Database** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="ae114-109">注解</span><span class="sxs-lookup"><span data-stu-id="ae114-109">Remarks</span></span>

<span data-ttu-id="ae114-p102">**Connect** 属性设置是一个 **String**，由一个数据库类型说明符以及由分号分隔的零个或更多个参数组成。 **Connect** 属性根据需要将其他信息传递给 ODBC 和某些 ISAM 驱动程序。</span><span class="sxs-lookup"><span data-stu-id="ae114-p102">The **Connect** property setting is a **String** composed of a database type specifier and zero or more parameters separated by semicolons. The **Connect** property passes additional information to ODBC and certain ISAM drivers as needed.</span></span>

<span data-ttu-id="ae114-112">若要对链接到 Microsoft Access 数据库文件的表执行 SQL 传递查询，必须首先将链接表的数据库的 **Connect** 属性设置为有效的 ODBC 连接字符串。</span><span class="sxs-lookup"><span data-stu-id="ae114-112">To perform an SQL pass-through query on a table linked to your Microsoft Access database file, you must first set the **Connect** property of the linked table's database to a valid ODBC connection string.</span></span>

<span data-ttu-id="ae114-p103">下表中所示的路径是包含数据库文件的目录的完整路径，它的前面必须是标识符 DATABASE=。在某些情况下（如使用 Microsoft Excel 和 Microsoft Access 数据库引擎数据库时），应该在数据库路径参数中包括特定的文件名。</span><span class="sxs-lookup"><span data-stu-id="ae114-p103">The path as shown in the following table is the full path for the directory containing the database files and must be preceded by the identifier DATABASE=. In some cases (as with Microsoft Excel and Microsoft Access database engine databases), you should include a specific file name in the database path argument.</span></span>

<span data-ttu-id="ae114-115">下表显示适用于 **Connect** 属性设置的可能的数据库类型及其相应的数据库说明符和路径。</span><span class="sxs-lookup"><span data-stu-id="ae114-115">The following table shows possible database types and their corresponding database specifiers and paths for the **Connect** property setting.</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="ae114-116">数据库类型</span><span class="sxs-lookup"><span data-stu-id="ae114-116">Database type</span></span></p></th>
<th><p><span data-ttu-id="ae114-117">说明符</span><span class="sxs-lookup"><span data-stu-id="ae114-117">Specifier</span></span></p></th>
<th><p><span data-ttu-id="ae114-118">示例</span><span class="sxs-lookup"><span data-stu-id="ae114-118">Example</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ae114-119">Microsoft Access 数据库</span><span class="sxs-lookup"><span data-stu-id="ae114-119">Microsoft Access Database</span></span></p></td>
<td><p><span data-ttu-id="ae114-120">[数据库;]</span><span class="sxs-lookup"><span data-stu-id="ae114-120">[database];</span></span></p></td>
<td><p><span data-ttu-id="ae114-121">drive:\path\filename</span><span class="sxs-lookup"><span data-stu-id="ae114-121">drive:\path\filename</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ae114-122">dBASE III</span><span class="sxs-lookup"><span data-stu-id="ae114-122">dBASE III</span></span></p></td>
<td><p><span data-ttu-id="ae114-123">dBASE III;</span><span class="sxs-lookup"><span data-stu-id="ae114-123">dBASE III;</span></span></p></td>
<td><p><span data-ttu-id="ae114-124">驱动器： \path</span><span class="sxs-lookup"><span data-stu-id="ae114-124">drive:\path</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ae114-125">dBASE IV</span><span class="sxs-lookup"><span data-stu-id="ae114-125">dBASE IV</span></span></p></td>
<td><p><span data-ttu-id="ae114-126">dBASE IV;</span><span class="sxs-lookup"><span data-stu-id="ae114-126">dBASE IV;</span></span></p></td>
<td><p><span data-ttu-id="ae114-127">驱动器： \path</span><span class="sxs-lookup"><span data-stu-id="ae114-127">drive:\path</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ae114-128">dBASE 5</span><span class="sxs-lookup"><span data-stu-id="ae114-128">dBASE 5</span></span></p></td>
<td><p><span data-ttu-id="ae114-129">dBASE 5.0;</span><span class="sxs-lookup"><span data-stu-id="ae114-129">dBASE 5.0;</span></span></p></td>
<td><p><span data-ttu-id="ae114-130">驱动器： \path</span><span class="sxs-lookup"><span data-stu-id="ae114-130">drive:\path</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ae114-131">Paradox 3.x</span><span class="sxs-lookup"><span data-stu-id="ae114-131">Paradox 3.x</span></span></p></td>
<td><p><span data-ttu-id="ae114-132">Paradox 3.x;</span><span class="sxs-lookup"><span data-stu-id="ae114-132">Paradox 3.x;</span></span></p></td>
<td><p><span data-ttu-id="ae114-133">驱动器： \path</span><span class="sxs-lookup"><span data-stu-id="ae114-133">drive:\path</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ae114-134">Paradox 4.x</span><span class="sxs-lookup"><span data-stu-id="ae114-134">Paradox 4.x</span></span></p></td>
<td><p><span data-ttu-id="ae114-135">Paradox 4.x;</span><span class="sxs-lookup"><span data-stu-id="ae114-135">Paradox 4.x;</span></span></p></td>
<td><p><span data-ttu-id="ae114-136">驱动器： \path</span><span class="sxs-lookup"><span data-stu-id="ae114-136">drive:\path</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ae114-137">Paradox 5.x</span><span class="sxs-lookup"><span data-stu-id="ae114-137">Paradox 5.x</span></span></p></td>
<td><p><span data-ttu-id="ae114-138">Paradox 5.x;</span><span class="sxs-lookup"><span data-stu-id="ae114-138">Paradox 5.x;</span></span></p></td>
<td><p><span data-ttu-id="ae114-139">驱动器： \path</span><span class="sxs-lookup"><span data-stu-id="ae114-139">drive:\path</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ae114-140">Microsoft Excel 3.0</span><span class="sxs-lookup"><span data-stu-id="ae114-140">Microsoft Excel 3.0</span></span></p></td>
<td><p><span data-ttu-id="ae114-141">Excel 3.0;</span><span class="sxs-lookup"><span data-stu-id="ae114-141">Excel 3.0;</span></span></p></td>
<td><p><span data-ttu-id="ae114-142">drive:\path\filename.xls</span><span class="sxs-lookup"><span data-stu-id="ae114-142">drive:\path\filename.xls</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ae114-143">Microsoft Excel 4.0</span><span class="sxs-lookup"><span data-stu-id="ae114-143">Microsoft Excel 4.0</span></span></p></td>
<td><p><span data-ttu-id="ae114-144">Excel 4.0;</span><span class="sxs-lookup"><span data-stu-id="ae114-144">Excel 4.0;</span></span></p></td>
<td><p><span data-ttu-id="ae114-145">drive:\path\filename.xls</span><span class="sxs-lookup"><span data-stu-id="ae114-145">drive:\path\filename.xls</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ae114-146">Microsoft Excel 5.0 或 Microsoft Excel 95</span><span class="sxs-lookup"><span data-stu-id="ae114-146">Microsoft Excel 5.0 or Microsoft Excel 95</span></span></p></td>
<td><p><span data-ttu-id="ae114-147">Excel 5.0;</span><span class="sxs-lookup"><span data-stu-id="ae114-147">Excel 5.0;</span></span></p></td>
<td><p><span data-ttu-id="ae114-148">drive:\path\filename.xls</span><span class="sxs-lookup"><span data-stu-id="ae114-148">drive:\path\filename.xls</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ae114-149">Microsoft Excel 97</span><span class="sxs-lookup"><span data-stu-id="ae114-149">Microsoft Excel 97</span></span></p></td>
<td><p><span data-ttu-id="ae114-150">Excel 8.0;</span><span class="sxs-lookup"><span data-stu-id="ae114-150">Excel 8.0;</span></span></p></td>
<td><p><span data-ttu-id="ae114-151">drive:\path\filename.xls</span><span class="sxs-lookup"><span data-stu-id="ae114-151">drive:\path\filename.xls</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ae114-152">Lotus 1-2-3 WKS 和 WK1</span><span class="sxs-lookup"><span data-stu-id="ae114-152">Lotus 1-2-3 WKS and WK1</span></span></p></td>
<td><p><span data-ttu-id="ae114-153">Lotus WK1;</span><span class="sxs-lookup"><span data-stu-id="ae114-153">Lotus WK1;</span></span></p></td>
<td><p><span data-ttu-id="ae114-154">drive:\path\filename.wk1</span><span class="sxs-lookup"><span data-stu-id="ae114-154">drive:\path\filename.wk1</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ae114-155">Lotus 1-2-3 WK3</span><span class="sxs-lookup"><span data-stu-id="ae114-155">Lotus 1-2-3 WK3</span></span></p></td>
<td><p><span data-ttu-id="ae114-156">Lotus WK3;</span><span class="sxs-lookup"><span data-stu-id="ae114-156">Lotus WK3;</span></span></p></td>
<td><p><span data-ttu-id="ae114-157">drive:\path\filename.wk3</span><span class="sxs-lookup"><span data-stu-id="ae114-157">drive:\path\filename.wk3</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ae114-158">Lotus 1-2-3 WK4</span><span class="sxs-lookup"><span data-stu-id="ae114-158">Lotus 1-2-3 WK4</span></span></p></td>
<td><p><span data-ttu-id="ae114-159">Lotus WK4;</span><span class="sxs-lookup"><span data-stu-id="ae114-159">Lotus WK4;</span></span></p></td>
<td><p><span data-ttu-id="ae114-160">drive:\path\filename.wk4</span><span class="sxs-lookup"><span data-stu-id="ae114-160">drive:\path\filename.wk4</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ae114-161">HTML Import</span><span class="sxs-lookup"><span data-stu-id="ae114-161">HTML Import</span></span></p></td>
<td><p><span data-ttu-id="ae114-162">HTML Import;</span><span class="sxs-lookup"><span data-stu-id="ae114-162">HTML Import;</span></span></p></td>
<td><p><span data-ttu-id="ae114-163">drive:\path\filename</span><span class="sxs-lookup"><span data-stu-id="ae114-163">drive:\path\filename</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ae114-164">HTML Export</span><span class="sxs-lookup"><span data-stu-id="ae114-164">HTML Export</span></span></p></td>
<td><p><span data-ttu-id="ae114-165">HTML Export;</span><span class="sxs-lookup"><span data-stu-id="ae114-165">HTML Export;</span></span></p></td>
<td><p><span data-ttu-id="ae114-166">驱动器： \path</span><span class="sxs-lookup"><span data-stu-id="ae114-166">drive:\path</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ae114-167">文本</span><span class="sxs-lookup"><span data-stu-id="ae114-167">Text</span></span></p></td>
<td><p><span data-ttu-id="ae114-168">Text;</span><span class="sxs-lookup"><span data-stu-id="ae114-168">Text;</span></span></p></td>
<td><p><span data-ttu-id="ae114-169">驱动器： \path</span><span class="sxs-lookup"><span data-stu-id="ae114-169">drive:\path</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ae114-170">ODBC</span><span class="sxs-lookup"><span data-stu-id="ae114-170">ODBC</span></span></p></td>
<td><p><span data-ttu-id="ae114-171">ODBC;数据库 = 数据库;UID = 用户;PWD = 密码;DSN = 名称;[LOGINTIMEOUT = 秒;]</span><span class="sxs-lookup"><span data-stu-id="ae114-171">ODBC; DATABASE=database; UID=user; PWD=password; DSN= datasourcename; [LOGINTIMEOUT=seconds;]</span></span></p></td>
<td><p><span data-ttu-id="ae114-172">无</span><span class="sxs-lookup"><span data-stu-id="ae114-172">None</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ae114-173">Microsoft Exchange</span><span class="sxs-lookup"><span data-stu-id="ae114-173">Microsoft Exchange</span></span></p></td>
<td><p><span data-ttu-id="ae114-174">Exchange 4.0;MAPILEVEL = folderpath;[TABLETYPE = {0 | 1}];[PROFILE = 配置文件;][PWD = 密码;][数据库 = 数据库;]</span><span class="sxs-lookup"><span data-stu-id="ae114-174">Exchange 4.0; MAPILEVEL=folderpath; [TABLETYPE={ 0 | 1 }];[PROFILE=profile;] [PWD=password;] [DATABASE=database;]</span></span></p></td>
<td><p><span data-ttu-id="ae114-175">drive:\path\filename</span><span class="sxs-lookup"><span data-stu-id="ae114-175">drive:\path\filename</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="ae114-176">如果说明符只是 "ODBC;"，则 ODBC 驱动程序显示一个对话框，列出所有注册的 ODBC 数据源名称，以便用户可以选择一个数据库。</span><span class="sxs-lookup"><span data-stu-id="ae114-176">If the specifier is only "ODBC;", the ODBC driver displays a dialog box listing all registered ODBC data source names so that the user can select a database.</span></span>

<span data-ttu-id="ae114-177">如果需要密码，但是 **Connect** 属性设置中未提供此密码，那么 ODBC 驱动程序首次访问表时，将显示一个登录对话框，并且在关闭并重新打开连接时，会再次显示该对话框。</span><span class="sxs-lookup"><span data-stu-id="ae114-177">If a password is required but not provided in the **Connect** property setting, a login dialog box is displayed the first time a table is accessed by the ODBC driver and again if the connection is closed and reopened.</span></span>

<span data-ttu-id="ae114-178">对于 Microsoft Exchange 中的数据，应该将必需的 MAPILEVEL 项设置为完全解析的文件夹路径（例如，"Mailbox - Pat SmithIAlpha/Today"）。</span><span class="sxs-lookup"><span data-stu-id="ae114-178">For data in Microsoft Exchange, the required MAPILEVEL key should be set to a fully-resolved folder path (for example, "Mailbox - Pat SmithIAlpha/Today").</span></span> <span data-ttu-id="ae114-179">路径不包含将作为表; 打开文件夹的名称而是应用作**CreateTable**方法的名称参数指定该文件夹的名称。</span><span class="sxs-lookup"><span data-stu-id="ae114-179">The path does not include the name of the folder that will be opened as a table; that folder’s name should instead be specified as the name argument to the **CreateTable** method.</span></span> <span data-ttu-id="ae114-180">TABLETYPE 项应设置为"0"以打开文件夹（默认设置），或设置为"1"以打开通讯簿。</span><span class="sxs-lookup"><span data-stu-id="ae114-180">The TABLETYPE key should be set to "0" to open a folder (default) or "1" to open an address book.</span></span> <span data-ttu-id="ae114-181">PROFILE 项默认为当前使用的配置文件。</span><span class="sxs-lookup"><span data-stu-id="ae114-181">The PROFILE key defaults to the profile currently in use.</span></span>

<span data-ttu-id="ae114-182">您可以通过提供给**OpenDatabase**方法在 source 参数设置**数据库**对象的**Connect**属性。</span><span class="sxs-lookup"><span data-stu-id="ae114-182">You can set the **Connect** property for a **Database** object by providing a source argument to the **OpenDatabase** method.</span></span> <span data-ttu-id="ae114-183">可以检查设置以确定数据库的类型、路径、用户 ID、密码或 ODBC 数据源。</span><span class="sxs-lookup"><span data-stu-id="ae114-183">You can check the setting to determine the type, path, user ID, password, or ODBC data source of the database.</span></span>


> [!NOTE]
> - <span data-ttu-id="ae114-184">必须先设置 **Connect** 属性，然后才能设置 **ReturnsRecords** 属性。</span><span class="sxs-lookup"><span data-stu-id="ae114-184">You must set the **Connect** property before you set the **ReturnsRecords** property.</span></span>
> - <span data-ttu-id="ae114-185">您必须有权访问包含您尝试访问的数据库服务器的计算机。</span><span class="sxs-lookup"><span data-stu-id="ae114-185">You must have access permissions to the computer that contains the database server you're trying to access.</span></span>


