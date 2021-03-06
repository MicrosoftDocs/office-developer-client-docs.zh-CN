---
title: Microsoft OLE DB Provider for Internet Publishing
TOCTitle: Microsoft OLE DB Provider for Internet Publishing
ms:assetid: 5d1e8db5-dabb-0914-e11e-e2eac72bfa77
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249327(v=office.15)
ms:contentKeyID: 48545100
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 38183cd8306f2425a362bd2650639120a2d16845
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32288965"
---
# <a name="microsoft-ole-db-provider-for-internet-publishing"></a>用于 Internet 发布的 Microsoft OLE DB 提供程序

**适用于**：Access 2013、Office 2013

Microsoft OLE DB Provider for Internet Publishing 允许 ADO 访问 Microsoft FrontPage 或 Microsoft Internet Information Server 提供的资源。此类资源包括 Web 源文件，如 HTML 文件或 Windows 2000 Web 文件夹。

## <a name="connection-string-parameters"></a>连接字符串参数

若要连接到此提供程序，请将 [ConnectionString](connectionstring-property-ado.md) 属性的 *Provider* 参数设置为：

```vb 
 
MSDAIPP.DSO 
```

也可以使用 [Provider](provider-property-ado.md) 属性设置或读取此值。

## <a name="typical-connection-string"></a>典型的连接字符串

此提供程序典型的连接字符串为：

```vb 
 
"Provider=MSDAIPP.DSO;Data Source=ResourceURL;User ID=userName;Password=userPassword;" 
```

\-和

```vb 
 
"URL=ResourceURL;User ID=userName;Password=userPassword;" 
```

该字符串由以下关键字组成：

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
<td><p><strong>Provider</strong></p></td>
<td><p>指定 OLE DB Provider for Internet Publishing。</p></td>
</tr>
<tr class="even">
<td><p><strong>Data Source</strong> -或- <strong>URL</strong></p></td>
<td><p>指定在 web 文件夹中发布的文件或目录的 URL。</p></td>
</tr>
<tr class="odd">
<td><p><strong>User ID</strong></p></td>
<td><p>指定用户名。</p></td>
</tr>
<tr class="even">
<td><p><strong>Password</strong></p></td>
<td><p>指定用户密码。</p></td>
</tr>
</tbody>
</table>


如果将连接字符串的“URL=”中的 *ResourceURL* 值设置为无效的值，则默认情况下 Internet Publishing Provider 会呈现一个对话框，提示您输入有效值。对于应用程序中间层中的组件，这是一种不恰当的行为，因为该行为将挂起程序的执行直到清除该对话框为止，而且客户端似乎会冻结，因为它未收到来自组件的响应。

> [!NOTE]
> 如果将 MSDAIPP.DSO 显式指定为提供程序的值（使用 *Provider* 连接字符串关键字或 **Provider** 属性），则您不能在连接字符串中使用“URL=”。否则，将会发生错误。只需按照[将 ADO 与 OLE DB Provider for Internet Publishing 结合使用](the-ole-db-provider-for-internet-publishing.md)主题中所述的方式指定 URL 即可。

