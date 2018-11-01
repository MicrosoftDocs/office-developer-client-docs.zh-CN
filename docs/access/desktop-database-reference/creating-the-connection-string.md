---
title: 创建连接字符串
TOCTitle: Creating the Connection String
ms:assetid: 0d34b1c6-bf2e-1299-9778-573ccd2da1c7
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248853(v=office.15)
ms:contentKeyID: 48543214
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: bd4bafd29195e2ff9898973351cd7d13262c3cec
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25869678"
---
# <a name="creating-the-connection-string"></a>创建连接字符串


**适用于**： Access 2013、 Office 2013

在连接字符串中，ADO 直接支持五个参数。其他参数将传递给 *Provider* 参数所命名的提供程序，ADO 不对其进行任何处理。

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>参数</p></th>
<th><p>说明</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><em>Provider</em></p></td>
<td><p>指定用于连接的提供程序的名称。</p></td>
</tr>
<tr class="even">
<td><p><em>文件名</em></p></td>
<td><p>指定包含预置连接信息的、特定于提供程序的文件（例如，持久化的数据源对象）的名称。</p></td>
</tr>
<tr class="odd">
<td><p><em>URL</em></p></td>
<td><p>将连接字符串指定为标识资源的绝对 URL，例如，文件或目录。</p></td>
</tr>
<tr class="even">
<td><p><em>Remote Provider</em></p></td>
<td><p>指定打开客户端连接时使用的提供程序的名称（仅限于远程数据服务）。</p></td>
</tr>
<tr class="odd">
<td><p><em>Remote Server</em></p></td>
<td><p>指定打开客户端连接时使用的服务器的路径名称（仅限于远程数据服务）。</p></td>
</tr>
</tbody>
</table>



> [!NOTE]
> 在以下示例和整个《ADO 程序员指南》中，将以用户 ID“MyId”和密码“123aBc”来向服务器进行身份验证。应当用您的服务器的有效登录凭据来替换这些值，并用您的服务器的名称替换“MySqlServer”。

第 1 章中 HelloData 应用程序使用以下连接字符串：

```vb 
 
m_sConnStr = "Provider='SQLOLEDB';Data Source='MySqlServer';" & _ 
 "Initial Catalog='Northwind';Integrated Security='SSPI';" 
```

此连接字符串中提供的唯一 ADO 参数是"Provider=SQLOLEDB"，它指示 Microsoft OLE DB Provider for SQL Server。 对于连接字符串中传递的其他有效参数，可以参考各个提供程序的文档来确定。 根据 OLE DB Provider for SQL Server 文档，您可以*Initial Catalog*参数的*数据源*参数和"数据库"替换"服务器"。 因此，以下连接字符串可以产生与第一个相同的结果：

```vb 
 
m_sConnStr = "Provider='SQLOLEDB';Server='MySqlServer';" & _ 
 "Database='Northwind';Integrated Security='SSPI';" 
```

若要打开连接，只需在 **Connection** 对象的 **Open** 方法中将连接字符串作为第一个参数传递：

```vb 
 
objConn.Open m_sConnStr 
```

还可以在打开连接之前通过设置 **Connection** 对象的属性来提供更多信息。例如，通过使用以下代码，可以获得与上述连接字符串相同的效果：

```vb 
 
With objConn 
 .Provider = "SQLOLEDB" 
 .DefaultDatabase = "Northwind" 
 .Properties("Data Source") = "MySqlServer" 
 .Properties("Integrated Security") = "SSPI" 
 .Open 
End With 
```

