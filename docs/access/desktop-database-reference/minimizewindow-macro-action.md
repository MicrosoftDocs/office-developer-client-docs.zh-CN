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
ms.openlocfilehash: c1c8cb8d0f1166b63031925a02186ebc8a1bdac2
ms.sourcegitcommit: 1dd744993ecb4bed241ace874ad26edaef1778b8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/06/2018
ms.locfileid: "25996711"
---
# <a name="minimizewindow-macro-action"></a>MinimizeWindow 宏操作

**适用于**： Access 2013、 Office 2013

如果访问配置为使用重叠窗口而不是选项卡式文档，您可以使用**MinimizeWindow**操作以减少于 Access 窗口的底部小型标题栏的活动窗口。

> [!NOTE]
> [!注释] 此操作不能应用于 Visual Basic 编辑器中的代码窗口。有关如何影响代码窗口的信息，请参阅 **WindowState** 属性主题。

## <a name="setting"></a>设置

**MinimizeWindow** 操作不具有任何参数。

## <a name="remarks"></a>说明

可以使用此操作从屏幕中移除窗口，同时使该数据库对象保持打开状态。还可以使用此操作打开对象而不显示其窗口。若要显示对象，请将 **SelectObject** 操作与 **MaximizeWindow** 或 **RestoreWindow** 操作结合使用。 **RestoreWindow** 操作可将最小化窗口还原为其原来的大小。

**MinimizeWindow** 操作等效于单击窗口右上角的 **"最小化"** 按钮或单击窗口 **"控件"** 菜单上的 **"最小化"**。

**提示**

- 如果要最小化的窗口不是活动窗口，则可能需要先使用 **SelectObject** 操作。

- 若要隐藏导航窗格中，请在导航窗格中参数设置为**是**，然后使用**MinimizeWindow**操作与使用**SelectObject**操作。 **SelectObject**操作中选择的对象可以是在数据库中的任何对象。

- 通过单击 **"视图"** 菜单上的 **"管理此窗口"**，然后单击 **"隐藏"**，可隐藏活动窗口。此时，窗口不是缩小为图标，而是从视图中消失。使用同一菜单上的 **"取消隐藏"** 命令可使该窗口重新显示出来。您可以使用 **RunMenuCommand** 操作通过宏执行上述任一命令。

- 还可以使用 **SetValue** 操作设置窗体的 **"Visible"** 属性，以隐藏或显示窗体的窗口。

若要在 Visual Basic for Applications (VBA) 模块中运行 **MinimizeWindow** 操作，请使用 **DoCmd** 对象的 **Minimize** 方法。

