---
title: 组件对象模型和 MAPI
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: cca4c70d-b73a-4834-80b5-9cb5889f63cc
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: a91ab8497a690fd4b99f76274d0213284253fd06
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32334466"
---
# <a name="component-object-model-and-mapi"></a><span data-ttu-id="6f2a5-103">组件对象模型和 MAPI</span><span class="sxs-lookup"><span data-stu-id="6f2a5-103">Component Object Model and MAPI</span></span>

  
  
<span data-ttu-id="6f2a5-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="6f2a5-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="6f2a5-105">此Windows SDK 文档包含有关实现符合 COM 组件对象模型组件模型 (对象的) 。</span><span class="sxs-lookup"><span data-stu-id="6f2a5-105">The Windows SDK documentation includes a comprehensive discussion of the rules for implementing objects that conform to the Component Object Model (COM).</span></span> <span data-ttu-id="6f2a5-106">这些规则将解决如何执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="6f2a5-106">These rules address how to do the following:</span></span>
  
- <span data-ttu-id="6f2a5-107">设计接口和对象。</span><span class="sxs-lookup"><span data-stu-id="6f2a5-107">Design interfaces and objects.</span></span>
    
- <span data-ttu-id="6f2a5-108">实现 [IUnknown](https://msdn.microsoft.com/library/ms680509%28VS.85%29.aspx) 接口。</span><span class="sxs-lookup"><span data-stu-id="6f2a5-108">Implement the [IUnknown](https://msdn.microsoft.com/library/ms680509%28VS.85%29.aspx) interface.</span></span> 
    
- <span data-ttu-id="6f2a5-109">管理内存。</span><span class="sxs-lookup"><span data-stu-id="6f2a5-109">Manage memory.</span></span>
    
- <span data-ttu-id="6f2a5-110">处理引用计数。</span><span class="sxs-lookup"><span data-stu-id="6f2a5-110">Handle reference counting.</span></span>
    
- <span data-ttu-id="6f2a5-111">实现单元线程对象。</span><span class="sxs-lookup"><span data-stu-id="6f2a5-111">Implement apartment-threaded objects.</span></span>
    
<span data-ttu-id="6f2a5-112">尽管所有 MAPI 对象都被视为基于 COM，因为它们实现从 [IUnknown](https://msdn.microsoft.com/library/ms680509%28VS.85%29.aspx)继承的接口，但在某些情况下 MAPI 偏离标准 COM 规则。</span><span class="sxs-lookup"><span data-stu-id="6f2a5-112">Although all MAPI objects are considered COM-based because they implement interfaces that inherit from [IUnknown](https://msdn.microsoft.com/library/ms680509%28VS.85%29.aspx), MAPI deviates in some situations from the standard COM rules.</span></span> <span data-ttu-id="6f2a5-113">此偏差允许开发人员更灵活地实现。</span><span class="sxs-lookup"><span data-stu-id="6f2a5-113">This deviation allows developers more flexibility in their implementations.</span></span> <span data-ttu-id="6f2a5-114">例如，MAPI 接口（如任何 COM 接口）描述了实现者与调用方之间的协定。</span><span class="sxs-lookup"><span data-stu-id="6f2a5-114">For example, a MAPI interface, like any COM interface, describes a contract between implementer and caller.</span></span> <span data-ttu-id="6f2a5-115">创建和发布接口后，其定义将不能且不会更改。</span><span class="sxs-lookup"><span data-stu-id="6f2a5-115">Once the interface is created and published, its definition cannot and does not change.</span></span> <span data-ttu-id="6f2a5-116">MAPI 不会偏离此说明，但它稍微缓解了该说明。</span><span class="sxs-lookup"><span data-stu-id="6f2a5-116">MAPI does not deviate from this description, but it relaxes the description somewhat.</span></span> <span data-ttu-id="6f2a5-117">实现者可以选择不实现特定方法，同时向调用方返回以下错误值之一：</span><span class="sxs-lookup"><span data-stu-id="6f2a5-117">Implementers can choose to not implement particular methods, returning one of the following error values to the caller:</span></span> 
  
- <span data-ttu-id="6f2a5-118">MAPI_E_NO_SUPPORT</span><span class="sxs-lookup"><span data-stu-id="6f2a5-118">MAPI_E_NO_SUPPORT</span></span>
    
- <span data-ttu-id="6f2a5-119">MAPI_E_TOO_COMPLEX</span><span class="sxs-lookup"><span data-stu-id="6f2a5-119">MAPI_E_TOO_COMPLEX</span></span>
    
- <span data-ttu-id="6f2a5-120">MAPI_E_BAD_CHARWIDTH</span><span class="sxs-lookup"><span data-stu-id="6f2a5-120">MAPI_E_BAD_CHARWIDTH</span></span>
    
- <span data-ttu-id="6f2a5-121">MAPI_E_TYPE_NO_SUPPORT</span><span class="sxs-lookup"><span data-stu-id="6f2a5-121">MAPI_E_TYPE_NO_SUPPORT</span></span>
    
<span data-ttu-id="6f2a5-122">下表介绍了与标准 COM 规则的其他偏差。</span><span class="sxs-lookup"><span data-stu-id="6f2a5-122">The other deviations from the standard COM rules are described in the following table.</span></span>
  
|<span data-ttu-id="6f2a5-123">**COM 编程规则**</span><span class="sxs-lookup"><span data-stu-id="6f2a5-123">**COM programming rule**</span></span>|<span data-ttu-id="6f2a5-124">**MAPI 变体**</span><span class="sxs-lookup"><span data-stu-id="6f2a5-124">**MAPI variation**</span></span>|
|:-----|:-----|
|<span data-ttu-id="6f2a5-125">接口方法中所有字符串参数应为 Unicode。</span><span class="sxs-lookup"><span data-stu-id="6f2a5-125">All string parameters in interface methods should be Unicode.</span></span>  <br/> |<span data-ttu-id="6f2a5-126">MAPI 接口定义为允许 Unicode 或 ANSI 字符串参数。</span><span class="sxs-lookup"><span data-stu-id="6f2a5-126">MAPI interfaces are defined to permit either Unicode or ANSI string parameters.</span></span> <span data-ttu-id="6f2a5-127">具有字符串参数的许多方法也具有 **ulFlags** 参数;字符串参数的宽度由 **ulFlags** 中 MAPI_UNICODE 标记的值指示。</span><span class="sxs-lookup"><span data-stu-id="6f2a5-127">Many methods that have a string parameter also have a **ulFlags** parameter; the width of a string parameter is indicated by the value of the MAPI_UNICODE flag in **ulFlags**.</span></span> <span data-ttu-id="6f2a5-128">有些 MAPI 接口不支持 Unicode，在设置 MAPI_E_BAD_CHARWIDTH 标志MAPI_UNICODE返回 Unicode。</span><span class="sxs-lookup"><span data-stu-id="6f2a5-128">Some MAPI interfaces do not support Unicode and return MAPI_E_BAD_CHARWIDTH when the MAPI_UNICODE flag is set.</span></span>  <br/> |
|<span data-ttu-id="6f2a5-129">所有接口方法都应具有 HRESULT 的返回类型。</span><span class="sxs-lookup"><span data-stu-id="6f2a5-129">All interface methods should have a return type of HRESULT.</span></span>  <br/> |<span data-ttu-id="6f2a5-130">MAPI 至少有一个返回非 HRESULT 值的方法 [：IMAPIAdviseSink：：OnNotify](imapiadvisesink-onnotify.md)。</span><span class="sxs-lookup"><span data-stu-id="6f2a5-130">MAPI has at least one method that returns a non-HRESULT value: [IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md).</span></span>  <br/> |
|<span data-ttu-id="6f2a5-131">调用方和实施者应该使用标准 COM 任务分配器为接口参数分配和释放内存。</span><span class="sxs-lookup"><span data-stu-id="6f2a5-131">Callers and implementers should allocate and free memory for interface parameters by using the standard COM task allocators.</span></span>  <br/> |<span data-ttu-id="6f2a5-132">所有 MAPI 方法都使用链接的分配器[MAPIAllocateBuffer、MAPIAllocateMore](mapiallocatebuffer.md)和[MAPIFreeBuffer](mapifreebuffer.md)来管理接口参数的内存。 [](mapiallocatemore.md)</span><span class="sxs-lookup"><span data-stu-id="6f2a5-132">All MAPI methods use the linked allocators [MAPIAllocateBuffer](mapiallocatebuffer.md), [MAPIAllocateMore](mapiallocatemore.md), and [MAPIFreeBuffer](mapifreebuffer.md) to manage memory for interface parameters.</span></span> <span data-ttu-id="6f2a5-133">所有由 OLE 定义的接口的 MAPI 实现（如 [IStream）](https://msdn.microsoft.com/library/aa380034%28VS.85%29.aspx)都使用标准 COM 任务分配器。</span><span class="sxs-lookup"><span data-stu-id="6f2a5-133">All MAPI implementations of interfaces defined by OLE, such as [IStream](https://msdn.microsoft.com/library/aa380034%28VS.85%29.aspx), use the standard COM task allocators.</span></span>  <br/> |
|<span data-ttu-id="6f2a5-134">方法失败时，必须将所有 out 指针参数显式设置为 NULL。</span><span class="sxs-lookup"><span data-stu-id="6f2a5-134">All out pointer parameters must explicitly be set to NULL when a method fails.</span></span>  <br/> |<span data-ttu-id="6f2a5-135">MAPI 接口要求将指针参数设置为 NULL，或在方法失败时保持不变。</span><span class="sxs-lookup"><span data-stu-id="6f2a5-135">MAPI interfaces require that out pointer parameters either be set to NULL or remain unchanged when a method fails.</span></span> <span data-ttu-id="6f2a5-136">所有由 OLE 定义的接口的 MAPI 实现在出现故障时显式将参数设置为 NULL。</span><span class="sxs-lookup"><span data-stu-id="6f2a5-136">All MAPI implementations of interfaces defined by OLE explicitly set out parameters to NULL on failure.</span></span>  <br/> |
|<span data-ttu-id="6f2a5-137">尽可能实现可聚合对象。</span><span class="sxs-lookup"><span data-stu-id="6f2a5-137">Implement aggregatable objects whenever possible.</span></span>  <br/> |<span data-ttu-id="6f2a5-138">MAPI 接口不可聚合。</span><span class="sxs-lookup"><span data-stu-id="6f2a5-138">MAPI interfaces are not aggregatable.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="6f2a5-139">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6f2a5-139">See also</span></span>



[<span data-ttu-id="6f2a5-140">MAPIAllocateBuffer</span><span class="sxs-lookup"><span data-stu-id="6f2a5-140">MAPIAllocateBuffer</span></span>](mapiallocatebuffer.md)
  
[<span data-ttu-id="6f2a5-141">MAPIAllocateMore</span><span class="sxs-lookup"><span data-stu-id="6f2a5-141">MAPIAllocateMore</span></span>](mapiallocatemore.md)
  
[<span data-ttu-id="6f2a5-142">MAPIFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="6f2a5-142">MAPIFreeBuffer</span></span>](mapifreebuffer.md)


[<span data-ttu-id="6f2a5-143">MAPI 对象和接口概述</span><span class="sxs-lookup"><span data-stu-id="6f2a5-143">MAPI Object and Interface Overview</span></span>](mapi-object-and-interface-overview.md)

