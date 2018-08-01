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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 595d5fdba28634b038838921102d3125135452a0
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775620"
---
# <a name="imapisupportmakeinvalid"></a><span data-ttu-id="19ea6-103">IMAPISupport::MakeInvalid</span><span class="sxs-lookup"><span data-stu-id="19ea6-103">IMAPISupport::MakeInvalid</span></span>

  
  
<span data-ttu-id="19ea6-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="19ea6-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="19ea6-105">将对象标记为不可用。</span><span class="sxs-lookup"><span data-stu-id="19ea6-105">Marks an object as unusable.</span></span>
  
```cpp
HRESULT MakeInvalid(
ULONG ulFlags,
LPVOID lpObject,
ULONG ulRefCount,
ULONG cMethods
);
```

## <a name="parameters"></a><span data-ttu-id="19ea6-106">参数</span><span class="sxs-lookup"><span data-stu-id="19ea6-106">Parameters</span></span>

 <span data-ttu-id="19ea6-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="19ea6-107">_ulFlags_</span></span>
  
> <span data-ttu-id="19ea6-108">保留;必须为零。</span><span class="sxs-lookup"><span data-stu-id="19ea6-108">Reserved; must be zero.</span></span>
    
 <span data-ttu-id="19ea6-109">_lpObject_</span><span class="sxs-lookup"><span data-stu-id="19ea6-109">_lpObject_</span></span>
  
> <span data-ttu-id="19ea6-110">[in]指向要失效的对象的指针。</span><span class="sxs-lookup"><span data-stu-id="19ea6-110">[in] A pointer to the object to be invalidated.</span></span> <span data-ttu-id="19ea6-111">必须从**iunknown 导出**派生的对象的接口。</span><span class="sxs-lookup"><span data-stu-id="19ea6-111">The object's interface must be derived from **IUnknown**.</span></span>
    
 <span data-ttu-id="19ea6-112">_ulRefCount_</span><span class="sxs-lookup"><span data-stu-id="19ea6-112">_ulRefCount_</span></span>
  
> <span data-ttu-id="19ea6-113">[in]对象的存在此参数引用计数。</span><span class="sxs-lookup"><span data-stu-id="19ea6-113">[in] The object's present reference count.</span></span>
    
 <span data-ttu-id="19ea6-114">_cMethods_</span><span class="sxs-lookup"><span data-stu-id="19ea6-114">_cMethods_</span></span>
  
> <span data-ttu-id="19ea6-115">[in]中对象的 vtable 方法的计数。</span><span class="sxs-lookup"><span data-stu-id="19ea6-115">[in] The count of methods in the object's vtable.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="19ea6-116">返回值</span><span class="sxs-lookup"><span data-stu-id="19ea6-116">Return value</span></span>

<span data-ttu-id="19ea6-117">S_OK</span><span class="sxs-lookup"><span data-stu-id="19ea6-117">S_OK</span></span> 
  
> <span data-ttu-id="19ea6-118">对象已成功地标记为不可用。</span><span class="sxs-lookup"><span data-stu-id="19ea6-118">The object was successfully marked as unusable.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="19ea6-119">说明</span><span class="sxs-lookup"><span data-stu-id="19ea6-119">Remarks</span></span>

<span data-ttu-id="19ea6-120">对于所有支持对象实现**IMAPISupport::MakeInvalid**方法。</span><span class="sxs-lookup"><span data-stu-id="19ea6-120">The **IMAPISupport::MakeInvalid** method is implemented for all support objects.</span></span> <span data-ttu-id="19ea6-121">要将失效的对象必须从**IUnknown**接口或派生自**IUnknown**接口派生。</span><span class="sxs-lookup"><span data-stu-id="19ea6-121">The object to be invalidated must be derived from the **IUnknown** interface or from an interface derived from **IUnknown**.</span></span>
  
 <span data-ttu-id="19ea6-122">**MakeInvalid**对象的 vtable 替换存根 vtable 顺序的**IUnknown::AddRef**和**IUnknown::Release**方法执行预期的类似大小的标记为不可用对象。</span><span class="sxs-lookup"><span data-stu-id="19ea6-122">**MakeInvalid** marks an object as unusable by replacing the object's vtable with a stub vtable of similar size in which the **IUnknown::AddRef** and **IUnknown::Release** methods perform as expected.</span></span> <span data-ttu-id="19ea6-123">但是，任何其他方法失败，返回值 MAPI_E_INVALID_OBJECT。</span><span class="sxs-lookup"><span data-stu-id="19ea6-123">However, any other methods fail, returning the value MAPI_E_INVALID_OBJECT.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="19ea6-124">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="19ea6-124">Notes to callers</span></span>

<span data-ttu-id="19ea6-125">服务提供商和消息服务通常在关闭时调用**MakeInvalid** 。</span><span class="sxs-lookup"><span data-stu-id="19ea6-125">Service providers and message services typically call **MakeInvalid** at shutdown time.</span></span> <span data-ttu-id="19ea6-126">但是，可以随时调用**MakeInvalid** 。</span><span class="sxs-lookup"><span data-stu-id="19ea6-126">However, **MakeInvalid** can be called at any time.</span></span> <span data-ttu-id="19ea6-127">例如，如果客户端版本不释放一些及其子对象的对象，则可以呼叫**MakeInvalid**立即以释放这些子对象。</span><span class="sxs-lookup"><span data-stu-id="19ea6-127">For example, if a client releases an object without releasing some of its subobjects, you can call **MakeInvalid** immediately to release those subobjects.</span></span> 
  
<span data-ttu-id="19ea6-128">您必须拥有您尝试使失效的对象。</span><span class="sxs-lookup"><span data-stu-id="19ea6-128">You must own the object that you attempt to invalidate.</span></span> <span data-ttu-id="19ea6-129">它必须是至少 16 个字节，而且必须在其 vtable 中的至少三种方法。</span><span class="sxs-lookup"><span data-stu-id="19ea6-129">It must be at least 16 bytes long and have at least three methods in its vtable.</span></span> 
  
<span data-ttu-id="19ea6-130">您可以调用**MakeInvalid** ，然后执行任何关闭工作，如放弃关联的数据结构期间释放对象通常完成。</span><span class="sxs-lookup"><span data-stu-id="19ea6-130">You can call **MakeInvalid** and then perform any shutdown work, such as discarding associated data structures, that is usually done during the release of an object.</span></span> <span data-ttu-id="19ea6-131">因为 MAPI 通过调用[MAPIFreeBuffer](mapifreebuffer.md)释放内存，然后释放对象，则不需要在内存中，保留代码以支持的对象。</span><span class="sxs-lookup"><span data-stu-id="19ea6-131">Code to support the object need not be kept in memory, because MAPI frees the memory by calling [MAPIFreeBuffer](mapifreebuffer.md) and then releases the object.</span></span> <span data-ttu-id="19ea6-132">您可以释放资源和呼叫**MakeInvalid**，然后忽略无效的对象。</span><span class="sxs-lookup"><span data-stu-id="19ea6-132">You can release resources, call **MakeInvalid**, and then ignore the invalidated object.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="19ea6-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="19ea6-133">See also</span></span>



[<span data-ttu-id="19ea6-134">MAPIAllocateBuffer</span><span class="sxs-lookup"><span data-stu-id="19ea6-134">MAPIAllocateBuffer</span></span>](mapiallocatebuffer.md)
  
[<span data-ttu-id="19ea6-135">IMAPISupport : IUnknown</span><span class="sxs-lookup"><span data-stu-id="19ea6-135">IMAPISupport : IUnknown</span></span>](imapisupportiunknown.md)

