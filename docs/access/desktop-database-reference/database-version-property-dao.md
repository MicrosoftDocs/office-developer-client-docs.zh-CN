---
title: Database.Version 属性 (DAO)
TOCTitle: Version Property
ms:assetid: 40faaa0c-e764-e968-f606-7e06ded80c3f
ms:mtpsurl: https://msdn.microsoft.com/library/Ff192887(v=office.15)
ms:contentKeyID: 48544440
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 6d39dc351eee86ec409f85b602dfa46099c0381b
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25923614"
---
# <a name="databaseversion-property-dao"></a>Database.Version 属性 (DAO)


**适用于**： Access 2013、 Office 2013

在 Microsoft Access 工作区中，返回创建数据库的 Microsoft Jet 或 Microsoft Access 数据库引擎的版本。 **String** 类型，只读。

## <a name="syntax"></a>语法

*表达式*。版本

*表达式*一个代表**Database**对象的变量。

## <a name="remarks"></a>注解

返回值是一个 String，其计算结果为版本号，格式如下所示。

  - Microsoft Access 工作区以“*major.minor*”的形式表示版本号。例如，“3.0”。产品版本号由版本号 (3)、句点和发行版本号 (0) 组成。

下表显示不同版本的 Microsoft 产品中包含的数据库引擎版本。

<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th><p>数据库引擎</p></th>
<th><p>版本（发行年份）</p></th>
<th><p>Microsoft Access</p></th>
<th><p>Microsoft Visual Basic</p></th>
<th><p>Microsoft Excel</p></th>
<th><p>Microsoft Visual C++</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Microsoft Jet</p></td>
<td><p>1.0 (1992)</p></td>
<td><p>1.0</p></td>
<td><p>无</p></td>
<td><p>不适用</p></td>
<td><p>无</p></td>
</tr>
<tr class="even">
<td><p>Microsoft Jet</p></td>
<td><p>1.1 (1993)</p></td>
<td><p>1.1</p></td>
<td><p>3.0</p></td>
<td><p>无</p></td>
<td><p>无</p></td>
</tr>
<tr class="odd">
<td><p>Microsoft Jet</p></td>
<td><p>2.0 (1994)</p></td>
<td><p>2.0</p></td>
<td><p>无</p></td>
<td><p>不适用</p></td>
<td><p>无</p></td>
</tr>
<tr class="even">
<td><p>Microsoft Jet</p></td>
<td><p>2.5 （1995 年）</p></td>
<td><p>无</p></td>
<td><p>4.0（16 位）</p></td>
<td><p>无</p></td>
<td><p>无</p></td>
</tr>
<tr class="odd">
<td><p>Microsoft Jet</p></td>
<td><p>3.0 （1995 年）</p></td>
<td><p>"95 (7.0)</p></td>
<td><p>4.0（32 位）</p></td>
<td><p>"95 (7.0)</p></td>
<td><p>4.x</p></td>
</tr>
<tr class="even">
<td><p>Microsoft Jet</p></td>
<td><p>3.5 （1996 年）</p></td>
<td><p>' 97 (8.0)</p></td>
<td><p>5.0</p></td>
<td><p>' 97 (8.0)</p></td>
<td><p>5.0</p></td>
</tr>
<tr class="odd">
<td><p>Microsoft Jet</p></td>
<td><p>4.0 (2000)</p></td>
<td><p>2000 (9.0)</p></td>
<td><p></p></td>
<td><p>2000 (9.0)</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>Microsoft Access 数据库引擎</p></td>
<td><p>12.0 (2007)</p></td>
<td><p>2007</p></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
</tbody>
</table>

