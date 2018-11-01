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
# <a name="creating-the-connection-string"></a><span data-ttu-id="baa20-102">创建连接字符串</span><span class="sxs-lookup"><span data-stu-id="baa20-102">Creating the Connection String</span></span>


<span data-ttu-id="baa20-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="baa20-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="baa20-p101">在连接字符串中，ADO 直接支持五个参数。其他参数将传递给 *Provider* 参数所命名的提供程序，ADO 不对其进行任何处理。</span><span class="sxs-lookup"><span data-stu-id="baa20-p101">ADO directly supports five arguments in a connection string. Other arguments are passed to the provider that is named in the *Provider* argument without any processing by ADO.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="baa20-106">参数</span><span class="sxs-lookup"><span data-stu-id="baa20-106">Argument</span></span></p></th>
<th><p><span data-ttu-id="baa20-107">说明</span><span class="sxs-lookup"><span data-stu-id="baa20-107">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="baa20-108"><em>Provider</em></span><span class="sxs-lookup"><span data-stu-id="baa20-108"><em>Provider</em></span></span></p></td>
<td><p><span data-ttu-id="baa20-109">指定用于连接的提供程序的名称。</span><span class="sxs-lookup"><span data-stu-id="baa20-109">Specifies the name of a provider to use for the connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="baa20-110"><em>文件名</em></span><span class="sxs-lookup"><span data-stu-id="baa20-110"><em>File Name</em></span></span></p></td>
<td><p><span data-ttu-id="baa20-111">指定包含预置连接信息的、特定于提供程序的文件（例如，持久化的数据源对象）的名称。</span><span class="sxs-lookup"><span data-stu-id="baa20-111">Specifies the name of a provider-specific file (for example, a persisted data source object) containing preset connection information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="baa20-112"><em>URL</em></span><span class="sxs-lookup"><span data-stu-id="baa20-112"><em>URL</em></span></span></p></td>
<td><p><span data-ttu-id="baa20-113">将连接字符串指定为标识资源的绝对 URL，例如，文件或目录。</span><span class="sxs-lookup"><span data-stu-id="baa20-113">Specifies the connection string as an absolute URL identifying a resource, such as a file or directory.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="baa20-114"><em>Remote Provider</em></span><span class="sxs-lookup"><span data-stu-id="baa20-114"><em>Remote Provider</em></span></span></p></td>
<td><p><span data-ttu-id="baa20-p102">指定打开客户端连接时使用的提供程序的名称（仅限于远程数据服务）。</span><span class="sxs-lookup"><span data-stu-id="baa20-p102">Specifies the name of a provider to use when opening a client-side connection. (Remote Data Service only.)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="baa20-117"><em>Remote Server</em></span><span class="sxs-lookup"><span data-stu-id="baa20-117"><em>Remote Server</em></span></span></p></td>
<td><p><span data-ttu-id="baa20-p103">指定打开客户端连接时使用的服务器的路径名称（仅限于远程数据服务）。</span><span class="sxs-lookup"><span data-stu-id="baa20-p103">Specifies the path name of the server to use when opening a client-side connection. (Remote Data Service only.)</span></span></p></td>
</tr>
</tbody>
</table>



> [!NOTE]
> <span data-ttu-id="baa20-p104">在以下示例和整个《ADO 程序员指南》中，将以用户 ID“MyId”和密码“123aBc”来向服务器进行身份验证。应当用您的服务器的有效登录凭据来替换这些值，并用您的服务器的名称替换“MySqlServer”。</span><span class="sxs-lookup"><span data-stu-id="baa20-p104">In the following examples and throughout the ADO Programmer's Guide, the user id "MyId" with a password of "123aBc" is used to authenticate against the server. You should substitute these values with valid login credentials for your server. Also, substitute the name of your server for "MySqlServer".</span></span>

<span data-ttu-id="baa20-123">第 1 章中 HelloData 应用程序使用以下连接字符串：</span><span class="sxs-lookup"><span data-stu-id="baa20-123">The HelloData application in Chapter 1 used the following connection string:</span></span>

```vb 
 
m_sConnStr = "Provider='SQLOLEDB';Data Source='MySqlServer';" & _ 
 "Initial Catalog='Northwind';Integrated Security='SSPI';" 
```

<span data-ttu-id="baa20-124">此连接字符串中提供的唯一 ADO 参数是"Provider=SQLOLEDB"，它指示 Microsoft OLE DB Provider for SQL Server。</span><span class="sxs-lookup"><span data-stu-id="baa20-124">The only ADO parameter supplied in this connection string was "Provider=SQLOLEDB", which indicated the Microsoft OLE DB Provider for SQL Server.</span></span> <span data-ttu-id="baa20-125">对于连接字符串中传递的其他有效参数，可以参考各个提供程序的文档来确定。</span><span class="sxs-lookup"><span data-stu-id="baa20-125">Other valid parameters that can be passed in the connection string can be determined by referring to individual providers' documentation.</span></span> <span data-ttu-id="baa20-126">根据 OLE DB Provider for SQL Server 文档，您可以*Initial Catalog*参数的*数据源*参数和"数据库"替换"服务器"。</span><span class="sxs-lookup"><span data-stu-id="baa20-126">According to the OLE DB Provider for SQL Server documentation, you can substitute "Server" for the *Data Source* parameter and "Database" for the *Initial Catalog* parameter.</span></span> <span data-ttu-id="baa20-127">因此，以下连接字符串可以产生与第一个相同的结果：</span><span class="sxs-lookup"><span data-stu-id="baa20-127">Thus, the following connection string would produce results identical to the first:</span></span>

```vb 
 
m_sConnStr = "Provider='SQLOLEDB';Server='MySqlServer';" & _ 
 "Database='Northwind';Integrated Security='SSPI';" 
```

<span data-ttu-id="baa20-128">若要打开连接，只需在 **Connection** 对象的 **Open** 方法中将连接字符串作为第一个参数传递：</span><span class="sxs-lookup"><span data-stu-id="baa20-128">To open the connection, simply pass the connection string as the first argument in the **Connection** object **Open** method:</span></span>

```vb 
 
objConn.Open m_sConnStr 
```

<span data-ttu-id="baa20-p106">还可以在打开连接之前通过设置 **Connection** 对象的属性来提供更多信息。例如，通过使用以下代码，可以获得与上述连接字符串相同的效果：</span><span class="sxs-lookup"><span data-stu-id="baa20-p106">It is also possible to supply much of this information by setting properties of the **Connection** object before opening the connection. For example, you could achieve the same effect as the connection string above by using the following code:</span></span>

```vb 
 
With objConn 
 .Provider = "SQLOLEDB" 
 .DefaultDatabase = "Northwind" 
 .Properties("Data Source") = "MySqlServer" 
 .Properties("Integrated Security") = "SSPI" 
 .Open 
End With 
```

