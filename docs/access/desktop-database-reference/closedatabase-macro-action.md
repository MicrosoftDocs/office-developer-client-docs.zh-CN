---
title: CloseDatabase 宏操作
TOCTitle: CloseDatabase Macro Action
ms:assetid: c4b4278d-932c-99f6-da2d-8953109b44b3
ms:mtpsurl: https://msdn.microsoft.com/library/Ff823085(v=office.15)
ms:contentKeyID: 48547598
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 42ba5925c35081f612bd4a81b49f3c2b16cf61dd
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25876636"
---
# <a name="closedatabase-macro-action"></a>CloseDatabase 宏操作


**适用于**： Access 2013、 Office 2013

可以使用 **CloseDatabase** 操作关闭当前数据库。

## <a name="setting"></a>设置

**CloseDatabase** 操作不具有任何参数。

## <a name="remarks"></a>说明

  - Access 将不会运行宏中位于 **CloseDatabase** 操作之后的任何操作。

  - 此操作具有相同的效果单击**文件**选项卡，然后单击**关闭数据库**。 在运行 **CloseDatabase** 操作时，如果有任何未保存的对象处于打开状态，则显示的对话框将与单击 **"关闭数据库"** 时显示的对话框相同。

  - 要在 Visual Basic for Applications (VBA) 模块中运行 **CloseDatabase** 操作，请使用 **DoCmd** 对象的 **CloseDatabase** 方法。

