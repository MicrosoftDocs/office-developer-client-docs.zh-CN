---
title: Connection 属性 (DAO)
TOCTitle: Connect Property
ms:assetid: 58b514a2-91cd-7918-cba5-15d71c2457a6
ms:mtpsurl: https://msdn.microsoft.com/library/Ff194335(v=office.15)
ms:contentKeyID: 48545001
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: e44ce5b4acf58f3f9d9e887d0136baed64c8e227
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32295924"
---
# <a name="connectionconnect-property-dao"></a><span data-ttu-id="6ad7a-102">Connection 属性 (DAO)</span><span class="sxs-lookup"><span data-stu-id="6ad7a-102">Connection.Connect property (DAO)</span></span>


<span data-ttu-id="6ad7a-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="6ad7a-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="6ad7a-104">设置或返回一个值，该值提供与已打开连接的源有关的信息。</span><span class="sxs-lookup"><span data-stu-id="6ad7a-104">Sets or returns a value that provides information about the source of an open connection.</span></span> <span data-ttu-id="6ad7a-105">可读/写 **String** 类型。</span><span class="sxs-lookup"><span data-stu-id="6ad7a-105">Read/write **String**.</span></span>

## <a name="syntax"></a><span data-ttu-id="6ad7a-106">语法</span><span class="sxs-lookup"><span data-stu-id="6ad7a-106">Syntax</span></span>

<span data-ttu-id="6ad7a-107">*表达式*。连接</span><span class="sxs-lookup"><span data-stu-id="6ad7a-107">*expression* .Connect</span></span>

<span data-ttu-id="6ad7a-108">*表达式*一个代表**Connection**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="6ad7a-108">*expression* A variable that represents a **Connection** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="6ad7a-109">注解</span><span class="sxs-lookup"><span data-stu-id="6ad7a-109">Remarks</span></span>

<span data-ttu-id="6ad7a-p102">**Connect** 属性设置是一个 **String**，由一个数据库类型说明符以及由分号分隔的零个或更多个参数组成。 **Connect** 属性根据需要将其他信息传递给 ODBC 和某些 ISAM 驱动程序。</span><span class="sxs-lookup"><span data-stu-id="6ad7a-p102">The **Connect** property setting is a **String** composed of a database type specifier and zero or more parameters separated by semicolons. The **Connect** property passes additional information to ODBC and certain ISAM drivers as needed.</span></span>

<span data-ttu-id="6ad7a-112">若要对链接到 Microsoft Access 数据库文件的表执行 SQL 传递查询，必须首先将链接表的数据库的 **Connect** 属性设置为有效的 ODBC 连接字符串。</span><span class="sxs-lookup"><span data-stu-id="6ad7a-112">To perform an SQL pass-through query on a table linked to your Microsoft Access database file, you must first set the **Connect** property of the linked table's database to a valid ODBC connection string.</span></span>

<span data-ttu-id="6ad7a-113">对于代表链接表的 **TableDef** 对象， **Connect** 属性设置由一个或两个部分（数据库类型说明符和指向该数据库的路径）组成，其中每个部分都以分号结尾。</span><span class="sxs-lookup"><span data-stu-id="6ad7a-113">For a **TableDef** object that represents a linked table, the **Connect** property setting consists of one or two parts (a database type specifier and a path to the database), each of which ends with a semicolon.</span></span>

<span data-ttu-id="6ad7a-114">下表中所示的路径是包含数据库文件的目录的完整路径，它的前面必须是标识符 DATABASE=。</span><span class="sxs-lookup"><span data-stu-id="6ad7a-114">The path as shown in the following table is the full path for the directory containing the database files and must be preceded by the identifier DATABASE=.</span></span> <span data-ttu-id="6ad7a-115">在某些情况下（如使用 Microsoft Excel 和 Microsoft Access 数据库引擎数据库时），应该在数据库路径参数中包括特定的文件名。</span><span class="sxs-lookup"><span data-stu-id="6ad7a-115">In some cases (as with Microsoft Excel and Microsoft Access database engine databases), you should include a specific file name in the database path argument.</span></span>

<span data-ttu-id="6ad7a-116">下表显示适用于 **Connect** 属性设置的可能的数据库类型及其相应的数据库说明符和路径。</span><span class="sxs-lookup"><span data-stu-id="6ad7a-116">The following table shows possible database types and their corresponding database specifiers and paths for the **Connect** property setting.</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="6ad7a-117">数据库类型</span><span class="sxs-lookup"><span data-stu-id="6ad7a-117">Database type</span></span></p></th>
<th><p><span data-ttu-id="6ad7a-118">分类</span><span class="sxs-lookup"><span data-stu-id="6ad7a-118">Specifier</span></span></p></th>
<th><p><span data-ttu-id="6ad7a-119">示例</span><span class="sxs-lookup"><span data-stu-id="6ad7a-119">Example</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6ad7a-120">Microsoft Access 数据库</span><span class="sxs-lookup"><span data-stu-id="6ad7a-120">Microsoft Access Database</span></span></p></td>
<td><p><span data-ttu-id="6ad7a-121">[数据库];</span><span class="sxs-lookup"><span data-stu-id="6ad7a-121">[database];</span></span></p></td>
<td><p><span data-ttu-id="6ad7a-122">驱动器: \ path\filename</span><span class="sxs-lookup"><span data-stu-id="6ad7a-122">drive:\path\filename</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6ad7a-123">dBASE III</span><span class="sxs-lookup"><span data-stu-id="6ad7a-123">dBASE III</span></span></p></td>
<td><p><span data-ttu-id="6ad7a-124">dBASE III;</span><span class="sxs-lookup"><span data-stu-id="6ad7a-124">dBASE III;</span></span></p></td>
<td><p><span data-ttu-id="6ad7a-125">驱动器: \ 路径</span><span class="sxs-lookup"><span data-stu-id="6ad7a-125">drive:\path</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6ad7a-126">dBASE IV</span><span class="sxs-lookup"><span data-stu-id="6ad7a-126">dBASE IV</span></span></p></td>
<td><p><span data-ttu-id="6ad7a-127">dBASE IV;</span><span class="sxs-lookup"><span data-stu-id="6ad7a-127">dBASE IV;</span></span></p></td>
<td><p><span data-ttu-id="6ad7a-128">驱动器: \ 路径</span><span class="sxs-lookup"><span data-stu-id="6ad7a-128">drive:\path</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6ad7a-129">dBASE 5</span><span class="sxs-lookup"><span data-stu-id="6ad7a-129">dBASE 5</span></span></p></td>
<td><p><span data-ttu-id="6ad7a-130">dBASE 5.0;</span><span class="sxs-lookup"><span data-stu-id="6ad7a-130">dBASE 5.0;</span></span></p></td>
<td><p><span data-ttu-id="6ad7a-131">驱动器: \ 路径</span><span class="sxs-lookup"><span data-stu-id="6ad7a-131">drive:\path</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6ad7a-132">Paradox 3.x</span><span class="sxs-lookup"><span data-stu-id="6ad7a-132">Paradox 3.x</span></span></p></td>
<td><p><span data-ttu-id="6ad7a-133">Paradox 3.x;</span><span class="sxs-lookup"><span data-stu-id="6ad7a-133">Paradox 3.x;</span></span></p></td>
<td><p><span data-ttu-id="6ad7a-134">驱动器: \ 路径</span><span class="sxs-lookup"><span data-stu-id="6ad7a-134">drive:\path</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6ad7a-135">Paradox 4.x</span><span class="sxs-lookup"><span data-stu-id="6ad7a-135">Paradox 4.x</span></span></p></td>
<td><p><span data-ttu-id="6ad7a-136">Paradox 4.x;</span><span class="sxs-lookup"><span data-stu-id="6ad7a-136">Paradox 4.x;</span></span></p></td>
<td><p><span data-ttu-id="6ad7a-137">驱动器: \ 路径</span><span class="sxs-lookup"><span data-stu-id="6ad7a-137">drive:\path</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6ad7a-138">Paradox 5.x</span><span class="sxs-lookup"><span data-stu-id="6ad7a-138">Paradox 5.x</span></span></p></td>
<td><p><span data-ttu-id="6ad7a-139">Paradox 5.x;</span><span class="sxs-lookup"><span data-stu-id="6ad7a-139">Paradox 5.x;</span></span></p></td>
<td><p><span data-ttu-id="6ad7a-140">驱动器: \ 路径</span><span class="sxs-lookup"><span data-stu-id="6ad7a-140">drive:\path</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6ad7a-141">Microsoft Excel 3.0</span><span class="sxs-lookup"><span data-stu-id="6ad7a-141">Microsoft Excel 3.0</span></span></p></td>
<td><p><span data-ttu-id="6ad7a-142">Excel 3.0;</span><span class="sxs-lookup"><span data-stu-id="6ad7a-142">Excel 3.0;</span></span></p></td>
<td><p><span data-ttu-id="6ad7a-143">驱动器: \ path\filename.xls</span><span class="sxs-lookup"><span data-stu-id="6ad7a-143">drive:\path\filename.xls</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6ad7a-144">Microsoft Excel 4.0</span><span class="sxs-lookup"><span data-stu-id="6ad7a-144">Microsoft Excel 4.0</span></span></p></td>
<td><p><span data-ttu-id="6ad7a-145">Excel 4.0;</span><span class="sxs-lookup"><span data-stu-id="6ad7a-145">Excel 4.0;</span></span></p></td>
<td><p><span data-ttu-id="6ad7a-146">驱动器: \ path\filename.xls</span><span class="sxs-lookup"><span data-stu-id="6ad7a-146">drive:\path\filename.xls</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6ad7a-147">Microsoft Excel 5.0 或 Microsoft Excel 95</span><span class="sxs-lookup"><span data-stu-id="6ad7a-147">Microsoft Excel 5.0 or Microsoft Excel 95</span></span></p></td>
<td><p><span data-ttu-id="6ad7a-148">Excel 5.0;</span><span class="sxs-lookup"><span data-stu-id="6ad7a-148">Excel 5.0;</span></span></p></td>
<td><p><span data-ttu-id="6ad7a-149">驱动器: \ path\filename.xls</span><span class="sxs-lookup"><span data-stu-id="6ad7a-149">drive:\path\filename.xls</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6ad7a-150">Microsoft Excel 97</span><span class="sxs-lookup"><span data-stu-id="6ad7a-150">Microsoft Excel 97</span></span></p></td>
<td><p><span data-ttu-id="6ad7a-151">Excel 8.0;</span><span class="sxs-lookup"><span data-stu-id="6ad7a-151">Excel 8.0;</span></span></p></td>
<td><p><span data-ttu-id="6ad7a-152">驱动器: \ path\filename.xls</span><span class="sxs-lookup"><span data-stu-id="6ad7a-152">drive:\path\filename.xls</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6ad7a-153">Lotus 1-2-3 WKS 和 WK1</span><span class="sxs-lookup"><span data-stu-id="6ad7a-153">Lotus 1-2-3 WKS and WK1</span></span></p></td>
<td><p><span data-ttu-id="6ad7a-154">Lotus WK1;</span><span class="sxs-lookup"><span data-stu-id="6ad7a-154">Lotus WK1;</span></span></p></td>
<td><p><span data-ttu-id="6ad7a-155">驱动器: \ path\filename.wk1</span><span class="sxs-lookup"><span data-stu-id="6ad7a-155">drive:\path\filename.wk1</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6ad7a-156">Lotus 1-2-3 WK3</span><span class="sxs-lookup"><span data-stu-id="6ad7a-156">Lotus 1-2-3 WK3</span></span></p></td>
<td><p><span data-ttu-id="6ad7a-157">Lotus WK3;</span><span class="sxs-lookup"><span data-stu-id="6ad7a-157">Lotus WK3;</span></span></p></td>
<td><p><span data-ttu-id="6ad7a-158">驱动器: \ path\filename.wk3</span><span class="sxs-lookup"><span data-stu-id="6ad7a-158">drive:\path\filename.wk3</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6ad7a-159">Lotus 1-2-3 WK4</span><span class="sxs-lookup"><span data-stu-id="6ad7a-159">Lotus 1-2-3 WK4</span></span></p></td>
<td><p><span data-ttu-id="6ad7a-160">Lotus WK4;</span><span class="sxs-lookup"><span data-stu-id="6ad7a-160">Lotus WK4;</span></span></p></td>
<td><p><span data-ttu-id="6ad7a-161">驱动器: \ path\filename.wk4</span><span class="sxs-lookup"><span data-stu-id="6ad7a-161">drive:\path\filename.wk4</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6ad7a-162">HTML Import</span><span class="sxs-lookup"><span data-stu-id="6ad7a-162">HTML Import</span></span></p></td>
<td><p><span data-ttu-id="6ad7a-163">HTML Import;</span><span class="sxs-lookup"><span data-stu-id="6ad7a-163">HTML Import;</span></span></p></td>
<td><p><span data-ttu-id="6ad7a-164">驱动器: \ path\filename</span><span class="sxs-lookup"><span data-stu-id="6ad7a-164">drive:\path\filename</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6ad7a-165">HTML Export</span><span class="sxs-lookup"><span data-stu-id="6ad7a-165">HTML Export</span></span></p></td>
<td><p><span data-ttu-id="6ad7a-166">HTML Export;</span><span class="sxs-lookup"><span data-stu-id="6ad7a-166">HTML Export;</span></span></p></td>
<td><p><span data-ttu-id="6ad7a-167">驱动器: \ 路径</span><span class="sxs-lookup"><span data-stu-id="6ad7a-167">drive:\path</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6ad7a-168">文本</span><span class="sxs-lookup"><span data-stu-id="6ad7a-168">Text</span></span></p></td>
<td><p><span data-ttu-id="6ad7a-169">文本框</span><span class="sxs-lookup"><span data-stu-id="6ad7a-169">Text;</span></span></p></td>
<td><p><span data-ttu-id="6ad7a-170">驱动器: \ 路径</span><span class="sxs-lookup"><span data-stu-id="6ad7a-170">drive:\path</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6ad7a-171">ODBC</span><span class="sxs-lookup"><span data-stu-id="6ad7a-171">ODBC</span></span></p></td>
<td><p><span data-ttu-id="6ad7a-172">ODBC数据库 = 数据库;UID = user;PWD = 密码;DSN = 值 1;[LOGINTIMEOUT = 秒;]</span><span class="sxs-lookup"><span data-stu-id="6ad7a-172">ODBC; DATABASE=database; UID=user; PWD=password; DSN= datasourcename; [LOGINTIMEOUT=seconds;]</span></span></p></td>
<td><p><span data-ttu-id="6ad7a-173">无</span><span class="sxs-lookup"><span data-stu-id="6ad7a-173">None</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6ad7a-174">Microsoft Exchange</span><span class="sxs-lookup"><span data-stu-id="6ad7a-174">Microsoft Exchange</span></span></p></td>
<td><p><span data-ttu-id="6ad7a-175">Exchange 4.0;MAPILEVEL = folderpath;[TABLETYPE = {0 | 1}];[profile = profile;][PWD = password;][数据库 = 数据库;]</span><span class="sxs-lookup"><span data-stu-id="6ad7a-175">Exchange 4.0; MAPILEVEL=folderpath; [TABLETYPE={ 0 | 1 }];[PROFILE=profile;] [PWD=password;] [DATABASE=database;]</span></span></p></td>
<td><p><span data-ttu-id="6ad7a-176">驱动器: \ path\filename</span><span class="sxs-lookup"><span data-stu-id="6ad7a-176">drive:\path\filename</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="6ad7a-177">如果说明符只是 "ODBC;"，则 ODBC 驱动程序显示一个对话框，列出所有注册的 ODBC 数据源名称，以便用户可以选择一个数据库。</span><span class="sxs-lookup"><span data-stu-id="6ad7a-177">If the specifier is only "ODBC;", the ODBC driver displays a dialog box listing all registered ODBC data source names so that the user can select a database.</span></span>

<span data-ttu-id="6ad7a-178">如果需要密码，但是 **Connect** 属性设置中未提供此密码，那么 ODBC 驱动程序首次访问表时，将显示一个登录对话框，并且在关闭并重新打开连接时，会再次显示该对话框。</span><span class="sxs-lookup"><span data-stu-id="6ad7a-178">If a password is required but not provided in the **Connect** property setting, a login dialog box is displayed the first time a table is accessed by the ODBC driver and again if the connection is closed and reopened.</span></span>

<span data-ttu-id="6ad7a-179">对于 Microsoft Exchange 中的数据，应该将必需的 MAPILEVEL 项设置为完全解析的文件夹路径（例如，"Mailbox - Pat SmithIAlpha/Today"）。</span><span class="sxs-lookup"><span data-stu-id="6ad7a-179">For data in Microsoft Exchange, the required MAPILEVEL key should be set to a fully-resolved folder path (for example, "Mailbox - Pat SmithIAlpha/Today").</span></span> <span data-ttu-id="6ad7a-180">路径不包括将作为表格打开的文件夹的名称;应改为将该文件夹的名称指定为**CreateTable**方法的 name 参数。</span><span class="sxs-lookup"><span data-stu-id="6ad7a-180">The path does not include the name of the folder that will be opened as a table; that folder’s name should instead be specified as the name argument to the **CreateTable** method.</span></span> <span data-ttu-id="6ad7a-181">TABLETYPE 项应设置为"0"以打开文件夹（默认设置），或设置为"1"以打开通讯簿。</span><span class="sxs-lookup"><span data-stu-id="6ad7a-181">The TABLETYPE key should be set to "0" to open a folder (default) or "1" to open an address book.</span></span> <span data-ttu-id="6ad7a-182">PROFILE 项默认为当前使用的配置文件。</span><span class="sxs-lookup"><span data-stu-id="6ad7a-182">The PROFILE key defaults to the profile currently in use.</span></span>

<span data-ttu-id="6ad7a-183">对于 Micorosoft Access 数据库中的基表， **Connect** 属性设置为零长度字符串 ("")。</span><span class="sxs-lookup"><span data-stu-id="6ad7a-183">For base tables in a Micorosoft Access database, the **Connect** property setting is a zero-length string ("").</span></span>

<span data-ttu-id="6ad7a-184">您可以通过为**OpenDatabase**方法提供 source 参数来设置**Database**对象的**Connect**属性。</span><span class="sxs-lookup"><span data-stu-id="6ad7a-184">You can set the **Connect** property for a **Database** object by providing a source argument to the **OpenDatabase** method.</span></span> <span data-ttu-id="6ad7a-185">可以检查设置以确定数据库的类型、路径、用户 ID、密码或 ODBC 数据源。</span><span class="sxs-lookup"><span data-stu-id="6ad7a-185">You can check the setting to determine the type, path, user ID, password, or ODBC data source of the database.</span></span>

<span data-ttu-id="6ad7a-186">对于 Microsoft Access 工作区中的 **QueryDef** 对象，可以将 **Connect** 属性与 ReturnsRecords 属性一起使用以创建一个 ODBC SQL 传递查询。</span><span class="sxs-lookup"><span data-stu-id="6ad7a-186">On a **QueryDef** object in a Microsoft Access workspace, you can use the **Connect** property with the ReturnsRecords property to create an ODBC SQL pass-through query.</span></span> <span data-ttu-id="6ad7a-187">连接字符串的 databasetype 为 "ODBC;"，字符串的其余部分包含用于访问远程数据的 ODBC 驱动程序的特定信息。</span><span class="sxs-lookup"><span data-stu-id="6ad7a-187">The databasetype of the connection string is "ODBC;", and the remainder of the string contains information specific to the ODBC driver used to access the remote data.</span></span> <span data-ttu-id="6ad7a-188">有关详细信息，请参阅特定驱动程序的文档。</span><span class="sxs-lookup"><span data-stu-id="6ad7a-188">For more information, see the documentation for the specific driver.</span></span>


> [!NOTE]
> - <span data-ttu-id="6ad7a-189">必须先设置 **Connect** 属性，然后才能设置 **ReturnsRecords** 属性。</span><span class="sxs-lookup"><span data-stu-id="6ad7a-189">You must set the **Connect** property before you set the **ReturnsRecords** property.</span></span>
> - <span data-ttu-id="6ad7a-190">您必须有权访问包含您尝试访问的数据库服务器的计算机。</span><span class="sxs-lookup"><span data-stu-id="6ad7a-190">You must have access permissions to the computer that contains the database server you're trying to access.</span></span>


