---
title: 在 MAPI 中分配和释放内存
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: e238f6bc-e9f6-4ea4-a2e4-ff5da2a04bd5
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 68250c5cbeaa366ed4555bb469c4e68d62302f28
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33419665"
---
# <a name="allocating-and-freeing-memory-in-mapi"></a><span data-ttu-id="9de3e-103">在 MAPI 中分配和释放内存</span><span class="sxs-lookup"><span data-stu-id="9de3e-103">Allocating and Freeing Memory in MAPI</span></span>

  
  
<span data-ttu-id="9de3e-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="9de3e-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="9de3e-105">除了指定如何分配和释放内存，MAPI 还定义了一个模型，用于了解何时应释放在公共接口方法和 API 函数调用之间传递的内存。</span><span class="sxs-lookup"><span data-stu-id="9de3e-105">In addition to specifying how to allocate and free memory, MAPI defines a model for knowing when memory passed between public interface method and API function calls should be freed.</span></span> <span data-ttu-id="9de3e-106">模型仅适用于分配给不是指向接口的指针的参数（如字符串和指向结构的指针）的内存。</span><span class="sxs-lookup"><span data-stu-id="9de3e-106">The model applies only to memory allocated for parameters that are not pointers to interfaces, such as strings and pointers to structures.</span></span> <span data-ttu-id="9de3e-107">接口指针使用通过 **IUnknown** 实现的引用计数机制。</span><span class="sxs-lookup"><span data-stu-id="9de3e-107">Interface pointers use the reference counting mechanism implemented through **IUnknown**.</span></span> <span data-ttu-id="9de3e-108">在客户端应用程序或服务提供商内部分配和释放非 MAPI 相关内存时，请使用任何有意义的机制。</span><span class="sxs-lookup"><span data-stu-id="9de3e-108">When allocating and freeing non-MAPI related memory internally within a client application or service provider, use whatever mechanism makes sense.</span></span> 
  
<span data-ttu-id="9de3e-109">模型将参数定义为三种类型之一。</span><span class="sxs-lookup"><span data-stu-id="9de3e-109">The model defines parameters as one of three types.</span></span> <span data-ttu-id="9de3e-110">它们可以是输入参数，由调用方设置，以及由被调用的函数或方法使用的信息、输出参数、由调用的函数或方法设置并返回到调用方或输入输出参数（两种类型的组合）。</span><span class="sxs-lookup"><span data-stu-id="9de3e-110">They can be input parameters, set by the caller with information to be used by the called function or method, output parameters, set by the called function or method and returned to the caller, or input-output parameters, a combination of the two types.</span></span> <span data-ttu-id="9de3e-111">输出参数通常是指向数据的指针或指向指向数据的指针。</span><span class="sxs-lookup"><span data-stu-id="9de3e-111">Output parameters are frequently pointers to data or pointers to pointers to data.</span></span> <span data-ttu-id="9de3e-112">尽管调用的函数负责为输出参数分配数据，但是调用方会为指针分配内存。</span><span class="sxs-lookup"><span data-stu-id="9de3e-112">Although the called function is responsible for allocating the data for output parameters, the caller allocates the memory for the pointer.</span></span> 
  
<span data-ttu-id="9de3e-113">下表介绍了为这些类型的参数分配和释放内存的规则。</span><span class="sxs-lookup"><span data-stu-id="9de3e-113">The rules for allocating and releasing memory for these types of parameters are explained in the following table.</span></span>
  
|<span data-ttu-id="9de3e-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="9de3e-114">**Type**</span></span>|<span data-ttu-id="9de3e-115">**内存分配**</span><span class="sxs-lookup"><span data-stu-id="9de3e-115">**Memory allocation**</span></span>|<span data-ttu-id="9de3e-116">**内存释放**</span><span class="sxs-lookup"><span data-stu-id="9de3e-116">**Memory release**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="9de3e-117">Input</span><span class="sxs-lookup"><span data-stu-id="9de3e-117">Input</span></span>  <br/> |<span data-ttu-id="9de3e-118">呼叫者负责，可以使用任何机制。</span><span class="sxs-lookup"><span data-stu-id="9de3e-118">Caller is responsible and can use any mechanism.</span></span>  <br/> |<span data-ttu-id="9de3e-119">呼叫者负责，可以使用任何机制。</span><span class="sxs-lookup"><span data-stu-id="9de3e-119">Caller is responsible and can use any mechanism.</span></span>  <br/> |
|<span data-ttu-id="9de3e-120">输出</span><span class="sxs-lookup"><span data-stu-id="9de3e-120">Output</span></span>  <br/> |<span data-ttu-id="9de3e-121">调用的函数负责，必须使用 **MAPIAllocateBuffer**。</span><span class="sxs-lookup"><span data-stu-id="9de3e-121">Called function is responsible and must use **MAPIAllocateBuffer**.</span></span> <span data-ttu-id="9de3e-122">有关详细信息，请参阅 [MAPIAllocateBuffer](mapiallocatebuffer.md)。</span><span class="sxs-lookup"><span data-stu-id="9de3e-122">For more information, see [MAPIAllocateBuffer](mapiallocatebuffer.md).</span></span>  <br/> |<span data-ttu-id="9de3e-123">呼叫者负责，必须使用 **MAPIFreeBuffer**。</span><span class="sxs-lookup"><span data-stu-id="9de3e-123">Caller is responsible and must use **MAPIFreeBuffer**.</span></span> <span data-ttu-id="9de3e-124">有关详细信息，请参阅 [MAPIFreeBuffer](mapifreebuffer.md)。</span><span class="sxs-lookup"><span data-stu-id="9de3e-124">For more information, see [MAPIFreeBuffer](mapifreebuffer.md).</span></span>  <br/> |
|<span data-ttu-id="9de3e-125">输入输出</span><span class="sxs-lookup"><span data-stu-id="9de3e-125">Input-output</span></span>  <br/> |<span data-ttu-id="9de3e-126">调用方负责初始分配，调用的函数可在必要时使用 **MAPIAllocateBuffer 重新分配**。</span><span class="sxs-lookup"><span data-stu-id="9de3e-126">Caller is responsible for the initial allocation and called function can reallocate if necessary using **MAPIAllocateBuffer**.</span></span>  <br/> |<span data-ttu-id="9de3e-127">调用的函数负责在需要重新分配时进行初始释放。</span><span class="sxs-lookup"><span data-stu-id="9de3e-127">Called function is responsible for initial freeing if reallocation is necessary.</span></span> <span data-ttu-id="9de3e-128">调用方必须释放最终的返回值。</span><span class="sxs-lookup"><span data-stu-id="9de3e-128">Caller must free the final return value.</span></span>  <br/> |
   
<span data-ttu-id="9de3e-129">在故障期间，接口方法的实现者需要注意输出和输入输出参数，因为调用方通常无法清理它们。</span><span class="sxs-lookup"><span data-stu-id="9de3e-129">During failure conditions, implementers of interface methods need to pay attention to output and input-output parameters because the caller generally has no way to clean them up.</span></span> <span data-ttu-id="9de3e-130">如果返回错误，则必须将每个输出或输入输出参数都保持为调用方初始化的值，或设置为无需调用方的任何操作即可清理的值。</span><span class="sxs-lookup"><span data-stu-id="9de3e-130">If an error is returned, then each output or input-output parameter must either be left at the value initialized by the caller or set to a value that can be cleaned up without any action on the part of the caller.</span></span> <span data-ttu-id="9de3e-131">例如，必须将 的输出 pointer-parameter 保留为 在输入时，也可以设置为 NULL (  `void ** ppv`  `*ppv = NULL`) 。</span><span class="sxs-lookup"><span data-stu-id="9de3e-131">For example, an output pointer-parameter of  `void ** ppv` must be left as it was on input or can be set to NULL (  `*ppv = NULL`).</span></span>
  

