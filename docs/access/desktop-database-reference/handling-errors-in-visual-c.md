---
title: 处理 Visual C++ 中的错误
TOCTitle: Handling errors in Visual C++
ms:assetid: 75e15699-0c84-1dca-654e-f9ac465c2a30
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249483(v=office.15)
ms:contentKeyID: 48545684
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: d0e76dc3cc9634a1531a34058bf7a1baf636c94c
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32292025"
---
# <a name="handling-errors-in-visual-c"></a><span data-ttu-id="bcc7f-102">处理 Visual C++ 中的错误</span><span class="sxs-lookup"><span data-stu-id="bcc7f-102">Handling errors in Visual C++</span></span>


<span data-ttu-id="bcc7f-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="bcc7f-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="bcc7f-104">在 COM 中, 大多数操作返回一个 HRESULT 返回代码, 该代码指示函数是否已成功完成。</span><span class="sxs-lookup"><span data-stu-id="bcc7f-104">In COM, most operations return an HRESULT return code that indicates whether a function completed successfully.</span></span> <span data-ttu-id="bcc7f-105">import \#指令在每个 "raw" 方法或属性的周围生成包装代码, 并检查返回的 HRESULT。</span><span class="sxs-lookup"><span data-stu-id="bcc7f-105">The \#import directive generates wrapper code around each "raw" method or property and checks the returned HRESULT.</span></span> <span data-ttu-id="bcc7f-106">如果 HRESULT 指示失败, 则包装代码会通过调用\_com\_问题\_errorex (), 并将 HRESULT 返回代码作为参数来引发 com 错误。</span><span class="sxs-lookup"><span data-stu-id="bcc7f-106">If the HRESULT indicates failure, the wrapper code throws a COM error by calling \_com\_issue\_errorex() with the HRESULT return code as an argument.</span></span> <span data-ttu-id="bcc7f-107">可以在**try-catch**块中捕获 COM error 对象。</span><span class="sxs-lookup"><span data-stu-id="bcc7f-107">COM error objects can be caught in a **try-catch** block.</span></span> <span data-ttu-id="bcc7f-108">(为了提高效率, 请捕获对\_com\_error 对象的引用。)</span><span class="sxs-lookup"><span data-stu-id="bcc7f-108">(For efficiency's sake, catch a reference to a \_com\_error object.)</span></span>

<span data-ttu-id="bcc7f-p102">请记住，这些是 ADO 错误：它们是由于 ADO 操作失败而导致的。基础提供程序返回的错误将作为 **Connection** 对象的 **Errors** 集合中的 **Error** 对象出现。</span><span class="sxs-lookup"><span data-stu-id="bcc7f-p102">Remember, these are ADO errors: they result from the ADO operation failing. Errors returned by the underlying provider appear as **Error** objects in the **Connection** object's **Errors** collection.</span></span>

<span data-ttu-id="bcc7f-111">\#import 指令仅为在 ADO 中声明的方法和属性创建错误处理例程。</span><span class="sxs-lookup"><span data-stu-id="bcc7f-111">The \#import directive only creates error-handling routines for methods and properties declared in the ADO .dll.</span></span> <span data-ttu-id="bcc7f-112">但是，通过编写自己的错误检查宏或内联函数，可以利用此相同的错误处理机制。</span><span class="sxs-lookup"><span data-stu-id="bcc7f-112">However, you can take advantage of this same error-handling mechanism by writing your own error-checking macro or inline function.</span></span> <span data-ttu-id="bcc7f-113">有关示例，请参阅主题"Visual C++ 扩展"。</span><span class="sxs-lookup"><span data-stu-id="bcc7f-113">See the topic Visual C++ Extensions for examples.</span></span>

