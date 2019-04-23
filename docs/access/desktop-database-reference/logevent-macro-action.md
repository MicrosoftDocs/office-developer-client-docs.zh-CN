---
title: LogEvent 宏操作
TOCTitle: LogEvent macro action
ms:assetid: 3578c725-64b9-385e-ef73-a15cdf751c33
ms:mtpsurl: https://msdn.microsoft.com/library/Ff192460(v=office.15)
ms:contentKeyID: 48544148
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 4106e66074975f08a5058aafbfc0c6deac156277
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32289834"
---
# <a name="logevent-macro-action"></a>LogEvent 宏操作

**适用于**：Access 2013、Office 2013

**LogEvent** 操作可向 **USysApplicationLog** 系统表中写入信息。

> [!NOTE]
> **LogEvent** 操作仅适用于数据宏。

## <a name="setting"></a>Setting

**LogEvent** 操作具有以下参数。

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>参数</p></th>
<th><p>必需</p></th>
<th><p>说明</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>说明</strong></p></td>
<td><p>否</p></td>
<td><p>一个用于描述要记录的条件的字符串表达式。该描述不能超过 255 个字符。</p></td>
</tr>
</tbody>
</table>

## <a name="remarks"></a>注解

**LogEvent** 操作可用于向不应使用 [**RaiseError**](raiseerror-macro-action.md) 操作引发错误的 **USysApplicationLog** 系统表中写入状态信息。例如，您可以记录对特定字段的更改，或使用写入 **USysApplicationLog** 的项来帮助您调试宏。

When you use the **LogEvent** action to write to the **USysApplicationLog** table, the **Category** column is automatically set to **User**.

若要查看 **USysApplicationLog** 表，请执行以下步骤：

1.  单击 **"文件"** 菜单，然后单击 **"选项"**。

2.  在 **"Access 选项"** 对话框中，单击 **"当前数据库"** 选项卡。

3.  在 **"导航"** 部分，单击 **"导航选项"**。

4.  在 **"导航选项"** 对话框中，单击 **"显示系统对象"**，然后单击 **"确定"**。

5.  单击 **"确定"** 关闭 **"Access 选项"** 对话框。

