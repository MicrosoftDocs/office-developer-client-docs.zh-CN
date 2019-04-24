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
localization_priority: Normal
ms.openlocfilehash: 32945f0822682a9432d75ed1ac59117dde3cc0e9
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32306809"
---
# <a name="rundatamacro-macro-action"></a>RunDataMacro 宏操作

**适用于**：Access 2013、Office 2013

您可以使用 **RunDataMacro** 操作来运行指定的数据宏。

## <a name="setting"></a>Setting

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
<td><p>Name</p></td>
<td><p>要运行的数据宏的名称。</p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>注解

您可以在宏、名为 data 宏和以下宏事件中使用**RunDataMacro**操作: **[Delete 宏定义](after-delete-macro-event.md)** after 宏事件后**[](after-insert-macro-event.md)** 和**[更新宏事件](after-update-macro-event.md)** 之后。

数据宏的名称必须包含它所附加到的表 (例如**AddComment**, 而不仅仅是**AddComment**)。

当您选择要在宏设计器中运行的数据宏时，Access 将确定该数据宏是否需要参数。 如果数据宏需要参数, 则将显示文本框, 您可以在其中键入参数。

当您运行包含 **RunDataMacro** 操作的宏并且该宏到达 **RunDataMacro** 操作时，Access 将运行调用的数据宏。当调用的数据宏完成时，Access 将返回到原始宏并运行下一操作。

## <a name="example"></a>示例

下面的示例演示如何将参数传递给已命名的数据宏。 tblServiceRequests 表的 dmGetCurrentServiceRequest 数据宏是通过使用 RunDataMacro 操作调用的。 dmGetCurrentServiceRequest 完成后, 返回的 CurrentServiceRequest 变量的数据宏将写入到 txtCurrentSR 文本框。

**示例代码提供方：**[Microsoft Access 2010 程序员参考](https://www.amazon.com/Microsoft-Access-2010-Programmers-Reference/dp/8126528125)。

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
