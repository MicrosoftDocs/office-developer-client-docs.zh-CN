---
title: 自定义文件 UserList 部分
TOCTitle: Customization File UserList section
ms:assetid: b60ba3b0-37d4-bb59-d3cd-2ab44d178b8a
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249873(v=office.15)
ms:contentKeyID: 48547263
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: ecaf77765051a202925449d0221f0a68a2a06622
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32295154"
---
# <a name="customization-file-userlist-section"></a>自定义文件 UserList 部分


**适用于**：Access 2013、Office 2013

**userlist** 节与具有相同节 *identifier* 参数的 **connect** 节相关。

此节可以包含*用户访问项*, 该条目指定指定用户的访问权限, 并替代匹配**connect**节中的*默认**访问项*。

## <a name="syntax"></a>语法

用户访问项的格式为：

*userName * * * =* accessRights * * *

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
<td><p><em>userName</em></p></td>
<td><p>表示使用此连接的用户的<em>用户名称</em>。 有效的用户名称是用 IIS“服务管理器”<strong></strong>对话框建立的。</p></td>
</tr>
<tr class="even">
<td><p><strong><em>accessRights</em></strong></p></td>
<td><p>表示下列访问权之一：<br />
</p>
<ul>
<li><p><strong>NoAccess</strong> - 用户无法访问数据源。</p></li>
<li><p><strong>ReadOnly</strong> - 用户可以读取数据源。</p></li>
<li><p><strong>ReadWrite</strong> - 用户可以读取或写入数据源。</p></li>
</ul>
<p></p></td>
</tr>
</tbody>
</table>

