---
title: 创建连接字符串
TOCTitle: Creating the connection string
ms:assetid: 0d34b1c6-bf2e-1299-9778-573ccd2da1c7
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248853(v=office.15)
ms:contentKeyID: 48543214
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: f43207edec0c0acb58c66318e5dc7668a28ea595
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32295325"
---
# <a name="creating-the-connection-string"></a><span data-ttu-id="ef3a9-102">创建连接字符串</span><span class="sxs-lookup"><span data-stu-id="ef3a9-102">Creating the connection string</span></span>

<span data-ttu-id="ef3a9-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="ef3a9-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="ef3a9-p101">在连接字符串中，ADO 直接支持五个参数。其他参数将传递给 *Provider* 参数所命名的提供程序，ADO 不对其进行任何处理。</span><span class="sxs-lookup"><span data-stu-id="ef3a9-p101">ADO directly supports five arguments in a connection string. Other arguments are passed to the provider that is named in the *Provider* argument without any processing by ADO.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="ef3a9-106">参数</span><span class="sxs-lookup"><span data-stu-id="ef3a9-106">Argument</span></span></p></th>
<th><p><span data-ttu-id="ef3a9-107">说明</span><span class="sxs-lookup"><span data-stu-id="ef3a9-107">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ef3a9-108"><em>Provider</em></span><span class="sxs-lookup"><span data-stu-id="ef3a9-108"><em>Provider</em></span></span></p></td>
<td><p><span data-ttu-id="ef3a9-109">指定用于连接的提供程序的名称。</span><span class="sxs-lookup"><span data-stu-id="ef3a9-109">Specifies the name of a provider to use for the connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ef3a9-110"><em>File Name</em></span><span class="sxs-lookup"><span data-stu-id="ef3a9-110"><em>File Name</em></span></span></p></td>
<td><p><span data-ttu-id="ef3a9-111">指定包含预置连接信息的、特定于提供程序的文件（例如，持久化的数据源对象）的名称。</span><span class="sxs-lookup"><span data-stu-id="ef3a9-111">Specifies the name of a provider-specific file (for example, a persisted data source object) containing preset connection information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ef3a9-112"><em>URL</em></span><span class="sxs-lookup"><span data-stu-id="ef3a9-112"><em>URL</em></span></span></p></td>
<td><p><span data-ttu-id="ef3a9-113">将连接字符串指定为标识资源的绝对 URL，例如，文件或目录。</span><span class="sxs-lookup"><span data-stu-id="ef3a9-113">Specifies the connection string as an absolute URL identifying a resource, such as a file or directory.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ef3a9-114"><em>Remote Provider</em></span><span class="sxs-lookup"><span data-stu-id="ef3a9-114"><em>Remote Provider</em></span></span></p></td>
<td><p><span data-ttu-id="ef3a9-p102">指定打开客户端连接时使用的提供程序的名称（仅限于远程数据服务）。</span><span class="sxs-lookup"><span data-stu-id="ef3a9-p102">Specifies the name of a provider to use when opening a client-side connection. (Remote Data Service only.)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ef3a9-117"><em>Remote Server</em></span><span class="sxs-lookup"><span data-stu-id="ef3a9-117"><em>Remote Server</em></span></span></p></td>
<td><p><span data-ttu-id="ef3a9-118">指定在打开客户端连接时要使用的服务器的路径名称。</span><span class="sxs-lookup"><span data-stu-id="ef3a9-118">Specifies the path name of the server to use when opening a client-side connection.</span></span> <span data-ttu-id="ef3a9-119">(仅限远程数据服务。)</span><span class="sxs-lookup"><span data-stu-id="ef3a9-119">(Remote Data Service only.)</span></span></p></td>
</tr>
</tbody>
</table>



> [!NOTE]
> <span data-ttu-id="ef3a9-120">在下面的示例和整个 ADO 程序员指南中, 使用密码为 "123aBc" 的用户 id "MyId" 将用于对服务器进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="ef3a9-120">In the following examples and throughout the ADO programmer's guide, the user id "MyId" with a password of "123aBc" is used to authenticate against the server.</span></span> <span data-ttu-id="ef3a9-121">您应将这些值替换为您的服务器的有效登录凭据。</span><span class="sxs-lookup"><span data-stu-id="ef3a9-121">You should substitute these values with valid login credentials for your server.</span></span> <span data-ttu-id="ef3a9-122">此外, 请将服务器的名称替换为 "MySqlServer"。</span><span class="sxs-lookup"><span data-stu-id="ef3a9-122">Also, substitute the name of your server for "MySqlServer".</span></span>

<span data-ttu-id="ef3a9-123">第 1 章中 HelloData 应用程序使用以下连接字符串：</span><span class="sxs-lookup"><span data-stu-id="ef3a9-123">The HelloData application in Chapter 1 used the following connection string:</span></span>

```vb 
 
m_sConnStr = "Provider='SQLOLEDB';Data Source='MySqlServer';" & _ 
 "Initial Catalog='Northwind';Integrated Security='SSPI';" 
```

<span data-ttu-id="ef3a9-p105">此连接字符串中提供的唯一 ADO 参数是“Provider=SQLOLEDB”，它指示 Microsoft OLE DB Provider for SQL Server。对于连接字符串中传递的其他有效参数，可以参考各个提供程序的文档来确定。按照 OLE DB Provider for SQL Server 文档，可以用“Server”代替 *Data Source* 参数，并用“Server”代替 *Initial Catalog* 参数。因此，以下连接字符串可以产生与第一个相同的结果：</span><span class="sxs-lookup"><span data-stu-id="ef3a9-p105">The only ADO parameter supplied in this connection string was "Provider=SQLOLEDB", which indicated the Microsoft OLE DB Provider for SQL Server. Other valid parameters that can be passed in the connection string can be determined by referring to individual providers' documentation. According to the OLE DB Provider for SQL Server documentation, you can substitute "Server" for the *Data Source* parameter and "Database" for the *Initial Catalog* parameter. Thus, the following connection string would produce results identical to the first:</span></span>

```vb 
 
m_sConnStr = "Provider='SQLOLEDB';Server='MySqlServer';" & _ 
 "Database='Northwind';Integrated Security='SSPI';" 
```

<span data-ttu-id="ef3a9-128">若要打开连接，只需在 **Connection** 对象的 **Open** 方法中将连接字符串作为第一个参数传递：</span><span class="sxs-lookup"><span data-stu-id="ef3a9-128">To open the connection, simply pass the connection string as the first argument in the **Connection** object **Open** method:</span></span>

```vb 
 
objConn.Open m_sConnStr 
```

<span data-ttu-id="ef3a9-p106">还可以在打开连接之前通过设置 **Connection** 对象的属性来提供更多信息。例如，通过使用以下代码，可以获得与上述连接字符串相同的效果：</span><span class="sxs-lookup"><span data-stu-id="ef3a9-p106">It is also possible to supply much of this information by setting properties of the **Connection** object before opening the connection. For example, you could achieve the same effect as the connection string above by using the following code:</span></span>

```vb 
 
With objConn 
 .Provider = "SQLOLEDB" 
 .DefaultDatabase = "Northwind" 
 .Properties("Data Source") = "MySqlServer" 
 .Properties("Integrated Security") = "SSPI" 
 .Open 
End With 
```

