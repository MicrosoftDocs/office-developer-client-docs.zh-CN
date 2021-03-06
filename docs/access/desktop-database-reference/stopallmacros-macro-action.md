---
title: StopAllMacros 宏操作
TOCTitle: StopAllMacros macro action
ms:assetid: 6afbf906-03b8-6e68-bbc9-7a4b141cf1c5
ms:mtpsurl: https://msdn.microsoft.com/library/Ff195440(v=office.15)
ms:contentKeyID: 48545442
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm104968
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: 4e44182dd4290b05a2cfc8fabdf9240819f4b7aa
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32314474"
---
# <a name="stopallmacros-macro-action"></a>StopAllMacros 宏操作


**适用于**：Access 2013、Office 2013

可以使用 **StopAllMacros** 操作停止当前正在运行的所有宏。

## <a name="setting"></a>Setting

**StopAllMacros** 操作不具有任何参数。

## <a name="remarks"></a>注解

当由于某种错误情况而不得不停止所有宏时，通常可以使用此操作。可以在宏中包含此操作的操作行中使用条件表达式。当表达式的计算结果为 **“True”**(–1) 时，Microsoft Access 将停止所有宏。

例如，您可能有一个包含许多复杂操作（包括运行其他宏）的宏，其中的一个操作显示一个消息框。如果用户单击此消息框中的 **"取消"**， **StopAllMacros** 操作可以停止正在运行的所有宏。

如果宏已经使用 **Echo** 或 **SetWarnings** 操作将回响或系统消息的显示关闭， **StopAllMacros** 操作会自动将它们再打开。

此操作在 Visual Basic for Applications (VBA) 模块中不可用。

