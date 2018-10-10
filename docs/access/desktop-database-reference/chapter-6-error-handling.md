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
# <a name="chapter-6-error-handling"></a><span data-ttu-id="83f76-102">第 6 章：错误处理</span><span class="sxs-lookup"><span data-stu-id="83f76-102">Chapter 6: Error Handling</span></span>


<span data-ttu-id="83f76-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="83f76-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="83f76-p101">ADO 使用几种不同的方法来将发生的错误通知应用程序。本章讨论在使用 ADO 时可能发生的错误类型，以及如何通知应用程序。本章最后提供了有关如何处理这些错误的建议。</span><span class="sxs-lookup"><span data-stu-id="83f76-p101">ADO uses several different methods to notify an application of errors that occur. This chapter discusses the types of errors that can occur when you are using ADO and how your application is notified. It concludes by making suggestions about how to handle those errors.</span></span>

## <a name="how-does-ado-report-errors"></a><span data-ttu-id="83f76-107">ADO 如何报告错误？</span><span class="sxs-lookup"><span data-stu-id="83f76-107">How Does ADO Report Errors?</span></span>

<span data-ttu-id="83f76-108">ADO 按以下几种方式通知错误：</span><span class="sxs-lookup"><span data-stu-id="83f76-108">ADO notifies you about errors in several ways:</span></span>

  - <span data-ttu-id="83f76-p102">ADO 错误生成运行时错误。请以处理其他任何运行时错误的相同方式来处理这类 ADO 错误，例如，在 Visual Basic 中使用 **On Error** 语句。</span><span class="sxs-lookup"><span data-stu-id="83f76-p102">ADO errors generate a run-time error. Handle an ADO error the same way you would any other run-time error, such as using an **On Error** statement in Visual Basic.</span></span>

  - <span data-ttu-id="83f76-p103">程序可以从 OLE DB 接收错误。OLE DB 错误也会生成运行时错误。</span><span class="sxs-lookup"><span data-stu-id="83f76-p103">Your program can receive errors from OLE DB. An OLE DB error generates a run-time error as well.</span></span>

  - <span data-ttu-id="83f76-113">如果错误是数据提供程序特有的，则在发生错误时，系统会将一个或多个 **Error** 对象放在用来访问数据存储的 **Connection** 对象的 **Errors** 集合中。</span><span class="sxs-lookup"><span data-stu-id="83f76-113">If the error is specific to your data provider, one or more **Error** objects are placed in the **Errors** collection of the **Connection** object that was used to access the data store when the error occurred.</span></span>

  - <span data-ttu-id="83f76-p104">如果引发事件的进程也产生了错误，则错误信息将放在 **Error** 对象中，并作为参数传递给事件。有关事件的详细信息，请参阅 [第 7 章：处理 ADO 事件](chapter-7-handling-ado-events.md)。</span><span class="sxs-lookup"><span data-stu-id="83f76-p104">If the process that raised an event also produced an error, error information is placed in an **Error** object and passed as a parameter to the event. See [Chapter 7: Handling ADO Events](chapter-7-handling-ado-events.md) for more information about events.</span></span>

  - <span data-ttu-id="83f76-p105">**Recordset** 的 **Status** 属性可以指示在处理涉及 **Recordset** 的批更新或其他批量操作时所发生的问题。例如， **RecordStatusEnum** 值可以指示架构约束冲突或权限不足。</span><span class="sxs-lookup"><span data-stu-id="83f76-p105">Problems that occur when processing batch updates or other bulk operations involving a **Recordset** can be indicated by the **Status** property of the **Recordset**. For example, schema constraint violations or insufficient permissions can be specified by **RecordStatusEnum** values.</span></span>

  - <span data-ttu-id="83f76-p106">**Record** 或 **Recordset** 的 **Fields** 集合中的每个 **Field** 的 **Status** 属性还可以指示当前记录中特定 **Field** 的问题。例如， **FieldStatusEnum** 值可以指定无法完成的更新或不兼容的数据类型。</span><span class="sxs-lookup"><span data-stu-id="83f76-p106">Problems that occur involving a particular **Field** in the current record are also indicated by the **Status** property of each **Field** in the **Fields** collection of the **Record** or **Recordset**. For example, updates that could not be completed or incompatible data types can be specified by **FieldStatusEnum** values.</span></span>

<span data-ttu-id="83f76-120">以下几节更详细地逐一描述了这些通知方法。</span><span class="sxs-lookup"><span data-stu-id="83f76-120">The following sections describe each of these notification methods in more detail.</span></span>

