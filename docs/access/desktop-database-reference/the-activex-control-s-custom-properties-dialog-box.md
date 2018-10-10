---
title: ActiveX 控件的自定义属性对话框
TOCTitle: ActiveX Control's Custom Properties Dialog Box
ms:assetid: 124cf679-6efc-567a-84d1-8057dec93bde
ms:mtpsurl: https://msdn.microsoft.com/library/Ff845396(v=office.15)
ms:contentKeyID: 48543338
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm4040
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 6f5924d04e9ea4febee1434f6ef99f95b02eab6b
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25467530"
---
# <a name="activex-controls-custom-properties-dialog-box"></a>ActiveX 控件的自定义属性对话框

**适用于**： Access 2013 |Office 2013

在设置 ActiveX 控件的属性时，您可能需要或更喜欢使用该控件的自定义属性对话框。在设计视图中设置 ActiveX 控件的属性时，除了使用 Microsoft Access 属性表中的属性列表以外，还可以使用自定义属性对话框。

> [!NOTE]
> [!注释] 以上信息仅适用于 Microsoft Access 数据库环境中的 ActiveX 控件。



## <a name="two-ways-to-set-properties"></a>设置属性的两种方法

使用自定义属性对话框的原因在于：并非所有使用 ActiveX 控件的应用程序都提供了 Microsoft Access 中所提供的那种属性表。无论主应用程序提供什么样的界面，自定义属性对话框均会提供一个界面来设置主要的控件属性。

对于某些 ActiveX 控件属性，可以选择下列两个位置之一来设置属性：

  - Microsoft Access 属性表。

  - ActiveX 控件的自定义属性对话框。

对于某些情况，在"设计"视图中只能使用自定义属性对话框设置属性。通常，当设置属性所需的界面在 Microsoft Access 属性表中无法工作时，就属于这种情况。例如，日历控件的 **GridFont** 属性有多个参数，但在 Microsoft Access 属性表中却不能为每个属性设置多个参数。

## <a name="finding-the-custom-properties-dialog-box"></a>查找自定义属性对话框

并非所有的 ActiveX 控件提供自定义属性对话框。 若要查看控件是否提供此自定义属性对话框中，此控件的 Microsoft Access 属性表中的**自定义**属性的外观。 如果属性的列表包含**自定义**的名称，控件将提供自定义属性对话框。

## <a name="using-the-custom-properties-dialog-box"></a>使用自定义属性对话框

单击 Microsoft Access 属性表在 **自定义** 属性框，再单击右侧的属性框中以显示控件的自定义属性对话框，通常显示为选项卡式的对话框的 **生成** 按钮。选择包含要设置的属性的界面的选项卡。

一个选项卡上做出更改后，您可以应用这些更改立即通过单击**应用**按钮 （如果提供）。 您可以单击其他选项卡，根据需要设置其他属性。 要接受所有更改在自定义属性对话框中，单击**确定**按钮。 若要返回的 Microsoft Access 属性表而不更改属性的任何设置，请单击**取消**按钮。

您还可以查看自定义属性对话框中，单击**编辑**菜单上的 ActiveX 控件 （例如， **Calendar 控件对象**） 中的**对象**命令**属性**子命令或通过单击同一子命令ActiveX 控件的快捷菜单。 此外，在 Microsoft Access 属性表中的 ActiveX 控件，如**GridFontColor**属性的日历控件中，有些属性具有属性框右侧的**生成**按钮。 单击**生成**按钮，将显示自定义属性对话框中，选择适当的选项卡 （例如，**颜色**）。

