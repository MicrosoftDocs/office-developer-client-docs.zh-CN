---
title: IMAPISupportIStorageFromStream
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISupport.IStorageFromStream
api_type:
- COM
ms.assetid: da9e8fdc-dfc5-4ecc-9f9b-b76921b92d7c
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: a73c87f172b4c97379bb9cd117679d3947c188af
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775622"
---
# <a name="imapisupportistoragefromstream"></a><span data-ttu-id="4d50c-103">IMAPISupport::IStorageFromStream</span><span class="sxs-lookup"><span data-stu-id="4d50c-103">IMAPISupport::IStorageFromStream</span></span>

  
  
<span data-ttu-id="4d50c-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="4d50c-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="4d50c-105">实现的存储对象访问的流。</span><span class="sxs-lookup"><span data-stu-id="4d50c-105">Implements a storage object to access a stream.</span></span>
  
```cpp
HRESULT IStorageFromStream(
  LPUNKNOWN lpUnkIn,
  LPCIID lpInterface,
  ULONG ulFlags,
  LPSTORAGE FAR * lppStorageOut
);
```

## <a name="parameters"></a><span data-ttu-id="4d50c-106">参数</span><span class="sxs-lookup"><span data-stu-id="4d50c-106">Parameters</span></span>

 <span data-ttu-id="4d50c-107">_lpUnkIn_</span><span class="sxs-lookup"><span data-stu-id="4d50c-107">_lpUnkIn_</span></span>
  
> <span data-ttu-id="4d50c-108">[in]指向 stream 对象的指针。</span><span class="sxs-lookup"><span data-stu-id="4d50c-108">[in] A pointer to a stream object.</span></span>
    
 <span data-ttu-id="4d50c-109">_lpInterface_</span><span class="sxs-lookup"><span data-stu-id="4d50c-109">_lpInterface_</span></span>
  
> <span data-ttu-id="4d50c-110">[in]指向接口标识 (IID) 值，该值代表要用于访问由_lpUnkIn_指向流的接口的指针。</span><span class="sxs-lookup"><span data-stu-id="4d50c-110">[in] A pointer to the interface identifier (IID) that represents the interface to be used to access the stream pointed to by  _lpUnkIn_.</span></span> <span data-ttu-id="4d50c-111">有有效的下列值： IID_IStream、 IID_ILockBytes，或**为空**，指示是否应使用[IStream](http://msdn.microsoft.com/en-us/library/aa380034%28VS.85%29.aspx)接口访问流。</span><span class="sxs-lookup"><span data-stu-id="4d50c-111">Any of the following values are valid: IID_IStream, IID_ILockBytes, or **null**, which indicates that the [IStream](http://msdn.microsoft.com/en-us/library/aa380034%28VS.85%29.aspx) interface should be used to access the stream.</span></span> 
    
 <span data-ttu-id="4d50c-112">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="4d50c-112">_ulFlags_</span></span>
  
> <span data-ttu-id="4d50c-113">[in]位掩码的标志控制如何存储对象是相对于 stream 对象创建的。</span><span class="sxs-lookup"><span data-stu-id="4d50c-113">[in] A bitmask of flags that controls how the storage object is to be created relative to the stream object.</span></span> <span data-ttu-id="4d50c-114">默认情况下存储创建具有只读访问权限和流开始，在存储中的位置为零。</span><span class="sxs-lookup"><span data-stu-id="4d50c-114">By default, the storage is created with read-only access and the stream starts at position zero in the storage.</span></span> <span data-ttu-id="4d50c-115">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="4d50c-115">The following flags can be set:</span></span>
    
<span data-ttu-id="4d50c-116">STGSTRM_CREATE</span><span class="sxs-lookup"><span data-stu-id="4d50c-116">STGSTRM_CREATE</span></span> 
  
> <span data-ttu-id="4d50c-117">应为 stream 对象创建新的存储对象。</span><span class="sxs-lookup"><span data-stu-id="4d50c-117">A new storage object should be created for the stream object.</span></span>
    
<span data-ttu-id="4d50c-118">STGSTRM_CURRENT</span><span class="sxs-lookup"><span data-stu-id="4d50c-118">STGSTRM_CURRENT</span></span> 
  
> <span data-ttu-id="4d50c-119">存储对象应在当前位置的 stream 的开始。</span><span class="sxs-lookup"><span data-stu-id="4d50c-119">The storage object should start at the current position of the stream.</span></span>
    
<span data-ttu-id="4d50c-120">STGSTRM_MODIFY</span><span class="sxs-lookup"><span data-stu-id="4d50c-120">STGSTRM_MODIFY</span></span> 
  
> <span data-ttu-id="4d50c-121">呼叫者应具有对返回的存储对象的读/写权限。</span><span class="sxs-lookup"><span data-stu-id="4d50c-121">The caller should have read/write permission to the returned storage object.</span></span>
    
<span data-ttu-id="4d50c-122">STGSTRM_RESET</span><span class="sxs-lookup"><span data-stu-id="4d50c-122">STGSTRM_RESET</span></span> 
  
> <span data-ttu-id="4d50c-123">存储对象应开始位置为零。</span><span class="sxs-lookup"><span data-stu-id="4d50c-123">The storage object should start at position zero.</span></span>
    
 <span data-ttu-id="4d50c-124">_lppStorageOut_</span><span class="sxs-lookup"><span data-stu-id="4d50c-124">_lppStorageOut_</span></span>
  
> <span data-ttu-id="4d50c-125">[输出]指向存储对象的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="4d50c-125">[out] A pointer to a pointer to the storage object.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="4d50c-126">返回值</span><span class="sxs-lookup"><span data-stu-id="4d50c-126">Return value</span></span>

<span data-ttu-id="4d50c-127">S_OK</span><span class="sxs-lookup"><span data-stu-id="4d50c-127">S_OK</span></span> 
  
> <span data-ttu-id="4d50c-128">已成功创建的存储对象。</span><span class="sxs-lookup"><span data-stu-id="4d50c-128">The storage object was successfully created.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="4d50c-129">说明</span><span class="sxs-lookup"><span data-stu-id="4d50c-129">Remarks</span></span>

<span data-ttu-id="4d50c-130">**IMAPISupport::IStorageFromStream**方法将执行所有服务提供商支持对象。</span><span class="sxs-lookup"><span data-stu-id="4d50c-130">The **IMAPISupport::IStorageFromStream** method is implemented for all service provider support objects.</span></span> <span data-ttu-id="4d50c-131">服务提供商调用**IStorageFromStream**可创建用于打开特定属性的存储对象。</span><span class="sxs-lookup"><span data-stu-id="4d50c-131">Service providers call **IStorageFromStream** to create a storage object to use for opening particular properties.</span></span> <span data-ttu-id="4d50c-132">[IStorage](http://msdn.microsoft.com/en-us/library/aa380015%28VS.85%29.aspx)接口自己实现服务提供商不需要调用**IStorageFromStream**。</span><span class="sxs-lookup"><span data-stu-id="4d50c-132">Service providers that have their own implementation of the [IStorage](http://msdn.microsoft.com/en-us/library/aa380015%28VS.85%29.aspx) interface do not need to call **IStorageFromStream**.</span></span> 
  
<span data-ttu-id="4d50c-133">时释放存储，由**IStorageFromStream**创建的存储对象将调用的流[IUnknown::AddRef](http://msdn.microsoft.com/en-us/library/ms691379%28v=VS.85%29.aspx)方法来增加其引用计数，然后递减计数。</span><span class="sxs-lookup"><span data-stu-id="4d50c-133">The storage object created by **IStorageFromStream** calls the stream's [IUnknown::AddRef](http://msdn.microsoft.com/en-us/library/ms691379%28v=VS.85%29.aspx) method to increment its reference count and then decrements the count when the storage is released.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="4d50c-134">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="4d50c-134">Notes to callers</span></span>

<span data-ttu-id="4d50c-135">当您对象之一的[IMAPIProp::OpenProperty](imapiprop-openproperty.md)方法调用与**IStorage**接口打开属性时，请执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="4d50c-135">When the [IMAPIProp::OpenProperty](imapiprop-openproperty.md) method of one of your objects is called to open a property with the **IStorage** interface, perform the following tasks:</span></span> 
  
1. <span data-ttu-id="4d50c-136">打开 stream 对象的属性的读/写权限。</span><span class="sxs-lookup"><span data-stu-id="4d50c-136">Open a stream object with read/write permission for the property.</span></span>
    
2. <span data-ttu-id="4d50c-137">内部将属性流标记为存储对象。</span><span class="sxs-lookup"><span data-stu-id="4d50c-137">Internally mark the property stream as a storage object.</span></span>
    
3. <span data-ttu-id="4d50c-138">调用**IStorageFromStream**生成的存储对象。</span><span class="sxs-lookup"><span data-stu-id="4d50c-138">Call **IStorageFromStream** to generate a storage object.</span></span> 
    
4. <span data-ttu-id="4d50c-139">返回到此存储对象的指针。</span><span class="sxs-lookup"><span data-stu-id="4d50c-139">Return a pointer to this storage object.</span></span>
    
<span data-ttu-id="4d50c-140">如果使用的存储对象的附加接口实现，创建包装存储对象的对象和实现更高级别的[IUnknown::QueryInterface](http://msdn.microsoft.com/en-us/library/ms682521%28v=VS.85%29.aspx)方法。</span><span class="sxs-lookup"><span data-stu-id="4d50c-140">If you implement additional interfaces that use the storage object, create an object that wraps the storage object and implement a higher level [IUnknown::QueryInterface](http://msdn.microsoft.com/en-us/library/ms682521%28v=VS.85%29.aspx) method.</span></span> 
  
<span data-ttu-id="4d50c-141">不允许打开与**IStream**接口，如果**IStorage**与创建它的属性。</span><span class="sxs-lookup"><span data-stu-id="4d50c-141">Do not allow a property to be opened with the **IStream** interface if it was created with **IStorage**.</span></span> <span data-ttu-id="4d50c-142">相反，不允许打开与**IStorage**接口，如果**IStream**与创建它的属性。</span><span class="sxs-lookup"><span data-stu-id="4d50c-142">Conversely, do not allow a property to be opened with the **IStorage** interface if it was created with **IStream**.</span></span> 
  
<span data-ttu-id="4d50c-143">有一个例外，它是可以接受使用**IStreamDocfile**接口 stream 从一个容器到另一个存储对象，但必须**OpenProperty**方法_中传递 IID_IStreamDocfile 接口标识符 lpInterface_参数。</span><span class="sxs-lookup"><span data-stu-id="4d50c-143">With one exception, it is acceptable to use the **IStreamDocfile** interface to stream a storage object from one container to another, but the IID_IStreamDocfile interface identifier must be passed in the **OpenProperty** method's  _lpInterface_ parameter.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="4d50c-144">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4d50c-144">See also</span></span>



[<span data-ttu-id="4d50c-145">IMAPIProp::OpenProperty</span><span class="sxs-lookup"><span data-stu-id="4d50c-145">IMAPIProp::OpenProperty</span></span>](imapiprop-openproperty.md)
  
[<span data-ttu-id="4d50c-146">IMAPISupport : IUnknown</span><span class="sxs-lookup"><span data-stu-id="4d50c-146">IMAPISupport : IUnknown</span></span>](imapisupportiunknown.md)

