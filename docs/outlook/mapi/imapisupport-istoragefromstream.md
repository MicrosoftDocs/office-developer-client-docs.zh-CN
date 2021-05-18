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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 7200e7d226eb148fef094ab8540990644d2d4c99
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32316585"
---
# <a name="imapisupportistoragefromstream"></a><span data-ttu-id="448df-103">IMAPISupport::IStorageFromStream</span><span class="sxs-lookup"><span data-stu-id="448df-103">IMAPISupport::IStorageFromStream</span></span>

  
  
<span data-ttu-id="448df-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="448df-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="448df-105">实现存储对象以访问流。</span><span class="sxs-lookup"><span data-stu-id="448df-105">Implements a storage object to access a stream.</span></span>
  
```cpp
HRESULT IStorageFromStream(
  LPUNKNOWN lpUnkIn,
  LPCIID lpInterface,
  ULONG ulFlags,
  LPSTORAGE FAR * lppStorageOut
);
```

## <a name="parameters"></a><span data-ttu-id="448df-106">参数</span><span class="sxs-lookup"><span data-stu-id="448df-106">Parameters</span></span>

 <span data-ttu-id="448df-107">_lpUnkIn_</span><span class="sxs-lookup"><span data-stu-id="448df-107">_lpUnkIn_</span></span>
  
> <span data-ttu-id="448df-108">[in]指向 stream 对象的指针。</span><span class="sxs-lookup"><span data-stu-id="448df-108">[in] A pointer to a stream object.</span></span>
    
 <span data-ttu-id="448df-109">_lpInterface_</span><span class="sxs-lookup"><span data-stu-id="448df-109">_lpInterface_</span></span>
  
> <span data-ttu-id="448df-110">[in]指向接口标识符的指针 (IID) 表示用于访问  _lpUnkIn_ 指向的流的接口。</span><span class="sxs-lookup"><span data-stu-id="448df-110">[in] A pointer to the interface identifier (IID) that represents the interface to be used to access the stream pointed to by  _lpUnkIn_.</span></span> <span data-ttu-id="448df-111">以下任一值均有效：IID_IStream、IID_ILockBytes 或 **null，** 指示 [IStream](https://msdn.microsoft.com/library/aa380034%28VS.85%29.aspx) 接口应该用于访问流。</span><span class="sxs-lookup"><span data-stu-id="448df-111">Any of the following values are valid: IID_IStream, IID_ILockBytes, or **null**, which indicates that the [IStream](https://msdn.microsoft.com/library/aa380034%28VS.85%29.aspx) interface should be used to access the stream.</span></span> 
    
 <span data-ttu-id="448df-112">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="448df-112">_ulFlags_</span></span>
  
> <span data-ttu-id="448df-113">[in]控制存储对象的创建方式（相对于流对象）的位掩码。</span><span class="sxs-lookup"><span data-stu-id="448df-113">[in] A bitmask of flags that controls how the storage object is to be created relative to the stream object.</span></span> <span data-ttu-id="448df-114">默认情况下，使用只读访问权限创建存储，并且流从存储中的位置零开始。</span><span class="sxs-lookup"><span data-stu-id="448df-114">By default, the storage is created with read-only access and the stream starts at position zero in the storage.</span></span> <span data-ttu-id="448df-115">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="448df-115">The following flags can be set:</span></span>
    
<span data-ttu-id="448df-116">STGSTRM_CREATE</span><span class="sxs-lookup"><span data-stu-id="448df-116">STGSTRM_CREATE</span></span> 
  
> <span data-ttu-id="448df-117">应为流对象创建一个新的存储对象。</span><span class="sxs-lookup"><span data-stu-id="448df-117">A new storage object should be created for the stream object.</span></span>
    
<span data-ttu-id="448df-118">STGSTRM_CURRENT</span><span class="sxs-lookup"><span data-stu-id="448df-118">STGSTRM_CURRENT</span></span> 
  
> <span data-ttu-id="448df-119">存储对象应从流的当前位置开始。</span><span class="sxs-lookup"><span data-stu-id="448df-119">The storage object should start at the current position of the stream.</span></span>
    
<span data-ttu-id="448df-120">STGSTRM_MODIFY</span><span class="sxs-lookup"><span data-stu-id="448df-120">STGSTRM_MODIFY</span></span> 
  
> <span data-ttu-id="448df-121">调用方应具有对返回的存储对象的读/写权限。</span><span class="sxs-lookup"><span data-stu-id="448df-121">The caller should have read/write permission to the returned storage object.</span></span>
    
<span data-ttu-id="448df-122">STGSTRM_RESET</span><span class="sxs-lookup"><span data-stu-id="448df-122">STGSTRM_RESET</span></span> 
  
> <span data-ttu-id="448df-123">存储对象应从零位置开始。</span><span class="sxs-lookup"><span data-stu-id="448df-123">The storage object should start at position zero.</span></span>
    
 <span data-ttu-id="448df-124">_lppStorageOut_</span><span class="sxs-lookup"><span data-stu-id="448df-124">_lppStorageOut_</span></span>
  
> <span data-ttu-id="448df-125">[out]指向存储对象的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="448df-125">[out] A pointer to a pointer to the storage object.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="448df-126">返回值</span><span class="sxs-lookup"><span data-stu-id="448df-126">Return value</span></span>

<span data-ttu-id="448df-127">S_OK</span><span class="sxs-lookup"><span data-stu-id="448df-127">S_OK</span></span> 
  
> <span data-ttu-id="448df-128">已成功创建存储对象。</span><span class="sxs-lookup"><span data-stu-id="448df-128">The storage object was successfully created.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="448df-129">备注</span><span class="sxs-lookup"><span data-stu-id="448df-129">Remarks</span></span>

<span data-ttu-id="448df-130">**IMAPISupport：：IStorageFromStream** 方法针对所有服务提供商支持对象实现。</span><span class="sxs-lookup"><span data-stu-id="448df-130">The **IMAPISupport::IStorageFromStream** method is implemented for all service provider support objects.</span></span> <span data-ttu-id="448df-131">服务提供商调用 **IStorageFromStream** 来创建用于打开特定属性的存储对象。</span><span class="sxs-lookup"><span data-stu-id="448df-131">Service providers call **IStorageFromStream** to create a storage object to use for opening particular properties.</span></span> <span data-ttu-id="448df-132">具有自己的 [IStorage](https://msdn.microsoft.com/library/aa380015%28VS.85%29.aspx) 接口实现的服务提供商不需要调用 **IStorageFromStream**。</span><span class="sxs-lookup"><span data-stu-id="448df-132">Service providers that have their own implementation of the [IStorage](https://msdn.microsoft.com/library/aa380015%28VS.85%29.aspx) interface do not need to call **IStorageFromStream**.</span></span> 
  
<span data-ttu-id="448df-133">**IStorageFromStream** 创建的存储对象调用流的 [IUnknown：：AddRef](https://msdn.microsoft.com/library/ms691379%28v=VS.85%29.aspx)方法来增加其引用计数，然后在释放存储时减量。</span><span class="sxs-lookup"><span data-stu-id="448df-133">The storage object created by **IStorageFromStream** calls the stream's [IUnknown::AddRef](https://msdn.microsoft.com/library/ms691379%28v=VS.85%29.aspx) method to increment its reference count and then decrements the count when the storage is released.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="448df-134">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="448df-134">Notes to callers</span></span>

<span data-ttu-id="448df-135">调用其中一个对象 [的 IMAPIProp：：OpenProperty](imapiprop-openproperty.md) 方法以使用 **IStorage** 接口打开属性时，请执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="448df-135">When the [IMAPIProp::OpenProperty](imapiprop-openproperty.md) method of one of your objects is called to open a property with the **IStorage** interface, perform the following tasks:</span></span> 
  
1. <span data-ttu-id="448df-136">使用属性的读/写权限打开 stream 对象。</span><span class="sxs-lookup"><span data-stu-id="448df-136">Open a stream object with read/write permission for the property.</span></span>
    
2. <span data-ttu-id="448df-137">在内部将属性流标记为存储对象。</span><span class="sxs-lookup"><span data-stu-id="448df-137">Internally mark the property stream as a storage object.</span></span>
    
3. <span data-ttu-id="448df-138">调用 **IStorageFromStream** 以生成存储对象。</span><span class="sxs-lookup"><span data-stu-id="448df-138">Call **IStorageFromStream** to generate a storage object.</span></span> 
    
4. <span data-ttu-id="448df-139">返回指向此存储对象的指针。</span><span class="sxs-lookup"><span data-stu-id="448df-139">Return a pointer to this storage object.</span></span>
    
<span data-ttu-id="448df-140">如果实现使用存储对象的其他接口，请创建包装存储对象并实现更高级别的 [IUnknown：：QueryInterface 方法的对象](https://msdn.microsoft.com/library/ms682521%28v=VS.85%29.aspx) 。</span><span class="sxs-lookup"><span data-stu-id="448df-140">If you implement additional interfaces that use the storage object, create an object that wraps the storage object and implement a higher level [IUnknown::QueryInterface](https://msdn.microsoft.com/library/ms682521%28v=VS.85%29.aspx) method.</span></span> 
  
<span data-ttu-id="448df-141">如果属性是使用 **IStorage** 创建的，则不允许使用 **IStream** 接口打开该属性。</span><span class="sxs-lookup"><span data-stu-id="448df-141">Do not allow a property to be opened with the **IStream** interface if it was created with **IStorage**.</span></span> <span data-ttu-id="448df-142">相反，如果属性是使用 IStream 创建的，则不允许使用 **IStorage** 接口 **打开它**。</span><span class="sxs-lookup"><span data-stu-id="448df-142">Conversely, do not allow a property to be opened with the **IStorage** interface if it was created with **IStream**.</span></span> 
  
<span data-ttu-id="448df-143">可以使用 **IStreamDocfile** 接口将存储对象从一个容器流式传输到另一个容器，但 IID_IStreamDocfile 接口标识符必须在 **OpenProperty** 方法的  _lpInterface_ 参数中传递。</span><span class="sxs-lookup"><span data-stu-id="448df-143">With one exception, it is acceptable to use the **IStreamDocfile** interface to stream a storage object from one container to another, but the IID_IStreamDocfile interface identifier must be passed in the **OpenProperty** method's  _lpInterface_ parameter.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="448df-144">另请参阅</span><span class="sxs-lookup"><span data-stu-id="448df-144">See also</span></span>



[<span data-ttu-id="448df-145">IMAPIProp::OpenProperty</span><span class="sxs-lookup"><span data-stu-id="448df-145">IMAPIProp::OpenProperty</span></span>](imapiprop-openproperty.md)
  
[<span data-ttu-id="448df-146">IMAPISupport : IUnknown</span><span class="sxs-lookup"><span data-stu-id="448df-146">IMAPISupport : IUnknown</span></span>](imapisupportiunknown.md)

