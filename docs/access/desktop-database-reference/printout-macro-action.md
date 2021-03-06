---
title: PrintOut 宏操作
TOCTitle: PrintOut macro action
ms:assetid: 13688158-1cf1-4b2e-d90a-271c8890e413
ms:mtpsurl: https://msdn.microsoft.com/library/Ff845432(v=office.15)
ms:contentKeyID: 48543368
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm1697
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: 04212a8bf63d5039c6548463612f006f0d116229
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32301405"
---
# <a name="printout-macro-action"></a>PrintOut 宏操作

**适用于**：Access 2013、Office 2013

可以使用 **PrintOut** 操作来打印打开的数据库中的活动对象。可以打印数据表、报表、窗体、数据访问页和模块。

> [!NOTE]
> 如果数据库不受信任，则不允许执行此操作。 

## <a name="setting"></a>设置

**PrintOut** 操作具有下列参数。

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
<td><p><strong>打印范围</strong></p></td>
<td><p>要打印的范围。请在“宏生成器”窗格<strong>“操作参数”</strong>部分的<strong>“打印范围”</strong>框中单击<strong>“全部”</strong>（用户可以打印所有对象）、<strong>“选中内容”</strong>（用户可以打印该对象的选定部分）或<strong>“页”</strong>（用户可以在“开始页码”<strong></strong>和“结束页码”<strong></strong>参数中指定页范围）。默认值为<strong>“全部”</strong>。</p></td>
</tr>
<tr class="even">
<td><p><strong>开始页码</strong></p></td>
<td><p>要打印的第一页。打印从此页顶部开始。如果在<strong>“打印范围”</strong>框中选择<strong>“页”</strong>，则此参数是必选参数。</p></td>
</tr>
<tr class="odd">
<td><p><strong>结束页码</strong></p></td>
<td><p>要打印的最后一页。打印在此页底部结束。如果在<strong>“打印范围”</strong>框中选择<strong>“页”</strong>，则此参数是必选参数。</p></td>
</tr>
<tr class="even">
<td><p><strong>Print Quality</strong></p></td>
<td><p>打印质量。 请单击<strong>“高品质”</strong>、<strong>“中品质”</strong>、<strong>“低品质”</strong>或<strong>“草稿”</strong>。 质量越低，对象的打印速度就越快。 默认值为<strong>“高品质”</strong>。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Copies</strong></p></td>
<td><p>要打印的份数。 默认值为 1。</p></td>
</tr>
<tr class="even">
<td><p><strong>逐份打印</strong></p></td>
<td><p>单击<strong>“是”</strong>（进行分页）或<strong>“否”</strong>（不进行分页）。如果此参数设置为<strong>“否”</strong>，对象的打印速度可能会更快。默认值为<strong>“是”</strong>。</p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>注解

此操作类似于选择某个对象，单击 **"文件"** 选项卡，然后单击 **"打印"**。但是，在执行此操作时，不会出现 **"打印"** 对话框。

> [!TIP]
> [!提示] 如果您有经常使用的特定打印设置，请创建一个包含 **PrintOut** 操作的宏，并让该操作的参数使用这些设置。

此操作的参数与 **"打印"** 对话框中的选项相对应。但是，与 **FindRecord** 操作和 **"查找和替换"** 对话框不同，这些参数设置并不与 **"打印"** 对话框选项共享。

要在 Visual Basic for Applications (VBA) 模块中运行 **PrintOut** 操作，请使用 **DoCmd** 对象的 **PrintOut** 方法。

