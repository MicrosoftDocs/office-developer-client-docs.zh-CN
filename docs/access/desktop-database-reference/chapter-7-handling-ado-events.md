---
title: 第 7 章：处理 ADO 事件
TOCTitle: 'Chapter 7: Handling ADO events'
ms:assetid: 22924fe2-d00d-8a0c-52f5-2dc6039537ff
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249004(v=office.15)
ms:contentKeyID: 48543709
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: e7357cc60a3bddbf96c2abae39fecfb7107025e2
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32296400"
---
# <a name="chapter-7-handling-ado-events"></a><span data-ttu-id="8be85-102">第 7 章：处理 ADO 事件</span><span class="sxs-lookup"><span data-stu-id="8be85-102">Chapter 7: Handling ADO events</span></span>

<span data-ttu-id="8be85-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="8be85-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="8be85-p101">ADO 事件模型支持某些可在操作开始之前或在完成之后发出*事件*（即通知）的同步和异步 ADO 操作。事件实际上是对应用程序中所定义的事件处理程序例程的调用。</span><span class="sxs-lookup"><span data-stu-id="8be85-p101">The ADO event model supports certain synchronous and asynchronous ADO operations that issue *events*, or notifications, before the operation starts or after it completes. An event is actually a call to an event-handler routine that you define in your application.</span></span>

<span data-ttu-id="8be85-p102">如果为在操作开始之前发生的一组事件提供处理程序函数或过程，则可以检查或修改传递给操作的参数。由于操作尚未执行，因此可以取消该操作或允许它完成。</span><span class="sxs-lookup"><span data-stu-id="8be85-p102">If you provide handler functions or procedures for the group of events that occur before the operation starts, you can examine or modify the parameters that were passed to the operation. Because it has not been executed yet, you can either cancel the operation or allow it to complete.</span></span>

<span data-ttu-id="8be85-p103">如果异步使用 ADO，则在操作完成之后所发生的这组事件尤其重要。例如，操作结束时，执行完成事件将通知启动异步 [Recordset.Open](open-method-ado-recordset.md) 操作的应用程序。</span><span class="sxs-lookup"><span data-stu-id="8be85-p103">The group of events that occur after an operation completes are especially important if you use ADO asynchronously. For example, an application that starts an asynchronous [Recordset.Open](open-method-ado-recordset.md) operation is notified by an execution complete event when the operation concludes.</span></span>

<span data-ttu-id="8be85-110">使用 ADO 事件模型会使应用程序增加一些开销，但与其他处理异步操作的方法相比，它会提供更大的灵活性，例如，通过循环来监视对象的 [State](state-property-ado.md) 属性。</span><span class="sxs-lookup"><span data-stu-id="8be85-110">Using the ADO event model adds some overhead to your application but provides far more flexibility than other methods of dealing with asynchronous operations, such as monitoring the [State](state-property-ado.md) property of an object with a loop.</span></span>

<span data-ttu-id="8be85-111">本章包含以下主题：</span><span class="sxs-lookup"><span data-stu-id="8be85-111">This chapter covers the following topics:</span></span>

- [<span data-ttu-id="8be85-112">ADO 事件处理程序摘要</span><span class="sxs-lookup"><span data-stu-id="8be85-112">ADO event handler summary</span></span>](ado-event-handler-summary.md)
- [<span data-ttu-id="8be85-113">事件类型</span><span class="sxs-lookup"><span data-stu-id="8be85-113">Types of events</span></span>](types-of-events.md)
- [<span data-ttu-id="8be85-114">事件参数</span><span class="sxs-lookup"><span data-stu-id="8be85-114">Event parameters</span></span>](event-parameters.md)
- [<span data-ttu-id="8be85-115">事件处理程序如何协同工作</span><span class="sxs-lookup"><span data-stu-id="8be85-115">How event handlers work together</span></span>](how-event-handlers-work-together.md)
- [<span data-ttu-id="8be85-116">ado 事件实例化 (按语言) (ado)</span><span class="sxs-lookup"><span data-stu-id="8be85-116">ADO event instantiation by language (ADO)</span></span>](ado-event-instantiation-by-language-ado.md)
