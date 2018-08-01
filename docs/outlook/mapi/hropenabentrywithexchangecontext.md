---
title: HrOpenABEntryWithExchangeContext
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: b640a5aa-4e36-4983-bf11-9428809e830b
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: fcedaf689db8280b4649662ba61c8468d0f98305
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775175"
---
# <a name="hropenabentrywithexchangecontext"></a><span data-ttu-id="63f31-103">HrOpenABEntryWithExchangeContext</span><span class="sxs-lookup"><span data-stu-id="63f31-103">HrOpenABEntryWithExchangeContext</span></span>

  
  
<span data-ttu-id="63f31-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="63f31-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="63f31-105">打开使用由**pEmsmdbUID**标识 Exchange 通讯簿**entryID** 。</span><span class="sxs-lookup"><span data-stu-id="63f31-105">Opens the **entryID** using the Exchange Address Book identified by **pEmsmdbUID**.</span></span> <span data-ttu-id="63f31-106">此功能向[IAddrBook::Details](iaddrbook-details.md)有效同样，只不过使用此函数可确保[IAddrBook::OpenEntry](iaddrbook-openentry.md)通过使用预期的 Exchange 通讯簿提供程序打开。</span><span class="sxs-lookup"><span data-stu-id="63f31-106">This function works similarly to [IAddrBook::Details](iaddrbook-details.md) except that using this function ensures that the [IAddrBook::OpenEntry](iaddrbook-openentry.md) is opened by using the expected Exchange Address Book Provider.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="63f31-107">头文件：</span><span class="sxs-lookup"><span data-stu-id="63f31-107">Header file:</span></span>  <br/> |<span data-ttu-id="63f31-108">abhelp.h</span><span class="sxs-lookup"><span data-stu-id="63f31-108">abhelp.h</span></span>  <br/> |
|<span data-ttu-id="63f31-109">通过实现：</span><span class="sxs-lookup"><span data-stu-id="63f31-109">Implemented by:</span></span>  <br/> |<span data-ttu-id="63f31-110">MAPI</span><span class="sxs-lookup"><span data-stu-id="63f31-110">MAPI</span></span>  <br/> |
|<span data-ttu-id="63f31-111">调用：</span><span class="sxs-lookup"><span data-stu-id="63f31-111">Called by:</span></span>  <br/> |<span data-ttu-id="63f31-112">客户端应用程序和服务提供商</span><span class="sxs-lookup"><span data-stu-id="63f31-112">Client applications and service providers</span></span>  <br/> |
   
```cpp
HRESULT HrDoABDetailsWithExchangeContext(
  LPMAPISESSION pmsess,
  const MAPIUID *pEmsmdbUID,
  LPADRBOOK pAddrBook,
  ULONG cbEntryID,
  LPENTRYID lpEntryID,
  LPCIID lpInterface,
  ULONG ulFlags
);
```

## <a name="parameters"></a><span data-ttu-id="63f31-113">参数</span><span class="sxs-lookup"><span data-stu-id="63f31-113">Parameters</span></span>

 <span data-ttu-id="63f31-114">_pmsess_</span><span class="sxs-lookup"><span data-stu-id="63f31-114">_pmsess_</span></span>
  
> <span data-ttu-id="63f31-115">[in]登录**IMAPISession**。</span><span class="sxs-lookup"><span data-stu-id="63f31-115">[in] The logged on **IMAPISession**.</span></span> <span data-ttu-id="63f31-116">它不能为 NULL。</span><span class="sxs-lookup"><span data-stu-id="63f31-116">It cannot be NULL.</span></span>
    
 <span data-ttu-id="63f31-117">_pEmsmdbUID_</span><span class="sxs-lookup"><span data-stu-id="63f31-117">_pEmsmdbUID_</span></span>
  
> <span data-ttu-id="63f31-118">[in]指向标识包含 Exchange 通讯簿提供程序，此函数应该使用要显示的项标识符的详细信息的 Exchange 服务**emsmdbUID**的指针。</span><span class="sxs-lookup"><span data-stu-id="63f31-118">[in] A pointer to an **emsmdbUID** that identifies the Exchange Service that contains the Exchange Address Book Provider that this function should use to display details on the entry identifier.</span></span> <span data-ttu-id="63f31-119">如果传入的项标识符不是 Exchange 通讯簿提供程序条目标识符，则忽略此参数，并函数调用与[IAddrBook::Details](iaddrbook-details.md)相似之处。</span><span class="sxs-lookup"><span data-stu-id="63f31-119">If the incoming entry identifier is not an Exchange Address Book Provider entry identifier, this parameter is ignored and the function call behaves like [IAddrBook::Details](iaddrbook-details.md).</span></span> <span data-ttu-id="63f31-120">如果此参数为 NULL 或零 MAPIUID，此函数的行为类似[IAddrBook::Details](iaddrbook-details.md)。</span><span class="sxs-lookup"><span data-stu-id="63f31-120">If this parameter is NULL or a zero MAPIUID, this function behaves like [IAddrBook::Details](iaddrbook-details.md).</span></span>
    
 <span data-ttu-id="63f31-121">_pAddrBook_</span><span class="sxs-lookup"><span data-stu-id="63f31-121">_pAddrBook_</span></span>
  
> <span data-ttu-id="63f31-122">[in]通讯簿用于打开的项标识符。</span><span class="sxs-lookup"><span data-stu-id="63f31-122">[in] The address book used to open the entry identifier.</span></span> <span data-ttu-id="63f31-123">它不能为 NULL。</span><span class="sxs-lookup"><span data-stu-id="63f31-123">It cannot be NULL.</span></span>
    
 <span data-ttu-id="63f31-124">_cbEntryID_</span><span class="sxs-lookup"><span data-stu-id="63f31-124">_cbEntryID_</span></span>
  
> <span data-ttu-id="63f31-125">[in]_LpEntryID_参数指定的项标识符的字节数。</span><span class="sxs-lookup"><span data-stu-id="63f31-125">[in] The byte count of the entry identifier specified by the  _lpEntryID_ parameter.</span></span> 
    
 <span data-ttu-id="63f31-126">_lpEntryID_</span><span class="sxs-lookup"><span data-stu-id="63f31-126">_lpEntryID_</span></span>
  
>  <span data-ttu-id="63f31-127">[in]一个指向代表打开的通讯簿条目的项标识符。</span><span class="sxs-lookup"><span data-stu-id="63f31-127">[in] A pointer to the entry identifier that represents the address book entry to open.</span></span> 
    
 <span data-ttu-id="63f31-128">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="63f31-128">_ulFlags_</span></span>
  
> <span data-ttu-id="63f31-129">[in]位掩码的标志，控制如何打开该条目。</span><span class="sxs-lookup"><span data-stu-id="63f31-129">[in] A bitmask of flags that controls how the entry is opened.</span></span> <span data-ttu-id="63f31-130">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="63f31-130">The following flags can be set:</span></span>
    
<span data-ttu-id="63f31-131">MAPI_BEST_ACCESS</span><span class="sxs-lookup"><span data-stu-id="63f31-131">MAPI_BEST_ACCESS</span></span>
  
> <span data-ttu-id="63f31-132">与最大允许网络和客户端权限打开的条目的请求。</span><span class="sxs-lookup"><span data-stu-id="63f31-132">Requests that the entry be opened with the maximum allowed network and client permissions.</span></span> <span data-ttu-id="63f31-133">例如，如果客户端具有读取和写入权限，通讯簿提供程序尝试打开条目具有读取和写入权限。</span><span class="sxs-lookup"><span data-stu-id="63f31-133">For example, if the client has read and write permission, the address book provider attempts to open the entry with read and write permission.</span></span> <span data-ttu-id="63f31-134">客户端可以检索通过调用打开条目的[IMAPIProp::GetProps](imapiprop-getprops.md)方法并检索 PR_ACCESS_LEVEL (PidTagAccessLevel) 属性授予的访问级别。</span><span class="sxs-lookup"><span data-stu-id="63f31-134">The client can retrieve the access level that was granted by calling the [IMAPIProp::GetProps](imapiprop-getprops.md) method of the open entry and retrieving the PR_ACCESS_LEVEL (PidTagAccessLevel) property.</span></span> 
    
<span data-ttu-id="63f31-135">MAPI_CACHE_ONLY</span><span class="sxs-lookup"><span data-stu-id="63f31-135">MAPI_CACHE_ONLY</span></span>
  
> <span data-ttu-id="63f31-136">使用仅脱机通讯簿执行名称解析。</span><span class="sxs-lookup"><span data-stu-id="63f31-136">Uses only the offline address book to perform name resolution.</span></span> <span data-ttu-id="63f31-137">例如，您可以使用此标志以允许将客户端应用程序在缓存的 exchange 模式下打开全局地址列表 (GAL)，而不创建客户端和服务器之间的流量从缓存中访问该通讯簿中的条目。</span><span class="sxs-lookup"><span data-stu-id="63f31-137">For example, you can use this flag to allow a client application to open the global address list (GAL) in cached exchange mode and access an entry in that address book from the cache without creating traffic between the client and the server.</span></span> <span data-ttu-id="63f31-138">此标志仅受 Exchange 通讯簿提供程序支持。</span><span class="sxs-lookup"><span data-stu-id="63f31-138">This flag is supported only by the Exchange Address Book Provider.</span></span>
    
<span data-ttu-id="63f31-139">MAPI_DEFERRED_ERRORS</span><span class="sxs-lookup"><span data-stu-id="63f31-139">MAPI_DEFERRED_ERRORS</span></span>
  
> <span data-ttu-id="63f31-140">允许的调用成功，可能之前该条目是完全打开且可用，这意味着该条目的后面对会返回一个错误。</span><span class="sxs-lookup"><span data-stu-id="63f31-140">Allows the call to succeed, potentially before the entry is fully open and available, implying that subsequent calls to the entry might return an error.</span></span>
    
<span data-ttu-id="63f31-141">MAPI_GAL_ONLY</span><span class="sxs-lookup"><span data-stu-id="63f31-141">MAPI_GAL_ONLY</span></span>
  
> <span data-ttu-id="63f31-142">使用仅 GAL 执行名称解析。</span><span class="sxs-lookup"><span data-stu-id="63f31-142">Uses only the GAL to perform name resolution.</span></span> <span data-ttu-id="63f31-143">此标志仅受 Exchange 通讯簿提供程序支持。</span><span class="sxs-lookup"><span data-stu-id="63f31-143">This flag is supported only by the Exchange Address Book Provider.</span></span>
    
<span data-ttu-id="63f31-144">MAPI_MODIFY</span><span class="sxs-lookup"><span data-stu-id="63f31-144">MAPI_MODIFY</span></span>
  
> <span data-ttu-id="63f31-145">请求项打开的读取和写入权限。</span><span class="sxs-lookup"><span data-stu-id="63f31-145">Requests that the entry be opened with read and write permission.</span></span> <span data-ttu-id="63f31-146">因为条目具有只读访问权限打开默认情况下，客户端不应假定的读取和写入无论是否设置 MAPI_MODIFY 授予了权限。</span><span class="sxs-lookup"><span data-stu-id="63f31-146">Because entries are opened with read-only access by default, clients should not assume that read and write permission was granted regardless of whether MAPI_MODIFY is set.</span></span>
    
<span data-ttu-id="63f31-147">MAPI_NO_CACHE</span><span class="sxs-lookup"><span data-stu-id="63f31-147">MAPI_NO_CACHE</span></span>
  
> <span data-ttu-id="63f31-148">不使用脱机通讯簿执行名称解析。</span><span class="sxs-lookup"><span data-stu-id="63f31-148">Does not use the offline address book to perform name resolution.</span></span> <span data-ttu-id="63f31-149">此标志仅受 Exchange 通讯簿提供程序支持。</span><span class="sxs-lookup"><span data-stu-id="63f31-149">This flag is supported only by the Exchange Address Book Provider.</span></span>
    

