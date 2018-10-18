---
title: Microsoft OLE DB Provider for ODBC
TOCTitle: Microsoft OLE DB Provider for ODBC
ms:assetid: c507567e-5ad1-b32a-f6ad-5ba2c39aa4c2
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249964(v=office.15)
ms:contentKeyID: 48547602
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 0098e646ea48656f44bd3ccd380ae41efc94ffba
ms.sourcegitcommit: a49b77f4c8cec69f90656a86f0872cf34c35968e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2018
ms.locfileid: "25606935"
---
# <a name="microsoft-ole-db-provider-for-odbc"></a><span data-ttu-id="9ee04-102">Microsoft OLE DB Provider for ODBC</span><span class="sxs-lookup"><span data-stu-id="9ee04-102">Microsoft OLE DB Provider for ODBC</span></span>

<span data-ttu-id="9ee04-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="9ee04-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="9ee04-p101">对 ADO 或 RDS 程序员来说，理想环境应该是：每个数据源都公开一个 OLE DB 接口，这样 ADO 就可以直接调入数据源。尽管越来越多的数据库供应商要实现 OLE DB 接口，但某些数据源却仍未以此方式公开。实际上，通过 ODBC 可以访问目前在用的所有 DBMS 系统。</span><span class="sxs-lookup"><span data-stu-id="9ee04-p101">To an ADO or RDS programmer, an ideal world would be one in which every data source exposes an OLE DB interface, so that ADO could call directly into the data source. Although increasingly more database vendors are implementing OLE DB interfaces, some data sources are not yet exposed this way. However, virtually all DBMS systems in use today can be accessed through ODBC.</span></span>

<span data-ttu-id="9ee04-107">ODBC 驱动程序可用于目前在用的所有主要的 DBMS，包括 Microsoft SQL Server、Microsoft Access（Microsoft Jet 数据库引擎）、Microsoft FoxPro 以及非 Microsoft 数据库产品（如 Oracle）。</span><span class="sxs-lookup"><span data-stu-id="9ee04-107">ODBC drivers are available for every major DBMS in use today, including Microsoft SQL Server, Microsoft Access (Microsoft Jet database engine), and Microsoft FoxPro, in addition to non-Microsoft database products such as Oracle.</span></span>

<span data-ttu-id="9ee04-p102">Microsoft ODBC Provider 允许 ADO 连接到任何 ODBC 数据源。此提供程序为自由线程并使用 Unicode。</span><span class="sxs-lookup"><span data-stu-id="9ee04-p102">The Microsoft ODBC Provider, however, allows ADO to connect to any ODBC data source. The provider is free-threaded and Unicode enabled.</span></span>

<span data-ttu-id="9ee04-p103">此提供程序支持事务处理，但不同的 DBMS 引擎所支持的事务类型不同。例如，Microsoft Access 支持的嵌套事务可达五层。</span><span class="sxs-lookup"><span data-stu-id="9ee04-p103">The provider supports transactions, although different DBMS engines offer different types of transaction support. For example, Microsoft Access supports nested transactions up to five levels deep.</span></span>

<span data-ttu-id="9ee04-112">此提供程序是 ADO 的默认提供程序，它支持所有与提供程序有关的 ADO 属性和方法。</span><span class="sxs-lookup"><span data-stu-id="9ee04-112">This is the default provider for ADO, and all provider-dependent ADO properties and methods are supported.</span></span>

## <a name="connection-string-parameters"></a><span data-ttu-id="9ee04-113">连接字符串参数</span><span class="sxs-lookup"><span data-stu-id="9ee04-113">Connection String Parameters</span></span>

<span data-ttu-id="9ee04-114">要连接到此提供程序，请将 **ConnectionString** 属性的 [Provider=](connectionstring-property-ado.md) 参数设置为：</span><span class="sxs-lookup"><span data-stu-id="9ee04-114">To connect to this provider, set the **Provider=** argument of the [ConnectionString](connectionstring-property-ado.md) property to:</span></span>

```sql 
 
MSDASQL 
```

<span data-ttu-id="9ee04-115">读取 [Provider](provider-property-ado.md) 属性时，也会返回此字符串。</span><span class="sxs-lookup"><span data-stu-id="9ee04-115">Reading the [Provider](provider-property-ado.md) property will return this string as well.</span></span>

## <a name="typical-connection-string"></a><span data-ttu-id="9ee04-116">典型的连接字符串</span><span class="sxs-lookup"><span data-stu-id="9ee04-116">Typical Connection String</span></span>

<span data-ttu-id="9ee04-117">此提供程序典型的连接字符串为：</span><span class="sxs-lookup"><span data-stu-id="9ee04-117">A typical connection string for this provider is:</span></span>

```sql 
 
"Provider=MSDASQL;DSN=dsnName;UID=userName;PWD=userPassword;" 
```

<span data-ttu-id="9ee04-118">该字符串由以下关键字组成：</span><span class="sxs-lookup"><span data-stu-id="9ee04-118">The string consists of these keywords:</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="9ee04-119">关键字</span><span class="sxs-lookup"><span data-stu-id="9ee04-119">Keyword</span></span></p></th>
<th><p><span data-ttu-id="9ee04-120">说明</span><span class="sxs-lookup"><span data-stu-id="9ee04-120">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9ee04-121"><strong>Provider</strong></span><span class="sxs-lookup"><span data-stu-id="9ee04-121"><strong>Provider</strong></span></span></p></td>
<td><p><span data-ttu-id="9ee04-122">指定 OLE DB Provider for ODBC。</span><span class="sxs-lookup"><span data-stu-id="9ee04-122">Specifies the OLE DB Provider for ODBC.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ee04-123"><strong>DSN</strong></span><span class="sxs-lookup"><span data-stu-id="9ee04-123"><strong>DSN</strong></span></span></p></td>
<td><p><span data-ttu-id="9ee04-124">指定数据源名称。</span><span class="sxs-lookup"><span data-stu-id="9ee04-124">Specifies the data source name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ee04-125"><strong>UID</strong></span><span class="sxs-lookup"><span data-stu-id="9ee04-125"><strong>UID</strong></span></span></p></td>
<td><p><span data-ttu-id="9ee04-126">指定用户名。</span><span class="sxs-lookup"><span data-stu-id="9ee04-126">Specifies the user name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ee04-127"><strong>PWD</strong></span><span class="sxs-lookup"><span data-stu-id="9ee04-127"><strong>PWD</strong></span></span></p></td>
<td><p><span data-ttu-id="9ee04-128">指定用户密码。</span><span class="sxs-lookup"><span data-stu-id="9ee04-128">Specifies the user password.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ee04-129"><strong>URL</strong></span><span class="sxs-lookup"><span data-stu-id="9ee04-129"><strong>URL</strong></span></span></p></td>
<span data-ttu-id="9ee04-130"><<<<<<< 标头</span><span class="sxs-lookup"><span data-stu-id="9ee04-130"><<<<<<< HEAD</span></span>
<td><p><span data-ttu-id="9ee04-131">指定 Web 文件夹中已发布文件或目录的 URL。</span><span class="sxs-lookup"><span data-stu-id="9ee04-131">Specifies the URL of a file or directory published in a Web folder.</span></span></p></td>
=======
<td><p><span data-ttu-id="9ee04-132">指定文件或目录 web 文件夹中发布的 URL。</span><span class="sxs-lookup"><span data-stu-id="9ee04-132">Specifies the URL of a file or directory published in a web folder.</span></span></p></td><span data-ttu-id="9ee04-133">
>>>>>>>主控形状</span><span class="sxs-lookup"><span data-stu-id="9ee04-133">
>>>>>>> master</span></span>
</tr>
</tbody>
</table>


<span data-ttu-id="9ee04-134">如果在连接字符串中省略 **Provider=** 参数，则 ADO 将尝试建立与此提供程序（因为它是 ADO 的默认提供程序）的连接。</span><span class="sxs-lookup"><span data-stu-id="9ee04-134">Because this is the default provider for ADO, if you omit the **Provider=** parameter from the connection string, ADO will attempt to establish a connection to this provider.</span></span>

<span data-ttu-id="9ee04-p104">除了 ADO 定义的连接参数以外，此提供程序不支持任何特定的连接参数，但它会将任何非 ADO 连接参数传递给 ODBC 驱动程序管理器。</span><span class="sxs-lookup"><span data-stu-id="9ee04-p104">The provider does not support any specific connection parameters in addition to those defined by ADO. However, the provider will pass any non-ADO connection parameters to the ODBC driver manager.</span></span>

<span data-ttu-id="9ee04-p105">由于可以省略 **Provider** 参数，因此，可以构造与同一个数据源的 ODBC 连接字符串完全一样的 ADO 连接字符串。参数名称（**DRIVER=**、**DATABASE=**、**DSN=** 等）、值和语法也和构造 ODBC 连接字符串时所用的一样。连接时，可以使用也可以不使用预定义的数据源名称 (DSN) 或 FileDSN。</span><span class="sxs-lookup"><span data-stu-id="9ee04-p105">Because you can omit the **Provider** parameter, you can therefore compose an ADO connection string that is identical to an ODBC connection string for the same data source. Use the same parameter names (**DRIVER=**, **DATABASE=**, **DSN=**, and so on), values, and syntax as you would when composing an ODBC connection string. You can connect with or without a predefined data source name (DSN) or FileDSN.</span></span>

<span data-ttu-id="9ee04-140">**带有 DSN 或 FileDSN 的语法：**</span><span class="sxs-lookup"><span data-stu-id="9ee04-140">**Syntax with a DSN or FileDSN:**</span></span>

`"[Provider=MSDASQL;] { DSN=name | FileDSN=filename } ; [DATABASE=database;] UID=user; PWD=password"`

<span data-ttu-id="9ee04-141">**不带 DSN（无 DSN 连接）的语法：**</span><span class="sxs-lookup"><span data-stu-id="9ee04-141">**Syntax without a DSN (DSN-less connection):**</span></span>

`"[Provider=MSDASQL;] DRIVER=driver; SERVER=server;DATABASE=database; UID=user; PWD=password"`

<span data-ttu-id="9ee04-p106">如果要使用 **DSN** 或 **FileDSN** ，必须通过 Windows "控制面板"中的"ODBC 数据源管理器"进行定义。在 Microsoft Windows 2000 中，ODBC 管理器位于"管理工具"中。在以前的 Windows 版本中，"ODBC 管理器"图标的名称是 **32 位 ODBC** 或者就是 **ODBC** 。</span><span class="sxs-lookup"><span data-stu-id="9ee04-p106">If you use a **DSN** or **FileDSN**, it must be defined through the ODBC Data Source Administrator in the Windows Control Panel. In Microsoft Windows 2000, the ODBC Administrator is located under Administrative Tools. In previous versions of Windows, the ODBC Administrator icon is named **32-bit ODBC** or simply **ODBC**.</span></span>

<span data-ttu-id="9ee04-145">除了设置 **DSN** 以外，还可以指定 ODBC 驱动程序，如“SQL Server” (**DRIVER=**)；可以指定服务器名称 (**SERVER=**) 和数据库名称 (**DATABASE=**)。</span><span class="sxs-lookup"><span data-stu-id="9ee04-145">As an alternative to setting a **DSN**, you can specify the ODBC driver (**DRIVER=**), such as "SQL Server;" the server name (**SERVER=**); and the database name (**DATABASE=**).</span></span>

<span data-ttu-id="9ee04-146">也可以在 ODBC 特定的参数中或在标准的 ADO 定义的 *user* 和 *password* 参数中指定用户帐户名 (**UID=**) 以及用户帐户的密码 (**PWD=**)。</span><span class="sxs-lookup"><span data-stu-id="9ee04-146">You can also specify a user account name (**UID=**), and the password for the user account (**PWD=**) in the ODBC-specific parameters or in the standard ADO-defined *user* and *password* parameters.</span></span>

<span data-ttu-id="9ee04-147">虽然**DSN**定义已指定了数据库，您可以指定除了**DSN**连接到其他数据库*的\*\*数据库*参数。</span><span class="sxs-lookup"><span data-stu-id="9ee04-147">Although a **DSN** definition already specifies a database, you can specify *a* *database* parameter in addition to a **DSN** to connect to a different database.</span></span> <span data-ttu-id="9ee04-148">最好若要使用**DSN**时始终包含\**database*参数\*。</span><span class="sxs-lookup"><span data-stu-id="9ee04-148">It is a good idea to always include *the* *database* parameter when you use a **DSN**.</span></span> <span data-ttu-id="9ee04-149">这将确保在上次检查了 **DSN** 定义后其他用户更改了默认的数据库参数的情况下，依然可以连接到正确的数据库。</span><span class="sxs-lookup"><span data-stu-id="9ee04-149">This will ensure that you connect to the proper database in the event that another user changed the default database parameter since you last checked the **DSN** definition.</span></span>

## <a name="provider-specific-connection-properties"></a><span data-ttu-id="9ee04-150">提供程序特定的连接属性</span><span class="sxs-lookup"><span data-stu-id="9ee04-150">Provider-Specific Connection Properties</span></span>

<span data-ttu-id="9ee04-p108">OLE DB Provider for ODBC 会将多个属性添加到 [Connection](properties-collection-ado.md) 对象的 **Properties** 集合中。下表列出了这些属性以及对应的 OLE DB 属性名（括在括号中）。</span><span class="sxs-lookup"><span data-stu-id="9ee04-p108">The OLE DB provider for ODBC adds several properties to the [Properties](properties-collection-ado.md) collection of the **Connection** object. The following table lists these properties with the corresponding OLE DB property name in parentheses.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="9ee04-153">属性名称</span><span class="sxs-lookup"><span data-stu-id="9ee04-153">Property Name</span></span></p></th>
<th><p><span data-ttu-id="9ee04-154">说明</span><span class="sxs-lookup"><span data-stu-id="9ee04-154">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9ee04-155">可访问的过程</span><span class="sxs-lookup"><span data-stu-id="9ee04-155">Accessible Procedures</span></span><br />
<span data-ttu-id="9ee04-156">(KAGPROP_ACCESSIBLEPROCEDURES)</span><span class="sxs-lookup"><span data-stu-id="9ee04-156">(KAGPROP_ACCESSIBLEPROCEDURES)</span></span></p></td>
<td><p><span data-ttu-id="9ee04-157">指示用户是否有权访问存储过程。</span><span class="sxs-lookup"><span data-stu-id="9ee04-157">Indicates whether the user has access to stored procedures.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ee04-158">可访问的表</span><span class="sxs-lookup"><span data-stu-id="9ee04-158">Accessible Tables</span></span><br />
<span data-ttu-id="9ee04-159">(KAGPROP_ACCESSIBLETABLES)</span><span class="sxs-lookup"><span data-stu-id="9ee04-159">(KAGPROP_ACCESSIBLETABLES)</span></span></p></td>
<td><p><span data-ttu-id="9ee04-160">指示用户是否有权针对数据库表执行 SELECT 语句。</span><span class="sxs-lookup"><span data-stu-id="9ee04-160">Indicates whether the user has permission to execute SELECT statements against the database tables.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ee04-161">活动语句</span><span class="sxs-lookup"><span data-stu-id="9ee04-161">Active Statements</span></span><br />
<span data-ttu-id="9ee04-162">(KAGPROP_ACTIVESTATEMENTS)</span><span class="sxs-lookup"><span data-stu-id="9ee04-162">(KAGPROP_ACTIVESTATEMENTS)</span></span></p></td>
<td><p><span data-ttu-id="9ee04-163">指示 ODBC 驱动程序在连接上可支持的句柄数量。</span><span class="sxs-lookup"><span data-stu-id="9ee04-163">Indicates the number of handles an ODBC driver can support on a connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ee04-164">驱动程序名称</span><span class="sxs-lookup"><span data-stu-id="9ee04-164">Driver Name</span></span><br />
<span data-ttu-id="9ee04-165">(KAGPROP_DRIVERNAME)</span><span class="sxs-lookup"><span data-stu-id="9ee04-165">(KAGPROP_DRIVERNAME)</span></span></p></td>
<td><p><span data-ttu-id="9ee04-166">指示 ODBC 驱动程序的文件名。</span><span class="sxs-lookup"><span data-stu-id="9ee04-166">Indicates the file name of the ODBC driver.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ee04-167">ODBC 驱动程序版本</span><span class="sxs-lookup"><span data-stu-id="9ee04-167">Driver ODBC Version</span></span><br />
<span data-ttu-id="9ee04-168">(KAGPROP_DRIVERODBCVER)</span><span class="sxs-lookup"><span data-stu-id="9ee04-168">(KAGPROP_DRIVERODBCVER)</span></span></p></td>
<td><p><span data-ttu-id="9ee04-169">指示此驱动程序支持的 ODBC 版本。</span><span class="sxs-lookup"><span data-stu-id="9ee04-169">Indicates the version of ODBC that this driver supports.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ee04-170">文件的使用情况</span><span class="sxs-lookup"><span data-stu-id="9ee04-170">File Usage</span></span><br />
<span data-ttu-id="9ee04-171">(KAGPROP_FILEUSAGE)</span><span class="sxs-lookup"><span data-stu-id="9ee04-171">(KAGPROP_FILEUSAGE)</span></span></p></td>
<td><p><span data-ttu-id="9ee04-172">指示驱动程序在数据源中处理文件的方式，作为表还是作为目录。</span><span class="sxs-lookup"><span data-stu-id="9ee04-172">Indicates how the driver treats a file in a data source; as a table or as a catalog.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ee04-173">Like 转义子句</span><span class="sxs-lookup"><span data-stu-id="9ee04-173">Like Escape Clause</span></span><br />
<span data-ttu-id="9ee04-174">(KAGPROP_LIKEESCAPECLAUSE)</span><span class="sxs-lookup"><span data-stu-id="9ee04-174">(KAGPROP_LIKEESCAPECLAUSE)</span></span></p></td>
<td><p><span data-ttu-id="9ee04-175">指示驱动程序是否支持为 WHERE 子句的 LIKE 谓词中的百分号字符 (%) 和下划线字符 (_) 定义和使用转义字符。</span><span class="sxs-lookup"><span data-stu-id="9ee04-175">Indicates whether the driver supports the definition and use of an escape character for the percent character (%) and underline character (_) in the LIKE predicate of a WHERE clause.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ee04-176">在组中的最大列数</span><span class="sxs-lookup"><span data-stu-id="9ee04-176">Max Columns in Group By</span></span><br />
<span data-ttu-id="9ee04-177">(KAGPROP_MAXCOLUMNSINGROUPBY)</span><span class="sxs-lookup"><span data-stu-id="9ee04-177">(KAGPROP_MAXCOLUMNSINGROUPBY)</span></span></p></td>
<td><p><span data-ttu-id="9ee04-178">指示 SELECT 语句的 GROUP BY 子句中可以列出的列的最大数目。</span><span class="sxs-lookup"><span data-stu-id="9ee04-178">Indicates the maximum number of columns that can be listed in the GROUP BY clause of a SELECT statement.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ee04-179">在索引中的最大列</span><span class="sxs-lookup"><span data-stu-id="9ee04-179">Max Columns in Index</span></span><br />
<span data-ttu-id="9ee04-180">(KAGPROP_MAXCOLUMNSININDEX)</span><span class="sxs-lookup"><span data-stu-id="9ee04-180">(KAGPROP_MAXCOLUMNSININDEX)</span></span></p></td>
<td><p><span data-ttu-id="9ee04-181">指示索引中可以包括的列的最大数目。</span><span class="sxs-lookup"><span data-stu-id="9ee04-181">Indicates the maximum number of columns that can be included in an index.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ee04-182">按顺序的最大列</span><span class="sxs-lookup"><span data-stu-id="9ee04-182">Max Columns in Order By</span></span><br />
<span data-ttu-id="9ee04-183">(KAGPROP_MAXCOLUMNSINORDERBY)</span><span class="sxs-lookup"><span data-stu-id="9ee04-183">(KAGPROP_MAXCOLUMNSINORDERBY)</span></span></p></td>
<td><p><span data-ttu-id="9ee04-184">指示 SELECT 语句的 ORDER BY 子句中可以列出的列的最大数目。</span><span class="sxs-lookup"><span data-stu-id="9ee04-184">Indicates the maximum number of columns that can be listed in the ORDER BY clause of a SELECT statement.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ee04-185">在选择最大列数</span><span class="sxs-lookup"><span data-stu-id="9ee04-185">Max Columns in Select</span></span><br />
<span data-ttu-id="9ee04-186">(KAGPROP_MAXCOLUMNSINSELECT)</span><span class="sxs-lookup"><span data-stu-id="9ee04-186">(KAGPROP_MAXCOLUMNSINSELECT)</span></span></p></td>
<td><p><span data-ttu-id="9ee04-187">指示 SELECT 语句的 SELECT 部分中可以列出的列的最大数目。</span><span class="sxs-lookup"><span data-stu-id="9ee04-187">Indicates the maximum number of columns that can be listed in the SELECT portion of a SELECT statement.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ee04-188">表中的最大列</span><span class="sxs-lookup"><span data-stu-id="9ee04-188">Max Columns in Table</span></span><br />
<span data-ttu-id="9ee04-189">(KAGPROP_MAXCOLUMNSINTABLE)</span><span class="sxs-lookup"><span data-stu-id="9ee04-189">(KAGPROP_MAXCOLUMNSINTABLE)</span></span></p></td>
<td><p><span data-ttu-id="9ee04-190">指示表中允许的列的最大数目。</span><span class="sxs-lookup"><span data-stu-id="9ee04-190">Indicates the maximum number of columns allowed in a table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ee04-191">数值函数</span><span class="sxs-lookup"><span data-stu-id="9ee04-191">Numeric Functions</span></span><br />
<span data-ttu-id="9ee04-192">(KAGPROP_NUMERICFUNCTIONS)</span><span class="sxs-lookup"><span data-stu-id="9ee04-192">(KAGPROP_NUMERICFUNCTIONS)</span></span></p></td>
<td><p><span data-ttu-id="9ee04-p109">指示 ODBC 驱动程序支持的数值函数。有关此位掩码中使用的函数名称和关联值的列表，请参阅 ODBC 文档中的“附录 E：标量函数”。</span><span class="sxs-lookup"><span data-stu-id="9ee04-p109">Indicates which numeric functions are supported by the ODBC driver. For a listing of function names and the associated values used in this bitmask, see Appendix E: Scalar Functions in the ODBC documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ee04-195">外部联接功能</span><span class="sxs-lookup"><span data-stu-id="9ee04-195">Outer Join Capabilities</span></span><br />
<span data-ttu-id="9ee04-196">(KAGPROP_OJCAPABILITY)</span><span class="sxs-lookup"><span data-stu-id="9ee04-196">(KAGPROP_OJCAPABILITY)</span></span></p></td>
<td><p><span data-ttu-id="9ee04-197">指示此提供程序支持的 OUTER JOIN 类型。</span><span class="sxs-lookup"><span data-stu-id="9ee04-197">Indicates the types of OUTER JOINs supported by the provider.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ee04-198">Outer Join</span><span class="sxs-lookup"><span data-stu-id="9ee04-198">Outer Joins</span></span><br />
<span data-ttu-id="9ee04-199">(KAGPROP_OUTERJOINS)</span><span class="sxs-lookup"><span data-stu-id="9ee04-199">(KAGPROP_OUTERJOINS)</span></span></p></td>
<td><p><span data-ttu-id="9ee04-200">指示支持 OUTER JOIN 的提供程序。</span><span class="sxs-lookup"><span data-stu-id="9ee04-200">Indicates whether the provider supports OUTER JOINs.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ee04-201">特殊字符</span><span class="sxs-lookup"><span data-stu-id="9ee04-201">Special Characters</span></span><br />
<span data-ttu-id="9ee04-202">(KAGPROP_SPECIALCHARACTERS)</span><span class="sxs-lookup"><span data-stu-id="9ee04-202">(KAGPROP_SPECIALCHARACTERS)</span></span></p></td>
<td><p><span data-ttu-id="9ee04-203">指示哪些字符对于 ODBC 驱动程序具有特殊意义。</span><span class="sxs-lookup"><span data-stu-id="9ee04-203">Indicates which characters have special meaning for the ODBC driver.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ee04-204">存储过程</span><span class="sxs-lookup"><span data-stu-id="9ee04-204">Stored Procedures</span></span><br />
<span data-ttu-id="9ee04-205">(KAGPROP_PROCEDURES)</span><span class="sxs-lookup"><span data-stu-id="9ee04-205">(KAGPROP_PROCEDURES)</span></span></p></td>
<td><p><span data-ttu-id="9ee04-206">指示是否可以在此 ODBC 驱动程序中使用存储过程。</span><span class="sxs-lookup"><span data-stu-id="9ee04-206">Indicates whether stored procedures are available for use with this ODBC driver.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ee04-207">字符串函数</span><span class="sxs-lookup"><span data-stu-id="9ee04-207">String Functions</span></span><br />
<span data-ttu-id="9ee04-208">(KAGPROP_STRINGFUNCTIONS)</span><span class="sxs-lookup"><span data-stu-id="9ee04-208">(KAGPROP_STRINGFUNCTIONS)</span></span></p></td>
<td><p><span data-ttu-id="9ee04-p110">指示 ODBC 驱动程序支持的字符串函数。有关此位掩码中使用的函数名称和关联值的列表，请参阅 ODBC 文档中的“附录 E：标量函数”。</span><span class="sxs-lookup"><span data-stu-id="9ee04-p110">Indicates which string functions are supported by the ODBC driver. For a listing of function names and the associated values used in this bitmask, see Appendix E: Scalar Functions in the ODBC documentation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ee04-211">系统函数</span><span class="sxs-lookup"><span data-stu-id="9ee04-211">System Functions</span></span><br />
<span data-ttu-id="9ee04-212">(KAGPROP_SYSTEMFUNCTIONS)</span><span class="sxs-lookup"><span data-stu-id="9ee04-212">(KAGPROP_SYSTEMFUNCTIONS)</span></span></p></td>
<td><p><span data-ttu-id="9ee04-p111">指示 ODBC 驱动程序支持的系统函数。有关此位掩码中使用的函数名称和关联值的列表，请参阅 ODBC 文档中的“附录 E：标量函数”。</span><span class="sxs-lookup"><span data-stu-id="9ee04-p111">Indicates which system functions are supported by the ODBC driver. For a listing of function names and the associated values used in this bitmask, see Appendix E: Scalar Functions in the ODBC documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ee04-215">时间/日期函数</span><span class="sxs-lookup"><span data-stu-id="9ee04-215">Time/Date Functions</span></span><br />
<span data-ttu-id="9ee04-216">(KAGPROP_TIMEDATEFUNCTIONS)</span><span class="sxs-lookup"><span data-stu-id="9ee04-216">(KAGPROP_TIMEDATEFUNCTIONS)</span></span></p></td>
<td><p><span data-ttu-id="9ee04-p112">指示 ODBC 驱动程序支持的时间和日期函数。有关此位掩码中使用的函数名称和关联值的列表，请参阅 ODBC 文档中的“附录 E：标量函数”。</span><span class="sxs-lookup"><span data-stu-id="9ee04-p112">Indicates which time and date functions are supported by the ODBC driver. For a listing of function names and the associated values used in this bitmask, see Appendix E: Scalar Functions in the ODBC documentation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ee04-219">SQL 语法支持</span><span class="sxs-lookup"><span data-stu-id="9ee04-219">SQL Grammar Support</span></span><br />
<span data-ttu-id="9ee04-220">(KAGPROP_ODBCSQLCONFORMANCE)</span><span class="sxs-lookup"><span data-stu-id="9ee04-220">(KAGPROP_ODBCSQLCONFORMANCE)</span></span></p></td>
<td><p><span data-ttu-id="9ee04-221">指示 ODBC 驱动程序支持的 SQL 语法。</span><span class="sxs-lookup"><span data-stu-id="9ee04-221">Indicates the SQL grammar that the ODBC driver supports.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="provider-specific-recordset-and-command-properties"></a><span data-ttu-id="9ee04-222">提供程序特定的 Recordset 和 Command 属性</span><span class="sxs-lookup"><span data-stu-id="9ee04-222">Provider-Specific Recordset and Command Properties</span></span>

<span data-ttu-id="9ee04-p113">OLE DB Provider for ODBC 会将多个属性添加到 **Recordset** 和 **Command** 对象的 **Properties** 集合中。下表列出了这些属性以及对应的 OLE DB 属性名（括在括号中）。</span><span class="sxs-lookup"><span data-stu-id="9ee04-p113">The OLE DB provider for ODBC adds several properties to the **Properties** collection of the **Recordset** and **Command** objects. The following table lists these properties with the corresponding OLE DB property name in parentheses.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="9ee04-225">属性名称</span><span class="sxs-lookup"><span data-stu-id="9ee04-225">Property Name</span></span></p></th>
<th><p><span data-ttu-id="9ee04-226">说明</span><span class="sxs-lookup"><span data-stu-id="9ee04-226">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9ee04-227">基于查询的插入/删除/更新</span><span class="sxs-lookup"><span data-stu-id="9ee04-227">Query Based Updates/Deletes/Inserts</span></span><br />
<span data-ttu-id="9ee04-228">(KAGPROP_QUERYBASEDUPDATES)</span><span class="sxs-lookup"><span data-stu-id="9ee04-228">(KAGPROP_QUERYBASEDUPDATES)</span></span></p></td>
<td><p><span data-ttu-id="9ee04-229">指示是否可以使用 SQL 查询执行更新、删除和插入。</span><span class="sxs-lookup"><span data-stu-id="9ee04-229">Indicates whether updates, deletions, and insertions can be performed using SQL queries.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ee04-230">ODBC 并发类型</span><span class="sxs-lookup"><span data-stu-id="9ee04-230">ODBC Concurrency Type</span></span><br />
<span data-ttu-id="9ee04-231">(KAGPROP_CONCURRENCY)</span><span class="sxs-lookup"><span data-stu-id="9ee04-231">(KAGPROP_CONCURRENCY)</span></span></p></td>
<td><p><span data-ttu-id="9ee04-232">指示用于减少由两个用户试图同时访问数据源中的相同数据而导致的潜在问题的方法。</span><span class="sxs-lookup"><span data-stu-id="9ee04-232">Indicates the method used to reduce potential problems caused by two users attempting to access the same data from the data source simultaneously.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ee04-233">仅向前型游标的 BLOB 辅助功能</span><span class="sxs-lookup"><span data-stu-id="9ee04-233">BLOB accessibility on Forward-Only cursor</span></span><br />
<span data-ttu-id="9ee04-234">(KAGPROP_BLOBSONFOCURSOR)</span><span class="sxs-lookup"><span data-stu-id="9ee04-234">(KAGPROP_BLOBSONFOCURSOR)</span></span></p></td>
<td><p><span data-ttu-id="9ee04-235">指示在使用只进游标时是否可以访问 BLOB <strong>字段</strong>。</span><span class="sxs-lookup"><span data-stu-id="9ee04-235">Indicates whether BLOB <strong>Fields</strong> can be accessed when using a forward-only cursor.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ee04-236">在 QBU WHERE 子句中包括 SQL_FLOAT、 SQL_DOUBLE 和 SQL_REAL</span><span class="sxs-lookup"><span data-stu-id="9ee04-236">Include SQL_FLOAT, SQL_DOUBLE, and SQL_REAL in QBU WHERE clauses</span></span><br />
<span data-ttu-id="9ee04-237">(KAGPROP_INCLUDENONEXACT)</span><span class="sxs-lookup"><span data-stu-id="9ee04-237">(KAGPROP_INCLUDENONEXACT)</span></span></p></td>
<td><p><span data-ttu-id="9ee04-238">指示 QBU WHERE 子句中是否可以包括 SQL_FLOAT、SQL_DOUBLE 和 SQL_REAL 值。</span><span class="sxs-lookup"><span data-stu-id="9ee04-238">Indicates whether SQL_FLOAT, SQL_DOUBLE, and SQL_REAL values can be included in a QBU WHERE clause.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ee04-239">在最后一行之后插入的位置</span><span class="sxs-lookup"><span data-stu-id="9ee04-239">Position on the last row after insert</span></span><br />
<span data-ttu-id="9ee04-240">(KAGPROP_POSITIONONNEWROW)</span><span class="sxs-lookup"><span data-stu-id="9ee04-240">(KAGPROP_POSITIONONNEWROW)</span></span></p></td>
<td><p><span data-ttu-id="9ee04-241">指示在表中插入新记录后，表中的最后一行是否将为当前行。</span><span class="sxs-lookup"><span data-stu-id="9ee04-241">Indicates that after a new record has been inserted in a table, the last row in the table will be come the current row.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ee04-242">IRowsetChangeExtInfo</span><span class="sxs-lookup"><span data-stu-id="9ee04-242">IRowsetChangeExtInfo</span></span><br />
<span data-ttu-id="9ee04-243">(KAGPROP_IROWSETCHANGEEXTINFO)</span><span class="sxs-lookup"><span data-stu-id="9ee04-243">(KAGPROP_IROWSETCHANGEEXTINFO)</span></span></p></td>
<td><p><span data-ttu-id="9ee04-244">指示 <strong>IRowsetChange</strong> 接口是否提供扩展的信息支持。</span><span class="sxs-lookup"><span data-stu-id="9ee04-244">Indicates whether the <strong>IRowsetChange</strong> interface provides extended information support.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ee04-245">ODBC 游标类型</span><span class="sxs-lookup"><span data-stu-id="9ee04-245">ODBC Cursor Type</span></span><br />
<span data-ttu-id="9ee04-246">(KAGPROP_CURSOR)</span><span class="sxs-lookup"><span data-stu-id="9ee04-246">(KAGPROP_CURSOR)</span></span></p></td>
<td><p><span data-ttu-id="9ee04-247">指示 <strong>Recordset</strong> 使用的游标类型。</span><span class="sxs-lookup"><span data-stu-id="9ee04-247">Indicates the type of cursor used by the <strong>Recordset</strong>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ee04-248">生成可封送的行集</span><span class="sxs-lookup"><span data-stu-id="9ee04-248">Generate a Rowset that can be marshaled</span></span><br />
<span data-ttu-id="9ee04-249">(KAGPROP_MARSHALLABLE)</span><span class="sxs-lookup"><span data-stu-id="9ee04-249">(KAGPROP_MARSHALLABLE)</span></span></p></td>
<td><p><span data-ttu-id="9ee04-250">指示 ODBC 驱动程序将生成可封送的记录集</span><span class="sxs-lookup"><span data-stu-id="9ee04-250">Indicates that the ODBC driver generates a recordset that can be marshaled</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="command-text"></a><span data-ttu-id="9ee04-251">命令文本</span><span class="sxs-lookup"><span data-stu-id="9ee04-251">Command Text</span></span>

<span data-ttu-id="9ee04-252">如何使用 [Command](command-object-ado.md) 对象在很大程度上取决于数据源及其将接受的查询语句或命令语句的类型。</span><span class="sxs-lookup"><span data-stu-id="9ee04-252">How you use the [Command](command-object-ado.md) object largely depends on the data source, and what type of query or command statement it will accept.</span></span>

<span data-ttu-id="9ee04-253">ODBC 提供了用于调用存储过程的特定语法。</span><span class="sxs-lookup"><span data-stu-id="9ee04-253">ODBC provides a specific syntax for calling stored procedures.</span></span> <span data-ttu-id="9ee04-254">**Command**对象、 的[Connection](connection-object-ado.md)对象的**Execute**方法的*CommandText*参数或[Recordset](recordset-object-ado.md)的**Open**方法的*源*参数[将 CommandText](commandtext-property-ado.md)属性对象，此语法与字符串中传递：</span><span class="sxs-lookup"><span data-stu-id="9ee04-254">For the [CommandText](commandtext-property-ado.md) property of a **Command** object, the *CommandText* argument to the **Execute** method on a [Connection](connection-object-ado.md) object, or the *Source* argument to the **Open** method on a [Recordset](recordset-object-ado.md) object, passes in a string with this syntax:</span></span>

`"{ [ ? = ] call procedure [ ( ? [, ? [ ,  ]] ) ] }"`

<span data-ttu-id="9ee04-p115">每个 **?** 都引用 [Parameters](parameters-collection-ado.md) 集合中的一个对象。第一个 **?** 引用 **Parameters**(0)，接下来的 **?** 引用 **Parameters**(1)，依此类推。</span><span class="sxs-lookup"><span data-stu-id="9ee04-p115">Each **?** references an object in the [Parameters](parameters-collection-ado.md) collection. The first **?** references **Parameters**(0), the next **?** references **Parameters**(1), and so on.</span></span>

<span data-ttu-id="9ee04-p116">参数引用是可选的，且取决于存储过程的结构。如果要调用未定义参数的存储过程，则字符串的形式将与以下所示类似：</span><span class="sxs-lookup"><span data-stu-id="9ee04-p116">The parameter references are optional and depend on the structure of the stored procedure. If you want to call a stored procedure that defines no parameters, your string would look like this:</span></span>

`"{ call procedure }"`

<span data-ttu-id="9ee04-262">如果具有两个查询参数，则字符串的形式将与以下所示类似：</span><span class="sxs-lookup"><span data-stu-id="9ee04-262">If you have two query parameters, your string would look like this:</span></span>

`"{ call procedure ( ?, ? ) }"`

<span data-ttu-id="9ee04-p117">如果存储过程返回一个值，则返回值被作为其他参数进行处理。如果您没有查询参数，但是有返回值，则字符串的形式将与以下所示类似：</span><span class="sxs-lookup"><span data-stu-id="9ee04-p117">If the stored procedure will return a value, the return value is treated as another parameter. If you have no query parameters but you do have a return value, your string would look like this:</span></span>

`"{ ? = call procedure }"`

<span data-ttu-id="9ee04-265">最后，如果您具有一个返回值和两个查询参数，则字符串的形式将与以下所示类似：</span><span class="sxs-lookup"><span data-stu-id="9ee04-265">Finally, if you have a return value and two query parameters, your string would look like this:</span></span>

`"{ ? = call procedure ( ?, ? ) }"`

## <a name="recordset-behavior"></a><span data-ttu-id="9ee04-266">Recordset 行为</span><span class="sxs-lookup"><span data-stu-id="9ee04-266">Recordset Behavior</span></span>

<span data-ttu-id="9ee04-267">下面的表列出了使用此提供程序打开的 **Recordset** 对象中可用的标准 ADO 方法和属性。</span><span class="sxs-lookup"><span data-stu-id="9ee04-267">The following tables list the standard ADO methods and properties available on a **Recordset** object opened with this provider.</span></span>

<span data-ttu-id="9ee04-268">有关提供程序配置的 **Recordset** 行为的详细信息，请运行 [Supports](supports-method-ado.md) 方法并枚举 **Recordset** 的 **Properties** 集合，以确定提供程序特定的动态属性是否存在。</span><span class="sxs-lookup"><span data-stu-id="9ee04-268">For more detailed information about **Recordset** behavior for your provider configuration, run the [Supports](supports-method-ado.md) method and enumerate the **Properties** collection of the **Recordset** to determine whether provider-specific dynamic properties are present.</span></span>

<span data-ttu-id="9ee04-269">标准 ADO **Recordset** 属性的可用性：</span><span class="sxs-lookup"><span data-stu-id="9ee04-269">Availability of standard ADO **Recordset** properties:</span></span>

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="9ee04-270">属性</span><span class="sxs-lookup"><span data-stu-id="9ee04-270">Property</span></span></p></th>
<th><p><span data-ttu-id="9ee04-271">ForwardOnly</span><span class="sxs-lookup"><span data-stu-id="9ee04-271">ForwardOnly</span></span></p></th>
<th><p><span data-ttu-id="9ee04-272">动态</span><span class="sxs-lookup"><span data-stu-id="9ee04-272">Dynamic</span></span></p></th>
<th><p><span data-ttu-id="9ee04-273">键集</span><span class="sxs-lookup"><span data-stu-id="9ee04-273">Keyset</span></span></p></th>
<th><p><span data-ttu-id="9ee04-274">静态</span><span class="sxs-lookup"><span data-stu-id="9ee04-274">Static</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9ee04-275"><a href="absolutepage-property-ado.md">AbsolutePage</a></span><span class="sxs-lookup"><span data-stu-id="9ee04-275"><a href="absolutepage-property-ado.md">AbsolutePage</a></span></span></p></td>
<td><p><span data-ttu-id="9ee04-276">不可用</span><span class="sxs-lookup"><span data-stu-id="9ee04-276">not available</span></span></p></td>
<td><p><span data-ttu-id="9ee04-277">不可用</span><span class="sxs-lookup"><span data-stu-id="9ee04-277">not available</span></span></p></td>
<td><p><span data-ttu-id="9ee04-278">读/写</span><span class="sxs-lookup"><span data-stu-id="9ee04-278">read/write</span></span></p></td>
<td><p><span data-ttu-id="9ee04-279">读/写</span><span class="sxs-lookup"><span data-stu-id="9ee04-279">read/write</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ee04-280"><a href="absoluteposition-property-ado.md">AbsolutePosition</a></span><span class="sxs-lookup"><span data-stu-id="9ee04-280"><a href="absoluteposition-property-ado.md">AbsolutePosition</a></span></span></p></td>
<td><p><span data-ttu-id="9ee04-281">不可用</span><span class="sxs-lookup"><span data-stu-id="9ee04-281">not available</span></span></p></td>
<td><p><span data-ttu-id="9ee04-282">不可用</span><span class="sxs-lookup"><span data-stu-id="9ee04-282">not available</span></span></p></td>
<td><p><span data-ttu-id="9ee04-283">读/写</span><span class="sxs-lookup"><span data-stu-id="9ee04-283">read/write</span></span></p></td>
<td><p><span data-ttu-id="9ee04-284">读/写</span><span class="sxs-lookup"><span data-stu-id="9ee04-284">read/write</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ee04-285"><a href="activeconnection-property-ado.md">ActiveConnection</a></span><span class="sxs-lookup"><span data-stu-id="9ee04-285"><a href="activeconnection-property-ado.md">ActiveConnection</a></span></span></p></td>
<td><p><span data-ttu-id="9ee04-286">读/写</span><span class="sxs-lookup"><span data-stu-id="9ee04-286">read/write</span></span></p></td>
<td><p><span data-ttu-id="9ee04-287">读/写</span><span class="sxs-lookup"><span data-stu-id="9ee04-287">read/write</span></span></p></td>
<td><p><span data-ttu-id="9ee04-288">读/写</span><span class="sxs-lookup"><span data-stu-id="9ee04-288">read/write</span></span></p></td>
<td><p><span data-ttu-id="9ee04-289">读/写</span><span class="sxs-lookup"><span data-stu-id="9ee04-289">read/write</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ee04-290"><a href="bof-eof-properties-ado.md">BOF</a></span><span class="sxs-lookup"><span data-stu-id="9ee04-290"><a href="bof-eof-properties-ado.md">BOF</a></span></span></p></td>
<td><p><span data-ttu-id="9ee04-291">只读</span><span class="sxs-lookup"><span data-stu-id="9ee04-291">read-only</span></span></p></td>
<td><p><span data-ttu-id="9ee04-292">只读</span><span class="sxs-lookup"><span data-stu-id="9ee04-292">read-only</span></span></p></td>
<td><p><span data-ttu-id="9ee04-293">只读</span><span class="sxs-lookup"><span data-stu-id="9ee04-293">read-only</span></span></p></td>
<td><p><span data-ttu-id="9ee04-294">只读</span><span class="sxs-lookup"><span data-stu-id="9ee04-294">read-only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ee04-295"><a href="bookmark-property-ado.md">Bookmark</a></span><span class="sxs-lookup"><span data-stu-id="9ee04-295"><a href="bookmark-property-ado.md">Bookmark</a></span></span></p></td>
<td><p><span data-ttu-id="9ee04-296">不可用</span><span class="sxs-lookup"><span data-stu-id="9ee04-296">not available</span></span></p></td>
<td><p><span data-ttu-id="9ee04-297">不可用</span><span class="sxs-lookup"><span data-stu-id="9ee04-297">not available</span></span></p></td>
<td><p><span data-ttu-id="9ee04-298">读/写</span><span class="sxs-lookup"><span data-stu-id="9ee04-298">read/write</span></span></p></td>
<td><p><span data-ttu-id="9ee04-299">读/写</span><span class="sxs-lookup"><span data-stu-id="9ee04-299">read/write</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ee04-300"><a href="cachesize-property-ado.md">CacheSize</a></span><span class="sxs-lookup"><span data-stu-id="9ee04-300"><a href="cachesize-property-ado.md">CacheSize</a></span></span></p></td>
<td><p><span data-ttu-id="9ee04-301">读/写</span><span class="sxs-lookup"><span data-stu-id="9ee04-301">read/write</span></span></p></td>
<td><p><span data-ttu-id="9ee04-302">读/写</span><span class="sxs-lookup"><span data-stu-id="9ee04-302">read/write</span></span></p></td>
<td><p><span data-ttu-id="9ee04-303">读/写</span><span class="sxs-lookup"><span data-stu-id="9ee04-303">read/write</span></span></p></td>
<td><p><span data-ttu-id="9ee04-304">读/写</span><span class="sxs-lookup"><span data-stu-id="9ee04-304">read/write</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ee04-305"><a href="cursorlocation-property-ado.md">CursorLocation</a></span><span class="sxs-lookup"><span data-stu-id="9ee04-305"><a href="cursorlocation-property-ado.md">CursorLocation</a></span></span></p></td>
<td><p><span data-ttu-id="9ee04-306">读/写</span><span class="sxs-lookup"><span data-stu-id="9ee04-306">read/write</span></span></p></td>
<td><p><span data-ttu-id="9ee04-307">读/写</span><span class="sxs-lookup"><span data-stu-id="9ee04-307">read/write</span></span></p></td>
<td><p><span data-ttu-id="9ee04-308">读/写</span><span class="sxs-lookup"><span data-stu-id="9ee04-308">read/write</span></span></p></td>
<td><p><span data-ttu-id="9ee04-309">读/写</span><span class="sxs-lookup"><span data-stu-id="9ee04-309">read/write</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ee04-310"><a href="cursortype-property-ado.md">CursorType</a></span><span class="sxs-lookup"><span data-stu-id="9ee04-310"><a href="cursortype-property-ado.md">CursorType</a></span></span></p></td>
<td><p><span data-ttu-id="9ee04-311">读/写</span><span class="sxs-lookup"><span data-stu-id="9ee04-311">read/write</span></span></p></td>
<td><p><span data-ttu-id="9ee04-312">读/写</span><span class="sxs-lookup"><span data-stu-id="9ee04-312">read/write</span></span></p></td>
<td><p><span data-ttu-id="9ee04-313">读/写</span><span class="sxs-lookup"><span data-stu-id="9ee04-313">read/write</span></span></p></td>
<td><p><span data-ttu-id="9ee04-314">读/写</span><span class="sxs-lookup"><span data-stu-id="9ee04-314">read/write</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ee04-315"><a href="editmode-property-ado.md">EditMode</a></span><span class="sxs-lookup"><span data-stu-id="9ee04-315"><a href="editmode-property-ado.md">EditMode</a></span></span></p></td>
<td><p><span data-ttu-id="9ee04-316">只读</span><span class="sxs-lookup"><span data-stu-id="9ee04-316">read-only</span></span></p></td>
<td><p><span data-ttu-id="9ee04-317">只读</span><span class="sxs-lookup"><span data-stu-id="9ee04-317">read-only</span></span></p></td>
<td><p><span data-ttu-id="9ee04-318">只读</span><span class="sxs-lookup"><span data-stu-id="9ee04-318">read-only</span></span></p></td>
<td><p><span data-ttu-id="9ee04-319">只读</span><span class="sxs-lookup"><span data-stu-id="9ee04-319">read-only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ee04-320"><a href="filter-property-ado.md">Filter</a></span><span class="sxs-lookup"><span data-stu-id="9ee04-320"><a href="filter-property-ado.md">Filter</a></span></span></p></td>
<td><p><span data-ttu-id="9ee04-321">读/写</span><span class="sxs-lookup"><span data-stu-id="9ee04-321">read/write</span></span></p></td>
<td><p><span data-ttu-id="9ee04-322">读/写</span><span class="sxs-lookup"><span data-stu-id="9ee04-322">read/write</span></span></p></td>
<td><p><span data-ttu-id="9ee04-323">读/写</span><span class="sxs-lookup"><span data-stu-id="9ee04-323">read/write</span></span></p></td>
<td><p><span data-ttu-id="9ee04-324">读/写</span><span class="sxs-lookup"><span data-stu-id="9ee04-324">read/write</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ee04-325"><a href="locktype-property-ado.md">LockType</a></span><span class="sxs-lookup"><span data-stu-id="9ee04-325"><a href="locktype-property-ado.md">LockType</a></span></span></p></td>
<td><p><span data-ttu-id="9ee04-326">读/写</span><span class="sxs-lookup"><span data-stu-id="9ee04-326">read/write</span></span></p></td>
<td><p><span data-ttu-id="9ee04-327">读/写</span><span class="sxs-lookup"><span data-stu-id="9ee04-327">read/write</span></span></p></td>
<td><p><span data-ttu-id="9ee04-328">读/写</span><span class="sxs-lookup"><span data-stu-id="9ee04-328">read/write</span></span></p></td>
<td><p><span data-ttu-id="9ee04-329">读/写</span><span class="sxs-lookup"><span data-stu-id="9ee04-329">read/write</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ee04-330"><a href="marshaloptions-property-ado.md">MarshalOptions</a></span><span class="sxs-lookup"><span data-stu-id="9ee04-330"><a href="marshaloptions-property-ado.md">MarshalOptions</a></span></span></p></td>
<td><p><span data-ttu-id="9ee04-331">读/写</span><span class="sxs-lookup"><span data-stu-id="9ee04-331">read/write</span></span></p></td>
<td><p><span data-ttu-id="9ee04-332">读/写</span><span class="sxs-lookup"><span data-stu-id="9ee04-332">read/write</span></span></p></td>
<td><p><span data-ttu-id="9ee04-333">读/写</span><span class="sxs-lookup"><span data-stu-id="9ee04-333">read/write</span></span></p></td>
<td><p><span data-ttu-id="9ee04-334">读/写</span><span class="sxs-lookup"><span data-stu-id="9ee04-334">read/write</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ee04-335"><a href="maxrecords-property-ado.md">MaxRecords</a></span><span class="sxs-lookup"><span data-stu-id="9ee04-335"><a href="maxrecords-property-ado.md">MaxRecords</a></span></span></p></td>
<td><p><span data-ttu-id="9ee04-336">读/写</span><span class="sxs-lookup"><span data-stu-id="9ee04-336">read/write</span></span></p></td>
<td><p><span data-ttu-id="9ee04-337">读/写</span><span class="sxs-lookup"><span data-stu-id="9ee04-337">read/write</span></span></p></td>
<td><p><span data-ttu-id="9ee04-338">读/写</span><span class="sxs-lookup"><span data-stu-id="9ee04-338">read/write</span></span></p></td>
<td><p><span data-ttu-id="9ee04-339">读/写</span><span class="sxs-lookup"><span data-stu-id="9ee04-339">read/write</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ee04-340"><a href="pagecount-property-ado.md">PageCount</a></span><span class="sxs-lookup"><span data-stu-id="9ee04-340"><a href="pagecount-property-ado.md">PageCount</a></span></span></p></td>
<td><p><span data-ttu-id="9ee04-341">读/写</span><span class="sxs-lookup"><span data-stu-id="9ee04-341">read/write</span></span></p></td>
<td><p><span data-ttu-id="9ee04-342">不可用</span><span class="sxs-lookup"><span data-stu-id="9ee04-342">not available</span></span></p></td>
<td><p><span data-ttu-id="9ee04-343">只读</span><span class="sxs-lookup"><span data-stu-id="9ee04-343">read-only</span></span></p></td>
<td><p><span data-ttu-id="9ee04-344">只读</span><span class="sxs-lookup"><span data-stu-id="9ee04-344">read-only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ee04-345"><a href="pagesize-property-ado.md">PageSize</a></span><span class="sxs-lookup"><span data-stu-id="9ee04-345"><a href="pagesize-property-ado.md">PageSize</a></span></span></p></td>
<td><p><span data-ttu-id="9ee04-346">读/写</span><span class="sxs-lookup"><span data-stu-id="9ee04-346">read/write</span></span></p></td>
<td><p><span data-ttu-id="9ee04-347">读/写</span><span class="sxs-lookup"><span data-stu-id="9ee04-347">read/write</span></span></p></td>
<td><p><span data-ttu-id="9ee04-348">读/写</span><span class="sxs-lookup"><span data-stu-id="9ee04-348">read/write</span></span></p></td>
<td><p><span data-ttu-id="9ee04-349">读/写</span><span class="sxs-lookup"><span data-stu-id="9ee04-349">read/write</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ee04-350"><a href="recordcount-property-ado.md">RecordCount</a></span><span class="sxs-lookup"><span data-stu-id="9ee04-350"><a href="recordcount-property-ado.md">RecordCount</a></span></span></p></td>
<td><p><span data-ttu-id="9ee04-351">读/写</span><span class="sxs-lookup"><span data-stu-id="9ee04-351">read/write</span></span></p></td>
<td><p><span data-ttu-id="9ee04-352">不可用</span><span class="sxs-lookup"><span data-stu-id="9ee04-352">not available</span></span></p></td>
<td><p><span data-ttu-id="9ee04-353">只读</span><span class="sxs-lookup"><span data-stu-id="9ee04-353">read-only</span></span></p></td>
<td><p><span data-ttu-id="9ee04-354">只读</span><span class="sxs-lookup"><span data-stu-id="9ee04-354">read-only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ee04-355"><a href="source-property-ado-recordset.md">Source</a></span><span class="sxs-lookup"><span data-stu-id="9ee04-355"><a href="source-property-ado-recordset.md">Source</a></span></span></p></td>
<td><p><span data-ttu-id="9ee04-356">读/写</span><span class="sxs-lookup"><span data-stu-id="9ee04-356">read/write</span></span></p></td>
<td><p><span data-ttu-id="9ee04-357">读/写</span><span class="sxs-lookup"><span data-stu-id="9ee04-357">read/write</span></span></p></td>
<td><p><span data-ttu-id="9ee04-358">读/写</span><span class="sxs-lookup"><span data-stu-id="9ee04-358">read/write</span></span></p></td>
<td><p><span data-ttu-id="9ee04-359">读/写</span><span class="sxs-lookup"><span data-stu-id="9ee04-359">read/write</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ee04-360"><a href="state-property-ado.md">State</a></span><span class="sxs-lookup"><span data-stu-id="9ee04-360"><a href="state-property-ado.md">State</a></span></span></p></td>
<td><p><span data-ttu-id="9ee04-361">只读</span><span class="sxs-lookup"><span data-stu-id="9ee04-361">read-only</span></span></p></td>
<td><p><span data-ttu-id="9ee04-362">只读</span><span class="sxs-lookup"><span data-stu-id="9ee04-362">read-only</span></span></p></td>
<td><p><span data-ttu-id="9ee04-363">只读</span><span class="sxs-lookup"><span data-stu-id="9ee04-363">read-only</span></span></p></td>
<td><p><span data-ttu-id="9ee04-364">只读</span><span class="sxs-lookup"><span data-stu-id="9ee04-364">read-only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ee04-365"><a href="status-property-ado-recordset.md">Status</a></span><span class="sxs-lookup"><span data-stu-id="9ee04-365"><a href="status-property-ado-recordset.md">Status</a></span></span></p></td>
<td><p><span data-ttu-id="9ee04-366">只读</span><span class="sxs-lookup"><span data-stu-id="9ee04-366">read-only</span></span></p></td>
<td><p><span data-ttu-id="9ee04-367">只读</span><span class="sxs-lookup"><span data-stu-id="9ee04-367">read-only</span></span></p></td>
<td><p><span data-ttu-id="9ee04-368">只读</span><span class="sxs-lookup"><span data-stu-id="9ee04-368">read-only</span></span></p></td>
<td><p><span data-ttu-id="9ee04-369">只读</span><span class="sxs-lookup"><span data-stu-id="9ee04-369">read-only</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="9ee04-370">在 1.0 版的 Microsoft OLE DB Provider for ODBC 中使用 ADO 时，[AbsolutePosition](absoluteposition-property-ado.md) 和 [AbsolutePage](absolutepage-property-ado.md) 属性是只写属性。</span><span class="sxs-lookup"><span data-stu-id="9ee04-370">The [AbsolutePosition](absoluteposition-property-ado.md) and [AbsolutePage](absolutepage-property-ado.md) properties are write-only when ADO is used with version 1.0 of the Microsoft OLE DB Provider for ODBC.</span></span>

<span data-ttu-id="9ee04-371">标准 ADO **Recordset** 方法的可用性：</span><span class="sxs-lookup"><span data-stu-id="9ee04-371">Availability of standard ADO **Recordset** methods:</span></span>

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="9ee04-372">方法</span><span class="sxs-lookup"><span data-stu-id="9ee04-372">Method</span></span></p></th>
<th><p><span data-ttu-id="9ee04-373">ForwardOnly</span><span class="sxs-lookup"><span data-stu-id="9ee04-373">ForwardOnly</span></span></p></th>
<th><p><span data-ttu-id="9ee04-374">动态</span><span class="sxs-lookup"><span data-stu-id="9ee04-374">Dynamic</span></span></p></th>
<th><p><span data-ttu-id="9ee04-375">键集</span><span class="sxs-lookup"><span data-stu-id="9ee04-375">Keyset</span></span></p></th>
<th><p><span data-ttu-id="9ee04-376">静态</span><span class="sxs-lookup"><span data-stu-id="9ee04-376">Static</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9ee04-377"><a href="addnew-method-ado.md">AddNew</a></span><span class="sxs-lookup"><span data-stu-id="9ee04-377"><a href="addnew-method-ado.md">AddNew</a></span></span></p></td>
<td><p><span data-ttu-id="9ee04-378">是</span><span class="sxs-lookup"><span data-stu-id="9ee04-378">Yes</span></span></p></td>
<td><p><span data-ttu-id="9ee04-379">是</span><span class="sxs-lookup"><span data-stu-id="9ee04-379">Yes</span></span></p></td>
<td><p><span data-ttu-id="9ee04-380">是</span><span class="sxs-lookup"><span data-stu-id="9ee04-380">Yes</span></span></p></td>
<td><p><span data-ttu-id="9ee04-381">是</span><span class="sxs-lookup"><span data-stu-id="9ee04-381">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ee04-382"><a href="cancel-method-ado.md">Cancel</a></span><span class="sxs-lookup"><span data-stu-id="9ee04-382"><a href="cancel-method-ado.md">Cancel</a></span></span></p></td>
<td><p><span data-ttu-id="9ee04-383">是</span><span class="sxs-lookup"><span data-stu-id="9ee04-383">Yes</span></span></p></td>
<td><p><span data-ttu-id="9ee04-384">是</span><span class="sxs-lookup"><span data-stu-id="9ee04-384">Yes</span></span></p></td>
<td><p><span data-ttu-id="9ee04-385">是</span><span class="sxs-lookup"><span data-stu-id="9ee04-385">Yes</span></span></p></td>
<td><p><span data-ttu-id="9ee04-386">是</span><span class="sxs-lookup"><span data-stu-id="9ee04-386">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ee04-387"><a href="cancelbatch-method-ado.md">CancelBatch</a></span><span class="sxs-lookup"><span data-stu-id="9ee04-387"><a href="cancelbatch-method-ado.md">CancelBatch</a></span></span></p></td>
<td><p><span data-ttu-id="9ee04-388">是</span><span class="sxs-lookup"><span data-stu-id="9ee04-388">Yes</span></span></p></td>
<td><p><span data-ttu-id="9ee04-389">是</span><span class="sxs-lookup"><span data-stu-id="9ee04-389">Yes</span></span></p></td>
<td><p><span data-ttu-id="9ee04-390">是</span><span class="sxs-lookup"><span data-stu-id="9ee04-390">Yes</span></span></p></td>
<td><p><span data-ttu-id="9ee04-391">是</span><span class="sxs-lookup"><span data-stu-id="9ee04-391">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ee04-392"><a href="cancelupdate-method-ado.md">CancelUpdate</a></span><span class="sxs-lookup"><span data-stu-id="9ee04-392"><a href="cancelupdate-method-ado.md">CancelUpdate</a></span></span></p></td>
<td><p><span data-ttu-id="9ee04-393">是</span><span class="sxs-lookup"><span data-stu-id="9ee04-393">Yes</span></span></p></td>
<td><p><span data-ttu-id="9ee04-394">是</span><span class="sxs-lookup"><span data-stu-id="9ee04-394">Yes</span></span></p></td>
<td><p><span data-ttu-id="9ee04-395">是</span><span class="sxs-lookup"><span data-stu-id="9ee04-395">Yes</span></span></p></td>
<td><p><span data-ttu-id="9ee04-396">是</span><span class="sxs-lookup"><span data-stu-id="9ee04-396">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ee04-397"><a href="clone-method-ado.md">Clone</a></span><span class="sxs-lookup"><span data-stu-id="9ee04-397"><a href="clone-method-ado.md">Clone</a></span></span></p></td>
<td><p><span data-ttu-id="9ee04-398">否</span><span class="sxs-lookup"><span data-stu-id="9ee04-398">No</span></span></p></td>
<td><p><span data-ttu-id="9ee04-399">否</span><span class="sxs-lookup"><span data-stu-id="9ee04-399">No</span></span></p></td>
<td><p><span data-ttu-id="9ee04-400">是</span><span class="sxs-lookup"><span data-stu-id="9ee04-400">Yes</span></span></p></td>
<td><p><span data-ttu-id="9ee04-401">是</span><span class="sxs-lookup"><span data-stu-id="9ee04-401">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ee04-402"><a href="close-method-ado.md">Close</a></span><span class="sxs-lookup"><span data-stu-id="9ee04-402"><a href="close-method-ado.md">Close</a></span></span></p></td>
<td><p><span data-ttu-id="9ee04-403">是</span><span class="sxs-lookup"><span data-stu-id="9ee04-403">Yes</span></span></p></td>
<td><p><span data-ttu-id="9ee04-404">是</span><span class="sxs-lookup"><span data-stu-id="9ee04-404">Yes</span></span></p></td>
<td><p><span data-ttu-id="9ee04-405">是</span><span class="sxs-lookup"><span data-stu-id="9ee04-405">Yes</span></span></p></td>
<td><p><span data-ttu-id="9ee04-406">是</span><span class="sxs-lookup"><span data-stu-id="9ee04-406">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ee04-407"><a href="delete-method-ado-recordset.md">Delete</a></span><span class="sxs-lookup"><span data-stu-id="9ee04-407"><a href="delete-method-ado-recordset.md">Delete</a></span></span></p></td>
<td><p><span data-ttu-id="9ee04-408">是</span><span class="sxs-lookup"><span data-stu-id="9ee04-408">Yes</span></span></p></td>
<td><p><span data-ttu-id="9ee04-409">是</span><span class="sxs-lookup"><span data-stu-id="9ee04-409">Yes</span></span></p></td>
<td><p><span data-ttu-id="9ee04-410">是</span><span class="sxs-lookup"><span data-stu-id="9ee04-410">Yes</span></span></p></td>
<td><p><span data-ttu-id="9ee04-411">是</span><span class="sxs-lookup"><span data-stu-id="9ee04-411">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ee04-412"><a href="getrows-method-ado.md">GetRows</a></span><span class="sxs-lookup"><span data-stu-id="9ee04-412"><a href="getrows-method-ado.md">GetRows</a></span></span></p></td>
<td><p><span data-ttu-id="9ee04-413">是</span><span class="sxs-lookup"><span data-stu-id="9ee04-413">Yes</span></span></p></td>
<td><p><span data-ttu-id="9ee04-414">是</span><span class="sxs-lookup"><span data-stu-id="9ee04-414">Yes</span></span></p></td>
<td><p><span data-ttu-id="9ee04-415">是</span><span class="sxs-lookup"><span data-stu-id="9ee04-415">Yes</span></span></p></td>
<td><p><span data-ttu-id="9ee04-416">是</span><span class="sxs-lookup"><span data-stu-id="9ee04-416">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ee04-417"><a href="move-method-ado.md">移动</a></span><span class="sxs-lookup"><span data-stu-id="9ee04-417"><a href="move-method-ado.md">Move</a></span></span></p></td>
<td><p><span data-ttu-id="9ee04-418">是</span><span class="sxs-lookup"><span data-stu-id="9ee04-418">Yes</span></span></p></td>
<td><p><span data-ttu-id="9ee04-419">是</span><span class="sxs-lookup"><span data-stu-id="9ee04-419">Yes</span></span></p></td>
<td><p><span data-ttu-id="9ee04-420">是</span><span class="sxs-lookup"><span data-stu-id="9ee04-420">Yes</span></span></p></td>
<td><p><span data-ttu-id="9ee04-421">是</span><span class="sxs-lookup"><span data-stu-id="9ee04-421">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ee04-422"><a href="movefirst-movelast-movenext-and-moveprevious-methods-ado.md">MoveFirst</a></span><span class="sxs-lookup"><span data-stu-id="9ee04-422"><a href="movefirst-movelast-movenext-and-moveprevious-methods-ado.md">MoveFirst</a></span></span></p></td>
<td><p><span data-ttu-id="9ee04-423">是</span><span class="sxs-lookup"><span data-stu-id="9ee04-423">Yes</span></span></p></td>
<td><p><span data-ttu-id="9ee04-424">是</span><span class="sxs-lookup"><span data-stu-id="9ee04-424">Yes</span></span></p></td>
<td><p><span data-ttu-id="9ee04-425">是</span><span class="sxs-lookup"><span data-stu-id="9ee04-425">Yes</span></span></p></td>
<td><p><span data-ttu-id="9ee04-426">是</span><span class="sxs-lookup"><span data-stu-id="9ee04-426">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ee04-427"><a href="movefirst-movelast-movenext-and-moveprevious-methods-ado.md">MoveLast</a></span><span class="sxs-lookup"><span data-stu-id="9ee04-427"><a href="movefirst-movelast-movenext-and-moveprevious-methods-ado.md">MoveLast</a></span></span></p></td>
<td><p><span data-ttu-id="9ee04-428">否</span><span class="sxs-lookup"><span data-stu-id="9ee04-428">No</span></span></p></td>
<td><p><span data-ttu-id="9ee04-429">是</span><span class="sxs-lookup"><span data-stu-id="9ee04-429">Yes</span></span></p></td>
<td><p><span data-ttu-id="9ee04-430">是</span><span class="sxs-lookup"><span data-stu-id="9ee04-430">Yes</span></span></p></td>
<td><p><span data-ttu-id="9ee04-431">是</span><span class="sxs-lookup"><span data-stu-id="9ee04-431">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ee04-432"><a href="movefirst-movelast-movenext-and-moveprevious-methods-ado.md">MoveNext</a></span><span class="sxs-lookup"><span data-stu-id="9ee04-432"><a href="movefirst-movelast-movenext-and-moveprevious-methods-ado.md">MoveNext</a></span></span></p></td>
<td><p><span data-ttu-id="9ee04-433">是</span><span class="sxs-lookup"><span data-stu-id="9ee04-433">Yes</span></span></p></td>
<td><p><span data-ttu-id="9ee04-434">是</span><span class="sxs-lookup"><span data-stu-id="9ee04-434">Yes</span></span></p></td>
<td><p><span data-ttu-id="9ee04-435">是</span><span class="sxs-lookup"><span data-stu-id="9ee04-435">Yes</span></span></p></td>
<td><p><span data-ttu-id="9ee04-436">是</span><span class="sxs-lookup"><span data-stu-id="9ee04-436">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ee04-437"><a href="movefirst-movelast-movenext-and-moveprevious-methods-ado.md">MovePrevious</a></span><span class="sxs-lookup"><span data-stu-id="9ee04-437"><a href="movefirst-movelast-movenext-and-moveprevious-methods-ado.md">MovePrevious</a></span></span></p></td>
<td><p><span data-ttu-id="9ee04-438">否</span><span class="sxs-lookup"><span data-stu-id="9ee04-438">No</span></span></p></td>
<td><p><span data-ttu-id="9ee04-439">是</span><span class="sxs-lookup"><span data-stu-id="9ee04-439">Yes</span></span></p></td>
<td><p><span data-ttu-id="9ee04-440">是</span><span class="sxs-lookup"><span data-stu-id="9ee04-440">Yes</span></span></p></td>
<td><p><span data-ttu-id="9ee04-441">是</span><span class="sxs-lookup"><span data-stu-id="9ee04-441">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ee04-442"><a href="nextrecordset-method-ado.md">NextRecordset</a>\*</span><span class="sxs-lookup"><span data-stu-id="9ee04-442"><a href="nextrecordset-method-ado.md">NextRecordset</a>\*</span></span></p></td>
<td><p><span data-ttu-id="9ee04-443">是</span><span class="sxs-lookup"><span data-stu-id="9ee04-443">Yes</span></span></p></td>
<td><p><span data-ttu-id="9ee04-444">是</span><span class="sxs-lookup"><span data-stu-id="9ee04-444">Yes</span></span></p></td>
<td><p><span data-ttu-id="9ee04-445">是</span><span class="sxs-lookup"><span data-stu-id="9ee04-445">Yes</span></span></p></td>
<td><p><span data-ttu-id="9ee04-446">是</span><span class="sxs-lookup"><span data-stu-id="9ee04-446">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ee04-447"><a href="open-method-ado-recordset.md">Open</a></span><span class="sxs-lookup"><span data-stu-id="9ee04-447"><a href="open-method-ado-recordset.md">Open</a></span></span></p></td>
<td><p><span data-ttu-id="9ee04-448">是</span><span class="sxs-lookup"><span data-stu-id="9ee04-448">Yes</span></span></p></td>
<td><p><span data-ttu-id="9ee04-449">是</span><span class="sxs-lookup"><span data-stu-id="9ee04-449">Yes</span></span></p></td>
<td><p><span data-ttu-id="9ee04-450">是</span><span class="sxs-lookup"><span data-stu-id="9ee04-450">Yes</span></span></p></td>
<td><p><span data-ttu-id="9ee04-451">是</span><span class="sxs-lookup"><span data-stu-id="9ee04-451">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ee04-452"><a href="requery-method-ado.md">Requery</a></span><span class="sxs-lookup"><span data-stu-id="9ee04-452"><a href="requery-method-ado.md">Requery</a></span></span></p></td>
<td><p><span data-ttu-id="9ee04-453">是</span><span class="sxs-lookup"><span data-stu-id="9ee04-453">Yes</span></span></p></td>
<td><p><span data-ttu-id="9ee04-454">是</span><span class="sxs-lookup"><span data-stu-id="9ee04-454">Yes</span></span></p></td>
<td><p><span data-ttu-id="9ee04-455">是</span><span class="sxs-lookup"><span data-stu-id="9ee04-455">Yes</span></span></p></td>
<td><p><span data-ttu-id="9ee04-456">是</span><span class="sxs-lookup"><span data-stu-id="9ee04-456">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ee04-457"><a href="resync-method-ado.md">Resync</a></span><span class="sxs-lookup"><span data-stu-id="9ee04-457"><a href="resync-method-ado.md">Resync</a></span></span></p></td>
<td><p><span data-ttu-id="9ee04-458">否</span><span class="sxs-lookup"><span data-stu-id="9ee04-458">No</span></span></p></td>
<td><p><span data-ttu-id="9ee04-459">否</span><span class="sxs-lookup"><span data-stu-id="9ee04-459">No</span></span></p></td>
<td><p><span data-ttu-id="9ee04-460">是</span><span class="sxs-lookup"><span data-stu-id="9ee04-460">Yes</span></span></p></td>
<td><p><span data-ttu-id="9ee04-461">是</span><span class="sxs-lookup"><span data-stu-id="9ee04-461">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ee04-462"><a href="supports-method-ado.md">支持</a></span><span class="sxs-lookup"><span data-stu-id="9ee04-462"><a href="supports-method-ado.md">Supports</a></span></span></p></td>
<td><p><span data-ttu-id="9ee04-463">是</span><span class="sxs-lookup"><span data-stu-id="9ee04-463">Yes</span></span></p></td>
<td><p><span data-ttu-id="9ee04-464">是</span><span class="sxs-lookup"><span data-stu-id="9ee04-464">Yes</span></span></p></td>
<td><p><span data-ttu-id="9ee04-465">是</span><span class="sxs-lookup"><span data-stu-id="9ee04-465">Yes</span></span></p></td>
<td><p><span data-ttu-id="9ee04-466">是</span><span class="sxs-lookup"><span data-stu-id="9ee04-466">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ee04-467"><a href="update-method-ado.md">更新</a></span><span class="sxs-lookup"><span data-stu-id="9ee04-467"><a href="update-method-ado.md">Update</a></span></span></p></td>
<td><p><span data-ttu-id="9ee04-468">是</span><span class="sxs-lookup"><span data-stu-id="9ee04-468">Yes</span></span></p></td>
<td><p><span data-ttu-id="9ee04-469">是</span><span class="sxs-lookup"><span data-stu-id="9ee04-469">Yes</span></span></p></td>
<td><p><span data-ttu-id="9ee04-470">是</span><span class="sxs-lookup"><span data-stu-id="9ee04-470">Yes</span></span></p></td>
<td><p><span data-ttu-id="9ee04-471">是</span><span class="sxs-lookup"><span data-stu-id="9ee04-471">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ee04-472"><a href="updatebatch-method-ado.md">UpdateBatch</a></span><span class="sxs-lookup"><span data-stu-id="9ee04-472"><a href="updatebatch-method-ado.md">UpdateBatch</a></span></span></p></td>
<td><p><span data-ttu-id="9ee04-473">是</span><span class="sxs-lookup"><span data-stu-id="9ee04-473">Yes</span></span></p></td>
<td><p><span data-ttu-id="9ee04-474">是</span><span class="sxs-lookup"><span data-stu-id="9ee04-474">Yes</span></span></p></td>
<td><p><span data-ttu-id="9ee04-475">是</span><span class="sxs-lookup"><span data-stu-id="9ee04-475">Yes</span></span></p></td>
<td><p><span data-ttu-id="9ee04-476">是</span><span class="sxs-lookup"><span data-stu-id="9ee04-476">Yes</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="9ee04-477">\*不受 Microsoft Access 数据库支持。</span><span class="sxs-lookup"><span data-stu-id="9ee04-477">\*Not supported for Microsoft Access databases.</span></span>

## <a name="dynamic-properties"></a><span data-ttu-id="9ee04-478">动态属性</span><span class="sxs-lookup"><span data-stu-id="9ee04-478">Dynamic Properties</span></span>

<span data-ttu-id="9ee04-479">Microsoft OLE DB Provider for ODBC 会将多个动态属性插入到未打开的 **Connection**、[Recordset](connection-object-ado.md) 和 [Command](recordset-object-ado.md) 对象的 [Properties](command-object-ado.md) 集合中。</span><span class="sxs-lookup"><span data-stu-id="9ee04-479">The Microsoft OLE DB Provider for ODBC inserts several dynamic properties into the **Properties** collection of the unopened [Connection](connection-object-ado.md), [Recordset](recordset-object-ado.md), and [Command](command-object-ado.md) objects.</span></span>

<span data-ttu-id="9ee04-p118">下面的表是每个动态属性的 ADO 和 OLE DB 名称的交叉索引。《OLE DB 程序员参考》使用术语"说明"来引用 ADO 属性名。您可以在《OLE DB 程序员参考》中找到有关这些属性的详细信息。请在"索引"中搜索 OLE DB 属性名，或者请参阅"附录 C：OLE DB 属性"。</span><span class="sxs-lookup"><span data-stu-id="9ee04-p118">The tables below are a cross-index of the ADO and OLE DB names for each dynamic property. The OLE DB Programmer's Reference refers to an ADO property name by the term, "Description." You can find more information about these properties in the OLE DB Programmer's Reference. Search for the OLE DB property name in the Index or see Appendix C: OLE DB Properties.</span></span>

## <a name="connection-dynamic-properties"></a><span data-ttu-id="9ee04-484">Connection 动态属性</span><span class="sxs-lookup"><span data-stu-id="9ee04-484">Connection Dynamic Properties</span></span>

<span data-ttu-id="9ee04-485">以下属性将被添加到 **Connection** 对象的 **Properties** 集合中。</span><span class="sxs-lookup"><span data-stu-id="9ee04-485">The following properties are added to the **Connection** object's **Properties** collection.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="9ee04-486">ADO 属性名</span><span class="sxs-lookup"><span data-stu-id="9ee04-486">ADO Property Name</span></span></p></th>
<th><p><span data-ttu-id="9ee04-487">OLE DB 属性名</span><span class="sxs-lookup"><span data-stu-id="9ee04-487">OLE DB Property Name</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9ee04-488">Active Sessions</span><span class="sxs-lookup"><span data-stu-id="9ee04-488">Active Sessions</span></span></p></td>
<td><p><span data-ttu-id="9ee04-489">DBPROP_ACTIVESESSIONS</span><span class="sxs-lookup"><span data-stu-id="9ee04-489">DBPROP_ACTIVESESSIONS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ee04-490">Asynchable Abort</span><span class="sxs-lookup"><span data-stu-id="9ee04-490">Asynchable Abort</span></span></p></td>
<td><p><span data-ttu-id="9ee04-491">DBPROP_ASYNCTXNABORT</span><span class="sxs-lookup"><span data-stu-id="9ee04-491">DBPROP_ASYNCTXNABORT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ee04-492">Asynchable Commit</span><span class="sxs-lookup"><span data-stu-id="9ee04-492">Asynchable Commit</span></span></p></td>
<td><p><span data-ttu-id="9ee04-493">DBPROP_ASYNCTNXCOMMIT</span><span class="sxs-lookup"><span data-stu-id="9ee04-493">DBPROP_ASYNCTNXCOMMIT</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ee04-494">Autocommit Isolation Levels</span><span class="sxs-lookup"><span data-stu-id="9ee04-494">Autocommit Isolation Levels</span></span></p></td>
<td><p><span data-ttu-id="9ee04-495">DBPROP_SESS_AUTOCOMMITISOLEVELS</span><span class="sxs-lookup"><span data-stu-id="9ee04-495">DBPROP_SESS_AUTOCOMMITISOLEVELS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ee04-496">Catalog Location</span><span class="sxs-lookup"><span data-stu-id="9ee04-496">Catalog Location</span></span></p></td>
<td><p><span data-ttu-id="9ee04-497">DBPROP_CATALOGLOCATION</span><span class="sxs-lookup"><span data-stu-id="9ee04-497">DBPROP_CATALOGLOCATION</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ee04-498">Catalog Term</span><span class="sxs-lookup"><span data-stu-id="9ee04-498">Catalog Term</span></span></p></td>
<td><p><span data-ttu-id="9ee04-499">DBPROP_CATALOGTERM</span><span class="sxs-lookup"><span data-stu-id="9ee04-499">DBPROP_CATALOGTERM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ee04-500">Column Definition</span><span class="sxs-lookup"><span data-stu-id="9ee04-500">Column Definition</span></span></p></td>
<td><p><span data-ttu-id="9ee04-501">DBPROP_COLUMNDEFINITION</span><span class="sxs-lookup"><span data-stu-id="9ee04-501">DBPROP_COLUMNDEFINITION</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ee04-502">Connect Timeout</span><span class="sxs-lookup"><span data-stu-id="9ee04-502">Connect Timeout</span></span></p></td>
<td><p><span data-ttu-id="9ee04-503">DBPROP_INIT_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="9ee04-503">DBPROP_INIT_TIMEOUT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ee04-504">Current Catalog</span><span class="sxs-lookup"><span data-stu-id="9ee04-504">Current Catalog</span></span></p></td>
<td><p><span data-ttu-id="9ee04-505">DBPROP_CURRENTCATALOG</span><span class="sxs-lookup"><span data-stu-id="9ee04-505">DBPROP_CURRENTCATALOG</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ee04-506">Data Source</span><span class="sxs-lookup"><span data-stu-id="9ee04-506">Data Source</span></span></p></td>
<td><p><span data-ttu-id="9ee04-507">DBPROP_INIT_DATASOURCE</span><span class="sxs-lookup"><span data-stu-id="9ee04-507">DBPROP_INIT_DATASOURCE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ee04-508">Data Source Name</span><span class="sxs-lookup"><span data-stu-id="9ee04-508">Data Source Name</span></span></p></td>
<td><p><span data-ttu-id="9ee04-509">DBPROP_DATASOURCENAME</span><span class="sxs-lookup"><span data-stu-id="9ee04-509">DBPROP_DATASOURCENAME</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ee04-510">Data Source Object Threading Model</span><span class="sxs-lookup"><span data-stu-id="9ee04-510">Data Source Object Threading Model</span></span></p></td>
<td><p><span data-ttu-id="9ee04-511">DBPROP_DSOTHREADMODEL</span><span class="sxs-lookup"><span data-stu-id="9ee04-511">DBPROP_DSOTHREADMODEL</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ee04-512">DBMS Name</span><span class="sxs-lookup"><span data-stu-id="9ee04-512">DBMS Name</span></span></p></td>
<td><p><span data-ttu-id="9ee04-513">DBPROP_DBMSNAME</span><span class="sxs-lookup"><span data-stu-id="9ee04-513">DBPROP_DBMSNAME</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ee04-514">DBMS Version</span><span class="sxs-lookup"><span data-stu-id="9ee04-514">DBMS Version</span></span></p></td>
<td><p><span data-ttu-id="9ee04-515">DBPROP_DBMSVER</span><span class="sxs-lookup"><span data-stu-id="9ee04-515">DBPROP_DBMSVER</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ee04-516">Extended Properties</span><span class="sxs-lookup"><span data-stu-id="9ee04-516">Extended Properties</span></span></p></td>
<td><p><span data-ttu-id="9ee04-517">DBPROP_INIT_PROVIDERSTRING</span><span class="sxs-lookup"><span data-stu-id="9ee04-517">DBPROP_INIT_PROVIDERSTRING</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ee04-518">GROUP BY Support</span><span class="sxs-lookup"><span data-stu-id="9ee04-518">GROUP BY Support</span></span></p></td>
<td><p><span data-ttu-id="9ee04-519">DBPROP_GROUPBY</span><span class="sxs-lookup"><span data-stu-id="9ee04-519">DBPROP_GROUPBY</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ee04-520">Heterogeneous Table Support</span><span class="sxs-lookup"><span data-stu-id="9ee04-520">Heterogeneous Table Support</span></span></p></td>
<td><p><span data-ttu-id="9ee04-521">DBPROP_HETEROGENEOUSTABLES</span><span class="sxs-lookup"><span data-stu-id="9ee04-521">DBPROP_HETEROGENEOUSTABLES</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ee04-522">Identifier Case Sensitivity</span><span class="sxs-lookup"><span data-stu-id="9ee04-522">Identifier Case Sensitivity</span></span></p></td>
<td><p><span data-ttu-id="9ee04-523">DBPROP_IDENTIFIERCASE</span><span class="sxs-lookup"><span data-stu-id="9ee04-523">DBPROP_IDENTIFIERCASE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ee04-524">Initial Catalog</span><span class="sxs-lookup"><span data-stu-id="9ee04-524">Initial Catalog</span></span></p></td>
<td><p><span data-ttu-id="9ee04-525">DBPROP_INIT_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9ee04-525">DBPROP_INIT_CATALOG</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ee04-526">Isolation Levels</span><span class="sxs-lookup"><span data-stu-id="9ee04-526">Isolation Levels</span></span></p></td>
<td><p><span data-ttu-id="9ee04-527">DBPROP_SUPPORTEDTXNISOLEVELS</span><span class="sxs-lookup"><span data-stu-id="9ee04-527">DBPROP_SUPPORTEDTXNISOLEVELS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ee04-528">Isolation Retention</span><span class="sxs-lookup"><span data-stu-id="9ee04-528">Isolation Retention</span></span></p></td>
<td><p><span data-ttu-id="9ee04-529">DBPROP_SUPPORTEDTXNISORETAIN</span><span class="sxs-lookup"><span data-stu-id="9ee04-529">DBPROP_SUPPORTEDTXNISORETAIN</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ee04-530">Locale Identifier</span><span class="sxs-lookup"><span data-stu-id="9ee04-530">Locale Identifier</span></span></p></td>
<td><p><span data-ttu-id="9ee04-531">DBPROP_INIT_LCID</span><span class="sxs-lookup"><span data-stu-id="9ee04-531">DBPROP_INIT_LCID</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ee04-532">Location</span><span class="sxs-lookup"><span data-stu-id="9ee04-532">Location</span></span></p></td>
<td><p><span data-ttu-id="9ee04-533">DBPROP_INIT_LOCATION</span><span class="sxs-lookup"><span data-stu-id="9ee04-533">DBPROP_INIT_LOCATION</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ee04-534">Maximum Index Size</span><span class="sxs-lookup"><span data-stu-id="9ee04-534">Maximum Index Size</span></span></p></td>
<td><p><span data-ttu-id="9ee04-535">DBPROP_MAXINDEXSIZE</span><span class="sxs-lookup"><span data-stu-id="9ee04-535">DBPROP_MAXINDEXSIZE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ee04-536">Maximum Row Size</span><span class="sxs-lookup"><span data-stu-id="9ee04-536">Maximum Row Size</span></span></p></td>
<td><p><span data-ttu-id="9ee04-537">DBPROP_MAXROWSIZE</span><span class="sxs-lookup"><span data-stu-id="9ee04-537">DBPROP_MAXROWSIZE</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ee04-538">Maximum Row Size Includes BLOB</span><span class="sxs-lookup"><span data-stu-id="9ee04-538">Maximum Row Size Includes BLOB</span></span></p></td>
<td><p><span data-ttu-id="9ee04-539">DBPROP_MAXROWSIZEINCLUDESBLOB</span><span class="sxs-lookup"><span data-stu-id="9ee04-539">DBPROP_MAXROWSIZEINCLUDESBLOB</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ee04-540">Maximum Tables in SELECT</span><span class="sxs-lookup"><span data-stu-id="9ee04-540">Maximum Tables in SELECT</span></span></p></td>
<td><p><span data-ttu-id="9ee04-541">DBPROP_MAXTABLESINSELECT</span><span class="sxs-lookup"><span data-stu-id="9ee04-541">DBPROP_MAXTABLESINSELECT</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ee04-542">Mode</span><span class="sxs-lookup"><span data-stu-id="9ee04-542">Mode</span></span></p></td>
<td><p><span data-ttu-id="9ee04-543">DBPROP_INIT_MODE</span><span class="sxs-lookup"><span data-stu-id="9ee04-543">DBPROP_INIT_MODE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ee04-544">Multiple Parameter Sets</span><span class="sxs-lookup"><span data-stu-id="9ee04-544">Multiple Parameter Sets</span></span></p></td>
<td><p><span data-ttu-id="9ee04-545">DBPROP_MULTIPLEPARAMSETS</span><span class="sxs-lookup"><span data-stu-id="9ee04-545">DBPROP_MULTIPLEPARAMSETS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ee04-546">Multiple Results</span><span class="sxs-lookup"><span data-stu-id="9ee04-546">Multiple Results</span></span></p></td>
<td><p><span data-ttu-id="9ee04-547">DBPROP_MULTIPLERESULTS</span><span class="sxs-lookup"><span data-stu-id="9ee04-547">DBPROP_MULTIPLERESULTS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ee04-548">Multiple Storage Objects</span><span class="sxs-lookup"><span data-stu-id="9ee04-548">Multiple Storage Objects</span></span></p></td>
<td><p><span data-ttu-id="9ee04-549">DBPROP_MULTIPLESTORAGEOBJECTS</span><span class="sxs-lookup"><span data-stu-id="9ee04-549">DBPROP_MULTIPLESTORAGEOBJECTS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ee04-550">Multi-Table Update</span><span class="sxs-lookup"><span data-stu-id="9ee04-550">Multi-Table Update</span></span></p></td>
<td><p><span data-ttu-id="9ee04-551">DBPROP_MULTITABLEUPDATE</span><span class="sxs-lookup"><span data-stu-id="9ee04-551">DBPROP_MULTITABLEUPDATE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ee04-552">NULL Collation Order</span><span class="sxs-lookup"><span data-stu-id="9ee04-552">NULL Collation Order</span></span></p></td>
<td><p><span data-ttu-id="9ee04-553">DBPROP_NULLCOLLATION</span><span class="sxs-lookup"><span data-stu-id="9ee04-553">DBPROP_NULLCOLLATION</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ee04-554">NULL Concatenation Behavior</span><span class="sxs-lookup"><span data-stu-id="9ee04-554">NULL Concatenation Behavior</span></span></p></td>
<td><p><span data-ttu-id="9ee04-555">DBPROP_CONCATNULLBEHAVIOR</span><span class="sxs-lookup"><span data-stu-id="9ee04-555">DBPROP_CONCATNULLBEHAVIOR</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ee04-556">OLE DB Services</span><span class="sxs-lookup"><span data-stu-id="9ee04-556">OLE DB Services</span></span></p></td>
<td><p><span data-ttu-id="9ee04-557">DBPROP_INIT_OLEDBSERVICES</span><span class="sxs-lookup"><span data-stu-id="9ee04-557">DBPROP_INIT_OLEDBSERVICES</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ee04-558">OLE DB Version</span><span class="sxs-lookup"><span data-stu-id="9ee04-558">OLE DB Version</span></span></p></td>
<td><p><span data-ttu-id="9ee04-559">DBPROP_PROVIDEROLEDBVER</span><span class="sxs-lookup"><span data-stu-id="9ee04-559">DBPROP_PROVIDEROLEDBVER</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ee04-560">OLE Object Support</span><span class="sxs-lookup"><span data-stu-id="9ee04-560">OLE Object Support</span></span></p></td>
<td><p><span data-ttu-id="9ee04-561">DBPROP_OLEOBJECTS</span><span class="sxs-lookup"><span data-stu-id="9ee04-561">DBPROP_OLEOBJECTS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ee04-562">Open Rowset Support</span><span class="sxs-lookup"><span data-stu-id="9ee04-562">Open Rowset Support</span></span></p></td>
<td><p><span data-ttu-id="9ee04-563">DBPROP_OPENROWSETSUPPORT</span><span class="sxs-lookup"><span data-stu-id="9ee04-563">DBPROP_OPENROWSETSUPPORT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ee04-564">ORDER BY Columns in Select List</span><span class="sxs-lookup"><span data-stu-id="9ee04-564">ORDER BY Columns in Select List</span></span></p></td>
<td><p><span data-ttu-id="9ee04-565">DBPROP_ORDERBYCOLUMNSINSELECT</span><span class="sxs-lookup"><span data-stu-id="9ee04-565">DBPROP_ORDERBYCOLUMNSINSELECT</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ee04-566">Output Parameter Availability</span><span class="sxs-lookup"><span data-stu-id="9ee04-566">Output Parameter Availability</span></span></p></td>
<td><p><span data-ttu-id="9ee04-567">DBPROP_OUTPUTPARAMETERAVAILABILITY</span><span class="sxs-lookup"><span data-stu-id="9ee04-567">DBPROP_OUTPUTPARAMETERAVAILABILITY</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ee04-568">Password</span><span class="sxs-lookup"><span data-stu-id="9ee04-568">Password</span></span></p></td>
<td><p><span data-ttu-id="9ee04-569">DBPROP_AUTH_PASSWORD</span><span class="sxs-lookup"><span data-stu-id="9ee04-569">DBPROP_AUTH_PASSWORD</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ee04-570">Pass By Ref Accessors</span><span class="sxs-lookup"><span data-stu-id="9ee04-570">Pass By Ref Accessors</span></span></p></td>
<td><p><span data-ttu-id="9ee04-571">DBPROP_BYREFACCESSORS</span><span class="sxs-lookup"><span data-stu-id="9ee04-571">DBPROP_BYREFACCESSORS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ee04-572">Persist Security Info</span><span class="sxs-lookup"><span data-stu-id="9ee04-572">Persist Security Info</span></span></p></td>
<td><p><span data-ttu-id="9ee04-573">DBPROP_AUTH_PERSIST_SENSITIVE_AUTHINFO</span><span class="sxs-lookup"><span data-stu-id="9ee04-573">DBPROP_AUTH_PERSIST_SENSITIVE_AUTHINFO</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ee04-574">Persistent ID Type</span><span class="sxs-lookup"><span data-stu-id="9ee04-574">Persistent ID Type</span></span></p></td>
<td><p><span data-ttu-id="9ee04-575">DBPROP_PERSISTENTIDTYPE</span><span class="sxs-lookup"><span data-stu-id="9ee04-575">DBPROP_PERSISTENTIDTYPE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ee04-576">Prepare Abort Behavior</span><span class="sxs-lookup"><span data-stu-id="9ee04-576">Prepare Abort Behavior</span></span></p></td>
<td><p><span data-ttu-id="9ee04-577">DBPROP_PREPAREABORTBEHAVIOR</span><span class="sxs-lookup"><span data-stu-id="9ee04-577">DBPROP_PREPAREABORTBEHAVIOR</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ee04-578">Prepare Commit Behavior</span><span class="sxs-lookup"><span data-stu-id="9ee04-578">Prepare Commit Behavior</span></span></p></td>
<td><p><span data-ttu-id="9ee04-579">DBPROP_PREPARECOMMITBEHAVIOR</span><span class="sxs-lookup"><span data-stu-id="9ee04-579">DBPROP_PREPARECOMMITBEHAVIOR</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ee04-580">Procedure Term</span><span class="sxs-lookup"><span data-stu-id="9ee04-580">Procedure Term</span></span></p></td>
<td><p><span data-ttu-id="9ee04-581">DBPROP_PROCEDURETERM</span><span class="sxs-lookup"><span data-stu-id="9ee04-581">DBPROP_PROCEDURETERM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ee04-582">Prompt</span><span class="sxs-lookup"><span data-stu-id="9ee04-582">Prompt</span></span></p></td>
<td><p><span data-ttu-id="9ee04-583">DBPROP_INIT_PROMPT</span><span class="sxs-lookup"><span data-stu-id="9ee04-583">DBPROP_INIT_PROMPT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ee04-584">Provider Friendly Name</span><span class="sxs-lookup"><span data-stu-id="9ee04-584">Provider Friendly Name</span></span></p></td>
<td><p><span data-ttu-id="9ee04-585">DBPROP_PROVIDERFRIENDLYNAME</span><span class="sxs-lookup"><span data-stu-id="9ee04-585">DBPROP_PROVIDERFRIENDLYNAME</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ee04-586">Provider Name</span><span class="sxs-lookup"><span data-stu-id="9ee04-586">Provider Name</span></span></p></td>
<td><p><span data-ttu-id="9ee04-587">DBPROP_PROVIDERFILENAME</span><span class="sxs-lookup"><span data-stu-id="9ee04-587">DBPROP_PROVIDERFILENAME</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ee04-588">Provider Version</span><span class="sxs-lookup"><span data-stu-id="9ee04-588">Provider Version</span></span></p></td>
<td><p><span data-ttu-id="9ee04-589">DBPROP_PROVIDERVER</span><span class="sxs-lookup"><span data-stu-id="9ee04-589">DBPROP_PROVIDERVER</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ee04-590">Read-Only Data Source</span><span class="sxs-lookup"><span data-stu-id="9ee04-590">Read-Only Data Source</span></span></p></td>
<td><p><span data-ttu-id="9ee04-591">DBPROP_DATASOURCEREADONLY</span><span class="sxs-lookup"><span data-stu-id="9ee04-591">DBPROP_DATASOURCEREADONLY</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ee04-592">Rowset Conversions on Command</span><span class="sxs-lookup"><span data-stu-id="9ee04-592">Rowset Conversions on Command</span></span></p></td>
<td><p><span data-ttu-id="9ee04-593">DBPROP_ROWSETCONVERSIONSONCOMMAND</span><span class="sxs-lookup"><span data-stu-id="9ee04-593">DBPROP_ROWSETCONVERSIONSONCOMMAND</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ee04-594">Schema Term</span><span class="sxs-lookup"><span data-stu-id="9ee04-594">Schema Term</span></span></p></td>
<td><p><span data-ttu-id="9ee04-595">DBPROP_SCHEMATERM</span><span class="sxs-lookup"><span data-stu-id="9ee04-595">DBPROP_SCHEMATERM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ee04-596">Schema Usage</span><span class="sxs-lookup"><span data-stu-id="9ee04-596">Schema Usage</span></span></p></td>
<td><p><span data-ttu-id="9ee04-597">DBPROP_SCHEMAUSAGE</span><span class="sxs-lookup"><span data-stu-id="9ee04-597">DBPROP_SCHEMAUSAGE</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ee04-598">SQL Support</span><span class="sxs-lookup"><span data-stu-id="9ee04-598">SQL Support</span></span></p></td>
<td><p><span data-ttu-id="9ee04-599">DBPROP_SQLSUPPORT</span><span class="sxs-lookup"><span data-stu-id="9ee04-599">DBPROP_SQLSUPPORT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ee04-600">Structured Storage</span><span class="sxs-lookup"><span data-stu-id="9ee04-600">Structured Storage</span></span></p></td>
<td><p><span data-ttu-id="9ee04-601">DBPROP_STRUCTUREDSTORAGE</span><span class="sxs-lookup"><span data-stu-id="9ee04-601">DBPROP_STRUCTUREDSTORAGE</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ee04-602">Subquery Support</span><span class="sxs-lookup"><span data-stu-id="9ee04-602">Subquery Support</span></span></p></td>
<td><p><span data-ttu-id="9ee04-603">DBPROP_SUBQUERIES</span><span class="sxs-lookup"><span data-stu-id="9ee04-603">DBPROP_SUBQUERIES</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ee04-604">Table Term</span><span class="sxs-lookup"><span data-stu-id="9ee04-604">Table Term</span></span></p></td>
<td><p><span data-ttu-id="9ee04-605">DBPROP_TABLETERM</span><span class="sxs-lookup"><span data-stu-id="9ee04-605">DBPROP_TABLETERM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ee04-606">Transaction DDL</span><span class="sxs-lookup"><span data-stu-id="9ee04-606">Transaction DDL</span></span></p></td>
<td><p><span data-ttu-id="9ee04-607">DBPROP_SUPPORTEDTXNDDL</span><span class="sxs-lookup"><span data-stu-id="9ee04-607">DBPROP_SUPPORTEDTXNDDL</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ee04-608">User ID</span><span class="sxs-lookup"><span data-stu-id="9ee04-608">User ID</span></span></p></td>
<td><p><span data-ttu-id="9ee04-609">DBPROP_AUTH_USERID</span><span class="sxs-lookup"><span data-stu-id="9ee04-609">DBPROP_AUTH_USERID</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ee04-610">User Name</span><span class="sxs-lookup"><span data-stu-id="9ee04-610">User Name</span></span></p></td>
<td><p><span data-ttu-id="9ee04-611">DBPROP_USERNAME</span><span class="sxs-lookup"><span data-stu-id="9ee04-611">DBPROP_USERNAME</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ee04-612">Window Handle</span><span class="sxs-lookup"><span data-stu-id="9ee04-612">Window Handle</span></span></p></td>
<td><p><span data-ttu-id="9ee04-613">DBPROP_INIT_HWND</span><span class="sxs-lookup"><span data-stu-id="9ee04-613">DBPROP_INIT_HWND</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="recordset-dynamic-properties"></a><span data-ttu-id="9ee04-614">Recordset 动态属性</span><span class="sxs-lookup"><span data-stu-id="9ee04-614">Recordset Dynamic Properties</span></span>

<span data-ttu-id="9ee04-615">以下属性将被添加到 **Recordset** 对象的 **Properties** 集合中。</span><span class="sxs-lookup"><span data-stu-id="9ee04-615">The following properties are added to the **Recordset** object's **Properties** collection.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="9ee04-616">ADO 属性名</span><span class="sxs-lookup"><span data-stu-id="9ee04-616">ADO Property Name</span></span></p></th>
<th><p><span data-ttu-id="9ee04-617">OLE DB 属性名</span><span class="sxs-lookup"><span data-stu-id="9ee04-617">OLE DB Property Name</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9ee04-618">Access Order</span><span class="sxs-lookup"><span data-stu-id="9ee04-618">Access Order</span></span></p></td>
<td><p><span data-ttu-id="9ee04-619">DBPROP_ACCESSORDER</span><span class="sxs-lookup"><span data-stu-id="9ee04-619">DBPROP_ACCESSORDER</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ee04-620">Blocking Storage Objects</span><span class="sxs-lookup"><span data-stu-id="9ee04-620">Blocking Storage Objects</span></span></p></td>
<td><p><span data-ttu-id="9ee04-621">DBPROP_BLOCKINGSTORAGEOBJECTS</span><span class="sxs-lookup"><span data-stu-id="9ee04-621">DBPROP_BLOCKINGSTORAGEOBJECTS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ee04-622">Bookmark Type</span><span class="sxs-lookup"><span data-stu-id="9ee04-622">Bookmark Type</span></span></p></td>
<td><p><span data-ttu-id="9ee04-623">DBPROP_BOOKMARKTYPE</span><span class="sxs-lookup"><span data-stu-id="9ee04-623">DBPROP_BOOKMARKTYPE</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ee04-624">Bookmarkable</span><span class="sxs-lookup"><span data-stu-id="9ee04-624">Bookmarkable</span></span></p></td>
<td><p><span data-ttu-id="9ee04-625">DBPROP_IROWSETLOCATE</span><span class="sxs-lookup"><span data-stu-id="9ee04-625">DBPROP_IROWSETLOCATE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ee04-626">Change Inserted Rows</span><span class="sxs-lookup"><span data-stu-id="9ee04-626">Change Inserted Rows</span></span></p></td>
<td><p><span data-ttu-id="9ee04-627">DBPROP_CHANGEINSERTEDROWS</span><span class="sxs-lookup"><span data-stu-id="9ee04-627">DBPROP_CHANGEINSERTEDROWS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ee04-628">Column Privileges</span><span class="sxs-lookup"><span data-stu-id="9ee04-628">Column Privileges</span></span></p></td>
<td><p><span data-ttu-id="9ee04-629">DBPROP_COLUMNRESTRICT</span><span class="sxs-lookup"><span data-stu-id="9ee04-629">DBPROP_COLUMNRESTRICT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ee04-630">Column Set Notification</span><span class="sxs-lookup"><span data-stu-id="9ee04-630">Column Set Notification</span></span></p></td>
<td><p><span data-ttu-id="9ee04-631">DBPROP_NOTIFYCOLUMNSET</span><span class="sxs-lookup"><span data-stu-id="9ee04-631">DBPROP_NOTIFYCOLUMNSET</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ee04-632">Delay Storage Object Updates</span><span class="sxs-lookup"><span data-stu-id="9ee04-632">Delay Storage Object Updates</span></span></p></td>
<td><p><span data-ttu-id="9ee04-633">DBPROP_DELAYSTORAGEOBJECTS</span><span class="sxs-lookup"><span data-stu-id="9ee04-633">DBPROP_DELAYSTORAGEOBJECTS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ee04-634">Fetch Backwards</span><span class="sxs-lookup"><span data-stu-id="9ee04-634">Fetch Backwards</span></span></p></td>
<td><p><span data-ttu-id="9ee04-635">DBPROP_CANFETCHBACKWARDS</span><span class="sxs-lookup"><span data-stu-id="9ee04-635">DBPROP_CANFETCHBACKWARDS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ee04-636">Hold Rows</span><span class="sxs-lookup"><span data-stu-id="9ee04-636">Hold Rows</span></span></p></td>
<td><p><span data-ttu-id="9ee04-637">DBPROP_CANHOLDROWS</span><span class="sxs-lookup"><span data-stu-id="9ee04-637">DBPROP_CANHOLDROWS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ee04-638">IAccessor</span><span class="sxs-lookup"><span data-stu-id="9ee04-638">IAccessor</span></span></p></td>
<td><p><span data-ttu-id="9ee04-639">DBPROP_IAccessor</span><span class="sxs-lookup"><span data-stu-id="9ee04-639">DBPROP_IAccessor</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ee04-640">IColumnsInfo</span><span class="sxs-lookup"><span data-stu-id="9ee04-640">IColumnsInfo</span></span></p></td>
<td><p><span data-ttu-id="9ee04-641">DBPROP_IColumnsInfo</span><span class="sxs-lookup"><span data-stu-id="9ee04-641">DBPROP_IColumnsInfo</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ee04-642">IColumnsRowset</span><span class="sxs-lookup"><span data-stu-id="9ee04-642">IColumnsRowset</span></span></p></td>
<td><p><span data-ttu-id="9ee04-643">DBPROP_IColumnsRowset</span><span class="sxs-lookup"><span data-stu-id="9ee04-643">DBPROP_IColumnsRowset</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ee04-644">IConnectionPointContainer</span><span class="sxs-lookup"><span data-stu-id="9ee04-644">IConnectionPointContainer</span></span></p></td>
<td><p><span data-ttu-id="9ee04-645">DBPROP_IConnectionPointContainer</span><span class="sxs-lookup"><span data-stu-id="9ee04-645">DBPROP_IConnectionPointContainer</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ee04-646">IConvertType</span><span class="sxs-lookup"><span data-stu-id="9ee04-646">IConvertType</span></span></p></td>
<td><p><span data-ttu-id="9ee04-647">DBPROP_IConvertType</span><span class="sxs-lookup"><span data-stu-id="9ee04-647">DBPROP_IConvertType</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ee04-648">Immobile Rows</span><span class="sxs-lookup"><span data-stu-id="9ee04-648">Immobile Rows</span></span></p></td>
<td><p><span data-ttu-id="9ee04-649">DBPROP_IMMOBILEROWS</span><span class="sxs-lookup"><span data-stu-id="9ee04-649">DBPROP_IMMOBILEROWS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ee04-650">IRowset</span><span class="sxs-lookup"><span data-stu-id="9ee04-650">IRowset</span></span></p></td>
<td><p><span data-ttu-id="9ee04-651">DBPROP_IRowset</span><span class="sxs-lookup"><span data-stu-id="9ee04-651">DBPROP_IRowset</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ee04-652">IRowsetChange</span><span class="sxs-lookup"><span data-stu-id="9ee04-652">IRowsetChange</span></span></p></td>
<td><p><span data-ttu-id="9ee04-653">DBPROP_IRowsetChange</span><span class="sxs-lookup"><span data-stu-id="9ee04-653">DBPROP_IRowsetChange</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ee04-654">IRowsetIdentity</span><span class="sxs-lookup"><span data-stu-id="9ee04-654">IRowsetIdentity</span></span></p></td>
<td><p><span data-ttu-id="9ee04-655">DBPROP_IRowsetIdentity</span><span class="sxs-lookup"><span data-stu-id="9ee04-655">DBPROP_IRowsetIdentity</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ee04-656">IRowsetInfo</span><span class="sxs-lookup"><span data-stu-id="9ee04-656">IRowsetInfo</span></span></p></td>
<td><p><span data-ttu-id="9ee04-657">DBPROP_IRowsetInfo</span><span class="sxs-lookup"><span data-stu-id="9ee04-657">DBPROP_IRowsetInfo</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ee04-658">IRowsetLocate</span><span class="sxs-lookup"><span data-stu-id="9ee04-658">IRowsetLocate</span></span></p></td>
<td><p><span data-ttu-id="9ee04-659">DBPROP_IRowsetLocate</span><span class="sxs-lookup"><span data-stu-id="9ee04-659">DBPROP_IRowsetLocate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ee04-660">IRowsetResynch</span><span class="sxs-lookup"><span data-stu-id="9ee04-660">IRowsetResynch</span></span></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ee04-661">IRowsetUpdate</span><span class="sxs-lookup"><span data-stu-id="9ee04-661">IRowsetUpdate</span></span></p></td>
<td><p><span data-ttu-id="9ee04-662">DBPROP_IRowsetUpdate</span><span class="sxs-lookup"><span data-stu-id="9ee04-662">DBPROP_IRowsetUpdate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ee04-663">ISequentialStream</span><span class="sxs-lookup"><span data-stu-id="9ee04-663">ISequentialStream</span></span></p></td>
<td><p><span data-ttu-id="9ee04-664">DBPROP_ISequentialStream</span><span class="sxs-lookup"><span data-stu-id="9ee04-664">DBPROP_ISequentialStream</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ee04-665">ISupportErrorInfo</span><span class="sxs-lookup"><span data-stu-id="9ee04-665">ISupportErrorInfo</span></span></p></td>
<td><p><span data-ttu-id="9ee04-666">DBPROP_ISupportErrorInfo</span><span class="sxs-lookup"><span data-stu-id="9ee04-666">DBPROP_ISupportErrorInfo</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ee04-667">Literal Bookmarks</span><span class="sxs-lookup"><span data-stu-id="9ee04-667">Literal Bookmarks</span></span></p></td>
<td><p><span data-ttu-id="9ee04-668">DBPROP_LITERALBOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="9ee04-668">DBPROP_LITERALBOOKMARKS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ee04-669">Literal Row Identity</span><span class="sxs-lookup"><span data-stu-id="9ee04-669">Literal Row Identity</span></span></p></td>
<td><p><span data-ttu-id="9ee04-670">DBPROP_LITERALIDENTITY</span><span class="sxs-lookup"><span data-stu-id="9ee04-670">DBPROP_LITERALIDENTITY</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ee04-671">Maximum Open Rows</span><span class="sxs-lookup"><span data-stu-id="9ee04-671">Maximum Open Rows</span></span></p></td>
<td><p><span data-ttu-id="9ee04-672">DBPROP_MAXOPENROWS</span><span class="sxs-lookup"><span data-stu-id="9ee04-672">DBPROP_MAXOPENROWS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ee04-673">Maximum Pending Rows</span><span class="sxs-lookup"><span data-stu-id="9ee04-673">Maximum Pending Rows</span></span></p></td>
<td><p><span data-ttu-id="9ee04-674">DBPROP_MAXPENDINGROWS</span><span class="sxs-lookup"><span data-stu-id="9ee04-674">DBPROP_MAXPENDINGROWS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ee04-675">Maximum Rows</span><span class="sxs-lookup"><span data-stu-id="9ee04-675">Maximum Rows</span></span></p></td>
<td><p><span data-ttu-id="9ee04-676">DBPROP_MAXROWS</span><span class="sxs-lookup"><span data-stu-id="9ee04-676">DBPROP_MAXROWS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ee04-677">Notification Granularity</span><span class="sxs-lookup"><span data-stu-id="9ee04-677">Notification Granularity</span></span></p></td>
<td><p><span data-ttu-id="9ee04-678">DBPROP_NOTIFICATIONGRANULARITY</span><span class="sxs-lookup"><span data-stu-id="9ee04-678">DBPROP_NOTIFICATIONGRANULARITY</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ee04-679">Notification Phases</span><span class="sxs-lookup"><span data-stu-id="9ee04-679">Notification Phases</span></span></p></td>
<td><p><span data-ttu-id="9ee04-680">DBPROP_NOTIFICATIONPHASES</span><span class="sxs-lookup"><span data-stu-id="9ee04-680">DBPROP_NOTIFICATIONPHASES</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ee04-681">Objects Transacted</span><span class="sxs-lookup"><span data-stu-id="9ee04-681">Objects Transacted</span></span></p></td>
<td><p><span data-ttu-id="9ee04-682">DBPROP_TRANSACTEDOBJECT</span><span class="sxs-lookup"><span data-stu-id="9ee04-682">DBPROP_TRANSACTEDOBJECT</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ee04-683">Own Changes Visible</span><span class="sxs-lookup"><span data-stu-id="9ee04-683">Own Changes Visible</span></span></p></td>
<td><p><span data-ttu-id="9ee04-684">DBPROP_OWNUPDATEDELETE</span><span class="sxs-lookup"><span data-stu-id="9ee04-684">DBPROP_OWNUPDATEDELETE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ee04-685">Own Inserts Visible</span><span class="sxs-lookup"><span data-stu-id="9ee04-685">Own Inserts Visible</span></span></p></td>
<td><p><span data-ttu-id="9ee04-686">DBPROP_OWNINSERT</span><span class="sxs-lookup"><span data-stu-id="9ee04-686">DBPROP_OWNINSERT</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ee04-687">Preserve on Abort</span><span class="sxs-lookup"><span data-stu-id="9ee04-687">Preserve on Abort</span></span></p></td>
<td><p><span data-ttu-id="9ee04-688">DBPROP_ABORTPRESERVE</span><span class="sxs-lookup"><span data-stu-id="9ee04-688">DBPROP_ABORTPRESERVE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ee04-689">Preserve on Commit</span><span class="sxs-lookup"><span data-stu-id="9ee04-689">Preserve on Commit</span></span></p></td>
<td><p><span data-ttu-id="9ee04-690">DBPROP_COMMITPRESERVE</span><span class="sxs-lookup"><span data-stu-id="9ee04-690">DBPROP_COMMITPRESERVE</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ee04-691">Quick Restart</span><span class="sxs-lookup"><span data-stu-id="9ee04-691">Quick Restart</span></span></p></td>
<td><p><span data-ttu-id="9ee04-692">DBPROP_QUICKRESTART</span><span class="sxs-lookup"><span data-stu-id="9ee04-692">DBPROP_QUICKRESTART</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ee04-693">Reentrant Events</span><span class="sxs-lookup"><span data-stu-id="9ee04-693">Reentrant Events</span></span></p></td>
<td><p><span data-ttu-id="9ee04-694">DBPROP_REENTRANTEVENTS</span><span class="sxs-lookup"><span data-stu-id="9ee04-694">DBPROP_REENTRANTEVENTS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ee04-695">Remove Deleted Rows</span><span class="sxs-lookup"><span data-stu-id="9ee04-695">Remove Deleted Rows</span></span></p></td>
<td><p><span data-ttu-id="9ee04-696">DBPROP_REMOVEDELETED</span><span class="sxs-lookup"><span data-stu-id="9ee04-696">DBPROP_REMOVEDELETED</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ee04-697">Report Multiple Changes</span><span class="sxs-lookup"><span data-stu-id="9ee04-697">Report Multiple Changes</span></span></p></td>
<td><p><span data-ttu-id="9ee04-698">DBPROP_REPORTMULTIPLECHANGES</span><span class="sxs-lookup"><span data-stu-id="9ee04-698">DBPROP_REPORTMULTIPLECHANGES</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ee04-699">Return Pending Inserts</span><span class="sxs-lookup"><span data-stu-id="9ee04-699">Return Pending Inserts</span></span></p></td>
<td><p><span data-ttu-id="9ee04-700">DBPROP_RETURNPENDINGINSERTS</span><span class="sxs-lookup"><span data-stu-id="9ee04-700">DBPROP_RETURNPENDINGINSERTS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ee04-701">Row Delete Notification</span><span class="sxs-lookup"><span data-stu-id="9ee04-701">Row Delete Notification</span></span></p></td>
<td><p><span data-ttu-id="9ee04-702">DBPROP_NOTIFYROWDELETE</span><span class="sxs-lookup"><span data-stu-id="9ee04-702">DBPROP_NOTIFYROWDELETE</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ee04-703">Row First Change Notification</span><span class="sxs-lookup"><span data-stu-id="9ee04-703">Row First Change Notification</span></span></p></td>
<td><p><span data-ttu-id="9ee04-704">DBPROP_NOTIFYROWFIRSTCHANGE</span><span class="sxs-lookup"><span data-stu-id="9ee04-704">DBPROP_NOTIFYROWFIRSTCHANGE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ee04-705">Row Insert Notification</span><span class="sxs-lookup"><span data-stu-id="9ee04-705">Row Insert Notification</span></span></p></td>
<td><p><span data-ttu-id="9ee04-706">DBPROP_NOTIFYROWINSERT</span><span class="sxs-lookup"><span data-stu-id="9ee04-706">DBPROP_NOTIFYROWINSERT</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ee04-707">Row Privileges</span><span class="sxs-lookup"><span data-stu-id="9ee04-707">Row Privileges</span></span></p></td>
<td><p><span data-ttu-id="9ee04-708">DBPROP_ROWRESTRICT</span><span class="sxs-lookup"><span data-stu-id="9ee04-708">DBPROP_ROWRESTRICT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ee04-709">Row Resynchronization Notification</span><span class="sxs-lookup"><span data-stu-id="9ee04-709">Row Resynchronization Notification</span></span></p></td>
<td><p><span data-ttu-id="9ee04-710">DBPROP_NOTIFYROWRESYNCH</span><span class="sxs-lookup"><span data-stu-id="9ee04-710">DBPROP_NOTIFYROWRESYNCH</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ee04-711">Row Threading Model</span><span class="sxs-lookup"><span data-stu-id="9ee04-711">Row Threading Model</span></span></p></td>
<td><p><span data-ttu-id="9ee04-712">DBPROP_ROWTHREADMODEL</span><span class="sxs-lookup"><span data-stu-id="9ee04-712">DBPROP_ROWTHREADMODEL</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ee04-713">Row Undo Change Notification</span><span class="sxs-lookup"><span data-stu-id="9ee04-713">Row Undo Change Notification</span></span></p></td>
<td><p><span data-ttu-id="9ee04-714">DBPROP_NOTIFYROWUNDOCHANGE</span><span class="sxs-lookup"><span data-stu-id="9ee04-714">DBPROP_NOTIFYROWUNDOCHANGE</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ee04-715">Row Undo Delete Notification</span><span class="sxs-lookup"><span data-stu-id="9ee04-715">Row Undo Delete Notification</span></span></p></td>
<td><p><span data-ttu-id="9ee04-716">DBPROP_NOTIFYROWUNDODELETE</span><span class="sxs-lookup"><span data-stu-id="9ee04-716">DBPROP_NOTIFYROWUNDODELETE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ee04-717">Row Undo Insert Notification</span><span class="sxs-lookup"><span data-stu-id="9ee04-717">Row Undo Insert Notification</span></span></p></td>
<td><p><span data-ttu-id="9ee04-718">DBPROP_NOTIFYROWUNDOINSERT</span><span class="sxs-lookup"><span data-stu-id="9ee04-718">DBPROP_NOTIFYROWUNDOINSERT</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ee04-719">Row Update Notification</span><span class="sxs-lookup"><span data-stu-id="9ee04-719">Row Update Notification</span></span></p></td>
<td><p><span data-ttu-id="9ee04-720">DBPROP_NOTIFYROWUPDATE</span><span class="sxs-lookup"><span data-stu-id="9ee04-720">DBPROP_NOTIFYROWUPDATE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ee04-721">Rowset Fetch Position Change Notification</span><span class="sxs-lookup"><span data-stu-id="9ee04-721">Rowset Fetch Position Change Notification</span></span></p></td>
<td><p><span data-ttu-id="9ee04-722">DBPROP_NOTIFYROWSETFETCHPOSISIONCHANGE</span><span class="sxs-lookup"><span data-stu-id="9ee04-722">DBPROP_NOTIFYROWSETFETCHPOSISIONCHANGE</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ee04-723">Rowset Release Notification</span><span class="sxs-lookup"><span data-stu-id="9ee04-723">Rowset Release Notification</span></span></p></td>
<td><p><span data-ttu-id="9ee04-724">DBPROP_NOTIFYROWSETRELEASE</span><span class="sxs-lookup"><span data-stu-id="9ee04-724">DBPROP_NOTIFYROWSETRELEASE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ee04-725">Scroll Backwards</span><span class="sxs-lookup"><span data-stu-id="9ee04-725">Scroll Backwards</span></span></p></td>
<td><p><span data-ttu-id="9ee04-726">DBPROP_CANSCROLLBACKWARDS</span><span class="sxs-lookup"><span data-stu-id="9ee04-726">DBPROP_CANSCROLLBACKWARDS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ee04-727">Skip Deleted Bookmarks</span><span class="sxs-lookup"><span data-stu-id="9ee04-727">Skip Deleted Bookmarks</span></span></p></td>
<td><p><span data-ttu-id="9ee04-728">DBPROP_BOOKMARKSKIPPED</span><span class="sxs-lookup"><span data-stu-id="9ee04-728">DBPROP_BOOKMARKSKIPPED</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ee04-729">Strong Row Identity</span><span class="sxs-lookup"><span data-stu-id="9ee04-729">Strong Row Identity</span></span></p></td>
<td><p><span data-ttu-id="9ee04-730">DBPROP_STRONGITDENTITY</span><span class="sxs-lookup"><span data-stu-id="9ee04-730">DBPROP_STRONGITDENTITY</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ee04-731">Unique Rows</span><span class="sxs-lookup"><span data-stu-id="9ee04-731">Unique Rows</span></span></p></td>
<td><p><span data-ttu-id="9ee04-732">DBPROP_UNIQUEROWS</span><span class="sxs-lookup"><span data-stu-id="9ee04-732">DBPROP_UNIQUEROWS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ee04-733">Updatability</span><span class="sxs-lookup"><span data-stu-id="9ee04-733">Updatability</span></span></p></td>
<td><p><span data-ttu-id="9ee04-734">DBPROP_UPDATABILITY</span><span class="sxs-lookup"><span data-stu-id="9ee04-734">DBPROP_UPDATABILITY</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ee04-735">Use Bookmarks</span><span class="sxs-lookup"><span data-stu-id="9ee04-735">Use Bookmarks</span></span></p></td>
<td><p><span data-ttu-id="9ee04-736">DBPROP_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="9ee04-736">DBPROP_BOOKMARKS</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="command-dynamic-properties"></a><span data-ttu-id="9ee04-737">Command 动态属性</span><span class="sxs-lookup"><span data-stu-id="9ee04-737">Command Dynamic Properties</span></span>

<span data-ttu-id="9ee04-738">以下属性将被添加到 **Command** 对象的 **Properties** 集合中。</span><span class="sxs-lookup"><span data-stu-id="9ee04-738">The following properties are added to the **Command** object's **Properties** collection.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="9ee04-739">ADO 属性名</span><span class="sxs-lookup"><span data-stu-id="9ee04-739">ADO Property Name</span></span></p></th>
<th><p><span data-ttu-id="9ee04-740">OLE DB 属性名</span><span class="sxs-lookup"><span data-stu-id="9ee04-740">OLE DB Property Name</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9ee04-741">Access Order</span><span class="sxs-lookup"><span data-stu-id="9ee04-741">Access Order</span></span></p></td>
<td><p><span data-ttu-id="9ee04-742">DBPROP_ACCESSORDER</span><span class="sxs-lookup"><span data-stu-id="9ee04-742">DBPROP_ACCESSORDER</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ee04-743">Blocking Storage Objects</span><span class="sxs-lookup"><span data-stu-id="9ee04-743">Blocking Storage Objects</span></span></p></td>
<td><p><span data-ttu-id="9ee04-744">DBPROP_BLOCKINGSTORAGEOBJECTS</span><span class="sxs-lookup"><span data-stu-id="9ee04-744">DBPROP_BLOCKINGSTORAGEOBJECTS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ee04-745">Bookmark Type</span><span class="sxs-lookup"><span data-stu-id="9ee04-745">Bookmark Type</span></span></p></td>
<td><p><span data-ttu-id="9ee04-746">DBPROP_BOOKMARKTYPE</span><span class="sxs-lookup"><span data-stu-id="9ee04-746">DBPROP_BOOKMARKTYPE</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ee04-747">Bookmarkable</span><span class="sxs-lookup"><span data-stu-id="9ee04-747">Bookmarkable</span></span></p></td>
<td><p><span data-ttu-id="9ee04-748">DBPROP_IROWSETLOCATE</span><span class="sxs-lookup"><span data-stu-id="9ee04-748">DBPROP_IROWSETLOCATE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ee04-749">Change Inserted Rows</span><span class="sxs-lookup"><span data-stu-id="9ee04-749">Change Inserted Rows</span></span></p></td>
<td><p><span data-ttu-id="9ee04-750">DBPROP_CHANGEINSERTEDROWS</span><span class="sxs-lookup"><span data-stu-id="9ee04-750">DBPROP_CHANGEINSERTEDROWS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ee04-751">Column Privileges</span><span class="sxs-lookup"><span data-stu-id="9ee04-751">Column Privileges</span></span></p></td>
<td><p><span data-ttu-id="9ee04-752">DBPROP_COLUMNRESTRICT</span><span class="sxs-lookup"><span data-stu-id="9ee04-752">DBPROP_COLUMNRESTRICT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ee04-753">Column Set Notification</span><span class="sxs-lookup"><span data-stu-id="9ee04-753">Column Set Notification</span></span></p></td>
<td><p><span data-ttu-id="9ee04-754">DBPROP_NOTIFYCOLUMNSET</span><span class="sxs-lookup"><span data-stu-id="9ee04-754">DBPROP_NOTIFYCOLUMNSET</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ee04-755">Delay Storage Object Updates</span><span class="sxs-lookup"><span data-stu-id="9ee04-755">Delay Storage Object Updates</span></span></p></td>
<td><p><span data-ttu-id="9ee04-756">DBPROP_DELAYSTORAGEOBJECTS</span><span class="sxs-lookup"><span data-stu-id="9ee04-756">DBPROP_DELAYSTORAGEOBJECTS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ee04-757">Fetch Backwards</span><span class="sxs-lookup"><span data-stu-id="9ee04-757">Fetch Backwards</span></span></p></td>
<td><p><span data-ttu-id="9ee04-758">DBPROP_CANFETCHBACKWARDS</span><span class="sxs-lookup"><span data-stu-id="9ee04-758">DBPROP_CANFETCHBACKWARDS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ee04-759">Hold Rows</span><span class="sxs-lookup"><span data-stu-id="9ee04-759">Hold Rows</span></span></p></td>
<td><p><span data-ttu-id="9ee04-760">DBPROP_CANHOLDROWS</span><span class="sxs-lookup"><span data-stu-id="9ee04-760">DBPROP_CANHOLDROWS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ee04-761">IAccessor</span><span class="sxs-lookup"><span data-stu-id="9ee04-761">IAccessor</span></span></p></td>
<td><p><span data-ttu-id="9ee04-762">DBPROP_IAccessor</span><span class="sxs-lookup"><span data-stu-id="9ee04-762">DBPROP_IAccessor</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ee04-763">IColumnsInfo</span><span class="sxs-lookup"><span data-stu-id="9ee04-763">IColumnsInfo</span></span></p></td>
<td><p><span data-ttu-id="9ee04-764">DBPROP_IColumnsInfo</span><span class="sxs-lookup"><span data-stu-id="9ee04-764">DBPROP_IColumnsInfo</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ee04-765">IColumnsRowset</span><span class="sxs-lookup"><span data-stu-id="9ee04-765">IColumnsRowset</span></span></p></td>
<td><p><span data-ttu-id="9ee04-766">DBPROP_IColumnsRowset</span><span class="sxs-lookup"><span data-stu-id="9ee04-766">DBPROP_IColumnsRowset</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ee04-767">IConnectionPointContainer</span><span class="sxs-lookup"><span data-stu-id="9ee04-767">IConnectionPointContainer</span></span></p></td>
<td><p><span data-ttu-id="9ee04-768">DBPROP_IConnectionPointContainer</span><span class="sxs-lookup"><span data-stu-id="9ee04-768">DBPROP_IConnectionPointContainer</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ee04-769">IConvertType</span><span class="sxs-lookup"><span data-stu-id="9ee04-769">IConvertType</span></span></p></td>
<td><p><span data-ttu-id="9ee04-770">DBPROP_IConvertType</span><span class="sxs-lookup"><span data-stu-id="9ee04-770">DBPROP_IConvertType</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ee04-771">Immobile Rows</span><span class="sxs-lookup"><span data-stu-id="9ee04-771">Immobile Rows</span></span></p></td>
<td><p><span data-ttu-id="9ee04-772">DBPROP_IMMOBILEROWS</span><span class="sxs-lookup"><span data-stu-id="9ee04-772">DBPROP_IMMOBILEROWS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ee04-773">IRowset</span><span class="sxs-lookup"><span data-stu-id="9ee04-773">IRowset</span></span></p></td>
<td><p><span data-ttu-id="9ee04-774">DBPROP_IRowset</span><span class="sxs-lookup"><span data-stu-id="9ee04-774">DBPROP_IRowset</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ee04-775">IRowsetChange</span><span class="sxs-lookup"><span data-stu-id="9ee04-775">IRowsetChange</span></span></p></td>
<td><p><span data-ttu-id="9ee04-776">DBPROP_IRowsetChange</span><span class="sxs-lookup"><span data-stu-id="9ee04-776">DBPROP_IRowsetChange</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ee04-777">IRowsetIdentity</span><span class="sxs-lookup"><span data-stu-id="9ee04-777">IRowsetIdentity</span></span></p></td>
<td><p><span data-ttu-id="9ee04-778">DBPROP_IRowsetIdentity</span><span class="sxs-lookup"><span data-stu-id="9ee04-778">DBPROP_IRowsetIdentity</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ee04-779">IRowsetInfo</span><span class="sxs-lookup"><span data-stu-id="9ee04-779">IRowsetInfo</span></span></p></td>
<td><p><span data-ttu-id="9ee04-780">DBPROP_IRowsetInfo</span><span class="sxs-lookup"><span data-stu-id="9ee04-780">DBPROP_IRowsetInfo</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ee04-781">IRowsetLocate</span><span class="sxs-lookup"><span data-stu-id="9ee04-781">IRowsetLocate</span></span></p></td>
<td><p><span data-ttu-id="9ee04-782">DBPROP_IRowsetLocate</span><span class="sxs-lookup"><span data-stu-id="9ee04-782">DBPROP_IRowsetLocate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ee04-783">IRowsetResynch</span><span class="sxs-lookup"><span data-stu-id="9ee04-783">IRowsetResynch</span></span></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ee04-784">IRowsetUpdate</span><span class="sxs-lookup"><span data-stu-id="9ee04-784">IRowsetUpdate</span></span></p></td>
<td><p><span data-ttu-id="9ee04-785">DBPROP_IRowsetUpdate</span><span class="sxs-lookup"><span data-stu-id="9ee04-785">DBPROP_IRowsetUpdate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ee04-786">ISequentialStream</span><span class="sxs-lookup"><span data-stu-id="9ee04-786">ISequentialStream</span></span></p></td>
<td><p><span data-ttu-id="9ee04-787">DBPROP_ISequentialStream</span><span class="sxs-lookup"><span data-stu-id="9ee04-787">DBPROP_ISequentialStream</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ee04-788">ISupportErrorInfo</span><span class="sxs-lookup"><span data-stu-id="9ee04-788">ISupportErrorInfo</span></span></p></td>
<td><p><span data-ttu-id="9ee04-789">DBPROP_ISupportErrorInfo</span><span class="sxs-lookup"><span data-stu-id="9ee04-789">DBPROP_ISupportErrorInfo</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ee04-790">Literal Bookmarks</span><span class="sxs-lookup"><span data-stu-id="9ee04-790">Literal Bookmarks</span></span></p></td>
<td><p><span data-ttu-id="9ee04-791">DBPROP_LITERALBOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="9ee04-791">DBPROP_LITERALBOOKMARKS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ee04-792">Literal Row Identity</span><span class="sxs-lookup"><span data-stu-id="9ee04-792">Literal Row Identity</span></span></p></td>
<td><p><span data-ttu-id="9ee04-793">DBPROP_LITERALIDENTITY</span><span class="sxs-lookup"><span data-stu-id="9ee04-793">DBPROP_LITERALIDENTITY</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ee04-794">Maximum Open Rows</span><span class="sxs-lookup"><span data-stu-id="9ee04-794">Maximum Open Rows</span></span></p></td>
<td><p><span data-ttu-id="9ee04-795">DBPROP_MAXOPENROWS</span><span class="sxs-lookup"><span data-stu-id="9ee04-795">DBPROP_MAXOPENROWS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ee04-796">Maximum Pending Rows</span><span class="sxs-lookup"><span data-stu-id="9ee04-796">Maximum Pending Rows</span></span></p></td>
<td><p><span data-ttu-id="9ee04-797">DBPROP_MAXPENDINGROWS</span><span class="sxs-lookup"><span data-stu-id="9ee04-797">DBPROP_MAXPENDINGROWS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ee04-798">Maximum Rows</span><span class="sxs-lookup"><span data-stu-id="9ee04-798">Maximum Rows</span></span></p></td>
<td><p><span data-ttu-id="9ee04-799">DBPROP_MAXROWS</span><span class="sxs-lookup"><span data-stu-id="9ee04-799">DBPROP_MAXROWS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ee04-800">Notification Granularity</span><span class="sxs-lookup"><span data-stu-id="9ee04-800">Notification Granularity</span></span></p></td>
<td><p><span data-ttu-id="9ee04-801">DBPROP_NOTIFICATIONGRANULARITY</span><span class="sxs-lookup"><span data-stu-id="9ee04-801">DBPROP_NOTIFICATIONGRANULARITY</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ee04-802">Notification Phases</span><span class="sxs-lookup"><span data-stu-id="9ee04-802">Notification Phases</span></span></p></td>
<td><p><span data-ttu-id="9ee04-803">DBPROP_NOTIFICATIONPHASES</span><span class="sxs-lookup"><span data-stu-id="9ee04-803">DBPROP_NOTIFICATIONPHASES</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ee04-804">Objects Transacted</span><span class="sxs-lookup"><span data-stu-id="9ee04-804">Objects Transacted</span></span></p></td>
<td><p><span data-ttu-id="9ee04-805">DBPROP_TRANSACTEDOBJECT</span><span class="sxs-lookup"><span data-stu-id="9ee04-805">DBPROP_TRANSACTEDOBJECT</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ee04-806">Own Changes Visible</span><span class="sxs-lookup"><span data-stu-id="9ee04-806">Own Changes Visible</span></span></p></td>
<td><p><span data-ttu-id="9ee04-807">DBPROP_OWNUPDATEDELETE</span><span class="sxs-lookup"><span data-stu-id="9ee04-807">DBPROP_OWNUPDATEDELETE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ee04-808">Own Inserts Visible</span><span class="sxs-lookup"><span data-stu-id="9ee04-808">Own Inserts Visible</span></span></p></td>
<td><p><span data-ttu-id="9ee04-809">DBPROP_OWNINSERT</span><span class="sxs-lookup"><span data-stu-id="9ee04-809">DBPROP_OWNINSERT</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ee04-810">Preserve on Abort</span><span class="sxs-lookup"><span data-stu-id="9ee04-810">Preserve on Abort</span></span></p></td>
<td><p><span data-ttu-id="9ee04-811">DBPROP_ABORTPRESERVE</span><span class="sxs-lookup"><span data-stu-id="9ee04-811">DBPROP_ABORTPRESERVE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ee04-812">Preserve on Commit</span><span class="sxs-lookup"><span data-stu-id="9ee04-812">Preserve on Commit</span></span></p></td>
<td><p><span data-ttu-id="9ee04-813">DBPROP_COMMITPRESERVE</span><span class="sxs-lookup"><span data-stu-id="9ee04-813">DBPROP_COMMITPRESERVE</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ee04-814">Quick Restart</span><span class="sxs-lookup"><span data-stu-id="9ee04-814">Quick Restart</span></span></p></td>
<td><p><span data-ttu-id="9ee04-815">DBPROP_QUICKRESTART</span><span class="sxs-lookup"><span data-stu-id="9ee04-815">DBPROP_QUICKRESTART</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ee04-816">Reentrant Events</span><span class="sxs-lookup"><span data-stu-id="9ee04-816">Reentrant Events</span></span></p></td>
<td><p><span data-ttu-id="9ee04-817">DBPROP_REENTRANTEVENTS</span><span class="sxs-lookup"><span data-stu-id="9ee04-817">DBPROP_REENTRANTEVENTS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ee04-818">Remove Deleted Rows</span><span class="sxs-lookup"><span data-stu-id="9ee04-818">Remove Deleted Rows</span></span></p></td>
<td><p><span data-ttu-id="9ee04-819">DBPROP_REMOVEDELETED</span><span class="sxs-lookup"><span data-stu-id="9ee04-819">DBPROP_REMOVEDELETED</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ee04-820">Report Multiple Changes</span><span class="sxs-lookup"><span data-stu-id="9ee04-820">Report Multiple Changes</span></span></p></td>
<td><p><span data-ttu-id="9ee04-821">DBPROP_REPORTMULTIPLECHANGES</span><span class="sxs-lookup"><span data-stu-id="9ee04-821">DBPROP_REPORTMULTIPLECHANGES</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ee04-822">Return Pending Inserts</span><span class="sxs-lookup"><span data-stu-id="9ee04-822">Return Pending Inserts</span></span></p></td>
<td><p><span data-ttu-id="9ee04-823">DBPROP_RETURNPENDINGINSERTS</span><span class="sxs-lookup"><span data-stu-id="9ee04-823">DBPROP_RETURNPENDINGINSERTS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ee04-824">Row Delete Notification</span><span class="sxs-lookup"><span data-stu-id="9ee04-824">Row Delete Notification</span></span></p></td>
<td><p><span data-ttu-id="9ee04-825">DBPROP_NOTIFYROWDELETE</span><span class="sxs-lookup"><span data-stu-id="9ee04-825">DBPROP_NOTIFYROWDELETE</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ee04-826">Row First Change Notification</span><span class="sxs-lookup"><span data-stu-id="9ee04-826">Row First Change Notification</span></span></p></td>
<td><p><span data-ttu-id="9ee04-827">DBPROP_NOTIFYROWFIRSTCHANGE</span><span class="sxs-lookup"><span data-stu-id="9ee04-827">DBPROP_NOTIFYROWFIRSTCHANGE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ee04-828">Row Insert Notification</span><span class="sxs-lookup"><span data-stu-id="9ee04-828">Row Insert Notification</span></span></p></td>
<td><p><span data-ttu-id="9ee04-829">DBPROP_NOTIFYROWINSERT</span><span class="sxs-lookup"><span data-stu-id="9ee04-829">DBPROP_NOTIFYROWINSERT</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ee04-830">Row Privileges</span><span class="sxs-lookup"><span data-stu-id="9ee04-830">Row Privileges</span></span></p></td>
<td><p><span data-ttu-id="9ee04-831">DBPROP_ROWRESTRICT</span><span class="sxs-lookup"><span data-stu-id="9ee04-831">DBPROP_ROWRESTRICT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ee04-832">Row Resynchronization Notification</span><span class="sxs-lookup"><span data-stu-id="9ee04-832">Row Resynchronization Notification</span></span></p></td>
<td><p><span data-ttu-id="9ee04-833">DBPROP_NOTIFYROWRESYNCH</span><span class="sxs-lookup"><span data-stu-id="9ee04-833">DBPROP_NOTIFYROWRESYNCH</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ee04-834">Row Threading Model</span><span class="sxs-lookup"><span data-stu-id="9ee04-834">Row Threading Model</span></span></p></td>
<td><p><span data-ttu-id="9ee04-835">DBPROP_ROWTHREADMODEL</span><span class="sxs-lookup"><span data-stu-id="9ee04-835">DBPROP_ROWTHREADMODEL</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ee04-836">Row Undo Change Notification</span><span class="sxs-lookup"><span data-stu-id="9ee04-836">Row Undo Change Notification</span></span></p></td>
<td><p><span data-ttu-id="9ee04-837">DBPROP_NOTIFYROWUNDOCHANGE</span><span class="sxs-lookup"><span data-stu-id="9ee04-837">DBPROP_NOTIFYROWUNDOCHANGE</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ee04-838">Row Undo Delete Notification</span><span class="sxs-lookup"><span data-stu-id="9ee04-838">Row Undo Delete Notification</span></span></p></td>
<td><p><span data-ttu-id="9ee04-839">DBPROP_NOTIFYROWUNDODELETE</span><span class="sxs-lookup"><span data-stu-id="9ee04-839">DBPROP_NOTIFYROWUNDODELETE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ee04-840">Row Undo Insert Notification</span><span class="sxs-lookup"><span data-stu-id="9ee04-840">Row Undo Insert Notification</span></span></p></td>
<td><p><span data-ttu-id="9ee04-841">DBPROP_NOTIFYROWUNDOINSERT</span><span class="sxs-lookup"><span data-stu-id="9ee04-841">DBPROP_NOTIFYROWUNDOINSERT</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ee04-842">Row Update Notification</span><span class="sxs-lookup"><span data-stu-id="9ee04-842">Row Update Notification</span></span></p></td>
<td><p><span data-ttu-id="9ee04-843">DBPROP_NOTIFYROWUPDATE</span><span class="sxs-lookup"><span data-stu-id="9ee04-843">DBPROP_NOTIFYROWUPDATE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ee04-844">Rowset Fetch Position Change Notification</span><span class="sxs-lookup"><span data-stu-id="9ee04-844">Rowset Fetch Position Change Notification</span></span></p></td>
<td><p><span data-ttu-id="9ee04-845">DBPROP_NOTIFYROWSETFETCHPOSITIONCHANGE</span><span class="sxs-lookup"><span data-stu-id="9ee04-845">DBPROP_NOTIFYROWSETFETCHPOSITIONCHANGE</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ee04-846">Rowset Release Notification</span><span class="sxs-lookup"><span data-stu-id="9ee04-846">Rowset Release Notification</span></span></p></td>
<td><p><span data-ttu-id="9ee04-847">DBPROP_NOTIFYROWSETRELEASE</span><span class="sxs-lookup"><span data-stu-id="9ee04-847">DBPROP_NOTIFYROWSETRELEASE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ee04-848">Scroll Backwards</span><span class="sxs-lookup"><span data-stu-id="9ee04-848">Scroll Backwards</span></span></p></td>
<td><p><span data-ttu-id="9ee04-849">DBPROP_CANSCROLLBACKWARDS</span><span class="sxs-lookup"><span data-stu-id="9ee04-849">DBPROP_CANSCROLLBACKWARDS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ee04-850">Skip Deleted Bookmarks</span><span class="sxs-lookup"><span data-stu-id="9ee04-850">Skip Deleted Bookmarks</span></span></p></td>
<td><p><span data-ttu-id="9ee04-851">DBPROP_BOOKMARKSKIP</span><span class="sxs-lookup"><span data-stu-id="9ee04-851">DBPROP_BOOKMARKSKIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ee04-852">Strong Row Identity</span><span class="sxs-lookup"><span data-stu-id="9ee04-852">Strong Row Identity</span></span></p></td>
<td><p><span data-ttu-id="9ee04-853">DBPROP_STRONGIDENTITY</span><span class="sxs-lookup"><span data-stu-id="9ee04-853">DBPROP_STRONGIDENTITY</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ee04-854">Updatability</span><span class="sxs-lookup"><span data-stu-id="9ee04-854">Updatability</span></span></p></td>
<td><p><span data-ttu-id="9ee04-855">DBPROP_UPDATABILITY</span><span class="sxs-lookup"><span data-stu-id="9ee04-855">DBPROP_UPDATABILITY</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ee04-856">Use Bookmarks</span><span class="sxs-lookup"><span data-stu-id="9ee04-856">Use Bookmarks</span></span></p></td>
<td><p><span data-ttu-id="9ee04-857">DBPROP_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="9ee04-857">DBPROP_BOOKMARKS</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="see-also"></a><span data-ttu-id="9ee04-858">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9ee04-858">See also</span></span>

<span data-ttu-id="9ee04-859">有关具体的实现以及有关 Microsoft OLE DB Provider for ODBC 的功能信息的详细信息，请参阅[OLE DB 程序员指南 》](https://docs.microsoft.com/previous-versions/windows/desktop/ms713643(v=vs.85))或访问[数据平台开发人员中心](https://docs.microsoft.com/sql/connect/sql-data-developer?view=sql-server-2017)。</span><span class="sxs-lookup"><span data-stu-id="9ee04-859">For details regarding specific implementation and functional information about the Microsoft OLE DB Provider for ODBC, consult the [OLE DB Programmer's Guide](https://docs.microsoft.com/previous-versions/windows/desktop/ms713643(v=vs.85)) or visit the [Data Platform Developer Center](https://docs.microsoft.com/sql/connect/sql-data-developer?view=sql-server-2017).</span></span>

