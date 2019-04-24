---
title: WorkflowTasks 宏操作
TOCTitle: WorkflowTasks macro action
ms:assetid: 4b299681-b45b-f6d1-2cfe-ebf01712bfc1
ms:mtpsurl: https://msdn.microsoft.com/library/Ff193503(v=office.15)
ms:contentKeyID: 48544684
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm8454
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: 921396edd480e06194d1c3dcbb683aa8556553e2
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32306004"
---
# <a name="workflowtasks-macro-action"></a>WorkflowTasks 宏操作


**适用于**：Access 2013、Office 2013

可以使用 **WorkflowTasks** 操作显示 **“工作流任务”** 对话框。

## <a name="setting"></a>Setting

**WorkflowTasks** 操作具有以下参数。

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
<td><p><strong>记录号</strong></p></td>
<td><p>项目在 Microsoft SharePoint Foundation 列表中的位置, 从<strong>1</strong>开始, 列表中的第一个项目开始, 第二个项目为<strong>2</strong> , 依此类推。 也可以为此参数输入表达式。</p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>注解

  - **WorkflowTasks** 操作可打开 **"工作流任务"** 对话框。此对话框显示可用于指定的项的所有任务。必须为 SharePoint Foundation 中的列表定义工作流。

  - 只有在打开并选择了链接的 SharePoint Foundation 列表后，才可以使用 **WorkflowTasks** 操作。若要打开并选择链接的列表，请使用 **OpenTable** 操作。如果该列表已经打开，请使用 **SelectObject** 操作选择它。

  - **WorkflowTasks** 操作等效于以下操作：当链接的 SharePoint Foundation 列表在数据表视图中处于打开状态时右键单击其中的任意单元格，指向 **"工作流"**，然后单击 **"工作流任务"**。

  - 要在 VBA 模块中运行 **WorkflowTasks** 操作，请使用 **DoCmd** 对象的 **WorkflowTasks** 方法。

