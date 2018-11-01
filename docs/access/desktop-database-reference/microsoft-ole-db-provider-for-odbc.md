---
title: Microsoft OLE DB Provider for ODBC
TOCTitle: Microsoft OLE DB Provider for ODBC
ms:assetid: c507567e-5ad1-b32a-f6ad-5ba2c39aa4c2
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249964(v=office.15)
ms:contentKeyID: 48547602
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 66ef27165e6f5823cc97a295643dfc2ae5c205c2
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25883181"
---
# <a name="microsoft-ole-db-provider-for-odbc"></a><span data-ttu-id="bdd32-102">Microsoft OLE DB Provider for ODBC</span><span class="sxs-lookup"><span data-stu-id="bdd32-102">Microsoft OLE DB Provider for ODBC</span></span>

<span data-ttu-id="bdd32-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="bdd32-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="bdd32-p101">对 ADO 或 RDS 程序员来说，理想环境应该是：每个数据源都公开一个 OLE DB 接口，这样 ADO 就可以直接调入数据源。尽管越来越多的数据库供应商要实现 OLE DB 接口，但某些数据源却仍未以此方式公开。实际上，通过 ODBC 可以访问目前在用的所有 DBMS 系统。</span><span class="sxs-lookup"><span data-stu-id="bdd32-p101">To an ADO or RDS programmer, an ideal world would be one in which every data source exposes an OLE DB interface, so that ADO could call directly into the data source. Although increasingly more database vendors are implementing OLE DB interfaces, some data sources are not yet exposed this way. However, virtually all DBMS systems in use today can be accessed through ODBC.</span></span>

<span data-ttu-id="bdd32-107">ODBC 驱动程序可用于目前在用的所有主要的 DBMS，包括 Microsoft SQL Server、Microsoft Access（Microsoft Jet 数据库引擎）、Microsoft FoxPro 以及非 Microsoft 数据库产品（如 Oracle）。</span><span class="sxs-lookup"><span data-stu-id="bdd32-107">ODBC drivers are available for every major DBMS in use today, including Microsoft SQL Server, Microsoft Access (Microsoft Jet database engine), and Microsoft FoxPro, in addition to non-Microsoft database products such as Oracle.</span></span>

<span data-ttu-id="bdd32-p102">Microsoft ODBC Provider 允许 ADO 连接到任何 ODBC 数据源。此提供程序为自由线程并使用 Unicode。</span><span class="sxs-lookup"><span data-stu-id="bdd32-p102">The Microsoft ODBC Provider, however, allows ADO to connect to any ODBC data source. The provider is free-threaded and Unicode enabled.</span></span>

<span data-ttu-id="bdd32-p103">此提供程序支持事务处理，但不同的 DBMS 引擎所支持的事务类型不同。例如，Microsoft Access 支持的嵌套事务可达五层。</span><span class="sxs-lookup"><span data-stu-id="bdd32-p103">The provider supports transactions, although different DBMS engines offer different types of transaction support. For example, Microsoft Access supports nested transactions up to five levels deep.</span></span>

<span data-ttu-id="bdd32-112">此提供程序是 ADO 的默认提供程序，它支持所有与提供程序有关的 ADO 属性和方法。</span><span class="sxs-lookup"><span data-stu-id="bdd32-112">This is the default provider for ADO, and all provider-dependent ADO properties and methods are supported.</span></span>

## <a name="connection-string-parameters"></a><span data-ttu-id="bdd32-113">连接字符串参数</span><span class="sxs-lookup"><span data-stu-id="bdd32-113">Connection String Parameters</span></span>

<span data-ttu-id="bdd32-114">要连接到此提供程序，请将 **ConnectionString** 属性的 [Provider=](connectionstring-property-ado.md) 参数设置为：</span><span class="sxs-lookup"><span data-stu-id="bdd32-114">To connect to this provider, set the **Provider=** argument of the [ConnectionString](connectionstring-property-ado.md) property to:</span></span>

```sql 
 
MSDASQL 
```

<span data-ttu-id="bdd32-115">读取 [Provider](provider-property-ado.md) 属性时，也会返回此字符串。</span><span class="sxs-lookup"><span data-stu-id="bdd32-115">Reading the [Provider](provider-property-ado.md) property will return this string as well.</span></span>

## <a name="typical-connection-string"></a><span data-ttu-id="bdd32-116">典型的连接字符串</span><span class="sxs-lookup"><span data-stu-id="bdd32-116">Typical Connection String</span></span>

<span data-ttu-id="bdd32-117">此提供程序典型的连接字符串为：</span><span class="sxs-lookup"><span data-stu-id="bdd32-117">A typical connection string for this provider is:</span></span>

```sql 
 
"Provider=MSDASQL;DSN=dsnName;UID=userName;PWD=userPassword;" 
```

<span data-ttu-id="bdd32-118">该字符串由以下关键字组成：</span><span class="sxs-lookup"><span data-stu-id="bdd32-118">The string consists of these keywords:</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="bdd32-119">关键字</span><span class="sxs-lookup"><span data-stu-id="bdd32-119">Keyword</span></span></p></th>
<th><p><span data-ttu-id="bdd32-120">说明</span><span class="sxs-lookup"><span data-stu-id="bdd32-120">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bdd32-121"><strong>Provider</strong></span><span class="sxs-lookup"><span data-stu-id="bdd32-121"><strong>Provider</strong></span></span></p></td>
<td><p><span data-ttu-id="bdd32-122">指定 OLE DB Provider for ODBC。</span><span class="sxs-lookup"><span data-stu-id="bdd32-122">Specifies the OLE DB Provider for ODBC.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdd32-123"><strong>DSN</strong></span><span class="sxs-lookup"><span data-stu-id="bdd32-123"><strong>DSN</strong></span></span></p></td>
<td><p><span data-ttu-id="bdd32-124">指定数据源名称。</span><span class="sxs-lookup"><span data-stu-id="bdd32-124">Specifies the data source name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdd32-125"><strong>UID</strong></span><span class="sxs-lookup"><span data-stu-id="bdd32-125"><strong>UID</strong></span></span></p></td>
<td><p><span data-ttu-id="bdd32-126">指定用户名。</span><span class="sxs-lookup"><span data-stu-id="bdd32-126">Specifies the user name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdd32-127"><strong>PWD</strong></span><span class="sxs-lookup"><span data-stu-id="bdd32-127"><strong>PWD</strong></span></span></p></td>
<td><p><span data-ttu-id="bdd32-128">指定用户密码。</span><span class="sxs-lookup"><span data-stu-id="bdd32-128">Specifies the user password.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdd32-129"><strong>URL</strong></span><span class="sxs-lookup"><span data-stu-id="bdd32-129"><strong>URL</strong></span></span></p></td>
<td><p><span data-ttu-id="bdd32-130">指定文件或目录 web 文件夹中发布的 URL。</span><span class="sxs-lookup"><span data-stu-id="bdd32-130">Specifies the URL of a file or directory published in a web folder.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="bdd32-131">如果在连接字符串中省略 **Provider=** 参数，则 ADO 将尝试建立与此提供程序（因为它是 ADO 的默认提供程序）的连接。</span><span class="sxs-lookup"><span data-stu-id="bdd32-131">Because this is the default provider for ADO, if you omit the **Provider=** parameter from the connection string, ADO will attempt to establish a connection to this provider.</span></span>

<span data-ttu-id="bdd32-p104">除了 ADO 定义的连接参数以外，此提供程序不支持任何特定的连接参数，但它会将任何非 ADO 连接参数传递给 ODBC 驱动程序管理器。</span><span class="sxs-lookup"><span data-stu-id="bdd32-p104">The provider does not support any specific connection parameters in addition to those defined by ADO. However, the provider will pass any non-ADO connection parameters to the ODBC driver manager.</span></span>

<span data-ttu-id="bdd32-p105">由于可以省略 **Provider** 参数，因此，可以构造与同一个数据源的 ODBC 连接字符串完全一样的 ADO 连接字符串。参数名称（**DRIVER=**、**DATABASE=**、**DSN=** 等）、值和语法也和构造 ODBC 连接字符串时所用的一样。连接时，可以使用也可以不使用预定义的数据源名称 (DSN) 或 FileDSN。</span><span class="sxs-lookup"><span data-stu-id="bdd32-p105">Because you can omit the **Provider** parameter, you can therefore compose an ADO connection string that is identical to an ODBC connection string for the same data source. Use the same parameter names (**DRIVER=**, **DATABASE=**, **DSN=**, and so on), values, and syntax as you would when composing an ODBC connection string. You can connect with or without a predefined data source name (DSN) or FileDSN.</span></span>

<span data-ttu-id="bdd32-137">**带有 DSN 或 FileDSN 的语法：**</span><span class="sxs-lookup"><span data-stu-id="bdd32-137">**Syntax with a DSN or FileDSN:**</span></span>

`"[Provider=MSDASQL;] { DSN=name | FileDSN=filename } ; [DATABASE=database;] UID=user; PWD=password"`

<span data-ttu-id="bdd32-138">**不带 DSN（无 DSN 连接）的语法：**</span><span class="sxs-lookup"><span data-stu-id="bdd32-138">**Syntax without a DSN (DSN-less connection):**</span></span>

`"[Provider=MSDASQL;] DRIVER=driver; SERVER=server;DATABASE=database; UID=user; PWD=password"`

<span data-ttu-id="bdd32-p106">如果要使用 **DSN** 或 **FileDSN** ，必须通过 Windows "控制面板"中的"ODBC 数据源管理器"进行定义。在 Microsoft Windows 2000 中，ODBC 管理器位于"管理工具"中。在以前的 Windows 版本中，"ODBC 管理器"图标的名称是 **32 位 ODBC** 或者就是 **ODBC** 。</span><span class="sxs-lookup"><span data-stu-id="bdd32-p106">If you use a **DSN** or **FileDSN**, it must be defined through the ODBC Data Source Administrator in the Windows Control Panel. In Microsoft Windows 2000, the ODBC Administrator is located under Administrative Tools. In previous versions of Windows, the ODBC Administrator icon is named **32-bit ODBC** or simply **ODBC**.</span></span>

<span data-ttu-id="bdd32-142">除了设置 **DSN** 以外，还可以指定 ODBC 驱动程序，如“SQL Server” (**DRIVER=**)；可以指定服务器名称 (**SERVER=**) 和数据库名称 (**DATABASE=**)。</span><span class="sxs-lookup"><span data-stu-id="bdd32-142">As an alternative to setting a **DSN**, you can specify the ODBC driver (**DRIVER=**), such as "SQL Server;" the server name (**SERVER=**); and the database name (**DATABASE=**).</span></span>

<span data-ttu-id="bdd32-143">也可以在 ODBC 特定的参数中或在标准的 ADO 定义的 *user* 和 *password* 参数中指定用户帐户名 (**UID=**) 以及用户帐户的密码 (**PWD=**)。</span><span class="sxs-lookup"><span data-stu-id="bdd32-143">You can also specify a user account name (**UID=**), and the password for the user account (**PWD=**) in the ODBC-specific parameters or in the standard ADO-defined *user* and *password* parameters.</span></span>

<span data-ttu-id="bdd32-144">虽然**DSN**定义已指定了数据库，您可以指定除了**DSN**连接到其他数据库*的\*\*数据库*参数。</span><span class="sxs-lookup"><span data-stu-id="bdd32-144">Although a **DSN** definition already specifies a database, you can specify *a* *database* parameter in addition to a **DSN** to connect to a different database.</span></span> <span data-ttu-id="bdd32-145">最好若要使用**DSN**时始终包含\**database*参数\*。</span><span class="sxs-lookup"><span data-stu-id="bdd32-145">It is a good idea to always include *the* *database* parameter when you use a **DSN**.</span></span> <span data-ttu-id="bdd32-146">这将确保在上次检查了 **DSN** 定义后其他用户更改了默认的数据库参数的情况下，依然可以连接到正确的数据库。</span><span class="sxs-lookup"><span data-stu-id="bdd32-146">This will ensure that you connect to the proper database in the event that another user changed the default database parameter since you last checked the **DSN** definition.</span></span>

## <a name="provider-specific-connection-properties"></a><span data-ttu-id="bdd32-147">提供程序特定的连接属性</span><span class="sxs-lookup"><span data-stu-id="bdd32-147">Provider-Specific Connection Properties</span></span>

<span data-ttu-id="bdd32-p108">OLE DB Provider for ODBC 会将多个属性添加到 [Connection](properties-collection-ado.md) 对象的 **Properties** 集合中。下表列出了这些属性以及对应的 OLE DB 属性名（括在括号中）。</span><span class="sxs-lookup"><span data-stu-id="bdd32-p108">The OLE DB provider for ODBC adds several properties to the [Properties](properties-collection-ado.md) collection of the **Connection** object. The following table lists these properties with the corresponding OLE DB property name in parentheses.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="bdd32-150">属性名称</span><span class="sxs-lookup"><span data-stu-id="bdd32-150">Property Name</span></span></p></th>
<th><p><span data-ttu-id="bdd32-151">说明</span><span class="sxs-lookup"><span data-stu-id="bdd32-151">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bdd32-152">可访问的过程</span><span class="sxs-lookup"><span data-stu-id="bdd32-152">Accessible Procedures</span></span><br />
<span data-ttu-id="bdd32-153">(KAGPROP_ACCESSIBLEPROCEDURES)</span><span class="sxs-lookup"><span data-stu-id="bdd32-153">(KAGPROP_ACCESSIBLEPROCEDURES)</span></span></p></td>
<td><p><span data-ttu-id="bdd32-154">指示用户是否有权访问存储过程。</span><span class="sxs-lookup"><span data-stu-id="bdd32-154">Indicates whether the user has access to stored procedures.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdd32-155">可访问的表</span><span class="sxs-lookup"><span data-stu-id="bdd32-155">Accessible Tables</span></span><br />
<span data-ttu-id="bdd32-156">(KAGPROP_ACCESSIBLETABLES)</span><span class="sxs-lookup"><span data-stu-id="bdd32-156">(KAGPROP_ACCESSIBLETABLES)</span></span></p></td>
<td><p><span data-ttu-id="bdd32-157">指示用户是否有权针对数据库表执行 SELECT 语句。</span><span class="sxs-lookup"><span data-stu-id="bdd32-157">Indicates whether the user has permission to execute SELECT statements against the database tables.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdd32-158">活动语句</span><span class="sxs-lookup"><span data-stu-id="bdd32-158">Active Statements</span></span><br />
<span data-ttu-id="bdd32-159">(KAGPROP_ACTIVESTATEMENTS)</span><span class="sxs-lookup"><span data-stu-id="bdd32-159">(KAGPROP_ACTIVESTATEMENTS)</span></span></p></td>
<td><p><span data-ttu-id="bdd32-160">指示 ODBC 驱动程序在连接上可支持的句柄数量。</span><span class="sxs-lookup"><span data-stu-id="bdd32-160">Indicates the number of handles an ODBC driver can support on a connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdd32-161">驱动程序名称</span><span class="sxs-lookup"><span data-stu-id="bdd32-161">Driver Name</span></span><br />
<span data-ttu-id="bdd32-162">(KAGPROP_DRIVERNAME)</span><span class="sxs-lookup"><span data-stu-id="bdd32-162">(KAGPROP_DRIVERNAME)</span></span></p></td>
<td><p><span data-ttu-id="bdd32-163">指示 ODBC 驱动程序的文件名。</span><span class="sxs-lookup"><span data-stu-id="bdd32-163">Indicates the file name of the ODBC driver.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdd32-164">ODBC 驱动程序版本</span><span class="sxs-lookup"><span data-stu-id="bdd32-164">Driver ODBC Version</span></span><br />
<span data-ttu-id="bdd32-165">(KAGPROP_DRIVERODBCVER)</span><span class="sxs-lookup"><span data-stu-id="bdd32-165">(KAGPROP_DRIVERODBCVER)</span></span></p></td>
<td><p><span data-ttu-id="bdd32-166">指示此驱动程序支持的 ODBC 版本。</span><span class="sxs-lookup"><span data-stu-id="bdd32-166">Indicates the version of ODBC that this driver supports.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdd32-167">文件的使用情况</span><span class="sxs-lookup"><span data-stu-id="bdd32-167">File Usage</span></span><br />
<span data-ttu-id="bdd32-168">(KAGPROP_FILEUSAGE)</span><span class="sxs-lookup"><span data-stu-id="bdd32-168">(KAGPROP_FILEUSAGE)</span></span></p></td>
<td><p><span data-ttu-id="bdd32-169">指示驱动程序在数据源中处理文件的方式，作为表还是作为目录。</span><span class="sxs-lookup"><span data-stu-id="bdd32-169">Indicates how the driver treats a file in a data source; as a table or as a catalog.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdd32-170">Like 转义子句</span><span class="sxs-lookup"><span data-stu-id="bdd32-170">Like Escape Clause</span></span><br />
<span data-ttu-id="bdd32-171">(KAGPROP_LIKEESCAPECLAUSE)</span><span class="sxs-lookup"><span data-stu-id="bdd32-171">(KAGPROP_LIKEESCAPECLAUSE)</span></span></p></td>
<td><p><span data-ttu-id="bdd32-172">指示驱动程序是否支持为 WHERE 子句的 LIKE 谓词中的百分号字符 (%) 和下划线字符 (_) 定义和使用转义字符。</span><span class="sxs-lookup"><span data-stu-id="bdd32-172">Indicates whether the driver supports the definition and use of an escape character for the percent character (%) and underline character (_) in the LIKE predicate of a WHERE clause.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdd32-173">在组中的最大列数</span><span class="sxs-lookup"><span data-stu-id="bdd32-173">Max Columns in Group By</span></span><br />
<span data-ttu-id="bdd32-174">(KAGPROP_MAXCOLUMNSINGROUPBY)</span><span class="sxs-lookup"><span data-stu-id="bdd32-174">(KAGPROP_MAXCOLUMNSINGROUPBY)</span></span></p></td>
<td><p><span data-ttu-id="bdd32-175">指示 SELECT 语句的 GROUP BY 子句中可以列出的列的最大数目。</span><span class="sxs-lookup"><span data-stu-id="bdd32-175">Indicates the maximum number of columns that can be listed in the GROUP BY clause of a SELECT statement.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdd32-176">在索引中的最大列</span><span class="sxs-lookup"><span data-stu-id="bdd32-176">Max Columns in Index</span></span><br />
<span data-ttu-id="bdd32-177">(KAGPROP_MAXCOLUMNSININDEX)</span><span class="sxs-lookup"><span data-stu-id="bdd32-177">(KAGPROP_MAXCOLUMNSININDEX)</span></span></p></td>
<td><p><span data-ttu-id="bdd32-178">指示索引中可以包括的列的最大数目。</span><span class="sxs-lookup"><span data-stu-id="bdd32-178">Indicates the maximum number of columns that can be included in an index.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdd32-179">按顺序的最大列</span><span class="sxs-lookup"><span data-stu-id="bdd32-179">Max Columns in Order By</span></span><br />
<span data-ttu-id="bdd32-180">(KAGPROP_MAXCOLUMNSINORDERBY)</span><span class="sxs-lookup"><span data-stu-id="bdd32-180">(KAGPROP_MAXCOLUMNSINORDERBY)</span></span></p></td>
<td><p><span data-ttu-id="bdd32-181">指示 SELECT 语句的 ORDER BY 子句中可以列出的列的最大数目。</span><span class="sxs-lookup"><span data-stu-id="bdd32-181">Indicates the maximum number of columns that can be listed in the ORDER BY clause of a SELECT statement.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdd32-182">在选择最大列数</span><span class="sxs-lookup"><span data-stu-id="bdd32-182">Max Columns in Select</span></span><br />
<span data-ttu-id="bdd32-183">(KAGPROP_MAXCOLUMNSINSELECT)</span><span class="sxs-lookup"><span data-stu-id="bdd32-183">(KAGPROP_MAXCOLUMNSINSELECT)</span></span></p></td>
<td><p><span data-ttu-id="bdd32-184">指示 SELECT 语句的 SELECT 部分中可以列出的列的最大数目。</span><span class="sxs-lookup"><span data-stu-id="bdd32-184">Indicates the maximum number of columns that can be listed in the SELECT portion of a SELECT statement.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdd32-185">表中的最大列</span><span class="sxs-lookup"><span data-stu-id="bdd32-185">Max Columns in Table</span></span><br />
<span data-ttu-id="bdd32-186">(KAGPROP_MAXCOLUMNSINTABLE)</span><span class="sxs-lookup"><span data-stu-id="bdd32-186">(KAGPROP_MAXCOLUMNSINTABLE)</span></span></p></td>
<td><p><span data-ttu-id="bdd32-187">指示表中允许的列的最大数目。</span><span class="sxs-lookup"><span data-stu-id="bdd32-187">Indicates the maximum number of columns allowed in a table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdd32-188">数值函数</span><span class="sxs-lookup"><span data-stu-id="bdd32-188">Numeric Functions</span></span><br />
<span data-ttu-id="bdd32-189">(KAGPROP_NUMERICFUNCTIONS)</span><span class="sxs-lookup"><span data-stu-id="bdd32-189">(KAGPROP_NUMERICFUNCTIONS)</span></span></p></td>
<td><p><span data-ttu-id="bdd32-p109">指示 ODBC 驱动程序支持的数值函数。有关此位掩码中使用的函数名称和关联值的列表，请参阅 ODBC 文档中的“附录 E：标量函数”。</span><span class="sxs-lookup"><span data-stu-id="bdd32-p109">Indicates which numeric functions are supported by the ODBC driver. For a listing of function names and the associated values used in this bitmask, see Appendix E: Scalar Functions in the ODBC documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdd32-192">外部联接功能</span><span class="sxs-lookup"><span data-stu-id="bdd32-192">Outer Join Capabilities</span></span><br />
<span data-ttu-id="bdd32-193">(KAGPROP_OJCAPABILITY)</span><span class="sxs-lookup"><span data-stu-id="bdd32-193">(KAGPROP_OJCAPABILITY)</span></span></p></td>
<td><p><span data-ttu-id="bdd32-194">指示此提供程序支持的 OUTER JOIN 类型。</span><span class="sxs-lookup"><span data-stu-id="bdd32-194">Indicates the types of OUTER JOINs supported by the provider.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdd32-195">Outer Join</span><span class="sxs-lookup"><span data-stu-id="bdd32-195">Outer Joins</span></span><br />
<span data-ttu-id="bdd32-196">(KAGPROP_OUTERJOINS)</span><span class="sxs-lookup"><span data-stu-id="bdd32-196">(KAGPROP_OUTERJOINS)</span></span></p></td>
<td><p><span data-ttu-id="bdd32-197">指示支持 OUTER JOIN 的提供程序。</span><span class="sxs-lookup"><span data-stu-id="bdd32-197">Indicates whether the provider supports OUTER JOINs.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdd32-198">特殊字符</span><span class="sxs-lookup"><span data-stu-id="bdd32-198">Special Characters</span></span><br />
<span data-ttu-id="bdd32-199">(KAGPROP_SPECIALCHARACTERS)</span><span class="sxs-lookup"><span data-stu-id="bdd32-199">(KAGPROP_SPECIALCHARACTERS)</span></span></p></td>
<td><p><span data-ttu-id="bdd32-200">指示哪些字符对于 ODBC 驱动程序具有特殊意义。</span><span class="sxs-lookup"><span data-stu-id="bdd32-200">Indicates which characters have special meaning for the ODBC driver.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdd32-201">存储过程</span><span class="sxs-lookup"><span data-stu-id="bdd32-201">Stored Procedures</span></span><br />
<span data-ttu-id="bdd32-202">(KAGPROP_PROCEDURES)</span><span class="sxs-lookup"><span data-stu-id="bdd32-202">(KAGPROP_PROCEDURES)</span></span></p></td>
<td><p><span data-ttu-id="bdd32-203">指示是否可以在此 ODBC 驱动程序中使用存储过程。</span><span class="sxs-lookup"><span data-stu-id="bdd32-203">Indicates whether stored procedures are available for use with this ODBC driver.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdd32-204">字符串函数</span><span class="sxs-lookup"><span data-stu-id="bdd32-204">String Functions</span></span><br />
<span data-ttu-id="bdd32-205">(KAGPROP_STRINGFUNCTIONS)</span><span class="sxs-lookup"><span data-stu-id="bdd32-205">(KAGPROP_STRINGFUNCTIONS)</span></span></p></td>
<td><p><span data-ttu-id="bdd32-p110">指示 ODBC 驱动程序支持的字符串函数。有关此位掩码中使用的函数名称和关联值的列表，请参阅 ODBC 文档中的“附录 E：标量函数”。</span><span class="sxs-lookup"><span data-stu-id="bdd32-p110">Indicates which string functions are supported by the ODBC driver. For a listing of function names and the associated values used in this bitmask, see Appendix E: Scalar Functions in the ODBC documentation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdd32-208">系统函数</span><span class="sxs-lookup"><span data-stu-id="bdd32-208">System Functions</span></span><br />
<span data-ttu-id="bdd32-209">(KAGPROP_SYSTEMFUNCTIONS)</span><span class="sxs-lookup"><span data-stu-id="bdd32-209">(KAGPROP_SYSTEMFUNCTIONS)</span></span></p></td>
<td><p><span data-ttu-id="bdd32-p111">指示 ODBC 驱动程序支持的系统函数。有关此位掩码中使用的函数名称和关联值的列表，请参阅 ODBC 文档中的“附录 E：标量函数”。</span><span class="sxs-lookup"><span data-stu-id="bdd32-p111">Indicates which system functions are supported by the ODBC driver. For a listing of function names and the associated values used in this bitmask, see Appendix E: Scalar Functions in the ODBC documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdd32-212">时间/日期函数</span><span class="sxs-lookup"><span data-stu-id="bdd32-212">Time/Date Functions</span></span><br />
<span data-ttu-id="bdd32-213">(KAGPROP_TIMEDATEFUNCTIONS)</span><span class="sxs-lookup"><span data-stu-id="bdd32-213">(KAGPROP_TIMEDATEFUNCTIONS)</span></span></p></td>
<td><p><span data-ttu-id="bdd32-p112">指示 ODBC 驱动程序支持的时间和日期函数。有关此位掩码中使用的函数名称和关联值的列表，请参阅 ODBC 文档中的“附录 E：标量函数”。</span><span class="sxs-lookup"><span data-stu-id="bdd32-p112">Indicates which time and date functions are supported by the ODBC driver. For a listing of function names and the associated values used in this bitmask, see Appendix E: Scalar Functions in the ODBC documentation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdd32-216">SQL 语法支持</span><span class="sxs-lookup"><span data-stu-id="bdd32-216">SQL Grammar Support</span></span><br />
<span data-ttu-id="bdd32-217">(KAGPROP_ODBCSQLCONFORMANCE)</span><span class="sxs-lookup"><span data-stu-id="bdd32-217">(KAGPROP_ODBCSQLCONFORMANCE)</span></span></p></td>
<td><p><span data-ttu-id="bdd32-218">指示 ODBC 驱动程序支持的 SQL 语法。</span><span class="sxs-lookup"><span data-stu-id="bdd32-218">Indicates the SQL grammar that the ODBC driver supports.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="provider-specific-recordset-and-command-properties"></a><span data-ttu-id="bdd32-219">提供程序特定的 Recordset 和 Command 属性</span><span class="sxs-lookup"><span data-stu-id="bdd32-219">Provider-Specific Recordset and Command Properties</span></span>

<span data-ttu-id="bdd32-p113">OLE DB Provider for ODBC 会将多个属性添加到 **Recordset** 和 **Command** 对象的 **Properties** 集合中。下表列出了这些属性以及对应的 OLE DB 属性名（括在括号中）。</span><span class="sxs-lookup"><span data-stu-id="bdd32-p113">The OLE DB provider for ODBC adds several properties to the **Properties** collection of the **Recordset** and **Command** objects. The following table lists these properties with the corresponding OLE DB property name in parentheses.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="bdd32-222">属性名称</span><span class="sxs-lookup"><span data-stu-id="bdd32-222">Property Name</span></span></p></th>
<th><p><span data-ttu-id="bdd32-223">说明</span><span class="sxs-lookup"><span data-stu-id="bdd32-223">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bdd32-224">基于查询的插入/删除/更新</span><span class="sxs-lookup"><span data-stu-id="bdd32-224">Query Based Updates/Deletes/Inserts</span></span><br />
<span data-ttu-id="bdd32-225">(KAGPROP_QUERYBASEDUPDATES)</span><span class="sxs-lookup"><span data-stu-id="bdd32-225">(KAGPROP_QUERYBASEDUPDATES)</span></span></p></td>
<td><p><span data-ttu-id="bdd32-226">指示是否可以使用 SQL 查询执行更新、删除和插入。</span><span class="sxs-lookup"><span data-stu-id="bdd32-226">Indicates whether updates, deletions, and insertions can be performed using SQL queries.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdd32-227">ODBC 并发类型</span><span class="sxs-lookup"><span data-stu-id="bdd32-227">ODBC Concurrency Type</span></span><br />
<span data-ttu-id="bdd32-228">(KAGPROP_CONCURRENCY)</span><span class="sxs-lookup"><span data-stu-id="bdd32-228">(KAGPROP_CONCURRENCY)</span></span></p></td>
<td><p><span data-ttu-id="bdd32-229">指示用于减少由两个用户试图同时访问数据源中的相同数据而导致的潜在问题的方法。</span><span class="sxs-lookup"><span data-stu-id="bdd32-229">Indicates the method used to reduce potential problems caused by two users attempting to access the same data from the data source simultaneously.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdd32-230">仅向前型游标的 BLOB 辅助功能</span><span class="sxs-lookup"><span data-stu-id="bdd32-230">BLOB accessibility on Forward-Only cursor</span></span><br />
<span data-ttu-id="bdd32-231">(KAGPROP_BLOBSONFOCURSOR)</span><span class="sxs-lookup"><span data-stu-id="bdd32-231">(KAGPROP_BLOBSONFOCURSOR)</span></span></p></td>
<td><p><span data-ttu-id="bdd32-232">指示在使用只进游标时是否可以访问 BLOB <strong>字段</strong>。</span><span class="sxs-lookup"><span data-stu-id="bdd32-232">Indicates whether BLOB <strong>Fields</strong> can be accessed when using a forward-only cursor.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdd32-233">在 QBU WHERE 子句中包括 SQL_FLOAT、 SQL_DOUBLE 和 SQL_REAL</span><span class="sxs-lookup"><span data-stu-id="bdd32-233">Include SQL_FLOAT, SQL_DOUBLE, and SQL_REAL in QBU WHERE clauses</span></span><br />
<span data-ttu-id="bdd32-234">(KAGPROP_INCLUDENONEXACT)</span><span class="sxs-lookup"><span data-stu-id="bdd32-234">(KAGPROP_INCLUDENONEXACT)</span></span></p></td>
<td><p><span data-ttu-id="bdd32-235">指示 QBU WHERE 子句中是否可以包括 SQL_FLOAT、SQL_DOUBLE 和 SQL_REAL 值。</span><span class="sxs-lookup"><span data-stu-id="bdd32-235">Indicates whether SQL_FLOAT, SQL_DOUBLE, and SQL_REAL values can be included in a QBU WHERE clause.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdd32-236">在最后一行之后插入的位置</span><span class="sxs-lookup"><span data-stu-id="bdd32-236">Position on the last row after insert</span></span><br />
<span data-ttu-id="bdd32-237">(KAGPROP_POSITIONONNEWROW)</span><span class="sxs-lookup"><span data-stu-id="bdd32-237">(KAGPROP_POSITIONONNEWROW)</span></span></p></td>
<td><p><span data-ttu-id="bdd32-238">指示在表中插入新记录后，表中的最后一行是否将为当前行。</span><span class="sxs-lookup"><span data-stu-id="bdd32-238">Indicates that after a new record has been inserted in a table, the last row in the table will be come the current row.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdd32-239">IRowsetChangeExtInfo</span><span class="sxs-lookup"><span data-stu-id="bdd32-239">IRowsetChangeExtInfo</span></span><br />
<span data-ttu-id="bdd32-240">(KAGPROP_IROWSETCHANGEEXTINFO)</span><span class="sxs-lookup"><span data-stu-id="bdd32-240">(KAGPROP_IROWSETCHANGEEXTINFO)</span></span></p></td>
<td><p><span data-ttu-id="bdd32-241">指示 <strong>IRowsetChange</strong> 接口是否提供扩展的信息支持。</span><span class="sxs-lookup"><span data-stu-id="bdd32-241">Indicates whether the <strong>IRowsetChange</strong> interface provides extended information support.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdd32-242">ODBC 游标类型</span><span class="sxs-lookup"><span data-stu-id="bdd32-242">ODBC Cursor Type</span></span><br />
<span data-ttu-id="bdd32-243">(KAGPROP_CURSOR)</span><span class="sxs-lookup"><span data-stu-id="bdd32-243">(KAGPROP_CURSOR)</span></span></p></td>
<td><p><span data-ttu-id="bdd32-244">指示 <strong>Recordset</strong> 使用的游标类型。</span><span class="sxs-lookup"><span data-stu-id="bdd32-244">Indicates the type of cursor used by the <strong>Recordset</strong>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdd32-245">生成可封送的行集</span><span class="sxs-lookup"><span data-stu-id="bdd32-245">Generate a Rowset that can be marshaled</span></span><br />
<span data-ttu-id="bdd32-246">(KAGPROP_MARSHALLABLE)</span><span class="sxs-lookup"><span data-stu-id="bdd32-246">(KAGPROP_MARSHALLABLE)</span></span></p></td>
<td><p><span data-ttu-id="bdd32-247">指示 ODBC 驱动程序将生成可封送的记录集</span><span class="sxs-lookup"><span data-stu-id="bdd32-247">Indicates that the ODBC driver generates a recordset that can be marshaled</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="command-text"></a><span data-ttu-id="bdd32-248">命令文本</span><span class="sxs-lookup"><span data-stu-id="bdd32-248">Command Text</span></span>

<span data-ttu-id="bdd32-249">如何使用 [Command](command-object-ado.md) 对象在很大程度上取决于数据源及其将接受的查询语句或命令语句的类型。</span><span class="sxs-lookup"><span data-stu-id="bdd32-249">How you use the [Command](command-object-ado.md) object largely depends on the data source, and what type of query or command statement it will accept.</span></span>

<span data-ttu-id="bdd32-250">ODBC 提供了用于调用存储过程的特定语法。</span><span class="sxs-lookup"><span data-stu-id="bdd32-250">ODBC provides a specific syntax for calling stored procedures.</span></span> <span data-ttu-id="bdd32-251">**Command**对象、 的[Connection](connection-object-ado.md)对象的**Execute**方法的*CommandText*参数或[Recordset](recordset-object-ado.md)的**Open**方法的*源*参数[将 CommandText](commandtext-property-ado.md)属性对象，此语法与字符串中传递：</span><span class="sxs-lookup"><span data-stu-id="bdd32-251">For the [CommandText](commandtext-property-ado.md) property of a **Command** object, the *CommandText* argument to the **Execute** method on a [Connection](connection-object-ado.md) object, or the *Source* argument to the **Open** method on a [Recordset](recordset-object-ado.md) object, passes in a string with this syntax:</span></span>

`"{ [ ? = ] call procedure [ ( ? [, ? [ ,  ]] ) ] }"`

<span data-ttu-id="bdd32-p115">每个 **?** 都引用 [Parameters](parameters-collection-ado.md) 集合中的一个对象。第一个 **?** 引用 **Parameters**(0)，接下来的 **?** 引用 **Parameters**(1)，依此类推。</span><span class="sxs-lookup"><span data-stu-id="bdd32-p115">Each **?** references an object in the [Parameters](parameters-collection-ado.md) collection. The first **?** references **Parameters**(0), the next **?** references **Parameters**(1), and so on.</span></span>

<span data-ttu-id="bdd32-p116">参数引用是可选的，且取决于存储过程的结构。如果要调用未定义参数的存储过程，则字符串的形式将与以下所示类似：</span><span class="sxs-lookup"><span data-stu-id="bdd32-p116">The parameter references are optional and depend on the structure of the stored procedure. If you want to call a stored procedure that defines no parameters, your string would look like this:</span></span>

`"{ call procedure }"`

<span data-ttu-id="bdd32-259">如果具有两个查询参数，则字符串的形式将与以下所示类似：</span><span class="sxs-lookup"><span data-stu-id="bdd32-259">If you have two query parameters, your string would look like this:</span></span>

`"{ call procedure ( ?, ? ) }"`

<span data-ttu-id="bdd32-p117">如果存储过程返回一个值，则返回值被作为其他参数进行处理。如果您没有查询参数，但是有返回值，则字符串的形式将与以下所示类似：</span><span class="sxs-lookup"><span data-stu-id="bdd32-p117">If the stored procedure will return a value, the return value is treated as another parameter. If you have no query parameters but you do have a return value, your string would look like this:</span></span>

`"{ ? = call procedure }"`

<span data-ttu-id="bdd32-262">最后，如果您具有一个返回值和两个查询参数，则字符串的形式将与以下所示类似：</span><span class="sxs-lookup"><span data-stu-id="bdd32-262">Finally, if you have a return value and two query parameters, your string would look like this:</span></span>

`"{ ? = call procedure ( ?, ? ) }"`

## <a name="recordset-behavior"></a><span data-ttu-id="bdd32-263">Recordset 行为</span><span class="sxs-lookup"><span data-stu-id="bdd32-263">Recordset Behavior</span></span>

<span data-ttu-id="bdd32-264">下面的表列出了使用此提供程序打开的 **Recordset** 对象中可用的标准 ADO 方法和属性。</span><span class="sxs-lookup"><span data-stu-id="bdd32-264">The following tables list the standard ADO methods and properties available on a **Recordset** object opened with this provider.</span></span>

<span data-ttu-id="bdd32-265">有关提供程序配置的 **Recordset** 行为的详细信息，请运行 [Supports](supports-method-ado.md) 方法并枚举 **Recordset** 的 **Properties** 集合，以确定提供程序特定的动态属性是否存在。</span><span class="sxs-lookup"><span data-stu-id="bdd32-265">For more detailed information about **Recordset** behavior for your provider configuration, run the [Supports](supports-method-ado.md) method and enumerate the **Properties** collection of the **Recordset** to determine whether provider-specific dynamic properties are present.</span></span>

<span data-ttu-id="bdd32-266">标准 ADO **Recordset** 属性的可用性：</span><span class="sxs-lookup"><span data-stu-id="bdd32-266">Availability of standard ADO **Recordset** properties:</span></span>

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
<th><p><span data-ttu-id="bdd32-267">属性</span><span class="sxs-lookup"><span data-stu-id="bdd32-267">Property</span></span></p></th>
<th><p><span data-ttu-id="bdd32-268">ForwardOnly</span><span class="sxs-lookup"><span data-stu-id="bdd32-268">ForwardOnly</span></span></p></th>
<th><p><span data-ttu-id="bdd32-269">动态</span><span class="sxs-lookup"><span data-stu-id="bdd32-269">Dynamic</span></span></p></th>
<th><p><span data-ttu-id="bdd32-270">键集</span><span class="sxs-lookup"><span data-stu-id="bdd32-270">Keyset</span></span></p></th>
<th><p><span data-ttu-id="bdd32-271">静态</span><span class="sxs-lookup"><span data-stu-id="bdd32-271">Static</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bdd32-272"><a href="absolutepage-property-ado.md">AbsolutePage</a></span><span class="sxs-lookup"><span data-stu-id="bdd32-272"><a href="absolutepage-property-ado.md">AbsolutePage</a></span></span></p></td>
<td><p><span data-ttu-id="bdd32-273">不可用</span><span class="sxs-lookup"><span data-stu-id="bdd32-273">not available</span></span></p></td>
<td><p><span data-ttu-id="bdd32-274">不可用</span><span class="sxs-lookup"><span data-stu-id="bdd32-274">not available</span></span></p></td>
<td><p><span data-ttu-id="bdd32-275">读/写</span><span class="sxs-lookup"><span data-stu-id="bdd32-275">read/write</span></span></p></td>
<td><p><span data-ttu-id="bdd32-276">读/写</span><span class="sxs-lookup"><span data-stu-id="bdd32-276">read/write</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdd32-277"><a href="absoluteposition-property-ado.md">AbsolutePosition</a></span><span class="sxs-lookup"><span data-stu-id="bdd32-277"><a href="absoluteposition-property-ado.md">AbsolutePosition</a></span></span></p></td>
<td><p><span data-ttu-id="bdd32-278">不可用</span><span class="sxs-lookup"><span data-stu-id="bdd32-278">not available</span></span></p></td>
<td><p><span data-ttu-id="bdd32-279">不可用</span><span class="sxs-lookup"><span data-stu-id="bdd32-279">not available</span></span></p></td>
<td><p><span data-ttu-id="bdd32-280">读/写</span><span class="sxs-lookup"><span data-stu-id="bdd32-280">read/write</span></span></p></td>
<td><p><span data-ttu-id="bdd32-281">读/写</span><span class="sxs-lookup"><span data-stu-id="bdd32-281">read/write</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdd32-282"><a href="activeconnection-property-ado.md">ActiveConnection</a></span><span class="sxs-lookup"><span data-stu-id="bdd32-282"><a href="activeconnection-property-ado.md">ActiveConnection</a></span></span></p></td>
<td><p><span data-ttu-id="bdd32-283">读/写</span><span class="sxs-lookup"><span data-stu-id="bdd32-283">read/write</span></span></p></td>
<td><p><span data-ttu-id="bdd32-284">读/写</span><span class="sxs-lookup"><span data-stu-id="bdd32-284">read/write</span></span></p></td>
<td><p><span data-ttu-id="bdd32-285">读/写</span><span class="sxs-lookup"><span data-stu-id="bdd32-285">read/write</span></span></p></td>
<td><p><span data-ttu-id="bdd32-286">读/写</span><span class="sxs-lookup"><span data-stu-id="bdd32-286">read/write</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdd32-287"><a href="bof-eof-properties-ado.md">BOF</a></span><span class="sxs-lookup"><span data-stu-id="bdd32-287"><a href="bof-eof-properties-ado.md">BOF</a></span></span></p></td>
<td><p><span data-ttu-id="bdd32-288">只读</span><span class="sxs-lookup"><span data-stu-id="bdd32-288">read-only</span></span></p></td>
<td><p><span data-ttu-id="bdd32-289">只读</span><span class="sxs-lookup"><span data-stu-id="bdd32-289">read-only</span></span></p></td>
<td><p><span data-ttu-id="bdd32-290">只读</span><span class="sxs-lookup"><span data-stu-id="bdd32-290">read-only</span></span></p></td>
<td><p><span data-ttu-id="bdd32-291">只读</span><span class="sxs-lookup"><span data-stu-id="bdd32-291">read-only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdd32-292"><a href="bookmark-property-ado.md">Bookmark</a></span><span class="sxs-lookup"><span data-stu-id="bdd32-292"><a href="bookmark-property-ado.md">Bookmark</a></span></span></p></td>
<td><p><span data-ttu-id="bdd32-293">不可用</span><span class="sxs-lookup"><span data-stu-id="bdd32-293">not available</span></span></p></td>
<td><p><span data-ttu-id="bdd32-294">不可用</span><span class="sxs-lookup"><span data-stu-id="bdd32-294">not available</span></span></p></td>
<td><p><span data-ttu-id="bdd32-295">读/写</span><span class="sxs-lookup"><span data-stu-id="bdd32-295">read/write</span></span></p></td>
<td><p><span data-ttu-id="bdd32-296">读/写</span><span class="sxs-lookup"><span data-stu-id="bdd32-296">read/write</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdd32-297"><a href="cachesize-property-ado.md">CacheSize</a></span><span class="sxs-lookup"><span data-stu-id="bdd32-297"><a href="cachesize-property-ado.md">CacheSize</a></span></span></p></td>
<td><p><span data-ttu-id="bdd32-298">读/写</span><span class="sxs-lookup"><span data-stu-id="bdd32-298">read/write</span></span></p></td>
<td><p><span data-ttu-id="bdd32-299">读/写</span><span class="sxs-lookup"><span data-stu-id="bdd32-299">read/write</span></span></p></td>
<td><p><span data-ttu-id="bdd32-300">读/写</span><span class="sxs-lookup"><span data-stu-id="bdd32-300">read/write</span></span></p></td>
<td><p><span data-ttu-id="bdd32-301">读/写</span><span class="sxs-lookup"><span data-stu-id="bdd32-301">read/write</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdd32-302"><a href="cursorlocation-property-ado.md">CursorLocation</a></span><span class="sxs-lookup"><span data-stu-id="bdd32-302"><a href="cursorlocation-property-ado.md">CursorLocation</a></span></span></p></td>
<td><p><span data-ttu-id="bdd32-303">读/写</span><span class="sxs-lookup"><span data-stu-id="bdd32-303">read/write</span></span></p></td>
<td><p><span data-ttu-id="bdd32-304">读/写</span><span class="sxs-lookup"><span data-stu-id="bdd32-304">read/write</span></span></p></td>
<td><p><span data-ttu-id="bdd32-305">读/写</span><span class="sxs-lookup"><span data-stu-id="bdd32-305">read/write</span></span></p></td>
<td><p><span data-ttu-id="bdd32-306">读/写</span><span class="sxs-lookup"><span data-stu-id="bdd32-306">read/write</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdd32-307"><a href="cursortype-property-ado.md">CursorType</a></span><span class="sxs-lookup"><span data-stu-id="bdd32-307"><a href="cursortype-property-ado.md">CursorType</a></span></span></p></td>
<td><p><span data-ttu-id="bdd32-308">读/写</span><span class="sxs-lookup"><span data-stu-id="bdd32-308">read/write</span></span></p></td>
<td><p><span data-ttu-id="bdd32-309">读/写</span><span class="sxs-lookup"><span data-stu-id="bdd32-309">read/write</span></span></p></td>
<td><p><span data-ttu-id="bdd32-310">读/写</span><span class="sxs-lookup"><span data-stu-id="bdd32-310">read/write</span></span></p></td>
<td><p><span data-ttu-id="bdd32-311">读/写</span><span class="sxs-lookup"><span data-stu-id="bdd32-311">read/write</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdd32-312"><a href="editmode-property-ado.md">EditMode</a></span><span class="sxs-lookup"><span data-stu-id="bdd32-312"><a href="editmode-property-ado.md">EditMode</a></span></span></p></td>
<td><p><span data-ttu-id="bdd32-313">只读</span><span class="sxs-lookup"><span data-stu-id="bdd32-313">read-only</span></span></p></td>
<td><p><span data-ttu-id="bdd32-314">只读</span><span class="sxs-lookup"><span data-stu-id="bdd32-314">read-only</span></span></p></td>
<td><p><span data-ttu-id="bdd32-315">只读</span><span class="sxs-lookup"><span data-stu-id="bdd32-315">read-only</span></span></p></td>
<td><p><span data-ttu-id="bdd32-316">只读</span><span class="sxs-lookup"><span data-stu-id="bdd32-316">read-only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdd32-317"><a href="filter-property-ado.md">Filter</a></span><span class="sxs-lookup"><span data-stu-id="bdd32-317"><a href="filter-property-ado.md">Filter</a></span></span></p></td>
<td><p><span data-ttu-id="bdd32-318">读/写</span><span class="sxs-lookup"><span data-stu-id="bdd32-318">read/write</span></span></p></td>
<td><p><span data-ttu-id="bdd32-319">读/写</span><span class="sxs-lookup"><span data-stu-id="bdd32-319">read/write</span></span></p></td>
<td><p><span data-ttu-id="bdd32-320">读/写</span><span class="sxs-lookup"><span data-stu-id="bdd32-320">read/write</span></span></p></td>
<td><p><span data-ttu-id="bdd32-321">读/写</span><span class="sxs-lookup"><span data-stu-id="bdd32-321">read/write</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdd32-322"><a href="locktype-property-ado.md">LockType</a></span><span class="sxs-lookup"><span data-stu-id="bdd32-322"><a href="locktype-property-ado.md">LockType</a></span></span></p></td>
<td><p><span data-ttu-id="bdd32-323">读/写</span><span class="sxs-lookup"><span data-stu-id="bdd32-323">read/write</span></span></p></td>
<td><p><span data-ttu-id="bdd32-324">读/写</span><span class="sxs-lookup"><span data-stu-id="bdd32-324">read/write</span></span></p></td>
<td><p><span data-ttu-id="bdd32-325">读/写</span><span class="sxs-lookup"><span data-stu-id="bdd32-325">read/write</span></span></p></td>
<td><p><span data-ttu-id="bdd32-326">读/写</span><span class="sxs-lookup"><span data-stu-id="bdd32-326">read/write</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdd32-327"><a href="marshaloptions-property-ado.md">MarshalOptions</a></span><span class="sxs-lookup"><span data-stu-id="bdd32-327"><a href="marshaloptions-property-ado.md">MarshalOptions</a></span></span></p></td>
<td><p><span data-ttu-id="bdd32-328">读/写</span><span class="sxs-lookup"><span data-stu-id="bdd32-328">read/write</span></span></p></td>
<td><p><span data-ttu-id="bdd32-329">读/写</span><span class="sxs-lookup"><span data-stu-id="bdd32-329">read/write</span></span></p></td>
<td><p><span data-ttu-id="bdd32-330">读/写</span><span class="sxs-lookup"><span data-stu-id="bdd32-330">read/write</span></span></p></td>
<td><p><span data-ttu-id="bdd32-331">读/写</span><span class="sxs-lookup"><span data-stu-id="bdd32-331">read/write</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdd32-332"><a href="maxrecords-property-ado.md">MaxRecords</a></span><span class="sxs-lookup"><span data-stu-id="bdd32-332"><a href="maxrecords-property-ado.md">MaxRecords</a></span></span></p></td>
<td><p><span data-ttu-id="bdd32-333">读/写</span><span class="sxs-lookup"><span data-stu-id="bdd32-333">read/write</span></span></p></td>
<td><p><span data-ttu-id="bdd32-334">读/写</span><span class="sxs-lookup"><span data-stu-id="bdd32-334">read/write</span></span></p></td>
<td><p><span data-ttu-id="bdd32-335">读/写</span><span class="sxs-lookup"><span data-stu-id="bdd32-335">read/write</span></span></p></td>
<td><p><span data-ttu-id="bdd32-336">读/写</span><span class="sxs-lookup"><span data-stu-id="bdd32-336">read/write</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdd32-337"><a href="pagecount-property-ado.md">PageCount</a></span><span class="sxs-lookup"><span data-stu-id="bdd32-337"><a href="pagecount-property-ado.md">PageCount</a></span></span></p></td>
<td><p><span data-ttu-id="bdd32-338">读/写</span><span class="sxs-lookup"><span data-stu-id="bdd32-338">read/write</span></span></p></td>
<td><p><span data-ttu-id="bdd32-339">不可用</span><span class="sxs-lookup"><span data-stu-id="bdd32-339">not available</span></span></p></td>
<td><p><span data-ttu-id="bdd32-340">只读</span><span class="sxs-lookup"><span data-stu-id="bdd32-340">read-only</span></span></p></td>
<td><p><span data-ttu-id="bdd32-341">只读</span><span class="sxs-lookup"><span data-stu-id="bdd32-341">read-only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdd32-342"><a href="pagesize-property-ado.md">PageSize</a></span><span class="sxs-lookup"><span data-stu-id="bdd32-342"><a href="pagesize-property-ado.md">PageSize</a></span></span></p></td>
<td><p><span data-ttu-id="bdd32-343">读/写</span><span class="sxs-lookup"><span data-stu-id="bdd32-343">read/write</span></span></p></td>
<td><p><span data-ttu-id="bdd32-344">读/写</span><span class="sxs-lookup"><span data-stu-id="bdd32-344">read/write</span></span></p></td>
<td><p><span data-ttu-id="bdd32-345">读/写</span><span class="sxs-lookup"><span data-stu-id="bdd32-345">read/write</span></span></p></td>
<td><p><span data-ttu-id="bdd32-346">读/写</span><span class="sxs-lookup"><span data-stu-id="bdd32-346">read/write</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdd32-347"><a href="recordcount-property-ado.md">RecordCount</a></span><span class="sxs-lookup"><span data-stu-id="bdd32-347"><a href="recordcount-property-ado.md">RecordCount</a></span></span></p></td>
<td><p><span data-ttu-id="bdd32-348">读/写</span><span class="sxs-lookup"><span data-stu-id="bdd32-348">read/write</span></span></p></td>
<td><p><span data-ttu-id="bdd32-349">不可用</span><span class="sxs-lookup"><span data-stu-id="bdd32-349">not available</span></span></p></td>
<td><p><span data-ttu-id="bdd32-350">只读</span><span class="sxs-lookup"><span data-stu-id="bdd32-350">read-only</span></span></p></td>
<td><p><span data-ttu-id="bdd32-351">只读</span><span class="sxs-lookup"><span data-stu-id="bdd32-351">read-only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdd32-352"><a href="source-property-ado-recordset.md">Source</a></span><span class="sxs-lookup"><span data-stu-id="bdd32-352"><a href="source-property-ado-recordset.md">Source</a></span></span></p></td>
<td><p><span data-ttu-id="bdd32-353">读/写</span><span class="sxs-lookup"><span data-stu-id="bdd32-353">read/write</span></span></p></td>
<td><p><span data-ttu-id="bdd32-354">读/写</span><span class="sxs-lookup"><span data-stu-id="bdd32-354">read/write</span></span></p></td>
<td><p><span data-ttu-id="bdd32-355">读/写</span><span class="sxs-lookup"><span data-stu-id="bdd32-355">read/write</span></span></p></td>
<td><p><span data-ttu-id="bdd32-356">读/写</span><span class="sxs-lookup"><span data-stu-id="bdd32-356">read/write</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdd32-357"><a href="state-property-ado.md">State</a></span><span class="sxs-lookup"><span data-stu-id="bdd32-357"><a href="state-property-ado.md">State</a></span></span></p></td>
<td><p><span data-ttu-id="bdd32-358">只读</span><span class="sxs-lookup"><span data-stu-id="bdd32-358">read-only</span></span></p></td>
<td><p><span data-ttu-id="bdd32-359">只读</span><span class="sxs-lookup"><span data-stu-id="bdd32-359">read-only</span></span></p></td>
<td><p><span data-ttu-id="bdd32-360">只读</span><span class="sxs-lookup"><span data-stu-id="bdd32-360">read-only</span></span></p></td>
<td><p><span data-ttu-id="bdd32-361">只读</span><span class="sxs-lookup"><span data-stu-id="bdd32-361">read-only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdd32-362"><a href="status-property-ado-recordset.md">Status</a></span><span class="sxs-lookup"><span data-stu-id="bdd32-362"><a href="status-property-ado-recordset.md">Status</a></span></span></p></td>
<td><p><span data-ttu-id="bdd32-363">只读</span><span class="sxs-lookup"><span data-stu-id="bdd32-363">read-only</span></span></p></td>
<td><p><span data-ttu-id="bdd32-364">只读</span><span class="sxs-lookup"><span data-stu-id="bdd32-364">read-only</span></span></p></td>
<td><p><span data-ttu-id="bdd32-365">只读</span><span class="sxs-lookup"><span data-stu-id="bdd32-365">read-only</span></span></p></td>
<td><p><span data-ttu-id="bdd32-366">只读</span><span class="sxs-lookup"><span data-stu-id="bdd32-366">read-only</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="bdd32-367">在 1.0 版的 Microsoft OLE DB Provider for ODBC 中使用 ADO 时，[AbsolutePosition](absoluteposition-property-ado.md) 和 [AbsolutePage](absolutepage-property-ado.md) 属性是只写属性。</span><span class="sxs-lookup"><span data-stu-id="bdd32-367">The [AbsolutePosition](absoluteposition-property-ado.md) and [AbsolutePage](absolutepage-property-ado.md) properties are write-only when ADO is used with version 1.0 of the Microsoft OLE DB Provider for ODBC.</span></span>

<span data-ttu-id="bdd32-368">标准 ADO **Recordset** 方法的可用性：</span><span class="sxs-lookup"><span data-stu-id="bdd32-368">Availability of standard ADO **Recordset** methods:</span></span>

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
<th><p><span data-ttu-id="bdd32-369">方法</span><span class="sxs-lookup"><span data-stu-id="bdd32-369">Method</span></span></p></th>
<th><p><span data-ttu-id="bdd32-370">ForwardOnly</span><span class="sxs-lookup"><span data-stu-id="bdd32-370">ForwardOnly</span></span></p></th>
<th><p><span data-ttu-id="bdd32-371">动态</span><span class="sxs-lookup"><span data-stu-id="bdd32-371">Dynamic</span></span></p></th>
<th><p><span data-ttu-id="bdd32-372">键集</span><span class="sxs-lookup"><span data-stu-id="bdd32-372">Keyset</span></span></p></th>
<th><p><span data-ttu-id="bdd32-373">静态</span><span class="sxs-lookup"><span data-stu-id="bdd32-373">Static</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bdd32-374"><a href="addnew-method-ado.md">AddNew</a></span><span class="sxs-lookup"><span data-stu-id="bdd32-374"><a href="addnew-method-ado.md">AddNew</a></span></span></p></td>
<td><p><span data-ttu-id="bdd32-375">是</span><span class="sxs-lookup"><span data-stu-id="bdd32-375">Yes</span></span></p></td>
<td><p><span data-ttu-id="bdd32-376">是</span><span class="sxs-lookup"><span data-stu-id="bdd32-376">Yes</span></span></p></td>
<td><p><span data-ttu-id="bdd32-377">是</span><span class="sxs-lookup"><span data-stu-id="bdd32-377">Yes</span></span></p></td>
<td><p><span data-ttu-id="bdd32-378">是</span><span class="sxs-lookup"><span data-stu-id="bdd32-378">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdd32-379"><a href="cancel-method-ado.md">Cancel</a></span><span class="sxs-lookup"><span data-stu-id="bdd32-379"><a href="cancel-method-ado.md">Cancel</a></span></span></p></td>
<td><p><span data-ttu-id="bdd32-380">是</span><span class="sxs-lookup"><span data-stu-id="bdd32-380">Yes</span></span></p></td>
<td><p><span data-ttu-id="bdd32-381">是</span><span class="sxs-lookup"><span data-stu-id="bdd32-381">Yes</span></span></p></td>
<td><p><span data-ttu-id="bdd32-382">是</span><span class="sxs-lookup"><span data-stu-id="bdd32-382">Yes</span></span></p></td>
<td><p><span data-ttu-id="bdd32-383">是</span><span class="sxs-lookup"><span data-stu-id="bdd32-383">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdd32-384"><a href="cancelbatch-method-ado.md">CancelBatch</a></span><span class="sxs-lookup"><span data-stu-id="bdd32-384"><a href="cancelbatch-method-ado.md">CancelBatch</a></span></span></p></td>
<td><p><span data-ttu-id="bdd32-385">是</span><span class="sxs-lookup"><span data-stu-id="bdd32-385">Yes</span></span></p></td>
<td><p><span data-ttu-id="bdd32-386">是</span><span class="sxs-lookup"><span data-stu-id="bdd32-386">Yes</span></span></p></td>
<td><p><span data-ttu-id="bdd32-387">是</span><span class="sxs-lookup"><span data-stu-id="bdd32-387">Yes</span></span></p></td>
<td><p><span data-ttu-id="bdd32-388">是</span><span class="sxs-lookup"><span data-stu-id="bdd32-388">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdd32-389"><a href="cancelupdate-method-ado.md">CancelUpdate</a></span><span class="sxs-lookup"><span data-stu-id="bdd32-389"><a href="cancelupdate-method-ado.md">CancelUpdate</a></span></span></p></td>
<td><p><span data-ttu-id="bdd32-390">是</span><span class="sxs-lookup"><span data-stu-id="bdd32-390">Yes</span></span></p></td>
<td><p><span data-ttu-id="bdd32-391">是</span><span class="sxs-lookup"><span data-stu-id="bdd32-391">Yes</span></span></p></td>
<td><p><span data-ttu-id="bdd32-392">是</span><span class="sxs-lookup"><span data-stu-id="bdd32-392">Yes</span></span></p></td>
<td><p><span data-ttu-id="bdd32-393">是</span><span class="sxs-lookup"><span data-stu-id="bdd32-393">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdd32-394"><a href="clone-method-ado.md">Clone</a></span><span class="sxs-lookup"><span data-stu-id="bdd32-394"><a href="clone-method-ado.md">Clone</a></span></span></p></td>
<td><p><span data-ttu-id="bdd32-395">否</span><span class="sxs-lookup"><span data-stu-id="bdd32-395">No</span></span></p></td>
<td><p><span data-ttu-id="bdd32-396">否</span><span class="sxs-lookup"><span data-stu-id="bdd32-396">No</span></span></p></td>
<td><p><span data-ttu-id="bdd32-397">是</span><span class="sxs-lookup"><span data-stu-id="bdd32-397">Yes</span></span></p></td>
<td><p><span data-ttu-id="bdd32-398">是</span><span class="sxs-lookup"><span data-stu-id="bdd32-398">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdd32-399"><a href="close-method-ado.md">Close</a></span><span class="sxs-lookup"><span data-stu-id="bdd32-399"><a href="close-method-ado.md">Close</a></span></span></p></td>
<td><p><span data-ttu-id="bdd32-400">是</span><span class="sxs-lookup"><span data-stu-id="bdd32-400">Yes</span></span></p></td>
<td><p><span data-ttu-id="bdd32-401">是</span><span class="sxs-lookup"><span data-stu-id="bdd32-401">Yes</span></span></p></td>
<td><p><span data-ttu-id="bdd32-402">是</span><span class="sxs-lookup"><span data-stu-id="bdd32-402">Yes</span></span></p></td>
<td><p><span data-ttu-id="bdd32-403">是</span><span class="sxs-lookup"><span data-stu-id="bdd32-403">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdd32-404"><a href="delete-method-ado-recordset.md">Delete</a></span><span class="sxs-lookup"><span data-stu-id="bdd32-404"><a href="delete-method-ado-recordset.md">Delete</a></span></span></p></td>
<td><p><span data-ttu-id="bdd32-405">是</span><span class="sxs-lookup"><span data-stu-id="bdd32-405">Yes</span></span></p></td>
<td><p><span data-ttu-id="bdd32-406">是</span><span class="sxs-lookup"><span data-stu-id="bdd32-406">Yes</span></span></p></td>
<td><p><span data-ttu-id="bdd32-407">是</span><span class="sxs-lookup"><span data-stu-id="bdd32-407">Yes</span></span></p></td>
<td><p><span data-ttu-id="bdd32-408">是</span><span class="sxs-lookup"><span data-stu-id="bdd32-408">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdd32-409"><a href="getrows-method-ado.md">GetRows</a></span><span class="sxs-lookup"><span data-stu-id="bdd32-409"><a href="getrows-method-ado.md">GetRows</a></span></span></p></td>
<td><p><span data-ttu-id="bdd32-410">是</span><span class="sxs-lookup"><span data-stu-id="bdd32-410">Yes</span></span></p></td>
<td><p><span data-ttu-id="bdd32-411">是</span><span class="sxs-lookup"><span data-stu-id="bdd32-411">Yes</span></span></p></td>
<td><p><span data-ttu-id="bdd32-412">是</span><span class="sxs-lookup"><span data-stu-id="bdd32-412">Yes</span></span></p></td>
<td><p><span data-ttu-id="bdd32-413">是</span><span class="sxs-lookup"><span data-stu-id="bdd32-413">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdd32-414"><a href="move-method-ado.md">移动</a></span><span class="sxs-lookup"><span data-stu-id="bdd32-414"><a href="move-method-ado.md">Move</a></span></span></p></td>
<td><p><span data-ttu-id="bdd32-415">是</span><span class="sxs-lookup"><span data-stu-id="bdd32-415">Yes</span></span></p></td>
<td><p><span data-ttu-id="bdd32-416">是</span><span class="sxs-lookup"><span data-stu-id="bdd32-416">Yes</span></span></p></td>
<td><p><span data-ttu-id="bdd32-417">是</span><span class="sxs-lookup"><span data-stu-id="bdd32-417">Yes</span></span></p></td>
<td><p><span data-ttu-id="bdd32-418">是</span><span class="sxs-lookup"><span data-stu-id="bdd32-418">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdd32-419"><a href="movefirst-movelast-movenext-and-moveprevious-methods-ado.md">MoveFirst</a></span><span class="sxs-lookup"><span data-stu-id="bdd32-419"><a href="movefirst-movelast-movenext-and-moveprevious-methods-ado.md">MoveFirst</a></span></span></p></td>
<td><p><span data-ttu-id="bdd32-420">是</span><span class="sxs-lookup"><span data-stu-id="bdd32-420">Yes</span></span></p></td>
<td><p><span data-ttu-id="bdd32-421">是</span><span class="sxs-lookup"><span data-stu-id="bdd32-421">Yes</span></span></p></td>
<td><p><span data-ttu-id="bdd32-422">是</span><span class="sxs-lookup"><span data-stu-id="bdd32-422">Yes</span></span></p></td>
<td><p><span data-ttu-id="bdd32-423">是</span><span class="sxs-lookup"><span data-stu-id="bdd32-423">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdd32-424"><a href="movefirst-movelast-movenext-and-moveprevious-methods-ado.md">MoveLast</a></span><span class="sxs-lookup"><span data-stu-id="bdd32-424"><a href="movefirst-movelast-movenext-and-moveprevious-methods-ado.md">MoveLast</a></span></span></p></td>
<td><p><span data-ttu-id="bdd32-425">否</span><span class="sxs-lookup"><span data-stu-id="bdd32-425">No</span></span></p></td>
<td><p><span data-ttu-id="bdd32-426">是</span><span class="sxs-lookup"><span data-stu-id="bdd32-426">Yes</span></span></p></td>
<td><p><span data-ttu-id="bdd32-427">是</span><span class="sxs-lookup"><span data-stu-id="bdd32-427">Yes</span></span></p></td>
<td><p><span data-ttu-id="bdd32-428">是</span><span class="sxs-lookup"><span data-stu-id="bdd32-428">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdd32-429"><a href="movefirst-movelast-movenext-and-moveprevious-methods-ado.md">MoveNext</a></span><span class="sxs-lookup"><span data-stu-id="bdd32-429"><a href="movefirst-movelast-movenext-and-moveprevious-methods-ado.md">MoveNext</a></span></span></p></td>
<td><p><span data-ttu-id="bdd32-430">是</span><span class="sxs-lookup"><span data-stu-id="bdd32-430">Yes</span></span></p></td>
<td><p><span data-ttu-id="bdd32-431">是</span><span class="sxs-lookup"><span data-stu-id="bdd32-431">Yes</span></span></p></td>
<td><p><span data-ttu-id="bdd32-432">是</span><span class="sxs-lookup"><span data-stu-id="bdd32-432">Yes</span></span></p></td>
<td><p><span data-ttu-id="bdd32-433">是</span><span class="sxs-lookup"><span data-stu-id="bdd32-433">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdd32-434"><a href="movefirst-movelast-movenext-and-moveprevious-methods-ado.md">MovePrevious</a></span><span class="sxs-lookup"><span data-stu-id="bdd32-434"><a href="movefirst-movelast-movenext-and-moveprevious-methods-ado.md">MovePrevious</a></span></span></p></td>
<td><p><span data-ttu-id="bdd32-435">否</span><span class="sxs-lookup"><span data-stu-id="bdd32-435">No</span></span></p></td>
<td><p><span data-ttu-id="bdd32-436">是</span><span class="sxs-lookup"><span data-stu-id="bdd32-436">Yes</span></span></p></td>
<td><p><span data-ttu-id="bdd32-437">是</span><span class="sxs-lookup"><span data-stu-id="bdd32-437">Yes</span></span></p></td>
<td><p><span data-ttu-id="bdd32-438">是</span><span class="sxs-lookup"><span data-stu-id="bdd32-438">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdd32-439"><a href="nextrecordset-method-ado.md">NextRecordset</a>\*</span><span class="sxs-lookup"><span data-stu-id="bdd32-439"><a href="nextrecordset-method-ado.md">NextRecordset</a>\*</span></span></p></td>
<td><p><span data-ttu-id="bdd32-440">是</span><span class="sxs-lookup"><span data-stu-id="bdd32-440">Yes</span></span></p></td>
<td><p><span data-ttu-id="bdd32-441">是</span><span class="sxs-lookup"><span data-stu-id="bdd32-441">Yes</span></span></p></td>
<td><p><span data-ttu-id="bdd32-442">是</span><span class="sxs-lookup"><span data-stu-id="bdd32-442">Yes</span></span></p></td>
<td><p><span data-ttu-id="bdd32-443">是</span><span class="sxs-lookup"><span data-stu-id="bdd32-443">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdd32-444"><a href="open-method-ado-recordset.md">Open</a></span><span class="sxs-lookup"><span data-stu-id="bdd32-444"><a href="open-method-ado-recordset.md">Open</a></span></span></p></td>
<td><p><span data-ttu-id="bdd32-445">是</span><span class="sxs-lookup"><span data-stu-id="bdd32-445">Yes</span></span></p></td>
<td><p><span data-ttu-id="bdd32-446">是</span><span class="sxs-lookup"><span data-stu-id="bdd32-446">Yes</span></span></p></td>
<td><p><span data-ttu-id="bdd32-447">是</span><span class="sxs-lookup"><span data-stu-id="bdd32-447">Yes</span></span></p></td>
<td><p><span data-ttu-id="bdd32-448">是</span><span class="sxs-lookup"><span data-stu-id="bdd32-448">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdd32-449"><a href="requery-method-ado.md">Requery</a></span><span class="sxs-lookup"><span data-stu-id="bdd32-449"><a href="requery-method-ado.md">Requery</a></span></span></p></td>
<td><p><span data-ttu-id="bdd32-450">是</span><span class="sxs-lookup"><span data-stu-id="bdd32-450">Yes</span></span></p></td>
<td><p><span data-ttu-id="bdd32-451">是</span><span class="sxs-lookup"><span data-stu-id="bdd32-451">Yes</span></span></p></td>
<td><p><span data-ttu-id="bdd32-452">是</span><span class="sxs-lookup"><span data-stu-id="bdd32-452">Yes</span></span></p></td>
<td><p><span data-ttu-id="bdd32-453">是</span><span class="sxs-lookup"><span data-stu-id="bdd32-453">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdd32-454"><a href="resync-method-ado.md">Resync</a></span><span class="sxs-lookup"><span data-stu-id="bdd32-454"><a href="resync-method-ado.md">Resync</a></span></span></p></td>
<td><p><span data-ttu-id="bdd32-455">否</span><span class="sxs-lookup"><span data-stu-id="bdd32-455">No</span></span></p></td>
<td><p><span data-ttu-id="bdd32-456">否</span><span class="sxs-lookup"><span data-stu-id="bdd32-456">No</span></span></p></td>
<td><p><span data-ttu-id="bdd32-457">是</span><span class="sxs-lookup"><span data-stu-id="bdd32-457">Yes</span></span></p></td>
<td><p><span data-ttu-id="bdd32-458">是</span><span class="sxs-lookup"><span data-stu-id="bdd32-458">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdd32-459"><a href="supports-method-ado.md">支持</a></span><span class="sxs-lookup"><span data-stu-id="bdd32-459"><a href="supports-method-ado.md">Supports</a></span></span></p></td>
<td><p><span data-ttu-id="bdd32-460">是</span><span class="sxs-lookup"><span data-stu-id="bdd32-460">Yes</span></span></p></td>
<td><p><span data-ttu-id="bdd32-461">是</span><span class="sxs-lookup"><span data-stu-id="bdd32-461">Yes</span></span></p></td>
<td><p><span data-ttu-id="bdd32-462">是</span><span class="sxs-lookup"><span data-stu-id="bdd32-462">Yes</span></span></p></td>
<td><p><span data-ttu-id="bdd32-463">是</span><span class="sxs-lookup"><span data-stu-id="bdd32-463">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdd32-464"><a href="update-method-ado.md">更新</a></span><span class="sxs-lookup"><span data-stu-id="bdd32-464"><a href="update-method-ado.md">Update</a></span></span></p></td>
<td><p><span data-ttu-id="bdd32-465">是</span><span class="sxs-lookup"><span data-stu-id="bdd32-465">Yes</span></span></p></td>
<td><p><span data-ttu-id="bdd32-466">是</span><span class="sxs-lookup"><span data-stu-id="bdd32-466">Yes</span></span></p></td>
<td><p><span data-ttu-id="bdd32-467">是</span><span class="sxs-lookup"><span data-stu-id="bdd32-467">Yes</span></span></p></td>
<td><p><span data-ttu-id="bdd32-468">是</span><span class="sxs-lookup"><span data-stu-id="bdd32-468">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdd32-469"><a href="updatebatch-method-ado.md">UpdateBatch</a></span><span class="sxs-lookup"><span data-stu-id="bdd32-469"><a href="updatebatch-method-ado.md">UpdateBatch</a></span></span></p></td>
<td><p><span data-ttu-id="bdd32-470">是</span><span class="sxs-lookup"><span data-stu-id="bdd32-470">Yes</span></span></p></td>
<td><p><span data-ttu-id="bdd32-471">是</span><span class="sxs-lookup"><span data-stu-id="bdd32-471">Yes</span></span></p></td>
<td><p><span data-ttu-id="bdd32-472">是</span><span class="sxs-lookup"><span data-stu-id="bdd32-472">Yes</span></span></p></td>
<td><p><span data-ttu-id="bdd32-473">是</span><span class="sxs-lookup"><span data-stu-id="bdd32-473">Yes</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="bdd32-474">\*不受 Microsoft Access 数据库支持。</span><span class="sxs-lookup"><span data-stu-id="bdd32-474">\*Not supported for Microsoft Access databases.</span></span>

## <a name="dynamic-properties"></a><span data-ttu-id="bdd32-475">动态属性</span><span class="sxs-lookup"><span data-stu-id="bdd32-475">Dynamic Properties</span></span>

<span data-ttu-id="bdd32-476">Microsoft OLE DB Provider for ODBC 会将多个动态属性插入到未打开的 **Connection**、[Recordset](connection-object-ado.md) 和 [Command](recordset-object-ado.md) 对象的 [Properties](command-object-ado.md) 集合中。</span><span class="sxs-lookup"><span data-stu-id="bdd32-476">The Microsoft OLE DB Provider for ODBC inserts several dynamic properties into the **Properties** collection of the unopened [Connection](connection-object-ado.md), [Recordset](recordset-object-ado.md), and [Command](command-object-ado.md) objects.</span></span>

<span data-ttu-id="bdd32-p118">下面的表是每个动态属性的 ADO 和 OLE DB 名称的交叉索引。《OLE DB 程序员参考》使用术语"说明"来引用 ADO 属性名。您可以在《OLE DB 程序员参考》中找到有关这些属性的详细信息。请在"索引"中搜索 OLE DB 属性名，或者请参阅"附录 C：OLE DB 属性"。</span><span class="sxs-lookup"><span data-stu-id="bdd32-p118">The tables below are a cross-index of the ADO and OLE DB names for each dynamic property. The OLE DB Programmer's Reference refers to an ADO property name by the term, "Description." You can find more information about these properties in the OLE DB Programmer's Reference. Search for the OLE DB property name in the Index or see Appendix C: OLE DB Properties.</span></span>

## <a name="connection-dynamic-properties"></a><span data-ttu-id="bdd32-481">Connection 动态属性</span><span class="sxs-lookup"><span data-stu-id="bdd32-481">Connection Dynamic Properties</span></span>

<span data-ttu-id="bdd32-482">以下属性将被添加到 **Connection** 对象的 **Properties** 集合中。</span><span class="sxs-lookup"><span data-stu-id="bdd32-482">The following properties are added to the **Connection** object's **Properties** collection.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="bdd32-483">ADO 属性名</span><span class="sxs-lookup"><span data-stu-id="bdd32-483">ADO Property Name</span></span></p></th>
<th><p><span data-ttu-id="bdd32-484">OLE DB 属性名</span><span class="sxs-lookup"><span data-stu-id="bdd32-484">OLE DB Property Name</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bdd32-485">Active Sessions</span><span class="sxs-lookup"><span data-stu-id="bdd32-485">Active Sessions</span></span></p></td>
<td><p><span data-ttu-id="bdd32-486">DBPROP_ACTIVESESSIONS</span><span class="sxs-lookup"><span data-stu-id="bdd32-486">DBPROP_ACTIVESESSIONS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdd32-487">Asynchable Abort</span><span class="sxs-lookup"><span data-stu-id="bdd32-487">Asynchable Abort</span></span></p></td>
<td><p><span data-ttu-id="bdd32-488">DBPROP_ASYNCTXNABORT</span><span class="sxs-lookup"><span data-stu-id="bdd32-488">DBPROP_ASYNCTXNABORT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdd32-489">Asynchable Commit</span><span class="sxs-lookup"><span data-stu-id="bdd32-489">Asynchable Commit</span></span></p></td>
<td><p><span data-ttu-id="bdd32-490">DBPROP_ASYNCTNXCOMMIT</span><span class="sxs-lookup"><span data-stu-id="bdd32-490">DBPROP_ASYNCTNXCOMMIT</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdd32-491">Autocommit Isolation Levels</span><span class="sxs-lookup"><span data-stu-id="bdd32-491">Autocommit Isolation Levels</span></span></p></td>
<td><p><span data-ttu-id="bdd32-492">DBPROP_SESS_AUTOCOMMITISOLEVELS</span><span class="sxs-lookup"><span data-stu-id="bdd32-492">DBPROP_SESS_AUTOCOMMITISOLEVELS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdd32-493">Catalog Location</span><span class="sxs-lookup"><span data-stu-id="bdd32-493">Catalog Location</span></span></p></td>
<td><p><span data-ttu-id="bdd32-494">DBPROP_CATALOGLOCATION</span><span class="sxs-lookup"><span data-stu-id="bdd32-494">DBPROP_CATALOGLOCATION</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdd32-495">Catalog Term</span><span class="sxs-lookup"><span data-stu-id="bdd32-495">Catalog Term</span></span></p></td>
<td><p><span data-ttu-id="bdd32-496">DBPROP_CATALOGTERM</span><span class="sxs-lookup"><span data-stu-id="bdd32-496">DBPROP_CATALOGTERM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdd32-497">Column Definition</span><span class="sxs-lookup"><span data-stu-id="bdd32-497">Column Definition</span></span></p></td>
<td><p><span data-ttu-id="bdd32-498">DBPROP_COLUMNDEFINITION</span><span class="sxs-lookup"><span data-stu-id="bdd32-498">DBPROP_COLUMNDEFINITION</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdd32-499">Connect Timeout</span><span class="sxs-lookup"><span data-stu-id="bdd32-499">Connect Timeout</span></span></p></td>
<td><p><span data-ttu-id="bdd32-500">DBPROP_INIT_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="bdd32-500">DBPROP_INIT_TIMEOUT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdd32-501">Current Catalog</span><span class="sxs-lookup"><span data-stu-id="bdd32-501">Current Catalog</span></span></p></td>
<td><p><span data-ttu-id="bdd32-502">DBPROP_CURRENTCATALOG</span><span class="sxs-lookup"><span data-stu-id="bdd32-502">DBPROP_CURRENTCATALOG</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdd32-503">Data Source</span><span class="sxs-lookup"><span data-stu-id="bdd32-503">Data Source</span></span></p></td>
<td><p><span data-ttu-id="bdd32-504">DBPROP_INIT_DATASOURCE</span><span class="sxs-lookup"><span data-stu-id="bdd32-504">DBPROP_INIT_DATASOURCE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdd32-505">Data Source Name</span><span class="sxs-lookup"><span data-stu-id="bdd32-505">Data Source Name</span></span></p></td>
<td><p><span data-ttu-id="bdd32-506">DBPROP_DATASOURCENAME</span><span class="sxs-lookup"><span data-stu-id="bdd32-506">DBPROP_DATASOURCENAME</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdd32-507">Data Source Object Threading Model</span><span class="sxs-lookup"><span data-stu-id="bdd32-507">Data Source Object Threading Model</span></span></p></td>
<td><p><span data-ttu-id="bdd32-508">DBPROP_DSOTHREADMODEL</span><span class="sxs-lookup"><span data-stu-id="bdd32-508">DBPROP_DSOTHREADMODEL</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdd32-509">DBMS Name</span><span class="sxs-lookup"><span data-stu-id="bdd32-509">DBMS Name</span></span></p></td>
<td><p><span data-ttu-id="bdd32-510">DBPROP_DBMSNAME</span><span class="sxs-lookup"><span data-stu-id="bdd32-510">DBPROP_DBMSNAME</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdd32-511">DBMS Version</span><span class="sxs-lookup"><span data-stu-id="bdd32-511">DBMS Version</span></span></p></td>
<td><p><span data-ttu-id="bdd32-512">DBPROP_DBMSVER</span><span class="sxs-lookup"><span data-stu-id="bdd32-512">DBPROP_DBMSVER</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdd32-513">Extended Properties</span><span class="sxs-lookup"><span data-stu-id="bdd32-513">Extended Properties</span></span></p></td>
<td><p><span data-ttu-id="bdd32-514">DBPROP_INIT_PROVIDERSTRING</span><span class="sxs-lookup"><span data-stu-id="bdd32-514">DBPROP_INIT_PROVIDERSTRING</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdd32-515">GROUP BY Support</span><span class="sxs-lookup"><span data-stu-id="bdd32-515">GROUP BY Support</span></span></p></td>
<td><p><span data-ttu-id="bdd32-516">DBPROP_GROUPBY</span><span class="sxs-lookup"><span data-stu-id="bdd32-516">DBPROP_GROUPBY</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdd32-517">Heterogeneous Table Support</span><span class="sxs-lookup"><span data-stu-id="bdd32-517">Heterogeneous Table Support</span></span></p></td>
<td><p><span data-ttu-id="bdd32-518">DBPROP_HETEROGENEOUSTABLES</span><span class="sxs-lookup"><span data-stu-id="bdd32-518">DBPROP_HETEROGENEOUSTABLES</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdd32-519">Identifier Case Sensitivity</span><span class="sxs-lookup"><span data-stu-id="bdd32-519">Identifier Case Sensitivity</span></span></p></td>
<td><p><span data-ttu-id="bdd32-520">DBPROP_IDENTIFIERCASE</span><span class="sxs-lookup"><span data-stu-id="bdd32-520">DBPROP_IDENTIFIERCASE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdd32-521">Initial Catalog</span><span class="sxs-lookup"><span data-stu-id="bdd32-521">Initial Catalog</span></span></p></td>
<td><p><span data-ttu-id="bdd32-522">DBPROP_INIT_CATALOG</span><span class="sxs-lookup"><span data-stu-id="bdd32-522">DBPROP_INIT_CATALOG</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdd32-523">Isolation Levels</span><span class="sxs-lookup"><span data-stu-id="bdd32-523">Isolation Levels</span></span></p></td>
<td><p><span data-ttu-id="bdd32-524">DBPROP_SUPPORTEDTXNISOLEVELS</span><span class="sxs-lookup"><span data-stu-id="bdd32-524">DBPROP_SUPPORTEDTXNISOLEVELS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdd32-525">Isolation Retention</span><span class="sxs-lookup"><span data-stu-id="bdd32-525">Isolation Retention</span></span></p></td>
<td><p><span data-ttu-id="bdd32-526">DBPROP_SUPPORTEDTXNISORETAIN</span><span class="sxs-lookup"><span data-stu-id="bdd32-526">DBPROP_SUPPORTEDTXNISORETAIN</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdd32-527">Locale Identifier</span><span class="sxs-lookup"><span data-stu-id="bdd32-527">Locale Identifier</span></span></p></td>
<td><p><span data-ttu-id="bdd32-528">DBPROP_INIT_LCID</span><span class="sxs-lookup"><span data-stu-id="bdd32-528">DBPROP_INIT_LCID</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdd32-529">Location</span><span class="sxs-lookup"><span data-stu-id="bdd32-529">Location</span></span></p></td>
<td><p><span data-ttu-id="bdd32-530">DBPROP_INIT_LOCATION</span><span class="sxs-lookup"><span data-stu-id="bdd32-530">DBPROP_INIT_LOCATION</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdd32-531">Maximum Index Size</span><span class="sxs-lookup"><span data-stu-id="bdd32-531">Maximum Index Size</span></span></p></td>
<td><p><span data-ttu-id="bdd32-532">DBPROP_MAXINDEXSIZE</span><span class="sxs-lookup"><span data-stu-id="bdd32-532">DBPROP_MAXINDEXSIZE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdd32-533">Maximum Row Size</span><span class="sxs-lookup"><span data-stu-id="bdd32-533">Maximum Row Size</span></span></p></td>
<td><p><span data-ttu-id="bdd32-534">DBPROP_MAXROWSIZE</span><span class="sxs-lookup"><span data-stu-id="bdd32-534">DBPROP_MAXROWSIZE</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdd32-535">Maximum Row Size Includes BLOB</span><span class="sxs-lookup"><span data-stu-id="bdd32-535">Maximum Row Size Includes BLOB</span></span></p></td>
<td><p><span data-ttu-id="bdd32-536">DBPROP_MAXROWSIZEINCLUDESBLOB</span><span class="sxs-lookup"><span data-stu-id="bdd32-536">DBPROP_MAXROWSIZEINCLUDESBLOB</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdd32-537">Maximum Tables in SELECT</span><span class="sxs-lookup"><span data-stu-id="bdd32-537">Maximum Tables in SELECT</span></span></p></td>
<td><p><span data-ttu-id="bdd32-538">DBPROP_MAXTABLESINSELECT</span><span class="sxs-lookup"><span data-stu-id="bdd32-538">DBPROP_MAXTABLESINSELECT</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdd32-539">Mode</span><span class="sxs-lookup"><span data-stu-id="bdd32-539">Mode</span></span></p></td>
<td><p><span data-ttu-id="bdd32-540">DBPROP_INIT_MODE</span><span class="sxs-lookup"><span data-stu-id="bdd32-540">DBPROP_INIT_MODE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdd32-541">Multiple Parameter Sets</span><span class="sxs-lookup"><span data-stu-id="bdd32-541">Multiple Parameter Sets</span></span></p></td>
<td><p><span data-ttu-id="bdd32-542">DBPROP_MULTIPLEPARAMSETS</span><span class="sxs-lookup"><span data-stu-id="bdd32-542">DBPROP_MULTIPLEPARAMSETS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdd32-543">Multiple Results</span><span class="sxs-lookup"><span data-stu-id="bdd32-543">Multiple Results</span></span></p></td>
<td><p><span data-ttu-id="bdd32-544">DBPROP_MULTIPLERESULTS</span><span class="sxs-lookup"><span data-stu-id="bdd32-544">DBPROP_MULTIPLERESULTS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdd32-545">Multiple Storage Objects</span><span class="sxs-lookup"><span data-stu-id="bdd32-545">Multiple Storage Objects</span></span></p></td>
<td><p><span data-ttu-id="bdd32-546">DBPROP_MULTIPLESTORAGEOBJECTS</span><span class="sxs-lookup"><span data-stu-id="bdd32-546">DBPROP_MULTIPLESTORAGEOBJECTS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdd32-547">Multi-Table Update</span><span class="sxs-lookup"><span data-stu-id="bdd32-547">Multi-Table Update</span></span></p></td>
<td><p><span data-ttu-id="bdd32-548">DBPROP_MULTITABLEUPDATE</span><span class="sxs-lookup"><span data-stu-id="bdd32-548">DBPROP_MULTITABLEUPDATE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdd32-549">NULL Collation Order</span><span class="sxs-lookup"><span data-stu-id="bdd32-549">NULL Collation Order</span></span></p></td>
<td><p><span data-ttu-id="bdd32-550">DBPROP_NULLCOLLATION</span><span class="sxs-lookup"><span data-stu-id="bdd32-550">DBPROP_NULLCOLLATION</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdd32-551">NULL Concatenation Behavior</span><span class="sxs-lookup"><span data-stu-id="bdd32-551">NULL Concatenation Behavior</span></span></p></td>
<td><p><span data-ttu-id="bdd32-552">DBPROP_CONCATNULLBEHAVIOR</span><span class="sxs-lookup"><span data-stu-id="bdd32-552">DBPROP_CONCATNULLBEHAVIOR</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdd32-553">OLE DB Services</span><span class="sxs-lookup"><span data-stu-id="bdd32-553">OLE DB Services</span></span></p></td>
<td><p><span data-ttu-id="bdd32-554">DBPROP_INIT_OLEDBSERVICES</span><span class="sxs-lookup"><span data-stu-id="bdd32-554">DBPROP_INIT_OLEDBSERVICES</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdd32-555">OLE DB Version</span><span class="sxs-lookup"><span data-stu-id="bdd32-555">OLE DB Version</span></span></p></td>
<td><p><span data-ttu-id="bdd32-556">DBPROP_PROVIDEROLEDBVER</span><span class="sxs-lookup"><span data-stu-id="bdd32-556">DBPROP_PROVIDEROLEDBVER</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdd32-557">OLE Object Support</span><span class="sxs-lookup"><span data-stu-id="bdd32-557">OLE Object Support</span></span></p></td>
<td><p><span data-ttu-id="bdd32-558">DBPROP_OLEOBJECTS</span><span class="sxs-lookup"><span data-stu-id="bdd32-558">DBPROP_OLEOBJECTS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdd32-559">Open Rowset Support</span><span class="sxs-lookup"><span data-stu-id="bdd32-559">Open Rowset Support</span></span></p></td>
<td><p><span data-ttu-id="bdd32-560">DBPROP_OPENROWSETSUPPORT</span><span class="sxs-lookup"><span data-stu-id="bdd32-560">DBPROP_OPENROWSETSUPPORT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdd32-561">ORDER BY Columns in Select List</span><span class="sxs-lookup"><span data-stu-id="bdd32-561">ORDER BY Columns in Select List</span></span></p></td>
<td><p><span data-ttu-id="bdd32-562">DBPROP_ORDERBYCOLUMNSINSELECT</span><span class="sxs-lookup"><span data-stu-id="bdd32-562">DBPROP_ORDERBYCOLUMNSINSELECT</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdd32-563">Output Parameter Availability</span><span class="sxs-lookup"><span data-stu-id="bdd32-563">Output Parameter Availability</span></span></p></td>
<td><p><span data-ttu-id="bdd32-564">DBPROP_OUTPUTPARAMETERAVAILABILITY</span><span class="sxs-lookup"><span data-stu-id="bdd32-564">DBPROP_OUTPUTPARAMETERAVAILABILITY</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdd32-565">Password</span><span class="sxs-lookup"><span data-stu-id="bdd32-565">Password</span></span></p></td>
<td><p><span data-ttu-id="bdd32-566">DBPROP_AUTH_PASSWORD</span><span class="sxs-lookup"><span data-stu-id="bdd32-566">DBPROP_AUTH_PASSWORD</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdd32-567">Pass By Ref Accessors</span><span class="sxs-lookup"><span data-stu-id="bdd32-567">Pass By Ref Accessors</span></span></p></td>
<td><p><span data-ttu-id="bdd32-568">DBPROP_BYREFACCESSORS</span><span class="sxs-lookup"><span data-stu-id="bdd32-568">DBPROP_BYREFACCESSORS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdd32-569">Persist Security Info</span><span class="sxs-lookup"><span data-stu-id="bdd32-569">Persist Security Info</span></span></p></td>
<td><p><span data-ttu-id="bdd32-570">DBPROP_AUTH_PERSIST_SENSITIVE_AUTHINFO</span><span class="sxs-lookup"><span data-stu-id="bdd32-570">DBPROP_AUTH_PERSIST_SENSITIVE_AUTHINFO</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdd32-571">Persistent ID Type</span><span class="sxs-lookup"><span data-stu-id="bdd32-571">Persistent ID Type</span></span></p></td>
<td><p><span data-ttu-id="bdd32-572">DBPROP_PERSISTENTIDTYPE</span><span class="sxs-lookup"><span data-stu-id="bdd32-572">DBPROP_PERSISTENTIDTYPE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdd32-573">Prepare Abort Behavior</span><span class="sxs-lookup"><span data-stu-id="bdd32-573">Prepare Abort Behavior</span></span></p></td>
<td><p><span data-ttu-id="bdd32-574">DBPROP_PREPAREABORTBEHAVIOR</span><span class="sxs-lookup"><span data-stu-id="bdd32-574">DBPROP_PREPAREABORTBEHAVIOR</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdd32-575">Prepare Commit Behavior</span><span class="sxs-lookup"><span data-stu-id="bdd32-575">Prepare Commit Behavior</span></span></p></td>
<td><p><span data-ttu-id="bdd32-576">DBPROP_PREPARECOMMITBEHAVIOR</span><span class="sxs-lookup"><span data-stu-id="bdd32-576">DBPROP_PREPARECOMMITBEHAVIOR</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdd32-577">Procedure Term</span><span class="sxs-lookup"><span data-stu-id="bdd32-577">Procedure Term</span></span></p></td>
<td><p><span data-ttu-id="bdd32-578">DBPROP_PROCEDURETERM</span><span class="sxs-lookup"><span data-stu-id="bdd32-578">DBPROP_PROCEDURETERM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdd32-579">Prompt</span><span class="sxs-lookup"><span data-stu-id="bdd32-579">Prompt</span></span></p></td>
<td><p><span data-ttu-id="bdd32-580">DBPROP_INIT_PROMPT</span><span class="sxs-lookup"><span data-stu-id="bdd32-580">DBPROP_INIT_PROMPT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdd32-581">Provider Friendly Name</span><span class="sxs-lookup"><span data-stu-id="bdd32-581">Provider Friendly Name</span></span></p></td>
<td><p><span data-ttu-id="bdd32-582">DBPROP_PROVIDERFRIENDLYNAME</span><span class="sxs-lookup"><span data-stu-id="bdd32-582">DBPROP_PROVIDERFRIENDLYNAME</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdd32-583">Provider Name</span><span class="sxs-lookup"><span data-stu-id="bdd32-583">Provider Name</span></span></p></td>
<td><p><span data-ttu-id="bdd32-584">DBPROP_PROVIDERFILENAME</span><span class="sxs-lookup"><span data-stu-id="bdd32-584">DBPROP_PROVIDERFILENAME</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdd32-585">Provider Version</span><span class="sxs-lookup"><span data-stu-id="bdd32-585">Provider Version</span></span></p></td>
<td><p><span data-ttu-id="bdd32-586">DBPROP_PROVIDERVER</span><span class="sxs-lookup"><span data-stu-id="bdd32-586">DBPROP_PROVIDERVER</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdd32-587">Read-Only Data Source</span><span class="sxs-lookup"><span data-stu-id="bdd32-587">Read-Only Data Source</span></span></p></td>
<td><p><span data-ttu-id="bdd32-588">DBPROP_DATASOURCEREADONLY</span><span class="sxs-lookup"><span data-stu-id="bdd32-588">DBPROP_DATASOURCEREADONLY</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdd32-589">Rowset Conversions on Command</span><span class="sxs-lookup"><span data-stu-id="bdd32-589">Rowset Conversions on Command</span></span></p></td>
<td><p><span data-ttu-id="bdd32-590">DBPROP_ROWSETCONVERSIONSONCOMMAND</span><span class="sxs-lookup"><span data-stu-id="bdd32-590">DBPROP_ROWSETCONVERSIONSONCOMMAND</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdd32-591">Schema Term</span><span class="sxs-lookup"><span data-stu-id="bdd32-591">Schema Term</span></span></p></td>
<td><p><span data-ttu-id="bdd32-592">DBPROP_SCHEMATERM</span><span class="sxs-lookup"><span data-stu-id="bdd32-592">DBPROP_SCHEMATERM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdd32-593">Schema Usage</span><span class="sxs-lookup"><span data-stu-id="bdd32-593">Schema Usage</span></span></p></td>
<td><p><span data-ttu-id="bdd32-594">DBPROP_SCHEMAUSAGE</span><span class="sxs-lookup"><span data-stu-id="bdd32-594">DBPROP_SCHEMAUSAGE</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdd32-595">SQL Support</span><span class="sxs-lookup"><span data-stu-id="bdd32-595">SQL Support</span></span></p></td>
<td><p><span data-ttu-id="bdd32-596">DBPROP_SQLSUPPORT</span><span class="sxs-lookup"><span data-stu-id="bdd32-596">DBPROP_SQLSUPPORT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdd32-597">Structured Storage</span><span class="sxs-lookup"><span data-stu-id="bdd32-597">Structured Storage</span></span></p></td>
<td><p><span data-ttu-id="bdd32-598">DBPROP_STRUCTUREDSTORAGE</span><span class="sxs-lookup"><span data-stu-id="bdd32-598">DBPROP_STRUCTUREDSTORAGE</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdd32-599">Subquery Support</span><span class="sxs-lookup"><span data-stu-id="bdd32-599">Subquery Support</span></span></p></td>
<td><p><span data-ttu-id="bdd32-600">DBPROP_SUBQUERIES</span><span class="sxs-lookup"><span data-stu-id="bdd32-600">DBPROP_SUBQUERIES</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdd32-601">Table Term</span><span class="sxs-lookup"><span data-stu-id="bdd32-601">Table Term</span></span></p></td>
<td><p><span data-ttu-id="bdd32-602">DBPROP_TABLETERM</span><span class="sxs-lookup"><span data-stu-id="bdd32-602">DBPROP_TABLETERM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdd32-603">Transaction DDL</span><span class="sxs-lookup"><span data-stu-id="bdd32-603">Transaction DDL</span></span></p></td>
<td><p><span data-ttu-id="bdd32-604">DBPROP_SUPPORTEDTXNDDL</span><span class="sxs-lookup"><span data-stu-id="bdd32-604">DBPROP_SUPPORTEDTXNDDL</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdd32-605">User ID</span><span class="sxs-lookup"><span data-stu-id="bdd32-605">User ID</span></span></p></td>
<td><p><span data-ttu-id="bdd32-606">DBPROP_AUTH_USERID</span><span class="sxs-lookup"><span data-stu-id="bdd32-606">DBPROP_AUTH_USERID</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdd32-607">User Name</span><span class="sxs-lookup"><span data-stu-id="bdd32-607">User Name</span></span></p></td>
<td><p><span data-ttu-id="bdd32-608">DBPROP_USERNAME</span><span class="sxs-lookup"><span data-stu-id="bdd32-608">DBPROP_USERNAME</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdd32-609">Window Handle</span><span class="sxs-lookup"><span data-stu-id="bdd32-609">Window Handle</span></span></p></td>
<td><p><span data-ttu-id="bdd32-610">DBPROP_INIT_HWND</span><span class="sxs-lookup"><span data-stu-id="bdd32-610">DBPROP_INIT_HWND</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="recordset-dynamic-properties"></a><span data-ttu-id="bdd32-611">Recordset 动态属性</span><span class="sxs-lookup"><span data-stu-id="bdd32-611">Recordset Dynamic Properties</span></span>

<span data-ttu-id="bdd32-612">以下属性将被添加到 **Recordset** 对象的 **Properties** 集合中。</span><span class="sxs-lookup"><span data-stu-id="bdd32-612">The following properties are added to the **Recordset** object's **Properties** collection.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="bdd32-613">ADO 属性名</span><span class="sxs-lookup"><span data-stu-id="bdd32-613">ADO Property Name</span></span></p></th>
<th><p><span data-ttu-id="bdd32-614">OLE DB 属性名</span><span class="sxs-lookup"><span data-stu-id="bdd32-614">OLE DB Property Name</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bdd32-615">Access Order</span><span class="sxs-lookup"><span data-stu-id="bdd32-615">Access Order</span></span></p></td>
<td><p><span data-ttu-id="bdd32-616">DBPROP_ACCESSORDER</span><span class="sxs-lookup"><span data-stu-id="bdd32-616">DBPROP_ACCESSORDER</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdd32-617">Blocking Storage Objects</span><span class="sxs-lookup"><span data-stu-id="bdd32-617">Blocking Storage Objects</span></span></p></td>
<td><p><span data-ttu-id="bdd32-618">DBPROP_BLOCKINGSTORAGEOBJECTS</span><span class="sxs-lookup"><span data-stu-id="bdd32-618">DBPROP_BLOCKINGSTORAGEOBJECTS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdd32-619">Bookmark Type</span><span class="sxs-lookup"><span data-stu-id="bdd32-619">Bookmark Type</span></span></p></td>
<td><p><span data-ttu-id="bdd32-620">DBPROP_BOOKMARKTYPE</span><span class="sxs-lookup"><span data-stu-id="bdd32-620">DBPROP_BOOKMARKTYPE</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdd32-621">Bookmarkable</span><span class="sxs-lookup"><span data-stu-id="bdd32-621">Bookmarkable</span></span></p></td>
<td><p><span data-ttu-id="bdd32-622">DBPROP_IROWSETLOCATE</span><span class="sxs-lookup"><span data-stu-id="bdd32-622">DBPROP_IROWSETLOCATE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdd32-623">Change Inserted Rows</span><span class="sxs-lookup"><span data-stu-id="bdd32-623">Change Inserted Rows</span></span></p></td>
<td><p><span data-ttu-id="bdd32-624">DBPROP_CHANGEINSERTEDROWS</span><span class="sxs-lookup"><span data-stu-id="bdd32-624">DBPROP_CHANGEINSERTEDROWS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdd32-625">Column Privileges</span><span class="sxs-lookup"><span data-stu-id="bdd32-625">Column Privileges</span></span></p></td>
<td><p><span data-ttu-id="bdd32-626">DBPROP_COLUMNRESTRICT</span><span class="sxs-lookup"><span data-stu-id="bdd32-626">DBPROP_COLUMNRESTRICT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdd32-627">Column Set Notification</span><span class="sxs-lookup"><span data-stu-id="bdd32-627">Column Set Notification</span></span></p></td>
<td><p><span data-ttu-id="bdd32-628">DBPROP_NOTIFYCOLUMNSET</span><span class="sxs-lookup"><span data-stu-id="bdd32-628">DBPROP_NOTIFYCOLUMNSET</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdd32-629">Delay Storage Object Updates</span><span class="sxs-lookup"><span data-stu-id="bdd32-629">Delay Storage Object Updates</span></span></p></td>
<td><p><span data-ttu-id="bdd32-630">DBPROP_DELAYSTORAGEOBJECTS</span><span class="sxs-lookup"><span data-stu-id="bdd32-630">DBPROP_DELAYSTORAGEOBJECTS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdd32-631">Fetch Backwards</span><span class="sxs-lookup"><span data-stu-id="bdd32-631">Fetch Backwards</span></span></p></td>
<td><p><span data-ttu-id="bdd32-632">DBPROP_CANFETCHBACKWARDS</span><span class="sxs-lookup"><span data-stu-id="bdd32-632">DBPROP_CANFETCHBACKWARDS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdd32-633">Hold Rows</span><span class="sxs-lookup"><span data-stu-id="bdd32-633">Hold Rows</span></span></p></td>
<td><p><span data-ttu-id="bdd32-634">DBPROP_CANHOLDROWS</span><span class="sxs-lookup"><span data-stu-id="bdd32-634">DBPROP_CANHOLDROWS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdd32-635">IAccessor</span><span class="sxs-lookup"><span data-stu-id="bdd32-635">IAccessor</span></span></p></td>
<td><p><span data-ttu-id="bdd32-636">DBPROP_IAccessor</span><span class="sxs-lookup"><span data-stu-id="bdd32-636">DBPROP_IAccessor</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdd32-637">IColumnsInfo</span><span class="sxs-lookup"><span data-stu-id="bdd32-637">IColumnsInfo</span></span></p></td>
<td><p><span data-ttu-id="bdd32-638">DBPROP_IColumnsInfo</span><span class="sxs-lookup"><span data-stu-id="bdd32-638">DBPROP_IColumnsInfo</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdd32-639">IColumnsRowset</span><span class="sxs-lookup"><span data-stu-id="bdd32-639">IColumnsRowset</span></span></p></td>
<td><p><span data-ttu-id="bdd32-640">DBPROP_IColumnsRowset</span><span class="sxs-lookup"><span data-stu-id="bdd32-640">DBPROP_IColumnsRowset</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdd32-641">IConnectionPointContainer</span><span class="sxs-lookup"><span data-stu-id="bdd32-641">IConnectionPointContainer</span></span></p></td>
<td><p><span data-ttu-id="bdd32-642">DBPROP_IConnectionPointContainer</span><span class="sxs-lookup"><span data-stu-id="bdd32-642">DBPROP_IConnectionPointContainer</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdd32-643">IConvertType</span><span class="sxs-lookup"><span data-stu-id="bdd32-643">IConvertType</span></span></p></td>
<td><p><span data-ttu-id="bdd32-644">DBPROP_IConvertType</span><span class="sxs-lookup"><span data-stu-id="bdd32-644">DBPROP_IConvertType</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdd32-645">Immobile Rows</span><span class="sxs-lookup"><span data-stu-id="bdd32-645">Immobile Rows</span></span></p></td>
<td><p><span data-ttu-id="bdd32-646">DBPROP_IMMOBILEROWS</span><span class="sxs-lookup"><span data-stu-id="bdd32-646">DBPROP_IMMOBILEROWS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdd32-647">IRowset</span><span class="sxs-lookup"><span data-stu-id="bdd32-647">IRowset</span></span></p></td>
<td><p><span data-ttu-id="bdd32-648">DBPROP_IRowset</span><span class="sxs-lookup"><span data-stu-id="bdd32-648">DBPROP_IRowset</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdd32-649">IRowsetChange</span><span class="sxs-lookup"><span data-stu-id="bdd32-649">IRowsetChange</span></span></p></td>
<td><p><span data-ttu-id="bdd32-650">DBPROP_IRowsetChange</span><span class="sxs-lookup"><span data-stu-id="bdd32-650">DBPROP_IRowsetChange</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdd32-651">IRowsetIdentity</span><span class="sxs-lookup"><span data-stu-id="bdd32-651">IRowsetIdentity</span></span></p></td>
<td><p><span data-ttu-id="bdd32-652">DBPROP_IRowsetIdentity</span><span class="sxs-lookup"><span data-stu-id="bdd32-652">DBPROP_IRowsetIdentity</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdd32-653">IRowsetInfo</span><span class="sxs-lookup"><span data-stu-id="bdd32-653">IRowsetInfo</span></span></p></td>
<td><p><span data-ttu-id="bdd32-654">DBPROP_IRowsetInfo</span><span class="sxs-lookup"><span data-stu-id="bdd32-654">DBPROP_IRowsetInfo</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdd32-655">IRowsetLocate</span><span class="sxs-lookup"><span data-stu-id="bdd32-655">IRowsetLocate</span></span></p></td>
<td><p><span data-ttu-id="bdd32-656">DBPROP_IRowsetLocate</span><span class="sxs-lookup"><span data-stu-id="bdd32-656">DBPROP_IRowsetLocate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdd32-657">IRowsetResynch</span><span class="sxs-lookup"><span data-stu-id="bdd32-657">IRowsetResynch</span></span></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdd32-658">IRowsetUpdate</span><span class="sxs-lookup"><span data-stu-id="bdd32-658">IRowsetUpdate</span></span></p></td>
<td><p><span data-ttu-id="bdd32-659">DBPROP_IRowsetUpdate</span><span class="sxs-lookup"><span data-stu-id="bdd32-659">DBPROP_IRowsetUpdate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdd32-660">ISequentialStream</span><span class="sxs-lookup"><span data-stu-id="bdd32-660">ISequentialStream</span></span></p></td>
<td><p><span data-ttu-id="bdd32-661">DBPROP_ISequentialStream</span><span class="sxs-lookup"><span data-stu-id="bdd32-661">DBPROP_ISequentialStream</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdd32-662">ISupportErrorInfo</span><span class="sxs-lookup"><span data-stu-id="bdd32-662">ISupportErrorInfo</span></span></p></td>
<td><p><span data-ttu-id="bdd32-663">DBPROP_ISupportErrorInfo</span><span class="sxs-lookup"><span data-stu-id="bdd32-663">DBPROP_ISupportErrorInfo</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdd32-664">Literal Bookmarks</span><span class="sxs-lookup"><span data-stu-id="bdd32-664">Literal Bookmarks</span></span></p></td>
<td><p><span data-ttu-id="bdd32-665">DBPROP_LITERALBOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="bdd32-665">DBPROP_LITERALBOOKMARKS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdd32-666">Literal Row Identity</span><span class="sxs-lookup"><span data-stu-id="bdd32-666">Literal Row Identity</span></span></p></td>
<td><p><span data-ttu-id="bdd32-667">DBPROP_LITERALIDENTITY</span><span class="sxs-lookup"><span data-stu-id="bdd32-667">DBPROP_LITERALIDENTITY</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdd32-668">Maximum Open Rows</span><span class="sxs-lookup"><span data-stu-id="bdd32-668">Maximum Open Rows</span></span></p></td>
<td><p><span data-ttu-id="bdd32-669">DBPROP_MAXOPENROWS</span><span class="sxs-lookup"><span data-stu-id="bdd32-669">DBPROP_MAXOPENROWS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdd32-670">Maximum Pending Rows</span><span class="sxs-lookup"><span data-stu-id="bdd32-670">Maximum Pending Rows</span></span></p></td>
<td><p><span data-ttu-id="bdd32-671">DBPROP_MAXPENDINGROWS</span><span class="sxs-lookup"><span data-stu-id="bdd32-671">DBPROP_MAXPENDINGROWS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdd32-672">Maximum Rows</span><span class="sxs-lookup"><span data-stu-id="bdd32-672">Maximum Rows</span></span></p></td>
<td><p><span data-ttu-id="bdd32-673">DBPROP_MAXROWS</span><span class="sxs-lookup"><span data-stu-id="bdd32-673">DBPROP_MAXROWS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdd32-674">Notification Granularity</span><span class="sxs-lookup"><span data-stu-id="bdd32-674">Notification Granularity</span></span></p></td>
<td><p><span data-ttu-id="bdd32-675">DBPROP_NOTIFICATIONGRANULARITY</span><span class="sxs-lookup"><span data-stu-id="bdd32-675">DBPROP_NOTIFICATIONGRANULARITY</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdd32-676">Notification Phases</span><span class="sxs-lookup"><span data-stu-id="bdd32-676">Notification Phases</span></span></p></td>
<td><p><span data-ttu-id="bdd32-677">DBPROP_NOTIFICATIONPHASES</span><span class="sxs-lookup"><span data-stu-id="bdd32-677">DBPROP_NOTIFICATIONPHASES</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdd32-678">Objects Transacted</span><span class="sxs-lookup"><span data-stu-id="bdd32-678">Objects Transacted</span></span></p></td>
<td><p><span data-ttu-id="bdd32-679">DBPROP_TRANSACTEDOBJECT</span><span class="sxs-lookup"><span data-stu-id="bdd32-679">DBPROP_TRANSACTEDOBJECT</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdd32-680">Own Changes Visible</span><span class="sxs-lookup"><span data-stu-id="bdd32-680">Own Changes Visible</span></span></p></td>
<td><p><span data-ttu-id="bdd32-681">DBPROP_OWNUPDATEDELETE</span><span class="sxs-lookup"><span data-stu-id="bdd32-681">DBPROP_OWNUPDATEDELETE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdd32-682">Own Inserts Visible</span><span class="sxs-lookup"><span data-stu-id="bdd32-682">Own Inserts Visible</span></span></p></td>
<td><p><span data-ttu-id="bdd32-683">DBPROP_OWNINSERT</span><span class="sxs-lookup"><span data-stu-id="bdd32-683">DBPROP_OWNINSERT</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdd32-684">Preserve on Abort</span><span class="sxs-lookup"><span data-stu-id="bdd32-684">Preserve on Abort</span></span></p></td>
<td><p><span data-ttu-id="bdd32-685">DBPROP_ABORTPRESERVE</span><span class="sxs-lookup"><span data-stu-id="bdd32-685">DBPROP_ABORTPRESERVE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdd32-686">Preserve on Commit</span><span class="sxs-lookup"><span data-stu-id="bdd32-686">Preserve on Commit</span></span></p></td>
<td><p><span data-ttu-id="bdd32-687">DBPROP_COMMITPRESERVE</span><span class="sxs-lookup"><span data-stu-id="bdd32-687">DBPROP_COMMITPRESERVE</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdd32-688">Quick Restart</span><span class="sxs-lookup"><span data-stu-id="bdd32-688">Quick Restart</span></span></p></td>
<td><p><span data-ttu-id="bdd32-689">DBPROP_QUICKRESTART</span><span class="sxs-lookup"><span data-stu-id="bdd32-689">DBPROP_QUICKRESTART</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdd32-690">Reentrant Events</span><span class="sxs-lookup"><span data-stu-id="bdd32-690">Reentrant Events</span></span></p></td>
<td><p><span data-ttu-id="bdd32-691">DBPROP_REENTRANTEVENTS</span><span class="sxs-lookup"><span data-stu-id="bdd32-691">DBPROP_REENTRANTEVENTS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdd32-692">Remove Deleted Rows</span><span class="sxs-lookup"><span data-stu-id="bdd32-692">Remove Deleted Rows</span></span></p></td>
<td><p><span data-ttu-id="bdd32-693">DBPROP_REMOVEDELETED</span><span class="sxs-lookup"><span data-stu-id="bdd32-693">DBPROP_REMOVEDELETED</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdd32-694">Report Multiple Changes</span><span class="sxs-lookup"><span data-stu-id="bdd32-694">Report Multiple Changes</span></span></p></td>
<td><p><span data-ttu-id="bdd32-695">DBPROP_REPORTMULTIPLECHANGES</span><span class="sxs-lookup"><span data-stu-id="bdd32-695">DBPROP_REPORTMULTIPLECHANGES</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdd32-696">Return Pending Inserts</span><span class="sxs-lookup"><span data-stu-id="bdd32-696">Return Pending Inserts</span></span></p></td>
<td><p><span data-ttu-id="bdd32-697">DBPROP_RETURNPENDINGINSERTS</span><span class="sxs-lookup"><span data-stu-id="bdd32-697">DBPROP_RETURNPENDINGINSERTS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdd32-698">Row Delete Notification</span><span class="sxs-lookup"><span data-stu-id="bdd32-698">Row Delete Notification</span></span></p></td>
<td><p><span data-ttu-id="bdd32-699">DBPROP_NOTIFYROWDELETE</span><span class="sxs-lookup"><span data-stu-id="bdd32-699">DBPROP_NOTIFYROWDELETE</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdd32-700">Row First Change Notification</span><span class="sxs-lookup"><span data-stu-id="bdd32-700">Row First Change Notification</span></span></p></td>
<td><p><span data-ttu-id="bdd32-701">DBPROP_NOTIFYROWFIRSTCHANGE</span><span class="sxs-lookup"><span data-stu-id="bdd32-701">DBPROP_NOTIFYROWFIRSTCHANGE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdd32-702">Row Insert Notification</span><span class="sxs-lookup"><span data-stu-id="bdd32-702">Row Insert Notification</span></span></p></td>
<td><p><span data-ttu-id="bdd32-703">DBPROP_NOTIFYROWINSERT</span><span class="sxs-lookup"><span data-stu-id="bdd32-703">DBPROP_NOTIFYROWINSERT</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdd32-704">Row Privileges</span><span class="sxs-lookup"><span data-stu-id="bdd32-704">Row Privileges</span></span></p></td>
<td><p><span data-ttu-id="bdd32-705">DBPROP_ROWRESTRICT</span><span class="sxs-lookup"><span data-stu-id="bdd32-705">DBPROP_ROWRESTRICT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdd32-706">Row Resynchronization Notification</span><span class="sxs-lookup"><span data-stu-id="bdd32-706">Row Resynchronization Notification</span></span></p></td>
<td><p><span data-ttu-id="bdd32-707">DBPROP_NOTIFYROWRESYNCH</span><span class="sxs-lookup"><span data-stu-id="bdd32-707">DBPROP_NOTIFYROWRESYNCH</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdd32-708">Row Threading Model</span><span class="sxs-lookup"><span data-stu-id="bdd32-708">Row Threading Model</span></span></p></td>
<td><p><span data-ttu-id="bdd32-709">DBPROP_ROWTHREADMODEL</span><span class="sxs-lookup"><span data-stu-id="bdd32-709">DBPROP_ROWTHREADMODEL</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdd32-710">Row Undo Change Notification</span><span class="sxs-lookup"><span data-stu-id="bdd32-710">Row Undo Change Notification</span></span></p></td>
<td><p><span data-ttu-id="bdd32-711">DBPROP_NOTIFYROWUNDOCHANGE</span><span class="sxs-lookup"><span data-stu-id="bdd32-711">DBPROP_NOTIFYROWUNDOCHANGE</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdd32-712">Row Undo Delete Notification</span><span class="sxs-lookup"><span data-stu-id="bdd32-712">Row Undo Delete Notification</span></span></p></td>
<td><p><span data-ttu-id="bdd32-713">DBPROP_NOTIFYROWUNDODELETE</span><span class="sxs-lookup"><span data-stu-id="bdd32-713">DBPROP_NOTIFYROWUNDODELETE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdd32-714">Row Undo Insert Notification</span><span class="sxs-lookup"><span data-stu-id="bdd32-714">Row Undo Insert Notification</span></span></p></td>
<td><p><span data-ttu-id="bdd32-715">DBPROP_NOTIFYROWUNDOINSERT</span><span class="sxs-lookup"><span data-stu-id="bdd32-715">DBPROP_NOTIFYROWUNDOINSERT</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdd32-716">Row Update Notification</span><span class="sxs-lookup"><span data-stu-id="bdd32-716">Row Update Notification</span></span></p></td>
<td><p><span data-ttu-id="bdd32-717">DBPROP_NOTIFYROWUPDATE</span><span class="sxs-lookup"><span data-stu-id="bdd32-717">DBPROP_NOTIFYROWUPDATE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdd32-718">Rowset Fetch Position Change Notification</span><span class="sxs-lookup"><span data-stu-id="bdd32-718">Rowset Fetch Position Change Notification</span></span></p></td>
<td><p><span data-ttu-id="bdd32-719">DBPROP_NOTIFYROWSETFETCHPOSISIONCHANGE</span><span class="sxs-lookup"><span data-stu-id="bdd32-719">DBPROP_NOTIFYROWSETFETCHPOSISIONCHANGE</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdd32-720">Rowset Release Notification</span><span class="sxs-lookup"><span data-stu-id="bdd32-720">Rowset Release Notification</span></span></p></td>
<td><p><span data-ttu-id="bdd32-721">DBPROP_NOTIFYROWSETRELEASE</span><span class="sxs-lookup"><span data-stu-id="bdd32-721">DBPROP_NOTIFYROWSETRELEASE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdd32-722">Scroll Backwards</span><span class="sxs-lookup"><span data-stu-id="bdd32-722">Scroll Backwards</span></span></p></td>
<td><p><span data-ttu-id="bdd32-723">DBPROP_CANSCROLLBACKWARDS</span><span class="sxs-lookup"><span data-stu-id="bdd32-723">DBPROP_CANSCROLLBACKWARDS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdd32-724">Skip Deleted Bookmarks</span><span class="sxs-lookup"><span data-stu-id="bdd32-724">Skip Deleted Bookmarks</span></span></p></td>
<td><p><span data-ttu-id="bdd32-725">DBPROP_BOOKMARKSKIPPED</span><span class="sxs-lookup"><span data-stu-id="bdd32-725">DBPROP_BOOKMARKSKIPPED</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdd32-726">Strong Row Identity</span><span class="sxs-lookup"><span data-stu-id="bdd32-726">Strong Row Identity</span></span></p></td>
<td><p><span data-ttu-id="bdd32-727">DBPROP_STRONGITDENTITY</span><span class="sxs-lookup"><span data-stu-id="bdd32-727">DBPROP_STRONGITDENTITY</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdd32-728">Unique Rows</span><span class="sxs-lookup"><span data-stu-id="bdd32-728">Unique Rows</span></span></p></td>
<td><p><span data-ttu-id="bdd32-729">DBPROP_UNIQUEROWS</span><span class="sxs-lookup"><span data-stu-id="bdd32-729">DBPROP_UNIQUEROWS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdd32-730">Updatability</span><span class="sxs-lookup"><span data-stu-id="bdd32-730">Updatability</span></span></p></td>
<td><p><span data-ttu-id="bdd32-731">DBPROP_UPDATABILITY</span><span class="sxs-lookup"><span data-stu-id="bdd32-731">DBPROP_UPDATABILITY</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdd32-732">Use Bookmarks</span><span class="sxs-lookup"><span data-stu-id="bdd32-732">Use Bookmarks</span></span></p></td>
<td><p><span data-ttu-id="bdd32-733">DBPROP_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="bdd32-733">DBPROP_BOOKMARKS</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="command-dynamic-properties"></a><span data-ttu-id="bdd32-734">Command 动态属性</span><span class="sxs-lookup"><span data-stu-id="bdd32-734">Command Dynamic Properties</span></span>

<span data-ttu-id="bdd32-735">以下属性将被添加到 **Command** 对象的 **Properties** 集合中。</span><span class="sxs-lookup"><span data-stu-id="bdd32-735">The following properties are added to the **Command** object's **Properties** collection.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="bdd32-736">ADO 属性名</span><span class="sxs-lookup"><span data-stu-id="bdd32-736">ADO Property Name</span></span></p></th>
<th><p><span data-ttu-id="bdd32-737">OLE DB 属性名</span><span class="sxs-lookup"><span data-stu-id="bdd32-737">OLE DB Property Name</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bdd32-738">Access Order</span><span class="sxs-lookup"><span data-stu-id="bdd32-738">Access Order</span></span></p></td>
<td><p><span data-ttu-id="bdd32-739">DBPROP_ACCESSORDER</span><span class="sxs-lookup"><span data-stu-id="bdd32-739">DBPROP_ACCESSORDER</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdd32-740">Blocking Storage Objects</span><span class="sxs-lookup"><span data-stu-id="bdd32-740">Blocking Storage Objects</span></span></p></td>
<td><p><span data-ttu-id="bdd32-741">DBPROP_BLOCKINGSTORAGEOBJECTS</span><span class="sxs-lookup"><span data-stu-id="bdd32-741">DBPROP_BLOCKINGSTORAGEOBJECTS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdd32-742">Bookmark Type</span><span class="sxs-lookup"><span data-stu-id="bdd32-742">Bookmark Type</span></span></p></td>
<td><p><span data-ttu-id="bdd32-743">DBPROP_BOOKMARKTYPE</span><span class="sxs-lookup"><span data-stu-id="bdd32-743">DBPROP_BOOKMARKTYPE</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdd32-744">Bookmarkable</span><span class="sxs-lookup"><span data-stu-id="bdd32-744">Bookmarkable</span></span></p></td>
<td><p><span data-ttu-id="bdd32-745">DBPROP_IROWSETLOCATE</span><span class="sxs-lookup"><span data-stu-id="bdd32-745">DBPROP_IROWSETLOCATE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdd32-746">Change Inserted Rows</span><span class="sxs-lookup"><span data-stu-id="bdd32-746">Change Inserted Rows</span></span></p></td>
<td><p><span data-ttu-id="bdd32-747">DBPROP_CHANGEINSERTEDROWS</span><span class="sxs-lookup"><span data-stu-id="bdd32-747">DBPROP_CHANGEINSERTEDROWS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdd32-748">Column Privileges</span><span class="sxs-lookup"><span data-stu-id="bdd32-748">Column Privileges</span></span></p></td>
<td><p><span data-ttu-id="bdd32-749">DBPROP_COLUMNRESTRICT</span><span class="sxs-lookup"><span data-stu-id="bdd32-749">DBPROP_COLUMNRESTRICT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdd32-750">Column Set Notification</span><span class="sxs-lookup"><span data-stu-id="bdd32-750">Column Set Notification</span></span></p></td>
<td><p><span data-ttu-id="bdd32-751">DBPROP_NOTIFYCOLUMNSET</span><span class="sxs-lookup"><span data-stu-id="bdd32-751">DBPROP_NOTIFYCOLUMNSET</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdd32-752">Delay Storage Object Updates</span><span class="sxs-lookup"><span data-stu-id="bdd32-752">Delay Storage Object Updates</span></span></p></td>
<td><p><span data-ttu-id="bdd32-753">DBPROP_DELAYSTORAGEOBJECTS</span><span class="sxs-lookup"><span data-stu-id="bdd32-753">DBPROP_DELAYSTORAGEOBJECTS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdd32-754">Fetch Backwards</span><span class="sxs-lookup"><span data-stu-id="bdd32-754">Fetch Backwards</span></span></p></td>
<td><p><span data-ttu-id="bdd32-755">DBPROP_CANFETCHBACKWARDS</span><span class="sxs-lookup"><span data-stu-id="bdd32-755">DBPROP_CANFETCHBACKWARDS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdd32-756">Hold Rows</span><span class="sxs-lookup"><span data-stu-id="bdd32-756">Hold Rows</span></span></p></td>
<td><p><span data-ttu-id="bdd32-757">DBPROP_CANHOLDROWS</span><span class="sxs-lookup"><span data-stu-id="bdd32-757">DBPROP_CANHOLDROWS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdd32-758">IAccessor</span><span class="sxs-lookup"><span data-stu-id="bdd32-758">IAccessor</span></span></p></td>
<td><p><span data-ttu-id="bdd32-759">DBPROP_IAccessor</span><span class="sxs-lookup"><span data-stu-id="bdd32-759">DBPROP_IAccessor</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdd32-760">IColumnsInfo</span><span class="sxs-lookup"><span data-stu-id="bdd32-760">IColumnsInfo</span></span></p></td>
<td><p><span data-ttu-id="bdd32-761">DBPROP_IColumnsInfo</span><span class="sxs-lookup"><span data-stu-id="bdd32-761">DBPROP_IColumnsInfo</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdd32-762">IColumnsRowset</span><span class="sxs-lookup"><span data-stu-id="bdd32-762">IColumnsRowset</span></span></p></td>
<td><p><span data-ttu-id="bdd32-763">DBPROP_IColumnsRowset</span><span class="sxs-lookup"><span data-stu-id="bdd32-763">DBPROP_IColumnsRowset</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdd32-764">IConnectionPointContainer</span><span class="sxs-lookup"><span data-stu-id="bdd32-764">IConnectionPointContainer</span></span></p></td>
<td><p><span data-ttu-id="bdd32-765">DBPROP_IConnectionPointContainer</span><span class="sxs-lookup"><span data-stu-id="bdd32-765">DBPROP_IConnectionPointContainer</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdd32-766">IConvertType</span><span class="sxs-lookup"><span data-stu-id="bdd32-766">IConvertType</span></span></p></td>
<td><p><span data-ttu-id="bdd32-767">DBPROP_IConvertType</span><span class="sxs-lookup"><span data-stu-id="bdd32-767">DBPROP_IConvertType</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdd32-768">Immobile Rows</span><span class="sxs-lookup"><span data-stu-id="bdd32-768">Immobile Rows</span></span></p></td>
<td><p><span data-ttu-id="bdd32-769">DBPROP_IMMOBILEROWS</span><span class="sxs-lookup"><span data-stu-id="bdd32-769">DBPROP_IMMOBILEROWS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdd32-770">IRowset</span><span class="sxs-lookup"><span data-stu-id="bdd32-770">IRowset</span></span></p></td>
<td><p><span data-ttu-id="bdd32-771">DBPROP_IRowset</span><span class="sxs-lookup"><span data-stu-id="bdd32-771">DBPROP_IRowset</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdd32-772">IRowsetChange</span><span class="sxs-lookup"><span data-stu-id="bdd32-772">IRowsetChange</span></span></p></td>
<td><p><span data-ttu-id="bdd32-773">DBPROP_IRowsetChange</span><span class="sxs-lookup"><span data-stu-id="bdd32-773">DBPROP_IRowsetChange</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdd32-774">IRowsetIdentity</span><span class="sxs-lookup"><span data-stu-id="bdd32-774">IRowsetIdentity</span></span></p></td>
<td><p><span data-ttu-id="bdd32-775">DBPROP_IRowsetIdentity</span><span class="sxs-lookup"><span data-stu-id="bdd32-775">DBPROP_IRowsetIdentity</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdd32-776">IRowsetInfo</span><span class="sxs-lookup"><span data-stu-id="bdd32-776">IRowsetInfo</span></span></p></td>
<td><p><span data-ttu-id="bdd32-777">DBPROP_IRowsetInfo</span><span class="sxs-lookup"><span data-stu-id="bdd32-777">DBPROP_IRowsetInfo</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdd32-778">IRowsetLocate</span><span class="sxs-lookup"><span data-stu-id="bdd32-778">IRowsetLocate</span></span></p></td>
<td><p><span data-ttu-id="bdd32-779">DBPROP_IRowsetLocate</span><span class="sxs-lookup"><span data-stu-id="bdd32-779">DBPROP_IRowsetLocate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdd32-780">IRowsetResynch</span><span class="sxs-lookup"><span data-stu-id="bdd32-780">IRowsetResynch</span></span></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdd32-781">IRowsetUpdate</span><span class="sxs-lookup"><span data-stu-id="bdd32-781">IRowsetUpdate</span></span></p></td>
<td><p><span data-ttu-id="bdd32-782">DBPROP_IRowsetUpdate</span><span class="sxs-lookup"><span data-stu-id="bdd32-782">DBPROP_IRowsetUpdate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdd32-783">ISequentialStream</span><span class="sxs-lookup"><span data-stu-id="bdd32-783">ISequentialStream</span></span></p></td>
<td><p><span data-ttu-id="bdd32-784">DBPROP_ISequentialStream</span><span class="sxs-lookup"><span data-stu-id="bdd32-784">DBPROP_ISequentialStream</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdd32-785">ISupportErrorInfo</span><span class="sxs-lookup"><span data-stu-id="bdd32-785">ISupportErrorInfo</span></span></p></td>
<td><p><span data-ttu-id="bdd32-786">DBPROP_ISupportErrorInfo</span><span class="sxs-lookup"><span data-stu-id="bdd32-786">DBPROP_ISupportErrorInfo</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdd32-787">Literal Bookmarks</span><span class="sxs-lookup"><span data-stu-id="bdd32-787">Literal Bookmarks</span></span></p></td>
<td><p><span data-ttu-id="bdd32-788">DBPROP_LITERALBOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="bdd32-788">DBPROP_LITERALBOOKMARKS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdd32-789">Literal Row Identity</span><span class="sxs-lookup"><span data-stu-id="bdd32-789">Literal Row Identity</span></span></p></td>
<td><p><span data-ttu-id="bdd32-790">DBPROP_LITERALIDENTITY</span><span class="sxs-lookup"><span data-stu-id="bdd32-790">DBPROP_LITERALIDENTITY</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdd32-791">Maximum Open Rows</span><span class="sxs-lookup"><span data-stu-id="bdd32-791">Maximum Open Rows</span></span></p></td>
<td><p><span data-ttu-id="bdd32-792">DBPROP_MAXOPENROWS</span><span class="sxs-lookup"><span data-stu-id="bdd32-792">DBPROP_MAXOPENROWS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdd32-793">Maximum Pending Rows</span><span class="sxs-lookup"><span data-stu-id="bdd32-793">Maximum Pending Rows</span></span></p></td>
<td><p><span data-ttu-id="bdd32-794">DBPROP_MAXPENDINGROWS</span><span class="sxs-lookup"><span data-stu-id="bdd32-794">DBPROP_MAXPENDINGROWS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdd32-795">Maximum Rows</span><span class="sxs-lookup"><span data-stu-id="bdd32-795">Maximum Rows</span></span></p></td>
<td><p><span data-ttu-id="bdd32-796">DBPROP_MAXROWS</span><span class="sxs-lookup"><span data-stu-id="bdd32-796">DBPROP_MAXROWS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdd32-797">Notification Granularity</span><span class="sxs-lookup"><span data-stu-id="bdd32-797">Notification Granularity</span></span></p></td>
<td><p><span data-ttu-id="bdd32-798">DBPROP_NOTIFICATIONGRANULARITY</span><span class="sxs-lookup"><span data-stu-id="bdd32-798">DBPROP_NOTIFICATIONGRANULARITY</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdd32-799">Notification Phases</span><span class="sxs-lookup"><span data-stu-id="bdd32-799">Notification Phases</span></span></p></td>
<td><p><span data-ttu-id="bdd32-800">DBPROP_NOTIFICATIONPHASES</span><span class="sxs-lookup"><span data-stu-id="bdd32-800">DBPROP_NOTIFICATIONPHASES</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdd32-801">Objects Transacted</span><span class="sxs-lookup"><span data-stu-id="bdd32-801">Objects Transacted</span></span></p></td>
<td><p><span data-ttu-id="bdd32-802">DBPROP_TRANSACTEDOBJECT</span><span class="sxs-lookup"><span data-stu-id="bdd32-802">DBPROP_TRANSACTEDOBJECT</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdd32-803">Own Changes Visible</span><span class="sxs-lookup"><span data-stu-id="bdd32-803">Own Changes Visible</span></span></p></td>
<td><p><span data-ttu-id="bdd32-804">DBPROP_OWNUPDATEDELETE</span><span class="sxs-lookup"><span data-stu-id="bdd32-804">DBPROP_OWNUPDATEDELETE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdd32-805">Own Inserts Visible</span><span class="sxs-lookup"><span data-stu-id="bdd32-805">Own Inserts Visible</span></span></p></td>
<td><p><span data-ttu-id="bdd32-806">DBPROP_OWNINSERT</span><span class="sxs-lookup"><span data-stu-id="bdd32-806">DBPROP_OWNINSERT</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdd32-807">Preserve on Abort</span><span class="sxs-lookup"><span data-stu-id="bdd32-807">Preserve on Abort</span></span></p></td>
<td><p><span data-ttu-id="bdd32-808">DBPROP_ABORTPRESERVE</span><span class="sxs-lookup"><span data-stu-id="bdd32-808">DBPROP_ABORTPRESERVE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdd32-809">Preserve on Commit</span><span class="sxs-lookup"><span data-stu-id="bdd32-809">Preserve on Commit</span></span></p></td>
<td><p><span data-ttu-id="bdd32-810">DBPROP_COMMITPRESERVE</span><span class="sxs-lookup"><span data-stu-id="bdd32-810">DBPROP_COMMITPRESERVE</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdd32-811">Quick Restart</span><span class="sxs-lookup"><span data-stu-id="bdd32-811">Quick Restart</span></span></p></td>
<td><p><span data-ttu-id="bdd32-812">DBPROP_QUICKRESTART</span><span class="sxs-lookup"><span data-stu-id="bdd32-812">DBPROP_QUICKRESTART</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdd32-813">Reentrant Events</span><span class="sxs-lookup"><span data-stu-id="bdd32-813">Reentrant Events</span></span></p></td>
<td><p><span data-ttu-id="bdd32-814">DBPROP_REENTRANTEVENTS</span><span class="sxs-lookup"><span data-stu-id="bdd32-814">DBPROP_REENTRANTEVENTS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdd32-815">Remove Deleted Rows</span><span class="sxs-lookup"><span data-stu-id="bdd32-815">Remove Deleted Rows</span></span></p></td>
<td><p><span data-ttu-id="bdd32-816">DBPROP_REMOVEDELETED</span><span class="sxs-lookup"><span data-stu-id="bdd32-816">DBPROP_REMOVEDELETED</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdd32-817">Report Multiple Changes</span><span class="sxs-lookup"><span data-stu-id="bdd32-817">Report Multiple Changes</span></span></p></td>
<td><p><span data-ttu-id="bdd32-818">DBPROP_REPORTMULTIPLECHANGES</span><span class="sxs-lookup"><span data-stu-id="bdd32-818">DBPROP_REPORTMULTIPLECHANGES</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdd32-819">Return Pending Inserts</span><span class="sxs-lookup"><span data-stu-id="bdd32-819">Return Pending Inserts</span></span></p></td>
<td><p><span data-ttu-id="bdd32-820">DBPROP_RETURNPENDINGINSERTS</span><span class="sxs-lookup"><span data-stu-id="bdd32-820">DBPROP_RETURNPENDINGINSERTS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdd32-821">Row Delete Notification</span><span class="sxs-lookup"><span data-stu-id="bdd32-821">Row Delete Notification</span></span></p></td>
<td><p><span data-ttu-id="bdd32-822">DBPROP_NOTIFYROWDELETE</span><span class="sxs-lookup"><span data-stu-id="bdd32-822">DBPROP_NOTIFYROWDELETE</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdd32-823">Row First Change Notification</span><span class="sxs-lookup"><span data-stu-id="bdd32-823">Row First Change Notification</span></span></p></td>
<td><p><span data-ttu-id="bdd32-824">DBPROP_NOTIFYROWFIRSTCHANGE</span><span class="sxs-lookup"><span data-stu-id="bdd32-824">DBPROP_NOTIFYROWFIRSTCHANGE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdd32-825">Row Insert Notification</span><span class="sxs-lookup"><span data-stu-id="bdd32-825">Row Insert Notification</span></span></p></td>
<td><p><span data-ttu-id="bdd32-826">DBPROP_NOTIFYROWINSERT</span><span class="sxs-lookup"><span data-stu-id="bdd32-826">DBPROP_NOTIFYROWINSERT</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdd32-827">Row Privileges</span><span class="sxs-lookup"><span data-stu-id="bdd32-827">Row Privileges</span></span></p></td>
<td><p><span data-ttu-id="bdd32-828">DBPROP_ROWRESTRICT</span><span class="sxs-lookup"><span data-stu-id="bdd32-828">DBPROP_ROWRESTRICT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdd32-829">Row Resynchronization Notification</span><span class="sxs-lookup"><span data-stu-id="bdd32-829">Row Resynchronization Notification</span></span></p></td>
<td><p><span data-ttu-id="bdd32-830">DBPROP_NOTIFYROWRESYNCH</span><span class="sxs-lookup"><span data-stu-id="bdd32-830">DBPROP_NOTIFYROWRESYNCH</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdd32-831">Row Threading Model</span><span class="sxs-lookup"><span data-stu-id="bdd32-831">Row Threading Model</span></span></p></td>
<td><p><span data-ttu-id="bdd32-832">DBPROP_ROWTHREADMODEL</span><span class="sxs-lookup"><span data-stu-id="bdd32-832">DBPROP_ROWTHREADMODEL</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdd32-833">Row Undo Change Notification</span><span class="sxs-lookup"><span data-stu-id="bdd32-833">Row Undo Change Notification</span></span></p></td>
<td><p><span data-ttu-id="bdd32-834">DBPROP_NOTIFYROWUNDOCHANGE</span><span class="sxs-lookup"><span data-stu-id="bdd32-834">DBPROP_NOTIFYROWUNDOCHANGE</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdd32-835">Row Undo Delete Notification</span><span class="sxs-lookup"><span data-stu-id="bdd32-835">Row Undo Delete Notification</span></span></p></td>
<td><p><span data-ttu-id="bdd32-836">DBPROP_NOTIFYROWUNDODELETE</span><span class="sxs-lookup"><span data-stu-id="bdd32-836">DBPROP_NOTIFYROWUNDODELETE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdd32-837">Row Undo Insert Notification</span><span class="sxs-lookup"><span data-stu-id="bdd32-837">Row Undo Insert Notification</span></span></p></td>
<td><p><span data-ttu-id="bdd32-838">DBPROP_NOTIFYROWUNDOINSERT</span><span class="sxs-lookup"><span data-stu-id="bdd32-838">DBPROP_NOTIFYROWUNDOINSERT</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdd32-839">Row Update Notification</span><span class="sxs-lookup"><span data-stu-id="bdd32-839">Row Update Notification</span></span></p></td>
<td><p><span data-ttu-id="bdd32-840">DBPROP_NOTIFYROWUPDATE</span><span class="sxs-lookup"><span data-stu-id="bdd32-840">DBPROP_NOTIFYROWUPDATE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdd32-841">Rowset Fetch Position Change Notification</span><span class="sxs-lookup"><span data-stu-id="bdd32-841">Rowset Fetch Position Change Notification</span></span></p></td>
<td><p><span data-ttu-id="bdd32-842">DBPROP_NOTIFYROWSETFETCHPOSITIONCHANGE</span><span class="sxs-lookup"><span data-stu-id="bdd32-842">DBPROP_NOTIFYROWSETFETCHPOSITIONCHANGE</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdd32-843">Rowset Release Notification</span><span class="sxs-lookup"><span data-stu-id="bdd32-843">Rowset Release Notification</span></span></p></td>
<td><p><span data-ttu-id="bdd32-844">DBPROP_NOTIFYROWSETRELEASE</span><span class="sxs-lookup"><span data-stu-id="bdd32-844">DBPROP_NOTIFYROWSETRELEASE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdd32-845">Scroll Backwards</span><span class="sxs-lookup"><span data-stu-id="bdd32-845">Scroll Backwards</span></span></p></td>
<td><p><span data-ttu-id="bdd32-846">DBPROP_CANSCROLLBACKWARDS</span><span class="sxs-lookup"><span data-stu-id="bdd32-846">DBPROP_CANSCROLLBACKWARDS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdd32-847">Skip Deleted Bookmarks</span><span class="sxs-lookup"><span data-stu-id="bdd32-847">Skip Deleted Bookmarks</span></span></p></td>
<td><p><span data-ttu-id="bdd32-848">DBPROP_BOOKMARKSKIP</span><span class="sxs-lookup"><span data-stu-id="bdd32-848">DBPROP_BOOKMARKSKIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdd32-849">Strong Row Identity</span><span class="sxs-lookup"><span data-stu-id="bdd32-849">Strong Row Identity</span></span></p></td>
<td><p><span data-ttu-id="bdd32-850">DBPROP_STRONGIDENTITY</span><span class="sxs-lookup"><span data-stu-id="bdd32-850">DBPROP_STRONGIDENTITY</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdd32-851">Updatability</span><span class="sxs-lookup"><span data-stu-id="bdd32-851">Updatability</span></span></p></td>
<td><p><span data-ttu-id="bdd32-852">DBPROP_UPDATABILITY</span><span class="sxs-lookup"><span data-stu-id="bdd32-852">DBPROP_UPDATABILITY</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdd32-853">Use Bookmarks</span><span class="sxs-lookup"><span data-stu-id="bdd32-853">Use Bookmarks</span></span></p></td>
<td><p><span data-ttu-id="bdd32-854">DBPROP_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="bdd32-854">DBPROP_BOOKMARKS</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="see-also"></a><span data-ttu-id="bdd32-855">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bdd32-855">See also</span></span>

<span data-ttu-id="bdd32-856">有关具体的实现以及有关 Microsoft OLE DB Provider for ODBC 的功能信息的详细信息，请参阅[OLE DB 程序员指南 》](https://docs.microsoft.com/previous-versions/windows/desktop/ms713643(v=vs.85))或访问[数据平台开发人员中心](https://docs.microsoft.com/sql/connect/sql-data-developer?view=sql-server-2017)。</span><span class="sxs-lookup"><span data-stu-id="bdd32-856">For details regarding specific implementation and functional information about the Microsoft OLE DB Provider for ODBC, consult the [OLE DB Programmer's Guide](https://docs.microsoft.com/previous-versions/windows/desktop/ms713643(v=vs.85)) or visit the [Data Platform Developer Center](https://docs.microsoft.com/sql/connect/sql-data-developer?view=sql-server-2017).</span></span>

