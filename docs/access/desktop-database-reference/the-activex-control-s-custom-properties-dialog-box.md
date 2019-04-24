---
title: ActiveXA 控件的自定义属性对话框
TOCTitle: ActiveX control custom properties dialog box
description: 在设计视图中设置 ActiveX 控件的属性时，除了使用 Microsoft Access 属性表中的属性列表以外，还可以使用此自定义属性对话框。
ms:assetid: 124cf679-6efc-567a-84d1-8057dec93bde
ms:mtpsurl: https://msdn.microsoft.com/library/Ff845396(v=office.15)
ms:contentKeyID: 48543338
ms.date: 10/16/2018
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm4040
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: f4574abc86e6eacd38721e601d26c8b8fbf0a0d3
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32314103"
---
# <a name="activex-control-custom-properties-dialog-box"></a>ActiveXA 控件的自定义属性对话框

**适用于**：Access 2013、Office 2013

在设置 ActiveX 控件的属性时，您可能需要或更喜欢使用该控件的自定义属性对话框。在设计视图中设置 ActiveX 控件的属性时，除了使用 Microsoft Access 属性表中的属性列表以外，还可以使用自定义属性对话框。

> [!NOTE]
> [!注释] 以上信息仅适用于 Microsoft Access 数据库环境中的 ActiveX 控件。

## <a name="two-ways-to-set-properties"></a>设置属性的两种方法

使用自定义属性对话框的原因在于：并非所有使用 ActiveX 控件的应用程序都提供了 Microsoft Access 中所提供的那种属性表。无论主应用程序提供什么样的界面，自定义属性对话框均会提供一个界面来设置主要的控件属性。

对于某些 ActiveX 控件属性，可以选择下列两个位置之一设置属性：

- Microsoft Access 属性表。
- ActiveX 控件的自定义属性对话框。

对于某些情况，在“设计”视图中只能使用自定义属性对话框设置属性。通常，当设置属性所需的界面在 Microsoft Access 属性表中无法工作时，就属于这种情况。例如，日历控件的 **GridFont** 属性有多个参数，但在 Microsoft Access 属性表中却不能为每个属性设置多个参数。

## <a name="finding-the-custom-properties-dialog-box"></a>查找自定义属性对话框

Not all ActiveX controls provide a custom properties dialog box. To see whether a control provides this custom properties dialog box, look for the **Custom** property in the Microsoft Access property sheet for this control. 如果属性列表包含名称**custom**, 则该控件提供自定义属性对话框。

## <a name="using-the-custom-properties-dialog-box"></a>使用 "自定义属性" 对话框

在 Microsoft Access 属性表中选择 "**自定义**" 属性框后, 选择属性框右侧的 "**生成**" 按钮, 以显示控件的自定义属性对话框, 通常显示为选项卡式对话框。 可以选择一个包含可在其中设置所需属性的界面的选项卡。

在某个选项卡上进行更改后, 通常可以通过选择 "**应用**" 按钮 (如果有的话) 来应用这些更改。 您可以根据需要选择其他选项卡来设置其他属性。 若要批准在自定义属性对话框中所做的所有更改, 请选择 **"确定"** 按钮。 若要返回到 Microsoft Access 属性表而不更改任何属性设置, 请选择 "**取消**" 按钮。

您还可以通过在 "**编辑**" 菜单上选择 "ActiveX 控件**对象**" 命令 (例如, "**日历" 控件对象**) 的 "**属性**" 子命令, 或选择相同的子命令, 来查看 "自定义属性" 对话框ActiveX 控件的快捷菜单。 此外，在 Microsoft Access 属性表中某些 ActiveX 控件属性（如日历控件的 **GridFontColor** 属性）框的右侧有一个“生成器”**** 按钮。 当您选择 "**生成**" 按钮时, 将显示 "自定义属性" 对话框, 并选中相应的选项卡 (例如, "**颜色**")。

