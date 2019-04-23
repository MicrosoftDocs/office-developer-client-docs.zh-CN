---
title: OpenVisualBasicModule 宏操作
TOCTitle: OpenVisualBasicModule macro action
ms:assetid: 26eb31c8-3c65-b17d-46cd-c8967434a7a0
ms:mtpsurl: https://msdn.microsoft.com/library/Ff191906(v=office.15)
ms:contentKeyID: 48543826
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm50916
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: 55af2ce884b26b4c3df219e7d1986e7dc2e4c8ce
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32288278"
---
# <a name="openvisualbasicmodule-macro-action"></a>OpenVisualBasicModule 宏操作

**适用于**：Access 2013、Office 2013

可以使用 **OpenVisualBasicModule** 操作在指定的过程处打开指定的 Visual Basic for Applications (VBA) 模块。此过程可以是 Sub 过程、Function 过程或事件过程。

> [!NOTE]
> 如果数据库不受信任，则不允许执行此操作。 

## <a name="setting"></a>设置

**OpenVisualBasicModule** 操作具有下列参数。

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
<td><p><strong>模块名称</strong></p></td>
<td><p>要打开的模块的名称。 如果要在数据库中的所有标准模块中搜索某个过程，并在该过程那里打开适当的模块，则可以将此参数留空。 如果在类库数据库中运行包含 <strong>OpenVisualBasicModule</strong> 操作的宏，Microsoft Access 将先在该类库数据库中查找具有此名称的模块，然后再在当前数据库中查找。</p></td>
</tr>
<tr class="even">
<td><p><strong>过程名称</strong></p></td>
<td><p>要在打开模块后显示的过程的名称。如果将此参数留空，则在打开模块后将显示其声明节。</p></td>
</tr>
</tbody>
</table>

> [!NOTE]
> 必须在“模块名称”**** 或“过程名称”**** 参数中输入一个有效的名称。


## <a name="remarks"></a>注解

You can use this action to open an event procedure by specifying the **Module Name** argument and the **Procedure Name** argument. 例如, 若要打开窗体 "订单" 上 "PrintInvoice" 按钮的**Click**事件过程, 请将 "**模块名称**" 参数设置为 " **form** ", 并将 "**过程名称**" 参数设置为**PrintInvoice\_**。 To view the event procedure for a form or report, the form or report must be open.

同样，要在类模块中打开某个过程，必须指定模块名称；不过，不需要打开类模块。

要打开私有过程，必须打开包含该过程的模块。

此操作等效于在导航窗格中右键单击模块，然后单击 **"设计视图"**。通过此操作还可以指定过程名称以及在数据库中的标准模块中搜索过程。

> [!TIP]
> [!提示] 您可以在导航窗格中选择模块并将其拖至宏操作行。这样会自动创建打开模块并显示其声明节的 **OpenVisualBasicModule** 操作。

若要在 VBA 模块中运行 **OpenVisualBasicModule** 操作，请使用 **DoCmd** 对象的 **OpenModule** 方法。

