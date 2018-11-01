---
title: Group 宏语句
TOCTitle: Group Macro Statement
ms:assetid: 42aa4afa-ab5d-9dcc-2182-786f025e316d
ms:mtpsurl: https://msdn.microsoft.com/library/Ff192918(v=office.15)
ms:contentKeyID: 48544481
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 35f9ad1d445dbddaa5487e28da60b9202a72dae1
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25879849"
---
# <a name="group-macro-statement"></a>Group 宏语句


**适用于**： Access 2013、 Office 2013

**使用 Group**语句，可以指定一个块中的宏，您可以展开或折叠的操作。

## <a name="setting"></a>设置

**Group** 操作具有以下参数。

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>参数</p></th>
<th><p>是否必需</p></th>
<th><p>说明</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>否</p></td>
<td><p>一个在折叠时显示为组标题的字符串。</p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>注释

**Group** 语句不定义可以单独执行的宏区域。使用 **[Submacro](submacro-macro-statement.md)** 语句可定义要在 **"宏设计器"** 窗口中单独执行的一组操作。

