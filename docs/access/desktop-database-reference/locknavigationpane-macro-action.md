---
title: LockNavigationPane 宏操作
TOCTitle: LockNavigationPane macro action
ms:assetid: abf7a989-c7cf-3efa-8df4-3c5b075d0e5f
ms:mtpsurl: https://msdn.microsoft.com/library/Ff821487(v=office.15)
ms:contentKeyID: 48546986
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm172454
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: 7f6ee19edaf2efdc03301e98e709db6dd69f101a
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28717802"
---
# <a name="locknavigationpane-macro-action"></a>LockNavigationPane 宏操作


**适用于**： Access 2013、 Office 2013

可以使用 **LockNavigationPane** 操作防止用户删除导航窗格中显示的数据库对象。

## <a name="setting"></a>设置

**LockNavigationPane** 操作具有以下参数。

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
<td><p><strong>Lock</strong></p></td>
<td><p>选择<strong>是</strong>可锁定导航窗格中，或<strong>否</strong>可解除锁定导航窗格。</p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>说明

通过锁定导航窗格，可防止删除数据库对象或将数据库对象剪切到剪贴板中。 但*不*阻止您执行任何以下操作：

  - 将数据库对象复制到剪贴板中

  - 粘贴剪贴板上的数据库对象

  - 显示或隐藏导航窗格

  - 选择不同的导航窗格组织方案

  - 显示或隐藏导航窗格的某些部分

要在 VBA 模块中运行 **LockNavigationPane** 操作，请使用 **DoCmd** 对象的 **LockNavigationPane** 方法。

