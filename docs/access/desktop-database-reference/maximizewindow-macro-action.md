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
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28715947"
---
# <a name="maximizewindow-macro-action"></a>MaximizeWindow 宏操作

**适用于**： Access 2013、 Office 2013

如果访问配置为使用重叠窗口而不是选项卡式文档，您可以使用**MaximizeWindow**操作放大活动窗口，使其填充 Access 窗口。 此操作可使您看到活动窗口中尽可能多的数据库对象。

> [!NOTE]
> [!注释] 此操作不能应用于 Visual Basic 编辑器中的代码窗口。有关如何影响代码窗口的信息，请参阅 **WindowState** 属性主题。

## <a name="setting"></a>设置

**MaximizeWindow** 操作不具有任何参数。

## <a name="remarks"></a>说明

此操作等效于单击窗口右上角中的 **"最大化"** 按钮或单击窗口 **"控件"** 菜单上的 **"最大化"**。

可以使用 **RestoreWindow** 操作使最大化窗口还原为其原来的大小。

> [!TIP]
> - 如果要最大化的窗口不是活动窗口，可能需要使用 **SelectObject** 操作。
> - 当在 Access 窗口最大化时，所有其他窗口不会最大化时所打开或切换到它们。 不过，弹出式窗体不会最大化。 如果您希望在其他窗口最大化时保持其大小的窗体，，设置其**PopUp**属性为**是**。

若要在 Visual Basic for Applications 模块中运行 **MaximizeWindow** 操作，请使用 **DoCmd** 对象的 **Maximize** 方法。

