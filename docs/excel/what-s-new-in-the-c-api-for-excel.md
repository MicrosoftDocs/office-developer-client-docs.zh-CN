---
title: 适用于 Excel 的 C API 中的新增功能
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
keywords:
- c api [excel 2007]，新增功能
localization_priority: Normal
ms.assetid: f11552e1-b8ea-4933-b6fc-c452b07eb59d
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: e80b667296af59f4d3f18238cd498830fcdc35a4
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/21/2018
ms.locfileid: "19773817"
---
# <a name="whats-new-in-the-c-api-for-excel"></a><span data-ttu-id="b2769-104">适用于 Excel 的 C API 中的新增功能</span><span class="sxs-lookup"><span data-stu-id="b2769-104">What's New in the C API for Excel</span></span>

 <span data-ttu-id="b2769-105">**适用于** Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="b2769-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="b2769-106">与 Microsoft Excel 2013 一起使用，Microsoft Excel 2013 XLL 软件开发工具包 (SDK) 包括支持以下功能。</span><span class="sxs-lookup"><span data-stu-id="b2769-106">In conjunction with Microsoft Excel 2013, the Microsoft Excel 2013 XLL Software Development Kit (SDK) includes support for the following features.</span></span>
  
- <span data-ttu-id="b2769-107">**新功能**</span><span class="sxs-lookup"><span data-stu-id="b2769-107">**New Functions**</span></span>
    
    <span data-ttu-id="b2769-108">Microsoft Excel 2013 XLL SDK 支持 Excel 2013 中的新工作表功能的所有回调。</span><span class="sxs-lookup"><span data-stu-id="b2769-108">The Microsoft Excel 2013 XLL SDK supports calling back to all of the new worksheet functions in Excel 2013.</span></span> <span data-ttu-id="b2769-109">有关调用 Excel 2013 函数的详细信息，请参阅[Excel 从 DLL 或 XLL 调用](calling-into-excel-from-the-dll-or-xll.md)。</span><span class="sxs-lookup"><span data-stu-id="b2769-109">For more information about calling Excel 2013 functions, see [Calling into Excel from the DLL or XLL](calling-into-excel-from-the-dll-or-xll.md).</span></span>
    
- <span data-ttu-id="b2769-110">**异步的用户定义函数**</span><span class="sxs-lookup"><span data-stu-id="b2769-110">**Asynchronous User-defined Functions**</span></span>
    
    <span data-ttu-id="b2769-111">Excel 2013 支持异步调用用户定义函数 (UDF) 通过启用多个计算同时运行这可以提高性能。</span><span class="sxs-lookup"><span data-stu-id="b2769-111">Excel 2013 supports calling user-defined functions (UDF) asynchronously, which can improve performance by enabling several calculations to run at the same time.</span></span> <span data-ttu-id="b2769-112">有关异步 Udf 的详细信息，请参阅[Asynchronous User-Defined 函数](asynchronous-user-defined-functions.md)。</span><span class="sxs-lookup"><span data-stu-id="b2769-112">For more information about asynchronous UDFs, see [Asynchronous User-Defined Functions](asynchronous-user-defined-functions.md).</span></span>
    
- <span data-ttu-id="b2769-113">**群集连接器**</span><span class="sxs-lookup"><span data-stu-id="b2769-113">**Cluster Connectors**</span></span>
    
    <span data-ttu-id="b2769-114">群集连接器启用 Udf 高性能计算群集上运行。</span><span class="sxs-lookup"><span data-stu-id="b2769-114">Cluster connectors enable UDFs to run on high-performance compute clusters.</span></span> <span data-ttu-id="b2769-115">有关创建群集连接器的详细信息，请参阅[开发 Excel 群集连接器](developing-excel-cluster-connectors.md)。</span><span class="sxs-lookup"><span data-stu-id="b2769-115">For more information about creating cluster connectors, see [Developing Excel Cluster Connectors](developing-excel-cluster-connectors.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="b2769-116">XLL 加载项您打算在计算群集上运行的必须调用仅群集安全函数。</span><span class="sxs-lookup"><span data-stu-id="b2769-116">XLL add-ins that you intend to run on compute clusters must call only cluster-safe functions.</span></span> <span data-ttu-id="b2769-117">有关功能的详细信息，您可以使用，请参阅[Excel XLL SDK API 函数参考](excel-xll-sdk-api-function-reference.md)和[群集安全函数](cluster-safe-functions.md)。</span><span class="sxs-lookup"><span data-stu-id="b2769-117">For more information about the functions you can use, see [Excel XLL SDK API Function Reference](excel-xll-sdk-api-function-reference.md) and [Cluster Safe Functions](cluster-safe-functions.md).</span></span> 
  
- <span data-ttu-id="b2769-118">**64 位支持**</span><span class="sxs-lookup"><span data-stu-id="b2769-118">**64-bit Support**</span></span>
    
    <span data-ttu-id="b2769-119">您现在可以编译并链接 32 位和 64 位 xll （英文）。</span><span class="sxs-lookup"><span data-stu-id="b2769-119">You can now compile and link both 32-bit and 64-bit XLLs.</span></span> <span data-ttu-id="b2769-120">有关详细信息，请参阅[创建 xll （英文）](creating-xlls.md)。</span><span class="sxs-lookup"><span data-stu-id="b2769-120">For more information, see [Creating XLLs](creating-xlls.md).</span></span>
    
## <a name="see-also"></a><span data-ttu-id="b2769-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b2769-121">See also</span></span>



[<span data-ttu-id="b2769-122">Developing Excel XLLs</span><span class="sxs-lookup"><span data-stu-id="b2769-122">Developing Excel XLLs</span></span>](developing-excel-xlls.md)
  
[<span data-ttu-id="b2769-123">�� Excel ��ʹ�� C API ���б��</span><span class="sxs-lookup"><span data-stu-id="b2769-123">Programming with the C API in Excel</span></span>](programming-with-the-c-api-in-excel.md)
  
[<span data-ttu-id="b2769-124">Excel 中的多线程处理和内存争用</span><span class="sxs-lookup"><span data-stu-id="b2769-124">Multithreading and Memory Contention in Excel</span></span>](multithreading-and-memory-contention-in-excel.md)


[<span data-ttu-id="b2769-125">Excel XLL SDK 入门</span><span class="sxs-lookup"><span data-stu-id="b2769-125">Getting Started with the Excel XLL SDK</span></span>](getting-started-with-the-excel-xll-sdk.md)

