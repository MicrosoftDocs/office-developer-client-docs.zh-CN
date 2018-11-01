---
title: WorkflowTasks 宏操作
TOCTitle: WorkflowTasks Macro Action
ms:assetid: 4b299681-b45b-f6d1-2cfe-ebf01712bfc1
ms:mtpsurl: https://msdn.microsoft.com/library/Ff193503(v=office.15)
ms:contentKeyID: 48544684
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm8454
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 1bbb04600dc6f7ecea4ce9084b146d3bf696cd6b
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25878120"
---
# <a name="workflowtasks-macro-action"></a>WorkflowTasks 宏操作


**适用于**： Access 2013、 Office 2013

可以使用 **WorkflowTasks** 操作显示 **"工作流任务"** 对话框。

## <a name="setting"></a>设置

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
<td><p>在 Microsoft SharePoint Foundation 列表中，启动与列表中的第一项<strong>1</strong> 、 <strong>2</strong>的第二个项目，依次类推项的位置。 您还可以输入一个表达式为此参数。</p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>说明

  - **WorkflowTasks** 操作可打开 **"工作流任务"** 对话框。此对话框显示可用于指定的项的所有任务。必须为 SharePoint Foundation 中的列表定义工作流。

  - 只有在打开并选择了链接的 SharePoint Foundation 列表后，才可以使用 **WorkflowTasks** 操作。若要打开并选择链接的列表，请使用 **OpenTable** 操作。如果该列表已经打开，请使用 **SelectObject** 操作选择它。

  - **WorkflowTasks** 操作等效于以下操作：当链接的 SharePoint Foundation 列表在数据表视图中处于打开状态时右键单击其中的任意单元格，指向 **"工作流"**，然后单击 **"工作流任务"**。

  - 要在 VBA 模块中运行 **WorkflowTasks** 操作，请使用 **DoCmd** 对象的 **WorkflowTasks** 方法。

