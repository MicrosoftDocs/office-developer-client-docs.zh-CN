---
title: Microsoft OLE DB Provider for Internet Publishing
TOCTitle: Microsoft OLE DB Provider for Internet Publishing
ms:assetid: 5d1e8db5-dabb-0914-e11e-e2eac72bfa77
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249327(v=office.15)
ms:contentKeyID: 48545100
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 7221c6bd0a6e8576237fdf4cbfcabe70620f6af8
ms.sourcegitcommit: a49b77f4c8cec69f90656a86f0872cf34c35968e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2018
ms.locfileid: "25603992"
---
# <a name="microsoft-ole-db-provider-for-internet-publishing"></a><span data-ttu-id="034b7-102">Microsoft OLE DB Provider for Internet Publishing</span><span class="sxs-lookup"><span data-stu-id="034b7-102">Microsoft OLE DB Provider for Internet Publishing</span></span>

<span data-ttu-id="034b7-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="034b7-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="034b7-p101">Microsoft OLE DB Provider for Internet Publishing 允许 ADO 访问 Microsoft FrontPage 或 Microsoft Internet Information Server 提供的资源。此类资源包括 Web 源文件，如 HTML 文件或 Windows 2000 Web 文件夹。</span><span class="sxs-lookup"><span data-stu-id="034b7-p101">The Microsoft OLE DB Provider for Internet Publishing allows ADO to access resources served by Microsoft FrontPage or Microsoft Internet Information Server. Resources include web source files such as HTML files, or Windows 2000 web folders.</span></span>

## <a name="connection-string-parameters"></a><span data-ttu-id="034b7-106">连接字符串参数</span><span class="sxs-lookup"><span data-stu-id="034b7-106">Connection String Parameters</span></span>

<span data-ttu-id="034b7-107">若要连接到此提供程序，请将 *ConnectionString* 属性的 [Provider](connectionstring-property-ado.md) 参数设置为：</span><span class="sxs-lookup"><span data-stu-id="034b7-107">To connect to this provider, set the *Provider* argument of the [ConnectionString](connectionstring-property-ado.md) property to:</span></span>

```vb 
 
MSDAIPP.DSO 
```

<span data-ttu-id="034b7-108">也可以使用 [Provider](provider-property-ado.md) 属性设置或读取此值。</span><span class="sxs-lookup"><span data-stu-id="034b7-108">This value can also be set or read using the [Provider](provider-property-ado.md) property.</span></span>

## <a name="typical-connection-string"></a><span data-ttu-id="034b7-109">典型的连接字符串</span><span class="sxs-lookup"><span data-stu-id="034b7-109">Typical Connection String</span></span>

<span data-ttu-id="034b7-110">此提供程序典型的连接字符串为：</span><span class="sxs-lookup"><span data-stu-id="034b7-110">A typical connection string for this provider is:</span></span>

```vb 
 
"Provider=MSDAIPP.DSO;Data Source=ResourceURL;User ID=userName;Password=userPassword;" 
```

<span data-ttu-id="034b7-111">\-或-</span><span class="sxs-lookup"><span data-stu-id="034b7-111">\-or-</span></span>

```vb 
 
"URL=ResourceURL;User ID=userName;Password=userPassword;" 
```

<span data-ttu-id="034b7-112">该字符串由以下关键字组成：</span><span class="sxs-lookup"><span data-stu-id="034b7-112">The string consists of these keywords:</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="034b7-113">关键字</span><span class="sxs-lookup"><span data-stu-id="034b7-113">Keyword</span></span></p></th>
<th><p><span data-ttu-id="034b7-114">说明</span><span class="sxs-lookup"><span data-stu-id="034b7-114">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="034b7-115"><strong>Provider</strong></span><span class="sxs-lookup"><span data-stu-id="034b7-115"><strong>Provider</strong></span></span></p></td>
<td><p><span data-ttu-id="034b7-116">指定 OLE DB Provider for Internet Publishing。</span><span class="sxs-lookup"><span data-stu-id="034b7-116">Specifies the OLE DB Provider for Internet Publishing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="034b7-117"><strong>Data Source</strong> -或- <strong>URL</strong></span><span class="sxs-lookup"><span data-stu-id="034b7-117"><strong>Data Source</strong> -or- <strong>URL</strong></span></span></p></td>
<span data-ttu-id="034b7-118"><<<<<<< 标头</span><span class="sxs-lookup"><span data-stu-id="034b7-118"><<<<<<< HEAD</span></span>
<td><p><span data-ttu-id="034b7-119">指定在 Web 文件夹中发布的文件或目录的 URL。</span><span class="sxs-lookup"><span data-stu-id="034b7-119">Specifies the URL of a file or directory published in a Web Folder.</span></span></p></td>
=======
<td><p><span data-ttu-id="034b7-120">指定文件或目录 web 文件夹中发布的 URL。</span><span class="sxs-lookup"><span data-stu-id="034b7-120">Specifies the URL of a file or directory published in a web folder.</span></span></p></td><span data-ttu-id="034b7-121">
>>>>>>>主控形状</span><span class="sxs-lookup"><span data-stu-id="034b7-121">
>>>>>>> master</span></span>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="034b7-122"><strong>User ID</strong></span><span class="sxs-lookup"><span data-stu-id="034b7-122"><strong>User ID</strong></span></span></p></td>
<td><p><span data-ttu-id="034b7-123">指定用户名。</span><span class="sxs-lookup"><span data-stu-id="034b7-123">Specifies the user name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="034b7-124"><strong>Password</strong></span><span class="sxs-lookup"><span data-stu-id="034b7-124"><strong>Password</strong></span></span></p></td>
<td><p><span data-ttu-id="034b7-125">指定用户密码。</span><span class="sxs-lookup"><span data-stu-id="034b7-125">Specifies the user password.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="034b7-p102">如果将连接字符串的“URL=”中的 *ResourceURL* 值设置为无效的值，则默认情况下 Internet Publishing Provider 会呈现一个对话框，提示您输入有效值。对于应用程序中间层中的组件，这是一种不恰当的行为，因为该行为将挂起程序的执行直到清除该对话框为止，而且客户端似乎会冻结，因为它未收到来自组件的响应。</span><span class="sxs-lookup"><span data-stu-id="034b7-p102">If you set the *ResourceURL* value from the "URL=" in the connection string to an invalid value, by default the Internet Publishing Provider raises a dialog box to prompt for a valid value. This is undesirable behavior for a component in the middle tier of an application, because it suspends program execution until the dialog box is cleared and the client appears to freeze because it has not received a response from the component.</span></span>


> [!NOTE]
> <P><span data-ttu-id="034b7-128">如果 MSDAIPP。DSO 显式指定为提供程序，则可以使用<EM>提供程序</EM>的连接字符串关键字或<STRONG>Provider</STRONG>属性，则不能使用"URL ="连接字符串中。</span><span class="sxs-lookup"><span data-stu-id="034b7-128">If MSDAIPP.DSO is explicitly specified as the value of the provider, either with the <EM>Provider</EM> connection string keyword or the <STRONG>Provider</STRONG> property, you cannot use "URL=" in the connection string.</span></span> <span data-ttu-id="034b7-129">否则，将会发生错误。</span><span class="sxs-lookup"><span data-stu-id="034b7-129">If you do, an error will occur.</span></span> <span data-ttu-id="034b7-130">只需按照 <A href="the-ole-db-provider-for-internet-publishing.md">将 ADO 与 OLE DB Provider for Internet Publishing 结合使用</A>主题中所述的方式指定 URL 即可。</span><span class="sxs-lookup"><span data-stu-id="034b7-130">Instead, simply specify the URL as shown in the topic <A href="the-ole-db-provider-for-internet-publishing.md">Using ADO with the OLE DB Provider for Internet Publishing</A>.</span></span></P>


