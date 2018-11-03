---
title: 预见错误
TOCTitle: Anticipating errors
ms:assetid: f2368a03-d446-ab42-b505-d5f5a214c000
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250229(v=office.15)
ms:contentKeyID: 48548645
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: eec7480698676c5da6ea14d1754fc15e42995fe3
ms.sourcegitcommit: 558d09fad81f8d80b5ad0edd21934fc09c098f2c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2018
ms.locfileid: "25944646"
---
# <a name="anticipating-errors"></a>预见错误


**适用于**： Access 2013、 Office 2013

无论如何，错误防范都与错误处理同样重要。最后这一部分简要介绍了您的应用程序可以采取的预防措施，以便降低错误发生可能性。

在尝试使用对象执行操作前，应通过检查 **State** 属性中的值来检查这些对象的状态。例如，如果应用程序使用全局 **Connection** ，请在调用 **Open** 方法前，检查其 **State** 属性以确定它是否已经打开。

- 从用户接受数据的任何程序都必须提供代码对数据进行验证，然后才能将数据发送给数据存储区。不能依赖数据存储区、提供程序、ADO 或编程语言来通知您存在问题。必须检查用户输入的每个字节，确保数据对于所在字段是正确类型，且必填字段不为空。

在试图将任何数据写入数据存储区之前应检查数据。实现这一点的最简单的方法是处理 **WillMove** 事件或 **WillUpdateRecordset** 事件。有关处理 ADO 事件的更全面的讨论，请参阅 [第 7 章：处理 ADO 事件](chapter-7-handling-ado-events.md)。

在试图移动记录指针前，要确保 **Recordset** 对象没有超出 **Recordset** 的边界。如果在 **EOF** 为 True 时尝试 **MovePrev** 或在 **BOF** 为 True 时尝试 **MovePrev** ，将会出现错误。在 **EOF** 和 **BOF** 都为 True 时执行任意 **Move** 方法，都将生成错误。

如果尝试对空 **Recordset** 执行诸如 **Seek** 和 **Find** 这样的操作，也会发生错误。

