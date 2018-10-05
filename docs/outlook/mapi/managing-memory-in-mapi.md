---
title: 管理 MAPI 中的内存
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 9eee6925-ab91-413e-8907-c747ab4a4bb5
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 66489c09be641d8fe9ae5f3ffff46a6d5004f473
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25388068"
---
# <a name="managing-memory-in-mapi"></a><span data-ttu-id="71c80-103">管理 MAPI 中的内存</span><span class="sxs-lookup"><span data-stu-id="71c80-103">Managing Memory in MAPI</span></span>

  
  
<span data-ttu-id="71c80-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="71c80-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="71c80-105">了解如何以及何时以分配和释放内存是使用 MAPI 编程的重要组成部分。</span><span class="sxs-lookup"><span data-stu-id="71c80-105">Knowing how and when to allocate and free memory is an important part of programming with MAPI.</span></span> <span data-ttu-id="71c80-106">MAPI 提供功能和宏的客户端或服务提供程序可用于管理内存中以一致方式。</span><span class="sxs-lookup"><span data-stu-id="71c80-106">MAPI provides both functions and macros that your client or service provider can use to manage memory in a consistent way.</span></span> <span data-ttu-id="71c80-107">三个函数，如下所示：</span><span class="sxs-lookup"><span data-stu-id="71c80-107">The three functions are as follows:</span></span>
  
[<span data-ttu-id="71c80-108">MAPIAllocateBuffer</span><span class="sxs-lookup"><span data-stu-id="71c80-108">MAPIAllocateBuffer</span></span>](mapiallocatebuffer.md)
  
[<span data-ttu-id="71c80-109">MAPIAllocateMore</span><span class="sxs-lookup"><span data-stu-id="71c80-109">MAPIAllocateMore</span></span>](mapiallocatemore.md)
  
[<span data-ttu-id="71c80-110">MAPIFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="71c80-110">MAPIFreeBuffer</span></span>](mapifreebuffer.md)
  
<span data-ttu-id="71c80-111">客户端和服务提供商时使用这些功能，该问题的"所有者"— 即，知道如何释放 — 去掉了特定块的内存。</span><span class="sxs-lookup"><span data-stu-id="71c80-111">When clients and service providers use these functions, the issue of who "owns" — that is, knows how to release — a particular block of memory is eliminated.</span></span> <span data-ttu-id="71c80-112">调用服务提供程序方法的客户端需要传递足以容纳任何大小的返回值的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="71c80-112">A client calling a service provider method need not pass a buffer large enough to hold a return value of any size.</span></span> <span data-ttu-id="71c80-113">服务提供程序只可以分配适当的使用**MAPIAllocateBuffer**的内存量和，如有必要， **MAPIAllocateMore**和客户端可以更高版本释放其在将使用**MAPIFreeBuffer**，独立的服务提供程序。</span><span class="sxs-lookup"><span data-stu-id="71c80-113">The service provider can simply allocate the appropriate amount of memory using **MAPIAllocateBuffer** and, if necessary, **MAPIAllocateMore**, and the client can later release it at will using **MAPIFreeBuffer**, independent of the service provider.</span></span> 
  
<span data-ttu-id="71c80-114">内存宏用于分配结构或结构特定大小的数组。</span><span class="sxs-lookup"><span data-stu-id="71c80-114">The memory macros are used to allocate structures or arrays of structures of a specific size.</span></span> <span data-ttu-id="71c80-115">客户端和服务提供商应使用这些宏而不是手动分配内存。</span><span class="sxs-lookup"><span data-stu-id="71c80-115">Clients and service providers should use these macros rather than allocate the memory manually.</span></span> <span data-ttu-id="71c80-116">例如，如果客户端需要执行处理上具有三个项的收件人列表的名称解析， **SizedADRLIST**宏可用于创建要与正确的数传递给**IAddrBook::ResolveName** **ADRLIST**结构**ADRENTRY**成员。</span><span class="sxs-lookup"><span data-stu-id="71c80-116">For example, if a client needs to perform name resolution processing on a recipient list with three entries, the **SizedADRLIST** macro can be used to create an **ADRLIST** structure to pass to **IAddrBook::ResolveName** with the correct number of **ADRENTRY** members.</span></span> <span data-ttu-id="71c80-117">所有内存宏 MAPIDEFS 中定义。H 头文件。</span><span class="sxs-lookup"><span data-stu-id="71c80-117">All of the memory macros are defined in the MAPIDEFS.H header file.</span></span> <span data-ttu-id="71c80-118">这些宏是：</span><span class="sxs-lookup"><span data-stu-id="71c80-118">These macros are:</span></span> 
  
|||
|:-----|:-----|
|[<span data-ttu-id="71c80-119">SizedADRLIST</span><span class="sxs-lookup"><span data-stu-id="71c80-119">SizedADRLIST</span></span>](sizedadrlist.md) <br/> |[<span data-ttu-id="71c80-120">SizedDtblPage</span><span class="sxs-lookup"><span data-stu-id="71c80-120">SizedDtblPage</span></span>](sizeddtblpage.md) <br/> |
|[<span data-ttu-id="71c80-121">SizedDtblButton</span><span class="sxs-lookup"><span data-stu-id="71c80-121">SizedDtblButton</span></span>](sizeddtblbutton.md) <br/> |[<span data-ttu-id="71c80-122">SizedENTRYID</span><span class="sxs-lookup"><span data-stu-id="71c80-122">SizedENTRYID</span></span>](sizedentryid.md) <br/> |
|[<span data-ttu-id="71c80-123">SizedDtblCheckBox</span><span class="sxs-lookup"><span data-stu-id="71c80-123">SizedDtblCheckBox</span></span>](sizeddtblcheckbox.md) <br/> |[<span data-ttu-id="71c80-124">SizedSPropProblemArray</span><span class="sxs-lookup"><span data-stu-id="71c80-124">SizedSPropProblemArray</span></span>](sizedspropproblemarray.md) <br/> |
|[<span data-ttu-id="71c80-125">SizedDtblComboBox</span><span class="sxs-lookup"><span data-stu-id="71c80-125">SizedDtblComboBox</span></span>](sizeddtblcombobox.md) <br/> |[<span data-ttu-id="71c80-126">SizedSPropTagArray</span><span class="sxs-lookup"><span data-stu-id="71c80-126">SizedSPropTagArray</span></span>](sizedsproptagarray.md) <br/> |
|[<span data-ttu-id="71c80-127">SizedDtblEdit</span><span class="sxs-lookup"><span data-stu-id="71c80-127">SizedDtblEdit</span></span>](sizeddtbledit.md) <br/> |[<span data-ttu-id="71c80-128">SizedSRowSet</span><span class="sxs-lookup"><span data-stu-id="71c80-128">SizedSRowSet</span></span>](sizedsrowset.md) <br/> |
|[<span data-ttu-id="71c80-129">SizedDtblGroupBox</span><span class="sxs-lookup"><span data-stu-id="71c80-129">SizedDtblGroupBox</span></span>](sizeddtblgroupbox.md) <br/> |[<span data-ttu-id="71c80-130">SizedSSortOrderSet</span><span class="sxs-lookup"><span data-stu-id="71c80-130">SizedSSortOrderSet</span></span>](sizedssortorderset.md) <br/> |
|[<span data-ttu-id="71c80-131">SizedDtblLabel</span><span class="sxs-lookup"><span data-stu-id="71c80-131">SizedDtblLabel</span></span>](sizeddtbllabel.md) <br/> | <br/> |
   
<span data-ttu-id="71c80-132">MAPI 还支持[IMalloc](https://msdn.microsoft.com/library/ms678425%28VS.85%29.aspx)的 COM 接口使用的内存管理。</span><span class="sxs-lookup"><span data-stu-id="71c80-132">MAPI also supports the use of the COM interface [IMalloc](https://msdn.microsoft.com/library/ms678425%28VS.85%29.aspx) for memory management.</span></span> <span data-ttu-id="71c80-133">服务提供商在初始化时通过 MAPI 授予**IMalloc**接口指针和还可以检索一星到[MAPIGetDefaultMalloc](mapigetdefaultmalloc.md)函数。</span><span class="sxs-lookup"><span data-stu-id="71c80-133">Service providers are given an **IMalloc** interface pointer by MAPI at initialization time and can also retrieve one through the [MAPIGetDefaultMalloc](mapigetdefaultmalloc.md) function.</span></span> <span data-ttu-id="71c80-134">用于通过 MAPI 函数管理内存使用**IMalloc**方法的主要优点是，使用 COM 方法就可以重新分配现有缓冲区。</span><span class="sxs-lookup"><span data-stu-id="71c80-134">The main advantage to using the **IMalloc** methods for managing memory over the MAPI functions is that with the COM methods it is possible to reallocate an existing buffer.</span></span> <span data-ttu-id="71c80-135">MAPI 内存函数不支持重新分配。</span><span class="sxs-lookup"><span data-stu-id="71c80-135">The MAPI memory functions do not support reallocation.</span></span> 
  

