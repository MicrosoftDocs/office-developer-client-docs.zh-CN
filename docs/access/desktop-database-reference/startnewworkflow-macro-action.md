---
title: StartNewWorkflow 宏操作
TOCTitle: StartNewWorkflow macro action
ms:assetid: b3e81a11-b816-0eef-fc70-6d6da7a5a845
ms:mtpsurl: https://msdn.microsoft.com/library/Ff822054(v=office.15)
ms:contentKeyID: 48547206
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm198223
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: 1e37d72754531fc4dd51427eefb355a057d08073
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28698153"
---
# <a name="startnewworkflow-macro-action"></a>StartNewWorkflow 宏操作


**适用于**： Access 2013、 Office 2013

可以使用 **StartNewWorkflow** 操作为链接的 Microsoft SharePoint Foundation 列表中的项启动新工作流。

## <a name="setting"></a>设置

**StartNewWorkflow** 操作具有以下参数。

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
<td><p>在 SharePoint Foundation 列表中，启动与列表中的第一项<strong>1</strong> 、 <strong>2</strong>的第二个项目，依次类推项的位置。 您还可以输入一个表达式为此参数。</p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>说明

  - **StartNewWorkflow** 操作会打开 **"启动新工作流"** 对话框。此对话框显示可用于指定的项的所有工作流。必须先为 SharePoint Foundation 中的列表定义工作流，然后才能使用此操作启动工作流。

  - 只有在打开并选择了链接的 SharePoint 列表后，才可以使用 **StartNewWorkflow** 操作。要打开并选择链接的列表，请使用 **OpenTable** 操作。如果该列表已经打开，请使用 **SelectObject** 操作选择它。

  - **StartNewWorkflow** 操作等效于当链接的 SharePoint 列表在数据表视图中处于打开状态时右键单击其中的任意单元格，指向 **"工作流"**，然后单击 **"启动新工作流"**。

  - 要在 VBA 模块中运行 **StartNewWorkflow** 操作，请使用 **DoCmd** 对象的 **StartNewWorkflow** 方法。

