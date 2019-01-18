---
title: RunApplication 宏操作
TOCTitle: RunApplication macro action
ms:assetid: 29967e6e-c441-b115-3ee6-2299b8a3bc25
ms:mtpsurl: https://msdn.microsoft.com/library/Ff192038(v=office.15)
ms:contentKeyID: 48543885
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm93359
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: e7bf54934c6be215b2be5f32160d74fc2b4ab346
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28721785"
---
# <a name="runapplication-macro-action"></a>RunApplication 宏操作

**适用于**： Access 2013、 Office 2013

<table>
<thead>
<tr class="header">
<th><img src="media/access-alert-security.gif" title="安全说明" alt="Security note" /><strong>安全注释</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>在运行可执行文件或者宏或应用程序中的代码时，请务必小心。可执行文件或代码所执行的操作可能会损害您的计算机和数据的安全性。</td>
</tr>
</tbody>
</table>

可以使用 **RunApplication** 操作在 Microsoft Access 内部运行基于 Microsoft Windows 或基于 MS-DOS 的应用程序，例如 Microsoft Excel、Microsoft Word 或 Microsoft PowerPoint。例如，您可能想将 Excel 电子表格数据贴粘到 Access 数据库中。

> [!NOTE]
> [!注释] 如果数据库不受信任，将不允许此操作。 

## <a name="setting"></a>设置

**RunApplication** 操作具有以下参数。

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
<td><p><strong>命令行</strong></p></td>
<td><p>用来启动应用程序的命令行（包括路径和任何其他必选参数，例如让应用程序在特定模式下运行的开关）。请在“宏生成器”窗格<strong>“操作参数”</strong>部分的<strong>“命令行”</strong>框中输入命令行。这是一个必选参数。</p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>说明

通过此操作选择的应用程序在前台加载和运行。启动应用程序后，包含此操作的宏将继续运行。

通过使用 Microsoft Windows 动态数据交换 (DDE) 功能或剪贴板，您可以在其他应用程序与 Access 之间传输数据。可以使用 **SendKeys** 操作将键击发送到其他应用程序，但 DDE 是更加高效的数据传输方法。还可以使用自动化功能在应用程序之间共享数据。

基于 MS-DOS 的应用程序在 Windows 环境中的 MS-DOS 窗口中运行。

在 Windows 操作系统中，有多种运行应用程序的方法，包括从 Windows 资源管理器中启动程序，使用 **"开始"** 菜单上的 **"运行"** 命令，以及双击 Windows 桌面上的程序图标。

不能在 Visual Basic for Applications (VBA) 模块中运行 **RunApplication** 操作。请改用 VBA **Shell** 函数。

