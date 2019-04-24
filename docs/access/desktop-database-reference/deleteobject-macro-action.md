---
title: DeleteObject 宏操作
TOCTitle: DeleteObject macro action
ms:assetid: a8deb2a7-4e73-8696-b8c1-3a3939d813f7
ms:mtpsurl: https://msdn.microsoft.com/library/Ff821415(v=office.15)
ms:contentKeyID: 48546912
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm152112
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: dae5718e7b4cb609cb50bd65ee6e2486f4ebaab6
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32294027"
---
# <a name="deleteobject-macro-action"></a>DeleteObject 宏操作

**适用于**：Access 2013、Office 2013

可以使用 **DeleteObject** 操作删除指定的数据库对象。

> [!NOTE]
> [!注释] 如果数据库不受信任，将不允许此操作。 

## <a name="setting"></a>设置

**DeleteObject** 操作具有下列参数。

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
<td><p><strong>对象类型</strong></p></td>
<td><p>要删除的对象的类型。请在“宏生成器”窗格<strong>“操作参数”</strong>部分的<strong>“对象类型”</strong>框中单击<strong>“表”</strong>、<strong>“查询”</strong>、<strong>“窗体”</strong>、<strong>“报表”</strong>、<strong>“宏”</strong>、<strong>“模块”</strong>、<strong>“数据访问页”</strong>、<strong>“服务器视图”</strong>、<strong>“图表”</strong>、<strong>“存储过程”</strong>或<strong>“函数”</strong>。要删除在导航窗格中选择的对象，请将此参数留空。</p></td>
</tr>
<tr class="even">
<td><p><strong>对象名称</strong></p></td>
<td><p>要删除的对象的名称。 “对象名称”<strong></strong>框会显示数据库中属于“对象类型”<strong></strong>参数所选的类型的所有对象。 如果将“对象类型”<strong></strong>框留空，请将此框也留空。 如果在类库数据库中运行包含 <strong>DeleteObject</strong> 操作的宏，Microsoft Office Access 2007 将先在该类库数据库中查找具有此名称的对象，然后再在当前数据库中查找。</p></td>
</tr>
</tbody>
</table>

> [!WARNING]
> If you leave the **Object Type** and **Object Name** boxes blank, Access deletes the object selected in the Navigation Pane without displaying a warning message when it encounters the **DeleteObject** action.

## <a name="remarks"></a>注解

可以使用 **DeleteObject** 操作删除在运行宏期间创建的临时对象。例如，可以使用 **OpenQuery** 操作运行创建临时表的生成表查询。在使用完临时表后，可以使用 **DeleteObject** 操作将其删除。

此操作等效于先在导航窗格中选择对象再按 Del 键，或先在导航窗格中右键单击对象再单击 **"删除"**。

要在 Visual Basic for Applications 模块中运行 **DeleteObject** 操作，可使用 **DoCmd** 对象的 **DeleteObject** 方法。

