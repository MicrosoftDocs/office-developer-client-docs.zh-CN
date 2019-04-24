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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32298094"
---
# <a name="managing-memory-in-mapi"></a><span data-ttu-id="8d66f-103">管理 MAPI 中的内存</span><span class="sxs-lookup"><span data-stu-id="8d66f-103">Managing Memory in MAPI</span></span>

  
  
<span data-ttu-id="8d66f-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="8d66f-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="8d66f-105">了解如何以及何时分配和释放内存是使用 MAPI 编程的重要部分。</span><span class="sxs-lookup"><span data-stu-id="8d66f-105">Knowing how and when to allocate and free memory is an important part of programming with MAPI.</span></span> <span data-ttu-id="8d66f-106">MAPI 提供了功能和宏, 客户端或服务提供商可以使用它们以一致的方式管理内存。</span><span class="sxs-lookup"><span data-stu-id="8d66f-106">MAPI provides both functions and macros that your client or service provider can use to manage memory in a consistent way.</span></span> <span data-ttu-id="8d66f-107">这三个函数如下所示:</span><span class="sxs-lookup"><span data-stu-id="8d66f-107">The three functions are as follows:</span></span>
  
[<span data-ttu-id="8d66f-108">MAPIAllocateBuffer</span><span class="sxs-lookup"><span data-stu-id="8d66f-108">MAPIAllocateBuffer</span></span>](mapiallocatebuffer.md)
  
[<span data-ttu-id="8d66f-109">MAPIAllocateMore</span><span class="sxs-lookup"><span data-stu-id="8d66f-109">MAPIAllocateMore</span></span>](mapiallocatemore.md)
  
[<span data-ttu-id="8d66f-110">MAPIFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="8d66f-110">MAPIFreeBuffer</span></span>](mapifreebuffer.md)
  
<span data-ttu-id="8d66f-111">当客户端和服务提供商使用这些功能时, 有权 "拥有" 的问题 (即知道如何释放) 将消除特定的内存块。</span><span class="sxs-lookup"><span data-stu-id="8d66f-111">When clients and service providers use these functions, the issue of who "owns" — that is, knows how to release — a particular block of memory is eliminated.</span></span> <span data-ttu-id="8d66f-112">调用服务提供程序方法的客户端无需传递足够大的缓冲区以容纳任意大小的返回值。</span><span class="sxs-lookup"><span data-stu-id="8d66f-112">A client calling a service provider method need not pass a buffer large enough to hold a return value of any size.</span></span> <span data-ttu-id="8d66f-113">服务提供程序可以简单地使用**MAPIAllocateBuffer**分配适当的内存量, 并在必要时**MAPIAllocateMore**, 并且客户端可以在以后使用**MAPIFreeBuffer**, 而不依赖于服务provider.</span><span class="sxs-lookup"><span data-stu-id="8d66f-113">The service provider can simply allocate the appropriate amount of memory using **MAPIAllocateBuffer** and, if necessary, **MAPIAllocateMore**, and the client can later release it at will using **MAPIFreeBuffer**, independent of the service provider.</span></span> 
  
<span data-ttu-id="8d66f-114">内存宏用于分配特定大小的结构或结构数组。</span><span class="sxs-lookup"><span data-stu-id="8d66f-114">The memory macros are used to allocate structures or arrays of structures of a specific size.</span></span> <span data-ttu-id="8d66f-115">客户端和服务提供商应使用这些宏, 而不是手动分配内存。</span><span class="sxs-lookup"><span data-stu-id="8d66f-115">Clients and service providers should use these macros rather than allocate the memory manually.</span></span> <span data-ttu-id="8d66f-116">例如, 如果客户端需要在具有三个条目的收件人列表中执行名称解析处理, 则可以使用**SizedADRLIST**宏创建**ADRLIST**结构, 以将结构传递给**IAddrBook:: ResolveName**的正确数量的**ADRENTRY**成员。</span><span class="sxs-lookup"><span data-stu-id="8d66f-116">For example, if a client needs to perform name resolution processing on a recipient list with three entries, the **SizedADRLIST** macro can be used to create an **ADRLIST** structure to pass to **IAddrBook::ResolveName** with the correct number of **ADRENTRY** members.</span></span> <span data-ttu-id="8d66f-117">所有内存宏都在 mapidefs.h 中进行了定义。H 头文件。</span><span class="sxs-lookup"><span data-stu-id="8d66f-117">All of the memory macros are defined in the MAPIDEFS.H header file.</span></span> <span data-ttu-id="8d66f-118">这些宏为:</span><span class="sxs-lookup"><span data-stu-id="8d66f-118">These macros are:</span></span> 
  
|||
|:-----|:-----|
|[<span data-ttu-id="8d66f-119">SizedADRLIST</span><span class="sxs-lookup"><span data-stu-id="8d66f-119">SizedADRLIST</span></span>](sizedadrlist.md) <br/> |[<span data-ttu-id="8d66f-120">SizedDtblPage</span><span class="sxs-lookup"><span data-stu-id="8d66f-120">SizedDtblPage</span></span>](sizeddtblpage.md) <br/> |
|[<span data-ttu-id="8d66f-121">SizedDtblButton</span><span class="sxs-lookup"><span data-stu-id="8d66f-121">SizedDtblButton</span></span>](sizeddtblbutton.md) <br/> |[<span data-ttu-id="8d66f-122">SizedENTRYID</span><span class="sxs-lookup"><span data-stu-id="8d66f-122">SizedENTRYID</span></span>](sizedentryid.md) <br/> |
|[<span data-ttu-id="8d66f-123">SizedDtblCheckBox</span><span class="sxs-lookup"><span data-stu-id="8d66f-123">SizedDtblCheckBox</span></span>](sizeddtblcheckbox.md) <br/> |[<span data-ttu-id="8d66f-124">SizedSPropProblemArray</span><span class="sxs-lookup"><span data-stu-id="8d66f-124">SizedSPropProblemArray</span></span>](sizedspropproblemarray.md) <br/> |
|[<span data-ttu-id="8d66f-125">SizedDtblComboBox</span><span class="sxs-lookup"><span data-stu-id="8d66f-125">SizedDtblComboBox</span></span>](sizeddtblcombobox.md) <br/> |[<span data-ttu-id="8d66f-126">SizedSPropTagArray</span><span class="sxs-lookup"><span data-stu-id="8d66f-126">SizedSPropTagArray</span></span>](sizedsproptagarray.md) <br/> |
|[<span data-ttu-id="8d66f-127">SizedDtblEdit</span><span class="sxs-lookup"><span data-stu-id="8d66f-127">SizedDtblEdit</span></span>](sizeddtbledit.md) <br/> |[<span data-ttu-id="8d66f-128">SizedSRowSet</span><span class="sxs-lookup"><span data-stu-id="8d66f-128">SizedSRowSet</span></span>](sizedsrowset.md) <br/> |
|[<span data-ttu-id="8d66f-129">SizedDtblGroupBox</span><span class="sxs-lookup"><span data-stu-id="8d66f-129">SizedDtblGroupBox</span></span>](sizeddtblgroupbox.md) <br/> |[<span data-ttu-id="8d66f-130">SizedSSortOrderSet</span><span class="sxs-lookup"><span data-stu-id="8d66f-130">SizedSSortOrderSet</span></span>](sizedssortorderset.md) <br/> |
|[<span data-ttu-id="8d66f-131">SizedDtblLabel</span><span class="sxs-lookup"><span data-stu-id="8d66f-131">SizedDtblLabel</span></span>](sizeddtbllabel.md) <br/> | <br/> |
   
<span data-ttu-id="8d66f-132">MAPI 还支持使用 COM 接口[IMalloc](https://msdn.microsoft.com/library/ms678425%28VS.85%29.aspx)进行内存管理。</span><span class="sxs-lookup"><span data-stu-id="8d66f-132">MAPI also supports the use of the COM interface [IMalloc](https://msdn.microsoft.com/library/ms678425%28VS.85%29.aspx) for memory management.</span></span> <span data-ttu-id="8d66f-133">服务提供程序在初始化时为 MAPI 提供**IMalloc**接口指针, 还可以通过[MAPIGetDefaultMalloc](mapigetdefaultmalloc.md)函数检索一个接口指针。</span><span class="sxs-lookup"><span data-stu-id="8d66f-133">Service providers are given an **IMalloc** interface pointer by MAPI at initialization time and can also retrieve one through the [MAPIGetDefaultMalloc](mapigetdefaultmalloc.md) function.</span></span> <span data-ttu-id="8d66f-134">使用**IMalloc**方法来通过 MAPI 函数管理内存的主要优势在于, 使用 COM 方法可以重新分配现有缓冲区。</span><span class="sxs-lookup"><span data-stu-id="8d66f-134">The main advantage to using the **IMalloc** methods for managing memory over the MAPI functions is that with the COM methods it is possible to reallocate an existing buffer.</span></span> <span data-ttu-id="8d66f-135">MAPI 内存函数不支持重新分配。</span><span class="sxs-lookup"><span data-stu-id="8d66f-135">The MAPI memory functions do not support reallocation.</span></span> 
  

