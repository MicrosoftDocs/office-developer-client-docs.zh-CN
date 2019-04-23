---
title: MinimizeWindow 宏操作
TOCTitle: MinimizeWindow macro action
ms:assetid: 3a92b654-15ce-1ed1-63e0-eed927dbe26c
ms:mtpsurl: https://msdn.microsoft.com/library/Ff192648(v=office.15)
ms:contentKeyID: 48544265
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm174420
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: 9f7c4ab535010dc0329673fd04721615f6eb3cd8
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32288881"
---
# <a name="minimizewindow-macro-action"></a>MinimizeWindow 宏操作

**适用于**：Access 2013、Office 2013

如果 Access 配置为使用重叠窗口而不是选项卡式文档, 则可以使用**MinimizeWindow**操作将活动窗口缩小为 Access 窗口底部的小标题栏。

> [!NOTE]
> [!注释] 此操作不能应用于 Visual Basic 编辑器中的代码窗口。有关如何影响代码窗口的信息，请参阅 **WindowState** 属性主题。

## <a name="setting"></a>Setting

**MinimizeWindow** 操作不具有任何参数。

## <a name="remarks"></a>注解

可以使用此操作从屏幕中移除窗口，同时使该数据库对象保持打开状态。还可以使用此操作打开对象而不显示其窗口。若要显示对象，请将 **SelectObject** 操作与 **MaximizeWindow** 或 **RestoreWindow** 操作结合使用。 **RestoreWindow** 操作可将最小化窗口还原为其原来的大小。

**MinimizeWindow** 操作等效于单击窗口右上角的 **"最小化"** 按钮或单击窗口 **"控件"** 菜单上的 **"最小化"**。

**提示**

- 如果要最小化的窗口不是活动窗口，则可能需要先使用 **SelectObject** 操作。

- To hide the Navigation Pane, use the **SelectObject** action with the In Navigation Pane argument set to **Yes** and then use the **MinimizeWindow** action. The object you select in the **SelectObject** action can be any object in the database.

- 通过单击 **"视图"** 菜单上的 **"管理此窗口"**，然后单击 **"隐藏"**，可隐藏活动窗口。此时，窗口不是缩小为图标，而是从视图中消失。使用同一菜单上的 **"取消隐藏"** 命令可使该窗口重新显示出来。您可以使用 **RunMenuCommand** 操作通过宏执行上述任一命令。

- 还可以使用 **SetValue** 操作设置窗体的 **"Visible"** 属性，以隐藏或显示窗体的窗口。

若要在 Visual Basic for Applications (VBA) 模块中运行 **MinimizeWindow** 操作，请使用 **DoCmd** 对象的 **Minimize** 方法。

