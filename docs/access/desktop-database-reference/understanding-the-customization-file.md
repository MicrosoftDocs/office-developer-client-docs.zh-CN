---
title: 了解自定义文件
TOCTitle: Understanding the Customization File
ms:assetid: 98fd5ec1-d5bd-cdd2-5eb5-9a1682fbed79
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249686(v=office.15)
ms:contentKeyID: 48546507
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 5bd19a1cec1e9618586b25b0b5cdf654cd1a5fdf
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25466508"
---
# <a name="understanding-the-customization-file"></a>了解自定义文件


**适用于**： Access 2013 |Office 2013

自定义文件中的每个节标头包含方括号 (**\[**) 包含类型和参数。 节分为四种类型，分别用字面字符串 **connect** 、 **sql** 、 **userlist** 或 **logs** 表示。 参数可以是字面字符串、默认值、用户指定的标识符或为空。

因此，每节用以下节标头中的一种进行标记：

```text 
 
[ connect   default     ]
[ connect   identifier  ]
[ sql       default     ]
[ sql       identifier  ]
[ userlist  identifier  ]
[ logs                  ]
```

节标头包含以下部分。

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>部分</p></th>
<th><p>说明</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>connect</strong></p></td>
<td><p>修改连接字符串的字面字符串。</p></td>
</tr>
<tr class="even">
<td><p><strong>sql</strong></p></td>
<td><p>修改命令字符串的字面字符串。</p></td>
</tr>
<tr class="odd">
<td><p><strong>userlist</strong></p></td>
<td><p>修改特定用户访问权限的字面字符串。</p></td>
</tr>
<tr class="even">
<td><p><strong>logs</strong></p></td>
<td><p>指定记录操作错误的日志文件的字面字符串。</p></td>
</tr>
<tr class="odd">
<td><p><strong>default</strong></p></td>
<td><p>当未指定或未找到标识符时所使用的字面字符串。</p></td>
</tr>
<tr class="even">
<td><p><em>identifier</em></p></td>
<td><p>与 <strong>connect</strong> 字符串或 <strong>command</strong> 字符串中的字符串匹配的字符串。
</p>
<p></p>
<ul>
<li><p>如果节标头中包含 <strong>connect</strong> 且在连接字符串中找到标识符字符串，则使用此节。</p></li>
<li><p>如果节标头中包含 <strong>sql</strong> 且在命令字符串中找到标识符字符串，则使用此节。</p></li>
<li><p>如果节标头中包含 <strong>userlist</strong> 且标识符字符串与 <strong>connect</strong> 节标识符匹配，则使用此节。</p></li>
</ul>
<p></p></td>
</tr>
</tbody>
</table>


**DataFactory** 调用处理程序，传递客户端参数。处理程序在客户端参数中搜索与相应节标头中的标识符匹配的整个字符串。如果找到匹配的字符串，则将此节的内容应用于客户端参数。

以上各节用在以下不同情况中：

  - 如果客户端的值部分的连接字符串关键字，则使用**连接**节"**数据源 = *** 值*"，与 *。* **连接**节标识符匹配

  - 如果客户端命令字符串中包含与 **sql** 节标识符匹配的字符串，则使用 **sql** 节。

  - 如果没有匹配的标识符，则使用带默认参数的 **connect** 或 **sql** 节。

  - 如果 **userlist** 节标识符与 **connect** 节标识符匹配，则使用 **userlist** 节。如果匹配，则将 **userlist** 的内容应用于 **connect** 节所控制的连接。

  - 如果连接字符串或命令字符串中的字符串与任何 **connect** 或 **sql** 节标头中的标识符都不匹配，且不存在带默认参数的 **connect** 或 **sql** 节标头，则按原样使用客户端字符串，不进行修改。

  - 只要 **DataFactory** 处于操作状态，便使用 **logs** 节。

