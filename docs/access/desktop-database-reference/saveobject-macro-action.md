---
title: SaveObject 宏操作
TOCTitle: SaveObject macro action
ms:assetid: 85716dfc-f76f-ca47-cc40-f8f88162f85a
ms:mtpsurl: https://msdn.microsoft.com/library/Ff196789(v=office.15)
ms:contentKeyID: 48546060
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm116962
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: cf6fe02616134f864a0e07092951ab9cf49aadbc
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32308930"
---
# <a name="saveobject-macro-action"></a>SaveObject 宏操作

**适用于**：Access 2013、Office 2013

可以使用 **SaveObject** 操作保存指定的 Microsoft Access 对象，如果未指定任何对象，则可以保存活动对象。在某些情况下，还可以用新名称保存活动对象（这与 **“快速访问工具栏”** 上的 **“另存为”** 命令的作用相同）。

> [!NOTE]
> 如果数据库不受信任，则不允许执行此操作。 

## <a name="setting"></a>设置

**SaveObject** 操作具有下列参数。

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
<td><p>要保存的对象的类型。请在“宏生成器”窗格<strong>“操作参数”</strong>部分的<strong>“对象类型”</strong>框中单击<strong>“表”</strong>、<strong>“查询”</strong>、<strong>“窗体”</strong>、<strong>“报表”</strong>、<strong>“宏”</strong>、<strong>“模块”</strong>、<strong>“数据访问页”</strong>、<strong>“服务器视图”</strong>、<strong>“图表”</strong>、<strong>“存储过程”</strong>或<strong>“函数”</strong>。要选择活动对象，请将此参数留空。如果在此参数中选择了一种对象类型，则必须在“对象名称”<strong></strong>参数中选择现有对象的名称。</p></td>
</tr>
<tr class="even">
<td><p><strong>对象名称</strong></p></td>
<td><p>要保存的对象的名称。 <strong>“对象名称”</strong>框会显示数据库中属于“对象类型”<strong></strong>参数所选的类型的所有对象。 如果将“对象类型”<strong></strong>参数留空，则可将此参数留空以保存活动对象，在某些情况下，也可以在此参数中输入一个新名称，用此新名称来保存活动对象。 如果输入新名称，该名称必须遵循 Microsoft Access 对象的标准命名约定。</p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>注解

**SaveObject** 操作可用于用户能够显式地打开和保存的所有数据库对象。 指定的对象必须处于打开状态，**SaveObject** 操作才会对其有作用。 此操作等效于选择一个对象，然后通过单击 **“快速访问工具栏”** 上的 **“保存”** 来保存该对象。 

将“对象类型”**** 参数留空并在“对象名称”**** 参数中输入一个新名称等效于以下操作：单击 **“快速访问工具栏”** 上的 **“另存为”**，然后为活动对象输入一个新名称。 通过使用 **SaveObject** 操作，您可以指定要保存的对象以及执行宏中的 **“另存为”** 命令。

> [!NOTE]
> 不能使用 **SaveObject** 操作用新名称保存以下任何一项：
> - "窗体" 视图或 "数据表" 视图中的窗体
> - 打印预览中的报表
> - 一个模块
> - "数据表" 视图或 "打印预览" 中的服务器视图
> - 页面视图中的数据访问页
> - 数据表视图或打印预览中的表
> - 数据表视图或打印预览中的查询
> - 数据表视图或打印预览中的存储过程

无论是在当前数据库中运行的宏中执行，还是在类库数据库中运行的宏中执行，**SaveObject** 操作总是将指定对象或活动对象保存在创建该对象的数据库中。

If you save the active object with a new name, but the name is the same as the name of an existing object of this type, a dialog box asks if you want to overwrite the existing object. If you've set the **Warnings On** argument of the **SetWarnings** action to **No**, the dialog box isn't displayed and the old object is automatically overwritten.

若要在 Visual Basic for Applications (VBA) 模块中运行 **SaveObject** 操作，请使用 **DoCmd** 对象的 **Save** 方法。

