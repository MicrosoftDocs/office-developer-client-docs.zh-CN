---
title: 设置窗体、报表和控件的属性
TOCTitle: Set form, report, and control properties
description: 每个窗体、报表、节和控件都有各自的属性设置，可以利用这些属性来更改 Access 2013 中特定项的外观和行为。
ms:assetid: 03349d86-f107-9e49-89df-62f55f3a0735
ms:mtpsurl: https://msdn.microsoft.com/library/Ff844789(v=office.15)
ms:contentKeyID: 48542977
ms.date: 10/16/2018
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm12286
f1_categories:
- Office.Version=v15
localization_priority: Priority
ms.openlocfilehash: bacbdc100d147be8bf4327a5a775b199c79347bb
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32308734"
---
# <a name="set-form-report-and-control-properties"></a>设置窗体、报表和控件的属性

**适用于**：Access 2013、Office 2013

每个窗体、报表、节和控件都有各自的属性设置，可以利用这些属性来更改特定项的外观和行为。使用属性表、宏或 Visual Basic 可以查看并更改属性。

## <a name="set-properties"></a>设置属性

1. 在窗体设计视图或报表设计视图中，选择要设置其属性的控件、节、窗体或报表。可以选择：
    
   - 一个或多个控件。 要选择多个控件，请按住 Shift 键并选择相应控件，或者在要选择的控件上拖动鼠标指针。 如果选择多个控件，属性表将仅显示选中的控件所共有的属性。
    
   - 一个节。 选择要选择的节的节选择器。
    
   - 整个窗体或报表。 选择窗体或报表左上角的窗体选择器或报表选择器。

2. 按如下方法显示属性表：右键单击对象或节，然后选择快捷菜单上的“**属性**”，或者选择工具栏上的“**属性**”。

3. 选择要设置值的属性，然后执行下列操作之一：
    
   - 在属性框中，键入适当的设置或表达式。
    
   - 如果属性框包含箭头，选择该箭头，然后选择列表中的值。
    
   - 如果属性框的右侧出现“**生成**”按钮，请选择该按钮以显示生成器或显示提供生成器选项的对话框。 例如，可以使用代码生成器、宏生成器或查询生成器来设置某些属性。

## <a name="tips"></a>提示

- Microsoft Access 提供了 **“缩放”** 框来键入和查看表达式或其他长属性设置。 若要显示 **“缩放”** 框，选择属性表中的属性框。 按 SHIFT+F2，或右键单击，然后在快捷菜单上选择 **“缩放”**。

- 对于某些控件，可以通过在控件本身中键入属性设置来设置 **ControlSource** 属性。

- 可以为一类控件更改默认属性设置，以便使未来创建的该类控件具有新的默认设置。

- 绑定控件的属性设置可能与控件所绑定到的基础表或基础查询中字段的相应设置不匹配。 如果设置不同，窗体或报表设置通常会覆盖表或查询中的相应设置。

