---
title: 自定义文件 UserList 节
TOCTitle: Customization File UserList Section
ms:assetid: b60ba3b0-37d4-bb59-d3cd-2ab44d178b8a
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249873(v=office.15)
ms:contentKeyID: 48547263
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: a14060858ad5cd90b410319a515eb271b2b397ea
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25467666"
---
# <a name="customization-file-userlist-section"></a>自定义文件 UserList 节


**适用于**： Access 2013 |Office 2013

**Userlist**节与具有相同节*identifier*参数的**连接**部分。

此节可以包含一个*用户访问项*，后者指定指定用户的访问权限，并替代匹配的**连接**部分中的*默认**访问项*。

## <a name="syntax"></a>语法

用户访问项的格式为：

*用户名 *** =* accessRights ***

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
<td><p><em>userName</em></p></td>
<td><p>使用此连接的人员的<em>用户名</em>。 有效的用户名建立与 IIS<strong>服务管理器</strong>对话框。</p></td>
</tr>
<tr class="even">
<td><p><strong><em>accessRights</em></strong></p></td>
<td><p>表示下列访问权之一：
<br />
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

