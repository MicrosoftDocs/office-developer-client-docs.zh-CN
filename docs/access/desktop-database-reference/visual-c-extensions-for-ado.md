---
title: Visual C++ Extensions for ADO
TOCTitle: Visual C++ Extensions for ADO
ms:assetid: 38048ae0-1dae-9e5e-c569-04011df8b5aa
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249134(v=office.15)
ms:contentKeyID: 48544212
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: f7d3a5e876dd98e26c2eb9169a21a8dcd5e532e2
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25467776"
---
# <a name="visual-c-extensions-for-ado"></a>Visual C++ Extensions for ADO


**适用于**： Access 2013 |Office 2013

Visual c + + ADO 编程的首选的方法使用**\#导入**指令，如下所述在[Microsoft Visual c + + ADO 编程](visual-c-ado-programming.md)。 但是，更早的 ADO 版本为使用 Visual C++ 编程提供了替代方法：Visual C++ Extensions。 本节介绍此功能的那些必须维护 Visual c + + Extensions 代码，但应通过编写新的 ADO 代码\#**导入**。

Visual C++ 程序员在用 ADO 检索数据时所面对的一项最繁琐的工作是将作为 VARIANT 数据类型返回的数据转换成 C++ 数据类型，然后将经过转换的数据存储在类或结构中。除了麻烦外，通过 VARIANT 数据类型来检索 C++ 数据会使性能降低。

ADO 提供的接口可以支持将数据检索为本机 C/C++ 数据类型，而不需要通过 VARIANT，并且还提供了预处理器宏来简化接口的使用。因此，该灵活工具更容易使用，并且有很好的性能。

常见的 C/C++ 客户端方案是将 [Recordset](recordset-object-ado.md) 中的记录绑定到包含本机 C/C++ 类型的 C/C++ 结构或类。通过 VARIANT 实现时，这涉及编写从 VARIANT 到 C/C++ 本机类型的转换代码。Visual C++ Extensions for ADO 的目标是使 Visual C++ 程序员更方便地使用此方案。

若要了解有关 Visual C++ Extensions for ADO 的详细信息，请参阅以下主题。

  - [使用 Visual C++ Extensions for ADO](using-visual-c-extensions.md)

  - [Visual C++ Extensions 头](visual-c-extensions-header.md)

  - [在 Visual C++ Extensions 中使用 ADO 的示例](visual-c-extensions-example.md)

