---
title: RemoveAllTempVars 宏操作
TOCTitle: RemoveAllTempVars macro action
ms:assetid: 409fd836-4a53-cefd-4264-8cee0fa8ac52
ms:mtpsurl: https://msdn.microsoft.com/library/Ff192877(v=office.15)
ms:contentKeyID: 48544430
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm117413
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: eade809a6e3982dc0dc4cf94ae382af72e8f454e
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28705074"
---
# <a name="removealltempvars-macro-action"></a>RemoveAllTempVars 宏操作


**适用于**： Access 2013、 Office 2013


可以使用 **RemoveAllTempVars** 操作删除用 **SetTempVar** 操作创建的所有临时变量。

## <a name="setting"></a>设置

**RemoveAllTempVars** 操作不具有任何参数。

## <a name="remarks"></a>说明

  - 一次最多可以定义 255 个临时变量。如果您不删除临时变量，它将一直保留在内存中，直到您关闭数据库或项目。在使用完临时变量后，最好将它们删除。

  - 在关闭数据库或项目时，Access 会自动删除所有临时变量。

  - 要删除单个临时变量，请使用 **RemoveTempVar** 操作，并将其参数设置为要删除的临时变量的名称。

  - 要在 VBA 模块中运行 **RemoveAllTempVars** 操作，请使用 **TempVars** 对象的 **RemoveAll** 方法。

## <a name="example"></a>示例

下面的宏演示如何创建一个临时变量，在条件和消息框中使用它，然后使用 **RemoveAllTempVars** 操作删除该临时变量。

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
<td><p><strong>RemoveAllTempVars</strong></p></td>
<td><p></p></td>
</tr>
</tbody>
</table>

