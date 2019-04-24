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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32281583"
---
# <a name="allocating-and-freeing-memory-in-mapi"></a><span data-ttu-id="06baf-103">在 MAPI 中分配和释放内存</span><span class="sxs-lookup"><span data-stu-id="06baf-103">Allocating and Freeing Memory in MAPI</span></span>

  
  
<span data-ttu-id="06baf-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="06baf-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="06baf-105">除了指定如何分配和释放内存之外, MAPI 还定义一个模型, 以了解在何时释放公共接口方法和 API 函数调用之间传递的内存。</span><span class="sxs-lookup"><span data-stu-id="06baf-105">In addition to specifying how to allocate and free memory, MAPI defines a model for knowing when memory passed between public interface method and API function calls should be freed.</span></span> <span data-ttu-id="06baf-106">模型仅适用于为不是指向接口的指针 (如字符串和指向结构的指针) 的参数分配的内存。</span><span class="sxs-lookup"><span data-stu-id="06baf-106">The model applies only to memory allocated for parameters that are not pointers to interfaces, such as strings and pointers to structures.</span></span> <span data-ttu-id="06baf-107">接口指针使用通过**IUnknown**实现的引用计数机制。</span><span class="sxs-lookup"><span data-stu-id="06baf-107">Interface pointers use the reference counting mechanism implemented through **IUnknown**.</span></span> <span data-ttu-id="06baf-108">在客户端应用程序或服务提供程序内部分配和释放与非 MAPI 相关的内存时, 请使用任何有意义的机制。</span><span class="sxs-lookup"><span data-stu-id="06baf-108">When allocating and freeing non-MAPI related memory internally within a client application or service provider, use whatever mechanism makes sense.</span></span> 
  
<span data-ttu-id="06baf-109">模型将参数定义为以下三种类型之一。</span><span class="sxs-lookup"><span data-stu-id="06baf-109">The model defines parameters as one of three types.</span></span> <span data-ttu-id="06baf-110">它们可以是输入参数, 由调用方设置, 由调用的函数或方法、输出参数、被调用的函数或方法设置并返回给调用方或输入输出参数 (这两种类型的组合) 所使用的信息。</span><span class="sxs-lookup"><span data-stu-id="06baf-110">They can be input parameters, set by the caller with information to be used by the called function or method, output parameters, set by the called function or method and returned to the caller, or input-output parameters, a combination of the two types.</span></span> <span data-ttu-id="06baf-111">输出参数通常是指向数据的数据或指向数据的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="06baf-111">Output parameters are frequently pointers to data or pointers to pointers to data.</span></span> <span data-ttu-id="06baf-112">虽然被调用的函数负责为输出参数分配数据, 但调用方为指针分配内存。</span><span class="sxs-lookup"><span data-stu-id="06baf-112">Although the called function is responsible for allocating the data for output parameters, the caller allocates the memory for the pointer.</span></span> 
  
<span data-ttu-id="06baf-113">下表介绍了为这些类型的参数分配和释放内存的规则。</span><span class="sxs-lookup"><span data-stu-id="06baf-113">The rules for allocating and releasing memory for these types of parameters are explained in the following table.</span></span>
  
|<span data-ttu-id="06baf-114">**Type**</span><span class="sxs-lookup"><span data-stu-id="06baf-114">**Type**</span></span>|<span data-ttu-id="06baf-115">**内存分配**</span><span class="sxs-lookup"><span data-stu-id="06baf-115">**Memory allocation**</span></span>|<span data-ttu-id="06baf-116">**内存释放**</span><span class="sxs-lookup"><span data-stu-id="06baf-116">**Memory release**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="06baf-117">Input</span><span class="sxs-lookup"><span data-stu-id="06baf-117">Input</span></span>  <br/> |<span data-ttu-id="06baf-118">呼叫者负责, 并且可以使用任何机制。</span><span class="sxs-lookup"><span data-stu-id="06baf-118">Caller is responsible and can use any mechanism.</span></span>  <br/> |<span data-ttu-id="06baf-119">呼叫者负责, 并且可以使用任何机制。</span><span class="sxs-lookup"><span data-stu-id="06baf-119">Caller is responsible and can use any mechanism.</span></span>  <br/> |
|<span data-ttu-id="06baf-120">Output</span><span class="sxs-lookup"><span data-stu-id="06baf-120">Output</span></span>  <br/> |<span data-ttu-id="06baf-121">被叫函数负责, 必须使用**MAPIAllocateBuffer**。</span><span class="sxs-lookup"><span data-stu-id="06baf-121">Called function is responsible and must use **MAPIAllocateBuffer**.</span></span> <span data-ttu-id="06baf-122">有关详细信息, 请参阅[MAPIAllocateBuffer](mapiallocatebuffer.md)。</span><span class="sxs-lookup"><span data-stu-id="06baf-122">For more information, see [MAPIAllocateBuffer](mapiallocatebuffer.md).</span></span>  <br/> |<span data-ttu-id="06baf-123">呼叫者负责, 必须使用**MAPIFreeBuffer**。</span><span class="sxs-lookup"><span data-stu-id="06baf-123">Caller is responsible and must use **MAPIFreeBuffer**.</span></span> <span data-ttu-id="06baf-124">有关详细信息, 请参阅[MAPIFreeBuffer](mapifreebuffer.md)。</span><span class="sxs-lookup"><span data-stu-id="06baf-124">For more information, see [MAPIFreeBuffer](mapifreebuffer.md).</span></span>  <br/> |
|<span data-ttu-id="06baf-125">输入输出</span><span class="sxs-lookup"><span data-stu-id="06baf-125">Input-output</span></span>  <br/> |<span data-ttu-id="06baf-126">如果需要, 调用方负责使用**MAPIAllocateBuffer**来重新分配初始分配和被调用函数。</span><span class="sxs-lookup"><span data-stu-id="06baf-126">Caller is responsible for the initial allocation and called function can reallocate if necessary using **MAPIAllocateBuffer**.</span></span>  <br/> |<span data-ttu-id="06baf-127">如果需要重新分配, 则调用的函数负责初始化释放。</span><span class="sxs-lookup"><span data-stu-id="06baf-127">Called function is responsible for initial freeing if reallocation is necessary.</span></span> <span data-ttu-id="06baf-128">调用方必须释放最终返回值。</span><span class="sxs-lookup"><span data-stu-id="06baf-128">Caller must free the final return value.</span></span>  <br/> |
   
<span data-ttu-id="06baf-129">在失败情况下, 接口方法的实现者需要注意输出和输入输出参数, 因为调用方通常无法清除它们。</span><span class="sxs-lookup"><span data-stu-id="06baf-129">During failure conditions, implementers of interface methods need to pay attention to output and input-output parameters because the caller generally has no way to clean them up.</span></span> <span data-ttu-id="06baf-130">如果返回错误, 则必须将每个输出或输入输出参数保留为调用方初始化的值, 或设置为一个可清除的值, 而不是调用方的任何操作。</span><span class="sxs-lookup"><span data-stu-id="06baf-130">If an error is returned, then each output or input-output parameter must either be left at the value initialized by the caller or set to a value that can be cleaned up without any action on the part of the caller.</span></span> <span data-ttu-id="06baf-131">例如, 的`void ** ppv`输出指针参数必须保留在输入中, 或可设置为 NULL ( `*ppv = NULL`)。</span><span class="sxs-lookup"><span data-stu-id="06baf-131">For example, an output pointer-parameter of  `void ** ppv` must be left as it was on input or can be set to NULL (  `*ppv = NULL`).</span></span>
  

