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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32316658"
---
# <a name="imapisupportmakeinvalid"></a><span data-ttu-id="9de81-103">IMAPISupport::MakeInvalid</span><span class="sxs-lookup"><span data-stu-id="9de81-103">IMAPISupport::MakeInvalid</span></span>

  
  
<span data-ttu-id="9de81-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="9de81-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="9de81-105">将对象标记为不可用。</span><span class="sxs-lookup"><span data-stu-id="9de81-105">Marks an object as unusable.</span></span>
  
```cpp
HRESULT MakeInvalid(
ULONG ulFlags,
LPVOID lpObject,
ULONG ulRefCount,
ULONG cMethods
);
```

## <a name="parameters"></a><span data-ttu-id="9de81-106">参数</span><span class="sxs-lookup"><span data-stu-id="9de81-106">Parameters</span></span>

 <span data-ttu-id="9de81-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="9de81-107">_ulFlags_</span></span>
  
> <span data-ttu-id="9de81-108">保留必须为零。</span><span class="sxs-lookup"><span data-stu-id="9de81-108">Reserved; must be zero.</span></span>
    
 <span data-ttu-id="9de81-109">_lpObject_</span><span class="sxs-lookup"><span data-stu-id="9de81-109">_lpObject_</span></span>
  
> <span data-ttu-id="9de81-110">实时指向要无效的对象的指针。</span><span class="sxs-lookup"><span data-stu-id="9de81-110">[in] A pointer to the object to be invalidated.</span></span> <span data-ttu-id="9de81-111">对象的接口必须从**IUnknown**派生。</span><span class="sxs-lookup"><span data-stu-id="9de81-111">The object's interface must be derived from **IUnknown**.</span></span>
    
 <span data-ttu-id="9de81-112">_ulRefCount_</span><span class="sxs-lookup"><span data-stu-id="9de81-112">_ulRefCount_</span></span>
  
> <span data-ttu-id="9de81-113">实时对象的当前引用计数。</span><span class="sxs-lookup"><span data-stu-id="9de81-113">[in] The object's present reference count.</span></span>
    
 <span data-ttu-id="9de81-114">_cMethods_</span><span class="sxs-lookup"><span data-stu-id="9de81-114">_cMethods_</span></span>
  
> <span data-ttu-id="9de81-115">实时对象的 vtable 中的方法数。</span><span class="sxs-lookup"><span data-stu-id="9de81-115">[in] The count of methods in the object's vtable.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="9de81-116">返回值</span><span class="sxs-lookup"><span data-stu-id="9de81-116">Return value</span></span>

<span data-ttu-id="9de81-117">S_OK</span><span class="sxs-lookup"><span data-stu-id="9de81-117">S_OK</span></span> 
  
> <span data-ttu-id="9de81-118">已成功将该对象标记为不可用。</span><span class="sxs-lookup"><span data-stu-id="9de81-118">The object was successfully marked as unusable.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="9de81-119">注解</span><span class="sxs-lookup"><span data-stu-id="9de81-119">Remarks</span></span>

<span data-ttu-id="9de81-120">**IMAPISupport:: MakeInvalid**方法是为所有支持对象实现的。</span><span class="sxs-lookup"><span data-stu-id="9de81-120">The **IMAPISupport::MakeInvalid** method is implemented for all support objects.</span></span> <span data-ttu-id="9de81-121">要使其失效的对象必须从**iunknown**接口或从**iunknown**派生的接口派生。</span><span class="sxs-lookup"><span data-stu-id="9de81-121">The object to be invalidated must be derived from the **IUnknown** interface or from an interface derived from **IUnknown**.</span></span>
  
 <span data-ttu-id="9de81-122">**MakeInvalid**通过将对象的 vtable 替换为大小相同且**iunknown:: AddRef**和**IUnknown:: Release**方法按预期执行的存根 vtable, 将对象标记为不可用。</span><span class="sxs-lookup"><span data-stu-id="9de81-122">**MakeInvalid** marks an object as unusable by replacing the object's vtable with a stub vtable of similar size in which the **IUnknown::AddRef** and **IUnknown::Release** methods perform as expected.</span></span> <span data-ttu-id="9de81-123">但是, 任何其他方法都将失败, 返回值 MAPI_E_INVALID_OBJECT。</span><span class="sxs-lookup"><span data-stu-id="9de81-123">However, any other methods fail, returning the value MAPI_E_INVALID_OBJECT.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="9de81-124">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="9de81-124">Notes to callers</span></span>

<span data-ttu-id="9de81-125">服务提供商和邮件服务通常会在关机时调用**MakeInvalid** 。</span><span class="sxs-lookup"><span data-stu-id="9de81-125">Service providers and message services typically call **MakeInvalid** at shutdown time.</span></span> <span data-ttu-id="9de81-126">但是, 可以随时调用**MakeInvalid** 。</span><span class="sxs-lookup"><span data-stu-id="9de81-126">However, **MakeInvalid** can be called at any time.</span></span> <span data-ttu-id="9de81-127">例如, 如果客户端释放对象而不释放它的一些子对象, 则可以立即调用**MakeInvalid**以释放这些子对象。</span><span class="sxs-lookup"><span data-stu-id="9de81-127">For example, if a client releases an object without releasing some of its subobjects, you can call **MakeInvalid** immediately to release those subobjects.</span></span> 
  
<span data-ttu-id="9de81-128">您必须拥有试图使其无效的对象。</span><span class="sxs-lookup"><span data-stu-id="9de81-128">You must own the object that you attempt to invalidate.</span></span> <span data-ttu-id="9de81-129">它的长度必须至少为16个字节, 并且在 vtable 中至少有三个方法。</span><span class="sxs-lookup"><span data-stu-id="9de81-129">It must be at least 16 bytes long and have at least three methods in its vtable.</span></span> 
  
<span data-ttu-id="9de81-130">您可以调用**MakeInvalid** , 然后执行任何关闭工作 (如丢弃关联的数据结构), 这通常在对象的发布过程中完成。</span><span class="sxs-lookup"><span data-stu-id="9de81-130">You can call **MakeInvalid** and then perform any shutdown work, such as discarding associated data structures, that is usually done during the release of an object.</span></span> <span data-ttu-id="9de81-131">支持该对象的代码不需要保留在内存中, 因为 MAPI 通过调用[MAPIFreeBuffer](mapifreebuffer.md)来释放内存, 然后释放该对象。</span><span class="sxs-lookup"><span data-stu-id="9de81-131">Code to support the object need not be kept in memory, because MAPI frees the memory by calling [MAPIFreeBuffer](mapifreebuffer.md) and then releases the object.</span></span> <span data-ttu-id="9de81-132">您可以释放资源, 调用**MakeInvalid**, 然后忽略无效的对象。</span><span class="sxs-lookup"><span data-stu-id="9de81-132">You can release resources, call **MakeInvalid**, and then ignore the invalidated object.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="9de81-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9de81-133">See also</span></span>



[<span data-ttu-id="9de81-134">MAPIAllocateBuffer</span><span class="sxs-lookup"><span data-stu-id="9de81-134">MAPIAllocateBuffer</span></span>](mapiallocatebuffer.md)
  
[<span data-ttu-id="9de81-135">IMAPISupport : IUnknown</span><span class="sxs-lookup"><span data-stu-id="9de81-135">IMAPISupport : IUnknown</span></span>](imapisupportiunknown.md)

