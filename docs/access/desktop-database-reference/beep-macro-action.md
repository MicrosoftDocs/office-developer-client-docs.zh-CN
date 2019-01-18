---
title: Beep 宏操作 （访问桌面数据库参考 （英文）
TOCTitle: Beep macro action
ms:assetid: 5ca1600f-7934-3b3d-19fd-f305cda0e5d8
ms:mtpsurl: https://msdn.microsoft.com/library/Ff194572(v=office.15)
ms:contentKeyID: 48545092
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm11853
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: 96051d8389f4b8ba7005c75ccdb5e2780ba17138
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28721470"
---
# <a name="beep-macro-action"></a>Beep 宏操作


**适用于**： Access 2013、 Office 2013

可以使用 **Beep** 操作通过计算机扬声器发出嘟嘟声。

## <a name="setting"></a>设置

**Beep** 操作不具有任何参数。

## <a name="remarks"></a>说明

可以使用 **Beep** 操作在出现以下情况时发出信号：

  - 屏幕发生重要更改。

  - 在控件中输入了错误的数据类型。例如，用户在文本框控件中输入了数值数据。

  - 宏已到达指定的点或已完成其操作。

嘟嘟声的频率和持续时间取决于硬件，因此可能会因计算机而异。

要在 Visual Basic for Applications (VBA) 模块中运行 **Beep** 操作，请使用 **DoCmd** 对象的 **Beep** 方法。

