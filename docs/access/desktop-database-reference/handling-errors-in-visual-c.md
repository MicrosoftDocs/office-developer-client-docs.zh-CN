---
title: 在 Visual c + + 中处理错误
TOCTitle: Handling errors in Visual C++
ms:assetid: 75e15699-0c84-1dca-654e-f9ac465c2a30
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249483(v=office.15)
ms:contentKeyID: 48545684
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 99f8a0f8c7b79769fba62b38ef5517781aea4600
ms.sourcegitcommit: 558d09fad81f8d80b5ad0edd21934fc09c098f2c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2018
ms.locfileid: "25945605"
---
# <a name="handling-errors-in-visual-c"></a><span data-ttu-id="0b417-102">在 Visual c + + 中处理错误</span><span class="sxs-lookup"><span data-stu-id="0b417-102">Handling errors in Visual C++</span></span>


<span data-ttu-id="0b417-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="0b417-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="0b417-104">在 COM，大多数操作返回 HRESULT 返回代码，指示函数是否已成功完成。</span><span class="sxs-lookup"><span data-stu-id="0b417-104">In COM, most operations return an HRESULT return code that indicates whether a function completed successfully.</span></span> <span data-ttu-id="0b417-105">\#导入指令生成周围每个"原始"方法或属性的包装代码，并检查返回的 HRESULT。</span><span class="sxs-lookup"><span data-stu-id="0b417-105">The \#import directive generates wrapper code around each "raw" method or property and checks the returned HRESULT.</span></span> <span data-ttu-id="0b417-106">如果 HRESULT 指示故障，包装代码通过调用引发 COM 错误\_com\_问题\_errorex() hresult 返回作为参数的代码。</span><span class="sxs-lookup"><span data-stu-id="0b417-106">If the HRESULT indicates failure, the wrapper code throws a COM error by calling \_com\_issue\_errorex() with the HRESULT return code as an argument.</span></span> <span data-ttu-id="0b417-107">可以在**try-catch**块中捕获 COM error 对象。</span><span class="sxs-lookup"><span data-stu-id="0b417-107">COM error objects can be caught in a **try-catch** block.</span></span> <span data-ttu-id="0b417-108">(为效率的起见，捕获对\_com\_error 对象。)</span><span class="sxs-lookup"><span data-stu-id="0b417-108">(For efficiency's sake, catch a reference to a \_com\_error object.)</span></span>

<span data-ttu-id="0b417-p102">请记住，这些是 ADO 错误：它们是由于 ADO 操作失败而导致的。基础提供程序返回的错误将作为 **Connection** 对象的 **Errors** 集合中的 **Error** 对象出现。</span><span class="sxs-lookup"><span data-stu-id="0b417-p102">Remember, these are ADO errors: they result from the ADO operation failing. Errors returned by the underlying provider appear as **Error** objects in the **Connection** object's **Errors** collection.</span></span>

<span data-ttu-id="0b417-111">\#导入指令仅创建的方法和属性在 ADO.dll 中声明的错误处理例程。</span><span class="sxs-lookup"><span data-stu-id="0b417-111">The \#import directive only creates error-handling routines for methods and properties declared in the ADO .dll.</span></span> <span data-ttu-id="0b417-112">但是，通过编写自己的错误检查宏或内联函数，可以利用此相同的错误处理机制。</span><span class="sxs-lookup"><span data-stu-id="0b417-112">However, you can take advantage of this same error-handling mechanism by writing your own error-checking macro or inline function.</span></span> <span data-ttu-id="0b417-113">有关示例，请参阅主题"Visual C++ 扩展"。</span><span class="sxs-lookup"><span data-stu-id="0b417-113">See the topic Visual C++ Extensions for examples.</span></span>

