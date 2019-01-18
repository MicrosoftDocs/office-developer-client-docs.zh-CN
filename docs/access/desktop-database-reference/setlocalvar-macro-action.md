---
title: SetLocalVar 宏操作
TOCTitle: SetLocalVar macro action
ms:assetid: 8a6af395-0f76-72e2-37f3-2cff22a38b3c
ms:mtpsurl: https://msdn.microsoft.com/library/Ff197097(v=office.15)
ms:contentKeyID: 48546190
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm176660
f1_categories:
- Office.Version=v15
localization_priority: Priority
ms.openlocfilehash: 091b9717b9a2e35cfc8d0c8555e28570628065ef
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28702458"
---
# <a name="setlocalvar-macro-action"></a>SetLocalVar 宏操作

**适用于**： Access 2013、 Office 2013

**SetLocalVar** 操作可创建一个临时变量并将其设置为特定值。

## <a name="setting"></a>设置

**SetLocalVar** 操作具有下列参数。

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
<td><p><strong>Name</strong></p></td>
<td><p>是</p></td>
<td><p>一个用于指定变量名称的字符串。</p></td>
</tr>
<tr class="even">
<td><p><strong>Expression</strong></p></td>
<td><p>是</p></td>
<td><p>一个表达式，用于设置为临时变量的值。 不在表达式前面放等号 （=）。 您可以单击<strong>生成</strong>按钮以使用<strong>表达式生成器</strong>设置此参数。</p></td>
</tr>
</tbody>
</table>

## <a name="remarks"></a>注释

由 **SetLocalVar** 操作创建的变量只能在定义这些变量的宏中使用。使用 **[SetTempVar](settempvar-macro-action.md)** 操作可定义可在其他宏、事件过程、窗体或报表中使用的变量。

创建临时变量后，即可在表达式中引用该变量。例如，如果创建一个名为 TotalAmount 的临时变量，则可以使用下面的语法将该变量用作文本框的控件来源。

`=[LocalVars]![TotalAmount]`

> [!NOTE]
> [!注释] 在数据宏中，您不必使用 LocalVars 集合来引用变量。 例如，如果您在一个名为 TotalAmount 的数据宏创建一个临时变量，您无法用作变量的控件来源文本框中使用以下语法： `=[TotalAmount]`。

