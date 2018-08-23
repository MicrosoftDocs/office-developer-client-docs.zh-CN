---
title: 分配和释放 MAPI 中的内存
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: e238f6bc-e9f6-4ea4-a2e4-ff5da2a04bd5
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 2ec5c2604c72d41078aa467764463e2659c62e65
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22587941"
---
# <a name="allocating-and-freeing-memory-in-mapi"></a><span data-ttu-id="aa493-103">分配和释放 MAPI 中的内存</span><span class="sxs-lookup"><span data-stu-id="aa493-103">Allocating and Freeing Memory in MAPI</span></span>

  
  
<span data-ttu-id="aa493-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="aa493-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="aa493-105">除了指定如何分配和释放内存，MAPI 定义了解时应释放调用的公共接口方法和 API 函数之间传递内存模型。</span><span class="sxs-lookup"><span data-stu-id="aa493-105">In addition to specifying how to allocate and free memory, MAPI defines a model for knowing when memory passed between public interface method and API function calls should be freed.</span></span> <span data-ttu-id="aa493-106">模型仅适用于参数不是到接口，如字符串和结构的指针的指针分配内存。</span><span class="sxs-lookup"><span data-stu-id="aa493-106">The model applies only to memory allocated for parameters that are not pointers to interfaces, such as strings and pointers to structures.</span></span> <span data-ttu-id="aa493-107">接口指针使用引用计数通过**IUnknown**实现的机制。</span><span class="sxs-lookup"><span data-stu-id="aa493-107">Interface pointers use the reference counting mechanism implemented through **IUnknown**.</span></span> <span data-ttu-id="aa493-108">分配和释放非 MAPI 相关的内部在客户端应用程序或服务提供商的内存时, 使用任何机制有意义。</span><span class="sxs-lookup"><span data-stu-id="aa493-108">When allocating and freeing non-MAPI related memory internally within a client application or service provider, use whatever mechanism makes sense.</span></span> 
  
<span data-ttu-id="aa493-109">模型定义参数为三种类型之一。</span><span class="sxs-lookup"><span data-stu-id="aa493-109">The model defines parameters as one of three types.</span></span> <span data-ttu-id="aa493-110">可以输入参数，将呼叫者与信息用于通过调用的函数或方法，将设置输出参数、 通过调用的函数或方法设置和返回给调用方或输入输出参数，两种类型的组合。</span><span class="sxs-lookup"><span data-stu-id="aa493-110">They can be input parameters, set by the caller with information to be used by the called function or method, output parameters, set by the called function or method and returned to the caller, or input-output parameters, a combination of the two types.</span></span> <span data-ttu-id="aa493-111">输出参数通常是指向数据或指向数据的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="aa493-111">Output parameters are frequently pointers to data or pointers to pointers to data.</span></span> <span data-ttu-id="aa493-112">尽管调用的函数，负责为输出参数分配数据，呼叫者的指针分配的内存。</span><span class="sxs-lookup"><span data-stu-id="aa493-112">Although the called function is responsible for allocating the data for output parameters, the caller allocates the memory for the pointer.</span></span> 
  
<span data-ttu-id="aa493-113">下表介绍分配和释放内存为这些类型的参数的规则。</span><span class="sxs-lookup"><span data-stu-id="aa493-113">The rules for allocating and releasing memory for these types of parameters are explained in the following table.</span></span>
  
|<span data-ttu-id="aa493-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="aa493-114">**Type**</span></span>|<span data-ttu-id="aa493-115">**内存分配**</span><span class="sxs-lookup"><span data-stu-id="aa493-115">**Memory allocation**</span></span>|<span data-ttu-id="aa493-116">**内存发行版**</span><span class="sxs-lookup"><span data-stu-id="aa493-116">**Memory release**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="aa493-117">输入</span><span class="sxs-lookup"><span data-stu-id="aa493-117">Input</span></span>  <br/> |<span data-ttu-id="aa493-118">呼叫者负责，并且可以使用任何机制。</span><span class="sxs-lookup"><span data-stu-id="aa493-118">Caller is responsible and can use any mechanism.</span></span>  <br/> |<span data-ttu-id="aa493-119">呼叫者负责，并且可以使用任何机制。</span><span class="sxs-lookup"><span data-stu-id="aa493-119">Caller is responsible and can use any mechanism.</span></span>  <br/> |
|<span data-ttu-id="aa493-120">输出</span><span class="sxs-lookup"><span data-stu-id="aa493-120">Output</span></span>  <br/> |<span data-ttu-id="aa493-121">调用的函数负责，且必须使用**MAPIAllocateBuffer**。</span><span class="sxs-lookup"><span data-stu-id="aa493-121">Called function is responsible and must use **MAPIAllocateBuffer**.</span></span> <span data-ttu-id="aa493-122">有关详细信息，请参阅[MAPIAllocateBuffer](mapiallocatebuffer.md)。</span><span class="sxs-lookup"><span data-stu-id="aa493-122">For more information, see [MAPIAllocateBuffer](mapiallocatebuffer.md).</span></span>  <br/> |<span data-ttu-id="aa493-123">呼叫者负责，且必须使用**MAPIFreeBuffer**。</span><span class="sxs-lookup"><span data-stu-id="aa493-123">Caller is responsible and must use **MAPIFreeBuffer**.</span></span> <span data-ttu-id="aa493-124">有关详细信息，请参阅[MAPIFreeBuffer](mapifreebuffer.md)。</span><span class="sxs-lookup"><span data-stu-id="aa493-124">For more information, see [MAPIFreeBuffer](mapifreebuffer.md).</span></span>  <br/> |
|<span data-ttu-id="aa493-125">输入输出</span><span class="sxs-lookup"><span data-stu-id="aa493-125">Input-output</span></span>  <br/> |<span data-ttu-id="aa493-126">呼叫者负责的初始分配和调用的函数可以重新分配必要使用**MAPIAllocateBuffer**。</span><span class="sxs-lookup"><span data-stu-id="aa493-126">Caller is responsible for the initial allocation and called function can reallocate if necessary using **MAPIAllocateBuffer**.</span></span>  <br/> |<span data-ttu-id="aa493-127">必要时重新分配的初始释放调用的函数。</span><span class="sxs-lookup"><span data-stu-id="aa493-127">Called function is responsible for initial freeing if reallocation is necessary.</span></span> <span data-ttu-id="aa493-128">呼叫者必须释放的最终的返回值。</span><span class="sxs-lookup"><span data-stu-id="aa493-128">Caller must free the final return value.</span></span>  <br/> |
   
<span data-ttu-id="aa493-129">在故障情形接口方法的实施者需要特别注意输出和输入输出参数，因为呼叫者通常无法清除它们。</span><span class="sxs-lookup"><span data-stu-id="aa493-129">During failure conditions, implementers of interface methods need to pay attention to output and input-output parameters because the caller generally has no way to clean them up.</span></span> <span data-ttu-id="aa493-130">如果将返回错误，然后每个输出或输入输出参数必须也将保留在初始化呼叫者或设置一个值，而无需任何操作需要呼叫者可以清理为的值。</span><span class="sxs-lookup"><span data-stu-id="aa493-130">If an error is returned, then each output or input-output parameter must either be left at the value initialized by the caller or set to a value that can be cleaned up without any action on the part of the caller.</span></span> <span data-ttu-id="aa493-131">例如，输出指针-参数的`void ** ppv`它已输入，也可以是设置为 NULL，则必须将保留 ( `*ppv = NULL`)。</span><span class="sxs-lookup"><span data-stu-id="aa493-131">For example, an output pointer-parameter of  `void ** ppv` must be left as it was on input or can be set to NULL (  `*ppv = NULL`).</span></span>
  

