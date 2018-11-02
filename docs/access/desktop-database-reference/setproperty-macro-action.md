---
title: SetProperty 宏操作
TOCTitle: SetProperty macro action
ms:assetid: 58d2eac3-35b2-e9f8-47e0-62c9b52f2c24
ms:mtpsurl: https://msdn.microsoft.com/library/Ff194340(v=office.15)
ms:contentKeyID: 48545004
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm139044
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 48b51ac15cde600b6f79968af49b73ad73333915
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25918994"
---
# <a name="setproperty-macro-action"></a>SetProperty 宏操作

**适用于**： Access 2013、 Office 2013

可以使用 **SetProperty** 操作设置窗体或报表上控件的属性。

## <a name="setting"></a>设置

**SetProperty** 操作具有下列参数。

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
<td><p>控件名称</p></td>
<td><p>键入您要为其设置属性值的控件的字段的名称。 只使用的控件名称，不完整的语法。 将此参数留空以便为当前窗体或报表设置属性。</p></td>
</tr>
<tr class="even">
<td><p>属性</p></td>
<td><p>请选择要设置的属性。有关可以使用此操作设置的属性的列表，请参阅本文的<strong>说明</strong>部分。</p></td>
</tr>
<tr class="odd">
<td><p>值</p></td>
<td><p>请键入要设置的属性值。对于值为“是”或“否”的属性，使用 <strong>-1</strong> 代表“是”，<strong>0</strong> 代表“否”。</p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>说明

- 您可以使用**SetProperty**操作设置控件的以下属性：**启用**、 **Visible**、**锁定**、**左**、**上**、**宽度**、**高度**、**前景色**、**背景色**，或**标题**。

- 如果为***值*** 参数输入的值无效，则不会发生错误，但 Access 可能会根据解释该参数的方式将属性更改为其他值。

- 只有在以下情况下才能在独立的宏中使用 **SetProperty** 操作：该操作前面的一个操作选择包含您要为其设置属性的控件的窗体或报表。如果窗体或报表未打开，可以使用 **OpenForm** 或 **OpenReport** 操作打开并选择它。如果窗体或报表已经打开，可以使用 **SelectObject** 操作选择它。接下来，可以使用 **SetProperty** 操作设置属性。如果在一个宏中使用 **SetProperty** 操作，而该宏嵌入其中的控件与您要为其设置属性的控件在相同的窗体或报表上，则选择对象不是必需的。

- 要在 VBA 模块中运行 **SetProperty** 操作，请使用 **DoCmd** 对象的 **SetProperty** 方法。

## <a name="example"></a>示例

下面的示例演示如何使用 SetProperty 操作切换的可见性**MyTextBox**文本框。

**示例代码提供者** [Microsoft Access 2010 Programmer's Reference](https://www.amazon.com/Microsoft-Access-2010-Programmers-Reference/dp/8126528125)。

```vb
    Submacro: TestVisible
        SetProperty
            Control Name Text40
            Property Visible
            Value =Not[Text40].[Visible]
    End Submacro
```
