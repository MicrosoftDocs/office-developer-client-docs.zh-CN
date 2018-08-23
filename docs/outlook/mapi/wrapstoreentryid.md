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
ms.openlocfilehash: 45263396e69852a9ae17ff6fce284663bdf2fb07
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22585134"
---
# <a name="wrapstoreentryid"></a><span data-ttu-id="57bd3-103">WrapStoreEntryID</span><span class="sxs-lookup"><span data-stu-id="57bd3-103">WrapStoreEntryID</span></span>

  
  
<span data-ttu-id="57bd3-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="57bd3-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="57bd3-105">通过在邮件系统转换更易于使用的项标识符的消息存储内部的项标识符。</span><span class="sxs-lookup"><span data-stu-id="57bd3-105">Converts a message store's internal entry identifier to an entry identifier more usable by the messaging system.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="57bd3-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="57bd3-106">Header file:</span></span>  <br/> |<span data-ttu-id="57bd3-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="57bd3-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="57bd3-108">通过实现：</span><span class="sxs-lookup"><span data-stu-id="57bd3-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="57bd3-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="57bd3-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="57bd3-110">调用：</span><span class="sxs-lookup"><span data-stu-id="57bd3-110">Called by:</span></span>  <br/> |<span data-ttu-id="57bd3-111">客户端应用程序和服务提供商</span><span class="sxs-lookup"><span data-stu-id="57bd3-111">Client applications and service providers</span></span>  <br/> |
   
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

## <a name="parameters"></a><span data-ttu-id="57bd3-112">参数</span><span class="sxs-lookup"><span data-stu-id="57bd3-112">Parameters</span></span>

 <span data-ttu-id="57bd3-113">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="57bd3-113">_ulFlags_</span></span>
  
> <span data-ttu-id="57bd3-114">[in]Flags 的位掩码。</span><span class="sxs-lookup"><span data-stu-id="57bd3-114">[in] Bitmask of flags.</span></span> <span data-ttu-id="57bd3-115">可以设置以下标记：</span><span class="sxs-lookup"><span data-stu-id="57bd3-115">The following flag can be set:</span></span>
    
<span data-ttu-id="57bd3-116">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="57bd3-116">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="57bd3-117">字符串是 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="57bd3-117">The strings are in Unicode format.</span></span> <span data-ttu-id="57bd3-118">如果未设置 MAPI_UNICODE 标志的字符串是以 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="57bd3-118">If the MAPI_UNICODE flag is not set, the strings are in ANSI format.</span></span> 
    
 <span data-ttu-id="57bd3-119">_szDLLName_</span><span class="sxs-lookup"><span data-stu-id="57bd3-119">_szDLLName_</span></span>
  
> <span data-ttu-id="57bd3-120">[in]消息存储提供程序 DLL 名称。</span><span class="sxs-lookup"><span data-stu-id="57bd3-120">[in] The name of the message store provider DLL.</span></span> 
    
 <span data-ttu-id="57bd3-121">_cbOrigEntry_</span><span class="sxs-lookup"><span data-stu-id="57bd3-121">_cbOrigEntry_</span></span>
  
> <span data-ttu-id="57bd3-122">[in]大小，以字节为单位的消息存储的原始项标识符。</span><span class="sxs-lookup"><span data-stu-id="57bd3-122">[in] Size, in bytes, of the original entry identifier for the message store.</span></span> 
    
 <span data-ttu-id="57bd3-123">_lpOrigEntry_</span><span class="sxs-lookup"><span data-stu-id="57bd3-123">_lpOrigEntry_</span></span>
  
> <span data-ttu-id="57bd3-124">[in]指针指向包含原始的项标识符的[ENTRYID](entryid.md)结构。</span><span class="sxs-lookup"><span data-stu-id="57bd3-124">[in] Pointer to an [ENTRYID](entryid.md) structure that contains the original entry identifier.</span></span> 
    
 <span data-ttu-id="57bd3-125">_lpcbWrappedEntry_</span><span class="sxs-lookup"><span data-stu-id="57bd3-125">_lpcbWrappedEntry_</span></span>
  
> <span data-ttu-id="57bd3-126">[输出]指向的大小，以字节为单位，新条目标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="57bd3-126">[out] Pointer to the size, in bytes, of the new entry identifier.</span></span> 
    
 <span data-ttu-id="57bd3-127">_lppWrappedEntry_</span><span class="sxs-lookup"><span data-stu-id="57bd3-127">_lppWrappedEntry_</span></span>
  
> <span data-ttu-id="57bd3-128">[输出]为包含新的项标识符的**ENTRYID**结构指针的指针。</span><span class="sxs-lookup"><span data-stu-id="57bd3-128">[out] Pointer to a pointer to an **ENTRYID** structure that contains the new entry identifier.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="57bd3-129">返回值</span><span class="sxs-lookup"><span data-stu-id="57bd3-129">Return value</span></span>

<span data-ttu-id="57bd3-130">无。</span><span class="sxs-lookup"><span data-stu-id="57bd3-130">None.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="57bd3-131">注解</span><span class="sxs-lookup"><span data-stu-id="57bd3-131">Remarks</span></span>

<span data-ttu-id="57bd3-132">消息存储对象保留其只对与该消息存储的服务提供程序 coresident 有意义的内部条目标识符。</span><span class="sxs-lookup"><span data-stu-id="57bd3-132">A message store object retains an internal entry identifier which is meaningful only to service providers coresident with that message store.</span></span> <span data-ttu-id="57bd3-133">对于其他消息组件，MAPI 提供内部条目标识符，如属于消息存储使可识别的换行的版本。</span><span class="sxs-lookup"><span data-stu-id="57bd3-133">For other messaging components, MAPI supplies a wrapped version of the internal entry identifier that makes it recognizable as that belong to the message store.</span></span> <span data-ttu-id="57bd3-134">Coresident 服务提供商应始终提供的原始解包的消息存储条目标识符;客户端应用程序应始终提供的换行的版本，然后可用任意位置和其他域中的消息的域。</span><span class="sxs-lookup"><span data-stu-id="57bd3-134">Coresident service providers should always be given the original unwrapped message store entry identifier; client applications should always be given the wrapped version, which is then usable anywhere in the messaging domain and in other domains.</span></span> 
  
<span data-ttu-id="57bd3-135">服务提供商可以换行使用**WrapStoreEntryID**函数或[IMAPISupport::WrapStoreEntryID](imapisupport-wrapstoreentryid.md)方法，该调用**WrapStoreEntryID**函数方法的消息存储项标识符。</span><span class="sxs-lookup"><span data-stu-id="57bd3-135">A service provider can wrap a message store entry identifier using either the **WrapStoreEntryID** function or the [IMAPISupport::WrapStoreEntryID](imapisupport-wrapstoreentryid.md) method, which calls the **WrapStoreEntryID** function.</span></span> <span data-ttu-id="57bd3-136">提供程序必须打包的项标识符时公开的消息存储**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 属性或编写它到配置文件部分中，并公开**PR_STORE_ENTRYID** ([PidTagStoreEntryId](pidtagstoreentryid-canonical-property.md)) 时属性。</span><span class="sxs-lookup"><span data-stu-id="57bd3-136">The provider must wrap the entry identifier when exposing the message store's **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) property or writing it into a profile section, and when exposing the **PR_STORE_ENTRYID** ([PidTagStoreEntryId](pidtagstoreentryid-canonical-property.md)) property.</span></span> <span data-ttu-id="57bd3-137">MAPI 响应[IMAPISession::OpenMsgStore](imapisession-openmsgstore.md)呼叫时的换行消息存储项标识符。</span><span class="sxs-lookup"><span data-stu-id="57bd3-137">MAPI wraps a message store entry identifier when responding to an [IMAPISession::OpenMsgStore](imapisession-openmsgstore.md) call.</span></span> 
  
<span data-ttu-id="57bd3-138">当客户端应用程序将传递给 MAPI 的换行的消息存储条目标识符时，例如进行[IMAPISession::OpenEntry](imapisession-openentry.md)通话，MAPI 进行解包的项标识符之前使用它来调用如[IMSProvider::Logon](imsprovider-logon.md)或[提供程序方法IMSProvider::CompareStoreIDs](imsprovider-comparestoreids.md)。</span><span class="sxs-lookup"><span data-stu-id="57bd3-138">When a client application passes a wrapped message store entry identifier to MAPI, for example in an [IMAPISession::OpenEntry](imapisession-openentry.md) call, MAPI unwraps the entry identifier before using it to call a provider method such as [IMSProvider::Logon](imsprovider-logon.md) or [IMSProvider::CompareStoreIDs](imsprovider-comparestoreids.md).</span></span> 
  

