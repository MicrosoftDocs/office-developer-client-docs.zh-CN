---
title: RemoveTempVar 宏操作
TOCTitle: RemoveTempVar macro action
ms:assetid: 7bcc5010-3e30-ecef-2c5d-a35e73c8e325
ms:mtpsurl: https://msdn.microsoft.com/library/Ff196352(v=office.15)
ms:contentKeyID: 48545822
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm147125
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: 5051cfd74f2a745ee430f2ed8a20445d2f9965f3
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28716304"
---
# <a name="removetempvar-macro-action"></a>RemoveTempVar 宏操作


**适用于**： Access 2013、 Office 2013



可以使用 **RemoveTempVar** 操作删除用 **SetTempVar** 操作创建的单个临时变量。

## <a name="setting"></a>设置

**RemoveTempVar** 操作具有以下参数。

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>操作参数</p></th>
<th><p>说明</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Name</strong></p></td>
<td><p>请输入要删除的临时变量的名称。</p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>说明

  - 一次最多可以定义 255 个临时变量。如果您不删除临时变量，它将一直保留在内存中，直到您关闭数据库。在使用完临时变量后，最好将它们删除。

  - 在关闭数据库或项目时，Access 会自动删除所有临时变量。

  - 如果要删除的变量的名称拼写不正确，Access 不会显示出错。要删除的变量将一直保留在内存中，直到您关闭数据库。

  - 如果创建了多个临时变量并且想同时将它们全部删除，请使用 **RemoveAllTempVars** 操作。

  - 要在 VBA 模块中运行 **RemoveTempVar** 操作，请使用 **TempVars** 对象的 **Remove** 方法。

## <a name="example"></a>示例

下面的宏演示如何创建一个临时变量，在条件和消息框中使用它，然后使用 **RemoveTempVar** 操作删除该临时变量。

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>条件</p></th>
<th><p>操作</p></th>
<th><p>参数</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p></p></td>
<td><p><strong>SetTempVar</strong></p></td>
<td><p><strong>名称</strong>： MyVar<strong>表达式</strong>： InputBox (&quot;输入非零数。&quot;)</p></td>
</tr>
<tr class="even">
<td><p>[TempVars] ！[MyVar]&lt; &gt;0</p></td>
<td><p><strong>MessageBox</strong></p></td>
<td><p><strong>消息</strong>: =&quot;您输入&quot; &amp; [TempVars] ！[MyVar]&amp; &quot;.&quot;<strong>发嘟嘟声</strong>： <strong>YesType</strong>：<strong>信息</strong></p></td>
</tr>
<tr class="odd">
<td><p></p></td>
<td><p><strong>RemoveTempVar</strong></p></td>
<td><p><strong>名称</strong>：MyVar</p></td>
</tr>
</tbody>
</table>

