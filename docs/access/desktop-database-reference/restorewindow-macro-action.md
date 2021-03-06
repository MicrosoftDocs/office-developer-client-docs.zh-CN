---
title: RestoreWindow 宏操作
TOCTitle: RestoreWindow macro action
ms:assetid: 507a6452-2be0-a523-1201-0108d2b9d23c
ms:mtpsurl: https://msdn.microsoft.com/library/Ff193815(v=office.15)
ms:contentKeyID: 48544796
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm11103
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: 35637781035b7a449ba574cf5f6c84f2cb5223db
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32306585"
---
# <a name="restorewindow-macro-action"></a>RestoreWindow 宏操作

**适用于**：Access 2013、Office 2013

可以使用 **RestoreWindow** 操作将已最大化或最小化的窗口还原为其原来的大小。

> [!NOTE]
> [!注释] 此操作不能应用于 Visual Basic 编辑器中的代码窗口。有关如何影响代码窗口的信息，请参阅 **WindowState** 属性主题。

## <a name="setting"></a>Setting

**RestoreWindow** 操作不具有任何参数。

## <a name="remarks"></a>注解

此操作对所选的数据库对象有效。如果对象已经最小化，可以先用 **SelectObject** 操作选定它，然后使用 **RestoreWindow** 操作将它还原为其原来的大小。

可以使用 **MoveAndSizeWindow** 操作移动已经还原的窗口或者调整其大小。

**RestoreWindow** 操作等效于单击窗口右上角的 **“还原”** 按钮或者单击窗口 **“控件”** 菜单上的 **“还原”** 命令。

若要在 Visual Basic for Applications (VBA) 模块中运行 **RestoreWindow** 操作，请使用 **DoCmd** 对象的 **Restore** 方法。

