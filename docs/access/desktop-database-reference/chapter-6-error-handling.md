---
title: 第 6 章：错误处理
TOCTitle: 'Chapter 6: Error Handling'
ms:assetid: 6ae7343b-b9e0-c4c3-f65c-110f903e573e
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249420(v=office.15)
ms:contentKeyID: 48545440
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 7e00f762ac76023f3f720d8e7341c517b932e3f1
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25465879"
---
# <a name="chapter-6-error-handling"></a>第 6 章：错误处理


**适用于**： Access 2013 |Office 2013

ADO 使用几种不同的方法来将发生的错误通知应用程序。本章讨论在使用 ADO 时可能发生的错误类型，以及如何通知应用程序。本章最后提供了有关如何处理这些错误的建议。

## <a name="how-does-ado-report-errors"></a>ADO 如何报告错误？

ADO 按以下几种方式通知错误：

  - ADO 错误生成运行时错误。请以处理其他任何运行时错误的相同方式来处理这类 ADO 错误，例如，在 Visual Basic 中使用 **On Error** 语句。

  - 程序可以从 OLE DB 接收错误。OLE DB 错误也会生成运行时错误。

  - 如果错误是数据提供程序特有的，则在发生错误时，系统会将一个或多个 **Error** 对象放在用来访问数据存储的 **Connection** 对象的 **Errors** 集合中。

  - 如果引发事件的进程也产生了错误，则错误信息将放在 **Error** 对象中，并作为参数传递给事件。有关事件的详细信息，请参阅 [第 7 章：处理 ADO 事件](chapter-7-handling-ado-events.md)。

  - **Recordset** 的 **Status** 属性可以指示在处理涉及 **Recordset** 的批更新或其他批量操作时所发生的问题。例如， **RecordStatusEnum** 值可以指示架构约束冲突或权限不足。

  - **Record** 或 **Recordset** 的 **Fields** 集合中的每个 **Field** 的 **Status** 属性还可以指示当前记录中特定 **Field** 的问题。例如， **FieldStatusEnum** 值可以指定无法完成的更新或不兼容的数据类型。

以下几节更详细地逐一描述了这些通知方法。

