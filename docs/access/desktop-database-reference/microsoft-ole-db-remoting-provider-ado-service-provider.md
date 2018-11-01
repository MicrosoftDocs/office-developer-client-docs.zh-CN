---
title: Microsoft OLE DB Remoting Provider（ADO 服务提供程序）
TOCTitle: Microsoft OLE DB Remoting Provider (ADO Service Provider)
ms:assetid: f39bd83d-8c2c-302e-16e3-0fae50f89fbc
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250238(v=office.15)
ms:contentKeyID: 48548673
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: c8e9e6e655198cba28ece0951414af85ec14f26f
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25878057"
---
# <a name="microsoft-ole-db-remoting-provider-ado-service-provider"></a><span data-ttu-id="98268-102">Microsoft OLE DB Remoting Provider（ADO 服务提供程序）</span><span class="sxs-lookup"><span data-stu-id="98268-102">Microsoft OLE DB Remoting Provider (ADO Service Provider)</span></span>

<span data-ttu-id="98268-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="98268-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="98268-p101">Microsoft OLE DB Remoting Provider 允许客户端计算机的本地用户调用远程计算机上的数据提供程序。您可以像远程计算机的本地用户一样为远程计算机指定数据提供程序参数，然后指定 Remoting Provider 所用的参数以访问远程计算机。于是，您就可以像远程计算机的本地用户一样访问远程计算机。</span><span class="sxs-lookup"><span data-stu-id="98268-p101">The Microsoft OLE DB Remoting Provider enables a local user on a client machine to invoke data providers on a remote machine. Specify the data provider parameters for the remote machine as you would if you were a local user on the remote machine. Then specify the parameters used by the Remoting Provider to access the remote machine. The resulting effect is that you will access the remote machine as if you were a local user.</span></span>

## <a name="provider-keyword"></a><span data-ttu-id="98268-108">提供程序关键字</span><span class="sxs-lookup"><span data-stu-id="98268-108">Provider Keyword</span></span>

<span data-ttu-id="98268-p102">要调用 OLE DB Remoting Provider，请在连接字符串中指定以下关键字和值（请注意提供程序名称中的空格）。</span><span class="sxs-lookup"><span data-stu-id="98268-p102">To invoke the OLE DB Remoting Provider, specify the following keyword and value in the connection string. (Note the blank space in the provider name.)</span></span>

```sql 
 
"Provider=MS Remote" 
```

## <a name="additional-keywords"></a><span data-ttu-id="98268-111">附加关键字</span><span class="sxs-lookup"><span data-stu-id="98268-111">Additional Keywords</span></span>

<span data-ttu-id="98268-112">调用此服务提供程序时，会涉及到以下附加的关键字。</span><span class="sxs-lookup"><span data-stu-id="98268-112">When this service provider is invoked, the following additional keywords are relevant.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="98268-113">关键字</span><span class="sxs-lookup"><span data-stu-id="98268-113">Keyword</span></span></p></th>
<th><p><span data-ttu-id="98268-114">说明</span><span class="sxs-lookup"><span data-stu-id="98268-114">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="98268-115"><strong>Data Source</strong></span><span class="sxs-lookup"><span data-stu-id="98268-115"><strong>Data Source</strong></span></span></p></td>
<td><p><span data-ttu-id="98268-116">指定远程数据源的名称。</span><span class="sxs-lookup"><span data-stu-id="98268-116">Specifies the name of the remote data source.</span></span> <span data-ttu-id="98268-117">它将传递到 OLE DB Remoting Provider 进行处理。</span><span class="sxs-lookup"><span data-stu-id="98268-117">It is passed to the OLE DB Remoting Provider for processing.</span></span> <span data-ttu-id="98268-118">此关键字与 <a href="datacontrol-object-rds.md">RDS.DataControl</a> 对象的 <a href="connect-property-rds.md">Connect</a> 属性等效。</span><span class="sxs-lookup"><span data-stu-id="98268-118">This keyword is equivalent to the <a href="datacontrol-object-rds.md">RDS.DataControl</a> object's <a href="connect-property-rds.md">Connect</a> property.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="dynamic-properties"></a><span data-ttu-id="98268-119">动态属性</span><span class="sxs-lookup"><span data-stu-id="98268-119">Dynamic Properties</span></span>

<span data-ttu-id="98268-120">调用此服务提供程序时，会将以下动态属性添加到 [Connection](connection-object-ado.md) 对象的 [Properties](properties-collection-ado.md) 集合中。</span><span class="sxs-lookup"><span data-stu-id="98268-120">When this service provider is invoked, the following dynamic properties are added to the [Connection](connection-object-ado.md) object's [Properties](properties-collection-ado.md) collection.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="98268-121">动态属性名称</span><span class="sxs-lookup"><span data-stu-id="98268-121">Dynamic Property Name</span></span></p></th>
<th><p><span data-ttu-id="98268-122">说明</span><span class="sxs-lookup"><span data-stu-id="98268-122">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="98268-123"><strong>DFMode</strong></span><span class="sxs-lookup"><span data-stu-id="98268-123"><strong>DFMode</strong></span></span></p></td>
<td><p><span data-ttu-id="98268-124">指示 DataFactory 模式。</span><span class="sxs-lookup"><span data-stu-id="98268-124">Indicates the DataFactory Mode.</span></span> <span data-ttu-id="98268-125">一个字符串，指定所需的版本的<a href="datafactory-object-rdsserver.md">DataFactory</a>对象的服务器上。</span><span class="sxs-lookup"><span data-stu-id="98268-125">A string that specifies the desired version of the <a href="datafactory-object-rdsserver.md">DataFactory</a> object on the server.</span></span> <span data-ttu-id="98268-126">打开连接请求<strong>DataFactory</strong>的特定版本之前设置该属性。</span><span class="sxs-lookup"><span data-stu-id="98268-126">Set this property before opening a connection to request a particular version of the <strong>DataFactory</strong>.</span></span> <span data-ttu-id="98268-127">如果请求的版本不可用，尝试将进行使用以前的版本。</span><span class="sxs-lookup"><span data-stu-id="98268-127">If the requested version is not available, an attempt will be made to use the preceding version.</span></span> <span data-ttu-id="98268-128">如果没有，则任何以前的版本，则会发生错误。</span><span class="sxs-lookup"><span data-stu-id="98268-128">If there is no preceding version, an error will occur.</span></span> <span data-ttu-id="98268-129">如果<strong>DFMode</strong>小于的可用版本，将发生错误。</span><span class="sxs-lookup"><span data-stu-id="98268-129">If <strong>DFMode</strong> is less than the available version, an error will occur.</span></span> <span data-ttu-id="98268-130">建立连接之后，此属性是只读的。</span><span class="sxs-lookup"><span data-stu-id="98268-130">This property is read-only after a connection is made.</span></span> <span data-ttu-id="98268-131">可为以下有效的字符串值之一：</span><span class="sxs-lookup"><span data-stu-id="98268-131">Can be one of the following valid string values:</span></span></p>
<p></p>
<ul>
<li><p><span data-ttu-id="98268-132">&quot;25&quot; — 版本 2.5 （默认值）</span><span class="sxs-lookup"><span data-stu-id="98268-132">&quot;25&quot; — Version 2.5 (Default)</span></span></p></li>
<li><p><span data-ttu-id="98268-133">&quot;21&quot; — 2.1 版</span><span class="sxs-lookup"><span data-stu-id="98268-133">&quot;21&quot; — Version 2.1</span></span></p></li>
<li><p><span data-ttu-id="98268-134">&quot;20&quot; — 2.0 版</span><span class="sxs-lookup"><span data-stu-id="98268-134">&quot;20&quot; — Version 2.0</span></span></p></li>
<li><p><span data-ttu-id="98268-135">&quot;15&quot; — 版本 1.5</span><span class="sxs-lookup"><span data-stu-id="98268-135">&quot;15&quot; — Version 1.5</span></span></p></li>
</ul>
<p></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="98268-136"><strong>Command Properties</strong></span><span class="sxs-lookup"><span data-stu-id="98268-136"><strong>Command Properties</strong></span></span></p></td>
<td><p><span data-ttu-id="98268-p105">指示将被添加到 MS Remote 提供程序发送到服务器的命令（行集）属性字符串中的值。此字符串的默认值为 vt_empty。</span><span class="sxs-lookup"><span data-stu-id="98268-p105">Indicates values that will be added to the string of command (rowset) properties sent to the server by the MS Remote provider. The default value for this string is vt_empty.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="98268-139"><strong>Current DFMode</strong></span><span class="sxs-lookup"><span data-stu-id="98268-139"><strong>Current DFMode</strong></span></span></p></td>
<td><p><span data-ttu-id="98268-140">指示<strong>DataFactory</strong>的服务器上实际的版本号。</span><span class="sxs-lookup"><span data-stu-id="98268-140">Indicates the actual version number of the <strong>DataFactory</strong> on the server.</span></span> <span data-ttu-id="98268-141">检查此属性，以了解是否请求<strong>DFMode</strong>属性中的版本。</span><span class="sxs-lookup"><span data-stu-id="98268-141">Check this property to see if the version requested in the <strong>DFMode</strong> property was honored.</span></span> <span data-ttu-id="98268-142">可以为以下有效的长整型值之一：</span><span class="sxs-lookup"><span data-stu-id="98268-142">Can be one of the following valid Long integer values:</span></span></p>
<p></p>
<ul>
<li><p><span data-ttu-id="98268-143">25 — 版本 2.5（默认值）</span><span class="sxs-lookup"><span data-stu-id="98268-143">25 — Version 2.5 (Default)</span></span></p></li>
<li><p><span data-ttu-id="98268-144">21 — 版本 2.1</span><span class="sxs-lookup"><span data-stu-id="98268-144">21 — Version 2.1</span></span></p></li>
<li><p><span data-ttu-id="98268-145">20 — 版本 2.0</span><span class="sxs-lookup"><span data-stu-id="98268-145">20 — Version 2.0</span></span></p></li>
<li><p><span data-ttu-id="98268-146">15 — 版本 1.5</span><span class="sxs-lookup"><span data-stu-id="98268-146">15 — Version 1.5</span></span></p></li>
</ul>
<p></p>
<p><span data-ttu-id="98268-147">添加&quot;DFMode = 20;&quot;对您的连接字符串时使用<strong>MSRemote</strong>提供程序可以提高服务器的性能数据更新时。</span><span class="sxs-lookup"><span data-stu-id="98268-147">Adding &quot;DFMode=20;&quot; to your connection string when using the <strong>MSRemote</strong> provider can improve your server's performance when updating data.</span></span> <span data-ttu-id="98268-148">通过使用此设置，服务器上的 <strong>RDSServer.DataFactory</strong> 对象可使用资源占用量较少的模式。</span><span class="sxs-lookup"><span data-stu-id="98268-148">With this setting, the <strong>RDSServer.DataFactory</strong> object on the server uses a less resource-intensive mode.</span></span> <span data-ttu-id="98268-149">但是，以下功能在此配置中不可用：</span><span class="sxs-lookup"><span data-stu-id="98268-149">However, the following features are not available in this configuration:</span></span></p>
<p></p>
<ul>
<li><p><span data-ttu-id="98268-150">使用参数化的查询。</span><span class="sxs-lookup"><span data-stu-id="98268-150">Using parameterized queries.</span></span></p></li>
<li><p><span data-ttu-id="98268-151">调用 <strong>Execute</strong> 方法之前获取参数信息或列信息。</span><span class="sxs-lookup"><span data-stu-id="98268-151">Getting parameter or column information before calling the <strong>Execute</strong> method.</span></span></p></li>
<li><p><span data-ttu-id="98268-152">将 <strong>Transact Updates</strong> 设置为 <strong>True</strong> 。</span><span class="sxs-lookup"><span data-stu-id="98268-152">Setting <strong>Transact Updates</strong> to <strong>True</strong>.</span></span></p></li>
<li><p><span data-ttu-id="98268-153">获取行状态。</span><span class="sxs-lookup"><span data-stu-id="98268-153">Getting row status.</span></span></p></li>
<li><p><span data-ttu-id="98268-154">调用 <strong>Resync</strong> 方法。</span><span class="sxs-lookup"><span data-stu-id="98268-154">Calling the <strong>Resync</strong> method.</span></span></p></li>
<li><p><span data-ttu-id="98268-155">通过 <strong>Update Resync</strong> 属性刷新（显式或自动）。</span><span class="sxs-lookup"><span data-stu-id="98268-155">Refreshing (explicitly or automatically) via the <strong>Update Resync</strong> property.</span></span></p></li>
<li><p><span data-ttu-id="98268-156">设置 <strong>Command</strong> 或 <strong>Recordset</strong> 属性。</span><span class="sxs-lookup"><span data-stu-id="98268-156">Setting <strong>Command</strong> or <strong>Recordset</strong> properties.</span></span></p></li>
<li><p><span data-ttu-id="98268-157">使用 <strong>adCmdTableDirect</strong> 。</span><span class="sxs-lookup"><span data-stu-id="98268-157">Using <strong>adCmdTableDirect</strong>.</span></span></p></li>
</ul>
<p></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="98268-158"><strong>处理程序</strong></span><span class="sxs-lookup"><span data-stu-id="98268-158"><strong>Handler</strong></span></span></p></td>
<td><p><span data-ttu-id="98268-159">指示扩展<a href="datafactory-object-rdsserver.md">RDSServer.DataFactory</a>和使用的处理<em>，</em>所有以逗号分隔的任何参数的功能的服务器端自定义程序 （或处理） 的名称 (&quot;，&quot;)。</span><span class="sxs-lookup"><span data-stu-id="98268-159">Indicates the name of a server-side customization program (or handler) that extends the functionality of the <a href="datafactory-object-rdsserver.md">RDSServer.DataFactory</a>, and any parameters used by the handler<em>,</em> all separated by commas (&quot;,&quot;).</span></span> <span data-ttu-id="98268-160"><strong>字符串型</strong> 值。</span><span class="sxs-lookup"><span data-stu-id="98268-160">A <strong>String</strong> value.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="98268-161"><strong>Internet Timeout</strong></span><span class="sxs-lookup"><span data-stu-id="98268-161"><strong>Internet Timeout</strong></span></span></p></td>
<td><p><span data-ttu-id="98268-p109">指示等待请求往返服务器所用的最大毫秒数（默认值为 5 分钟）。</span><span class="sxs-lookup"><span data-stu-id="98268-p109">Indicates the maximum number of milliseconds to wait for a request to travel to and from the server. (The default is 5 minutes.)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="98268-164"><strong>Remote Provider</strong></span><span class="sxs-lookup"><span data-stu-id="98268-164"><strong>Remote Provider</strong></span></span></p></td>
<td><p><span data-ttu-id="98268-165">指示要在远程服务器上使用的数据提供程序的名称。</span><span class="sxs-lookup"><span data-stu-id="98268-165">Indicates the name of the data provider to be used on the remote server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="98268-166"><strong>Remote Server</strong></span><span class="sxs-lookup"><span data-stu-id="98268-166"><strong>Remote Server</strong></span></span></p></td>
<td><p><span data-ttu-id="98268-p110">指示此连接所使用的服务器名称和通信协议。此属性等效于 <a href="datacontrol-object-rds.md">RDS.DataControl</a> 对象的 <a href="server-property-rds.md">Server</a> 属性。</span><span class="sxs-lookup"><span data-stu-id="98268-p110">Indicates the server name and communication protocol to be used by this connection. This property is equivalent to the <a href="datacontrol-object-rds.md">RDS.DataControl</a> object <a href="server-property-rds.md">Server</a> property.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="98268-169"><strong>Transact Updates</strong></span><span class="sxs-lookup"><span data-stu-id="98268-169"><strong>Transact Updates</strong></span></span></p></td>
<td><p><span data-ttu-id="98268-p111">设置为 True 时，此值指示在服务器上执行 <a href="updatebatch-method-ado.md">UpdateBatch</a> 时，该操作将在事务处理内部完成。此 Boolean 动态属性的默认值为 False。</span><span class="sxs-lookup"><span data-stu-id="98268-p111">When set to True, this value indicates that when <a href="updatebatch-method-ado.md">UpdateBatch</a> is performed on the server, it will be done inside a transaction. The default value for this Boolean dynamic property is False.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="98268-p112">您还可以设置可写入的动态属性，方法是在连接字符串中将动态属性的名称指定为关键字。例如，通过指定以下代码，可以将 **Internet Timeout** 动态属性设置为五秒：</span><span class="sxs-lookup"><span data-stu-id="98268-p112">You may also set writable dynamic properties by specifying their names as keywords in the connection string. For example, set the **Internet Timeout** dynamic property to five seconds by specifying:</span></span>

```sql 
 
Dim cn as New ADODB.Connection 
cn.Open "Provider=MS Remote;Internet Timeout=5000" 
```

<span data-ttu-id="98268-p113">您还可以设置或检索动态属性，方法是将动态属性的名称指定为 **Properties** 属性的索引。例如，可以像下面一样，获取并输出 **Internet Timeout** 动态属性的当前值，随后设置一个新值：</span><span class="sxs-lookup"><span data-stu-id="98268-p113">You may also set or retrieve a dynamic property by specifying its name as the index to the **Properties** property. For example, get and print the current value of the **Internet Timeout** dynamic property, and then set a new value, like this:</span></span>

```sql 
 
Debug.Print cn.Properties("Internet Timeout") 
cn.Properties("Internet Timeout") = 5000 
```

## <a name="remarks"></a><span data-ttu-id="98268-176">备注</span><span class="sxs-lookup"><span data-stu-id="98268-176">Remarks</span></span>

<span data-ttu-id="98268-177">在 ADO 2.0 中，OLE DB Remoting Provider 只无法[Recordset](recordset-object-ado.md)对象的**Open**方法的*ActiveConnection*参数中指定。</span><span class="sxs-lookup"><span data-stu-id="98268-177">In ADO 2.0, the OLE DB Remoting Provider could only be specified in the *ActiveConnection* parameter of the [Recordset](recordset-object-ado.md) object **Open** method.</span></span> <span data-ttu-id="98268-178">从开始 ADO 2.1，提供程序可能还指定[Connection](connection-object-ado.md)对象的**Open**方法的*ConnectionString*参数中。</span><span class="sxs-lookup"><span data-stu-id="98268-178">Starting with ADO 2.1, the provider may also be specified in the *ConnectionString* parameter of the [Connection](connection-object-ado.md) object **Open** method.</span></span>

<span data-ttu-id="98268-179">与 **RDS.DataControl** 对象的 [SQL](https://msdn.microsoft.com/library/jj248989\(v=office.15\)) 属性等效的属性不可用。</span><span class="sxs-lookup"><span data-stu-id="98268-179">The equivalent of the **RDS.DataControl** object [SQL](https://msdn.microsoft.com/library/jj248989\(v=office.15\)) property is not available.</span></span> <span data-ttu-id="98268-180">而使用[Recordset](recordset-object-ado.md)对象的**Open**方法的*Source*参数之后。</span><span class="sxs-lookup"><span data-stu-id="98268-180">The [Recordset](recordset-object-ado.md) object **Open** method *Source* argument is used instead.</span></span>

<span data-ttu-id="98268-181">通过指定"...;Remote Provider=MS Remote;..."，将创建包含一个四层方案。大于三层的方案均未经过测试，应该不会有此方面的需要。</span><span class="sxs-lookup"><span data-stu-id="98268-181">Specifying "...;Remote Provider=MS Remote;..." would create a four-tier scenario.Scenarios beyond three tiers have not been tested and should not be needed.</span></span>

## <a name="example"></a><span data-ttu-id="98268-182">示例</span><span class="sxs-lookup"><span data-stu-id="98268-182">Example</span></span>

<span data-ttu-id="98268-p116">本示例对服务器 *YourServer* 上的 **pubs** 数据库的 **authors**（作者）表执行查询。远程数据源和远程服务器的名称是在 [Connection](connection-object-ado.md) 对象的 [Open](open-method-ado-connection.md) 方法中提供的，而 SQL 查询是在 [Recordset](recordset-object-ado.md) 对象的 [Open](open-method-ado-recordset.md) 方法中指定的。**Recordset** 对象将被返回，将对其进行编辑并用于更新数据源。</span><span class="sxs-lookup"><span data-stu-id="98268-p116">This example performs a query on the **authors** table of the **pubs** database on a server named, *YourServer*. The names of the remote data source and remote server are provided in the [Connection](connection-object-ado.md) object [Open](open-method-ado-connection.md) method, and the SQL query is specified in the [Recordset](recordset-object-ado.md) object [Open](open-method-ado-recordset.md) method. A **Recordset** object is returned, edited, and used to update the data source.</span></span>

```vb 
 
Dim rs as New ADODB.Recordset 
Dim cn as New ADODB.Connection 
cn.Open  "Provider=MS Remote;Data Source=pubs;" & _ 
         "Remote Server=https://YourServer" 
rs.Open "SELECT * FROM authors", cn 
...                'Edit the recordset 
rs.UpdateBatch     'Equivalent of RDS SubmitChanges 
... 
```

