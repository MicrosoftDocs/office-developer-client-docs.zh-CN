---
title: 多线程处理和内存管理
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 6f7e052a-4270-4b83-b1ed-feabf6dbeaa2
description: ���÷�Χ�� Excel 2013?| Office 2013?| Visual Studio
ms.openlocfilehash: 4f5495648c9012b0e028358037090f7e10ef5219
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773800"
---
# <a name="multithreading-and-memory-management"></a><span data-ttu-id="63e89-103">多线程处理和内存管理</span><span class="sxs-lookup"><span data-stu-id="63e89-103">Multithreading and Memory Management</span></span>

 <span data-ttu-id="63e89-104">**适用于**： Excel 2013 |Office 2013 |Visual Studio</span><span class="sxs-lookup"><span data-stu-id="63e89-104">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="63e89-105">正确处理内存至关重要的 Microsoft Excel 中创建可靠的 XLL 加载项。</span><span class="sxs-lookup"><span data-stu-id="63e89-105">Proper handling of memory is vital to creating reliable XLL add-ins for Microsoft Excel.</span></span> <span data-ttu-id="63e89-106">未能分配相应的内存缓冲区释放它们时不再需要它们会降低性能，创建资源争用和 destabilizes Excel。</span><span class="sxs-lookup"><span data-stu-id="63e89-106">Failure to allocate appropriate memory buffers and free them when they are no longer needed reduces performance, creates resource contention, and destabilizes Excel.</span></span>
  
<span data-ttu-id="63e89-107">从 Microsoft Office Excel 2007 开始，您可以配置 Excel 重新计算时使用最多包含 1,024 并发线程。</span><span class="sxs-lookup"><span data-stu-id="63e89-107">Beginning with Microsoft Office Excel 2007, you can configure Excel to use up to 1,024 concurrent threads when recalculating.</span></span> <span data-ttu-id="63e89-108">在某些情况下，尤其是当多个处理器都可以使用或用户定义函数聚集多线程处理服务器上运行可以提高性能。</span><span class="sxs-lookup"><span data-stu-id="63e89-108">In some cases, especially when multiple processors are available or with user-defined functions running on clustered servers, multithreading can improve performance.</span></span>
  
<span data-ttu-id="63e89-109">以下主题介绍如何管理内存和 xll 中的线程数：</span><span class="sxs-lookup"><span data-stu-id="63e89-109">The following topics describe how to manage memory and threads in XLLs:</span></span>
  
- [<span data-ttu-id="63e89-110">在 Excel 中进行内存管理</span><span class="sxs-lookup"><span data-stu-id="63e89-110">Memory Management in Excel</span></span>](memory-management-in-excel.md)
    
- [<span data-ttu-id="63e89-111">多线程和 Excel 中的内存争用</span><span class="sxs-lookup"><span data-stu-id="63e89-111">Multithreading and Memory Contention in Excel</span></span>](multithreading-and-memory-contention-in-excel.md)
    
- [<span data-ttu-id="63e89-112">在 Excel 中的多线程重新计算</span><span class="sxs-lookup"><span data-stu-id="63e89-112">Multithreaded Recalculation in Excel</span></span>](multithreaded-recalculation-in-excel.md)
    
## <a name="see-also"></a><span data-ttu-id="63e89-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="63e89-113">See also</span></span>



[<span data-ttu-id="63e89-114">Developing Excel XLLs</span><span class="sxs-lookup"><span data-stu-id="63e89-114">Developing Excel XLLs</span></span>](developing-excel-xlls.md)

