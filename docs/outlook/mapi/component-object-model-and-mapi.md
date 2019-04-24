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
# <a name="component-object-model-and-mapi"></a><span data-ttu-id="f9644-103">组件对象模型和 MAPI</span><span class="sxs-lookup"><span data-stu-id="f9644-103">Component Object Model and MAPI</span></span>

  
  
<span data-ttu-id="f9644-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="f9644-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="f9644-105">Windows SDK 文档包含有关实现符合组件对象模型 (COM) 的对象的规则的全面讨论。</span><span class="sxs-lookup"><span data-stu-id="f9644-105">The Windows SDK documentation includes a comprehensive discussion of the rules for implementing objects that conform to the Component Object Model (COM).</span></span> <span data-ttu-id="f9644-106">这些规则解决了如何执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="f9644-106">These rules address how to do the following:</span></span>
  
- <span data-ttu-id="f9644-107">设计接口和对象。</span><span class="sxs-lookup"><span data-stu-id="f9644-107">Design interfaces and objects.</span></span>
    
- <span data-ttu-id="f9644-108">实现[IUnknown](https://msdn.microsoft.com/library/ms680509%28VS.85%29.aspx)接口。</span><span class="sxs-lookup"><span data-stu-id="f9644-108">Implement the [IUnknown](https://msdn.microsoft.com/library/ms680509%28VS.85%29.aspx) interface.</span></span> 
    
- <span data-ttu-id="f9644-109">管理内存。</span><span class="sxs-lookup"><span data-stu-id="f9644-109">Manage memory.</span></span>
    
- <span data-ttu-id="f9644-110">处理引用计数。</span><span class="sxs-lookup"><span data-stu-id="f9644-110">Handle reference counting.</span></span>
    
- <span data-ttu-id="f9644-111">实现单元线程对象。</span><span class="sxs-lookup"><span data-stu-id="f9644-111">Implement apartment-threaded objects.</span></span>
    
<span data-ttu-id="f9644-112">尽管所有 MAPI 对象都是基于 COM 的, 因为它们实现从[IUnknown](https://msdn.microsoft.com/library/ms680509%28VS.85%29.aspx)继承的接口, 而 mapi 在某些情况下与标准 COM 规则发生了偏离。</span><span class="sxs-lookup"><span data-stu-id="f9644-112">Although all MAPI objects are considered COM-based because they implement interfaces that inherit from [IUnknown](https://msdn.microsoft.com/library/ms680509%28VS.85%29.aspx), MAPI deviates in some situations from the standard COM rules.</span></span> <span data-ttu-id="f9644-113">通过这种差异, 开发者可以更灵活地实现其实现。</span><span class="sxs-lookup"><span data-stu-id="f9644-113">This deviation allows developers more flexibility in their implementations.</span></span> <span data-ttu-id="f9644-114">例如, MAPI 接口 (如任何 COM 接口) 描述实施者和调用方之间的合约。</span><span class="sxs-lookup"><span data-stu-id="f9644-114">For example, a MAPI interface, like any COM interface, describes a contract between implementer and caller.</span></span> <span data-ttu-id="f9644-115">创建并发布接口后, 其定义无法且不会更改。</span><span class="sxs-lookup"><span data-stu-id="f9644-115">Once the interface is created and published, its definition cannot and does not change.</span></span> <span data-ttu-id="f9644-116">MAPI 并不偏离此说明, 但在某些情况下 relaxes 说明。</span><span class="sxs-lookup"><span data-stu-id="f9644-116">MAPI does not deviate from this description, but it relaxes the description somewhat.</span></span> <span data-ttu-id="f9644-117">实施者可以选择不实现特定的方法, 并将以下错误值之一返回给调用程序:</span><span class="sxs-lookup"><span data-stu-id="f9644-117">Implementers can choose to not implement particular methods, returning one of the following error values to the caller:</span></span> 
  
- <span data-ttu-id="f9644-118">MAPI_E_NO_SUPPORT</span><span class="sxs-lookup"><span data-stu-id="f9644-118">MAPI_E_NO_SUPPORT</span></span>
    
- <span data-ttu-id="f9644-119">MAPI_E_TOO_COMPLEX</span><span class="sxs-lookup"><span data-stu-id="f9644-119">MAPI_E_TOO_COMPLEX</span></span>
    
- <span data-ttu-id="f9644-120">MAPI_E_BAD_CHARWIDTH</span><span class="sxs-lookup"><span data-stu-id="f9644-120">MAPI_E_BAD_CHARWIDTH</span></span>
    
- <span data-ttu-id="f9644-121">MAPI_E_TYPE_NO_SUPPORT</span><span class="sxs-lookup"><span data-stu-id="f9644-121">MAPI_E_TYPE_NO_SUPPORT</span></span>
    
<span data-ttu-id="f9644-122">下表介绍了与标准 COM 规则的其他偏差。</span><span class="sxs-lookup"><span data-stu-id="f9644-122">The other deviations from the standard COM rules are described in the following table.</span></span>
  
|<span data-ttu-id="f9644-123">**COM 编程规则**</span><span class="sxs-lookup"><span data-stu-id="f9644-123">**COM programming rule**</span></span>|<span data-ttu-id="f9644-124">**MAPI 变体**</span><span class="sxs-lookup"><span data-stu-id="f9644-124">**MAPI variation**</span></span>|
|:-----|:-----|
|<span data-ttu-id="f9644-125">接口方法中的所有字符串参数都应为 Unicode。</span><span class="sxs-lookup"><span data-stu-id="f9644-125">All string parameters in interface methods should be Unicode.</span></span>  <br/> |<span data-ttu-id="f9644-126">MAPI 接口定义为允许 Unicode 或 ANSI 字符串参数。</span><span class="sxs-lookup"><span data-stu-id="f9644-126">MAPI interfaces are defined to permit either Unicode or ANSI string parameters.</span></span> <span data-ttu-id="f9644-127">具有 string 参数的许多方法也具有**ulFlags**参数;字符串参数的宽度由**ulFlags**中的 MAPI_UNICODE 标志的值指示。</span><span class="sxs-lookup"><span data-stu-id="f9644-127">Many methods that have a string parameter also have a **ulFlags** parameter; the width of a string parameter is indicated by the value of the MAPI_UNICODE flag in **ulFlags**.</span></span> <span data-ttu-id="f9644-128">某些 MAPI 接口不支持 Unicode, 并在设置 MAPI_UNICODE 标志时返回 MAPI_E_BAD_CHARWIDTH。</span><span class="sxs-lookup"><span data-stu-id="f9644-128">Some MAPI interfaces do not support Unicode and return MAPI_E_BAD_CHARWIDTH when the MAPI_UNICODE flag is set.</span></span>  <br/> |
|<span data-ttu-id="f9644-129">所有接口方法应具有 HRESULT 的返回类型。</span><span class="sxs-lookup"><span data-stu-id="f9644-129">All interface methods should have a return type of HRESULT.</span></span>  <br/> |<span data-ttu-id="f9644-130">MAPI 至少有一个返回非 HRESULT 值的方法: [IMAPIAdviseSink:: OnNotify](imapiadvisesink-onnotify.md)。</span><span class="sxs-lookup"><span data-stu-id="f9644-130">MAPI has at least one method that returns a non-HRESULT value: [IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md).</span></span>  <br/> |
|<span data-ttu-id="f9644-131">调用方和实现者应使用标准的 COM 任务 allocators 为接口参数分配和释放内存。</span><span class="sxs-lookup"><span data-stu-id="f9644-131">Callers and implementers should allocate and free memory for interface parameters by using the standard COM task allocators.</span></span>  <br/> |<span data-ttu-id="f9644-132">所有 MAPI 方法均使用链接的 allocators [MAPIAllocateBuffer](mapiallocatebuffer.md)、 [MAPIAllocateMore](mapiallocatemore.md)和[MAPIFreeBuffer](mapifreebuffer.md)来管理接口参数的内存。</span><span class="sxs-lookup"><span data-stu-id="f9644-132">All MAPI methods use the linked allocators [MAPIAllocateBuffer](mapiallocatebuffer.md), [MAPIAllocateMore](mapiallocatemore.md), and [MAPIFreeBuffer](mapifreebuffer.md) to manage memory for interface parameters.</span></span> <span data-ttu-id="f9644-133">所有由 OLE 定义的接口的 MAPI 实现 (如[IStream](https://msdn.microsoft.com/library/aa380034%28VS.85%29.aspx)) 使用标准的 COM 任务 allocators。</span><span class="sxs-lookup"><span data-stu-id="f9644-133">All MAPI implementations of interfaces defined by OLE, such as [IStream](https://msdn.microsoft.com/library/aa380034%28VS.85%29.aspx), use the standard COM task allocators.</span></span>  <br/> |
|<span data-ttu-id="f9644-134">当方法失败时, 所有 out 指针参数都必须显式设置为 NULL。</span><span class="sxs-lookup"><span data-stu-id="f9644-134">All out pointer parameters must explicitly be set to NULL when a method fails.</span></span>  <br/> |<span data-ttu-id="f9644-135">MAPI 接口要求输出的指针参数设置为 NULL 或在方法失败时保持不变。</span><span class="sxs-lookup"><span data-stu-id="f9644-135">MAPI interfaces require that out pointer parameters either be set to NULL or remain unchanged when a method fails.</span></span> <span data-ttu-id="f9644-136">通过 OLE 定义的所有 MAPI 接口实现都会在失败时显式将参数设置为 NULL。</span><span class="sxs-lookup"><span data-stu-id="f9644-136">All MAPI implementations of interfaces defined by OLE explicitly set out parameters to NULL on failure.</span></span>  <br/> |
|<span data-ttu-id="f9644-137">尽可能实现可聚合对象。</span><span class="sxs-lookup"><span data-stu-id="f9644-137">Implement aggregatable objects whenever possible.</span></span>  <br/> |<span data-ttu-id="f9644-138">MAPI 接口不可聚合。</span><span class="sxs-lookup"><span data-stu-id="f9644-138">MAPI interfaces are not aggregatable.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="f9644-139">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f9644-139">See also</span></span>



[<span data-ttu-id="f9644-140">MAPIAllocateBuffer</span><span class="sxs-lookup"><span data-stu-id="f9644-140">MAPIAllocateBuffer</span></span>](mapiallocatebuffer.md)
  
[<span data-ttu-id="f9644-141">MAPIAllocateMore</span><span class="sxs-lookup"><span data-stu-id="f9644-141">MAPIAllocateMore</span></span>](mapiallocatemore.md)
  
[<span data-ttu-id="f9644-142">MAPIFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="f9644-142">MAPIFreeBuffer</span></span>](mapifreebuffer.md)


[<span data-ttu-id="f9644-143">MAPI 对象和接口概述</span><span class="sxs-lookup"><span data-stu-id="f9644-143">MAPI Object and Interface Overview</span></span>](mapi-object-and-interface-overview.md)

