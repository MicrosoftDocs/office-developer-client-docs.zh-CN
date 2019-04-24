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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32325667"
---
# <a name="wrapstoreentryid"></a><span data-ttu-id="6b9a7-103">WrapStoreEntryID</span><span class="sxs-lookup"><span data-stu-id="6b9a7-103">WrapStoreEntryID</span></span>

  
  
<span data-ttu-id="6b9a7-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="6b9a7-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="6b9a7-105">将邮件存储区的内部条目标识符转换为邮件系统更易于使用的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="6b9a7-105">Converts a message store's internal entry identifier to an entry identifier more usable by the messaging system.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="6b9a7-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="6b9a7-106">Header file:</span></span>  <br/> |<span data-ttu-id="6b9a7-107">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="6b9a7-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="6b9a7-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="6b9a7-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="6b9a7-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="6b9a7-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="6b9a7-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="6b9a7-110">Called by:</span></span>  <br/> |<span data-ttu-id="6b9a7-111">客户端应用程序和服务提供程序</span><span class="sxs-lookup"><span data-stu-id="6b9a7-111">Client applications and service providers</span></span>  <br/> |
   
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

## <a name="parameters"></a><span data-ttu-id="6b9a7-112">参数</span><span class="sxs-lookup"><span data-stu-id="6b9a7-112">Parameters</span></span>

 <span data-ttu-id="6b9a7-113">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="6b9a7-113">_ulFlags_</span></span>
  
> <span data-ttu-id="6b9a7-114">实时标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="6b9a7-114">[in] Bitmask of flags.</span></span> <span data-ttu-id="6b9a7-115">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="6b9a7-115">The following flag can be set:</span></span>
    
<span data-ttu-id="6b9a7-116">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="6b9a7-116">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="6b9a7-117">字符串采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="6b9a7-117">The strings are in Unicode format.</span></span> <span data-ttu-id="6b9a7-118">如果未设置 MAPI_UNICODE 标志, 则字符串将采用 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="6b9a7-118">If the MAPI_UNICODE flag is not set, the strings are in ANSI format.</span></span> 
    
 <span data-ttu-id="6b9a7-119">_szDLLName_</span><span class="sxs-lookup"><span data-stu-id="6b9a7-119">_szDLLName_</span></span>
  
> <span data-ttu-id="6b9a7-120">实时邮件存储提供程序 DLL 的名称。</span><span class="sxs-lookup"><span data-stu-id="6b9a7-120">[in] The name of the message store provider DLL.</span></span> 
    
 <span data-ttu-id="6b9a7-121">_cbOrigEntry_</span><span class="sxs-lookup"><span data-stu-id="6b9a7-121">_cbOrigEntry_</span></span>
  
> <span data-ttu-id="6b9a7-122">实时邮件存储的原始条目标识符的大小 (以字节为单位)。</span><span class="sxs-lookup"><span data-stu-id="6b9a7-122">[in] Size, in bytes, of the original entry identifier for the message store.</span></span> 
    
 <span data-ttu-id="6b9a7-123">_lpOrigEntry_</span><span class="sxs-lookup"><span data-stu-id="6b9a7-123">_lpOrigEntry_</span></span>
  
> <span data-ttu-id="6b9a7-124">实时指向包含原始条目标识符的[ENTRYID](entryid.md)结构的指针。</span><span class="sxs-lookup"><span data-stu-id="6b9a7-124">[in] Pointer to an [ENTRYID](entryid.md) structure that contains the original entry identifier.</span></span> 
    
 <span data-ttu-id="6b9a7-125">_lpcbWrappedEntry_</span><span class="sxs-lookup"><span data-stu-id="6b9a7-125">_lpcbWrappedEntry_</span></span>
  
> <span data-ttu-id="6b9a7-126">排除指向新条目标识符的大小 (以字节为单位) 的指针。</span><span class="sxs-lookup"><span data-stu-id="6b9a7-126">[out] Pointer to the size, in bytes, of the new entry identifier.</span></span> 
    
 <span data-ttu-id="6b9a7-127">_lppWrappedEntry_</span><span class="sxs-lookup"><span data-stu-id="6b9a7-127">_lppWrappedEntry_</span></span>
  
> <span data-ttu-id="6b9a7-128">排除指向包含新条目标识符的**ENTRYID**结构的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="6b9a7-128">[out] Pointer to a pointer to an **ENTRYID** structure that contains the new entry identifier.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="6b9a7-129">返回值</span><span class="sxs-lookup"><span data-stu-id="6b9a7-129">Return value</span></span>

<span data-ttu-id="6b9a7-130">无。</span><span class="sxs-lookup"><span data-stu-id="6b9a7-130">None.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="6b9a7-131">注解</span><span class="sxs-lookup"><span data-stu-id="6b9a7-131">Remarks</span></span>

<span data-ttu-id="6b9a7-132">邮件存储对象保留内部条目标识符, 该标识符仅对与该邮件存储 coresident 的服务提供程序有意义。</span><span class="sxs-lookup"><span data-stu-id="6b9a7-132">A message store object retains an internal entry identifier which is meaningful only to service providers coresident with that message store.</span></span> <span data-ttu-id="6b9a7-133">对于其他邮件组件, MAPI 提供了内部条目标识符的包装版本, 使其无法识别为邮件存储区。</span><span class="sxs-lookup"><span data-stu-id="6b9a7-133">For other messaging components, MAPI supplies a wrapped version of the internal entry identifier that makes it recognizable as that belong to the message store.</span></span> <span data-ttu-id="6b9a7-134">应始终为 Coresident 服务提供程序提供原始的已解开邮件存储项标识符;应始终为客户端应用程序提供包装版本, 然后在邮件域和其他域中的任何位置使用该版本。</span><span class="sxs-lookup"><span data-stu-id="6b9a7-134">Coresident service providers should always be given the original unwrapped message store entry identifier; client applications should always be given the wrapped version, which is then usable anywhere in the messaging domain and in other domains.</span></span> 
  
<span data-ttu-id="6b9a7-135">服务提供程序可以使用**WrapStoreEntryID**函数或[IMAPISupport:: WrapStoreEntryID](imapisupport-wrapstoreentryid.md)方法包装邮件存储区条目标识符, 后者调用**WrapStoreEntryID**函数。</span><span class="sxs-lookup"><span data-stu-id="6b9a7-135">A service provider can wrap a message store entry identifier using either the **WrapStoreEntryID** function or the [IMAPISupport::WrapStoreEntryID](imapisupport-wrapstoreentryid.md) method, which calls the **WrapStoreEntryID** function.</span></span> <span data-ttu-id="6b9a7-136">提供程序必须在公开邮件存储的**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 属性或将其写入配置文件部分时包装条目标识符, 并在公开**PR_STORE_ENTRYID**时 ([PidTagStoreEntryId](pidtagstoreentryid-canonical-property.md))财产.</span><span class="sxs-lookup"><span data-stu-id="6b9a7-136">The provider must wrap the entry identifier when exposing the message store's **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) property or writing it into a profile section, and when exposing the **PR_STORE_ENTRYID** ([PidTagStoreEntryId](pidtagstoreentryid-canonical-property.md)) property.</span></span> <span data-ttu-id="6b9a7-137">MAPI 对[IMAPISession:: OpenMsgStore](imapisession-openmsgstore.md)调用进行响应时, 会对邮件存储条目标识符进行包装。</span><span class="sxs-lookup"><span data-stu-id="6b9a7-137">MAPI wraps a message store entry identifier when responding to an [IMAPISession::OpenMsgStore](imapisession-openmsgstore.md) call.</span></span> 
  
<span data-ttu-id="6b9a7-138">当客户端应用程序将包装的邮件存储项标识符传递给 MAPI (例如在[IMAPISession:: OpenEntry](imapisession-openentry.md)调用中) 时, MAPI 将在使用它来调用提供程序方法 (如[IMSProvider:: Logon](imsprovider-logon.md) or [) 之前, 对条目标识符进行解包。IMSProvider:: CompareStoreIDs](imsprovider-comparestoreids.md)。</span><span class="sxs-lookup"><span data-stu-id="6b9a7-138">When a client application passes a wrapped message store entry identifier to MAPI, for example in an [IMAPISession::OpenEntry](imapisession-openentry.md) call, MAPI unwraps the entry identifier before using it to call a provider method such as [IMSProvider::Logon](imsprovider-logon.md) or [IMSProvider::CompareStoreIDs](imsprovider-comparestoreids.md).</span></span> 
  

