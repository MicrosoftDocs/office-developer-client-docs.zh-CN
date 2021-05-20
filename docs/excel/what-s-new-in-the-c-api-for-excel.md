---
title: 适用于开发人员的 C API 的Excel
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
keywords:
- c api [excel 2007]，新增功能
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
# <a name="whats-new-in-the-c-api-for-excel"></a><span data-ttu-id="1762f-104">适用于开发人员的 C API 的Excel</span><span class="sxs-lookup"><span data-stu-id="1762f-104">What's New in the C API for Excel</span></span>

 <span data-ttu-id="1762f-105">**适用于**：Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="1762f-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="1762f-106">XLL Microsoft Excel 2013 Sdk Microsoft Excel 2013 SDK (SDK) 支持以下功能。</span><span class="sxs-lookup"><span data-stu-id="1762f-106">In conjunction with Microsoft Excel 2013, the Microsoft Excel 2013 XLL Software Development Kit (SDK) includes support for the following features.</span></span>
  
- <span data-ttu-id="1762f-107">**新函数**</span><span class="sxs-lookup"><span data-stu-id="1762f-107">**New Functions**</span></span>
    
    <span data-ttu-id="1762f-108">XLL SDK Microsoft Excel 2013 2013 中所有新工作表函数的Excel调用。</span><span class="sxs-lookup"><span data-stu-id="1762f-108">The Microsoft Excel 2013 XLL SDK supports calling back to all of the new worksheet functions in Excel 2013.</span></span> <span data-ttu-id="1762f-109">有关调用 2013 Excel，请参阅从 DLL 或[XLL Excel调用代码](calling-into-excel-from-the-dll-or-xll.md)。</span><span class="sxs-lookup"><span data-stu-id="1762f-109">For more information about calling Excel 2013 functions, see [Calling into Excel from the DLL or XLL](calling-into-excel-from-the-dll-or-xll.md).</span></span>
    
- <span data-ttu-id="1762f-110">**异步用户定义函数**</span><span class="sxs-lookup"><span data-stu-id="1762f-110">**Asynchronous User-defined Functions**</span></span>
    
    <span data-ttu-id="1762f-111">Excel 2013 支持异步调用 (UDF) 用户定义函数，这可以通过允许多个计算同时运行来提高性能。</span><span class="sxs-lookup"><span data-stu-id="1762f-111">Excel 2013 supports calling user-defined functions (UDF) asynchronously, which can improve performance by enabling several calculations to run at the same time.</span></span> <span data-ttu-id="1762f-112">有关异步 UDF 详细信息，请参阅 [Asynchronous User-Defined Functions](asynchronous-user-defined-functions.md)。</span><span class="sxs-lookup"><span data-stu-id="1762f-112">For more information about asynchronous UDFs, see [Asynchronous User-Defined Functions](asynchronous-user-defined-functions.md).</span></span>
    
- <span data-ttu-id="1762f-113">**群集连接器**</span><span class="sxs-lookup"><span data-stu-id="1762f-113">**Cluster Connectors**</span></span>
    
    <span data-ttu-id="1762f-114">群集连接器使 UDF 能够运行在高性能计算群集上。</span><span class="sxs-lookup"><span data-stu-id="1762f-114">Cluster connectors enable UDFs to run on high-performance compute clusters.</span></span> <span data-ttu-id="1762f-115">有关创建群集连接器的信息，请参阅 Developing [Excel Cluster Connectors。](developing-excel-cluster-connectors.md)</span><span class="sxs-lookup"><span data-stu-id="1762f-115">For more information about creating cluster connectors, see [Developing Excel Cluster Connectors](developing-excel-cluster-connectors.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="1762f-116">打算在计算群集上运行的 XLL 加载项只能调用群集安全函数。</span><span class="sxs-lookup"><span data-stu-id="1762f-116">XLL add-ins that you intend to run on compute clusters must call only cluster-safe functions.</span></span> <span data-ttu-id="1762f-117">有关可以使用的函数详细信息，请参阅Excel [XLL SDK API 函数](excel-xll-sdk-api-function-reference.md)参考和群集[保险箱函数](cluster-safe-functions.md)。</span><span class="sxs-lookup"><span data-stu-id="1762f-117">For more information about the functions you can use, see [Excel XLL SDK API Function Reference](excel-xll-sdk-api-function-reference.md) and [Cluster Safe Functions](cluster-safe-functions.md).</span></span> 
  
- <span data-ttu-id="1762f-118">**64 位支持**</span><span class="sxs-lookup"><span data-stu-id="1762f-118">**64-bit Support**</span></span>
    
    <span data-ttu-id="1762f-119">现在可以编译和链接 32 位和 64 位 XLL。</span><span class="sxs-lookup"><span data-stu-id="1762f-119">You can now compile and link both 32-bit and 64-bit XLLs.</span></span> <span data-ttu-id="1762f-120">有关详细信息，请参阅创建[XLL。](creating-xlls.md)</span><span class="sxs-lookup"><span data-stu-id="1762f-120">For more information, see [Creating XLLs](creating-xlls.md).</span></span>
    
## <a name="see-also"></a><span data-ttu-id="1762f-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1762f-121">See also</span></span>



[<span data-ttu-id="1762f-122">开发 Excel XLL</span><span class="sxs-lookup"><span data-stu-id="1762f-122">Developing Excel XLLs</span></span>](developing-excel-xlls.md)
  
[<span data-ttu-id="1762f-123">在 Excel 中使用 C API 进行编程</span><span class="sxs-lookup"><span data-stu-id="1762f-123">Programming with the C API in Excel</span></span>](programming-with-the-c-api-in-excel.md)
  
[<span data-ttu-id="1762f-124">线程中的多线程和内存Excel</span><span class="sxs-lookup"><span data-stu-id="1762f-124">Multithreading and Memory Contention in Excel</span></span>](multithreading-and-memory-contention-in-excel.md)


[<span data-ttu-id="1762f-125">Getting Started with the Excel XLL SDK</span><span class="sxs-lookup"><span data-stu-id="1762f-125">Getting Started with the Excel XLL SDK</span></span>](getting-started-with-the-excel-xll-sdk.md)

