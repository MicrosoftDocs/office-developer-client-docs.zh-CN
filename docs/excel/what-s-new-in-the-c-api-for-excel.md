---
title: 适用于 Excel 的 C API 中的新增功能
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
keywords:
- c api [excel 2007], 新增功能
localization_priority: Normal
ms.assetid: f11552e1-b8ea-4933-b6fc-c452b07eb59d
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 64e3933ec25f0771db5bd36bbf57f3f259cdc8a1
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33439686"
---
# <a name="whats-new-in-the-c-api-for-excel"></a><span data-ttu-id="6580a-104">适用于 Excel 的 C API 中的新增功能</span><span class="sxs-lookup"><span data-stu-id="6580a-104">What's New in the C API for Excel</span></span>

 <span data-ttu-id="6580a-105">**适用于**：Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="6580a-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="6580a-106">microsoft excel 2013 XLL 软件开发工具包 (SDK) 与 microsoft excel 2013 联合提供了对以下功能的支持。</span><span class="sxs-lookup"><span data-stu-id="6580a-106">In conjunction with Microsoft Excel 2013, the Microsoft Excel 2013 XLL Software Development Kit (SDK) includes support for the following features.</span></span>
  
- <span data-ttu-id="6580a-107">**新函数**</span><span class="sxs-lookup"><span data-stu-id="6580a-107">**New Functions**</span></span>
    
    <span data-ttu-id="6580a-108">Microsoft excel 2013 XLL SDK 支持回调到 Excel 2013 中的所有新工作表函数。</span><span class="sxs-lookup"><span data-stu-id="6580a-108">The Microsoft Excel 2013 XLL SDK supports calling back to all of the new worksheet functions in Excel 2013.</span></span> <span data-ttu-id="6580a-109">有关调用 excel 2013 函数的详细信息, 请参阅[从 DLL 或 XLL 调用 Excel](calling-into-excel-from-the-dll-or-xll.md)。</span><span class="sxs-lookup"><span data-stu-id="6580a-109">For more information about calling Excel 2013 functions, see [Calling into Excel from the DLL or XLL](calling-into-excel-from-the-dll-or-xll.md).</span></span>
    
- <span data-ttu-id="6580a-110">**异步用户定义函数**</span><span class="sxs-lookup"><span data-stu-id="6580a-110">**Asynchronous User-defined Functions**</span></span>
    
    <span data-ttu-id="6580a-111">Excel 2013 支持异步调用用户定义的函数 (UDF), 这可以通过启用多个计算同时运行来提高性能。</span><span class="sxs-lookup"><span data-stu-id="6580a-111">Excel 2013 supports calling user-defined functions (UDF) asynchronously, which can improve performance by enabling several calculations to run at the same time.</span></span> <span data-ttu-id="6580a-112">有关异步 udf 的详细信息, 请参阅[异步用户定义函数](asynchronous-user-defined-functions.md)。</span><span class="sxs-lookup"><span data-stu-id="6580a-112">For more information about asynchronous UDFs, see [Asynchronous User-Defined Functions](asynchronous-user-defined-functions.md).</span></span>
    
- <span data-ttu-id="6580a-113">**群集连接器**</span><span class="sxs-lookup"><span data-stu-id="6580a-113">**Cluster Connectors**</span></span>
    
    <span data-ttu-id="6580a-114">群集连接器使 udf 能够在高性能计算群集上运行。</span><span class="sxs-lookup"><span data-stu-id="6580a-114">Cluster connectors enable UDFs to run on high-performance compute clusters.</span></span> <span data-ttu-id="6580a-115">有关创建群集连接器的详细信息, 请参阅[开发 Excel 群集连接器](developing-excel-cluster-connectors.md)。</span><span class="sxs-lookup"><span data-stu-id="6580a-115">For more information about creating cluster connectors, see [Developing Excel Cluster Connectors](developing-excel-cluster-connectors.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="6580a-116">您打算在计算群集上运行的 XLL 加载项必须仅调用群集安全函数。</span><span class="sxs-lookup"><span data-stu-id="6580a-116">XLL add-ins that you intend to run on compute clusters must call only cluster-safe functions.</span></span> <span data-ttu-id="6580a-117">有关可以使用的函数的详细信息, 请参阅[Excel XLL SDK API 函数引用](excel-xll-sdk-api-function-reference.md)和[群集安全函数](cluster-safe-functions.md)。</span><span class="sxs-lookup"><span data-stu-id="6580a-117">For more information about the functions you can use, see [Excel XLL SDK API Function Reference](excel-xll-sdk-api-function-reference.md) and [Cluster Safe Functions](cluster-safe-functions.md).</span></span> 
  
- <span data-ttu-id="6580a-118">**64位支持**</span><span class="sxs-lookup"><span data-stu-id="6580a-118">**64-bit Support**</span></span>
    
    <span data-ttu-id="6580a-119">现在可以编译和链接32位和64位 xll。</span><span class="sxs-lookup"><span data-stu-id="6580a-119">You can now compile and link both 32-bit and 64-bit XLLs.</span></span> <span data-ttu-id="6580a-120">有关详细信息, 请参阅[创建 xll](creating-xlls.md)。</span><span class="sxs-lookup"><span data-stu-id="6580a-120">For more information, see [Creating XLLs](creating-xlls.md).</span></span>
    
## <a name="see-also"></a><span data-ttu-id="6580a-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6580a-121">See also</span></span>



[<span data-ttu-id="6580a-122">开发 Excel XLL</span><span class="sxs-lookup"><span data-stu-id="6580a-122">Developing Excel XLLs</span></span>](developing-excel-xlls.md)
  
[<span data-ttu-id="6580a-123">在 Excel 中使用 C API 进行编程</span><span class="sxs-lookup"><span data-stu-id="6580a-123">Programming with the C API in Excel</span></span>](programming-with-the-c-api-in-excel.md)
  
[<span data-ttu-id="6580a-124">Excel 中的多线程和内存争用</span><span class="sxs-lookup"><span data-stu-id="6580a-124">Multithreading and Memory Contention in Excel</span></span>](multithreading-and-memory-contention-in-excel.md)


[<span data-ttu-id="6580a-125">Getting Started with the Excel XLL SDK</span><span class="sxs-lookup"><span data-stu-id="6580a-125">Getting Started with the Excel XLL SDK</span></span>](getting-started-with-the-excel-xll-sdk.md)

