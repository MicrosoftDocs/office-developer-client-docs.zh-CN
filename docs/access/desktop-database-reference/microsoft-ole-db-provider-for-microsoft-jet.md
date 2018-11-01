---
title: Microsoft OLE DB Provider for Microsoft Jet
TOCTitle: Microsoft OLE DB Provider for Microsoft Jet
ms:assetid: 4a210d72-8c90-aa7c-4621-1a555a30a2d2
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249228(v=office.15)
ms:contentKeyID: 48544660
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 39cb1288ef5e6be4f50d4ef976725122635db1dc
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25884084"
---
# <a name="microsoft-ole-db-provider-for-microsoft-jet"></a><span data-ttu-id="53d1c-102">Microsoft OLE DB Provider for Microsoft Jet</span><span class="sxs-lookup"><span data-stu-id="53d1c-102">Microsoft OLE DB Provider for Microsoft Jet</span></span>

<span data-ttu-id="53d1c-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="53d1c-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="53d1c-104">OLE DB Provider for Microsoft Jet 允许 ADO 访问 Microsoft Jet 数据库。</span><span class="sxs-lookup"><span data-stu-id="53d1c-104">The OLE DB Provider for Microsoft Jet allows ADO to access Microsoft Jet databases.</span></span>

## <a name="connection-string-parameters"></a><span data-ttu-id="53d1c-105">连接字符串参数</span><span class="sxs-lookup"><span data-stu-id="53d1c-105">Connection String Parameters</span></span>

<span data-ttu-id="53d1c-106">若要连接到此提供程序，请将 *ConnectionString* 属性的 [Provider](connectionstring-property-ado.md) 参数设置为：</span><span class="sxs-lookup"><span data-stu-id="53d1c-106">To connect to this provider, set the *Provider* argument of the [ConnectionString](connectionstring-property-ado.md) property to:</span></span>

```vb 
 
Microsoft.Jet.OLEDB.4.0 
```

<span data-ttu-id="53d1c-107">读取 [Provider](provider-property-ado.md) 属性时，也会返回此字符串。</span><span class="sxs-lookup"><span data-stu-id="53d1c-107">Reading the [Provider](provider-property-ado.md) property will return this string as well.</span></span>

## <a name="typical-connection-string"></a><span data-ttu-id="53d1c-108">典型的连接字符串</span><span class="sxs-lookup"><span data-stu-id="53d1c-108">Typical Connection String</span></span>

<span data-ttu-id="53d1c-109">此提供程序典型的连接字符串为：</span><span class="sxs-lookup"><span data-stu-id="53d1c-109">A typical connection string for this provider is:</span></span>

```vb 
 
"Provider=Microsoft.Jet.OLEDB.4.0;Data Source=databaseName;User ID=userName;Password=userPassword;" 
```

<span data-ttu-id="53d1c-110">该字符串由以下关键字组成：</span><span class="sxs-lookup"><span data-stu-id="53d1c-110">The string consists of these keywords:</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="53d1c-111">关键字</span><span class="sxs-lookup"><span data-stu-id="53d1c-111">Keyword</span></span></p></th>
<th><p><span data-ttu-id="53d1c-112">说明</span><span class="sxs-lookup"><span data-stu-id="53d1c-112">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="53d1c-113"><strong>Provider</strong></span><span class="sxs-lookup"><span data-stu-id="53d1c-113"><strong>Provider</strong></span></span></p></td>
<td><p><span data-ttu-id="53d1c-114">指定 OLE DB Provider for Microsoft Jet。</span><span class="sxs-lookup"><span data-stu-id="53d1c-114">Specifies the OLE DB Provider for Microsoft Jet.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53d1c-115"><strong>Data Source</strong></span><span class="sxs-lookup"><span data-stu-id="53d1c-115"><strong>Data Source</strong></span></span></p></td>
<td><p><span data-ttu-id="53d1c-116">指定数据库路径和文件名称 (例如，c:\Northwind.mdb)。</span><span class="sxs-lookup"><span data-stu-id="53d1c-116">Specifies the database path and file name (for example, c:\Northwind.mdb).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53d1c-117"><strong>User ID</strong></span><span class="sxs-lookup"><span data-stu-id="53d1c-117"><strong>User ID</strong></span></span></p></td>
<td><p><span data-ttu-id="53d1c-118">指定用户名。</span><span class="sxs-lookup"><span data-stu-id="53d1c-118">Specifies the user name.</span></span> <span data-ttu-id="53d1c-119">如果未指定此关键字，字符串&quot;管理&quot;，默认情况下使用。</span><span class="sxs-lookup"><span data-stu-id="53d1c-119">If this keyword is not specified, the string, &quot;admin&quot;, is used by default.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53d1c-120"><strong>Password</strong></span><span class="sxs-lookup"><span data-stu-id="53d1c-120"><strong>Password</strong></span></span></p></td>
<td><p><span data-ttu-id="53d1c-121">指定用户密码。</span><span class="sxs-lookup"><span data-stu-id="53d1c-121">Specifies the user password.</span></span> <span data-ttu-id="53d1c-122">如果未指定此关键字，则空字符串 (&quot;&quot;)，默认情况下使用。</span><span class="sxs-lookup"><span data-stu-id="53d1c-122">If this keyword is not specified, the empty string (&quot;&quot;), is used by default.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="provider-specific-connection-parameters"></a><span data-ttu-id="53d1c-123">提供程序特定的连接参数</span><span class="sxs-lookup"><span data-stu-id="53d1c-123">Provider-Specific Connection Parameters</span></span>

<span data-ttu-id="53d1c-p103">OLE DB Provider for Microsoft Jet 除了支持 ADO 定义的那些属性以外，还支持几个提供程序特定的动态属性。与所有其他的 **Connection** 参数一样，可以通过 **Connection** 对象的 **Properties** 集合或将其作为连接字符串的一部分来设置这些动态属性。</span><span class="sxs-lookup"><span data-stu-id="53d1c-p103">The OLE DB Provider for Microsoft Jet supports several provider-specific dynamic properties in addition to those defined by ADO. As with all other **Connection** parameters, they can be set via the **Connection** object's **Properties** collection or as part of the connection string.</span></span>

<span data-ttu-id="53d1c-126">下表列出了这些属性以及对应的 OLE DB 属性名（括在括号中）。</span><span class="sxs-lookup"><span data-stu-id="53d1c-126">The following table lists these properties with the corresponding OLE DB property name in parentheses.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="53d1c-127">参数</span><span class="sxs-lookup"><span data-stu-id="53d1c-127">Parameter</span></span></p></th>
<th><p><span data-ttu-id="53d1c-128">说明</span><span class="sxs-lookup"><span data-stu-id="53d1c-128">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="53d1c-129">Jet OLEDB:Compact 回收的空间量</span><span class="sxs-lookup"><span data-stu-id="53d1c-129">Jet OLEDB:Compact Reclaimed Space Amount</span></span><br />
<span data-ttu-id="53d1c-130">(DBPROP_JETOLEDB_COMPACTFREESPACESIZE)</span><span class="sxs-lookup"><span data-stu-id="53d1c-130">(DBPROP_JETOLEDB_COMPACTFREESPACESIZE)</span></span></p></td>
<td><p><span data-ttu-id="53d1c-p104">指示空间量的估计值（以字节为单位），可通过压缩数据库来回收空间。仅在建立了数据库连接后，此值才有效。</span><span class="sxs-lookup"><span data-stu-id="53d1c-p104">Indicates an estimate of the amount of space, in bytes, that can be reclaimed by compacting the database. This value is only valid after a database connection has been established.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53d1c-133">Jet OLEDB:Connection 控件</span><span class="sxs-lookup"><span data-stu-id="53d1c-133">Jet OLEDB:Connection Control</span></span><br />
<span data-ttu-id="53d1c-134">(DBPROP_JETOLEDB_CONNECTIONCONTROL)</span><span class="sxs-lookup"><span data-stu-id="53d1c-134">(DBPROP_JETOLEDB_CONNECTIONCONTROL)</span></span></p></td>
<td><p><span data-ttu-id="53d1c-135">指示用户是否可以连接到数据库。</span><span class="sxs-lookup"><span data-stu-id="53d1c-135">Indicates whether users can connect to the database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53d1c-136">Jet OLEDB： 创建系统数据库</span><span class="sxs-lookup"><span data-stu-id="53d1c-136">Jet OLEDB:Create System Database</span></span><br />
<span data-ttu-id="53d1c-137">(DBPROP_JETOLEDB_CREATESYSTEMDATABASE)</span><span class="sxs-lookup"><span data-stu-id="53d1c-137">(DBPROP_JETOLEDB_CREATESYSTEMDATABASE)</span></span></p></td>
<td><p><span data-ttu-id="53d1c-138">指示在创建新的数据源时是否应该创建系统数据库。</span><span class="sxs-lookup"><span data-stu-id="53d1c-138">Indicates whether a system database should be created when creating a new data source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53d1c-139">Jet OLEDB:Database 锁定模式</span><span class="sxs-lookup"><span data-stu-id="53d1c-139">Jet OLEDB:Database Locking Mode</span></span><br />
<span data-ttu-id="53d1c-140">(DBPROP_JETOLEDB_DATABASELOCKMODE)</span><span class="sxs-lookup"><span data-stu-id="53d1c-140">(DBPROP_JETOLEDB_DATABASELOCKMODE)</span></span></p></td>
<td><p><span data-ttu-id="53d1c-p105">指示此数据库的锁定模式。打开该数据库的第一个用户可以确定数据库打开时使用的模式。</span><span class="sxs-lookup"><span data-stu-id="53d1c-p105">Indicates the locking mode for this database. The first user to open the database determines the mode used while the database is open.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53d1c-143">Jet OLEDB:Database Password</span><span class="sxs-lookup"><span data-stu-id="53d1c-143">Jet OLEDB:Database Password</span></span><br />
<span data-ttu-id="53d1c-144">(DBPROP_JETOLEDB_DATABASEPASSWORD)</span><span class="sxs-lookup"><span data-stu-id="53d1c-144">(DBPROP_JETOLEDB_DATABASEPASSWORD)</span></span></p></td>
<td><p><span data-ttu-id="53d1c-145">指示数据库密码。</span><span class="sxs-lookup"><span data-stu-id="53d1c-145">Indicates the database password.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53d1c-146">Jet OLEDB:Don't Copy Locale on Compact</span><span class="sxs-lookup"><span data-stu-id="53d1c-146">Jet OLEDB:Don't Copy Locale on Compact</span></span><br />
<span data-ttu-id="53d1c-147">(DBPROP_JETOLEDB_COMPACT_DONTCOPYLOCALE)</span><span class="sxs-lookup"><span data-stu-id="53d1c-147">(DBPROP_JETOLEDB_COMPACT_DONTCOPYLOCALE)</span></span></p></td>
<td><p><span data-ttu-id="53d1c-148">指示压缩数据库时 Jet 是否应该复制区域设置信息。</span><span class="sxs-lookup"><span data-stu-id="53d1c-148">Indicates whether Jet should copy locale information when compacting a database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53d1c-149">Jet OLEDB:Encrypt Database</span><span class="sxs-lookup"><span data-stu-id="53d1c-149">Jet OLEDB:Encrypt Database</span></span><br />
<span data-ttu-id="53d1c-150">(DBPROP_JETOLEDB_ENCRYPTDATABASE)</span><span class="sxs-lookup"><span data-stu-id="53d1c-150">(DBPROP_JETOLEDB_ENCRYPTDATABASE)</span></span></p></td>
<td><p><span data-ttu-id="53d1c-p106">指示是否应对压缩的数据库进行加密。如果没有设置此属性，则在对原始数据库进行加密时也会对压缩的数据库加密。</span><span class="sxs-lookup"><span data-stu-id="53d1c-p106">Indicates whether a compacted database should be encrypted. If this property is not set, the compacted database will be encrypted if the original database was also encrypted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53d1c-153">Jet OLEDB:Engine Type</span><span class="sxs-lookup"><span data-stu-id="53d1c-153">Jet OLEDB:Engine Type</span></span><br />
<span data-ttu-id="53d1c-154">(DBPROP_JETOLEDB_ENGINE)</span><span class="sxs-lookup"><span data-stu-id="53d1c-154">(DBPROP_JETOLEDB_ENGINE)</span></span></p></td>
<td><p><span data-ttu-id="53d1c-155">指示用于访问当前数据存储区的存储引擎。</span><span class="sxs-lookup"><span data-stu-id="53d1c-155">Indicates the storage engine used to access the current data store.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53d1c-156">Jet OLEDB:Exclusive Async Delay</span><span class="sxs-lookup"><span data-stu-id="53d1c-156">Jet OLEDB:Exclusive Async Delay</span></span><br />
<span data-ttu-id="53d1c-157">(DBPROP_JETOLEDB_EXCLUSIVEASYNCDELAY)</span><span class="sxs-lookup"><span data-stu-id="53d1c-157">(DBPROP_JETOLEDB_EXCLUSIVEASYNCDELAY)</span></span></p></td>
<td><p><span data-ttu-id="53d1c-158">指示以独占方式打开数据库时，Jet 可延迟磁盘异步写入的最长时间（以毫秒为单位）。
</span><span class="sxs-lookup"><span data-stu-id="53d1c-158">Indicates the maximum length of time, in milliseconds, that Jet can delay asynchronous writes to disk when the database is opened exclusively.</span></span> <span data-ttu-id="53d1c-159">除非将 <strong>Jet OLEDB:Flush Transaction Timeout</strong> 设置为 0，否则将忽略此属性。</span><span class="sxs-lookup"><span data-stu-id="53d1c-159">This property is ignored unless <strong>Jet OLEDB:Flush Transaction Timeout</strong> is set to 0.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53d1c-160">Jet OLEDB:Flush Transaction Timeout</span><span class="sxs-lookup"><span data-stu-id="53d1c-160">Jet OLEDB:Flush Transaction Timeout</span></span><br />
<span data-ttu-id="53d1c-161">(DBPROP_JETOLEDB_FLUSHTRANSACTIONTIMEOUT)</span><span class="sxs-lookup"><span data-stu-id="53d1c-161">(DBPROP_JETOLEDB_FLUSHTRANSACTIONTIMEOUT)</span></span></p></td>
<td><p><span data-ttu-id="53d1c-p108">指示将存储在缓存中要异步写入的数据实际写入磁盘之前等待的时间。此设置将覆盖 <strong>Jet OLEDB:Shared Async Delay</strong> 和 <strong>Jet OLEDB:Exclusive Async Delay</strong> 的值。</span><span class="sxs-lookup"><span data-stu-id="53d1c-p108">Indicates the amount of time to wait before data stored in a cache for asynchronous writing is actually written to disk. This setting overrides the values for <strong>Jet OLEDB:Shared Async Delay</strong> and <strong>Jet OLEDB:Exclusive Async Delay</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53d1c-164">Jet OLEDB： 全局批量事务</span><span class="sxs-lookup"><span data-stu-id="53d1c-164">Jet OLEDB:Global Bulk Transactions</span></span><br />
<span data-ttu-id="53d1c-165">(DBPROP_JETOLEDB_GLOBALBULKNOTRANSACTIONS)</span><span class="sxs-lookup"><span data-stu-id="53d1c-165">(DBPROP_JETOLEDB_GLOBALBULKNOTRANSACTIONS)</span></span></p></td>
<td><p><span data-ttu-id="53d1c-166">指示是否要处理 SQL 批量事务处理。</span><span class="sxs-lookup"><span data-stu-id="53d1c-166">Indicates whether SQL bulk transactions are transacted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53d1c-167">Jet OLEDB： 全局部分批量操作</span><span class="sxs-lookup"><span data-stu-id="53d1c-167">Jet OLEDB:Global Partial Bulk Ops</span></span><br />
<span data-ttu-id="53d1c-168">(DBPROP_JETOLEDB_GLOBALBULKPARTIAL)</span><span class="sxs-lookup"><span data-stu-id="53d1c-168">(DBPROP_JETOLEDB_GLOBALBULKPARTIAL)</span></span></p></td>
<td><p><span data-ttu-id="53d1c-169">指示用于打开数据库的密码。</span><span class="sxs-lookup"><span data-stu-id="53d1c-169">Indicates the password used to open the database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53d1c-170">Jet OLEDB:Implicit Commit Sync</span><span class="sxs-lookup"><span data-stu-id="53d1c-170">Jet OLEDB:Implicit Commit Sync</span></span><br />
<span data-ttu-id="53d1c-171">(DBPROP_JETOLEDB_IMPLICITCOMMITSYNC)</span><span class="sxs-lookup"><span data-stu-id="53d1c-171">(DBPROP_JETOLEDB_IMPLICITCOMMITSYNC)</span></span></p></td>
<td><p><span data-ttu-id="53d1c-172">指示采用同步模式还是异步模式写入在内部隐式事务处理中所做的更改。</span><span class="sxs-lookup"><span data-stu-id="53d1c-172">Indicates whether changes made in internal implicit transactions are written in synchronous or asynchronous mode.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53d1c-173">Jet OLEDB:Lock Delay</span><span class="sxs-lookup"><span data-stu-id="53d1c-173">Jet OLEDB:Lock Delay</span></span><br />
<span data-ttu-id="53d1c-174">(DBPROP_JETOLEDB_LOCKDELAY)</span><span class="sxs-lookup"><span data-stu-id="53d1c-174">(DBPROP_JETOLEDB_LOCKDELAY)</span></span></p></td>
<td><p><span data-ttu-id="53d1c-175">指示在上一次尝试失败后与再次尝试获取锁定之前等待的毫秒数。</span><span class="sxs-lookup"><span data-stu-id="53d1c-175">Indicates the number of milliseconds to wait before attempting to acquire a lock after a previous attempt has failed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53d1c-176">Jet OLEDB:Lock Retry</span><span class="sxs-lookup"><span data-stu-id="53d1c-176">Jet OLEDB:Lock Retry</span></span><br />
<span data-ttu-id="53d1c-177">(DBPROP_JETOLEDB_LOCKRETRY)</span><span class="sxs-lookup"><span data-stu-id="53d1c-177">(DBPROP_JETOLEDB_LOCKRETRY)</span></span></p></td>
<td><p><span data-ttu-id="53d1c-178">指示重复尝试访问已锁定页面的次数。</span><span class="sxs-lookup"><span data-stu-id="53d1c-178">Indicates how many times an attempt to access a locked page is repeated.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53d1c-179">Jet OLEDB:Max Buffer Size</span><span class="sxs-lookup"><span data-stu-id="53d1c-179">Jet OLEDB:Max Buffer Size</span></span><br />
<span data-ttu-id="53d1c-180">(DBPROP_JETOLEDB_MAXBUFFERSIZE)</span><span class="sxs-lookup"><span data-stu-id="53d1c-180">(DBPROP_JETOLEDB_MAXBUFFERSIZE)</span></span></p></td>
<td><p><span data-ttu-id="53d1c-181">指示 Jet 在开始刷新对磁盘所做的更改之前可以使用的最大内存量 (KB)。</span><span class="sxs-lookup"><span data-stu-id="53d1c-181">Indicates the maximum amount of memory, in kilobytes, Jet can use before it starts flushing changes to disk.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53d1c-182">Jet OLEDB:Max Locks Per File</span><span class="sxs-lookup"><span data-stu-id="53d1c-182">Jet OLEDB:Max Locks Per File</span></span><br />
<span data-ttu-id="53d1c-183">(DBPROP_JETOLEDB_MAXLOCKSPERFILE)</span><span class="sxs-lookup"><span data-stu-id="53d1c-183">(DBPROP_JETOLEDB_MAXLOCKSPERFILE)</span></span></p></td>
<td><p><span data-ttu-id="53d1c-p109">指示 Jet 可在数据库上放置的最大锁定数目。默认值为 9500。</span><span class="sxs-lookup"><span data-stu-id="53d1c-p109">Indicates the maximum number of locks Jet can place on a database. The default value is 9500.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53d1c-186">Jet OLEDB： 新数据库密码</span><span class="sxs-lookup"><span data-stu-id="53d1c-186">Jet OLEDB:New Database Password</span></span><br />
<span data-ttu-id="53d1c-187">(DBPROP_JETOLEDB_NEWDATABASEPASSWORD)</span><span class="sxs-lookup"><span data-stu-id="53d1c-187">(DBPROP_JETOLEDB_NEWDATABASEPASSWORD)</span></span></p></td>
<td><p><span data-ttu-id="53d1c-p110">指示要为此数据库设置的新密码。旧密码存储在 <strong>Jet OLEDB:Database Password</strong> 中。</span><span class="sxs-lookup"><span data-stu-id="53d1c-p110">Indicates the new password to be set for this database. The old password is stored in <strong>Jet OLEDB:Database Password</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53d1c-190">Jet OLEDB:ODBC Command Time Out</span><span class="sxs-lookup"><span data-stu-id="53d1c-190">Jet OLEDB:ODBC Command Time Out</span></span><br />
<span data-ttu-id="53d1c-191">(DBPROP_JETOLEDB_ODBCCOMMANDTIMEOUT)</span><span class="sxs-lookup"><span data-stu-id="53d1c-191">(DBPROP_JETOLEDB_ODBCCOMMANDTIMEOUT)</span></span></p></td>
<td><p><span data-ttu-id="53d1c-192">指示 Jet 中的远程 ODBC 查询超时之前的毫秒数。</span><span class="sxs-lookup"><span data-stu-id="53d1c-192">Indicates the number of milliseconds before a remote ODBC query from Jet will timeout.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53d1c-193">为表锁定 jet OLEDB:Page 锁定</span><span class="sxs-lookup"><span data-stu-id="53d1c-193">Jet OLEDB:Page Locks to Table Lock</span></span><br />
<span data-ttu-id="53d1c-194">(DBPROP_JETOLEDB_PAGELOCKSTOTABLELOCK)</span><span class="sxs-lookup"><span data-stu-id="53d1c-194">(DBPROP_JETOLEDB_PAGELOCKSTOTABLELOCK)</span></span></p></td>
<td><p><span data-ttu-id="53d1c-p111">指示 Jet 尝试将锁定提升到表锁定之前，在事务处理中需要锁定的页数。如果此值为 0，则永远不会提升锁定。</span><span class="sxs-lookup"><span data-stu-id="53d1c-p111">Indicates how many pages need to be locked within a transaction before Jet attempts to promote the lock to a table lock. If this value is 0, then the lock is never promoted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53d1c-197">Jet OLEDB:Page Timeout</span><span class="sxs-lookup"><span data-stu-id="53d1c-197">Jet OLEDB:Page Timeout</span></span><br />
<span data-ttu-id="53d1c-198">(DBPROP_JETOLEDB_PAGETIMEOUT)</span><span class="sxs-lookup"><span data-stu-id="53d1c-198">(DBPROP_JETOLEDB_PAGETIMEOUT)</span></span></p></td>
<td><p><span data-ttu-id="53d1c-199">指示 Jet 在查看其数据文件的缓存是否过期之前等待的毫秒数。</span><span class="sxs-lookup"><span data-stu-id="53d1c-199">Indicates the number of milliseconds Jet will wait before checking to see if its cache is out of date with the database file.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53d1c-200">Jet OLEDB:Recycle Long-Valued Pages</span><span class="sxs-lookup"><span data-stu-id="53d1c-200">Jet OLEDB:Recycle Long-Valued Pages</span></span><br />
<span data-ttu-id="53d1c-201">(DBPROP_JETOLEDB_RECYCLELONGVALUEPAGES)</span><span class="sxs-lookup"><span data-stu-id="53d1c-201">(DBPROP_JETOLEDB_RECYCLELONGVALUEPAGES)</span></span></p></td>
<td><p><span data-ttu-id="53d1c-202">指示释放 BLOB 页后 Jet 是否应该主动尝试回收这些 BLOB 页。</span><span class="sxs-lookup"><span data-stu-id="53d1c-202">Indicates whether Jet should aggressively try to reclaim BLOB pages when they are freed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53d1c-203">Jet OLEDB:Registry Path</span><span class="sxs-lookup"><span data-stu-id="53d1c-203">Jet OLEDB:Registry Path</span></span><br />
<span data-ttu-id="53d1c-204">(DBPROP_JETOLEDB_REGPATH)</span><span class="sxs-lookup"><span data-stu-id="53d1c-204">(DBPROP_JETOLEDB_REGPATH)</span></span></p></td>
<td><p><span data-ttu-id="53d1c-205">指示包含 Jet 数据库引擎的值的 Windows 注册表项。</span><span class="sxs-lookup"><span data-stu-id="53d1c-205">Indicates the Windows registry key that contains values for the Jet database engine.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53d1c-206">Jet OLEDB:Reset ISAM Stats</span><span class="sxs-lookup"><span data-stu-id="53d1c-206">Jet OLEDB:Reset ISAM Stats</span></span><br />
<span data-ttu-id="53d1c-207">(DBPROP_JETOLEDB_RESETISAMSTATS)</span><span class="sxs-lookup"><span data-stu-id="53d1c-207">(DBPROP_JETOLEDB_RESETISAMSTATS)</span></span></p></td>
<td><p><span data-ttu-id="53d1c-208">指示返回性能信息后，架构 <strong>Recordset</strong> DBSCHEMA_JETOLEDB_ISAMSTATS 是否应该重新设置其性能计数器。</span><span class="sxs-lookup"><span data-stu-id="53d1c-208">Indicates whether the schema <strong>Recordset</strong> DBSCHEMA_JETOLEDB_ISAMSTATS should reset its performance counters after returning performance information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53d1c-209">Jet OLEDB:Shared Async Delay</span><span class="sxs-lookup"><span data-stu-id="53d1c-209">Jet OLEDB:Shared Async Delay</span></span><br />
<span data-ttu-id="53d1c-210">(DBPROP_JETOLEDB_SHAREDASYNCDELAY)</span><span class="sxs-lookup"><span data-stu-id="53d1c-210">(DBPROP_JETOLEDB_SHAREDASYNCDELAY)</span></span></p></td>
<td><p><span data-ttu-id="53d1c-211">指示以多用户模式打开数据库时，Jet 可以延迟异步磁盘写入的最长时间（以毫秒为单位）。</span><span class="sxs-lookup"><span data-stu-id="53d1c-211">Indicates the maximum amount of time, in milliseconds, Jet can delay asynchronous writes to disk when the database is opened in multi-user mode.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53d1c-212">Jet OLEDB:System Database</span><span class="sxs-lookup"><span data-stu-id="53d1c-212">Jet OLEDB:System Database</span></span><br />
<span data-ttu-id="53d1c-213">(DBPROP_JETOLEDB_SYSDBPATH)</span><span class="sxs-lookup"><span data-stu-id="53d1c-213">(DBPROP_JETOLEDB_SYSDBPATH)</span></span></p></td>
<td><p><span data-ttu-id="53d1c-214">指示工作组信息文件（系统数据库）的路径和文件名。</span><span class="sxs-lookup"><span data-stu-id="53d1c-214">Indicates the path and file name for the workgroup information file (system database).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53d1c-215">Jet OLEDB:Transaction 提交模式</span><span class="sxs-lookup"><span data-stu-id="53d1c-215">Jet OLEDB:Transaction Commit Mode</span></span><br />
<span data-ttu-id="53d1c-216">(DBPROP_JETOLEDB_TXNCOMMITMODE)</span><span class="sxs-lookup"><span data-stu-id="53d1c-216">(DBPROP_JETOLEDB_TXNCOMMITMODE)</span></span></p></td>
<td><p><span data-ttu-id="53d1c-217">指示提交事务处理时 Jet 采用同步方式还是异步方式将数据写入磁盘。</span><span class="sxs-lookup"><span data-stu-id="53d1c-217">Indicates whether Jet writes data to disk synchronously or asynchronously when a transaction is committed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53d1c-218">Jet OLEDB:User Commit Sync</span><span class="sxs-lookup"><span data-stu-id="53d1c-218">Jet OLEDB:User Commit Sync</span></span><br />
<span data-ttu-id="53d1c-219">(DBPROP_JETOLEDB_USERCOMMITSYNC)</span><span class="sxs-lookup"><span data-stu-id="53d1c-219">(DBPROP_JETOLEDB_USERCOMMITSYNC)</span></span></p></td>
<td><p><span data-ttu-id="53d1c-220">指示采用同步模式还是异步模式写入在事务处理中所做的更改。</span><span class="sxs-lookup"><span data-stu-id="53d1c-220">Indicates whether changes made in transactions are written in synchronous or asynchronous mode.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="provider-specific-recordset-and-command-properties"></a><span data-ttu-id="53d1c-221">提供程序特定的 Recordset 和 Command 属性</span><span class="sxs-lookup"><span data-stu-id="53d1c-221">Provider-Specific Recordset and Command Properties</span></span>

<span data-ttu-id="53d1c-p112">Jet 提供程序还支持多个提供程序特定的 **Recordset** 和 **Command** 属性。这些属性可通过 **Recordset** 或 **Command** 对象的 **Properties** 集合进行访问和设置。该表列出了 ADO 属性名及其对应的 OLE DB 属性名（括在括号中）。</span><span class="sxs-lookup"><span data-stu-id="53d1c-p112">The Jet provider also supports several provider-specific **Recordset** and **Command** properties. These properties are accessed and set through the **Properties** collection of the **Recordset** or **Command** object. The table lists the ADO property name and its corresponding OLE DB property name in parentheses.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="53d1c-225">属性名称</span><span class="sxs-lookup"><span data-stu-id="53d1c-225">Property Name</span></span></p></th>
<th><p><span data-ttu-id="53d1c-226">说明</span><span class="sxs-lookup"><span data-stu-id="53d1c-226">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="53d1c-227">Jet OLEDB:Bulk 事务</span><span class="sxs-lookup"><span data-stu-id="53d1c-227">Jet OLEDB:Bulk Transactions</span></span><br />
<span data-ttu-id="53d1c-228">(DBPROP_JETOLEDB_BULKNOTRANSACTIONS)</span><span class="sxs-lookup"><span data-stu-id="53d1c-228">(DBPROP_JETOLEDB_BULKNOTRANSACTIONS)</span></span></p></td>
<td><p><span data-ttu-id="53d1c-p113">指示是否处理 SQL 批量操作。处理时，由于资源延迟，大量的批量操作可能会失败。</span><span class="sxs-lookup"><span data-stu-id="53d1c-p113">Indicates whether SQL bulk operations are transacted. Large bulk operations might fail when transacted, due to resource delays.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53d1c-231">Jet OLEDB:Enable Fat 游标</span><span class="sxs-lookup"><span data-stu-id="53d1c-231">Jet OLEDB:Enable Fat Cursors</span></span><br />
<span data-ttu-id="53d1c-232">(DBPROP_JETOLEDB_ENABLEFATCURSOR)</span><span class="sxs-lookup"><span data-stu-id="53d1c-232">(DBPROP_JETOLEDB_ENABLEFATCURSOR)</span></span></p></td>
<td><p><span data-ttu-id="53d1c-233">指示为远程行源填充记录集时，Jet 是否应该缓存多个行。</span><span class="sxs-lookup"><span data-stu-id="53d1c-233">Indicates whether Jet should cache multiple rows when populating a recordset for remote row sources.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53d1c-234">Jet OLEDB:Fat 光标缓存大小</span><span class="sxs-lookup"><span data-stu-id="53d1c-234">Jet OLEDB:Fat Cursor Cache Size</span></span><br />
<span data-ttu-id="53d1c-235">(DBPROP_JETOLEDB_FATCURSORMAXROWS)</span><span class="sxs-lookup"><span data-stu-id="53d1c-235">(DBPROP_JETOLEDB_FATCURSORMAXROWS)</span></span></p></td>
<td><p><span data-ttu-id="53d1c-p114">指示使用远程数据存储区行缓存时要缓存的行数。除非 <strong>Jet OLEDB:Enable Fat Cursors</strong> 为 True，否则将忽略此值。</span><span class="sxs-lookup"><span data-stu-id="53d1c-p114">Indicates the number of rows to cache when using remote data store row caching. This value is ignored unless <strong>Jet OLEDB:Enable Fat Cursors</strong> is True.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53d1c-238">Jet OLEDB： 不一致</span><span class="sxs-lookup"><span data-stu-id="53d1c-238">Jet OLEDB:Inconsistent</span></span><br />
<span data-ttu-id="53d1c-239">(DBPROP_JETOLEDB_INCONSISTENT)</span><span class="sxs-lookup"><span data-stu-id="53d1c-239">(DBPROP_JETOLEDB_INCONSISTENT)</span></span></p></td>
<td><p><span data-ttu-id="53d1c-240">指示查询结果是否允许不一致的更新。</span><span class="sxs-lookup"><span data-stu-id="53d1c-240">Indicates whether query results allow inconsistent updates.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53d1c-241">Jet OLEDB： 锁定粒度</span><span class="sxs-lookup"><span data-stu-id="53d1c-241">Jet OLEDB:Locking Granularity</span></span><br />
<span data-ttu-id="53d1c-242">(DBPROP_JETOLEDB_LOCKGRANULARITY)</span><span class="sxs-lookup"><span data-stu-id="53d1c-242">(DBPROP_JETOLEDB_LOCKGRANULARITY)</span></span></p></td>
<td><p><span data-ttu-id="53d1c-243">指示是否使用行级锁定打开表。</span><span class="sxs-lookup"><span data-stu-id="53d1c-243">Indicates whether a table is opened using row-level locking.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53d1c-244">Jet OLEDB:ODBC 传递语句</span><span class="sxs-lookup"><span data-stu-id="53d1c-244">Jet OLEDB:ODBC Pass-Through Statement</span></span><br />
<span data-ttu-id="53d1c-245">(DBPROP_JETOLEDB_ODBCPASSTHROUGH)</span><span class="sxs-lookup"><span data-stu-id="53d1c-245">(DBPROP_JETOLEDB_ODBCPASSTHROUGH)</span></span></p></td>
<td><p><span data-ttu-id="53d1c-246">指示 Jet 是否应该将 <strong>Command</strong> 对象中的 SQL 文本原封不动地传递到后端。</span><span class="sxs-lookup"><span data-stu-id="53d1c-246">Indicates that Jet should pass the SQL text in a <strong>Command</strong> object to the back end unaltered.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53d1c-247">Jet OLEDB:Partial 批量操作</span><span class="sxs-lookup"><span data-stu-id="53d1c-247">Jet OLEDB:Partial Bulk Ops</span></span><br />
<span data-ttu-id="53d1c-248">(DBPROP_JETOLEDB_BULKPARTIAL)</span><span class="sxs-lookup"><span data-stu-id="53d1c-248">(DBPROP_JETOLEDB_BULKPARTIAL)</span></span></p></td>
<td><p><span data-ttu-id="53d1c-249">指示 SQL DML 操作失败时 Jet 的行为。</span><span class="sxs-lookup"><span data-stu-id="53d1c-249">Indicates Jet's behavior when SQL DML operations fail.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53d1c-250">通过查询批量桌面 jet OLEDB:Pass</span><span class="sxs-lookup"><span data-stu-id="53d1c-250">Jet OLEDB:Pass Through Query Bulk-Op</span></span><br />
<span data-ttu-id="53d1c-251">(DBPROP_JETOLEDB_PASSTHROUGHBULKOP)</span><span class="sxs-lookup"><span data-stu-id="53d1c-251">(DBPROP_JETOLEDB_PASSTHROUGHBULKOP)</span></span></p></td>
<td><p><span data-ttu-id="53d1c-252">指示是否将不返回 <strong>Recordset</strong> 的查询原封不动地传递到数据源。</span><span class="sxs-lookup"><span data-stu-id="53d1c-252">Indicates whether queries that do not return a <strong>Recordset</strong> are passed unaltered to the data source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53d1c-253">通过查询 jet OLEDB:Pass 连接字符串</span><span class="sxs-lookup"><span data-stu-id="53d1c-253">Jet OLEDB:Pass Through Query Connect String</span></span><br />
<span data-ttu-id="53d1c-254">(DBPROP_JETOLEDB_ODBCPASSTHROUGHCONNECTSTRING)</span><span class="sxs-lookup"><span data-stu-id="53d1c-254">(DBPROP_JETOLEDB_ODBCPASSTHROUGHCONNECTSTRING)</span></span></p></td>
<td><p><span data-ttu-id="53d1c-p115">指示用于连接到远程数据存储区的 Jet 连接字符串。除非 <strong>Jet OLEDB:ODBC Pass-Through Statement</strong> 为 True，否则将忽略此值。</span><span class="sxs-lookup"><span data-stu-id="53d1c-p115">Indicates the Jet connect string used to connect to a remote data store. This value is ignored unless <strong>Jet OLEDB:ODBC Pass-Through Statement</strong> is True.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53d1c-257">Jet OLEDB： 存储查询</span><span class="sxs-lookup"><span data-stu-id="53d1c-257">Jet OLEDB:Stored Query</span></span><br />
<span data-ttu-id="53d1c-258">(DBPROP_JETOLEDB_STOREDQUERY)</span><span class="sxs-lookup"><span data-stu-id="53d1c-258">(DBPROP_JETOLEDB_STOREDQUERY)</span></span></p></td>
<td><p><span data-ttu-id="53d1c-259">指示是否应将命令文本解释为存储查询，而不是解释为 SQL 命令。</span><span class="sxs-lookup"><span data-stu-id="53d1c-259">Indicates whether the command text should be interpreted as a stored query instead of an SQL command.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53d1c-260">Jet OLEDB： 验证规则集</span><span class="sxs-lookup"><span data-stu-id="53d1c-260">Jet OLEDB:Validate Rules On Set</span></span><br />
<span data-ttu-id="53d1c-261">(DBPROP_JETOLEDB_VALIDATEONSET)</span><span class="sxs-lookup"><span data-stu-id="53d1c-261">(DBPROP_JETOLEDB_VALIDATEONSET)</span></span></p></td>
<td><p><span data-ttu-id="53d1c-262">指示在设置列数据或将更改提交到数据库时，是否应该评估 Jet 验证规则。</span><span class="sxs-lookup"><span data-stu-id="53d1c-262">Indicates whether the Jet validation rules are evaluated when column data is set or when the changes are committed to the database.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="53d1c-p116">默认情况下，OLE DB Provider for Microsoft Jet 在可读/写模式下打开 Microsoft Jet 数据库。若要在只读模式下打开数据库，请将 ADO [Connection](mode-property-ado.md) 对象上的 **Mode** 属性设置为 **adModeRead** 。</span><span class="sxs-lookup"><span data-stu-id="53d1c-p116">By default, the OLE DB Provider for Microsoft Jet opens Microsoft Jet databases in read/write mode. To open a database in read-only mode, set the [Mode](mode-property-ado.md) property on the ADO **Connection** object to **adModeRead**.</span></span>

## <a name="command-object-usage"></a><span data-ttu-id="53d1c-265">Command 对象用法</span><span class="sxs-lookup"><span data-stu-id="53d1c-265">Command Object Usage</span></span>

<span data-ttu-id="53d1c-p117">[Command](command-object-ado.md) 对象中的命令文本使用 Microsoft Jet SQL 语句。您可以在命令文本中指定行返回查询、操作查询和表名称；但是，存储过程不受支持，因而不应指定。</span><span class="sxs-lookup"><span data-stu-id="53d1c-p117">Command text in the [Command](command-object-ado.md) object uses the Microsoft Jet SQL dialect. You can specify row-returning queries, action queries, and table names in the command text; however, stored procedures are not supported and should not be specified.</span></span>

## <a name="recordset-behavior"></a><span data-ttu-id="53d1c-268">Recordset 行为</span><span class="sxs-lookup"><span data-stu-id="53d1c-268">Recordset Behavior</span></span>

<span data-ttu-id="53d1c-p118">Microsoft Jet 数据库引擎不支持动态游标。因此，OLE DB Provider for Microsoft Jet 也不支持 **adLockDynamic** 游标类型。请求动态游标时，该提供程序将返回键集游标并重新设置 [CursorType](cursortype-property-ado.md) 属性，以指示返回的 [Recordset](recordset-object-ado.md) 的类型。而且，如果请求可更新的 **Recordset**（**LockType** 是 **adLockOptimistic**、**adLockBatchOptimistic** 或 **adLockPessimistic**），则该提供程序也会返回一个键集游标并重新设置 **CursorType** 属性。</span><span class="sxs-lookup"><span data-stu-id="53d1c-p118">The Microsoft Jet database engine does not support dynamic cursors. Therefore, the OLE DB Provider for Microsoft Jet does not support the **adLockDynamic** cursor type. When a dynamic cursor is requested, the provider will return a keyset cursor and reset the [CursorType](cursortype-property-ado.md) property to indicate the type of [Recordset](recordset-object-ado.md) returned. Further, if an updatable **Recordset** is requested (**LockType** is **adLockOptimistic**, **adLockBatchOptimistic**, or **adLockPessimistic**) the provider will also return a keyset cursor and reset the **CursorType** property.</span></span>

## <a name="dynamic-properties"></a><span data-ttu-id="53d1c-273">动态属性</span><span class="sxs-lookup"><span data-stu-id="53d1c-273">Dynamic Properties</span></span>

<span data-ttu-id="53d1c-274">OLE DB Provider for Microsoft Jet 可以将多个动态属性插入到未打开的 **Connection**、[Recordset](connection-object-ado.md) 和 [Command](recordset-object-ado.md) 对象的 [Properties](command-object-ado.md) 集合中。</span><span class="sxs-lookup"><span data-stu-id="53d1c-274">The OLE DB Provider for Microsoft Jet inserts several dynamic properties into the **Properties** collection of the unopened [Connection](connection-object-ado.md), [Recordset](recordset-object-ado.md), and [Command](command-object-ado.md) objects.</span></span>

<span data-ttu-id="53d1c-p119">下面的表是每个动态属性的 ADO 和 OLE DB 名称的交叉索引。《OLE DB 程序员参考》使用术语"说明"来引用 ADO 属性名。您可以在《OLE DB 程序员参考》中找到有关这些属性的详细信息。请在"索引"中搜索 OLE DB 属性名，或者请参阅"附录 C：OLE DB 属性"。</span><span class="sxs-lookup"><span data-stu-id="53d1c-p119">The tables below are a cross-index of the ADO and OLE DB names for each dynamic property. The OLE DB Programmer's Reference refers to an ADO property name by the term, "Description." You can find more information about these properties in the OLE DB Programmer's Reference. Search for the OLE DB property name in the Index or see Appendix C: OLE DB Properties.</span></span>

## <a name="connection-dynamic-properties"></a><span data-ttu-id="53d1c-279">Connection 动态属性</span><span class="sxs-lookup"><span data-stu-id="53d1c-279">Connection Dynamic Properties</span></span>

<span data-ttu-id="53d1c-280">以下属性将被添加到 **Connection** 对象的 **Properties** 集合中。</span><span class="sxs-lookup"><span data-stu-id="53d1c-280">The following properties are added to the **Connection** object's **Properties** collection.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="53d1c-281">ADO 属性名</span><span class="sxs-lookup"><span data-stu-id="53d1c-281">ADO Property Name</span></span></p></th>
<th><p><span data-ttu-id="53d1c-282">OLE DB 属性名</span><span class="sxs-lookup"><span data-stu-id="53d1c-282">OLE DB Property Name</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="53d1c-283">Active Sessions</span><span class="sxs-lookup"><span data-stu-id="53d1c-283">Active Sessions</span></span></p></td>
<td><p><span data-ttu-id="53d1c-284">DBPROP_ACTIVESESSIONS</span><span class="sxs-lookup"><span data-stu-id="53d1c-284">DBPROP_ACTIVESESSIONS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53d1c-285">Asynchable Abort</span><span class="sxs-lookup"><span data-stu-id="53d1c-285">Asynchable Abort</span></span></p></td>
<td><p><span data-ttu-id="53d1c-286">DBPROP_ASYNCTXNABORT</span><span class="sxs-lookup"><span data-stu-id="53d1c-286">DBPROP_ASYNCTXNABORT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53d1c-287">Asynchable Commit</span><span class="sxs-lookup"><span data-stu-id="53d1c-287">Asynchable Commit</span></span></p></td>
<td><p><span data-ttu-id="53d1c-288">DBPROP_ASYNCTNXCOMMIT</span><span class="sxs-lookup"><span data-stu-id="53d1c-288">DBPROP_ASYNCTNXCOMMIT</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53d1c-289">Autocommit Isolation Levels</span><span class="sxs-lookup"><span data-stu-id="53d1c-289">Autocommit Isolation Levels</span></span></p></td>
<td><p><span data-ttu-id="53d1c-290">DBPROP_SESS_AUTOCOMMITISOLEVELS</span><span class="sxs-lookup"><span data-stu-id="53d1c-290">DBPROP_SESS_AUTOCOMMITISOLEVELS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53d1c-291">Catalog Location</span><span class="sxs-lookup"><span data-stu-id="53d1c-291">Catalog Location</span></span></p></td>
<td><p><span data-ttu-id="53d1c-292">DBPROP_CATALOGLOCATION</span><span class="sxs-lookup"><span data-stu-id="53d1c-292">DBPROP_CATALOGLOCATION</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53d1c-293">Catalog Term</span><span class="sxs-lookup"><span data-stu-id="53d1c-293">Catalog Term</span></span></p></td>
<td><p><span data-ttu-id="53d1c-294">DBPROP_CATALOGTERM</span><span class="sxs-lookup"><span data-stu-id="53d1c-294">DBPROP_CATALOGTERM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53d1c-295">Column Definition</span><span class="sxs-lookup"><span data-stu-id="53d1c-295">Column Definition</span></span></p></td>
<td><p><span data-ttu-id="53d1c-296">DBPROP_COLUMNDEFINITION</span><span class="sxs-lookup"><span data-stu-id="53d1c-296">DBPROP_COLUMNDEFINITION</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53d1c-297">Current Catalog</span><span class="sxs-lookup"><span data-stu-id="53d1c-297">Current Catalog</span></span></p></td>
<td><p><span data-ttu-id="53d1c-298">DBPROP_CURRENTCATALOG</span><span class="sxs-lookup"><span data-stu-id="53d1c-298">DBPROP_CURRENTCATALOG</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53d1c-299">Data Source</span><span class="sxs-lookup"><span data-stu-id="53d1c-299">Data Source</span></span></p></td>
<td><p><span data-ttu-id="53d1c-300">DBPROP_INIT_DATASOURCE</span><span class="sxs-lookup"><span data-stu-id="53d1c-300">DBPROP_INIT_DATASOURCE</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53d1c-301">Data Source Name</span><span class="sxs-lookup"><span data-stu-id="53d1c-301">Data Source Name</span></span></p></td>
<td><p><span data-ttu-id="53d1c-302">DBPROP_DATASOURCENAME</span><span class="sxs-lookup"><span data-stu-id="53d1c-302">DBPROP_DATASOURCENAME</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53d1c-303">Data Source Object Threading Model</span><span class="sxs-lookup"><span data-stu-id="53d1c-303">Data Source Object Threading Model</span></span></p></td>
<td><p><span data-ttu-id="53d1c-304">DBPROP_DSOTHREADMODEL</span><span class="sxs-lookup"><span data-stu-id="53d1c-304">DBPROP_DSOTHREADMODEL</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53d1c-305">DBMS Name</span><span class="sxs-lookup"><span data-stu-id="53d1c-305">DBMS Name</span></span></p></td>
<td><p><span data-ttu-id="53d1c-306">DBPROP_DBMSNAME</span><span class="sxs-lookup"><span data-stu-id="53d1c-306">DBPROP_DBMSNAME</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53d1c-307">DBMS Version</span><span class="sxs-lookup"><span data-stu-id="53d1c-307">DBMS Version</span></span></p></td>
<td><p><span data-ttu-id="53d1c-308">DBPROP_DBMSVER</span><span class="sxs-lookup"><span data-stu-id="53d1c-308">DBPROP_DBMSVER</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53d1c-309">GROUP BY Support</span><span class="sxs-lookup"><span data-stu-id="53d1c-309">GROUP BY Support</span></span></p></td>
<td><p><span data-ttu-id="53d1c-310">DBPROP_GROUPBY</span><span class="sxs-lookup"><span data-stu-id="53d1c-310">DBPROP_GROUPBY</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53d1c-311">Heterogeneous Table Support</span><span class="sxs-lookup"><span data-stu-id="53d1c-311">Heterogeneous Table Support</span></span></p></td>
<td><p><span data-ttu-id="53d1c-312">DBPROP_HETEROGENEOUSTABLES</span><span class="sxs-lookup"><span data-stu-id="53d1c-312">DBPROP_HETEROGENEOUSTABLES</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53d1c-313">Identifier Case Sensitivity</span><span class="sxs-lookup"><span data-stu-id="53d1c-313">Identifier Case Sensitivity</span></span></p></td>
<td><p><span data-ttu-id="53d1c-314">DBPROP_IDENTIFIERCASE</span><span class="sxs-lookup"><span data-stu-id="53d1c-314">DBPROP_IDENTIFIERCASE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53d1c-315">Isolation Levels</span><span class="sxs-lookup"><span data-stu-id="53d1c-315">Isolation Levels</span></span></p></td>
<td><p><span data-ttu-id="53d1c-316">DBPROP_SUPPORTEDTXNISOLEVELS</span><span class="sxs-lookup"><span data-stu-id="53d1c-316">DBPROP_SUPPORTEDTXNISOLEVELS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53d1c-317">Isolation Retention</span><span class="sxs-lookup"><span data-stu-id="53d1c-317">Isolation Retention</span></span></p></td>
<td><p><span data-ttu-id="53d1c-318">DBPROP_SUPPORTEDTXNISORETAIN</span><span class="sxs-lookup"><span data-stu-id="53d1c-318">DBPROP_SUPPORTEDTXNISORETAIN</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53d1c-319">Locale Identifier</span><span class="sxs-lookup"><span data-stu-id="53d1c-319">Locale Identifier</span></span></p></td>
<td><p><span data-ttu-id="53d1c-320">DBPROP_INIT_LCID</span><span class="sxs-lookup"><span data-stu-id="53d1c-320">DBPROP_INIT_LCID</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53d1c-321">Maximum Index Size</span><span class="sxs-lookup"><span data-stu-id="53d1c-321">Maximum Index Size</span></span></p></td>
<td><p><span data-ttu-id="53d1c-322">DBPROP_MAXINDEXSIZE</span><span class="sxs-lookup"><span data-stu-id="53d1c-322">DBPROP_MAXINDEXSIZE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53d1c-323">Maximum Row Size</span><span class="sxs-lookup"><span data-stu-id="53d1c-323">Maximum Row Size</span></span></p></td>
<td><p><span data-ttu-id="53d1c-324">DBPROP_MAXROWSIZE</span><span class="sxs-lookup"><span data-stu-id="53d1c-324">DBPROP_MAXROWSIZE</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53d1c-325">Maximum Row Size Includes BLOB</span><span class="sxs-lookup"><span data-stu-id="53d1c-325">Maximum Row Size Includes BLOB</span></span></p></td>
<td><p><span data-ttu-id="53d1c-326">DBPROP_MAXROWSIZEINCLUDESBLOB</span><span class="sxs-lookup"><span data-stu-id="53d1c-326">DBPROP_MAXROWSIZEINCLUDESBLOB</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53d1c-327">Maximum Tables in SELECT</span><span class="sxs-lookup"><span data-stu-id="53d1c-327">Maximum Tables in SELECT</span></span></p></td>
<td><p><span data-ttu-id="53d1c-328">DBPROP_MAXTABLESINSELECT</span><span class="sxs-lookup"><span data-stu-id="53d1c-328">DBPROP_MAXTABLESINSELECT</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53d1c-329">Mode</span><span class="sxs-lookup"><span data-stu-id="53d1c-329">Mode</span></span></p></td>
<td><p><span data-ttu-id="53d1c-330">DBPROP_INIT_MODE</span><span class="sxs-lookup"><span data-stu-id="53d1c-330">DBPROP_INIT_MODE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53d1c-331">Multiple Parameter Sets</span><span class="sxs-lookup"><span data-stu-id="53d1c-331">Multiple Parameter Sets</span></span></p></td>
<td><p><span data-ttu-id="53d1c-332">DBPROP_MULTIPLEPARAMSETS</span><span class="sxs-lookup"><span data-stu-id="53d1c-332">DBPROP_MULTIPLEPARAMSETS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53d1c-333">Multiple Results</span><span class="sxs-lookup"><span data-stu-id="53d1c-333">Multiple Results</span></span></p></td>
<td><p><span data-ttu-id="53d1c-334">DBPROP_MULTIPLERESULTS</span><span class="sxs-lookup"><span data-stu-id="53d1c-334">DBPROP_MULTIPLERESULTS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53d1c-335">Multiple Storage Objects</span><span class="sxs-lookup"><span data-stu-id="53d1c-335">Multiple Storage Objects</span></span></p></td>
<td><p><span data-ttu-id="53d1c-336">DBPROP_MULTIPLESTORAGEOBJECTS</span><span class="sxs-lookup"><span data-stu-id="53d1c-336">DBPROP_MULTIPLESTORAGEOBJECTS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53d1c-337">Multi-Table Update</span><span class="sxs-lookup"><span data-stu-id="53d1c-337">Multi-Table Update</span></span></p></td>
<td><p><span data-ttu-id="53d1c-338">DBPROP_MULTITABLEUPDATE</span><span class="sxs-lookup"><span data-stu-id="53d1c-338">DBPROP_MULTITABLEUPDATE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53d1c-339">NULL Collation Order</span><span class="sxs-lookup"><span data-stu-id="53d1c-339">NULL Collation Order</span></span></p></td>
<td><p><span data-ttu-id="53d1c-340">DBPROP_NULLCOLLATION</span><span class="sxs-lookup"><span data-stu-id="53d1c-340">DBPROP_NULLCOLLATION</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53d1c-341">NULL Concatenation Behavior</span><span class="sxs-lookup"><span data-stu-id="53d1c-341">NULL Concatenation Behavior</span></span></p></td>
<td><p><span data-ttu-id="53d1c-342">DBPROP_CONCATNULLBEHAVIOR</span><span class="sxs-lookup"><span data-stu-id="53d1c-342">DBPROP_CONCATNULLBEHAVIOR</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53d1c-343">OLE DB Version</span><span class="sxs-lookup"><span data-stu-id="53d1c-343">OLE DB Version</span></span></p></td>
<td><p><span data-ttu-id="53d1c-344">DBPROP_PROVIDEROLEDBVER</span><span class="sxs-lookup"><span data-stu-id="53d1c-344">DBPROP_PROVIDEROLEDBVER</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53d1c-345">OLE Object Support</span><span class="sxs-lookup"><span data-stu-id="53d1c-345">OLE Object Support</span></span></p></td>
<td><p><span data-ttu-id="53d1c-346">DBPROP_OLEOBJECTS</span><span class="sxs-lookup"><span data-stu-id="53d1c-346">DBPROP_OLEOBJECTS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53d1c-347">Open Rowset Support</span><span class="sxs-lookup"><span data-stu-id="53d1c-347">Open Rowset Support</span></span></p></td>
<td><p><span data-ttu-id="53d1c-348">DBPROP_OPENROWSETSUPPORT</span><span class="sxs-lookup"><span data-stu-id="53d1c-348">DBPROP_OPENROWSETSUPPORT</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53d1c-349">ORDER BY Columns in Select List</span><span class="sxs-lookup"><span data-stu-id="53d1c-349">ORDER BY Columns in Select List</span></span></p></td>
<td><p><span data-ttu-id="53d1c-350">DBPROP_ORDERBYCOLUMNSINSELECT</span><span class="sxs-lookup"><span data-stu-id="53d1c-350">DBPROP_ORDERBYCOLUMNSINSELECT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53d1c-351">Output Parameter Availability</span><span class="sxs-lookup"><span data-stu-id="53d1c-351">Output Parameter Availability</span></span></p></td>
<td><p><span data-ttu-id="53d1c-352">DBPROP_OUTPUTPARAMETERAVAILABILITY</span><span class="sxs-lookup"><span data-stu-id="53d1c-352">DBPROP_OUTPUTPARAMETERAVAILABILITY</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53d1c-353">Pass By Ref Accessors</span><span class="sxs-lookup"><span data-stu-id="53d1c-353">Pass By Ref Accessors</span></span></p></td>
<td><p><span data-ttu-id="53d1c-354">DBPROP_BYREFACCESSORS</span><span class="sxs-lookup"><span data-stu-id="53d1c-354">DBPROP_BYREFACCESSORS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53d1c-355">Password</span><span class="sxs-lookup"><span data-stu-id="53d1c-355">Password</span></span></p></td>
<td><p><span data-ttu-id="53d1c-356">DBPROP_AUTH_PASSWORD</span><span class="sxs-lookup"><span data-stu-id="53d1c-356">DBPROP_AUTH_PASSWORD</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53d1c-357">Persistent ID Type</span><span class="sxs-lookup"><span data-stu-id="53d1c-357">Persistent ID Type</span></span></p></td>
<td><p><span data-ttu-id="53d1c-358">DBPROP_PERSISTENTIDTYPE</span><span class="sxs-lookup"><span data-stu-id="53d1c-358">DBPROP_PERSISTENTIDTYPE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53d1c-359">Prepare Abort Behavior</span><span class="sxs-lookup"><span data-stu-id="53d1c-359">Prepare Abort Behavior</span></span></p></td>
<td><p><span data-ttu-id="53d1c-360">DBPROP_PREPAREABORTBEHAVIOR</span><span class="sxs-lookup"><span data-stu-id="53d1c-360">DBPROP_PREPAREABORTBEHAVIOR</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53d1c-361">Prepare Commit Behavior</span><span class="sxs-lookup"><span data-stu-id="53d1c-361">Prepare Commit Behavior</span></span></p></td>
<td><p><span data-ttu-id="53d1c-362">DBPROP_PREPARECOMMITBEHAVIOR</span><span class="sxs-lookup"><span data-stu-id="53d1c-362">DBPROP_PREPARECOMMITBEHAVIOR</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53d1c-363">Procedure Term</span><span class="sxs-lookup"><span data-stu-id="53d1c-363">Procedure Term</span></span></p></td>
<td><p><span data-ttu-id="53d1c-364">DBPROP_PROCEDURETERM</span><span class="sxs-lookup"><span data-stu-id="53d1c-364">DBPROP_PROCEDURETERM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53d1c-365">Prompt</span><span class="sxs-lookup"><span data-stu-id="53d1c-365">Prompt</span></span></p></td>
<td><p><span data-ttu-id="53d1c-366">DBPROP_INIT_PROMPT</span><span class="sxs-lookup"><span data-stu-id="53d1c-366">DBPROP_INIT_PROMPT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53d1c-367">Provider Friendly Name</span><span class="sxs-lookup"><span data-stu-id="53d1c-367">Provider Friendly Name</span></span></p></td>
<td><p><span data-ttu-id="53d1c-368">DBPROP_PROVIDERFRIENDLYNAME</span><span class="sxs-lookup"><span data-stu-id="53d1c-368">DBPROP_PROVIDERFRIENDLYNAME</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53d1c-369">Provider Name</span><span class="sxs-lookup"><span data-stu-id="53d1c-369">Provider Name</span></span></p></td>
<td><p><span data-ttu-id="53d1c-370">DBPROP_PROVIDERFILENAME</span><span class="sxs-lookup"><span data-stu-id="53d1c-370">DBPROP_PROVIDERFILENAME</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53d1c-371">Provider Version</span><span class="sxs-lookup"><span data-stu-id="53d1c-371">Provider Version</span></span></p></td>
<td><p><span data-ttu-id="53d1c-372">DBPROP_PROVIDERVER</span><span class="sxs-lookup"><span data-stu-id="53d1c-372">DBPROP_PROVIDERVER</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53d1c-373">Read-Only Data Source</span><span class="sxs-lookup"><span data-stu-id="53d1c-373">Read-Only Data Source</span></span></p></td>
<td><p><span data-ttu-id="53d1c-374">DBPROP_DATASOURCEREADONLY</span><span class="sxs-lookup"><span data-stu-id="53d1c-374">DBPROP_DATASOURCEREADONLY</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53d1c-375">Rowset Conversions on Command</span><span class="sxs-lookup"><span data-stu-id="53d1c-375">Rowset Conversions on Command</span></span></p></td>
<td><p><span data-ttu-id="53d1c-376">DBPROP_ROWSETCONVERSIONSONCOMMAND</span><span class="sxs-lookup"><span data-stu-id="53d1c-376">DBPROP_ROWSETCONVERSIONSONCOMMAND</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53d1c-377">Schema Term</span><span class="sxs-lookup"><span data-stu-id="53d1c-377">Schema Term</span></span></p></td>
<td><p><span data-ttu-id="53d1c-378">DBPROP_SCHEMATERM</span><span class="sxs-lookup"><span data-stu-id="53d1c-378">DBPROP_SCHEMATERM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53d1c-379">Schema Usage</span><span class="sxs-lookup"><span data-stu-id="53d1c-379">Schema Usage</span></span></p></td>
<td><p><span data-ttu-id="53d1c-380">DBPROP_SCHEMAUSAGE</span><span class="sxs-lookup"><span data-stu-id="53d1c-380">DBPROP_SCHEMAUSAGE</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53d1c-381">SQL Support</span><span class="sxs-lookup"><span data-stu-id="53d1c-381">SQL Support</span></span></p></td>
<td><p><span data-ttu-id="53d1c-382">DBPROP_SQLSUPPORT</span><span class="sxs-lookup"><span data-stu-id="53d1c-382">DBPROP_SQLSUPPORT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53d1c-383">Structured Storage</span><span class="sxs-lookup"><span data-stu-id="53d1c-383">Structured Storage</span></span></p></td>
<td><p><span data-ttu-id="53d1c-384">DBPROP_STRUCTUREDSTORAGE</span><span class="sxs-lookup"><span data-stu-id="53d1c-384">DBPROP_STRUCTUREDSTORAGE</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53d1c-385">Subquery Support</span><span class="sxs-lookup"><span data-stu-id="53d1c-385">Subquery Support</span></span></p></td>
<td><p><span data-ttu-id="53d1c-386">DBPROP_SUBQUERIES</span><span class="sxs-lookup"><span data-stu-id="53d1c-386">DBPROP_SUBQUERIES</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53d1c-387">Table Term</span><span class="sxs-lookup"><span data-stu-id="53d1c-387">Table Term</span></span></p></td>
<td><p><span data-ttu-id="53d1c-388">DBPROP_TABLETERM</span><span class="sxs-lookup"><span data-stu-id="53d1c-388">DBPROP_TABLETERM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53d1c-389">Transaction DDL</span><span class="sxs-lookup"><span data-stu-id="53d1c-389">Transaction DDL</span></span></p></td>
<td><p><span data-ttu-id="53d1c-390">DBPROP_SUPPORTEDTXNDDL</span><span class="sxs-lookup"><span data-stu-id="53d1c-390">DBPROP_SUPPORTEDTXNDDL</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53d1c-391">User ID</span><span class="sxs-lookup"><span data-stu-id="53d1c-391">User ID</span></span></p></td>
<td><p><span data-ttu-id="53d1c-392">DBPROP_AUTH_USERID</span><span class="sxs-lookup"><span data-stu-id="53d1c-392">DBPROP_AUTH_USERID</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53d1c-393">User Name</span><span class="sxs-lookup"><span data-stu-id="53d1c-393">User Name</span></span></p></td>
<td><p><span data-ttu-id="53d1c-394">DBPROP_USERNAME</span><span class="sxs-lookup"><span data-stu-id="53d1c-394">DBPROP_USERNAME</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53d1c-395">Window Handle</span><span class="sxs-lookup"><span data-stu-id="53d1c-395">Window Handle</span></span></p></td>
<td><p><span data-ttu-id="53d1c-396">DBPROP_INIT_HWND</span><span class="sxs-lookup"><span data-stu-id="53d1c-396">DBPROP_INIT_HWND</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="recordset-dynamic-properties"></a><span data-ttu-id="53d1c-397">Recordset 动态属性</span><span class="sxs-lookup"><span data-stu-id="53d1c-397">Recordset Dynamic Properties</span></span>

<span data-ttu-id="53d1c-398">以下属性将被添加到 **Recordset** 对象的 **Properties** 集合中。</span><span class="sxs-lookup"><span data-stu-id="53d1c-398">The following properties are added to the **Recordset** object's **Properties** collection.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="53d1c-399">ADO 属性名</span><span class="sxs-lookup"><span data-stu-id="53d1c-399">ADO Property Name</span></span></p></th>
<th><p><span data-ttu-id="53d1c-400">OLE DB 属性名</span><span class="sxs-lookup"><span data-stu-id="53d1c-400">OLE DB Property Name</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="53d1c-401">Access Order</span><span class="sxs-lookup"><span data-stu-id="53d1c-401">Access Order</span></span></p></td>
<td><p><span data-ttu-id="53d1c-402">DBPROP_ACCESSORDER</span><span class="sxs-lookup"><span data-stu-id="53d1c-402">DBPROP_ACCESSORDER</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53d1c-403">Append-Only Rowset</span><span class="sxs-lookup"><span data-stu-id="53d1c-403">Append-Only Rowset</span></span></p></td>
<td><p><span data-ttu-id="53d1c-404">DBPROP_APPENDONLY</span><span class="sxs-lookup"><span data-stu-id="53d1c-404">DBPROP_APPENDONLY</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53d1c-405">Blocking Storage Objects</span><span class="sxs-lookup"><span data-stu-id="53d1c-405">Blocking Storage Objects</span></span></p></td>
<td><p><span data-ttu-id="53d1c-406">DBPROP_BLOCKINGSTORAGEOBJECTS</span><span class="sxs-lookup"><span data-stu-id="53d1c-406">DBPROP_BLOCKINGSTORAGEOBJECTS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53d1c-407">Bookmark Type</span><span class="sxs-lookup"><span data-stu-id="53d1c-407">Bookmark Type</span></span></p></td>
<td><p><span data-ttu-id="53d1c-408">DBPROP_BOOKMARKTYPE</span><span class="sxs-lookup"><span data-stu-id="53d1c-408">DBPROP_BOOKMARKTYPE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53d1c-409">Bookmarkable</span><span class="sxs-lookup"><span data-stu-id="53d1c-409">Bookmarkable</span></span></p></td>
<td><p><span data-ttu-id="53d1c-410">DBPROP_IROWSETLOCATE</span><span class="sxs-lookup"><span data-stu-id="53d1c-410">DBPROP_IROWSETLOCATE</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53d1c-411">Bookmarks Ordered</span><span class="sxs-lookup"><span data-stu-id="53d1c-411">Bookmarks Ordered</span></span></p></td>
<td><p><span data-ttu-id="53d1c-412">DBPROP_ORDEREDBOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="53d1c-412">DBPROP_ORDEREDBOOKMARKS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53d1c-413">Cache Deferred Columns</span><span class="sxs-lookup"><span data-stu-id="53d1c-413">Cache Deferred Columns</span></span></p></td>
<td><p><span data-ttu-id="53d1c-414">DBPROP_CACHEDEFERRED</span><span class="sxs-lookup"><span data-stu-id="53d1c-414">DBPROP_CACHEDEFERRED</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53d1c-415">Change Inserted Rows</span><span class="sxs-lookup"><span data-stu-id="53d1c-415">Change Inserted Rows</span></span></p></td>
<td><p><span data-ttu-id="53d1c-416">DBPROP_CHANGEINSERTEDROWS</span><span class="sxs-lookup"><span data-stu-id="53d1c-416">DBPROP_CHANGEINSERTEDROWS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53d1c-417">Column Privileges</span><span class="sxs-lookup"><span data-stu-id="53d1c-417">Column Privileges</span></span></p></td>
<td><p><span data-ttu-id="53d1c-418">DBPROP_COLUMNRESTRICT</span><span class="sxs-lookup"><span data-stu-id="53d1c-418">DBPROP_COLUMNRESTRICT</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53d1c-419">Column Set Notification</span><span class="sxs-lookup"><span data-stu-id="53d1c-419">Column Set Notification</span></span></p></td>
<td><p><span data-ttu-id="53d1c-420">DBPROP_NOTIFYCOLUMNSET</span><span class="sxs-lookup"><span data-stu-id="53d1c-420">DBPROP_NOTIFYCOLUMNSET</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53d1c-421">Column Writable</span><span class="sxs-lookup"><span data-stu-id="53d1c-421">Column Writable</span></span></p></td>
<td><p><span data-ttu-id="53d1c-422">DBPROP_MAYWRITECOLUMN</span><span class="sxs-lookup"><span data-stu-id="53d1c-422">DBPROP_MAYWRITECOLUMN</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53d1c-423">Defer Column</span><span class="sxs-lookup"><span data-stu-id="53d1c-423">Defer Column</span></span></p></td>
<td><p><span data-ttu-id="53d1c-424">DBPROP_DEFERRED</span><span class="sxs-lookup"><span data-stu-id="53d1c-424">DBPROP_DEFERRED</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53d1c-425">Delay Storage Object Updates</span><span class="sxs-lookup"><span data-stu-id="53d1c-425">Delay Storage Object Updates</span></span></p></td>
<td><p><span data-ttu-id="53d1c-426">DBPROP_DELAYSTORAGEOBJECTS</span><span class="sxs-lookup"><span data-stu-id="53d1c-426">DBPROP_DELAYSTORAGEOBJECTS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53d1c-427">Fetch Backwards</span><span class="sxs-lookup"><span data-stu-id="53d1c-427">Fetch Backwards</span></span></p></td>
<td><p><span data-ttu-id="53d1c-428">DBPROP_CANFETCHBACKWARDS</span><span class="sxs-lookup"><span data-stu-id="53d1c-428">DBPROP_CANFETCHBACKWARDS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53d1c-429">Hold Rows</span><span class="sxs-lookup"><span data-stu-id="53d1c-429">Hold Rows</span></span></p></td>
<td><p><span data-ttu-id="53d1c-430">DBPROP_CANHOLDROWS</span><span class="sxs-lookup"><span data-stu-id="53d1c-430">DBPROP_CANHOLDROWS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53d1c-431">IAccessor</span><span class="sxs-lookup"><span data-stu-id="53d1c-431">IAccessor</span></span></p></td>
<td><p><span data-ttu-id="53d1c-432">DBPROP_IAccessor</span><span class="sxs-lookup"><span data-stu-id="53d1c-432">DBPROP_IAccessor</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53d1c-433">IColumnsInfo</span><span class="sxs-lookup"><span data-stu-id="53d1c-433">IColumnsInfo</span></span></p></td>
<td><p><span data-ttu-id="53d1c-434">DBPROP_IColumnsInfo</span><span class="sxs-lookup"><span data-stu-id="53d1c-434">DBPROP_IColumnsInfo</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53d1c-435">IColumnsRowset</span><span class="sxs-lookup"><span data-stu-id="53d1c-435">IColumnsRowset</span></span></p></td>
<td><p><span data-ttu-id="53d1c-436">DBPROP_IColumnsRowset</span><span class="sxs-lookup"><span data-stu-id="53d1c-436">DBPROP_IColumnsRowset</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53d1c-437">IConnectionPointContainer</span><span class="sxs-lookup"><span data-stu-id="53d1c-437">IConnectionPointContainer</span></span></p></td>
<td><p><span data-ttu-id="53d1c-438">DBPROP_IConnectionPointContainer</span><span class="sxs-lookup"><span data-stu-id="53d1c-438">DBPROP_IConnectionPointContainer</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53d1c-439">IConvertType</span><span class="sxs-lookup"><span data-stu-id="53d1c-439">IConvertType</span></span></p></td>
<td><p><span data-ttu-id="53d1c-440">DBPROP_IConvertType</span><span class="sxs-lookup"><span data-stu-id="53d1c-440">DBPROP_IConvertType</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53d1c-441">ILockBytes</span><span class="sxs-lookup"><span data-stu-id="53d1c-441">ILockBytes</span></span></p></td>
<td><p><span data-ttu-id="53d1c-442">DBPROP_ILockBytes</span><span class="sxs-lookup"><span data-stu-id="53d1c-442">DBPROP_ILockBytes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53d1c-443">Immobile Rows</span><span class="sxs-lookup"><span data-stu-id="53d1c-443">Immobile Rows</span></span></p></td>
<td><p><span data-ttu-id="53d1c-444">DBPROP_IMMOBILEROWS</span><span class="sxs-lookup"><span data-stu-id="53d1c-444">DBPROP_IMMOBILEROWS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53d1c-445">IRowset</span><span class="sxs-lookup"><span data-stu-id="53d1c-445">IRowset</span></span></p></td>
<td><p><span data-ttu-id="53d1c-446">DBPROP_IRowset</span><span class="sxs-lookup"><span data-stu-id="53d1c-446">DBPROP_IRowset</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53d1c-447">IRowsetChange</span><span class="sxs-lookup"><span data-stu-id="53d1c-447">IRowsetChange</span></span></p></td>
<td><p><span data-ttu-id="53d1c-448">DBPROP_IRowsetChange</span><span class="sxs-lookup"><span data-stu-id="53d1c-448">DBPROP_IRowsetChange</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53d1c-449">IRowsetIdentity</span><span class="sxs-lookup"><span data-stu-id="53d1c-449">IRowsetIdentity</span></span></p></td>
<td><p><span data-ttu-id="53d1c-450">DBPROP_IRowsetIdentity</span><span class="sxs-lookup"><span data-stu-id="53d1c-450">DBPROP_IRowsetIdentity</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53d1c-451">IRowsetIndex</span><span class="sxs-lookup"><span data-stu-id="53d1c-451">IRowsetIndex</span></span></p></td>
<td><p><span data-ttu-id="53d1c-452">DBPROP_IRowsetIndex</span><span class="sxs-lookup"><span data-stu-id="53d1c-452">DBPROP_IRowsetIndex</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53d1c-453">IRowsetInfo</span><span class="sxs-lookup"><span data-stu-id="53d1c-453">IRowsetInfo</span></span></p></td>
<td><p><span data-ttu-id="53d1c-454">DBPROP_IRowsetInfo</span><span class="sxs-lookup"><span data-stu-id="53d1c-454">DBPROP_IRowsetInfo</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53d1c-455">IRowsetLocate</span><span class="sxs-lookup"><span data-stu-id="53d1c-455">IRowsetLocate</span></span></p></td>
<td><p><span data-ttu-id="53d1c-456">DBPROP_IRowsestLocate</span><span class="sxs-lookup"><span data-stu-id="53d1c-456">DBPROP_IRowsestLocate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53d1c-457">IRowsetResynch</span><span class="sxs-lookup"><span data-stu-id="53d1c-457">IRowsetResynch</span></span></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53d1c-458">IRowsetScroll</span><span class="sxs-lookup"><span data-stu-id="53d1c-458">IRowsetScroll</span></span></p></td>
<td><p><span data-ttu-id="53d1c-459">DBPROP_IRowsetScroll</span><span class="sxs-lookup"><span data-stu-id="53d1c-459">DBPROP_IRowsetScroll</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53d1c-460">IRowsetUpdate</span><span class="sxs-lookup"><span data-stu-id="53d1c-460">IRowsetUpdate</span></span></p></td>
<td><p><span data-ttu-id="53d1c-461">DBPROP_IRowsetUpdate</span><span class="sxs-lookup"><span data-stu-id="53d1c-461">DBPROP_IRowsetUpdate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53d1c-462">ISequentialStream</span><span class="sxs-lookup"><span data-stu-id="53d1c-462">ISequentialStream</span></span></p></td>
<td><p><span data-ttu-id="53d1c-463">DBPROP_ISequentialStream</span><span class="sxs-lookup"><span data-stu-id="53d1c-463">DBPROP_ISequentialStream</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53d1c-464">IStorage</span><span class="sxs-lookup"><span data-stu-id="53d1c-464">IStorage</span></span></p></td>
<td><p><span data-ttu-id="53d1c-465">DBPROP_IStorage</span><span class="sxs-lookup"><span data-stu-id="53d1c-465">DBPROP_IStorage</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53d1c-466">IStream</span><span class="sxs-lookup"><span data-stu-id="53d1c-466">IStream</span></span></p></td>
<td><p><span data-ttu-id="53d1c-467">DBPROP_IStream</span><span class="sxs-lookup"><span data-stu-id="53d1c-467">DBPROP_IStream</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53d1c-468">ISupportErrorInfo</span><span class="sxs-lookup"><span data-stu-id="53d1c-468">ISupportErrorInfo</span></span></p></td>
<td><p><span data-ttu-id="53d1c-469">DBPROP_ISupportErrorInfo</span><span class="sxs-lookup"><span data-stu-id="53d1c-469">DBPROP_ISupportErrorInfo</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53d1c-470">Literal Bookmarks</span><span class="sxs-lookup"><span data-stu-id="53d1c-470">Literal Bookmarks</span></span></p></td>
<td><p><span data-ttu-id="53d1c-471">DBPROP_LITERALBOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="53d1c-471">DBPROP_LITERALBOOKMARKS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53d1c-472">Literal Row Identity</span><span class="sxs-lookup"><span data-stu-id="53d1c-472">Literal Row Identity</span></span></p></td>
<td><p><span data-ttu-id="53d1c-473">DBPROP_LITERALIDENTITY</span><span class="sxs-lookup"><span data-stu-id="53d1c-473">DBPROP_LITERALIDENTITY</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53d1c-474">Maximum Open Rows</span><span class="sxs-lookup"><span data-stu-id="53d1c-474">Maximum Open Rows</span></span></p></td>
<td><p><span data-ttu-id="53d1c-475">DBPROP_MAXOPENROWS</span><span class="sxs-lookup"><span data-stu-id="53d1c-475">DBPROP_MAXOPENROWS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53d1c-476">Maximum Pending Rows</span><span class="sxs-lookup"><span data-stu-id="53d1c-476">Maximum Pending Rows</span></span></p></td>
<td><p><span data-ttu-id="53d1c-477">DBPROP_MAXPENDINGROWS</span><span class="sxs-lookup"><span data-stu-id="53d1c-477">DBPROP_MAXPENDINGROWS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53d1c-478">Maximum Rows</span><span class="sxs-lookup"><span data-stu-id="53d1c-478">Maximum Rows</span></span></p></td>
<td><p><span data-ttu-id="53d1c-479">DBPROP_MAXROWS</span><span class="sxs-lookup"><span data-stu-id="53d1c-479">DBPROP_MAXROWS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53d1c-480">Memory Usage</span><span class="sxs-lookup"><span data-stu-id="53d1c-480">Memory Usage</span></span></p></td>
<td><p><span data-ttu-id="53d1c-481">DBPROP_MEMORYUSAGE</span><span class="sxs-lookup"><span data-stu-id="53d1c-481">DBPROP_MEMORYUSAGE</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53d1c-482">Notification Granularity</span><span class="sxs-lookup"><span data-stu-id="53d1c-482">Notification Granularity</span></span></p></td>
<td><p><span data-ttu-id="53d1c-483">DBPROP_NOTIFICATIONGRANULARITY</span><span class="sxs-lookup"><span data-stu-id="53d1c-483">DBPROP_NOTIFICATIONGRANULARITY</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53d1c-484">Notification Phases</span><span class="sxs-lookup"><span data-stu-id="53d1c-484">Notification Phases</span></span></p></td>
<td><p><span data-ttu-id="53d1c-485">DBPROP_NOTIFICATIONPHASES</span><span class="sxs-lookup"><span data-stu-id="53d1c-485">DBPROP_NOTIFICATIONPHASES</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53d1c-486">Objects Transacted</span><span class="sxs-lookup"><span data-stu-id="53d1c-486">Objects Transacted</span></span></p></td>
<td><p><span data-ttu-id="53d1c-487">DBPROP_TRANSACTEDOBJECT</span><span class="sxs-lookup"><span data-stu-id="53d1c-487">DBPROP_TRANSACTEDOBJECT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53d1c-488">Others' Changes Visible</span><span class="sxs-lookup"><span data-stu-id="53d1c-488">Others' Changes Visible</span></span></p></td>
<td><p><span data-ttu-id="53d1c-489">DBPROP_OTHERUPDATEDELETE</span><span class="sxs-lookup"><span data-stu-id="53d1c-489">DBPROP_OTHERUPDATEDELETE</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53d1c-490">Others' Inserts Visible</span><span class="sxs-lookup"><span data-stu-id="53d1c-490">Others' Inserts Visible</span></span></p></td>
<td><p><span data-ttu-id="53d1c-491">DBPROP_OTHERINSERT</span><span class="sxs-lookup"><span data-stu-id="53d1c-491">DBPROP_OTHERINSERT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53d1c-492">Own Changes Visible</span><span class="sxs-lookup"><span data-stu-id="53d1c-492">Own Changes Visible</span></span></p></td>
<td><p><span data-ttu-id="53d1c-493">DBPROP_OWNUPDATEDELETE</span><span class="sxs-lookup"><span data-stu-id="53d1c-493">DBPROP_OWNUPDATEDELETE</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53d1c-494">Own Inserts Visible</span><span class="sxs-lookup"><span data-stu-id="53d1c-494">Own Inserts Visible</span></span></p></td>
<td><p><span data-ttu-id="53d1c-495">DBPROP_OWNINSERT</span><span class="sxs-lookup"><span data-stu-id="53d1c-495">DBPROP_OWNINSERT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53d1c-496">Preserve on Abort</span><span class="sxs-lookup"><span data-stu-id="53d1c-496">Preserve on Abort</span></span></p></td>
<td><p><span data-ttu-id="53d1c-497">DBPROP_ABORTPRESERVE</span><span class="sxs-lookup"><span data-stu-id="53d1c-497">DBPROP_ABORTPRESERVE</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53d1c-498">Preserve on Commit</span><span class="sxs-lookup"><span data-stu-id="53d1c-498">Preserve on Commit</span></span></p></td>
<td><p><span data-ttu-id="53d1c-499">DBPROP_COMMITPRESERVE</span><span class="sxs-lookup"><span data-stu-id="53d1c-499">DBPROP_COMMITPRESERVE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53d1c-500">Quick Restart</span><span class="sxs-lookup"><span data-stu-id="53d1c-500">Quick Restart</span></span></p></td>
<td><p><span data-ttu-id="53d1c-501">DBPROP_QUICKRESTART</span><span class="sxs-lookup"><span data-stu-id="53d1c-501">DBPROP_QUICKRESTART</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53d1c-502">Reentrant Events</span><span class="sxs-lookup"><span data-stu-id="53d1c-502">Reentrant Events</span></span></p></td>
<td><p><span data-ttu-id="53d1c-503">DBPROP_REENTRANTEVENTS</span><span class="sxs-lookup"><span data-stu-id="53d1c-503">DBPROP_REENTRANTEVENTS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53d1c-504">Remove Deleted Rows</span><span class="sxs-lookup"><span data-stu-id="53d1c-504">Remove Deleted Rows</span></span></p></td>
<td><p><span data-ttu-id="53d1c-505">DBPROP_REMOVEDELETED</span><span class="sxs-lookup"><span data-stu-id="53d1c-505">DBPROP_REMOVEDELETED</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53d1c-506">Report Multiple Changes</span><span class="sxs-lookup"><span data-stu-id="53d1c-506">Report Multiple Changes</span></span></p></td>
<td><p><span data-ttu-id="53d1c-507">DBPROP_REPORTMULTIPLECHANGES</span><span class="sxs-lookup"><span data-stu-id="53d1c-507">DBPROP_REPORTMULTIPLECHANGES</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53d1c-508">Return Pending Inserts</span><span class="sxs-lookup"><span data-stu-id="53d1c-508">Return Pending Inserts</span></span></p></td>
<td><p><span data-ttu-id="53d1c-509">DBPROP_RETURNPENDINGINSERTS</span><span class="sxs-lookup"><span data-stu-id="53d1c-509">DBPROP_RETURNPENDINGINSERTS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53d1c-510">Row Delete Notification</span><span class="sxs-lookup"><span data-stu-id="53d1c-510">Row Delete Notification</span></span></p></td>
<td><p><span data-ttu-id="53d1c-511">DBPROP_NOTIFYROWDELETE</span><span class="sxs-lookup"><span data-stu-id="53d1c-511">DBPROP_NOTIFYROWDELETE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53d1c-512">Row First Change Notification</span><span class="sxs-lookup"><span data-stu-id="53d1c-512">Row First Change Notification</span></span></p></td>
<td><p><span data-ttu-id="53d1c-513">DBPROP_NOTIFYROWFIRSTCHANGE</span><span class="sxs-lookup"><span data-stu-id="53d1c-513">DBPROP_NOTIFYROWFIRSTCHANGE</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53d1c-514">Row Insert Notification</span><span class="sxs-lookup"><span data-stu-id="53d1c-514">Row Insert Notification</span></span></p></td>
<td><p><span data-ttu-id="53d1c-515">DBPROP_NOTIFYROWINSERT</span><span class="sxs-lookup"><span data-stu-id="53d1c-515">DBPROP_NOTIFYROWINSERT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53d1c-516">Row Privileges</span><span class="sxs-lookup"><span data-stu-id="53d1c-516">Row Privileges</span></span></p></td>
<td><p><span data-ttu-id="53d1c-517">DBPROP_ROWRESTRICT</span><span class="sxs-lookup"><span data-stu-id="53d1c-517">DBPROP_ROWRESTRICT</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53d1c-518">Row Resynchronization Notification</span><span class="sxs-lookup"><span data-stu-id="53d1c-518">Row Resynchronization Notification</span></span></p></td>
<td><p><span data-ttu-id="53d1c-519">DBPROP_NOTIFYROWRESYNCH</span><span class="sxs-lookup"><span data-stu-id="53d1c-519">DBPROP_NOTIFYROWRESYNCH</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53d1c-520">Row Threading Model</span><span class="sxs-lookup"><span data-stu-id="53d1c-520">Row Threading Model</span></span></p></td>
<td><p><span data-ttu-id="53d1c-521">DBPROP_ROWTHREADMODEL</span><span class="sxs-lookup"><span data-stu-id="53d1c-521">DBPROP_ROWTHREADMODEL</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53d1c-522">Row Undo Change Notification</span><span class="sxs-lookup"><span data-stu-id="53d1c-522">Row Undo Change Notification</span></span></p></td>
<td><p><span data-ttu-id="53d1c-523">DBPROP_NOTIFYROWUNDOCHANGE</span><span class="sxs-lookup"><span data-stu-id="53d1c-523">DBPROP_NOTIFYROWUNDOCHANGE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53d1c-524">Row Undo Delete Notification</span><span class="sxs-lookup"><span data-stu-id="53d1c-524">Row Undo Delete Notification</span></span></p></td>
<td><p><span data-ttu-id="53d1c-525">DBPROP_NOTIFYROWUNDODELETE</span><span class="sxs-lookup"><span data-stu-id="53d1c-525">DBPROP_NOTIFYROWUNDODELETE</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53d1c-526">Row Undo Insert Notification</span><span class="sxs-lookup"><span data-stu-id="53d1c-526">Row Undo Insert Notification</span></span></p></td>
<td><p><span data-ttu-id="53d1c-527">DBPROP_NOTIFYROWUNDOINSERT</span><span class="sxs-lookup"><span data-stu-id="53d1c-527">DBPROP_NOTIFYROWUNDOINSERT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53d1c-528">Row Update Notification</span><span class="sxs-lookup"><span data-stu-id="53d1c-528">Row Update Notification</span></span></p></td>
<td><p><span data-ttu-id="53d1c-529">DBPROP_NOTIFYROWUPDATE</span><span class="sxs-lookup"><span data-stu-id="53d1c-529">DBPROP_NOTIFYROWUPDATE</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53d1c-530">Rowset Fetch Position Change Notification</span><span class="sxs-lookup"><span data-stu-id="53d1c-530">Rowset Fetch Position Change Notification</span></span></p></td>
<td><p><span data-ttu-id="53d1c-531">DBPROP_NOTIFYROWSETFETCHPOSISIONCHANGE</span><span class="sxs-lookup"><span data-stu-id="53d1c-531">DBPROP_NOTIFYROWSETFETCHPOSISIONCHANGE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53d1c-532">Rowset Release Notification</span><span class="sxs-lookup"><span data-stu-id="53d1c-532">Rowset Release Notification</span></span></p></td>
<td><p><span data-ttu-id="53d1c-533">DBPROP_NOTIFYROWSETRELEASE</span><span class="sxs-lookup"><span data-stu-id="53d1c-533">DBPROP_NOTIFYROWSETRELEASE</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53d1c-534">Scroll Backwards</span><span class="sxs-lookup"><span data-stu-id="53d1c-534">Scroll Backwards</span></span></p></td>
<td><p><span data-ttu-id="53d1c-535">DBPROP_CANSCROLLBACKWARDS</span><span class="sxs-lookup"><span data-stu-id="53d1c-535">DBPROP_CANSCROLLBACKWARDS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53d1c-536">Skip Deleted Bookmarks</span><span class="sxs-lookup"><span data-stu-id="53d1c-536">Skip Deleted Bookmarks</span></span></p></td>
<td><p><span data-ttu-id="53d1c-537">DBPROP_BOOKMARKSKIPPED</span><span class="sxs-lookup"><span data-stu-id="53d1c-537">DBPROP_BOOKMARKSKIPPED</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53d1c-538">Strong Row Identity</span><span class="sxs-lookup"><span data-stu-id="53d1c-538">Strong Row Identity</span></span></p></td>
<td><p><span data-ttu-id="53d1c-539">DBPROP_STRONGITDENTITY</span><span class="sxs-lookup"><span data-stu-id="53d1c-539">DBPROP_STRONGITDENTITY</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53d1c-540">Updatability</span><span class="sxs-lookup"><span data-stu-id="53d1c-540">Updatability</span></span></p></td>
<td><p><span data-ttu-id="53d1c-541">DBPROP_UPDATABILITY</span><span class="sxs-lookup"><span data-stu-id="53d1c-541">DBPROP_UPDATABILITY</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53d1c-542">Use Bookmarks</span><span class="sxs-lookup"><span data-stu-id="53d1c-542">Use Bookmarks</span></span></p></td>
<td><p><span data-ttu-id="53d1c-543">DBPROP_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="53d1c-543">DBPROP_BOOKMARKS</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="command-dynamic-properties"></a><span data-ttu-id="53d1c-544">Command 动态属性</span><span class="sxs-lookup"><span data-stu-id="53d1c-544">Command Dynamic Properties</span></span>

<span data-ttu-id="53d1c-545">以下属性将被添加到 **Command** 对象的 **Properties** 集合中。</span><span class="sxs-lookup"><span data-stu-id="53d1c-545">The following properties are added to the **Command** object's **Properties** collection.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="53d1c-546">ADO 属性名</span><span class="sxs-lookup"><span data-stu-id="53d1c-546">ADO Property Name</span></span></p></th>
<th><p><span data-ttu-id="53d1c-547">OLE DB 属性名</span><span class="sxs-lookup"><span data-stu-id="53d1c-547">OLE DB Property Name</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="53d1c-548">Access Order</span><span class="sxs-lookup"><span data-stu-id="53d1c-548">Access Order</span></span></p></td>
<td><p><span data-ttu-id="53d1c-549">DBPROP_ACCESSORDER</span><span class="sxs-lookup"><span data-stu-id="53d1c-549">DBPROP_ACCESSORDER</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53d1c-550">Append-Only Rowset</span><span class="sxs-lookup"><span data-stu-id="53d1c-550">Append-Only Rowset</span></span></p></td>
<td><p><span data-ttu-id="53d1c-551">DBPROP_APPENDONLY</span><span class="sxs-lookup"><span data-stu-id="53d1c-551">DBPROP_APPENDONLY</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53d1c-552">Blocking Storage Objects</span><span class="sxs-lookup"><span data-stu-id="53d1c-552">Blocking Storage Objects</span></span></p></td>
<td><p><span data-ttu-id="53d1c-553">DBPROP_BLOCKINGSTORAGEOBJECTS</span><span class="sxs-lookup"><span data-stu-id="53d1c-553">DBPROP_BLOCKINGSTORAGEOBJECTS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53d1c-554">Bookmark Type</span><span class="sxs-lookup"><span data-stu-id="53d1c-554">Bookmark Type</span></span></p></td>
<td><p><span data-ttu-id="53d1c-555">DBPROP_BOOKMARKTYPE</span><span class="sxs-lookup"><span data-stu-id="53d1c-555">DBPROP_BOOKMARKTYPE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53d1c-556">Bookmarkable</span><span class="sxs-lookup"><span data-stu-id="53d1c-556">Bookmarkable</span></span></p></td>
<td><p><span data-ttu-id="53d1c-557">DBPROP_IROWSETLOCATE</span><span class="sxs-lookup"><span data-stu-id="53d1c-557">DBPROP_IROWSETLOCATE</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53d1c-558">Change Inserted Rows</span><span class="sxs-lookup"><span data-stu-id="53d1c-558">Change Inserted Rows</span></span></p></td>
<td><p><span data-ttu-id="53d1c-559">DBPROP_CHANGEINSERTEDROWS</span><span class="sxs-lookup"><span data-stu-id="53d1c-559">DBPROP_CHANGEINSERTEDROWS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53d1c-560">Column Privileges</span><span class="sxs-lookup"><span data-stu-id="53d1c-560">Column Privileges</span></span></p></td>
<td><p><span data-ttu-id="53d1c-561">DBPROP_COLUMNRESTRICT</span><span class="sxs-lookup"><span data-stu-id="53d1c-561">DBPROP_COLUMNRESTRICT</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53d1c-562">Column Set Notification</span><span class="sxs-lookup"><span data-stu-id="53d1c-562">Column Set Notification</span></span></p></td>
<td><p><span data-ttu-id="53d1c-563">DBPROP_NOTIFYCOLUMNSET</span><span class="sxs-lookup"><span data-stu-id="53d1c-563">DBPROP_NOTIFYCOLUMNSET</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53d1c-564">Defer Column</span><span class="sxs-lookup"><span data-stu-id="53d1c-564">Defer Column</span></span></p></td>
<td><p><span data-ttu-id="53d1c-565">DBPROP_DEFERRED</span><span class="sxs-lookup"><span data-stu-id="53d1c-565">DBPROP_DEFERRED</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53d1c-566">Delay Storage Object Updates</span><span class="sxs-lookup"><span data-stu-id="53d1c-566">Delay Storage Object Updates</span></span></p></td>
<td><p><span data-ttu-id="53d1c-567">DBPROP_DELAYSTORAGEOBJECTS</span><span class="sxs-lookup"><span data-stu-id="53d1c-567">DBPROP_DELAYSTORAGEOBJECTS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53d1c-568">Fetch Backwards</span><span class="sxs-lookup"><span data-stu-id="53d1c-568">Fetch Backwards</span></span></p></td>
<td><p><span data-ttu-id="53d1c-569">DBPROP_CANFETCHBACKWARDS</span><span class="sxs-lookup"><span data-stu-id="53d1c-569">DBPROP_CANFETCHBACKWARDS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53d1c-570">Hold Rows</span><span class="sxs-lookup"><span data-stu-id="53d1c-570">Hold Rows</span></span></p></td>
<td><p><span data-ttu-id="53d1c-571">DBPROP_CANHOLDROWS</span><span class="sxs-lookup"><span data-stu-id="53d1c-571">DBPROP_CANHOLDROWS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53d1c-572">IAccessor</span><span class="sxs-lookup"><span data-stu-id="53d1c-572">IAccessor</span></span></p></td>
<td><p><span data-ttu-id="53d1c-573">DBPROP_IAccessor</span><span class="sxs-lookup"><span data-stu-id="53d1c-573">DBPROP_IAccessor</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53d1c-574">IColumnsInfo</span><span class="sxs-lookup"><span data-stu-id="53d1c-574">IColumnsInfo</span></span></p></td>
<td><p><span data-ttu-id="53d1c-575">DBPROP_IColumnsInfo</span><span class="sxs-lookup"><span data-stu-id="53d1c-575">DBPROP_IColumnsInfo</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53d1c-576">IColumnsRowset</span><span class="sxs-lookup"><span data-stu-id="53d1c-576">IColumnsRowset</span></span></p></td>
<td><p><span data-ttu-id="53d1c-577">DBPROP_IColumnsRowset</span><span class="sxs-lookup"><span data-stu-id="53d1c-577">DBPROP_IColumnsRowset</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53d1c-578">IConnectionPointContainer</span><span class="sxs-lookup"><span data-stu-id="53d1c-578">IConnectionPointContainer</span></span></p></td>
<td><p><span data-ttu-id="53d1c-579">DBPROP_IConnectionPointContainer</span><span class="sxs-lookup"><span data-stu-id="53d1c-579">DBPROP_IConnectionPointContainer</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53d1c-580">IConvertType</span><span class="sxs-lookup"><span data-stu-id="53d1c-580">IConvertType</span></span></p></td>
<td><p><span data-ttu-id="53d1c-581">DBPROP_IConvertType</span><span class="sxs-lookup"><span data-stu-id="53d1c-581">DBPROP_IConvertType</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53d1c-582">ILockBytes</span><span class="sxs-lookup"><span data-stu-id="53d1c-582">ILockBytes</span></span></p></td>
<td><p><span data-ttu-id="53d1c-583">DBPROP_ILockBytes</span><span class="sxs-lookup"><span data-stu-id="53d1c-583">DBPROP_ILockBytes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53d1c-584">Immobile Rows</span><span class="sxs-lookup"><span data-stu-id="53d1c-584">Immobile Rows</span></span></p></td>
<td><p><span data-ttu-id="53d1c-585">DBPROP_IMMOBILEROWS</span><span class="sxs-lookup"><span data-stu-id="53d1c-585">DBPROP_IMMOBILEROWS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53d1c-586">IRowset</span><span class="sxs-lookup"><span data-stu-id="53d1c-586">IRowset</span></span></p></td>
<td><p><span data-ttu-id="53d1c-587">DBPROP_IRowset</span><span class="sxs-lookup"><span data-stu-id="53d1c-587">DBPROP_IRowset</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53d1c-588">IRowsetChange</span><span class="sxs-lookup"><span data-stu-id="53d1c-588">IRowsetChange</span></span></p></td>
<td><p><span data-ttu-id="53d1c-589">DBPROP_IRowsetChange</span><span class="sxs-lookup"><span data-stu-id="53d1c-589">DBPROP_IRowsetChange</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53d1c-590">IRowsetIdentity</span><span class="sxs-lookup"><span data-stu-id="53d1c-590">IRowsetIdentity</span></span></p></td>
<td><p><span data-ttu-id="53d1c-591">DBPROP_IRowsetIdentity</span><span class="sxs-lookup"><span data-stu-id="53d1c-591">DBPROP_IRowsetIdentity</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53d1c-592">IRowsetIndex</span><span class="sxs-lookup"><span data-stu-id="53d1c-592">IRowsetIndex</span></span></p></td>
<td><p><span data-ttu-id="53d1c-593">DBPROP_IRowsetIndex</span><span class="sxs-lookup"><span data-stu-id="53d1c-593">DBPROP_IRowsetIndex</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53d1c-594">IRowsetInfo</span><span class="sxs-lookup"><span data-stu-id="53d1c-594">IRowsetInfo</span></span></p></td>
<td><p><span data-ttu-id="53d1c-595">DBPROP_IRowsetInfo</span><span class="sxs-lookup"><span data-stu-id="53d1c-595">DBPROP_IRowsetInfo</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53d1c-596">IRowsetLocate</span><span class="sxs-lookup"><span data-stu-id="53d1c-596">IRowsetLocate</span></span></p></td>
<td><p><span data-ttu-id="53d1c-597">DBPROP_IRowsetLocate</span><span class="sxs-lookup"><span data-stu-id="53d1c-597">DBPROP_IRowsetLocate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53d1c-598">IRowsetResynch</span><span class="sxs-lookup"><span data-stu-id="53d1c-598">IRowsetResynch</span></span></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53d1c-599">IRowsetScroll</span><span class="sxs-lookup"><span data-stu-id="53d1c-599">IRowsetScroll</span></span></p></td>
<td><p><span data-ttu-id="53d1c-600">DBPROP_IRowsetScroll</span><span class="sxs-lookup"><span data-stu-id="53d1c-600">DBPROP_IRowsetScroll</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53d1c-601">IRowsetUpdate</span><span class="sxs-lookup"><span data-stu-id="53d1c-601">IRowsetUpdate</span></span></p></td>
<td><p><span data-ttu-id="53d1c-602">DBPROP_IRowsetUpdate</span><span class="sxs-lookup"><span data-stu-id="53d1c-602">DBPROP_IRowsetUpdate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53d1c-603">ISequentialStream</span><span class="sxs-lookup"><span data-stu-id="53d1c-603">ISequentialStream</span></span></p></td>
<td><p><span data-ttu-id="53d1c-604">DBPROP_ISequentialStream</span><span class="sxs-lookup"><span data-stu-id="53d1c-604">DBPROP_ISequentialStream</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53d1c-605">IStorage</span><span class="sxs-lookup"><span data-stu-id="53d1c-605">IStorage</span></span></p></td>
<td><p><span data-ttu-id="53d1c-606">DBPROP_IStorage</span><span class="sxs-lookup"><span data-stu-id="53d1c-606">DBPROP_IStorage</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53d1c-607">IStream</span><span class="sxs-lookup"><span data-stu-id="53d1c-607">IStream</span></span></p></td>
<td><p><span data-ttu-id="53d1c-608">DBPROP_IStream</span><span class="sxs-lookup"><span data-stu-id="53d1c-608">DBPROP_IStream</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53d1c-609">ISupportErrorInfo</span><span class="sxs-lookup"><span data-stu-id="53d1c-609">ISupportErrorInfo</span></span></p></td>
<td><p><span data-ttu-id="53d1c-610">DBPROP_ISupportErrorInfo</span><span class="sxs-lookup"><span data-stu-id="53d1c-610">DBPROP_ISupportErrorInfo</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53d1c-611">Literal Bookmarks</span><span class="sxs-lookup"><span data-stu-id="53d1c-611">Literal Bookmarks</span></span></p></td>
<td><p><span data-ttu-id="53d1c-612">DBPROP_LITERALBOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="53d1c-612">DBPROP_LITERALBOOKMARKS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53d1c-613">Literal Row Identity</span><span class="sxs-lookup"><span data-stu-id="53d1c-613">Literal Row Identity</span></span></p></td>
<td><p><span data-ttu-id="53d1c-614">DBPROP_LITERALIDENTITY</span><span class="sxs-lookup"><span data-stu-id="53d1c-614">DBPROP_LITERALIDENTITY</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53d1c-615">Lock Mode</span><span class="sxs-lookup"><span data-stu-id="53d1c-615">Lock Mode</span></span></p></td>
<td><p><span data-ttu-id="53d1c-616">DBPROP_LOCKMODE</span><span class="sxs-lookup"><span data-stu-id="53d1c-616">DBPROP_LOCKMODE</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53d1c-617">Maximum Open Rows</span><span class="sxs-lookup"><span data-stu-id="53d1c-617">Maximum Open Rows</span></span></p></td>
<td><p><span data-ttu-id="53d1c-618">DBPROP_MAXOPENROWS</span><span class="sxs-lookup"><span data-stu-id="53d1c-618">DBPROP_MAXOPENROWS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53d1c-619">Maximum Pending Rows</span><span class="sxs-lookup"><span data-stu-id="53d1c-619">Maximum Pending Rows</span></span></p></td>
<td><p><span data-ttu-id="53d1c-620">DBPROP_MAXPENDINGROWS</span><span class="sxs-lookup"><span data-stu-id="53d1c-620">DBPROP_MAXPENDINGROWS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53d1c-621">Maximum Rows</span><span class="sxs-lookup"><span data-stu-id="53d1c-621">Maximum Rows</span></span></p></td>
<td><p><span data-ttu-id="53d1c-622">DBPROP_MAXROWS</span><span class="sxs-lookup"><span data-stu-id="53d1c-622">DBPROP_MAXROWS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53d1c-623">Notification Granularity</span><span class="sxs-lookup"><span data-stu-id="53d1c-623">Notification Granularity</span></span></p></td>
<td><p><span data-ttu-id="53d1c-624">DBPROP_NOTIFICATIONGRANULARITY</span><span class="sxs-lookup"><span data-stu-id="53d1c-624">DBPROP_NOTIFICATIONGRANULARITY</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53d1c-625">Notification Phases</span><span class="sxs-lookup"><span data-stu-id="53d1c-625">Notification Phases</span></span></p></td>
<td><p><span data-ttu-id="53d1c-626">DBPROP_NOTIFICATIONPHASES</span><span class="sxs-lookup"><span data-stu-id="53d1c-626">DBPROP_NOTIFICATIONPHASES</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53d1c-627">Objects Transacted</span><span class="sxs-lookup"><span data-stu-id="53d1c-627">Objects Transacted</span></span></p></td>
<td><p><span data-ttu-id="53d1c-628">DBPROP_TRANSACTEDOBJECT</span><span class="sxs-lookup"><span data-stu-id="53d1c-628">DBPROP_TRANSACTEDOBJECT</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53d1c-629">Others' Changes Visible</span><span class="sxs-lookup"><span data-stu-id="53d1c-629">Others' Changes Visible</span></span></p></td>
<td><p><span data-ttu-id="53d1c-630">DBPROP_OTHERUPDATEDELETE</span><span class="sxs-lookup"><span data-stu-id="53d1c-630">DBPROP_OTHERUPDATEDELETE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53d1c-631">Others' Inserts Visible</span><span class="sxs-lookup"><span data-stu-id="53d1c-631">Others' Inserts Visible</span></span></p></td>
<td><p><span data-ttu-id="53d1c-632">DBPROP_OTHERINSERT</span><span class="sxs-lookup"><span data-stu-id="53d1c-632">DBPROP_OTHERINSERT</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53d1c-633">Own Changes Visible</span><span class="sxs-lookup"><span data-stu-id="53d1c-633">Own Changes Visible</span></span></p></td>
<td><p><span data-ttu-id="53d1c-634">DBPROP_OWNUPDATEDELETE</span><span class="sxs-lookup"><span data-stu-id="53d1c-634">DBPROP_OWNUPDATEDELETE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53d1c-635">Own Inserts Visible</span><span class="sxs-lookup"><span data-stu-id="53d1c-635">Own Inserts Visible</span></span></p></td>
<td><p><span data-ttu-id="53d1c-636">DBPROP_OWNINSERT</span><span class="sxs-lookup"><span data-stu-id="53d1c-636">DBPROP_OWNINSERT</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53d1c-637">Preserve on Abort</span><span class="sxs-lookup"><span data-stu-id="53d1c-637">Preserve on Abort</span></span></p></td>
<td><p><span data-ttu-id="53d1c-638">DBPROP_ABORTPRESERVE</span><span class="sxs-lookup"><span data-stu-id="53d1c-638">DBPROP_ABORTPRESERVE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53d1c-639">Preserve on Commit</span><span class="sxs-lookup"><span data-stu-id="53d1c-639">Preserve on Commit</span></span></p></td>
<td><p><span data-ttu-id="53d1c-640">DBPROP_COMMITPRESERVE</span><span class="sxs-lookup"><span data-stu-id="53d1c-640">DBPROP_COMMITPRESERVE</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53d1c-641">Quick Restart</span><span class="sxs-lookup"><span data-stu-id="53d1c-641">Quick Restart</span></span></p></td>
<td><p><span data-ttu-id="53d1c-642">DBPROP_QUICKRESTART</span><span class="sxs-lookup"><span data-stu-id="53d1c-642">DBPROP_QUICKRESTART</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53d1c-643">Reentrant Events</span><span class="sxs-lookup"><span data-stu-id="53d1c-643">Reentrant Events</span></span></p></td>
<td><p><span data-ttu-id="53d1c-644">DBPROP_REENTRANTEVENTS</span><span class="sxs-lookup"><span data-stu-id="53d1c-644">DBPROP_REENTRANTEVENTS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53d1c-645">Remove Deleted Rows</span><span class="sxs-lookup"><span data-stu-id="53d1c-645">Remove Deleted Rows</span></span></p></td>
<td><p><span data-ttu-id="53d1c-646">DBPROP_REMOVEDELETED</span><span class="sxs-lookup"><span data-stu-id="53d1c-646">DBPROP_REMOVEDELETED</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53d1c-647">Report Multiple Changes</span><span class="sxs-lookup"><span data-stu-id="53d1c-647">Report Multiple Changes</span></span></p></td>
<td><p><span data-ttu-id="53d1c-648">DBPROP_REPORTMULTIPLECHANGES</span><span class="sxs-lookup"><span data-stu-id="53d1c-648">DBPROP_REPORTMULTIPLECHANGES</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53d1c-649">Return Pending Inserts</span><span class="sxs-lookup"><span data-stu-id="53d1c-649">Return Pending Inserts</span></span></p></td>
<td><p><span data-ttu-id="53d1c-650">DBPROP_RETURNPENDINGINSERTS</span><span class="sxs-lookup"><span data-stu-id="53d1c-650">DBPROP_RETURNPENDINGINSERTS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53d1c-651">Row Delete Notification</span><span class="sxs-lookup"><span data-stu-id="53d1c-651">Row Delete Notification</span></span></p></td>
<td><p><span data-ttu-id="53d1c-652">DBPROP_NOTIFYROWDELETE</span><span class="sxs-lookup"><span data-stu-id="53d1c-652">DBPROP_NOTIFYROWDELETE</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53d1c-653">Row First Change Notification</span><span class="sxs-lookup"><span data-stu-id="53d1c-653">Row First Change Notification</span></span></p></td>
<td><p><span data-ttu-id="53d1c-654">DBPROP_NOTIFYROWFIRSTCHANGE</span><span class="sxs-lookup"><span data-stu-id="53d1c-654">DBPROP_NOTIFYROWFIRSTCHANGE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53d1c-655">Row Insert Notification</span><span class="sxs-lookup"><span data-stu-id="53d1c-655">Row Insert Notification</span></span></p></td>
<td><p><span data-ttu-id="53d1c-656">DBPROP_NOTIFYROWINSERT</span><span class="sxs-lookup"><span data-stu-id="53d1c-656">DBPROP_NOTIFYROWINSERT</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53d1c-657">Row Privileges</span><span class="sxs-lookup"><span data-stu-id="53d1c-657">Row Privileges</span></span></p></td>
<td><p><span data-ttu-id="53d1c-658">DBPROP_ROWRESTRICT</span><span class="sxs-lookup"><span data-stu-id="53d1c-658">DBPROP_ROWRESTRICT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53d1c-659">Row Resynchronization Notification</span><span class="sxs-lookup"><span data-stu-id="53d1c-659">Row Resynchronization Notification</span></span></p></td>
<td><p><span data-ttu-id="53d1c-660">DBPROP_NOTIFYROWRESYNCH</span><span class="sxs-lookup"><span data-stu-id="53d1c-660">DBPROP_NOTIFYROWRESYNCH</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53d1c-661">Row Threading Model</span><span class="sxs-lookup"><span data-stu-id="53d1c-661">Row Threading Model</span></span></p></td>
<td><p><span data-ttu-id="53d1c-662">DBPROP_ROWTHREADMODEL</span><span class="sxs-lookup"><span data-stu-id="53d1c-662">DBPROP_ROWTHREADMODEL</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53d1c-663">Row Undo Change Notification</span><span class="sxs-lookup"><span data-stu-id="53d1c-663">Row Undo Change Notification</span></span></p></td>
<td><p><span data-ttu-id="53d1c-664">DBPROP_NOTIFYROWUNDOCHANGE</span><span class="sxs-lookup"><span data-stu-id="53d1c-664">DBPROP_NOTIFYROWUNDOCHANGE</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53d1c-665">Row Undo Delete Notification</span><span class="sxs-lookup"><span data-stu-id="53d1c-665">Row Undo Delete Notification</span></span></p></td>
<td><p><span data-ttu-id="53d1c-666">DBPROP_NOTIFYROWUNDODELETE</span><span class="sxs-lookup"><span data-stu-id="53d1c-666">DBPROP_NOTIFYROWUNDODELETE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53d1c-667">Row Undo Insert Notification</span><span class="sxs-lookup"><span data-stu-id="53d1c-667">Row Undo Insert Notification</span></span></p></td>
<td><p><span data-ttu-id="53d1c-668">DBPROP_NOTIFYROWUNDOINSERT</span><span class="sxs-lookup"><span data-stu-id="53d1c-668">DBPROP_NOTIFYROWUNDOINSERT</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53d1c-669">Row Update Notification</span><span class="sxs-lookup"><span data-stu-id="53d1c-669">Row Update Notification</span></span></p></td>
<td><p><span data-ttu-id="53d1c-670">DBPROP_NOTIFYROWUPDATE</span><span class="sxs-lookup"><span data-stu-id="53d1c-670">DBPROP_NOTIFYROWUPDATE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53d1c-671">Rowset Fetch Position Change Notification</span><span class="sxs-lookup"><span data-stu-id="53d1c-671">Rowset Fetch Position Change Notification</span></span></p></td>
<td><p><span data-ttu-id="53d1c-672">DBPROP_NOTIFYROWSETFETCHPOSITIONCHANGE</span><span class="sxs-lookup"><span data-stu-id="53d1c-672">DBPROP_NOTIFYROWSETFETCHPOSITIONCHANGE</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53d1c-673">Rowset Release Notification</span><span class="sxs-lookup"><span data-stu-id="53d1c-673">Rowset Release Notification</span></span></p></td>
<td><p><span data-ttu-id="53d1c-674">DBPROP_NOTIFYROWSETRELEASE</span><span class="sxs-lookup"><span data-stu-id="53d1c-674">DBPROP_NOTIFYROWSETRELEASE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53d1c-675">Scroll Backwards</span><span class="sxs-lookup"><span data-stu-id="53d1c-675">Scroll Backwards</span></span></p></td>
<td><p><span data-ttu-id="53d1c-676">DBPROP_CANSCROLLBACKWARDS</span><span class="sxs-lookup"><span data-stu-id="53d1c-676">DBPROP_CANSCROLLBACKWARDS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53d1c-677">Server Data on Insert</span><span class="sxs-lookup"><span data-stu-id="53d1c-677">Server Data on Insert</span></span></p></td>
<td><p><span data-ttu-id="53d1c-678">DBPROP_SERVERDATAONINSERT</span><span class="sxs-lookup"><span data-stu-id="53d1c-678">DBPROP_SERVERDATAONINSERT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53d1c-679">Skip Deleted Bookmarks</span><span class="sxs-lookup"><span data-stu-id="53d1c-679">Skip Deleted Bookmarks</span></span></p></td>
<td><p><span data-ttu-id="53d1c-680">DBPROP_BOOKMARKSKIP</span><span class="sxs-lookup"><span data-stu-id="53d1c-680">DBPROP_BOOKMARKSKIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53d1c-681">Strong Row Identity</span><span class="sxs-lookup"><span data-stu-id="53d1c-681">Strong Row Identity</span></span></p></td>
<td><p><span data-ttu-id="53d1c-682">DBPROP_STRONGIDENTITY</span><span class="sxs-lookup"><span data-stu-id="53d1c-682">DBPROP_STRONGIDENTITY</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53d1c-683">Updatability</span><span class="sxs-lookup"><span data-stu-id="53d1c-683">Updatability</span></span></p></td>
<td><p><span data-ttu-id="53d1c-684">DBPROP_UPDATABILITY</span><span class="sxs-lookup"><span data-stu-id="53d1c-684">DBPROP_UPDATABILITY</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53d1c-685">Use Bookmarks</span><span class="sxs-lookup"><span data-stu-id="53d1c-685">Use Bookmarks</span></span></p></td>
<td><p><span data-ttu-id="53d1c-686">DBPROP_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="53d1c-686">DBPROP_BOOKMARKS</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="see-also"></a><span data-ttu-id="53d1c-687">另请参阅</span><span class="sxs-lookup"><span data-stu-id="53d1c-687">See also</span></span>

<span data-ttu-id="53d1c-688">有关具体的实现详细信息以及有关 OLE DB Provider for Microsoft Jet 的功能信息，请参阅 OLE DB Provider for Microsoft Jet MDAC SDK 中的文档。</span><span class="sxs-lookup"><span data-stu-id="53d1c-688">For specific implementation details and functional information about the OLE DB Provider for Microsoft Jet, consult the OLE DB Provider for Microsoft Jet documentation in the MDAC SDK.</span></span>

