---
title: ExportWithFormatting 宏操作
TOCTitle: ExportWithFormatting Macro Action
ms:assetid: 8926dfa3-bf11-30ab-0f85-46f0a4961784
ms:mtpsurl: https://msdn.microsoft.com/library/Ff197066(v=office.15)
ms:contentKeyID: 48546152
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm159503
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 8a0ca9d2dde2ae5d39fb9159655f37b5140eee3e
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25868015"
---
# <a name="exportwithformatting-macro-action"></a>ExportWithFormatting 宏操作


**适用于**： Access 2013、 Office 2013

可以使用 **ExportWithFormatting** 操作将指定的 Microsoft Access 数据库对象（数据表、窗体、报表、模块或数据访问页）中的数据输出为若干种输出格式。

## <a name="settings"></a>设置

**ExportWithFormatting** 操作具有下列参数。

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
<td><p>包含的数据输出的对象类型。 单击<strong>对象中的<strong>表</strong>（表数据表）、<strong>查询</strong>（用于查询数据表）、 （对于窗体或窗体数据表） 的<strong>窗体</strong>、<strong>报表</strong>、<strong>模块</strong>、<strong>服务器视图</strong>、<strong>存储过程</strong>或<strong>函数</strong>类型</strong>框在宏生成器窗格的<strong>操作参数</strong>部分。 不能输出宏。 如果您想要输出活动对象，请选择与此参数，其类型，但将<strong>对象名称</strong>参数留空。 这是必需参数。 默认值是<strong>表</strong>。</p></td>
</tr>
<tr class="even">
<td><p><strong>对象名称</strong></p></td>
<td><p>包含要输出的数据对象的名称。 <strong>对象名称</strong>框中显示<strong>对象类型</strong>参数所选类型的数据库中的所有对象。 如果在类库数据库中运行包含 <strong>ExportWithFormatting</strong> 操作的宏，Access 将先在该类库数据库中查找具有此名称的对象，然后再在当前数据库中查找。</p></td>
</tr>
<tr class="odd">
<td><p><strong>输出格式</strong></p></td>
<td><p>要用来输出数据的格式类型。可以选择<strong>“Excel 97 - Excel 2003 工作簿(*.xls)”</strong>、<strong>“Excel 二进制工作簿(*.xlsb)”</strong>、<strong>“Excel 工作簿(*.xlsx)”</strong>、<strong>“HTML (*.htm; *.html)”</strong>、<strong>“Microsoft Excel 5.0/95 工作簿(*.xls)”</strong>、<strong>“PDF 格式(*.pdf)”</strong>、<strong>“RTF 格式(*.rtf)”</strong>、<strong>“文本文件(*.txt)”</strong>或<strong>“XPS 格式(*.xps)”</strong>。如果将此参数留空，Access 将提示您提供输出格式。</p></td>
</tr>
<tr class="even">
<td><p><strong>输出文件</strong></p></td>
<td><p>所需的数据，包括完整路径输出文件。 您可以包括标准的文件扩展名为您选择使用<strong>输出格式</strong>参数，输出格式，但不是必需的。 如果将<strong>输出文件</strong>参数留空，Access 将提示您进行了输出文件名称。</p></td>
</tr>
<tr class="odd">
<td><p><strong>自动启动</strong></p></td>
<td><p>指定是否希望相应的软件在<strong>ExportWithFormatting</strong>操作将运行后立即, 启动并打开<strong>输出文件</strong>参数指定的文件。</p></td>
</tr>
<tr class="even">
<td><p><strong>模板文件</strong></p></td>
<td><p>要作为 HTML 文件的模板的文件的路径和文件名。模板文件是包含 Access 独有的 HTML 标记和符号的文本文件。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Encoding</strong></p></td>
<td><p>要用于输出文本或 HTML 数据的字符编码格式的类型。可以选择<strong>“MS-DOS”</strong>、<strong>“Unicode”</strong>或<strong>“Unicode (UTF-8)”</strong>。<strong>“MS-DOS”</strong>参数设置仅适用于文本文件。如果将此参数留空，Access 则通过对文本文件使用 Windows 默认编码，对 HTML 文件使用默认系统编码来输出数据。</p></td>
</tr>
<tr class="even">
<td><p><strong>输出质量</strong></p></td>
<td><p>选择<strong>“打印”</strong>优化打印输出，或者选择<strong>“屏幕”</strong>来优化屏幕上的显示输出。</p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>说明

Access 数据将按所选的格式输出，并且可由使用相同格式的任何程序读取。例如，可将 Access 报表输出为 RTF 格式文档并保留其格式，然后用 Microsoft Word 打开该文档。

如果输出为 HTML 格式的数据库对象，Access 将创建一个文件中包含的数据对象中的 HTML 格式。 **模板文件**参数用于指定要用作.html 文件模板的文件。

使用 **ExportWithFormatting** 操作将数据库对象输出为任意输出格式时，下列规则适用：

  - 可以输出表、查询和窗体数据表中的数据。在输出文件中，数据表中所有字段的显示都与它们在 Access 中一样，但包含 OLE 对象的字段除外。OLE 对象字段的列包含在输出文件中，但这些字段为空。

  - 控件绑定到字段是/否 （切换按钮、 选项按钮或复选框），输出文件将显示值-1 （是） 或 0 （无）。

  - 对于绑定到超链接字段的文本框，无论输出格式如何，输出文件都会显示超链接，只有 MS-DOS 文本除外，在此情况下，超链接显示为普通文本。

  - 如果输出的是窗体视图中的窗体中的数据，则输出文件总是包含该窗体的数据表视图。

  - 在以 HTML 格式输出数据表、窗体或数据访问页时，会创建一个 .html 文件。在以 HTML 格式输出报表时，会为报表中的每一页创建一个 .html 文件。

**ExportWithFormatting** 操作的运行结果与单击 **"外部数据"** 选项卡上 **"导出"** 组中的某个选项类似。该操作的参数对应于 **"导出"** 对话框中的设置。

若要在 Visual Basic for Applications (VBA) 模块中运行 **ExportWithFormatting** 操作，请使用 **DoCmd** 对象的 **OutputTo** 方法。

