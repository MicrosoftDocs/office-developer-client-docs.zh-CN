---
title: RunDataMacro 宏操作
TOCTitle: RunDataMacro macro action
ms:assetid: fe4ac2f4-7851-7797-ce91-5f2dd3ba4d22
ms:mtpsurl: https://msdn.microsoft.com/library/Ff837269(v=office.15)
ms:contentKeyID: 48548933
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm168493
f1_categories:
- Office.Version=v15
ms.openlocfilehash: c1d540b909a2ac5741719470f5632e34205806ff
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25927982"
---
# <a name="rundatamacro-macro-action"></a>RunDataMacro 宏操作

**适用于**： Access 2013、 Office 2013

您可以使用 **RunDataMacro** 操作来运行指定的数据宏。

## <a name="setting"></a>设置

**RunDataMacro** 操作具有以下参数。

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
<td><p>名称</p></td>
<td><p>要运行的数据宏的名称。</p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>注释

您可以在宏、 指定的数据宏和以下宏事件中使用**RunDataMacro**操作：**[删除后宏事件](after-delete-macro-event.md)**、**[插入后宏事件](after-insert-macro-event.md)** 和**[更新后宏事件](after-update-macro-event.md)**。

数据宏的名称必须包括所附加 （例如， **Comments.AddComment**，而不仅仅是**AddComment**） 到的表。

当您选择要在宏设计器中运行的数据宏时，Access 将确定该数据宏是否需要参数。 如果数据宏需要参数，文本框将显示您可在其中键入参数。

当您运行包含 **RunDataMacro** 操作的宏并且该宏到达 **RunDataMacro** 操作时，Access 将运行调用的数据宏。当调用的数据宏完成时，Access 将返回到原始宏并运行下一操作。

## <a name="example"></a>示例

下面的示例演示如何将参数传递到已命名的数据宏。 使用 RunDataMacro 操作调用 dmGetCurrentServiceRequest tblServiceRequests 表的数据宏。 完成 dmGetCurrentServiceRequest 后，CurrentServiceRequest 变量返回数据宏将被写至 txtCurrentSR 文本框的窗体。

**示例代码提供者** [Microsoft Access 2010 Programmer's Reference](https://www.amazon.com/Microsoft-Access-2010-Programmers-Reference/dp/8126528125)。

```vb
    RunDataMacro
        Macro Name tblServiceRequests.dmGetCurrentServiceRequest
    
    Parameters
        prmAssignedTo =[ID]
    
    SetProperty
        Control Name txtCurrentSR
        Property Value
        Value =[ReturnVars]![CurrentServiceRequest]
```
