---
title: 多线程和内存管理
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 6f7e052a-4270-4b83-b1ed-feabf6dbeaa2
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: f387d5ddb184c681ab5e005a6eb24058f6f52f9a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32310386"
---
# <a name="multithreading-and-memory-management"></a><span data-ttu-id="b4874-103">多线程和内存管理</span><span class="sxs-lookup"><span data-stu-id="b4874-103">Multithreading and Memory Management</span></span>

 <span data-ttu-id="b4874-104">**适用于** Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="b4874-104">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="b4874-105">正确处理内存对于创建适用于 Microsoft Excel 的可靠 XLL 外接程序至关重要。</span><span class="sxs-lookup"><span data-stu-id="b4874-105">Proper handling of memory is vital to creating reliable XLL add-ins for Microsoft Excel.</span></span> <span data-ttu-id="b4874-106">如果无法分配适当的内存缓冲区, 并在不再需要它们时释放它们, 则会降低性能, 创建资源争用和 destabilizes Excel。</span><span class="sxs-lookup"><span data-stu-id="b4874-106">Failure to allocate appropriate memory buffers and free them when they are no longer needed reduces performance, creates resource contention, and destabilizes Excel.</span></span>
  
<span data-ttu-id="b4874-107">从 Microsoft Office Excel 2007 开始, 可以将 Excel 配置为在重新计算时最长可使用1024个并发线程。</span><span class="sxs-lookup"><span data-stu-id="b4874-107">Beginning with Microsoft Office Excel 2007, you can configure Excel to use up to 1,024 concurrent threads when recalculating.</span></span> <span data-ttu-id="b4874-108">在某些情况下, 尤其是当多个处理器可用或在群集服务器上运行的用户定义的函数时, 多线程处理可以提高性能。</span><span class="sxs-lookup"><span data-stu-id="b4874-108">In some cases, especially when multiple processors are available or with user-defined functions running on clustered servers, multithreading can improve performance.</span></span>
  
<span data-ttu-id="b4874-109">以下主题介绍如何在 xll 中管理内存和线程:</span><span class="sxs-lookup"><span data-stu-id="b4874-109">The following topics describe how to manage memory and threads in XLLs:</span></span>
  
- [<span data-ttu-id="b4874-110">Excel 中的内存管理</span><span class="sxs-lookup"><span data-stu-id="b4874-110">Memory Management in Excel</span></span>](memory-management-in-excel.md)
    
- [<span data-ttu-id="b4874-111">Excel 中的多线程和内存争用</span><span class="sxs-lookup"><span data-stu-id="b4874-111">Multithreading and Memory Contention in Excel</span></span>](multithreading-and-memory-contention-in-excel.md)
    
- [<span data-ttu-id="b4874-112">Excel 中的多线程重新计算</span><span class="sxs-lookup"><span data-stu-id="b4874-112">Multithreaded Recalculation in Excel</span></span>](multithreaded-recalculation-in-excel.md)
    
## <a name="see-also"></a><span data-ttu-id="b4874-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b4874-113">See also</span></span>



[<span data-ttu-id="b4874-114">开发 Excel XLL</span><span class="sxs-lookup"><span data-stu-id="b4874-114">Developing Excel XLLs</span></span>](developing-excel-xlls.md)

