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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: b3850da2917dbf463590643b9e7ba8420f4ea219
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22576055"
---
# <a name="imapisupportwrapstoreentryid"></a><span data-ttu-id="9b165-103">IMAPISupport::WrapStoreEntryID</span><span class="sxs-lookup"><span data-stu-id="9b165-103">IMAPISupport::WrapStoreEntryID</span></span>

  
  
<span data-ttu-id="9b165-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="9b165-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="9b165-105">转换 MAPI 标准格式中的项标识符的消息存储内部的项标识符。</span><span class="sxs-lookup"><span data-stu-id="9b165-105">Converts a message store's internal entry identifier to an entry identifier in the MAPI standard format.</span></span>
  
```cpp
HRESULT WrapStoreEntryID(
ULONG cbOrigEntry,
LPENTRYID lpOrigEntry,
ULONG FAR * lpcbWrappedEntry,
LPENTRYID FAR * lppWrappedEntry
);
```

## <a name="parameters"></a><span data-ttu-id="9b165-106">参数</span><span class="sxs-lookup"><span data-stu-id="9b165-106">Parameters</span></span>

 <span data-ttu-id="9b165-107">_cbOrigEntry_</span><span class="sxs-lookup"><span data-stu-id="9b165-107">_cbOrigEntry_</span></span>
  
> <span data-ttu-id="9b165-108">[in]在_lpOrigEntry_参数指向的项标识符的字节数。</span><span class="sxs-lookup"><span data-stu-id="9b165-108">[in] The byte count in the entry identifier pointed to by the  _lpOrigEntry_ parameter.</span></span> 
    
 <span data-ttu-id="9b165-109">_lpOrigEntry_</span><span class="sxs-lookup"><span data-stu-id="9b165-109">_lpOrigEntry_</span></span>
  
> <span data-ttu-id="9b165-110">[in]指向消息存储库的专用的项标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="9b165-110">[in] A pointer to the private entry identifier for the message store.</span></span>
    
 <span data-ttu-id="9b165-111">_lpcbWrappedEntry_</span><span class="sxs-lookup"><span data-stu-id="9b165-111">_lpcbWrappedEntry_</span></span>
  
> <span data-ttu-id="9b165-112">[输出]一个指向_lppWrappedEntry_参数指向该条目标识符中的字节数。</span><span class="sxs-lookup"><span data-stu-id="9b165-112">[out] A pointer to the byte count in the entry identifier pointed to by the  _lppWrappedEntry_ parameter.</span></span> 
    
 <span data-ttu-id="9b165-113">_lppWrappedEntry_</span><span class="sxs-lookup"><span data-stu-id="9b165-113">_lppWrappedEntry_</span></span>
  
> <span data-ttu-id="9b165-114">[输出]指向与换行的项标识符的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="9b165-114">[out] A pointer to a pointer to the wrapped entry identifier.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="9b165-115">返回值</span><span class="sxs-lookup"><span data-stu-id="9b165-115">Return value</span></span>

<span data-ttu-id="9b165-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="9b165-116">S_OK</span></span> 
  
> <span data-ttu-id="9b165-117">成功自动换行的项标识符。</span><span class="sxs-lookup"><span data-stu-id="9b165-117">The entry identifier was successfully wrapped.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="9b165-118">注解</span><span class="sxs-lookup"><span data-stu-id="9b165-118">Remarks</span></span>

<span data-ttu-id="9b165-119">**IMAPISupport::WrapStoreEntryID**方法将执行所有服务提供商支持对象。</span><span class="sxs-lookup"><span data-stu-id="9b165-119">The **IMAPISupport::WrapStoreEntryID** method is implemented for all service provider support objects.</span></span> <span data-ttu-id="9b165-120">服务提供商使用**WrapStoreEntryID**已生成的存储内部的项标识符的换行的消息存储的项标识符的 MAPI。</span><span class="sxs-lookup"><span data-stu-id="9b165-120">Service providers use **WrapStoreEntryID** to have MAPI generate an entry identifier for a message store that wraps the store's internal entry identifier.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="9b165-121">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="9b165-121">Notes to callers</span></span>

<span data-ttu-id="9b165-122">当客户端调用消息存储库[IMAPIProp::GetProps](imapiprop-getprops.md)方法来检索其**PR_STORE_ENTRYID** ([PidTagStoreEntryId](pidtagstoreentryid-canonical-property.md)) 属性，您和您的消息存储区专用格式中使用的项标识符，调用**WrapStoreEntryID**并返回_lppWrappedEntry_参数指向的项标识符。</span><span class="sxs-lookup"><span data-stu-id="9b165-122">When a client calls your message store's [IMAPIProp::GetProps](imapiprop-getprops.md) method to retrieve its **PR_STORE_ENTRYID** ([PidTagStoreEntryId](pidtagstoreentryid-canonical-property.md)) property, and your message store uses an entry identifier in a private format, call **WrapStoreEntryID** and return the entry identifier pointed to by the  _lppWrappedEntry_ parameter.</span></span> 
  
<span data-ttu-id="9b165-123">对[IMSProvider::Logon](imsprovider-logon.md)和[IMSLogon::CompareEntryIDs](imslogon-compareentryids.md)方法的调用始终获取存储区的专用条目标识符;客户端应用程序和 MAPI 之间只使用换行的版本。</span><span class="sxs-lookup"><span data-stu-id="9b165-123">Calls to the [IMSProvider::Logon](imsprovider-logon.md) and [IMSLogon::CompareEntryIDs](imslogon-compareentryids.md) methods always obtain the store's private entry identifier; the wrapped version is used only between client applications and MAPI.</span></span> 
  
<span data-ttu-id="9b165-124">忙时使用的项标识符完使用[MAPIFreeBuffer](mapifreebuffer.md)函数_lppWrappedEntry_参数指向的项标识符的内存。</span><span class="sxs-lookup"><span data-stu-id="9b165-124">Free the memory for the entry identifier pointed to by the  _lppWrappedEntry_ parameter by using the [MAPIFreeBuffer](mapifreebuffer.md) function when you are finished using the entry identifier.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="9b165-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9b165-125">See also</span></span>



[<span data-ttu-id="9b165-126">IMAPIProp::GetProps</span><span class="sxs-lookup"><span data-stu-id="9b165-126">IMAPIProp::GetProps</span></span>](imapiprop-getprops.md)
  
[<span data-ttu-id="9b165-127">IMAPISupport::CompareEntryIDs</span><span class="sxs-lookup"><span data-stu-id="9b165-127">IMAPISupport::CompareEntryIDs</span></span>](imapisupport-compareentryids.md)
  
[<span data-ttu-id="9b165-128">IMSLogon::CompareEntryIDs</span><span class="sxs-lookup"><span data-stu-id="9b165-128">IMSLogon::CompareEntryIDs</span></span>](imslogon-compareentryids.md)
  
[<span data-ttu-id="9b165-129">IMSProvider::Logon</span><span class="sxs-lookup"><span data-stu-id="9b165-129">IMSProvider::Logon</span></span>](imsprovider-logon.md)
  
[<span data-ttu-id="9b165-130">MAPIFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="9b165-130">MAPIFreeBuffer</span></span>](mapifreebuffer.md)
  
[<span data-ttu-id="9b165-131">IMAPISupport : IUnknown</span><span class="sxs-lookup"><span data-stu-id="9b165-131">IMAPISupport : IUnknown</span></span>](imapisupportiunknown.md)

