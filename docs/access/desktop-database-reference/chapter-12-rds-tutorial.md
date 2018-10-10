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
# <a name="chapter-12-rds-tutorial"></a><span data-ttu-id="3611c-102">第 12 章：RDS 教程</span><span class="sxs-lookup"><span data-stu-id="3611c-102">Chapter 12: RDS Tutorial</span></span>


<span data-ttu-id="3611c-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="3611c-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="3611c-p101">本教程阐释如何使用 RDS 编程模型来对数据源进行查询和更新。本教程首先介绍完成此任务所需的步骤，然后针对具有 ADO for Windows Foundation Classes (ADO/WFC) 的 Microsoft® Visual Basic Scripting Edition 和 Microsoft® Visual J++® 进行重复说明。</span><span class="sxs-lookup"><span data-stu-id="3611c-p101">This tutorial illustrates using the RDS programming model to query and update a data source. First, it describes the steps necessary to accomplish this task. Then the tutorial is repeated in Microsoft® Visual Basic Scripting Edition and Microsoft® Visual J++®, featuring ADO for Windows Foundation Classes (ADO/WFC).</span></span>

<span data-ttu-id="3611c-107">本教程使用不同语言的代码，主要有以下两个原因：</span><span class="sxs-lookup"><span data-stu-id="3611c-107">This tutorial is coded in different languages for two reasons:</span></span>

  - <span data-ttu-id="3611c-p102">假设 RDS 文档的读者使用 Visual Basic 编码。这使得文档方便了 Visual Basic 编程人员，但对于使用其他语言的编程人员则没有多少用处。</span><span class="sxs-lookup"><span data-stu-id="3611c-p102">The documentation for RDS assumes the reader codes in Visual Basic. This makes the documentation convenient for Visual Basic programmers, but less useful for programmers who use other languages.</span></span>

  - <span data-ttu-id="3611c-110">如果您不太熟悉具体的 RDS 功能，但对于其他语言有所了解，那么可以通过在其他语言中寻求相同的功能来解决问题。</span><span class="sxs-lookup"><span data-stu-id="3611c-110">If you are uncertain about a particular RDS feature and you know a little of another language, you might be able to resolve your question by looking for the same feature expressed in another language.</span></span>

## <a name="how-the-tutorial-is-presented"></a><span data-ttu-id="3611c-111">本教程的表示方式</span><span class="sxs-lookup"><span data-stu-id="3611c-111">How the Tutorial is Presented</span></span>

<span data-ttu-id="3611c-p103">本教程基于 RDS 编程模型，并对该编程模型的每个步骤分别进行讨论，另外，还使用 Visual Basic 代码段举例讲述每个步骤。</span><span class="sxs-lookup"><span data-stu-id="3611c-p103">This tutorial is based on the RDS programming model. It discusses each step of the programming model individually. In addition, it illustrates each step with a fragment of Visual Basic code.</span></span>

<span data-ttu-id="3611c-p104">代码示例使用其他语言重复演示，但是对其很少进行讨论。在采用给定编程语言的教程中，每个步骤都以编程模型和说明性教程中的相应步骤来标记。请使用步骤编号来引用说明性教程中的讨论。</span><span class="sxs-lookup"><span data-stu-id="3611c-p104">The code example is repeated in other languages with minimal discussion. Each step in a given programming language tutorial is marked with the corresponding step in the programming model and descriptive tutorial. Use the number of the step to refer to the discussion in the descriptive tutorial.</span></span>

<span data-ttu-id="3611c-p105">下面对 RDS 编程模型进行了说明。在使用本教程时可将其作为路线图。</span><span class="sxs-lookup"><span data-stu-id="3611c-p105">The RDS programming model is stated below. Use it as a roadmap as you proceed through the tutorial.</span></span>

## <a name="rds-programming-model-with-objects"></a><span data-ttu-id="3611c-120">RDS 编程模型与对象</span><span class="sxs-lookup"><span data-stu-id="3611c-120">RDS Programming Model with Objects</span></span>

  - <span data-ttu-id="3611c-121">指定要在服务器上调用的程序，并获取从客户端引用它的方法（代理）。</span><span class="sxs-lookup"><span data-stu-id="3611c-121">Specify the program to be invoked on the server, and obtain a way (proxy) to refer to it from the client.</span></span>

  - <span data-ttu-id="3611c-p106">调用服务器程序，将参数传递给标识数据源和所发命令的服务器程序。</span><span class="sxs-lookup"><span data-stu-id="3611c-p106">Invoke the server program. Pass parameters to the server program that identifies the data source and the command to issue.</span></span>

  - <span data-ttu-id="3611c-p107">服务器程序通常是通过使用 ADO 从数据源获取 [Recordset](recordset-object-ado.md) 对象。可以选择在服务器上处理 **Recordset** 对象。</span><span class="sxs-lookup"><span data-stu-id="3611c-p107">The server program obtains a [Recordset](recordset-object-ado.md) object from the data source, typically by using ADO. Optionally, the **Recordset** object is processed on the server.</span></span>

  - <span data-ttu-id="3611c-126">服务器程序将最终的 **Recordset** 对象返回给客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="3611c-126">The server program returns the final **Recordset** object to the client application.</span></span>

  - <span data-ttu-id="3611c-127">在客户端上，可以选择将 **Recordset** 对象置为便于可视控件使用的形式。</span><span class="sxs-lookup"><span data-stu-id="3611c-127">On the client, the **Recordset** object is optionally put into a form that can be easily used by visual controls.</span></span>

  - <span data-ttu-id="3611c-128">将对于 **Recordset** 对象进行的更改发回到服务器并将其用于更新数据源。</span><span class="sxs-lookup"><span data-stu-id="3611c-128">Changes to the **Recordset** object are sent back to the server and used to update the data source.</span></span>

