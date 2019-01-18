---
title: Microsoft OLE DB Provider for SQL Server
TOCTitle: Microsoft OLE DB Provider for SQL Server
ms:assetid: 0ffdea03-1a76-499b-f649-423f6b3c13d7
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248868(v=office.15)
ms:contentKeyID: 48543282
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: c4faa664ed9001c1c06906f58c7d873faf75a5d0
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28705104"
---
# <a name="microsoft-ole-db-provider-for-sql-server"></a><span data-ttu-id="68517-102">Microsoft OLE DB Provider for SQL Server</span><span class="sxs-lookup"><span data-stu-id="68517-102">Microsoft OLE DB Provider for SQL Server</span></span>


<span data-ttu-id="68517-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="68517-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="68517-104">Microsoft OLE DB Provider for SQL Server (SQLOLEDB) 允许 ADO 访问 Microsoft SQL Server。</span><span class="sxs-lookup"><span data-stu-id="68517-104">The Microsoft OLE DB Provider for SQL Server, SQLOLEDB, allows ADO to access Microsoft SQL Server.</span></span>

## <a name="connection-string-parameters"></a><span data-ttu-id="68517-105">连接字符串参数</span><span class="sxs-lookup"><span data-stu-id="68517-105">Connection String Parameters</span></span>

<span data-ttu-id="68517-106">若要连接到此提供程序，请将*提供程序*参数设置为将[ConnectionString](connectionstring-property-ado.md)属性设为：</span><span class="sxs-lookup"><span data-stu-id="68517-106">To connect to this provider, set the *Provider* argument to the [ConnectionString](connectionstring-property-ado.md) property to:</span></span>

```sql 
 
SQLOLEDB 
```

<span data-ttu-id="68517-107">也可以使用 [Provider](provider-property-ado.md) 属性设置或读取此值。</span><span class="sxs-lookup"><span data-stu-id="68517-107">This value can also be set or read using the [Provider](provider-property-ado.md) property.</span></span>

## <a name="typical-connection-string"></a><span data-ttu-id="68517-108">典型的连接字符串</span><span class="sxs-lookup"><span data-stu-id="68517-108">Typical Connection String</span></span>

<span data-ttu-id="68517-109">此提供程序典型的连接字符串为：</span><span class="sxs-lookup"><span data-stu-id="68517-109">A typical connection string for this provider is:</span></span>

```sql 
 
"Provider=SQLOLEDB;Data Source=serverName;" 
Initial Catalog=databaseName; 
User ID=userName;Password=userPassword;" 
```

<span data-ttu-id="68517-110">该字符串由以下关键字组成：</span><span class="sxs-lookup"><span data-stu-id="68517-110">The string consists of these keywords:</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="68517-111">关键字</span><span class="sxs-lookup"><span data-stu-id="68517-111">Keyword</span></span></p></th>
<th><p><span data-ttu-id="68517-112">说明</span><span class="sxs-lookup"><span data-stu-id="68517-112">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="68517-113"><strong>Provider</strong></span><span class="sxs-lookup"><span data-stu-id="68517-113"><strong>Provider</strong></span></span></p></td>
<td><p><span data-ttu-id="68517-114">指定 OLE DB Provider for SQL Server。</span><span class="sxs-lookup"><span data-stu-id="68517-114">Specifies the OLE DB Provider for SQL Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68517-115"><strong>Data Source</strong> 或 <strong>Server</strong></span><span class="sxs-lookup"><span data-stu-id="68517-115"><strong>Data Source</strong> or <strong>Server</strong></span></span></p></td>
<td><p><span data-ttu-id="68517-116">指定服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="68517-116">Specifies the name of a server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68517-117"><strong>Initial Catalog</strong> 或 <strong>Database</strong></span><span class="sxs-lookup"><span data-stu-id="68517-117"><strong>Initial Catalog</strong> or <strong>Database</strong></span></span></p></td>
<td><p><span data-ttu-id="68517-118">指定服务器上的数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="68517-118">Specifies the name of a database on the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68517-119"><strong>User ID</strong> 或 <strong>uid</strong></span><span class="sxs-lookup"><span data-stu-id="68517-119"><strong>User ID</strong> or <strong>uid</strong></span></span></p></td>
<td><p><span data-ttu-id="68517-120">指定用户名（用于 SQL Server 身份验证）。</span><span class="sxs-lookup"><span data-stu-id="68517-120">Specifies the user name (for SQL Server Authentication).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68517-121"><strong>Password</strong> 或 <strong>pwd</strong></span><span class="sxs-lookup"><span data-stu-id="68517-121"><strong>Password</strong> or <strong>pwd</strong></span></span></p></td>
<td><p><span data-ttu-id="68517-122">指定用户密码（用于 SQL Server 身份验证）。</span><span class="sxs-lookup"><span data-stu-id="68517-122">Specifies the user password (for SQL Server Authentication).</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="provider-specific-connection-parameters"></a><span data-ttu-id="68517-123">提供程序特定的连接参数</span><span class="sxs-lookup"><span data-stu-id="68517-123">Provider-Specific Connection Parameters</span></span>

<span data-ttu-id="68517-p101">除了支持 ADO 定义的那些参数以外，该提供程序还支持几个提供程序特定的连接参数。与 ADO 连接属性一样，可以通过 [Connection](properties-collection-ado.md) 的 [Properties](connection-object-ado.md) 集合或将其作为 **ConnectionString** 的一部分来设置这些提供程序特定的属性。</span><span class="sxs-lookup"><span data-stu-id="68517-p101">The provider supports several provider-specific connection parameters in addition to those defined by ADO. As with the ADO connection properties, these provider-specific properties can be set via the [Properties](properties-collection-ado.md) collection of a [Connection](connection-object-ado.md) or can be set as part of the **ConnectionString**.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="68517-126">参数</span><span class="sxs-lookup"><span data-stu-id="68517-126">Parameter</span></span></p></th>
<th><p><span data-ttu-id="68517-127">说明</span><span class="sxs-lookup"><span data-stu-id="68517-127">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="68517-128">Trusted_Connection</span><span class="sxs-lookup"><span data-stu-id="68517-128">Trusted_Connection</span></span></p></td>
<td><p><span data-ttu-id="68517-129">指示用户身份验证模式。</span><span class="sxs-lookup"><span data-stu-id="68517-129">Indicates the user authentication mode.</span></span> <span data-ttu-id="68517-130">这可以设置为<strong>是</strong>或<strong>否</strong>。</span><span class="sxs-lookup"><span data-stu-id="68517-130">This can be set to <strong>Yes</strong> or <strong>No</strong>.</span></span> <span data-ttu-id="68517-131">默认值为<strong>否</strong>。</span><span class="sxs-lookup"><span data-stu-id="68517-131">The default value is <strong>No</strong>.</span></span> <span data-ttu-id="68517-132">如果此属性设置为<strong>是</strong>，SQLOLEDB 将使用 Microsoft Windows NT 身份验证模式以授权用户访问的<strong>位置</strong>和<a href="datasource-property-ado.md">Datasource</a>属性值指定的 SQL Server 数据库。</span><span class="sxs-lookup"><span data-stu-id="68517-132">If this property is set to <strong>Yes</strong>, then SQLOLEDB uses Microsoft Windows NT Authentication Mode to authorize user access to the SQL Server database specified by the <strong>Location</strong> and <a href="datasource-property-ado.md">Datasource</a> property values.</span></span> <span data-ttu-id="68517-133">如果此属性设置为<strong>No</strong>，SQLOLEDB 将使用混合模式来授权用户访问 SQL Server 数据库。</span><span class="sxs-lookup"><span data-stu-id="68517-133">If this property is set to <strong>No</strong>, then SQLOLEDB uses Mixed Mode to authorize user access to the SQL Server database.</span></span> <span data-ttu-id="68517-134"><strong>用户 Id</strong>和<strong>密码</strong>属性中指定的 SQL Server 登录名和密码。</span><span class="sxs-lookup"><span data-stu-id="68517-134">The SQL Server login and password are specified in the <strong>User Id</strong> and <strong>Password</strong> properties.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68517-135">Current Language</span><span class="sxs-lookup"><span data-stu-id="68517-135">Current Language</span></span></p></td>
<td><p><span data-ttu-id="68517-p103">指示 SQL Server 语言名称。标识用于选择和设置系统消息格式的语言。必须在 SQL Server 上安装该语言，否则打开连接时就会失败。</span><span class="sxs-lookup"><span data-stu-id="68517-p103">Indicates a SQL Server language name. Identifies the language used for system message selection and formatting. The language must be installed on the SQL Server, otherwise opening the connection will fail.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68517-139">Network Address</span><span class="sxs-lookup"><span data-stu-id="68517-139">Network Address</span></span></p></td>
<td><p><span data-ttu-id="68517-140">指示通过 <strong>Location</strong> 属性指定的 SQL Server 的网络地址。</span><span class="sxs-lookup"><span data-stu-id="68517-140">Indicates the network address of the SQL Server specified by the <strong>Location</strong> property.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68517-141">Network Library</span><span class="sxs-lookup"><span data-stu-id="68517-141">Network Library</span></span></p></td>
<td><p><span data-ttu-id="68517-p104">指示用于与 SQL Server 进行通信的网络库（动态链接库）的名称。此名称不应包括路径或 .dll 文件扩展名。默认值由 SQL Server 客户端配置提供。</span><span class="sxs-lookup"><span data-stu-id="68517-p104">Indicates the name of the network library (dynamic-link libraries) used to communicate with the SQL Server. The name should not include the path or the .dll file name extension. The default is provided by the SQL Server client configuration.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68517-145">Use Procedure for Prepare</span><span class="sxs-lookup"><span data-stu-id="68517-145">Use Procedure for Prepare</span></span></p></td>
<td><p><span data-ttu-id="68517-146">确定在准备（通过 <strong>Prepared</strong> 属性）Command 时，SQL Server 是否创建临时的存储过程。</span><span class="sxs-lookup"><span data-stu-id="68517-146">Determines whether SQL Server creates temporary stored procedures when Commands are prepared (by the <strong>Prepared</strong> property).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68517-147">Auto Translate</span><span class="sxs-lookup"><span data-stu-id="68517-147">Auto Translate</span></span></p></td>
<td><p><span data-ttu-id="68517-148">指示是否将 OEM/ANSI 字符转换。</span><span class="sxs-lookup"><span data-stu-id="68517-148">Indicates whether OEM/ANSI characters are converted.</span></span> <span data-ttu-id="68517-149">此属性可以设置为<strong>True</strong>或<strong>False</strong>。</span><span class="sxs-lookup"><span data-stu-id="68517-149">This property can be set to <strong>True</strong> or <strong>False</strong>.</span></span> <span data-ttu-id="68517-150">默认值为 <strong>True</strong>。</span><span class="sxs-lookup"><span data-stu-id="68517-150">The default value is <strong>True</strong>.</span></span> <span data-ttu-id="68517-151">如果此属性设置为<strong>True</strong>，然后 SQLOLEDB OEM/ANSI 字符转换时执行从，检索多字节字符串或发给 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="68517-151">If this property is set to <strong>True</strong>, then SQLOLEDB performs OEM/ANSI character conversion when multi-byte character strings are retrieved from, or sent to, the SQL Server.</span></span> <span data-ttu-id="68517-152">如果此属性设置为<strong>False</strong>，SQLOLEDB 不 OEM/ANSI 字符转换执行多字节字符串数据。</span><span class="sxs-lookup"><span data-stu-id="68517-152">If this property is set to <strong>False</strong>, then SQLOLEDB does not perform OEM/ANSI character conversion on multi-byte character string data.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68517-153">Packet Size</span><span class="sxs-lookup"><span data-stu-id="68517-153">Packet Size</span></span></p></td>
<td><p><span data-ttu-id="68517-p106">指示网络数据包的大小（以字节为单位）。数据包大小属性值必须介于 512 与 32767 之间。默认的 SQLOLEDB 网络数据包大小为 4096。</span><span class="sxs-lookup"><span data-stu-id="68517-p106">Indicates a network packet size in bytes. The packet size property value must be between 512 and 32767. The default SQLOLEDB network packet size is 4096.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68517-157">Application Name</span><span class="sxs-lookup"><span data-stu-id="68517-157">Application Name</span></span></p></td>
<td><p><span data-ttu-id="68517-158">指示客户端应用程序名称。</span><span class="sxs-lookup"><span data-stu-id="68517-158">Indicates the client application name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68517-159">Workstation ID</span><span class="sxs-lookup"><span data-stu-id="68517-159">Workstation ID</span></span></p></td>
<td><p><span data-ttu-id="68517-160">标识工作站的字符串。</span><span class="sxs-lookup"><span data-stu-id="68517-160">A string identifying the workstation.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="command-object-usage"></a><span data-ttu-id="68517-161">Command 对象用法</span><span class="sxs-lookup"><span data-stu-id="68517-161">Command Object Usage</span></span>

<span data-ttu-id="68517-p107">SQLOLEDB 接受 ODBC、ANSI 以及 SQL Server 特定 Transact-SQL 的混合形式作为有效语法。例如，以下 SQL 语句使用 ODBC SQL 转义序列指定 LCASE 字符串函数：</span><span class="sxs-lookup"><span data-stu-id="68517-p107">SQLOLEDB accepts an amalgam of ODBC, ANSI, and SQL Server-specific Transact-SQL as valid syntax. For example, the following SQL statement uses an ODBC SQL escape sequence to specify the LCASE string function:</span></span>

```sql 
 
SELECT customerid={fn LCASE(CustomerID)} FROM Customers 
```

<span data-ttu-id="68517-p108">LCASE 将返回一个字符串，且将所有的大写字符都转换为小写字符等效项。ANSI SQL 字符串函数 LOWER 执行相同的操作，因此，以下 SQL 语句是与上面显示的 ODBC 语句等效的 ANSI 语句：</span><span class="sxs-lookup"><span data-stu-id="68517-p108">LCASE returns a character string, converting all uppercase characters to their lowercase equivalents. The ANSI SQL string function LOWER performs the same operation, so the following SQL statement is an ANSI equivalent to the ODBC statement presented above:</span></span>

```sql
 
SELECT customerid=LOWER(CustomerID) FROM Customers 
```

<span data-ttu-id="68517-166">SQLOLEDB 将成功处理指定为命令文本的这两种语句形式。</span><span class="sxs-lookup"><span data-stu-id="68517-166">SQLOLEDB successfully processes either form of the statement when specified as text for a command.</span></span>

## <a name="stored-procedures"></a><span data-ttu-id="68517-167">存储过程</span><span class="sxs-lookup"><span data-stu-id="68517-167">Stored Procedures</span></span>

<span data-ttu-id="68517-p109">使用 SQLOLEDB 命令执行 SQL Server 存储过程时，请在该命令文本中使用 ODBC 过程调用转义序列。随后，SQLOLEDB 将使用 SQL Server DE 的远程过程调用机制来优化命令处理。例如，以下 ODBC SQL 语句优于 Transact-SQL 形式的命令文本：</span><span class="sxs-lookup"><span data-stu-id="68517-p109">When executing a SQL Server stored procedure using a SQLOLEDB command, use the ODBC procedure call escape sequence in the command text. SQLOLEDB then uses the remote procedure call mechanism of SQL Server to optimize command processing. For example, the following ODBC SQL statement is the preferred command text over the Transact-SQL form:</span></span>

## <a name="odbc-sql"></a><span data-ttu-id="68517-171">ODBC SQL</span><span class="sxs-lookup"><span data-stu-id="68517-171">ODBC SQL</span></span>

```sql 
 
{call SalesByCategory('Produce', '1995')} 
```

## <a name="transact-sql"></a><span data-ttu-id="68517-172">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="68517-172">Transact-SQL</span></span>

```sql 
 
EXECUTE SalesByCategory 'Produce', '1995' 
```

## <a name="recordset-behavior"></a><span data-ttu-id="68517-173">Recordset 行为</span><span class="sxs-lookup"><span data-stu-id="68517-173">Recordset Behavior</span></span>

<span data-ttu-id="68517-p110">SQLOLEDB 无法使用 SQL Server 游标来支持通过许多命令生成的多个结果。如果用户请求需要 SQL Server 游标支持的记录集，则当使用的命令文本生成多个记录集作为结果时，将会发生错误。</span><span class="sxs-lookup"><span data-stu-id="68517-p110">SQLOLEDB cannot use SQL Server cursors to support the multiple-result generated by many commands. If a consumer requests a recordset requiring SQL Server cursor support, an error occurs if the command text used generates more than a single recordset as its result.</span></span>

<span data-ttu-id="68517-p111">SQL Server 游标支持可滚动的 SQLOLEDB 记录集。SQL Server 将针对对数据库的其他用户所做更改敏感的游标强制施加限制。具体来说，某些游标中的行不能进行排序，尝试使用包含 SQL ORDER BY 子句的命令创建记录集可能会失败。</span><span class="sxs-lookup"><span data-stu-id="68517-p111">Scrollable SQLOLEDB recordsets are supported by SQL Server cursors. SQL Server imposes limitations on cursors that are sensitive to changes made by other users of the database. Specifically, the rows in some cursors cannot be ordered, and attempting to create a recordset using a command containing an SQL ORDER BY clause can fail.</span></span>

## <a name="dynamic-properties"></a><span data-ttu-id="68517-179">动态属性</span><span class="sxs-lookup"><span data-stu-id="68517-179">Dynamic Properties</span></span>

<span data-ttu-id="68517-180">Microsoft OLE DB Provider for SQL Server 将多个动态属性插入到未打开的 **Connection**、[Recordset](connection-object-ado.md) 和 [Command](recordset-object-ado.md) 对象的 [Properties](command-object-ado.md) 集合中。</span><span class="sxs-lookup"><span data-stu-id="68517-180">The Microsoft OLE DB Provider for SQL Server inserts several dynamic properties into the **Properties** collection of the unopened [Connection](connection-object-ado.md), [Recordset](recordset-object-ado.md), and [Command](command-object-ado.md) objects.</span></span>

<span data-ttu-id="68517-p112">下面的表是每个动态属性的 ADO 和 OLE DB 名称的交叉索引。《OLE DB 程序员参考》使用术语"说明"来引用 ADO 属性名称。您可以在《OLE DB 程序员参考》中找到有关这些属性的详细信息。请在"索引"中搜索 OLE DB 属性名，或者请参阅"附录 C：OLE DB 属性"。</span><span class="sxs-lookup"><span data-stu-id="68517-p112">The following tables are a cross-index of the ADO and OLE DB names for each dynamic property. The OLE DB Programmer's Reference refers to an ADO property name by the term "Description." You can find more information about these properties in the OLE DB Programmer's Reference. Search for the OLE DB property name in the Index or see Appendix C: OLE DB Properties.</span></span>

## <a name="connection-dynamic-properties"></a><span data-ttu-id="68517-185">Connection 动态属性</span><span class="sxs-lookup"><span data-stu-id="68517-185">Connection Dynamic Properties</span></span>

<span data-ttu-id="68517-186">以下属性将被添加到 **Connection** 对象的 **Properties** 集合中。</span><span class="sxs-lookup"><span data-stu-id="68517-186">The following properties are added to the **Connection** object's **Properties** collection.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="68517-187">ADO 属性名</span><span class="sxs-lookup"><span data-stu-id="68517-187">ADO Property Name</span></span></p></th>
<th><p><span data-ttu-id="68517-188">OLE DB 属性名</span><span class="sxs-lookup"><span data-stu-id="68517-188">OLE DB Property Name</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="68517-189">Active Sessions</span><span class="sxs-lookup"><span data-stu-id="68517-189">Active Sessions</span></span></p></td>
<td><p><span data-ttu-id="68517-190">DBPROP_ACTIVESESSIONS</span><span class="sxs-lookup"><span data-stu-id="68517-190">DBPROP_ACTIVESESSIONS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68517-191">Asynchable Abort</span><span class="sxs-lookup"><span data-stu-id="68517-191">Asynchable Abort</span></span></p></td>
<td><p><span data-ttu-id="68517-192">DBPROP_ASYNCTXNABORT</span><span class="sxs-lookup"><span data-stu-id="68517-192">DBPROP_ASYNCTXNABORT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68517-193">Asynchable Commit</span><span class="sxs-lookup"><span data-stu-id="68517-193">Asynchable Commit</span></span></p></td>
<td><p><span data-ttu-id="68517-194">DBPROP_ASYNCTNXCOMMIT</span><span class="sxs-lookup"><span data-stu-id="68517-194">DBPROP_ASYNCTNXCOMMIT</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68517-195">Autocommit Isolation Levels</span><span class="sxs-lookup"><span data-stu-id="68517-195">Autocommit Isolation Levels</span></span></p></td>
<td><p><span data-ttu-id="68517-196">DBPROP_SESS_AUTOCOMMITISOLEVELS</span><span class="sxs-lookup"><span data-stu-id="68517-196">DBPROP_SESS_AUTOCOMMITISOLEVELS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68517-197">Catalog Location</span><span class="sxs-lookup"><span data-stu-id="68517-197">Catalog Location</span></span></p></td>
<td><p><span data-ttu-id="68517-198">DBPROP_CATALOGLOCATION</span><span class="sxs-lookup"><span data-stu-id="68517-198">DBPROP_CATALOGLOCATION</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68517-199">Catalog Term</span><span class="sxs-lookup"><span data-stu-id="68517-199">Catalog Term</span></span></p></td>
<td><p><span data-ttu-id="68517-200">DBPROP_CATALOGTERM</span><span class="sxs-lookup"><span data-stu-id="68517-200">DBPROP_CATALOGTERM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68517-201">Column Definition</span><span class="sxs-lookup"><span data-stu-id="68517-201">Column Definition</span></span></p></td>
<td><p><span data-ttu-id="68517-202">DBPROP_COLUMNDEFINITION</span><span class="sxs-lookup"><span data-stu-id="68517-202">DBPROP_COLUMNDEFINITION</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68517-203">Connect Timeout</span><span class="sxs-lookup"><span data-stu-id="68517-203">Connect Timeout</span></span></p></td>
<td><p><span data-ttu-id="68517-204">DBPROP_INIT_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="68517-204">DBPROP_INIT_TIMEOUT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68517-205">Current Catalog</span><span class="sxs-lookup"><span data-stu-id="68517-205">Current Catalog</span></span></p></td>
<td><p><span data-ttu-id="68517-206">DBPROP_CURRENTCATALOG</span><span class="sxs-lookup"><span data-stu-id="68517-206">DBPROP_CURRENTCATALOG</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68517-207">Data Source</span><span class="sxs-lookup"><span data-stu-id="68517-207">Data Source</span></span></p></td>
<td><p><span data-ttu-id="68517-208">DBPROP_INIT_DATASOURCE</span><span class="sxs-lookup"><span data-stu-id="68517-208">DBPROP_INIT_DATASOURCE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68517-209">Data Source Name</span><span class="sxs-lookup"><span data-stu-id="68517-209">Data Source Name</span></span></p></td>
<td><p><span data-ttu-id="68517-210">DBPROP_DATASOURCENAME</span><span class="sxs-lookup"><span data-stu-id="68517-210">DBPROP_DATASOURCENAME</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68517-211">Data Source Object Threading Model</span><span class="sxs-lookup"><span data-stu-id="68517-211">Data Source Object Threading Model</span></span></p></td>
<td><p><span data-ttu-id="68517-212">DBPROP_DSOTHREADMODEL</span><span class="sxs-lookup"><span data-stu-id="68517-212">DBPROP_DSOTHREADMODEL</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68517-213">DBMS Name</span><span class="sxs-lookup"><span data-stu-id="68517-213">DBMS Name</span></span></p></td>
<td><p><span data-ttu-id="68517-214">DBPROP_DBMSNAME</span><span class="sxs-lookup"><span data-stu-id="68517-214">DBPROP_DBMSNAME</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68517-215">DBMS Version</span><span class="sxs-lookup"><span data-stu-id="68517-215">DBMS Version</span></span></p></td>
<td><p><span data-ttu-id="68517-216">DBPROP_DBMSVER</span><span class="sxs-lookup"><span data-stu-id="68517-216">DBPROP_DBMSVER</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68517-217">Extended Properties</span><span class="sxs-lookup"><span data-stu-id="68517-217">Extended Properties</span></span></p></td>
<td><p><span data-ttu-id="68517-218">DBPROP_INIT_PROVIDERSTRING</span><span class="sxs-lookup"><span data-stu-id="68517-218">DBPROP_INIT_PROVIDERSTRING</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68517-219">GROUP BY Support</span><span class="sxs-lookup"><span data-stu-id="68517-219">GROUP BY Support</span></span></p></td>
<td><p><span data-ttu-id="68517-220">DBPROP_GROUPBY</span><span class="sxs-lookup"><span data-stu-id="68517-220">DBPROP_GROUPBY</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68517-221">Heterogeneous Table Support</span><span class="sxs-lookup"><span data-stu-id="68517-221">Heterogeneous Table Support</span></span></p></td>
<td><p><span data-ttu-id="68517-222">DBPROP_HETEROGENEOUSTABLES</span><span class="sxs-lookup"><span data-stu-id="68517-222">DBPROP_HETEROGENEOUSTABLES</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68517-223">Identifier Case Sensitivity</span><span class="sxs-lookup"><span data-stu-id="68517-223">Identifier Case Sensitivity</span></span></p></td>
<td><p><span data-ttu-id="68517-224">DBPROP_IDENTIFIERCASE</span><span class="sxs-lookup"><span data-stu-id="68517-224">DBPROP_IDENTIFIERCASE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68517-225">Initial Catalog</span><span class="sxs-lookup"><span data-stu-id="68517-225">Initial Catalog</span></span></p></td>
<td><p><span data-ttu-id="68517-226">DBPROP_INIT_CATALOG</span><span class="sxs-lookup"><span data-stu-id="68517-226">DBPROP_INIT_CATALOG</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68517-227">Isolation Levels</span><span class="sxs-lookup"><span data-stu-id="68517-227">Isolation Levels</span></span></p></td>
<td><p><span data-ttu-id="68517-228">DBPROP_SUPPORTEDTXNISOLEVELS</span><span class="sxs-lookup"><span data-stu-id="68517-228">DBPROP_SUPPORTEDTXNISOLEVELS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68517-229">Isolation Retention</span><span class="sxs-lookup"><span data-stu-id="68517-229">Isolation Retention</span></span></p></td>
<td><p><span data-ttu-id="68517-230">DBPROP_SUPPORTEDTXNISORETAIN</span><span class="sxs-lookup"><span data-stu-id="68517-230">DBPROP_SUPPORTEDTXNISORETAIN</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68517-231">Locale Identifier</span><span class="sxs-lookup"><span data-stu-id="68517-231">Locale Identifier</span></span></p></td>
<td><p><span data-ttu-id="68517-232">DBPROP_INIT_LCID</span><span class="sxs-lookup"><span data-stu-id="68517-232">DBPROP_INIT_LCID</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68517-233">Maximum Index Size</span><span class="sxs-lookup"><span data-stu-id="68517-233">Maximum Index Size</span></span></p></td>
<td><p><span data-ttu-id="68517-234">DBPROP_MAXINDEXSIZE</span><span class="sxs-lookup"><span data-stu-id="68517-234">DBPROP_MAXINDEXSIZE</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68517-235">Maximum Row Size</span><span class="sxs-lookup"><span data-stu-id="68517-235">Maximum Row Size</span></span></p></td>
<td><p><span data-ttu-id="68517-236">DBPROP_MAXROWSIZE</span><span class="sxs-lookup"><span data-stu-id="68517-236">DBPROP_MAXROWSIZE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68517-237">Maximum Row Size Includes BLOB</span><span class="sxs-lookup"><span data-stu-id="68517-237">Maximum Row Size Includes BLOB</span></span></p></td>
<td><p><span data-ttu-id="68517-238">DBPROP_MAXROWSIZEINCLUDESBLOB</span><span class="sxs-lookup"><span data-stu-id="68517-238">DBPROP_MAXROWSIZEINCLUDESBLOB</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68517-239">Maximum Tables in SELECT</span><span class="sxs-lookup"><span data-stu-id="68517-239">Maximum Tables in SELECT</span></span></p></td>
<td><p><span data-ttu-id="68517-240">DBPROP_MAXTABLESINSELECT</span><span class="sxs-lookup"><span data-stu-id="68517-240">DBPROP_MAXTABLESINSELECT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68517-241">Multiple Parameter Sets</span><span class="sxs-lookup"><span data-stu-id="68517-241">Multiple Parameter Sets</span></span></p></td>
<td><p><span data-ttu-id="68517-242">DBPROP_MULTIPLEPARAMSETS</span><span class="sxs-lookup"><span data-stu-id="68517-242">DBPROP_MULTIPLEPARAMSETS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68517-243">Multiple Results</span><span class="sxs-lookup"><span data-stu-id="68517-243">Multiple Results</span></span></p></td>
<td><p><span data-ttu-id="68517-244">DBPROP_MULTIPLERESULTS</span><span class="sxs-lookup"><span data-stu-id="68517-244">DBPROP_MULTIPLERESULTS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68517-245">Multiple Storage Objects</span><span class="sxs-lookup"><span data-stu-id="68517-245">Multiple Storage Objects</span></span></p></td>
<td><p><span data-ttu-id="68517-246">DBPROP_MULTIPLESTORAGEOBJECTS</span><span class="sxs-lookup"><span data-stu-id="68517-246">DBPROP_MULTIPLESTORAGEOBJECTS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68517-247">Multi-Table Update</span><span class="sxs-lookup"><span data-stu-id="68517-247">Multi-Table Update</span></span></p></td>
<td><p><span data-ttu-id="68517-248">DBPROP_MULTITABLEUPDATE</span><span class="sxs-lookup"><span data-stu-id="68517-248">DBPROP_MULTITABLEUPDATE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68517-249">NULL Collation Order</span><span class="sxs-lookup"><span data-stu-id="68517-249">NULL Collation Order</span></span></p></td>
<td><p><span data-ttu-id="68517-250">DBPROP_NULLCOLLATION</span><span class="sxs-lookup"><span data-stu-id="68517-250">DBPROP_NULLCOLLATION</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68517-251">NULL Concatenation Behavior</span><span class="sxs-lookup"><span data-stu-id="68517-251">NULL Concatenation Behavior</span></span></p></td>
<td><p><span data-ttu-id="68517-252">DBPROP_CONCATNULLBEHAVIOR</span><span class="sxs-lookup"><span data-stu-id="68517-252">DBPROP_CONCATNULLBEHAVIOR</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68517-253">OLE DB Version</span><span class="sxs-lookup"><span data-stu-id="68517-253">OLE DB Version</span></span></p></td>
<td><p><span data-ttu-id="68517-254">DBPROP_PROVIDEROLEDBVER</span><span class="sxs-lookup"><span data-stu-id="68517-254">DBPROP_PROVIDEROLEDBVER</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68517-255">OLE Object Support</span><span class="sxs-lookup"><span data-stu-id="68517-255">OLE Object Support</span></span></p></td>
<td><p><span data-ttu-id="68517-256">DBPROP_OLEOBJECTS</span><span class="sxs-lookup"><span data-stu-id="68517-256">DBPROP_OLEOBJECTS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68517-257">Open Rowset Support</span><span class="sxs-lookup"><span data-stu-id="68517-257">Open Rowset Support</span></span></p></td>
<td><p><span data-ttu-id="68517-258">DBPROP_OPENROWSETSUPPORT</span><span class="sxs-lookup"><span data-stu-id="68517-258">DBPROP_OPENROWSETSUPPORT</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68517-259">ORDER BY Columns in Select List</span><span class="sxs-lookup"><span data-stu-id="68517-259">ORDER BY Columns in Select List</span></span></p></td>
<td><p><span data-ttu-id="68517-260">DBPROP_ORDERBYCOLUMNSINSELECT</span><span class="sxs-lookup"><span data-stu-id="68517-260">DBPROP_ORDERBYCOLUMNSINSELECT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68517-261">Output Parameter Availability</span><span class="sxs-lookup"><span data-stu-id="68517-261">Output Parameter Availability</span></span></p></td>
<td><p><span data-ttu-id="68517-262">DBPROP_OUTPUTPARAMETERAVAILABILITY</span><span class="sxs-lookup"><span data-stu-id="68517-262">DBPROP_OUTPUTPARAMETERAVAILABILITY</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68517-263">Pass By Ref Accessors</span><span class="sxs-lookup"><span data-stu-id="68517-263">Pass By Ref Accessors</span></span></p></td>
<td><p><span data-ttu-id="68517-264">DBPROP_BYREFACCESSORS</span><span class="sxs-lookup"><span data-stu-id="68517-264">DBPROP_BYREFACCESSORS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68517-265">Password</span><span class="sxs-lookup"><span data-stu-id="68517-265">Password</span></span></p></td>
<td><p><span data-ttu-id="68517-266">DBPROP_AUTH_PASSWORD</span><span class="sxs-lookup"><span data-stu-id="68517-266">DBPROP_AUTH_PASSWORD</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68517-267">Persist Security Info</span><span class="sxs-lookup"><span data-stu-id="68517-267">Persist Security Info</span></span></p></td>
<td><p><span data-ttu-id="68517-268">DBPROP_AUTH_PERSIST_SENSITIVE_AUTHINFO</span><span class="sxs-lookup"><span data-stu-id="68517-268">DBPROP_AUTH_PERSIST_SENSITIVE_AUTHINFO</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68517-269">Persistent ID Type</span><span class="sxs-lookup"><span data-stu-id="68517-269">Persistent ID Type</span></span></p></td>
<td><p><span data-ttu-id="68517-270">DBPROP_PERSISTENTIDTYPE</span><span class="sxs-lookup"><span data-stu-id="68517-270">DBPROP_PERSISTENTIDTYPE</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68517-271">Prepare Abort Behavior</span><span class="sxs-lookup"><span data-stu-id="68517-271">Prepare Abort Behavior</span></span></p></td>
<td><p><span data-ttu-id="68517-272">DBPROP_PREPAREABORTBEHAVIOR</span><span class="sxs-lookup"><span data-stu-id="68517-272">DBPROP_PREPAREABORTBEHAVIOR</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68517-273">Prepare Commit Behavior</span><span class="sxs-lookup"><span data-stu-id="68517-273">Prepare Commit Behavior</span></span></p></td>
<td><p><span data-ttu-id="68517-274">DBPROP_PREPARECOMMITBEHAVIOR</span><span class="sxs-lookup"><span data-stu-id="68517-274">DBPROP_PREPARECOMMITBEHAVIOR</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68517-275">Procedure Term</span><span class="sxs-lookup"><span data-stu-id="68517-275">Procedure Term</span></span></p></td>
<td><p><span data-ttu-id="68517-276">DBPROP_PROCEDURETERM</span><span class="sxs-lookup"><span data-stu-id="68517-276">DBPROP_PROCEDURETERM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68517-277">Prompt</span><span class="sxs-lookup"><span data-stu-id="68517-277">Prompt</span></span></p></td>
<td><p><span data-ttu-id="68517-278">DBPROP_INIT_PROMPT</span><span class="sxs-lookup"><span data-stu-id="68517-278">DBPROP_INIT_PROMPT</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68517-279">Provider Friendly Name</span><span class="sxs-lookup"><span data-stu-id="68517-279">Provider Friendly Name</span></span></p></td>
<td><p><span data-ttu-id="68517-280">DBPROP_PROVIDERFRIENDLYNAME</span><span class="sxs-lookup"><span data-stu-id="68517-280">DBPROP_PROVIDERFRIENDLYNAME</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68517-281">Provider Name</span><span class="sxs-lookup"><span data-stu-id="68517-281">Provider Name</span></span></p></td>
<td><p><span data-ttu-id="68517-282">DBPROP_PROVIDERFILENAME</span><span class="sxs-lookup"><span data-stu-id="68517-282">DBPROP_PROVIDERFILENAME</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68517-283">Provider Version</span><span class="sxs-lookup"><span data-stu-id="68517-283">Provider Version</span></span></p></td>
<td><p><span data-ttu-id="68517-284">DBPROP_PROVIDERVER</span><span class="sxs-lookup"><span data-stu-id="68517-284">DBPROP_PROVIDERVER</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68517-285">Read-Only Data Source</span><span class="sxs-lookup"><span data-stu-id="68517-285">Read-Only Data Source</span></span></p></td>
<td><p><span data-ttu-id="68517-286">DBPROP_DATASOURCEREADONLY</span><span class="sxs-lookup"><span data-stu-id="68517-286">DBPROP_DATASOURCEREADONLY</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68517-287">Rowset Conversions on Command</span><span class="sxs-lookup"><span data-stu-id="68517-287">Rowset Conversions on Command</span></span></p></td>
<td><p><span data-ttu-id="68517-288">DBPROP_ROWSETCONVERSIONSONCOMMAND</span><span class="sxs-lookup"><span data-stu-id="68517-288">DBPROP_ROWSETCONVERSIONSONCOMMAND</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68517-289">Schema Term</span><span class="sxs-lookup"><span data-stu-id="68517-289">Schema Term</span></span></p></td>
<td><p><span data-ttu-id="68517-290">DBPROP_SCHEMATERM</span><span class="sxs-lookup"><span data-stu-id="68517-290">DBPROP_SCHEMATERM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68517-291">Schema Usage</span><span class="sxs-lookup"><span data-stu-id="68517-291">Schema Usage</span></span></p></td>
<td><p><span data-ttu-id="68517-292">DBPROP_SCHEMAUSAGE</span><span class="sxs-lookup"><span data-stu-id="68517-292">DBPROP_SCHEMAUSAGE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68517-293">SQL Support</span><span class="sxs-lookup"><span data-stu-id="68517-293">SQL Support</span></span></p></td>
<td><p><span data-ttu-id="68517-294">DBPROP_SQLSUPPORT</span><span class="sxs-lookup"><span data-stu-id="68517-294">DBPROP_SQLSUPPORT</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68517-295">Structured Storage</span><span class="sxs-lookup"><span data-stu-id="68517-295">Structured Storage</span></span></p></td>
<td><p><span data-ttu-id="68517-296">DBPROP_STRUCTUREDSTORAGE</span><span class="sxs-lookup"><span data-stu-id="68517-296">DBPROP_STRUCTUREDSTORAGE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68517-297">Subquery Support</span><span class="sxs-lookup"><span data-stu-id="68517-297">Subquery Support</span></span></p></td>
<td><p><span data-ttu-id="68517-298">DBPROP_SUBQUERIES</span><span class="sxs-lookup"><span data-stu-id="68517-298">DBPROP_SUBQUERIES</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68517-299">Table Term</span><span class="sxs-lookup"><span data-stu-id="68517-299">Table Term</span></span></p></td>
<td><p><span data-ttu-id="68517-300">DBPROP_TABLETERM</span><span class="sxs-lookup"><span data-stu-id="68517-300">DBPROP_TABLETERM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68517-301">Transaction DDL</span><span class="sxs-lookup"><span data-stu-id="68517-301">Transaction DDL</span></span></p></td>
<td><p><span data-ttu-id="68517-302">DBPROP_SUPPORTEDTXNDDL</span><span class="sxs-lookup"><span data-stu-id="68517-302">DBPROP_SUPPORTEDTXNDDL</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68517-303">User ID</span><span class="sxs-lookup"><span data-stu-id="68517-303">User ID</span></span></p></td>
<td><p><span data-ttu-id="68517-304">DBPROP_AUTH_USERID</span><span class="sxs-lookup"><span data-stu-id="68517-304">DBPROP_AUTH_USERID</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68517-305">User Name</span><span class="sxs-lookup"><span data-stu-id="68517-305">User Name</span></span></p></td>
<td><p><span data-ttu-id="68517-306">DBPROP_USERNAME</span><span class="sxs-lookup"><span data-stu-id="68517-306">DBPROP_USERNAME</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68517-307">Window Handle</span><span class="sxs-lookup"><span data-stu-id="68517-307">Window Handle</span></span></p></td>
<td><p><span data-ttu-id="68517-308">DBPROP_INIT_HWND</span><span class="sxs-lookup"><span data-stu-id="68517-308">DBPROP_INIT_HWND</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="recordset-dynamic-properties"></a><span data-ttu-id="68517-309">Recordset 动态属性</span><span class="sxs-lookup"><span data-stu-id="68517-309">Recordset Dynamic Properties</span></span>

<span data-ttu-id="68517-310">以下属性将被添加到 **Recordset** 对象的 **Properties** 集合中。</span><span class="sxs-lookup"><span data-stu-id="68517-310">The following properties are added to the **Recordset** object's **Properties** collection.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="68517-311">ADO 属性名</span><span class="sxs-lookup"><span data-stu-id="68517-311">ADO Property Name</span></span></p></th>
<th><p><span data-ttu-id="68517-312">OLE DB 属性名</span><span class="sxs-lookup"><span data-stu-id="68517-312">OLE DB Property Name</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="68517-313">Access Order</span><span class="sxs-lookup"><span data-stu-id="68517-313">Access Order</span></span></p></td>
<td><p><span data-ttu-id="68517-314">DBPROP_ACCESSORDER</span><span class="sxs-lookup"><span data-stu-id="68517-314">DBPROP_ACCESSORDER</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68517-315">Blocking Storage Objects</span><span class="sxs-lookup"><span data-stu-id="68517-315">Blocking Storage Objects</span></span></p></td>
<td><p><span data-ttu-id="68517-316">DBPROP_BLOCKINGSTORAGEOBJECTS</span><span class="sxs-lookup"><span data-stu-id="68517-316">DBPROP_BLOCKINGSTORAGEOBJECTS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68517-317">Bookmark Type</span><span class="sxs-lookup"><span data-stu-id="68517-317">Bookmark Type</span></span></p></td>
<td><p><span data-ttu-id="68517-318">DBPROP_BOOKMARKTYPE</span><span class="sxs-lookup"><span data-stu-id="68517-318">DBPROP_BOOKMARKTYPE</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68517-319">Bookmarkable</span><span class="sxs-lookup"><span data-stu-id="68517-319">Bookmarkable</span></span></p></td>
<td><p><span data-ttu-id="68517-320">DBPROP_IROWSETLOCATE</span><span class="sxs-lookup"><span data-stu-id="68517-320">DBPROP_IROWSETLOCATE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68517-321">Change Inserted Rows</span><span class="sxs-lookup"><span data-stu-id="68517-321">Change Inserted Rows</span></span></p></td>
<td><p><span data-ttu-id="68517-322">DBPROP_CHANGEINSERTEDROWS</span><span class="sxs-lookup"><span data-stu-id="68517-322">DBPROP_CHANGEINSERTEDROWS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68517-323">Column Privileges</span><span class="sxs-lookup"><span data-stu-id="68517-323">Column Privileges</span></span></p></td>
<td><p><span data-ttu-id="68517-324">DBPROP_COLUMNRESTRICT</span><span class="sxs-lookup"><span data-stu-id="68517-324">DBPROP_COLUMNRESTRICT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68517-325">Column Set Notification</span><span class="sxs-lookup"><span data-stu-id="68517-325">Column Set Notification</span></span></p></td>
<td><p><span data-ttu-id="68517-326">DBPROP_NOTIFYCOLUMNSET</span><span class="sxs-lookup"><span data-stu-id="68517-326">DBPROP_NOTIFYCOLUMNSET</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68517-327">Command Time Out</span><span class="sxs-lookup"><span data-stu-id="68517-327">Command Time Out</span></span></p></td>
<td><p><span data-ttu-id="68517-328">DBPROP_COMMANDTIMEOUT</span><span class="sxs-lookup"><span data-stu-id="68517-328">DBPROP_COMMANDTIMEOUT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68517-329">Defer Column</span><span class="sxs-lookup"><span data-stu-id="68517-329">Defer Column</span></span></p></td>
<td><p><span data-ttu-id="68517-330">DBPROP_DEFERRED</span><span class="sxs-lookup"><span data-stu-id="68517-330">DBPROP_DEFERRED</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68517-331">Delay Storage Object Updates</span><span class="sxs-lookup"><span data-stu-id="68517-331">Delay Storage Object Updates</span></span></p></td>
<td><p><span data-ttu-id="68517-332">DBPROP_DELAYSTORAGEOBJECTS</span><span class="sxs-lookup"><span data-stu-id="68517-332">DBPROP_DELAYSTORAGEOBJECTS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68517-333">Fetch Backwards</span><span class="sxs-lookup"><span data-stu-id="68517-333">Fetch Backwards</span></span></p></td>
<td><p><span data-ttu-id="68517-334">DBPROP_CANFETCHBACKWARDS</span><span class="sxs-lookup"><span data-stu-id="68517-334">DBPROP_CANFETCHBACKWARDS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68517-335">Hold Rows</span><span class="sxs-lookup"><span data-stu-id="68517-335">Hold Rows</span></span></p></td>
<td><p><span data-ttu-id="68517-336">DBPROP_CANHOLDROWS</span><span class="sxs-lookup"><span data-stu-id="68517-336">DBPROP_CANHOLDROWS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68517-337">IAccessor</span><span class="sxs-lookup"><span data-stu-id="68517-337">IAccessor</span></span></p></td>
<td><p><span data-ttu-id="68517-338">DBPROP_IAccessor</span><span class="sxs-lookup"><span data-stu-id="68517-338">DBPROP_IAccessor</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68517-339">IColumnsInfo</span><span class="sxs-lookup"><span data-stu-id="68517-339">IColumnsInfo</span></span></p></td>
<td><p><span data-ttu-id="68517-340">DBPROP_IColumnsInfo</span><span class="sxs-lookup"><span data-stu-id="68517-340">DBPROP_IColumnsInfo</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68517-341">IColumnsRowset</span><span class="sxs-lookup"><span data-stu-id="68517-341">IColumnsRowset</span></span></p></td>
<td><p><span data-ttu-id="68517-342">DBPROP_IColumnsRowset</span><span class="sxs-lookup"><span data-stu-id="68517-342">DBPROP_IColumnsRowset</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68517-343">IConnectionPointContainer</span><span class="sxs-lookup"><span data-stu-id="68517-343">IConnectionPointContainer</span></span></p></td>
<td><p><span data-ttu-id="68517-344">DBPROP_IConnectionPointContainer</span><span class="sxs-lookup"><span data-stu-id="68517-344">DBPROP_IConnectionPointContainer</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68517-345">IConvertType</span><span class="sxs-lookup"><span data-stu-id="68517-345">IConvertType</span></span></p></td>
<td><p><span data-ttu-id="68517-346">DBPROP_IConvertType</span><span class="sxs-lookup"><span data-stu-id="68517-346">DBPROP_IConvertType</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68517-347">Immobile Rows</span><span class="sxs-lookup"><span data-stu-id="68517-347">Immobile Rows</span></span></p></td>
<td><p><span data-ttu-id="68517-348">DBPROP_IMMOBILEROWS</span><span class="sxs-lookup"><span data-stu-id="68517-348">DBPROP_IMMOBILEROWS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68517-349">IRowset</span><span class="sxs-lookup"><span data-stu-id="68517-349">IRowset</span></span></p></td>
<td><p><span data-ttu-id="68517-350">DBPROP_IRowset</span><span class="sxs-lookup"><span data-stu-id="68517-350">DBPROP_IRowset</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68517-351">IRowsetChange</span><span class="sxs-lookup"><span data-stu-id="68517-351">IRowsetChange</span></span></p></td>
<td><p><span data-ttu-id="68517-352">DBPROP_IRowsetChange</span><span class="sxs-lookup"><span data-stu-id="68517-352">DBPROP_IRowsetChange</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68517-353">IRowsetIdentity</span><span class="sxs-lookup"><span data-stu-id="68517-353">IRowsetIdentity</span></span></p></td>
<td><p><span data-ttu-id="68517-354">DBPROP_IRowsetIdentity</span><span class="sxs-lookup"><span data-stu-id="68517-354">DBPROP_IRowsetIdentity</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68517-355">IRowsetInfo</span><span class="sxs-lookup"><span data-stu-id="68517-355">IRowsetInfo</span></span></p></td>
<td><p><span data-ttu-id="68517-356">DBPROP_IRowsetInfo</span><span class="sxs-lookup"><span data-stu-id="68517-356">DBPROP_IRowsetInfo</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68517-357">IRowsetLocate</span><span class="sxs-lookup"><span data-stu-id="68517-357">IRowsetLocate</span></span></p></td>
<td><p><span data-ttu-id="68517-358">DBPROP_IRowsestLocate</span><span class="sxs-lookup"><span data-stu-id="68517-358">DBPROP_IRowsestLocate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68517-359">IRowsetResynch</span><span class="sxs-lookup"><span data-stu-id="68517-359">IRowsetResynch</span></span></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68517-360">IRowsetScroll</span><span class="sxs-lookup"><span data-stu-id="68517-360">IRowsetScroll</span></span></p></td>
<td><p><span data-ttu-id="68517-361">DBPROP_IRowsetScroll</span><span class="sxs-lookup"><span data-stu-id="68517-361">DBPROP_IRowsetScroll</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68517-362">IRowsetUpdate</span><span class="sxs-lookup"><span data-stu-id="68517-362">IRowsetUpdate</span></span></p></td>
<td><p><span data-ttu-id="68517-363">DBPROP_IRowsetUpdate</span><span class="sxs-lookup"><span data-stu-id="68517-363">DBPROP_IRowsetUpdate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68517-364">ISequentialStream</span><span class="sxs-lookup"><span data-stu-id="68517-364">ISequentialStream</span></span></p></td>
<td><p><span data-ttu-id="68517-365">DBPROP_ISequentialStream</span><span class="sxs-lookup"><span data-stu-id="68517-365">DBPROP_ISequentialStream</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68517-366">ISupportErrorInfo</span><span class="sxs-lookup"><span data-stu-id="68517-366">ISupportErrorInfo</span></span></p></td>
<td><p><span data-ttu-id="68517-367">DBPROP_ISupportErrorInfo</span><span class="sxs-lookup"><span data-stu-id="68517-367">DBPROP_ISupportErrorInfo</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68517-368">Literal Bookmarks</span><span class="sxs-lookup"><span data-stu-id="68517-368">Literal Bookmarks</span></span></p></td>
<td><p><span data-ttu-id="68517-369">DBPROP_LITERALBOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="68517-369">DBPROP_LITERALBOOKMARKS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68517-370">Literal Row Identity</span><span class="sxs-lookup"><span data-stu-id="68517-370">Literal Row Identity</span></span></p></td>
<td><p><span data-ttu-id="68517-371">DBPROP_LITERALIDENTITY</span><span class="sxs-lookup"><span data-stu-id="68517-371">DBPROP_LITERALIDENTITY</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68517-372">Maximum Open Rows</span><span class="sxs-lookup"><span data-stu-id="68517-372">Maximum Open Rows</span></span></p></td>
<td><p><span data-ttu-id="68517-373">DBPROP_MAXOPENROWS</span><span class="sxs-lookup"><span data-stu-id="68517-373">DBPROP_MAXOPENROWS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68517-374">Maximum Pending Rows</span><span class="sxs-lookup"><span data-stu-id="68517-374">Maximum Pending Rows</span></span></p></td>
<td><p><span data-ttu-id="68517-375">DBPROP_MAXPENDINGROWS</span><span class="sxs-lookup"><span data-stu-id="68517-375">DBPROP_MAXPENDINGROWS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68517-376">Maximum Rows</span><span class="sxs-lookup"><span data-stu-id="68517-376">Maximum Rows</span></span></p></td>
<td><p><span data-ttu-id="68517-377">DBPROP_MAXROWS</span><span class="sxs-lookup"><span data-stu-id="68517-377">DBPROP_MAXROWS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68517-378">Notification Granularity</span><span class="sxs-lookup"><span data-stu-id="68517-378">Notification Granularity</span></span></p></td>
<td><p><span data-ttu-id="68517-379">DBPROP_NOTIFICATIONGRANULARITY</span><span class="sxs-lookup"><span data-stu-id="68517-379">DBPROP_NOTIFICATIONGRANULARITY</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68517-380">Notification Phases</span><span class="sxs-lookup"><span data-stu-id="68517-380">Notification Phases</span></span></p></td>
<td><p><span data-ttu-id="68517-381">DBPROP_NOTIFICATIONPHASES</span><span class="sxs-lookup"><span data-stu-id="68517-381">DBPROP_NOTIFICATIONPHASES</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68517-382">Objects Transacted</span><span class="sxs-lookup"><span data-stu-id="68517-382">Objects Transacted</span></span></p></td>
<td><p><span data-ttu-id="68517-383">DBPROP_TRANSACTEDOBJECT</span><span class="sxs-lookup"><span data-stu-id="68517-383">DBPROP_TRANSACTEDOBJECT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68517-384">Others' Changes Visible</span><span class="sxs-lookup"><span data-stu-id="68517-384">Others' Changes Visible</span></span></p></td>
<td><p><span data-ttu-id="68517-385">DBPROP_OTHERUPDATEDELETE</span><span class="sxs-lookup"><span data-stu-id="68517-385">DBPROP_OTHERUPDATEDELETE</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68517-386">Others' Inserts Visible</span><span class="sxs-lookup"><span data-stu-id="68517-386">Others' Inserts Visible</span></span></p></td>
<td><p><span data-ttu-id="68517-387">DBPROP_OTHERINSERT</span><span class="sxs-lookup"><span data-stu-id="68517-387">DBPROP_OTHERINSERT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68517-388">Own Changes Visible</span><span class="sxs-lookup"><span data-stu-id="68517-388">Own Changes Visible</span></span></p></td>
<td><p><span data-ttu-id="68517-389">DBPROP_OWNUPDATEDELETE</span><span class="sxs-lookup"><span data-stu-id="68517-389">DBPROP_OWNUPDATEDELETE</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68517-390">Own Inserts Visible</span><span class="sxs-lookup"><span data-stu-id="68517-390">Own Inserts Visible</span></span></p></td>
<td><p><span data-ttu-id="68517-391">DBPROP_OWNINSERT</span><span class="sxs-lookup"><span data-stu-id="68517-391">DBPROP_OWNINSERT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68517-392">Preserve on Abort</span><span class="sxs-lookup"><span data-stu-id="68517-392">Preserve on Abort</span></span></p></td>
<td><p><span data-ttu-id="68517-393">DBPROP_ABORTPRESERVE</span><span class="sxs-lookup"><span data-stu-id="68517-393">DBPROP_ABORTPRESERVE</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68517-394">Preserve on Commit</span><span class="sxs-lookup"><span data-stu-id="68517-394">Preserve on Commit</span></span></p></td>
<td><p><span data-ttu-id="68517-395">DBPROP_COMMITPRESERVE</span><span class="sxs-lookup"><span data-stu-id="68517-395">DBPROP_COMMITPRESERVE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68517-396">Quick Restart</span><span class="sxs-lookup"><span data-stu-id="68517-396">Quick Restart</span></span></p></td>
<td><p><span data-ttu-id="68517-397">DBPROP_QUICKRESTART</span><span class="sxs-lookup"><span data-stu-id="68517-397">DBPROP_QUICKRESTART</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68517-398">Reentrant Events</span><span class="sxs-lookup"><span data-stu-id="68517-398">Reentrant Events</span></span></p></td>
<td><p><span data-ttu-id="68517-399">DBPROP_REENTRANTEVENTS</span><span class="sxs-lookup"><span data-stu-id="68517-399">DBPROP_REENTRANTEVENTS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68517-400">Remove Deleted Rows</span><span class="sxs-lookup"><span data-stu-id="68517-400">Remove Deleted Rows</span></span></p></td>
<td><p><span data-ttu-id="68517-401">DBPROP_REMOVEDELETED</span><span class="sxs-lookup"><span data-stu-id="68517-401">DBPROP_REMOVEDELETED</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68517-402">Report Multiple Changes</span><span class="sxs-lookup"><span data-stu-id="68517-402">Report Multiple Changes</span></span></p></td>
<td><p><span data-ttu-id="68517-403">DBPROP_REPORTMULTIPLECHANGES</span><span class="sxs-lookup"><span data-stu-id="68517-403">DBPROP_REPORTMULTIPLECHANGES</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68517-404">Return Pending Inserts</span><span class="sxs-lookup"><span data-stu-id="68517-404">Return Pending Inserts</span></span></p></td>
<td><p><span data-ttu-id="68517-405">DBPROP_RETURNPENDINGINSERTS</span><span class="sxs-lookup"><span data-stu-id="68517-405">DBPROP_RETURNPENDINGINSERTS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68517-406">Row Delete Notification</span><span class="sxs-lookup"><span data-stu-id="68517-406">Row Delete Notification</span></span></p></td>
<td><p><span data-ttu-id="68517-407">DBPROP_NOTIFYROWDELETE</span><span class="sxs-lookup"><span data-stu-id="68517-407">DBPROP_NOTIFYROWDELETE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68517-408">Row First Change Notification</span><span class="sxs-lookup"><span data-stu-id="68517-408">Row First Change Notification</span></span></p></td>
<td><p><span data-ttu-id="68517-409">DBPROP_NOTIFYROWFIRSTCHANGE</span><span class="sxs-lookup"><span data-stu-id="68517-409">DBPROP_NOTIFYROWFIRSTCHANGE</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68517-410">Row Insert Notification</span><span class="sxs-lookup"><span data-stu-id="68517-410">Row Insert Notification</span></span></p></td>
<td><p><span data-ttu-id="68517-411">DBPROP_NOTIFYROWINSERT</span><span class="sxs-lookup"><span data-stu-id="68517-411">DBPROP_NOTIFYROWINSERT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68517-412">Row Privileges</span><span class="sxs-lookup"><span data-stu-id="68517-412">Row Privileges</span></span></p></td>
<td><p><span data-ttu-id="68517-413">DBPROP_ROWRESTRICT</span><span class="sxs-lookup"><span data-stu-id="68517-413">DBPROP_ROWRESTRICT</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68517-414">Row Resynchronization Notification</span><span class="sxs-lookup"><span data-stu-id="68517-414">Row Resynchronization Notification</span></span></p></td>
<td><p><span data-ttu-id="68517-415">DBPROP_NOTIFYROWRESYNCH</span><span class="sxs-lookup"><span data-stu-id="68517-415">DBPROP_NOTIFYROWRESYNCH</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68517-416">Row Threading Model</span><span class="sxs-lookup"><span data-stu-id="68517-416">Row Threading Model</span></span></p></td>
<td><p><span data-ttu-id="68517-417">DBPROP_ROWTHREADMODEL</span><span class="sxs-lookup"><span data-stu-id="68517-417">DBPROP_ROWTHREADMODEL</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68517-418">Row Undo Change Notification</span><span class="sxs-lookup"><span data-stu-id="68517-418">Row Undo Change Notification</span></span></p></td>
<td><p><span data-ttu-id="68517-419">DBPROP_NOTIFYROWUNDOCHANGE</span><span class="sxs-lookup"><span data-stu-id="68517-419">DBPROP_NOTIFYROWUNDOCHANGE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68517-420">Row Undo Delete Notification</span><span class="sxs-lookup"><span data-stu-id="68517-420">Row Undo Delete Notification</span></span></p></td>
<td><p><span data-ttu-id="68517-421">DBPROP_NOTIFYROWUNDODELETE</span><span class="sxs-lookup"><span data-stu-id="68517-421">DBPROP_NOTIFYROWUNDODELETE</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68517-422">Row Undo Insert Notification</span><span class="sxs-lookup"><span data-stu-id="68517-422">Row Undo Insert Notification</span></span></p></td>
<td><p><span data-ttu-id="68517-423">DBPROP_NOTIFYROWUNDOINSERT</span><span class="sxs-lookup"><span data-stu-id="68517-423">DBPROP_NOTIFYROWUNDOINSERT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68517-424">Row Update Notification</span><span class="sxs-lookup"><span data-stu-id="68517-424">Row Update Notification</span></span></p></td>
<td><p><span data-ttu-id="68517-425">DBPROP_NOTIFYROWUPDATE</span><span class="sxs-lookup"><span data-stu-id="68517-425">DBPROP_NOTIFYROWUPDATE</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68517-426">Rowset Fetch Position Change Notification</span><span class="sxs-lookup"><span data-stu-id="68517-426">Rowset Fetch Position Change Notification</span></span></p></td>
<td><p><span data-ttu-id="68517-427">DBPROP_NOTIFYROWSETFETCHPOSISIONCHANGE</span><span class="sxs-lookup"><span data-stu-id="68517-427">DBPROP_NOTIFYROWSETFETCHPOSISIONCHANGE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68517-428">Rowset Release Notification</span><span class="sxs-lookup"><span data-stu-id="68517-428">Rowset Release Notification</span></span></p></td>
<td><p><span data-ttu-id="68517-429">DBPROP_NOTIFYROWSETRELEASE</span><span class="sxs-lookup"><span data-stu-id="68517-429">DBPROP_NOTIFYROWSETRELEASE</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68517-430">Scroll Backwards</span><span class="sxs-lookup"><span data-stu-id="68517-430">Scroll Backwards</span></span></p></td>
<td><p><span data-ttu-id="68517-431">DBPROP_CANSCROLLBACKWARDS</span><span class="sxs-lookup"><span data-stu-id="68517-431">DBPROP_CANSCROLLBACKWARDS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68517-432">Server Cursor</span><span class="sxs-lookup"><span data-stu-id="68517-432">Server Cursor</span></span></p></td>
<td><p><span data-ttu-id="68517-433">DBPROP_SERVERCURSOR</span><span class="sxs-lookup"><span data-stu-id="68517-433">DBPROP_SERVERCURSOR</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68517-434">Skip Deleted Bookmarks</span><span class="sxs-lookup"><span data-stu-id="68517-434">Skip Deleted Bookmarks</span></span></p></td>
<td><p><span data-ttu-id="68517-435">DBPROP_BOOKMARKSKIPPED</span><span class="sxs-lookup"><span data-stu-id="68517-435">DBPROP_BOOKMARKSKIPPED</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68517-436">Strong Row Identity</span><span class="sxs-lookup"><span data-stu-id="68517-436">Strong Row Identity</span></span></p></td>
<td><p><span data-ttu-id="68517-437">DBPROP_STRONGITDENTITY</span><span class="sxs-lookup"><span data-stu-id="68517-437">DBPROP_STRONGITDENTITY</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68517-438">Unique Rows</span><span class="sxs-lookup"><span data-stu-id="68517-438">Unique Rows</span></span></p></td>
<td><p><span data-ttu-id="68517-439">DBPROP_UNIQUEROWS</span><span class="sxs-lookup"><span data-stu-id="68517-439">DBPROP_UNIQUEROWS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68517-440">Updatability</span><span class="sxs-lookup"><span data-stu-id="68517-440">Updatability</span></span></p></td>
<td><p><span data-ttu-id="68517-441">DBPROP_UPDATABILITY</span><span class="sxs-lookup"><span data-stu-id="68517-441">DBPROP_UPDATABILITY</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68517-442">Use Bookmarks</span><span class="sxs-lookup"><span data-stu-id="68517-442">Use Bookmarks</span></span></p></td>
<td><p><span data-ttu-id="68517-443">DBPROP_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="68517-443">DBPROP_BOOKMARKS</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="command-dynamic-properties"></a><span data-ttu-id="68517-444">Command 动态属性</span><span class="sxs-lookup"><span data-stu-id="68517-444">Command Dynamic Properties</span></span>

<span data-ttu-id="68517-445">以下属性将被添加到 **Command** 对象的 **Properties** 集合中。</span><span class="sxs-lookup"><span data-stu-id="68517-445">The following properties are added to the **Command** object's **Properties** collection.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="68517-446">ADO 属性名</span><span class="sxs-lookup"><span data-stu-id="68517-446">ADO Property Name</span></span></p></th>
<th><p><span data-ttu-id="68517-447">OLE DB 属性名</span><span class="sxs-lookup"><span data-stu-id="68517-447">OLE DB Property Name</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="68517-448">Access Order</span><span class="sxs-lookup"><span data-stu-id="68517-448">Access Order</span></span></p></td>
<td><p><span data-ttu-id="68517-449">DBPROP_ACCESSORDER</span><span class="sxs-lookup"><span data-stu-id="68517-449">DBPROP_ACCESSORDER</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68517-450">Base Path</span><span class="sxs-lookup"><span data-stu-id="68517-450">Base Path</span></span></p></td>
<td><p><span data-ttu-id="68517-451">SSPROP_STREAM_BASEPATH</span><span class="sxs-lookup"><span data-stu-id="68517-451">SSPROP_STREAM_BASEPATH</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68517-452">Blocking Storage Objects</span><span class="sxs-lookup"><span data-stu-id="68517-452">Blocking Storage Objects</span></span></p></td>
<td><p><span data-ttu-id="68517-453">DBPROP_BLOCKINGSTORAGEOBJECTS</span><span class="sxs-lookup"><span data-stu-id="68517-453">DBPROP_BLOCKINGSTORAGEOBJECTS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68517-454">Bookmark Type</span><span class="sxs-lookup"><span data-stu-id="68517-454">Bookmark Type</span></span></p></td>
<td><p><span data-ttu-id="68517-455">DBPROP_BOOKMARKTYPE</span><span class="sxs-lookup"><span data-stu-id="68517-455">DBPROP_BOOKMARKTYPE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68517-456">Bookmarkable</span><span class="sxs-lookup"><span data-stu-id="68517-456">Bookmarkable</span></span></p></td>
<td><p><span data-ttu-id="68517-457">DBPROP_IROWSETLOCATE</span><span class="sxs-lookup"><span data-stu-id="68517-457">DBPROP_IROWSETLOCATE</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68517-458">Change Inserted Rows</span><span class="sxs-lookup"><span data-stu-id="68517-458">Change Inserted Rows</span></span></p></td>
<td><p><span data-ttu-id="68517-459">DBPROP_CHANGEINSERTEDROWS</span><span class="sxs-lookup"><span data-stu-id="68517-459">DBPROP_CHANGEINSERTEDROWS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68517-460">Column Privileges</span><span class="sxs-lookup"><span data-stu-id="68517-460">Column Privileges</span></span></p></td>
<td><p><span data-ttu-id="68517-461">DBPROP_COLUMNRESTRICT</span><span class="sxs-lookup"><span data-stu-id="68517-461">DBPROP_COLUMNRESTRICT</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68517-462">Column Set Notification</span><span class="sxs-lookup"><span data-stu-id="68517-462">Column Set Notification</span></span></p></td>
<td><p><span data-ttu-id="68517-463">DBPROP_NOTIFYCOLUMNSET</span><span class="sxs-lookup"><span data-stu-id="68517-463">DBPROP_NOTIFYCOLUMNSET</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68517-464">Content Type</span><span class="sxs-lookup"><span data-stu-id="68517-464">Content Type</span></span></p></td>
<td><p><span data-ttu-id="68517-465">SSPROP_STREAM_CONTENTTYPE</span><span class="sxs-lookup"><span data-stu-id="68517-465">SSPROP_STREAM_CONTENTTYPE</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68517-466">Cursor Auto Fetch</span><span class="sxs-lookup"><span data-stu-id="68517-466">Cursor Auto Fetch</span></span></p></td>
<td><p><span data-ttu-id="68517-467">SSPROP_CURSORAUTOFETCH</span><span class="sxs-lookup"><span data-stu-id="68517-467">SSPROP_CURSORAUTOFETCH</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68517-468">Defer Column</span><span class="sxs-lookup"><span data-stu-id="68517-468">Defer Column</span></span></p></td>
<td><p><span data-ttu-id="68517-469">DBPROP_DEFERRED</span><span class="sxs-lookup"><span data-stu-id="68517-469">DBPROP_DEFERRED</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68517-470">Defer Prepare</span><span class="sxs-lookup"><span data-stu-id="68517-470">Defer Prepare</span></span></p></td>
<td><p><span data-ttu-id="68517-471">SSPROP_DEFERPREPARE</span><span class="sxs-lookup"><span data-stu-id="68517-471">SSPROP_DEFERPREPARE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68517-472">Delay Storage Object Updates</span><span class="sxs-lookup"><span data-stu-id="68517-472">Delay Storage Object Updates</span></span></p></td>
<td><p><span data-ttu-id="68517-473">DBPROP_DELAYSTORAGEOBJECTS</span><span class="sxs-lookup"><span data-stu-id="68517-473">DBPROP_DELAYSTORAGEOBJECTS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68517-474">Fetch Backwards</span><span class="sxs-lookup"><span data-stu-id="68517-474">Fetch Backwards</span></span></p></td>
<td><p><span data-ttu-id="68517-475">DBPROP_CANFETCHBACKWARDS</span><span class="sxs-lookup"><span data-stu-id="68517-475">DBPROP_CANFETCHBACKWARDS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68517-476">Hold Rows</span><span class="sxs-lookup"><span data-stu-id="68517-476">Hold Rows</span></span></p></td>
<td><p><span data-ttu-id="68517-477">DBPROP_CANHOLDROWS</span><span class="sxs-lookup"><span data-stu-id="68517-477">DBPROP_CANHOLDROWS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68517-478">IAccessor</span><span class="sxs-lookup"><span data-stu-id="68517-478">IAccessor</span></span></p></td>
<td><p><span data-ttu-id="68517-479">DBPROP_IAccessor</span><span class="sxs-lookup"><span data-stu-id="68517-479">DBPROP_IAccessor</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68517-480">IColumnsInfo</span><span class="sxs-lookup"><span data-stu-id="68517-480">IColumnsInfo</span></span></p></td>
<td><p><span data-ttu-id="68517-481">DBPROP_IColumnsInfo</span><span class="sxs-lookup"><span data-stu-id="68517-481">DBPROP_IColumnsInfo</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68517-482">IColumnsRowset</span><span class="sxs-lookup"><span data-stu-id="68517-482">IColumnsRowset</span></span></p></td>
<td><p><span data-ttu-id="68517-483">DBPROP_IColumnsRowset</span><span class="sxs-lookup"><span data-stu-id="68517-483">DBPROP_IColumnsRowset</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68517-484">IConnectionPointContainer</span><span class="sxs-lookup"><span data-stu-id="68517-484">IConnectionPointContainer</span></span></p></td>
<td><p><span data-ttu-id="68517-485">DBPROP_IConnectionPointContainer</span><span class="sxs-lookup"><span data-stu-id="68517-485">DBPROP_IConnectionPointContainer</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68517-486">IConvertType</span><span class="sxs-lookup"><span data-stu-id="68517-486">IConvertType</span></span></p></td>
<td><p><span data-ttu-id="68517-487">DBPROP_IConvertType</span><span class="sxs-lookup"><span data-stu-id="68517-487">DBPROP_IConvertType</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68517-488">Immobile Rows</span><span class="sxs-lookup"><span data-stu-id="68517-488">Immobile Rows</span></span></p></td>
<td><p><span data-ttu-id="68517-489">DBPROP_IMMOBILEROWS</span><span class="sxs-lookup"><span data-stu-id="68517-489">DBPROP_IMMOBILEROWS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68517-490">IRowset</span><span class="sxs-lookup"><span data-stu-id="68517-490">IRowset</span></span></p></td>
<td><p><span data-ttu-id="68517-491">DBPROP_IRowset</span><span class="sxs-lookup"><span data-stu-id="68517-491">DBPROP_IRowset</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68517-492">IRowsetChange</span><span class="sxs-lookup"><span data-stu-id="68517-492">IRowsetChange</span></span></p></td>
<td><p><span data-ttu-id="68517-493">DBPROP_IRowsetChange</span><span class="sxs-lookup"><span data-stu-id="68517-493">DBPROP_IRowsetChange</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68517-494">IRowsetIdentity</span><span class="sxs-lookup"><span data-stu-id="68517-494">IRowsetIdentity</span></span></p></td>
<td><p><span data-ttu-id="68517-495">DBPROP_IRowsetIdentity</span><span class="sxs-lookup"><span data-stu-id="68517-495">DBPROP_IRowsetIdentity</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68517-496">IRowsetInfo</span><span class="sxs-lookup"><span data-stu-id="68517-496">IRowsetInfo</span></span></p></td>
<td><p><span data-ttu-id="68517-497">DBPROP_IRowsetInfo</span><span class="sxs-lookup"><span data-stu-id="68517-497">DBPROP_IRowsetInfo</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68517-498">IRowsetLocate</span><span class="sxs-lookup"><span data-stu-id="68517-498">IRowsetLocate</span></span></p></td>
<td><p><span data-ttu-id="68517-499">DBPROP_IRowsetLocate</span><span class="sxs-lookup"><span data-stu-id="68517-499">DBPROP_IRowsetLocate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68517-500">IRowsetResynch</span><span class="sxs-lookup"><span data-stu-id="68517-500">IRowsetResynch</span></span></p></td>
<td><p><span data-ttu-id="68517-501">DBPROP_IRowsetResynch</span><span class="sxs-lookup"><span data-stu-id="68517-501">DBPROP_IRowsetResynch</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68517-502">IRowsetScroll</span><span class="sxs-lookup"><span data-stu-id="68517-502">IRowsetScroll</span></span></p></td>
<td><p><span data-ttu-id="68517-503">DBPROP_IRowsetScroll</span><span class="sxs-lookup"><span data-stu-id="68517-503">DBPROP_IRowsetScroll</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68517-504">IRowsetUpdate</span><span class="sxs-lookup"><span data-stu-id="68517-504">IRowsetUpdate</span></span></p></td>
<td><p><span data-ttu-id="68517-505">DBPROP_IRowsetUpdate</span><span class="sxs-lookup"><span data-stu-id="68517-505">DBPROP_IRowsetUpdate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68517-506">ISequentialStream</span><span class="sxs-lookup"><span data-stu-id="68517-506">ISequentialStream</span></span></p></td>
<td><p><span data-ttu-id="68517-507">DBPROP_ISequentialStream</span><span class="sxs-lookup"><span data-stu-id="68517-507">DBPROP_ISequentialStream</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68517-508">ISupportErrorInfo</span><span class="sxs-lookup"><span data-stu-id="68517-508">ISupportErrorInfo</span></span></p></td>
<td><p><span data-ttu-id="68517-509">DBPROP_ISupportErrorInfo</span><span class="sxs-lookup"><span data-stu-id="68517-509">DBPROP_ISupportErrorInfo</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68517-510">Literal Bookmarks</span><span class="sxs-lookup"><span data-stu-id="68517-510">Literal Bookmarks</span></span></p></td>
<td><p><span data-ttu-id="68517-511">DBPROP_LITERALBOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="68517-511">DBPROP_LITERALBOOKMARKS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68517-512">Literal Row Identity</span><span class="sxs-lookup"><span data-stu-id="68517-512">Literal Row Identity</span></span></p></td>
<td><p><span data-ttu-id="68517-513">DBPROP_LITERALIDENTITY</span><span class="sxs-lookup"><span data-stu-id="68517-513">DBPROP_LITERALIDENTITY</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68517-514">Lock Mode</span><span class="sxs-lookup"><span data-stu-id="68517-514">Lock Mode</span></span></p></td>
<td><p><span data-ttu-id="68517-515">DBPROP_LOCKMODE</span><span class="sxs-lookup"><span data-stu-id="68517-515">DBPROP_LOCKMODE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68517-516">Maximum Open Rows</span><span class="sxs-lookup"><span data-stu-id="68517-516">Maximum Open Rows</span></span></p></td>
<td><p><span data-ttu-id="68517-517">DBPROP_MAXOPENROWS</span><span class="sxs-lookup"><span data-stu-id="68517-517">DBPROP_MAXOPENROWS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68517-518">Maximum Pending Rows</span><span class="sxs-lookup"><span data-stu-id="68517-518">Maximum Pending Rows</span></span></p></td>
<td><p><span data-ttu-id="68517-519">DBPROP_MAXPENDINGROWS</span><span class="sxs-lookup"><span data-stu-id="68517-519">DBPROP_MAXPENDINGROWS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68517-520">Maximum Rows</span><span class="sxs-lookup"><span data-stu-id="68517-520">Maximum Rows</span></span></p></td>
<td><p><span data-ttu-id="68517-521">DBPROP_MAXROWS</span><span class="sxs-lookup"><span data-stu-id="68517-521">DBPROP_MAXROWS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68517-522">Notification Granularity</span><span class="sxs-lookup"><span data-stu-id="68517-522">Notification Granularity</span></span></p></td>
<td><p><span data-ttu-id="68517-523">DBPROP_NOTIFICATIONGRANULARITY</span><span class="sxs-lookup"><span data-stu-id="68517-523">DBPROP_NOTIFICATIONGRANULARITY</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68517-524">Notification Phases</span><span class="sxs-lookup"><span data-stu-id="68517-524">Notification Phases</span></span></p></td>
<td><p><span data-ttu-id="68517-525">DBPROP_NOTIFICATIONPHASES</span><span class="sxs-lookup"><span data-stu-id="68517-525">DBPROP_NOTIFICATIONPHASES</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68517-526">Objects Transacted</span><span class="sxs-lookup"><span data-stu-id="68517-526">Objects Transacted</span></span></p></td>
<td><p><span data-ttu-id="68517-527">DBPROP_TRANSACTEDOBJECT</span><span class="sxs-lookup"><span data-stu-id="68517-527">DBPROP_TRANSACTEDOBJECT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68517-528">Others' Changes Visible</span><span class="sxs-lookup"><span data-stu-id="68517-528">Others' Changes Visible</span></span></p></td>
<td><p><span data-ttu-id="68517-529">DBPROP_OTHERUPDATEDELETE</span><span class="sxs-lookup"><span data-stu-id="68517-529">DBPROP_OTHERUPDATEDELETE</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68517-530">Others' Inserts Visible</span><span class="sxs-lookup"><span data-stu-id="68517-530">Others' Inserts Visible</span></span></p></td>
<td><p><span data-ttu-id="68517-531">DBPROP_OTHERINSERT</span><span class="sxs-lookup"><span data-stu-id="68517-531">DBPROP_OTHERINSERT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68517-532">Output Encoding Property</span><span class="sxs-lookup"><span data-stu-id="68517-532">Output Encoding Property</span></span></p></td>
<td><p><span data-ttu-id="68517-533">DBPROP_OUTPUTENCODING</span><span class="sxs-lookup"><span data-stu-id="68517-533">DBPROP_OUTPUTENCODING</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68517-534">Output Stream Property</span><span class="sxs-lookup"><span data-stu-id="68517-534">Output Stream Property</span></span></p></td>
<td><p><span data-ttu-id="68517-535">DBPROP_OUTPUTSTREAM</span><span class="sxs-lookup"><span data-stu-id="68517-535">DBPROP_OUTPUTSTREAM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68517-536">Own Changes Visible</span><span class="sxs-lookup"><span data-stu-id="68517-536">Own Changes Visible</span></span></p></td>
<td><p><span data-ttu-id="68517-537">DBPROP_OWNUPDATEDELETE</span><span class="sxs-lookup"><span data-stu-id="68517-537">DBPROP_OWNUPDATEDELETE</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68517-538">Own Inserts Visible</span><span class="sxs-lookup"><span data-stu-id="68517-538">Own Inserts Visible</span></span></p></td>
<td><p><span data-ttu-id="68517-539">DBPROP_OWNINSERT</span><span class="sxs-lookup"><span data-stu-id="68517-539">DBPROP_OWNINSERT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68517-540">Preserve on Abort</span><span class="sxs-lookup"><span data-stu-id="68517-540">Preserve on Abort</span></span></p></td>
<td><p><span data-ttu-id="68517-541">DBPROP_ABORTPRESERVE</span><span class="sxs-lookup"><span data-stu-id="68517-541">DBPROP_ABORTPRESERVE</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68517-542">Preserve on Commit</span><span class="sxs-lookup"><span data-stu-id="68517-542">Preserve on Commit</span></span></p></td>
<td><p><span data-ttu-id="68517-543">DBPROP_COMMITPRESERVE</span><span class="sxs-lookup"><span data-stu-id="68517-543">DBPROP_COMMITPRESERVE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68517-544">Quick Restart</span><span class="sxs-lookup"><span data-stu-id="68517-544">Quick Restart</span></span></p></td>
<td><p><span data-ttu-id="68517-545">DBPROP_QUICKRESTART</span><span class="sxs-lookup"><span data-stu-id="68517-545">DBPROP_QUICKRESTART</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68517-546">Reentrant Events</span><span class="sxs-lookup"><span data-stu-id="68517-546">Reentrant Events</span></span></p></td>
<td><p><span data-ttu-id="68517-547">DBPROP_REENTRANTEVENTS</span><span class="sxs-lookup"><span data-stu-id="68517-547">DBPROP_REENTRANTEVENTS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68517-548">Remove Deleted Rows</span><span class="sxs-lookup"><span data-stu-id="68517-548">Remove Deleted Rows</span></span></p></td>
<td><p><span data-ttu-id="68517-549">DBPROP_REMOVEDELETED</span><span class="sxs-lookup"><span data-stu-id="68517-549">DBPROP_REMOVEDELETED</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68517-550">Report Multiple Changes</span><span class="sxs-lookup"><span data-stu-id="68517-550">Report Multiple Changes</span></span></p></td>
<td><p><span data-ttu-id="68517-551">DBPROP_REPORTMULTIPLECHANGES</span><span class="sxs-lookup"><span data-stu-id="68517-551">DBPROP_REPORTMULTIPLECHANGES</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68517-552">Return Pending Inserts</span><span class="sxs-lookup"><span data-stu-id="68517-552">Return Pending Inserts</span></span></p></td>
<td><p><span data-ttu-id="68517-553">DBPROP_RETURNPENDINGINSERTS</span><span class="sxs-lookup"><span data-stu-id="68517-553">DBPROP_RETURNPENDINGINSERTS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68517-554">Row Delete Notification</span><span class="sxs-lookup"><span data-stu-id="68517-554">Row Delete Notification</span></span></p></td>
<td><p><span data-ttu-id="68517-555">DBPROP_NOTIFYROWDELETE</span><span class="sxs-lookup"><span data-stu-id="68517-555">DBPROP_NOTIFYROWDELETE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68517-556">Row First Change Notification</span><span class="sxs-lookup"><span data-stu-id="68517-556">Row First Change Notification</span></span></p></td>
<td><p><span data-ttu-id="68517-557">DBPROP_NOTIFYROWFIRSTCHANGE</span><span class="sxs-lookup"><span data-stu-id="68517-557">DBPROP_NOTIFYROWFIRSTCHANGE</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68517-558">Row Insert Notification</span><span class="sxs-lookup"><span data-stu-id="68517-558">Row Insert Notification</span></span></p></td>
<td><p><span data-ttu-id="68517-559">DBPROP_NOTIFYROWINSERT</span><span class="sxs-lookup"><span data-stu-id="68517-559">DBPROP_NOTIFYROWINSERT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68517-560">Row Privileges</span><span class="sxs-lookup"><span data-stu-id="68517-560">Row Privileges</span></span></p></td>
<td><p><span data-ttu-id="68517-561">DBPROP_ROWRESTRICT</span><span class="sxs-lookup"><span data-stu-id="68517-561">DBPROP_ROWRESTRICT</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68517-562">Row Resynchronization Notification</span><span class="sxs-lookup"><span data-stu-id="68517-562">Row Resynchronization Notification</span></span></p></td>
<td><p><span data-ttu-id="68517-563">DBPROP_NOTIFYROWRESYNCH</span><span class="sxs-lookup"><span data-stu-id="68517-563">DBPROP_NOTIFYROWRESYNCH</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68517-564">Row Threading Model</span><span class="sxs-lookup"><span data-stu-id="68517-564">Row Threading Model</span></span></p></td>
<td><p><span data-ttu-id="68517-565">DBPROP_ROWTHREADMODEL</span><span class="sxs-lookup"><span data-stu-id="68517-565">DBPROP_ROWTHREADMODEL</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68517-566">Row Undo Change Notification</span><span class="sxs-lookup"><span data-stu-id="68517-566">Row Undo Change Notification</span></span></p></td>
<td><p><span data-ttu-id="68517-567">DBPROP_NOTIFYROWUNDOCHANGE</span><span class="sxs-lookup"><span data-stu-id="68517-567">DBPROP_NOTIFYROWUNDOCHANGE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68517-568">Row Undo Delete Notification</span><span class="sxs-lookup"><span data-stu-id="68517-568">Row Undo Delete Notification</span></span></p></td>
<td><p><span data-ttu-id="68517-569">DBPROP_NOTIFYROWUNDODELETE</span><span class="sxs-lookup"><span data-stu-id="68517-569">DBPROP_NOTIFYROWUNDODELETE</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68517-570">Row Undo Insert Notification</span><span class="sxs-lookup"><span data-stu-id="68517-570">Row Undo Insert Notification</span></span></p></td>
<td><p><span data-ttu-id="68517-571">DBPROP_NOTIFYROWUNDOINSERT</span><span class="sxs-lookup"><span data-stu-id="68517-571">DBPROP_NOTIFYROWUNDOINSERT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68517-572">Row Update Notification</span><span class="sxs-lookup"><span data-stu-id="68517-572">Row Update Notification</span></span></p></td>
<td><p><span data-ttu-id="68517-573">DBPROP_NOTIFYROWUPDATE</span><span class="sxs-lookup"><span data-stu-id="68517-573">DBPROP_NOTIFYROWUPDATE</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68517-574">Rowset Fetch Position Change Notification</span><span class="sxs-lookup"><span data-stu-id="68517-574">Rowset Fetch Position Change Notification</span></span></p></td>
<td><p><span data-ttu-id="68517-575">DBPROP_NOTIFYROWSETFETCHPOSITIONCHANGE</span><span class="sxs-lookup"><span data-stu-id="68517-575">DBPROP_NOTIFYROWSETFETCHPOSITIONCHANGE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68517-576">Rowset Release Notification</span><span class="sxs-lookup"><span data-stu-id="68517-576">Rowset Release Notification</span></span></p></td>
<td><p><span data-ttu-id="68517-577">DBPROP_NOTIFYROWSETRELEASE</span><span class="sxs-lookup"><span data-stu-id="68517-577">DBPROP_NOTIFYROWSETRELEASE</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68517-578">Scroll Backwards</span><span class="sxs-lookup"><span data-stu-id="68517-578">Scroll Backwards</span></span></p></td>
<td><p><span data-ttu-id="68517-579">DBPROP_CANSCROLLBACKWARDS</span><span class="sxs-lookup"><span data-stu-id="68517-579">DBPROP_CANSCROLLBACKWARDS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68517-580">Server Cursor</span><span class="sxs-lookup"><span data-stu-id="68517-580">Server Cursor</span></span></p></td>
<td><p><span data-ttu-id="68517-581">DBPROP_SERVERCURSOR</span><span class="sxs-lookup"><span data-stu-id="68517-581">DBPROP_SERVERCURSOR</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68517-582">Server Data on Insert</span><span class="sxs-lookup"><span data-stu-id="68517-582">Server Data on Insert</span></span></p></td>
<td><p><span data-ttu-id="68517-583">DBPROP_SERVERDATAONINSERT</span><span class="sxs-lookup"><span data-stu-id="68517-583">DBPROP_SERVERDATAONINSERT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68517-584">Skip Deleted Bookmarks</span><span class="sxs-lookup"><span data-stu-id="68517-584">Skip Deleted Bookmarks</span></span></p></td>
<td><p><span data-ttu-id="68517-585">DBPROP_BOOKMARKSKIP</span><span class="sxs-lookup"><span data-stu-id="68517-585">DBPROP_BOOKMARKSKIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68517-586">Strong Row Identity</span><span class="sxs-lookup"><span data-stu-id="68517-586">Strong Row Identity</span></span></p></td>
<td><p><span data-ttu-id="68517-587">DBPROP_STRONGIDENTITY</span><span class="sxs-lookup"><span data-stu-id="68517-587">DBPROP_STRONGIDENTITY</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68517-588">Updatability</span><span class="sxs-lookup"><span data-stu-id="68517-588">Updatability</span></span></p></td>
<td><p><span data-ttu-id="68517-589">DBPROP_UPDATABILITY</span><span class="sxs-lookup"><span data-stu-id="68517-589">DBPROP_UPDATABILITY</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68517-590">Use Bookmarks</span><span class="sxs-lookup"><span data-stu-id="68517-590">Use Bookmarks</span></span></p></td>
<td><p><span data-ttu-id="68517-591">DBPROP_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="68517-591">DBPROP_BOOKMARKS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68517-592">XML Root</span><span class="sxs-lookup"><span data-stu-id="68517-592">XML Root</span></span></p></td>
<td><p><span data-ttu-id="68517-593">SSPROP_STREAM_XMLROOT</span><span class="sxs-lookup"><span data-stu-id="68517-593">SSPROP_STREAM_XMLROOT</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68517-594">XSL</span><span class="sxs-lookup"><span data-stu-id="68517-594">XSL</span></span></p></td>
<td><p><span data-ttu-id="68517-595">SSPROP_STREAM_XSL</span><span class="sxs-lookup"><span data-stu-id="68517-595">SSPROP_STREAM_XSL</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="68517-596">有关具体的实现详细信息以及有关 Microsoft SQL Server OLE DB Provider 的功能信息，请参阅 MDAC SDK 的"OLE DB"一节中的"OLE DB Provider for SQL Server"文档。</span><span class="sxs-lookup"><span data-stu-id="68517-596">For specific implementation details and functional information about the Microsoft SQL Server OLE DB Provider, consult the OLE DB Provider for SQL Server documentation in the OLE DB section of the MDAC SDK.</span></span>

