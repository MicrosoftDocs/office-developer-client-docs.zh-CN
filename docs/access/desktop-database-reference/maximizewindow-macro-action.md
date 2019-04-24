---
title: MaximizeWindow 宏操作
TOCTitle: MaximizeWindow macro action
ms:assetid: 79c9e430-07a7-02b2-ff5a-c6b9ec32c5b6
ms:mtpsurl: https://msdn.microsoft.com/library/Ff196171(v=office.15)
ms:contentKeyID: 48545778
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm196948
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: 262e6781b61018cec3d52dbb930f380d3ff5bd85
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32289747"
---
# <a name="maximizewindow-macro-action"></a>MaximizeWindow 宏操作

**适用于**：Access 2013、Office 2013

如果 Access 配置为使用重叠窗口而不是选项卡式文档, 则可以使用**MaximizeWindow**操作放大活动窗口, 使其填满 Access 窗口。 此操作可使您看到活动窗口中尽可能多的数据库对象。

> [!NOTE]
> [!注释] 此操作不能应用于 Visual Basic 编辑器中的代码窗口。有关如何影响代码窗口的信息，请参阅 **WindowState** 属性主题。

## <a name="setting"></a>Setting

**MaximizeWindow** 操作不具有任何参数。

## <a name="remarks"></a>注解

此操作等效于单击窗口右上角中的 **“最大化”** 按钮或单击窗口 **“控件”** 菜单上的 **“最大化”**。

可以使用 **RestoreWindow** 操作使最大化窗口还原为其原来的大小。

> [!TIP]
> - 如果要最大化的窗口不是活动窗口，可能需要使用 **SelectObject** 操作。
> - When you maximize a window in Access, all other windows are also maximized when you open them or switch to them. However, pop-up forms aren't maximized. If you want a form to maintain its size when other windows are maximized, set its **PopUp** property to **Yes**.

若要在 Visual Basic for Applications 模块中运行 **MaximizeWindow** 操作，请使用 **DoCmd** 对象的 **Maximize** 方法。

