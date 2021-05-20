---
title: IMAPISupportMakeInvalid
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISupport.MakeInvalid
api_type:
- COM
ms.assetid: c630ecaf-b19c-4991-9779-e13cc492c755
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 84e87f8a8d3c419afc4b86e200aeaba57e6a85f1
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33427491"
---
# <a name="imapisupportmakeinvalid"></a><span data-ttu-id="f7d07-103">IMAPISupport::MakeInvalid</span><span class="sxs-lookup"><span data-stu-id="f7d07-103">IMAPISupport::MakeInvalid</span></span>

  
  
<span data-ttu-id="f7d07-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="f7d07-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="f7d07-105">将对象标记为不可用。</span><span class="sxs-lookup"><span data-stu-id="f7d07-105">Marks an object as unusable.</span></span>
  
```cpp
HRESULT MakeInvalid(
ULONG ulFlags,
LPVOID lpObject,
ULONG ulRefCount,
ULONG cMethods
);
```

## <a name="parameters"></a><span data-ttu-id="f7d07-106">参数</span><span class="sxs-lookup"><span data-stu-id="f7d07-106">Parameters</span></span>

 <span data-ttu-id="f7d07-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="f7d07-107">_ulFlags_</span></span>
  
> <span data-ttu-id="f7d07-108">保留;必须为零。</span><span class="sxs-lookup"><span data-stu-id="f7d07-108">Reserved; must be zero.</span></span>
    
 <span data-ttu-id="f7d07-109">_lpObject_</span><span class="sxs-lookup"><span data-stu-id="f7d07-109">_lpObject_</span></span>
  
> <span data-ttu-id="f7d07-110">[in]指向要失效的对象的指针。</span><span class="sxs-lookup"><span data-stu-id="f7d07-110">[in] A pointer to the object to be invalidated.</span></span> <span data-ttu-id="f7d07-111">对象的接口必须派生自 **IUnknown**。</span><span class="sxs-lookup"><span data-stu-id="f7d07-111">The object's interface must be derived from **IUnknown**.</span></span>
    
 <span data-ttu-id="f7d07-112">_ulRefCount_</span><span class="sxs-lookup"><span data-stu-id="f7d07-112">_ulRefCount_</span></span>
  
> <span data-ttu-id="f7d07-113">[in]对象的当前引用计数。</span><span class="sxs-lookup"><span data-stu-id="f7d07-113">[in] The object's present reference count.</span></span>
    
 <span data-ttu-id="f7d07-114">_cMethods_</span><span class="sxs-lookup"><span data-stu-id="f7d07-114">_cMethods_</span></span>
  
> <span data-ttu-id="f7d07-115">[in]对象 vtable 中的方法计数。</span><span class="sxs-lookup"><span data-stu-id="f7d07-115">[in] The count of methods in the object's vtable.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="f7d07-116">返回值</span><span class="sxs-lookup"><span data-stu-id="f7d07-116">Return value</span></span>

<span data-ttu-id="f7d07-117">S_OK</span><span class="sxs-lookup"><span data-stu-id="f7d07-117">S_OK</span></span> 
  
> <span data-ttu-id="f7d07-118">对象已成功标记为不可用。</span><span class="sxs-lookup"><span data-stu-id="f7d07-118">The object was successfully marked as unusable.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="f7d07-119">备注</span><span class="sxs-lookup"><span data-stu-id="f7d07-119">Remarks</span></span>

<span data-ttu-id="f7d07-120">**IMAPISupport：：MakeInvalid** 方法针对所有支持对象实现。</span><span class="sxs-lookup"><span data-stu-id="f7d07-120">The **IMAPISupport::MakeInvalid** method is implemented for all support objects.</span></span> <span data-ttu-id="f7d07-121">要失效的对象必须派生自 **IUnknown** 接口或派生自 **IUnknown** 的接口。</span><span class="sxs-lookup"><span data-stu-id="f7d07-121">The object to be invalidated must be derived from the **IUnknown** interface or from an interface derived from **IUnknown**.</span></span>
  
 <span data-ttu-id="f7d07-122">**MakeInvalid** 将对象的 vtable 替换为 **IUnknown：：AddRef** 和 **IUnknown：：Release** 方法按预期执行的大小类似的存根 vtable，从而将对象标记为不可用。</span><span class="sxs-lookup"><span data-stu-id="f7d07-122">**MakeInvalid** marks an object as unusable by replacing the object's vtable with a stub vtable of similar size in which the **IUnknown::AddRef** and **IUnknown::Release** methods perform as expected.</span></span> <span data-ttu-id="f7d07-123">但是，任何其他方法都失败，返回值 MAPI_E_INVALID_OBJECT。</span><span class="sxs-lookup"><span data-stu-id="f7d07-123">However, any other methods fail, returning the value MAPI_E_INVALID_OBJECT.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="f7d07-124">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="f7d07-124">Notes to callers</span></span>

<span data-ttu-id="f7d07-125">服务提供程序和邮件服务通常在关闭时调用 **MakeInvalid。**</span><span class="sxs-lookup"><span data-stu-id="f7d07-125">Service providers and message services typically call **MakeInvalid** at shutdown time.</span></span> <span data-ttu-id="f7d07-126">但是，随时都可以调用 **MakeInvalid。**</span><span class="sxs-lookup"><span data-stu-id="f7d07-126">However, **MakeInvalid** can be called at any time.</span></span> <span data-ttu-id="f7d07-127">例如，如果客户端释放对象而不释放其一些子对象，您可以立即调用 **MakeInvalid** 以释放这些子对象。</span><span class="sxs-lookup"><span data-stu-id="f7d07-127">For example, if a client releases an object without releasing some of its subobjects, you can call **MakeInvalid** immediately to release those subobjects.</span></span> 
  
<span data-ttu-id="f7d07-128">您必须拥有您尝试失效的对象。</span><span class="sxs-lookup"><span data-stu-id="f7d07-128">You must own the object that you attempt to invalidate.</span></span> <span data-ttu-id="f7d07-129">其 vtable 中必须至少有 16 个字节长且至少有三个方法。</span><span class="sxs-lookup"><span data-stu-id="f7d07-129">It must be at least 16 bytes long and have at least three methods in its vtable.</span></span> 
  
<span data-ttu-id="f7d07-130">可以调用 **MakeInvalid，** 然后执行通常在对象发布期间完成的任何关闭工作，例如放弃关联的数据结构。</span><span class="sxs-lookup"><span data-stu-id="f7d07-130">You can call **MakeInvalid** and then perform any shutdown work, such as discarding associated data structures, that is usually done during the release of an object.</span></span> <span data-ttu-id="f7d07-131">支持对象的代码无需保存在内存中，因为 MAPI 通过调用 [MAPIFreeBuffer](mapifreebuffer.md) 释放内存，然后释放对象。</span><span class="sxs-lookup"><span data-stu-id="f7d07-131">Code to support the object need not be kept in memory, because MAPI frees the memory by calling [MAPIFreeBuffer](mapifreebuffer.md) and then releases the object.</span></span> <span data-ttu-id="f7d07-132">您可以释放资源，调用 **MakeInvalid**，然后忽略失效的对象。</span><span class="sxs-lookup"><span data-stu-id="f7d07-132">You can release resources, call **MakeInvalid**, and then ignore the invalidated object.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="f7d07-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f7d07-133">See also</span></span>



[<span data-ttu-id="f7d07-134">MAPIAllocateBuffer</span><span class="sxs-lookup"><span data-stu-id="f7d07-134">MAPIAllocateBuffer</span></span>](mapiallocatebuffer.md)
  
[<span data-ttu-id="f7d07-135">IMAPISupport : IUnknown</span><span class="sxs-lookup"><span data-stu-id="f7d07-135">IMAPISupport : IUnknown</span></span>](imapisupportiunknown.md)

