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
ms.openlocfilehash: cf687a7bfadb0981ca3440c2f81bc5de8f910924
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774689"
---
# <a name="component-object-model-and-mapi"></a><span data-ttu-id="6ff53-103">组件对象模型和 MAPI</span><span class="sxs-lookup"><span data-stu-id="6ff53-103">Component Object Model and MAPI</span></span>

  
  
<span data-ttu-id="6ff53-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="6ff53-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="6ff53-105">Windows SDK 文档中包含的规则实现符合到组件对象模型 (COM) 的对象的全面讨论。</span><span class="sxs-lookup"><span data-stu-id="6ff53-105">The Windows SDK documentation includes a comprehensive discussion of the rules for implementing objects that conform to the Component Object Model (COM).</span></span> <span data-ttu-id="6ff53-106">这些规则地址如何执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="6ff53-106">These rules address how to do the following:</span></span>
  
- <span data-ttu-id="6ff53-107">设计接口和对象。</span><span class="sxs-lookup"><span data-stu-id="6ff53-107">Design interfaces and objects.</span></span>
    
- <span data-ttu-id="6ff53-108">实现[IUnknown](http://msdn.microsoft.com/en-us/library/ms680509%28VS.85%29.aspx)接口。</span><span class="sxs-lookup"><span data-stu-id="6ff53-108">Implement the [IUnknown](http://msdn.microsoft.com/en-us/library/ms680509%28VS.85%29.aspx) interface.</span></span> 
    
- <span data-ttu-id="6ff53-109">管理内存。</span><span class="sxs-lookup"><span data-stu-id="6ff53-109">Manage memory.</span></span>
    
- <span data-ttu-id="6ff53-110">处理引用计数。</span><span class="sxs-lookup"><span data-stu-id="6ff53-110">Handle reference counting.</span></span>
    
- <span data-ttu-id="6ff53-111">实现单元线程对象。</span><span class="sxs-lookup"><span data-stu-id="6ff53-111">Implement apartment-threaded objects.</span></span>
    
<span data-ttu-id="6ff53-112">虽然所有 MAPI 对象都视为基于 COM，这是因为它们实现继承[IUnknown](http://msdn.microsoft.com/en-us/library/ms680509%28VS.85%29.aspx)接口，MAPI 偏离在某些情况下，从标准 COM 的规则。</span><span class="sxs-lookup"><span data-stu-id="6ff53-112">Although all MAPI objects are considered COM-based because they implement interfaces that inherit from [IUnknown](http://msdn.microsoft.com/en-us/library/ms680509%28VS.85%29.aspx), MAPI deviates in some situations from the standard COM rules.</span></span> <span data-ttu-id="6ff53-113">此偏差使开发人员在其实现更大的灵活性。</span><span class="sxs-lookup"><span data-stu-id="6ff53-113">This deviation allows developers more flexibility in their implementations.</span></span> <span data-ttu-id="6ff53-114">例如，任何 COM 接口，类似的 MAPI 界面介绍之间实施和呼叫者的合同。</span><span class="sxs-lookup"><span data-stu-id="6ff53-114">For example, a MAPI interface, like any COM interface, describes a contract between implementer and caller.</span></span> <span data-ttu-id="6ff53-115">后的接口是创建和发布，其定义无法，并且不会更改。</span><span class="sxs-lookup"><span data-stu-id="6ff53-115">Once the interface is created and published, its definition cannot and does not change.</span></span> <span data-ttu-id="6ff53-116">MAPI 不偏离此说明，但它 ア ネ 较解除说明。</span><span class="sxs-lookup"><span data-stu-id="6ff53-116">MAPI does not deviate from this description, but it relaxes the description somewhat.</span></span> <span data-ttu-id="6ff53-117">实施者可以选择不实现特定方法，调用方返回下列错误值之一：</span><span class="sxs-lookup"><span data-stu-id="6ff53-117">Implementers can choose to not implement particular methods, returning one of the following error values to the caller:</span></span> 
  
- <span data-ttu-id="6ff53-118">MAPI_E_NO_SUPPORT</span><span class="sxs-lookup"><span data-stu-id="6ff53-118">MAPI_E_NO_SUPPORT</span></span>
    
- <span data-ttu-id="6ff53-119">MAPI_E_TOO_COMPLEX</span><span class="sxs-lookup"><span data-stu-id="6ff53-119">MAPI_E_TOO_COMPLEX</span></span>
    
- <span data-ttu-id="6ff53-120">MAPI_E_BAD_CHARWIDTH</span><span class="sxs-lookup"><span data-stu-id="6ff53-120">MAPI_E_BAD_CHARWIDTH</span></span>
    
- <span data-ttu-id="6ff53-121">MAPI_E_TYPE_NO_SUPPORT</span><span class="sxs-lookup"><span data-stu-id="6ff53-121">MAPI_E_TYPE_NO_SUPPORT</span></span>
    
<span data-ttu-id="6ff53-122">标准的 COM 规则其他流入下表所述。</span><span class="sxs-lookup"><span data-stu-id="6ff53-122">The other deviations from the standard COM rules are described in the following table.</span></span>
  
|<span data-ttu-id="6ff53-123">**COM 编程规则**</span><span class="sxs-lookup"><span data-stu-id="6ff53-123">**COM programming rule**</span></span>|<span data-ttu-id="6ff53-124">**MAPI 变体**</span><span class="sxs-lookup"><span data-stu-id="6ff53-124">**MAPI variation**</span></span>|
|:-----|:-----|
|<span data-ttu-id="6ff53-125">接口方法中的所有字符串参数应都为 Unicode。</span><span class="sxs-lookup"><span data-stu-id="6ff53-125">All string parameters in interface methods should be Unicode.</span></span>  <br/> |<span data-ttu-id="6ff53-126">MAPI 接口定义允许 Unicode 或 ANSI 字符串参数。</span><span class="sxs-lookup"><span data-stu-id="6ff53-126">MAPI interfaces are defined to permit either Unicode or ANSI string parameters.</span></span> <span data-ttu-id="6ff53-127">具有字符串参数的许多方法还具有**ulFlags**参数;由中**ulFlags**MAPI_UNICODE 标志的值指示字符串参数的宽度。</span><span class="sxs-lookup"><span data-stu-id="6ff53-127">Many methods that have a string parameter also have a **ulFlags** parameter; the width of a string parameter is indicated by the value of the MAPI_UNICODE flag in **ulFlags**.</span></span> <span data-ttu-id="6ff53-128">一些 MAPI 接口不支持 Unicode，并返回 MAPI_E_BAD_CHARWIDTH 时设置 MAPI_UNICODE 标志。</span><span class="sxs-lookup"><span data-stu-id="6ff53-128">Some MAPI interfaces do not support Unicode and return MAPI_E_BAD_CHARWIDTH when the MAPI_UNICODE flag is set.</span></span>  <br/> |
|<span data-ttu-id="6ff53-129">所有接口方法应都具有 HRESULT 返回的类型。</span><span class="sxs-lookup"><span data-stu-id="6ff53-129">All interface methods should have a return type of HRESULT.</span></span>  <br/> |<span data-ttu-id="6ff53-130">MAPI 具有至少一个返回非 HRESULT 值的方法： [IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md)。</span><span class="sxs-lookup"><span data-stu-id="6ff53-130">MAPI has at least one method that returns a non-HRESULT value: [IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md).</span></span>  <br/> |
|<span data-ttu-id="6ff53-131">呼叫者和实施者应分配并使用标准的 COM 任务分配器释放内存接口参数。</span><span class="sxs-lookup"><span data-stu-id="6ff53-131">Callers and implementers should allocate and free memory for interface parameters by using the standard COM task allocators.</span></span>  <br/> |<span data-ttu-id="6ff53-132">所有 MAPI 方法都使用链接的分配器[MAPIAllocateBuffer](mapiallocatebuffer.md)、 [MAPIAllocateMore](mapiallocatemore.md)和[MAPIFreeBuffer](mapifreebuffer.md)管理接口参数的内存。</span><span class="sxs-lookup"><span data-stu-id="6ff53-132">All MAPI methods use the linked allocators [MAPIAllocateBuffer](mapiallocatebuffer.md), [MAPIAllocateMore](mapiallocatemore.md), and [MAPIFreeBuffer](mapifreebuffer.md) to manage memory for interface parameters.</span></span> <span data-ttu-id="6ff53-133">所有 MAPI 实现的接口定义的 OLE，如[IStream](http://msdn.microsoft.com/en-us/library/aa380034%28VS.85%29.aspx)，都使用标准的 COM 任务分配器。</span><span class="sxs-lookup"><span data-stu-id="6ff53-133">All MAPI implementations of interfaces defined by OLE, such as [IStream](http://msdn.microsoft.com/en-us/library/aa380034%28VS.85%29.aspx), use the standard COM task allocators.</span></span>  <br/> |
|<span data-ttu-id="6ff53-134">所有出指针参数必须明确设置为 NULL 时方法将失败。</span><span class="sxs-lookup"><span data-stu-id="6ff53-134">All out pointer parameters must explicitly be set to NULL when a method fails.</span></span>  <br/> |<span data-ttu-id="6ff53-135">MAPI 接口要求的 out 指针参数设置为 NULL 或保持不变，当方法时将失败。</span><span class="sxs-lookup"><span data-stu-id="6ff53-135">MAPI interfaces require that out pointer parameters either be set to NULL or remain unchanged when a method fails.</span></span> <span data-ttu-id="6ff53-136">所有 MAPI 实现的接口定义 OLE 显式设置出故障参数为 NULL。</span><span class="sxs-lookup"><span data-stu-id="6ff53-136">All MAPI implementations of interfaces defined by OLE explicitly set out parameters to NULL on failure.</span></span>  <br/> |
|<span data-ttu-id="6ff53-137">实现尽可能可聚合的对象。</span><span class="sxs-lookup"><span data-stu-id="6ff53-137">Implement aggregatable objects whenever possible.</span></span>  <br/> |<span data-ttu-id="6ff53-138">MAPI 接口不可聚合。</span><span class="sxs-lookup"><span data-stu-id="6ff53-138">MAPI interfaces are not aggregatable.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="6ff53-139">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6ff53-139">See also</span></span>



[<span data-ttu-id="6ff53-140">MAPIAllocateBuffer</span><span class="sxs-lookup"><span data-stu-id="6ff53-140">MAPIAllocateBuffer</span></span>](mapiallocatebuffer.md)
  
[<span data-ttu-id="6ff53-141">MAPIAllocateMore</span><span class="sxs-lookup"><span data-stu-id="6ff53-141">MAPIAllocateMore</span></span>](mapiallocatemore.md)
  
[<span data-ttu-id="6ff53-142">MAPIFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="6ff53-142">MAPIFreeBuffer</span></span>](mapifreebuffer.md)


[<span data-ttu-id="6ff53-143">MAPI 对象和接口概述</span><span class="sxs-lookup"><span data-stu-id="6ff53-143">MAPI Object and Interface Overview</span></span>](mapi-object-and-interface-overview.md)

