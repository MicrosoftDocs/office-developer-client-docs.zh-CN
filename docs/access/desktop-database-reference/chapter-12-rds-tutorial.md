---
title: 第 12 章：RDS 教程
TOCTitle: 'Chapter 12: RDS Tutorial'
ms:assetid: fa44a5e8-e4df-dfdd-d7a1-a870ec3cabdd
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250277(v=office.15)
ms:contentKeyID: 48548837
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: a482da49bb78a74cc68f589c928ffe13dd4a54ad
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25468393"
---
# <a name="chapter-12-rds-tutorial"></a>第 12 章：RDS 教程


**适用于**： Access 2013 |Office 2013

本教程阐释如何使用 RDS 编程模型来对数据源进行查询和更新。本教程首先介绍完成此任务所需的步骤，然后针对具有 ADO for Windows Foundation Classes (ADO/WFC) 的 Microsoft® Visual Basic Scripting Edition 和 Microsoft® Visual J++® 进行重复说明。

本教程使用不同语言的代码，主要有以下两个原因：

  - 假设 RDS 文档的读者使用 Visual Basic 编码。这使得文档方便了 Visual Basic 编程人员，但对于使用其他语言的编程人员则没有多少用处。

  - 如果您不太熟悉具体的 RDS 功能，但对于其他语言有所了解，那么可以通过在其他语言中寻求相同的功能来解决问题。

## <a name="how-the-tutorial-is-presented"></a>本教程的表示方式

本教程基于 RDS 编程模型，并对该编程模型的每个步骤分别进行讨论，另外，还使用 Visual Basic 代码段举例讲述每个步骤。

代码示例使用其他语言重复演示，但是对其很少进行讨论。在采用给定编程语言的教程中，每个步骤都以编程模型和说明性教程中的相应步骤来标记。请使用步骤编号来引用说明性教程中的讨论。

下面对 RDS 编程模型进行了说明。在使用本教程时可将其作为路线图。

## <a name="rds-programming-model-with-objects"></a>RDS 编程模型与对象

  - 指定要在服务器上调用的程序，并获取从客户端引用它的方法（代理）。

  - 调用服务器程序，将参数传递给标识数据源和所发命令的服务器程序。

  - 服务器程序通常是通过使用 ADO 从数据源获取 [Recordset](recordset-object-ado.md) 对象。可以选择在服务器上处理 **Recordset** 对象。

  - 服务器程序将最终的 **Recordset** 对象返回给客户端应用程序。

  - 在客户端上，可以选择将 **Recordset** 对象置为便于可视控件使用的形式。

  - 将对于 **Recordset** 对象进行的更改发回到服务器并将其用于更新数据源。

