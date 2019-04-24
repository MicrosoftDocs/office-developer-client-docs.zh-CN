---
title: ClearMacroError 宏操作
TOCTitle: ClearMacroError macro action
ms:assetid: 1091747e-e957-38c6-6454-5169f091323e
ms:mtpsurl: https://msdn.microsoft.com/library/Ff845338(v=office.15)
ms:contentKeyID: 48543296
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm109100
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: f42386674ff76d550fb47a971860b4e1a5905236
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32296372"
---
# <a name="clearmacroerror-macro-action"></a>ClearMacroError 宏操作


**适用于**：Access 2013、Office 2013


可以使用 **ClearMacroError** 操作清除有关 **MacroError** 对象中所存储的错误的信息。

## <a name="setting"></a>Setting

**ClearMacroError** 操作不具有任何参数。

## <a name="remarks"></a>注解

- 宏错误时，错误的信息存储在 **MacroError** 对象。 如果您未使用**[OnError](onerror-macro-action.md)** 操作来禁止显示错误消息, 则宏将停止, 错误信息将显示在标准错误消息中。 但是, 如果您已使用**OnError**操作禁止显示错误消息, 则可能需要在条件中或自定义错误消息中使用存储在**MacroError**对象中的信息。
    
  在错误得到处理后， **MacroError** 对象中的信息将过期，因此最好使用 **ClearMacroError** 操作清除该对象。执行此操作会将 **MacroError** 对象的错误数量重置为 0，并清除有关存储在该对象中的错误的所有其他信息，例如错误说明、宏名称、操作名称、条件和参数。通过这种方式，可在以后重新检查 **MacroError** 对象，以确定是否发生了其他错误。

- 在任何宏结束时，都会自动清除 **MacroError** 对象，因此无需在宏末尾使用 **ClearMacroError** 操作。

- **MacroError** 对象每次仅包含有关一个错误的信息。如果宏中发生了多个错误， **MacroError** 对象将仅包含有关最后一个错误的信息。

- 要在 VBA 模块中运行 **ClearMacroError** 操作，请使用 **DoCmd** 对象的 **ClearMacroError** 方法。

## <a name="example"></a>示例

The following macro uses the **OnError** action with the **Next** argument to suppress error messages, and then uses the **OpenForm** action to open a form. For this example, an error is deliberately created by using the **GoToRecord** action to go to the previous record. 条件** \[MacroError\]。\[\>数字\]\<0**测试**MacroError**对象。 If an error has occurred, the error number is non-zero, and the **MessageBox** action runs. The message box displays the name of the action that caused the error (in this case, the **GoToRecord** action), and the error number is displayed. 此示例最后运行 **ClearMacroError** 操作清除 **MacroError** 对象。

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
<td><p><strong>OnError</strong></p></td>
<td><p><strong>转至</strong>：<strong>“下一个”</strong></p></td>
</tr>
<tr class="even">
<td><p></p></td>
<td><p><strong>OpenForm</strong></p></td>
<td><p><strong>表单名称</strong>: 类别窗体<strong>View</strong>: <strong>FormWindow Mode</strong>: <strong>Normal</strong></p></td>
</tr>
<tr class="odd">
<td><p></p></td>
<td><p><strong>GoToRecord</strong></p></td>
<td><p><strong>对象类型</strong>: <strong>FormObject Name</strong>: 类别窗体<strong>Record</strong>: Previous</p></td>
</tr>
<tr class="even">
<td><p>[MacroError]。多种&lt; &gt;0</p></td>
<td><p><strong>MessageBox</strong></p></td>
<td><p><strong>消息</strong>: =&quot;错误 # &quot; &amp; [MacroError]。多种在 [MacroError &amp; ] 上。 &quot; &amp; &quot;ActionName&amp; &quot;操作。&quot;<strong>嘟嘟声</strong>: <strong>YesType</strong>: 信息</p></td>
</tr>
<tr class="odd">
<td><p></p></td>
<td><p><strong>ClearMacroError</strong></p></td>
<td><p></p></td>
</tr>
</tbody>
</table>

