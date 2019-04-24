---
title: 预测错误
TOCTitle: Anticipating errors
ms:assetid: f2368a03-d446-ab42-b505-d5f5a214c000
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250229(v=office.15)
ms:contentKeyID: 48548645
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: c4bd130ca05527c7761ca587781c1fd4f939ebe9
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32297169"
---
# <a name="anticipating-errors"></a><span data-ttu-id="a3a4b-102">预测错误</span><span class="sxs-lookup"><span data-stu-id="a3a4b-102">Anticipating errors</span></span>


<span data-ttu-id="a3a4b-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="a3a4b-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="a3a4b-p101">无论如何，错误防范都与错误处理同样重要。最后这一部分简要介绍了您的应用程序可以采取的预防措施，以便降低错误发生可能性。</span><span class="sxs-lookup"><span data-stu-id="a3a4b-p101">Error prevention is at least as important as error handling. This final section contains a short list of precautions your application can take to help make errors less likely to occur.</span></span>

<span data-ttu-id="a3a4b-p102">在尝试使用对象执行操作前，应通过检查 **State** 属性中的值来检查这些对象的状态。例如，如果应用程序使用全局 **Connection** ，请在调用 **Open** 方法前，检查其 **State** 属性以确定它是否已经打开。</span><span class="sxs-lookup"><span data-stu-id="a3a4b-p102">Check the state of objects by checking the value in the **State** property before trying to perform an operation using those objects. For example, if your application uses a global **Connection**, check its **State** property to see if it is already open before calling the **Open** method.</span></span>

- <span data-ttu-id="a3a4b-p103">从用户接受数据的任何程序都必须提供代码对数据进行验证，然后才能将数据发送给数据存储区。不能依赖数据存储区、提供程序、ADO 或编程语言来通知您存在问题。必须检查用户输入的每个字节，确保数据对于所在字段是正确类型，且必填字段不为空。</span><span class="sxs-lookup"><span data-stu-id="a3a4b-p103">Any program that accepts data from a user must include code to validate that data before sending it to the data store. You cannot rely on the data store, the provider, ADO, or even your programming language to notify you of problems. You must check every byte entered by your users, making sure that data is the correct type for its field and that required fields are not empty.</span></span>

<span data-ttu-id="a3a4b-p104">在试图将任何数据写入数据存储区之前应检查数据。实现这一点的最简单的方法是处理 **WillMove** 事件或 **WillUpdateRecordset** 事件。有关处理 ADO 事件的更全面的讨论，请参阅 [第 7 章：处理 ADO 事件](chapter-7-handling-ado-events.md)。</span><span class="sxs-lookup"><span data-stu-id="a3a4b-p104">Check the data before you try to write any data to the data store. The easiest way to do so is to handle the **WillMove** event or the **WillUpdateRecordset** event. For a more complete discussion of handling ADO events, see [Chapter 7: Handling ADO Events](chapter-7-handling-ado-events.md).</span></span>

<span data-ttu-id="a3a4b-p105">在试图移动记录指针前，要确保 **Recordset** 对象没有超出 **Recordset** 的边界。如果在 **EOF** 为 True 时尝试 **MovePrev** 或在 **BOF** 为 True 时尝试 **MovePrev** ，将会出现错误。在 **EOF** 和 **BOF** 都为 True 时执行任意 **Move** 方法，都将生成错误。</span><span class="sxs-lookup"><span data-stu-id="a3a4b-p105">Make sure that **Recordset** objects are not beyond the boundaries of the **Recordset** before attempting to move the record pointer. If you try to **MoveNext** when **EOF** is True or **MovePrev** when **BOF** is True, an error will occur. If you perform any of the **Move** methods when both **EOF** and **BOF** are True, an error will be generated.</span></span>

<span data-ttu-id="a3a4b-117">如果尝试对空 **Recordset** 执行诸如 **Seek** 和 **Find** 这样的操作，也会发生错误。</span><span class="sxs-lookup"><span data-stu-id="a3a4b-117">Errors also will occur if you try to perform operations such as **Seek** and **Find** on an empty **Recordset**.</span></span>

