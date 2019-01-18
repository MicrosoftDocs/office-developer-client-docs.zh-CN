---
title: Microsoft OLE DB Remoting Provider（ADO 服务提供程序）
TOCTitle: Microsoft OLE DB Remoting Provider (ADO Service Provider)
ms:assetid: f39bd83d-8c2c-302e-16e3-0fae50f89fbc
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250238(v=office.15)
ms:contentKeyID: 48548673
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 54ea659aa5392dd4404ffb591eba06f1f9c2910b
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28701898"
---
# <a name="microsoft-ole-db-remoting-provider-ado-service-provider"></a>Microsoft OLE DB Remoting Provider（ADO 服务提供程序）

**适用于**： Access 2013、 Office 2013

Microsoft OLE DB Remoting Provider 允许客户端计算机的本地用户调用远程计算机上的数据提供程序。您可以像远程计算机的本地用户一样为远程计算机指定数据提供程序参数，然后指定 Remoting Provider 所用的参数以访问远程计算机。于是，您就可以像远程计算机的本地用户一样访问远程计算机。

## <a name="provider-keyword"></a>提供程序关键字

要调用 OLE DB Remoting Provider，请在连接字符串中指定以下关键字和值（请注意提供程序名称中的空格）。

```sql 
 
"Provider=MS Remote" 
```

## <a name="additional-keywords"></a>附加关键字

调用此服务提供程序时，会涉及到以下附加的关键字。

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>关键字</p></th>
<th><p>说明</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Data Source</strong></p></td>
<td><p>指定远程数据源的名称。 它将传递到 OLE DB Remoting Provider 进行处理。 此关键字与 <a href="datacontrol-object-rds.md">RDS.DataControl</a> 对象的 <a href="connect-property-rds.md">Connect</a> 属性等效。</p></td>
</tr>
</tbody>
</table>


## <a name="dynamic-properties"></a>动态属性

调用此服务提供程序时，会将以下动态属性添加到 [Connection](connection-object-ado.md) 对象的 [Properties](properties-collection-ado.md) 集合中。

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>动态属性名称</p></th>
<th><p>说明</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>DFMode</strong></p></td>
<td><p>指示 DataFactory 模式。 一个字符串，指定所需的版本的<a href="datafactory-object-rdsserver.md">DataFactory</a>对象的服务器上。 打开连接请求<strong>DataFactory</strong>的特定版本之前设置该属性。 如果请求的版本不可用，尝试将进行使用以前的版本。 如果没有，则任何以前的版本，则会发生错误。 如果<strong>DFMode</strong>小于的可用版本，将发生错误。 建立连接之后，此属性是只读的。 可为以下有效的字符串值之一：</p>
<p></p>
<ul>
<li><p>&quot;25&quot; — 版本 2.5 （默认值）</p></li>
<li><p>&quot;21&quot; — 2.1 版</p></li>
<li><p>&quot;20&quot; — 2.0 版</p></li>
<li><p>&quot;15&quot; — 版本 1.5</p></li>
</ul>
<p></p></td>
</tr>
<tr class="even">
<td><p><strong>Command Properties</strong></p></td>
<td><p>指示将被添加到 MS Remote 提供程序发送到服务器的命令（行集）属性字符串中的值。此字符串的默认值为 vt_empty。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Current DFMode</strong></p></td>
<td><p>指示<strong>DataFactory</strong>的服务器上实际的版本号。 检查此属性，以了解是否请求<strong>DFMode</strong>属性中的版本。 可以为以下有效的长整型值之一：</p>
<p></p>
<ul>
<li><p>25 — 版本 2.5（默认值）</p></li>
<li><p>21 — 版本 2.1</p></li>
<li><p>20 — 版本 2.0</p></li>
<li><p>15 — 版本 1.5</p></li>
</ul>
<p></p>
<p>添加&quot;DFMode = 20;&quot;对您的连接字符串时使用<strong>MSRemote</strong>提供程序可以提高服务器的性能数据更新时。 通过使用此设置，服务器上的 <strong>RDSServer.DataFactory</strong> 对象可使用资源占用量较少的模式。 但是，以下功能在此配置中不可用：</p>
<p></p>
<ul>
<li><p>使用参数化的查询。</p></li>
<li><p>调用 <strong>Execute</strong> 方法之前获取参数信息或列信息。</p></li>
<li><p>将 <strong>Transact Updates</strong> 设置为 <strong>True</strong> 。</p></li>
<li><p>获取行状态。</p></li>
<li><p>调用 <strong>Resync</strong> 方法。</p></li>
<li><p>通过 <strong>Update Resync</strong> 属性刷新（显式或自动）。</p></li>
<li><p>设置 <strong>Command</strong> 或 <strong>Recordset</strong> 属性。</p></li>
<li><p>使用 <strong>adCmdTableDirect</strong> 。</p></li>
</ul>
<p></p></td>
</tr>
<tr class="even">
<td><p><strong>处理程序</strong></p></td>
<td><p>指示扩展<a href="datafactory-object-rdsserver.md">RDSServer.DataFactory</a>和使用的处理<em>，</em>所有以逗号分隔的任何参数的功能的服务器端自定义程序 （或处理） 的名称 (&quot;，&quot;)。 <strong>字符串型</strong> 值。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Internet Timeout</strong></p></td>
<td><p>指示等待请求往返服务器所用的最大毫秒数（默认值为 5 分钟）。</p></td>
</tr>
<tr class="even">
<td><p><strong>Remote Provider</strong></p></td>
<td><p>指示要在远程服务器上使用的数据提供程序的名称。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Remote Server</strong></p></td>
<td><p>指示此连接所使用的服务器名称和通信协议。此属性等效于 <a href="datacontrol-object-rds.md">RDS.DataControl</a> 对象的 <a href="server-property-rds.md">Server</a> 属性。</p></td>
</tr>
<tr class="even">
<td><p><strong>Transact Updates</strong></p></td>
<td><p>设置为 True 时，此值指示在服务器上执行 <a href="updatebatch-method-ado.md">UpdateBatch</a> 时，该操作将在事务处理内部完成。此 Boolean 动态属性的默认值为 False。</p></td>
</tr>
</tbody>
</table>


您还可以设置可写入的动态属性，方法是在连接字符串中将动态属性的名称指定为关键字。例如，通过指定以下代码，可以将 **Internet Timeout** 动态属性设置为五秒：

```sql 
 
Dim cn as New ADODB.Connection 
cn.Open "Provider=MS Remote;Internet Timeout=5000" 
```

您还可以设置或检索动态属性，方法是将动态属性的名称指定为 **Properties** 属性的索引。例如，可以像下面一样，获取并输出 **Internet Timeout** 动态属性的当前值，随后设置一个新值：

```sql 
 
Debug.Print cn.Properties("Internet Timeout") 
cn.Properties("Internet Timeout") = 5000 
```

## <a name="remarks"></a>备注

在 ADO 2.0 中，OLE DB Remoting Provider 只无法[Recordset](recordset-object-ado.md)对象的**Open**方法的*ActiveConnection*参数中指定。 从开始 ADO 2.1，提供程序可能还指定[Connection](connection-object-ado.md)对象的**Open**方法的*ConnectionString*参数中。

与 **RDS.DataControl** 对象的 [SQL](https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/sql-property-ado) 属性等效的属性不可用。 而使用[Recordset](recordset-object-ado.md)对象的**Open**方法的*Source*参数之后。

通过指定"...;Remote Provider=MS Remote;..."，将创建包含一个四层方案。大于三层的方案均未经过测试，应该不会有此方面的需要。

## <a name="example"></a>示例

本示例对服务器 *YourServer* 上的 **pubs** 数据库的 **authors**（作者）表执行查询。远程数据源和远程服务器的名称是在 [Connection](connection-object-ado.md) 对象的 [Open](open-method-ado-connection.md) 方法中提供的，而 SQL 查询是在 [Recordset](recordset-object-ado.md) 对象的 [Open](open-method-ado-recordset.md) 方法中指定的。**Recordset** 对象将被返回，将对其进行编辑并用于更新数据源。

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

