---
title: TableDef.Connect 属性 (DAO)
TOCTitle: Connect Property
ms:assetid: 4fbb324c-a358-8fad-60f2-fb8005cf74d9
ms:mtpsurl: https://msdn.microsoft.com/library/Ff193791(v=office.15)
ms:contentKeyID: 48544782
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1053064
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 322b59c6556b73186fe4034e64c75d9104d29560
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25926897"
---
# <a name="tabledefconnect-property-dao"></a><span data-ttu-id="636e9-102">TableDef.Connect 属性 (DAO)</span><span class="sxs-lookup"><span data-stu-id="636e9-102">TableDef.Connect property (DAO)</span></span>


<span data-ttu-id="636e9-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="636e9-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="636e9-p101">设置或返回一个值，该值提供有关链接表的信息。可读/写 **String** 类型。</span><span class="sxs-lookup"><span data-stu-id="636e9-p101">Sets or returns a value that provides information about a linked table. Read/write **String**.</span></span>

## <a name="syntax"></a><span data-ttu-id="636e9-106">语法</span><span class="sxs-lookup"><span data-stu-id="636e9-106">Syntax</span></span>

<span data-ttu-id="636e9-107">*表达式*。连接</span><span class="sxs-lookup"><span data-stu-id="636e9-107">*expression* .Connect</span></span>

<span data-ttu-id="636e9-108">*表达式*一个代表**TableDef**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="636e9-108">*expression* A variable that represents a **TableDef** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="636e9-109">注解</span><span class="sxs-lookup"><span data-stu-id="636e9-109">Remarks</span></span>

<span data-ttu-id="636e9-p102">**Connect** 属性设置是一个 **String**，由一个数据库类型说明符以及由分号分隔的零个或更多个参数组成。 **Connect** 属性根据需要将其他信息传递给 ODBC 和某些 ISAM 驱动程序。</span><span class="sxs-lookup"><span data-stu-id="636e9-p102">The **Connect** property setting is a **String** composed of a database type specifier and zero or more parameters separated by semicolons. The **Connect** property passes additional information to ODBC and certain ISAM drivers as needed.</span></span>

<span data-ttu-id="636e9-112">对于代表链接表的 **TableDef** 对象， **Connect** 属性设置由一个或两个部分（数据库类型说明符和指向该数据库的路径）组成，其中每个部分都以分号结尾。</span><span class="sxs-lookup"><span data-stu-id="636e9-112">For a **TableDef** object that represents a linked table, the **Connect** property setting consists of one or two parts (a database type specifier and a path to the database), each of which ends with a semicolon.</span></span>

<span data-ttu-id="636e9-p103">下表中所示的路径是包含数据库文件的目录的完整路径，它的前面必须是标识符 DATABASE=。在某些情况下（如使用 Microsoft Excel 和 Microsoft Access 数据库引擎数据库时），应该在数据库路径参数中包括特定的文件名。</span><span class="sxs-lookup"><span data-stu-id="636e9-p103">The path as shown in the following table is the full path for the directory containing the database files and must be preceded by the identifier DATABASE=. In some cases (as with Microsoft Excel and Microsoft Access database engine databases), you should include a specific file name in the database path argument.</span></span>

<span data-ttu-id="636e9-115">下表显示适用于 **Connect** 属性设置的可能的数据库类型及其相应的数据库说明符和路径。</span><span class="sxs-lookup"><span data-stu-id="636e9-115">The following table shows possible database types and their corresponding database specifiers and paths for the **Connect** property setting.</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="636e9-116">数据库类型</span><span class="sxs-lookup"><span data-stu-id="636e9-116">Database type</span></span></p></th>
<th><p><span data-ttu-id="636e9-117">说明符</span><span class="sxs-lookup"><span data-stu-id="636e9-117">Specifier</span></span></p></th>
<th><p><span data-ttu-id="636e9-118">示例</span><span class="sxs-lookup"><span data-stu-id="636e9-118">Example</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="636e9-119">Microsoft Access 数据库</span><span class="sxs-lookup"><span data-stu-id="636e9-119">Microsoft Access Database</span></span></p></td>
<td><p><span data-ttu-id="636e9-120">[数据库;]</span><span class="sxs-lookup"><span data-stu-id="636e9-120">[database];</span></span></p></td>
<td><p><span data-ttu-id="636e9-121">drive:\path\filename</span><span class="sxs-lookup"><span data-stu-id="636e9-121">drive:\path\filename</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="636e9-122">dBASE III</span><span class="sxs-lookup"><span data-stu-id="636e9-122">dBASE III</span></span></p></td>
<td><p><span data-ttu-id="636e9-123">dBASE III;</span><span class="sxs-lookup"><span data-stu-id="636e9-123">dBASE III;</span></span></p></td>
<td><p><span data-ttu-id="636e9-124">驱动器： \path</span><span class="sxs-lookup"><span data-stu-id="636e9-124">drive:\path</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="636e9-125">dBASE IV</span><span class="sxs-lookup"><span data-stu-id="636e9-125">dBASE IV</span></span></p></td>
<td><p><span data-ttu-id="636e9-126">dBASE IV;</span><span class="sxs-lookup"><span data-stu-id="636e9-126">dBASE IV;</span></span></p></td>
<td><p><span data-ttu-id="636e9-127">驱动器： \path</span><span class="sxs-lookup"><span data-stu-id="636e9-127">drive:\path</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="636e9-128">dBASE 5</span><span class="sxs-lookup"><span data-stu-id="636e9-128">dBASE 5</span></span></p></td>
<td><p><span data-ttu-id="636e9-129">dBASE 5.0;</span><span class="sxs-lookup"><span data-stu-id="636e9-129">dBASE 5.0;</span></span></p></td>
<td><p><span data-ttu-id="636e9-130">驱动器： \path</span><span class="sxs-lookup"><span data-stu-id="636e9-130">drive:\path</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="636e9-131">Paradox 3.x</span><span class="sxs-lookup"><span data-stu-id="636e9-131">Paradox 3.x</span></span></p></td>
<td><p><span data-ttu-id="636e9-132">Paradox 3.x;</span><span class="sxs-lookup"><span data-stu-id="636e9-132">Paradox 3.x;</span></span></p></td>
<td><p><span data-ttu-id="636e9-133">驱动器： \path</span><span class="sxs-lookup"><span data-stu-id="636e9-133">drive:\path</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="636e9-134">Paradox 4.x</span><span class="sxs-lookup"><span data-stu-id="636e9-134">Paradox 4.x</span></span></p></td>
<td><p><span data-ttu-id="636e9-135">Paradox 4.x;</span><span class="sxs-lookup"><span data-stu-id="636e9-135">Paradox 4.x;</span></span></p></td>
<td><p><span data-ttu-id="636e9-136">驱动器： \path</span><span class="sxs-lookup"><span data-stu-id="636e9-136">drive:\path</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="636e9-137">Paradox 5.x</span><span class="sxs-lookup"><span data-stu-id="636e9-137">Paradox 5.x</span></span></p></td>
<td><p><span data-ttu-id="636e9-138">Paradox 5.x;</span><span class="sxs-lookup"><span data-stu-id="636e9-138">Paradox 5.x;</span></span></p></td>
<td><p><span data-ttu-id="636e9-139">驱动器： \path</span><span class="sxs-lookup"><span data-stu-id="636e9-139">drive:\path</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="636e9-140">Microsoft Excel 3.0</span><span class="sxs-lookup"><span data-stu-id="636e9-140">Microsoft Excel 3.0</span></span></p></td>
<td><p><span data-ttu-id="636e9-141">Excel 3.0;</span><span class="sxs-lookup"><span data-stu-id="636e9-141">Excel 3.0;</span></span></p></td>
<td><p><span data-ttu-id="636e9-142">drive:\path\filename.xls</span><span class="sxs-lookup"><span data-stu-id="636e9-142">drive:\path\filename.xls</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="636e9-143">Microsoft Excel 4.0</span><span class="sxs-lookup"><span data-stu-id="636e9-143">Microsoft Excel 4.0</span></span></p></td>
<td><p><span data-ttu-id="636e9-144">Excel 4.0;</span><span class="sxs-lookup"><span data-stu-id="636e9-144">Excel 4.0;</span></span></p></td>
<td><p><span data-ttu-id="636e9-145">drive:\path\filename.xls</span><span class="sxs-lookup"><span data-stu-id="636e9-145">drive:\path\filename.xls</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="636e9-146">Microsoft Excel 5.0 或 Microsoft Excel 95</span><span class="sxs-lookup"><span data-stu-id="636e9-146">Microsoft Excel 5.0 or Microsoft Excel 95</span></span></p></td>
<td><p><span data-ttu-id="636e9-147">Excel 5.0;</span><span class="sxs-lookup"><span data-stu-id="636e9-147">Excel 5.0;</span></span></p></td>
<td><p><span data-ttu-id="636e9-148">drive:\path\filename.xls</span><span class="sxs-lookup"><span data-stu-id="636e9-148">drive:\path\filename.xls</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="636e9-149">Microsoft Excel 97</span><span class="sxs-lookup"><span data-stu-id="636e9-149">Microsoft Excel 97</span></span></p></td>
<td><p><span data-ttu-id="636e9-150">Excel 8.0;</span><span class="sxs-lookup"><span data-stu-id="636e9-150">Excel 8.0;</span></span></p></td>
<td><p><span data-ttu-id="636e9-151">drive:\path\filename.xls</span><span class="sxs-lookup"><span data-stu-id="636e9-151">drive:\path\filename.xls</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="636e9-152">Lotus 1-2-3 WKS 和 WK1</span><span class="sxs-lookup"><span data-stu-id="636e9-152">Lotus 1-2-3 WKS and WK1</span></span></p></td>
<td><p><span data-ttu-id="636e9-153">Lotus WK1;</span><span class="sxs-lookup"><span data-stu-id="636e9-153">Lotus WK1;</span></span></p></td>
<td><p><span data-ttu-id="636e9-154">drive:\path\filename.wk1</span><span class="sxs-lookup"><span data-stu-id="636e9-154">drive:\path\filename.wk1</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="636e9-155">Lotus 1-2-3 WK3</span><span class="sxs-lookup"><span data-stu-id="636e9-155">Lotus 1-2-3 WK3</span></span></p></td>
<td><p><span data-ttu-id="636e9-156">Lotus WK3;</span><span class="sxs-lookup"><span data-stu-id="636e9-156">Lotus WK3;</span></span></p></td>
<td><p><span data-ttu-id="636e9-157">drive:\path\filename.wk3</span><span class="sxs-lookup"><span data-stu-id="636e9-157">drive:\path\filename.wk3</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="636e9-158">Lotus 1-2-3 WK4</span><span class="sxs-lookup"><span data-stu-id="636e9-158">Lotus 1-2-3 WK4</span></span></p></td>
<td><p><span data-ttu-id="636e9-159">Lotus WK4;</span><span class="sxs-lookup"><span data-stu-id="636e9-159">Lotus WK4;</span></span></p></td>
<td><p><span data-ttu-id="636e9-160">drive:\path\filename.wk4</span><span class="sxs-lookup"><span data-stu-id="636e9-160">drive:\path\filename.wk4</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="636e9-161">HTML Import</span><span class="sxs-lookup"><span data-stu-id="636e9-161">HTML Import</span></span></p></td>
<td><p><span data-ttu-id="636e9-162">HTML Import;</span><span class="sxs-lookup"><span data-stu-id="636e9-162">HTML Import;</span></span></p></td>
<td><p><span data-ttu-id="636e9-163">drive:\path\filename</span><span class="sxs-lookup"><span data-stu-id="636e9-163">drive:\path\filename</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="636e9-164">HTML Export</span><span class="sxs-lookup"><span data-stu-id="636e9-164">HTML Export</span></span></p></td>
<td><p><span data-ttu-id="636e9-165">HTML Export;</span><span class="sxs-lookup"><span data-stu-id="636e9-165">HTML Export;</span></span></p></td>
<td><p><span data-ttu-id="636e9-166">驱动器： \path</span><span class="sxs-lookup"><span data-stu-id="636e9-166">drive:\path</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="636e9-167">文本</span><span class="sxs-lookup"><span data-stu-id="636e9-167">Text</span></span></p></td>
<td><p><span data-ttu-id="636e9-168">Text;</span><span class="sxs-lookup"><span data-stu-id="636e9-168">Text;</span></span></p></td>
<td><p><span data-ttu-id="636e9-169">驱动器： \path</span><span class="sxs-lookup"><span data-stu-id="636e9-169">drive:\path</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="636e9-170">ODBC</span><span class="sxs-lookup"><span data-stu-id="636e9-170">ODBC</span></span></p></td>
<td><p><span data-ttu-id="636e9-171">ODBC;数据库 = 数据库;UID = 用户;PWD = 密码;DSN = 名称;[LOGINTIMEOUT = 秒;]</span><span class="sxs-lookup"><span data-stu-id="636e9-171">ODBC; DATABASE=database; UID=user; PWD=password; DSN= datasourcename; [LOGINTIMEOUT=seconds;]</span></span></p></td>
<td><p><span data-ttu-id="636e9-172">无</span><span class="sxs-lookup"><span data-stu-id="636e9-172">None</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="636e9-173">Microsoft Exchange</span><span class="sxs-lookup"><span data-stu-id="636e9-173">Microsoft Exchange</span></span></p></td>
<td><p><span data-ttu-id="636e9-174">Exchange 4.0;MAPILEVEL = folderpath;[TABLETYPE = {0 | 1}];[PROFILE = 配置文件;][PWD = 密码;][数据库 = 数据库;]</span><span class="sxs-lookup"><span data-stu-id="636e9-174">Exchange 4.0; MAPILEVEL=folderpath; [TABLETYPE={ 0 | 1 }];[PROFILE=profile;] [PWD=password;] [DATABASE=database;]</span></span></p></td>
<td><p><span data-ttu-id="636e9-175">drive:\path\filename</span><span class="sxs-lookup"><span data-stu-id="636e9-175">drive:\path\filename</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="636e9-176">如果需要密码，但是 **Connect** 属性设置中未提供此密码，那么 ODBC 驱动程序首次访问表时，将显示一个登录对话框，并且在关闭并重新打开连接时，会再次显示该对话框。</span><span class="sxs-lookup"><span data-stu-id="636e9-176">If a password is required but not provided in the **Connect** property setting, a login dialog box is displayed the first time a table is accessed by the ODBC driver and again if the connection is closed and reopened.</span></span>

<span data-ttu-id="636e9-177">对于 Microsoft Exchange 中的数据，应该将必需的 MAPILEVEL 项设置为完全解析的文件夹路径（例如，"Mailbox - Pat SmithIAlpha/Today"）。</span><span class="sxs-lookup"><span data-stu-id="636e9-177">For data in Microsoft Exchange, the required MAPILEVEL key should be set to a fully-resolved folder path (for example, "Mailbox - Pat SmithIAlpha/Today").</span></span> <span data-ttu-id="636e9-178">路径不包含将作为表; 打开文件夹的名称而是应用作**CreateTable**方法的名称参数指定该文件夹的名称。</span><span class="sxs-lookup"><span data-stu-id="636e9-178">The path does not include the name of the folder that will be opened as a table; that folder’s name should instead be specified as the name argument to the **CreateTable** method.</span></span> <span data-ttu-id="636e9-179">TABLETYPE 项应设置为"0"以打开文件夹（默认设置），或设置为"1"以打开通讯簿。</span><span class="sxs-lookup"><span data-stu-id="636e9-179">The TABLETYPE key should be set to "0" to open a folder (default) or "1" to open an address book.</span></span> <span data-ttu-id="636e9-180">PROFILE 项默认为当前使用的配置文件。</span><span class="sxs-lookup"><span data-stu-id="636e9-180">The PROFILE key defaults to the profile currently in use.</span></span>

<span data-ttu-id="636e9-181">对于 Micorosoft Access 数据库中的基表， **Connect** 属性设置为零长度字符串 ("")。</span><span class="sxs-lookup"><span data-stu-id="636e9-181">For base tables in a Micorosoft Access database, the **Connect** property setting is a zero-length string ("").</span></span>


> [!NOTE]
> <UL>
> <LI>
> <P><span data-ttu-id="636e9-182">必须先设置 <STRONG>Connect</STRONG> 属性，然后才能设置 <STRONG>ReturnsRecords</STRONG> 属性。</span><span class="sxs-lookup"><span data-stu-id="636e9-182">You must set the <STRONG>Connect</STRONG> property before you set the <STRONG>ReturnsRecords</STRONG> property.</span></span></P>
> <LI>
> <P><span data-ttu-id="636e9-183">您必须有权访问包含您尝试访问的数据库服务器的计算机。</span><span class="sxs-lookup"><span data-stu-id="636e9-183">You must have access permissions to the computer that contains the database server you're trying to access.</span></span></P></LI></UL>


