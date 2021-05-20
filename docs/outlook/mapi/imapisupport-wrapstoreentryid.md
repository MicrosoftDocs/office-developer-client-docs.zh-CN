---
title: IMAPISupportWrapStoreEntryID
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISupport.WrapStoreEntryID
api_type:
- COM
ms.assetid: 923fb879-5f32-4fe2-8920-2ec17002256c
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: a623ef24f76dae93bfc13e6613e885a120f3278e
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33430446"
---
# <a name="imapisupportwrapstoreentryid"></a><span data-ttu-id="20d4b-103">IMAPISupport::WrapStoreEntryID</span><span class="sxs-lookup"><span data-stu-id="20d4b-103">IMAPISupport::WrapStoreEntryID</span></span>

  
  
<span data-ttu-id="20d4b-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="20d4b-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="20d4b-105">将邮件存储的内部条目标识符转换为 MAPI 标准格式的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="20d4b-105">Converts a message store's internal entry identifier to an entry identifier in the MAPI standard format.</span></span>
  
```cpp
HRESULT WrapStoreEntryID(
ULONG cbOrigEntry,
LPENTRYID lpOrigEntry,
ULONG FAR * lpcbWrappedEntry,
LPENTRYID FAR * lppWrappedEntry
);
```

## <a name="parameters"></a><span data-ttu-id="20d4b-106">参数</span><span class="sxs-lookup"><span data-stu-id="20d4b-106">Parameters</span></span>

 <span data-ttu-id="20d4b-107">_cbOrigEntry_</span><span class="sxs-lookup"><span data-stu-id="20d4b-107">_cbOrigEntry_</span></span>
  
> <span data-ttu-id="20d4b-108">[in]  _lpOrigEntry_ 参数指向的条目标识符中的字节计数。</span><span class="sxs-lookup"><span data-stu-id="20d4b-108">[in] The byte count in the entry identifier pointed to by the  _lpOrigEntry_ parameter.</span></span> 
    
 <span data-ttu-id="20d4b-109">_lpOrigEntry_</span><span class="sxs-lookup"><span data-stu-id="20d4b-109">_lpOrigEntry_</span></span>
  
> <span data-ttu-id="20d4b-110">[in]指向邮件存储的专用条目标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="20d4b-110">[in] A pointer to the private entry identifier for the message store.</span></span>
    
 <span data-ttu-id="20d4b-111">_lpcbWrappedEntry_</span><span class="sxs-lookup"><span data-stu-id="20d4b-111">_lpcbWrappedEntry_</span></span>
  
> <span data-ttu-id="20d4b-112">[out]指向  _lppWrappedEntry_ 参数指向的条目标识符中的字节计数的指针。</span><span class="sxs-lookup"><span data-stu-id="20d4b-112">[out] A pointer to the byte count in the entry identifier pointed to by the  _lppWrappedEntry_ parameter.</span></span> 
    
 <span data-ttu-id="20d4b-113">_lppWrappedEntry_</span><span class="sxs-lookup"><span data-stu-id="20d4b-113">_lppWrappedEntry_</span></span>
  
> <span data-ttu-id="20d4b-114">[out]指向指向封装条目标识符的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="20d4b-114">[out] A pointer to a pointer to the wrapped entry identifier.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="20d4b-115">返回值</span><span class="sxs-lookup"><span data-stu-id="20d4b-115">Return value</span></span>

<span data-ttu-id="20d4b-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="20d4b-116">S_OK</span></span> 
  
> <span data-ttu-id="20d4b-117">条目标识符已成功包装。</span><span class="sxs-lookup"><span data-stu-id="20d4b-117">The entry identifier was successfully wrapped.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="20d4b-118">备注</span><span class="sxs-lookup"><span data-stu-id="20d4b-118">Remarks</span></span>

<span data-ttu-id="20d4b-119">**IMAPISupport：：WrapStoreEntryID** 方法针对所有服务提供程序支持对象实现。</span><span class="sxs-lookup"><span data-stu-id="20d4b-119">The **IMAPISupport::WrapStoreEntryID** method is implemented for all service provider support objects.</span></span> <span data-ttu-id="20d4b-120">服务提供商使用 **WrapStoreEntryID** 让 MAPI 为包装存储的内部条目标识符的邮件存储生成条目标识符。</span><span class="sxs-lookup"><span data-stu-id="20d4b-120">Service providers use **WrapStoreEntryID** to have MAPI generate an entry identifier for a message store that wraps the store's internal entry identifier.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="20d4b-121">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="20d4b-121">Notes to callers</span></span>

<span data-ttu-id="20d4b-122">当客户端调用邮件存储 [的 IMAPIProp：：GetProps](imapiprop-getprops.md) 方法检索其 **PR_STORE_ENTRYID** ([PidTagStoreEntryId](pidtagstoreentryid-canonical-property.md)) 属性时，如果邮件存储使用私有格式的条目标识符，请调用 **WrapStoreEntryID** 并返回  _lppWrappedEntry_ 参数指向的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="20d4b-122">When a client calls your message store's [IMAPIProp::GetProps](imapiprop-getprops.md) method to retrieve its **PR_STORE_ENTRYID** ([PidTagStoreEntryId](pidtagstoreentryid-canonical-property.md)) property, and your message store uses an entry identifier in a private format, call **WrapStoreEntryID** and return the entry identifier pointed to by the  _lppWrappedEntry_ parameter.</span></span> 
  
<span data-ttu-id="20d4b-123">对 [IMSProvider：：Logon](imsprovider-logon.md) 和 [IMSLogon：：CompareEntryIDs](imslogon-compareentryids.md) 方法的调用始终获取存储的私有条目标识符;包装的版本仅在客户端应用程序和 MAPI 之间使用。</span><span class="sxs-lookup"><span data-stu-id="20d4b-123">Calls to the [IMSProvider::Logon](imsprovider-logon.md) and [IMSLogon::CompareEntryIDs](imslogon-compareentryids.md) methods always obtain the store's private entry identifier; the wrapped version is used only between client applications and MAPI.</span></span> 
  
<span data-ttu-id="20d4b-124">使用完条目标识符后，使用 [MAPIFreeBuffer](mapifreebuffer.md)函数释放 _lppWrappedEntry_ 参数指向的条目标识符的内存。</span><span class="sxs-lookup"><span data-stu-id="20d4b-124">Free the memory for the entry identifier pointed to by the  _lppWrappedEntry_ parameter by using the [MAPIFreeBuffer](mapifreebuffer.md) function when you are finished using the entry identifier.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="20d4b-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="20d4b-125">See also</span></span>



[<span data-ttu-id="20d4b-126">IMAPIProp::GetProps</span><span class="sxs-lookup"><span data-stu-id="20d4b-126">IMAPIProp::GetProps</span></span>](imapiprop-getprops.md)
  
[<span data-ttu-id="20d4b-127">IMAPISupport::CompareEntryIDs</span><span class="sxs-lookup"><span data-stu-id="20d4b-127">IMAPISupport::CompareEntryIDs</span></span>](imapisupport-compareentryids.md)
  
[<span data-ttu-id="20d4b-128">IMSLogon::CompareEntryIDs</span><span class="sxs-lookup"><span data-stu-id="20d4b-128">IMSLogon::CompareEntryIDs</span></span>](imslogon-compareentryids.md)
  
[<span data-ttu-id="20d4b-129">IMSProvider::Logon</span><span class="sxs-lookup"><span data-stu-id="20d4b-129">IMSProvider::Logon</span></span>](imsprovider-logon.md)
  
[<span data-ttu-id="20d4b-130">MAPIFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="20d4b-130">MAPIFreeBuffer</span></span>](mapifreebuffer.md)
  
[<span data-ttu-id="20d4b-131">IMAPISupport : IUnknown</span><span class="sxs-lookup"><span data-stu-id="20d4b-131">IMAPISupport : IUnknown</span></span>](imapisupportiunknown.md)

