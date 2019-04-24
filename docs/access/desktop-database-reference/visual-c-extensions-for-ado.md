---
title: Visual C++ Extensions for ADO
TOCTitle: Visual C++ Extensions for ADO
ms:assetid: 38048ae0-1dae-9e5e-c569-04011df8b5aa
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249134(v=office.15)
ms:contentKeyID: 48544212
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: fc69d3244cf6faf3aa91fe954e4b39323cf13abf
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32302749"
---
# <a name="visual-c-extensions-for-ado"></a>适用于 ADO 的 Visual C++ 扩展


**适用于**：Access 2013、Office 2013

使用 Visual c + + 编程 ADO 编程的首选方法是使用** \#导入**指令, 如[Microsoft Visual c + + ADO 编程](visual-c-ado-programming.md)中所述。 但是，更早的 ADO 版本为使用 Visual C++ 编程提供了替代方法：Visual C++ Extensions。 本部分介绍了必须维护 Visual c + + 扩展代码的那些功能, 但应使用\#**导入**来编写新的 ADO 代码。

Visual C++ 程序员在用 ADO 检索数据时所面对的一项最繁琐的工作是将作为 VARIANT 数据类型返回的数据转换成 C++ 数据类型，然后将经过转换的数据存储在类或结构中。除了麻烦外，通过 VARIANT 数据类型来检索 C++ 数据会使性能降低。

ADO 提供的接口可以支持将数据检索为本机 C/C++ 数据类型，而不需要通过 VARIANT，并且还提供了预处理器宏来简化接口的使用。因此，该灵活工具更容易使用，并且有很好的性能。

常见的 C/C++ 客户端方案是将 [Recordset](recordset-object-ado.md) 中的记录绑定到包含本机 C/C++ 类型的 C/C++ 结构或类。通过 VARIANT 实现时，这涉及编写从 VARIANT 到 C/C++ 本机类型的转换代码。Visual C++ Extensions for ADO 的目标是使 Visual C++ 程序员更方便地使用此方案。

若要了解有关 Visual C++ Extensions for ADO 的详细信息，请参阅以下主题。

  - [使用 Visual C++ Extensions for ADO](using-visual-c-extensions.md)

  - [Visual C++ Extensions 头](visual-c-extensions-header.md)

  - [在 Visual C++ Extensions 中使用 ADO 的示例](visual-c-extensions-example.md)

