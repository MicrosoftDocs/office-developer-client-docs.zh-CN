---
title: WrapStoreEntryID
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- WrapStoreEntryID
api_type:
- HeaderDef
ms.assetid: b20107e3-5e23-4cde-9cd6-670c914ea70a
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: e797a80cf8659baa7ca935f94b3ab65c200530a3
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33409207"
---
# <a name="wrapstoreentryid"></a><span data-ttu-id="fa9a1-103">WrapStoreEntryID</span><span class="sxs-lookup"><span data-stu-id="fa9a1-103">WrapStoreEntryID</span></span>

  
  
<span data-ttu-id="fa9a1-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="fa9a1-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="fa9a1-105">将邮件存储的内部条目标识符转换为邮件系统更可用条目标识符。</span><span class="sxs-lookup"><span data-stu-id="fa9a1-105">Converts a message store's internal entry identifier to an entry identifier more usable by the messaging system.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="fa9a1-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="fa9a1-106">Header file:</span></span>  <br/> |<span data-ttu-id="fa9a1-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="fa9a1-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="fa9a1-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="fa9a1-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="fa9a1-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="fa9a1-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="fa9a1-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="fa9a1-110">Called by:</span></span>  <br/> |<span data-ttu-id="fa9a1-111">客户端应用程序和服务提供商</span><span class="sxs-lookup"><span data-stu-id="fa9a1-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
WrapStoreEntryID(
  ULONG ulFlags,
  LPSTR szDLLName,
  ULONG cbOrigEntry,
  LPENTRYID lpOrigEntry,
  ULONG * lpcbWrappedEntry,
  LPENTRYID * lppWrappedEntry
);
```

## <a name="parameters"></a><span data-ttu-id="fa9a1-112">参数</span><span class="sxs-lookup"><span data-stu-id="fa9a1-112">Parameters</span></span>

 <span data-ttu-id="fa9a1-113">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="fa9a1-113">_ulFlags_</span></span>
  
> <span data-ttu-id="fa9a1-114">[in]标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="fa9a1-114">[in] Bitmask of flags.</span></span> <span data-ttu-id="fa9a1-115">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="fa9a1-115">The following flag can be set:</span></span>
    
<span data-ttu-id="fa9a1-116">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="fa9a1-116">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="fa9a1-117">字符串采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="fa9a1-117">The strings are in Unicode format.</span></span> <span data-ttu-id="fa9a1-118">如果未MAPI_UNICODE，则字符串采用 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="fa9a1-118">If the MAPI_UNICODE flag is not set, the strings are in ANSI format.</span></span> 
    
 <span data-ttu-id="fa9a1-119">_szDLLName_</span><span class="sxs-lookup"><span data-stu-id="fa9a1-119">_szDLLName_</span></span>
  
> <span data-ttu-id="fa9a1-120">[in]邮件存储提供程序 DLL 的名称。</span><span class="sxs-lookup"><span data-stu-id="fa9a1-120">[in] The name of the message store provider DLL.</span></span> 
    
 <span data-ttu-id="fa9a1-121">_cbOrigEntry_</span><span class="sxs-lookup"><span data-stu-id="fa9a1-121">_cbOrigEntry_</span></span>
  
> <span data-ttu-id="fa9a1-122">[in]邮件存储的原始条目标识符的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="fa9a1-122">[in] Size, in bytes, of the original entry identifier for the message store.</span></span> 
    
 <span data-ttu-id="fa9a1-123">_lpOrigEntry_</span><span class="sxs-lookup"><span data-stu-id="fa9a1-123">_lpOrigEntry_</span></span>
  
> <span data-ttu-id="fa9a1-124">[in]指向包含原始条目标识符的 [ENTRYID](entryid.md) 结构的指针。</span><span class="sxs-lookup"><span data-stu-id="fa9a1-124">[in] Pointer to an [ENTRYID](entryid.md) structure that contains the original entry identifier.</span></span> 
    
 <span data-ttu-id="fa9a1-125">_lpcbWrappedEntry_</span><span class="sxs-lookup"><span data-stu-id="fa9a1-125">_lpcbWrappedEntry_</span></span>
  
> <span data-ttu-id="fa9a1-126">[out]指向新条目标识符的大小（以字节为单位）的指针。</span><span class="sxs-lookup"><span data-stu-id="fa9a1-126">[out] Pointer to the size, in bytes, of the new entry identifier.</span></span> 
    
 <span data-ttu-id="fa9a1-127">_lppWrappedEntry_</span><span class="sxs-lookup"><span data-stu-id="fa9a1-127">_lppWrappedEntry_</span></span>
  
> <span data-ttu-id="fa9a1-128">[out]指向包含新条目标识符 **的 ENTRYID** 结构的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="fa9a1-128">[out] Pointer to a pointer to an **ENTRYID** structure that contains the new entry identifier.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="fa9a1-129">返回值</span><span class="sxs-lookup"><span data-stu-id="fa9a1-129">Return value</span></span>

<span data-ttu-id="fa9a1-130">无。</span><span class="sxs-lookup"><span data-stu-id="fa9a1-130">None.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="fa9a1-131">说明</span><span class="sxs-lookup"><span data-stu-id="fa9a1-131">Remarks</span></span>

<span data-ttu-id="fa9a1-132">邮件存储对象保留一个内部条目标识符，该标识符仅对具有该邮件存储的服务提供商核心标识有意义。</span><span class="sxs-lookup"><span data-stu-id="fa9a1-132">A message store object retains an internal entry identifier which is meaningful only to service providers coresident with that message store.</span></span> <span data-ttu-id="fa9a1-133">对于其他邮件组件，MAPI 提供内部条目标识符的包装版本，使其可识别为属于邮件存储的版本。</span><span class="sxs-lookup"><span data-stu-id="fa9a1-133">For other messaging components, MAPI supplies a wrapped version of the internal entry identifier that makes it recognizable as that belong to the message store.</span></span> <span data-ttu-id="fa9a1-134">应始终为 Coresident 服务提供商提供原始未包的邮件存储条目标识符;应始终为客户端应用程序提供包装版本，该版本随后将在邮件域和其他域中的任何位置使用。</span><span class="sxs-lookup"><span data-stu-id="fa9a1-134">Coresident service providers should always be given the original unwrapped message store entry identifier; client applications should always be given the wrapped version, which is then usable anywhere in the messaging domain and in other domains.</span></span> 
  
<span data-ttu-id="fa9a1-135">服务提供商可以使用 **WrapStoreEntryID** 函数或调用 **WrapStoreEntryID** 函数的 [IMAPISupport：：WrapStoreEntryID](imapisupport-wrapstoreentryid.md)方法包装邮件存储条目标识符。</span><span class="sxs-lookup"><span data-stu-id="fa9a1-135">A service provider can wrap a message store entry identifier using either the **WrapStoreEntryID** function or the [IMAPISupport::WrapStoreEntryID](imapisupport-wrapstoreentryid.md) method, which calls the **WrapStoreEntryID** function.</span></span> <span data-ttu-id="fa9a1-136">当公开邮件存储的 **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 属性或将其写入配置文件部分，以及公开 **PR_STORE_ENTRYID** ([PidTagStoreEntryId](pidtagstoreentryid-canonical-property.md)) 属性时，提供程序必须包装条目标识符。</span><span class="sxs-lookup"><span data-stu-id="fa9a1-136">The provider must wrap the entry identifier when exposing the message store's **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) property or writing it into a profile section, and when exposing the **PR_STORE_ENTRYID** ([PidTagStoreEntryId](pidtagstoreentryid-canonical-property.md)) property.</span></span> <span data-ttu-id="fa9a1-137">MAPI 在响应 [IMAPISession：：OpenMsgStore](imapisession-openmsgstore.md) 调用时封装邮件存储条目标识符。</span><span class="sxs-lookup"><span data-stu-id="fa9a1-137">MAPI wraps a message store entry identifier when responding to an [IMAPISession::OpenMsgStore](imapisession-openmsgstore.md) call.</span></span> 
  
<span data-ttu-id="fa9a1-138">当客户端应用程序将包装的邮件存储条目标识符传递给 MAPI（例如 [，在 IMAPISession：：OpenEntry](imapisession-openentry.md) 调用中）时，MAPI 在使用它调用提供程序方法（如 [IMSProvider：：Logon](imsprovider-logon.md) 或 [IMSProvider：：CompareStoreIDs）之前将](imsprovider-comparestoreids.md)取消封装条目标识符。</span><span class="sxs-lookup"><span data-stu-id="fa9a1-138">When a client application passes a wrapped message store entry identifier to MAPI, for example in an [IMAPISession::OpenEntry](imapisession-openentry.md) call, MAPI unwraps the entry identifier before using it to call a provider method such as [IMSProvider::Logon](imsprovider-logon.md) or [IMSProvider::CompareStoreIDs](imsprovider-comparestoreids.md).</span></span> 
  

