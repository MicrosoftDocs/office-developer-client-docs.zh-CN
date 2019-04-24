---
title: 自定义文件 Connect 部分
TOCTitle: Customization File Connect section
ms:assetid: 037abfb4-798d-4b09-6133-356969aee95c
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248802(v=office.15)
ms:contentKeyID: 48542985
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 8652aa2c028350aab79cdf101cba189026b9a5ae
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32295140"
---
# <a name="customization-file-connect-section"></a>自定义文件 Connect 部分

**适用于**：Access 2013、Office 2013

处理程序的默认行为是拒绝所有连接。 **connect** 节指定该行为的例外。例如，如果不存在任何 **connect** 节或这些节都为空，则默认情况下不能建立任何连接。

**connect** 节可以包含：

- 默认访问项，用于指定在此连接上所允许的默认读取和写入操作。如果此节中没有默认访问项，将忽略该节。

- 新连接字符串，用于替换客户端连接字符串。

## <a name="syntax"></a>语法

默认访问项的格式为：

`Access=accessRight`

替换连接字符串项的格式为：

`Connect=connectionString`

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Part</p></th>
<th><p>说明</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Connect</strong></p></td>
<td><p>字面字符串，用于指示这是连接字符串项。</p></td>
</tr>
<tr class="even">
<td><p><strong><em>connectionString</em></strong></p></td>
<td><p>字符串，用于替换整个客户端连接字符串。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Access</strong></p></td>
<td><p>字面字符串，用于指示这是访问项。</p></td>
</tr>
<tr class="even">
<td><p><strong><em>accessRight</em></strong></p></td>
<td><p>表示下列访问权之一：</p>
<p></p>
<ul>
<li><p><strong>NoAccess</strong> - 用户无法访问数据源。</p></li>
<li><p><strong>ReadOnly</strong> - 用户可以读取数据源。</p></li>
<li><p><strong>ReadWrite</strong> - 用户可以读取或写入数据源。</p></li>
</ul>
<p></p></td>
</tr>
</tbody>
</table>


如果要允许任何连接 (实际上, 禁用默认处理程序行为), 请将 "**连接默认**" 部分中的访问项设置为, 并删除或注释掉任何其他**connect** *标识符*部分。

