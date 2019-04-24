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
ms.openlocfilehash: 415d108f7fd9e84ba2a9090658bc0923550390f2
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32347787"
---
# <a name="hropenabentrywithexchangecontext"></a><span data-ttu-id="fa8ba-103">HrOpenABEntryWithExchangeContext</span><span class="sxs-lookup"><span data-stu-id="fa8ba-103">HrOpenABEntryWithExchangeContext</span></span>

  
  
<span data-ttu-id="fa8ba-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="fa8ba-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="fa8ba-105">使用由**pEmsmdbUID**标识的 Exchange 通讯簿打开**entryID** 。</span><span class="sxs-lookup"><span data-stu-id="fa8ba-105">Opens the **entryID** using the Exchange Address Book identified by **pEmsmdbUID**.</span></span> <span data-ttu-id="fa8ba-106">此函数的工作方式类似于[IAddrBook::D etails](iaddrbook-details.md) , 但使用此函数可确保使用预期的 Exchange 通讯簿提供程序打开[IAddrBook:: OpenEntry](iaddrbook-openentry.md) 。</span><span class="sxs-lookup"><span data-stu-id="fa8ba-106">This function works similarly to [IAddrBook::Details](iaddrbook-details.md) except that using this function ensures that the [IAddrBook::OpenEntry](iaddrbook-openentry.md) is opened by using the expected Exchange Address Book Provider.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="fa8ba-107">标头文件：</span><span class="sxs-lookup"><span data-stu-id="fa8ba-107">Header file:</span></span>  <br/> |<span data-ttu-id="fa8ba-108">abhelp</span><span class="sxs-lookup"><span data-stu-id="fa8ba-108">abhelp.h</span></span>  <br/> |
|<span data-ttu-id="fa8ba-109">实现者：</span><span class="sxs-lookup"><span data-stu-id="fa8ba-109">Implemented by:</span></span>  <br/> |<span data-ttu-id="fa8ba-110">MAPI</span><span class="sxs-lookup"><span data-stu-id="fa8ba-110">MAPI</span></span>  <br/> |
|<span data-ttu-id="fa8ba-111">调用者：</span><span class="sxs-lookup"><span data-stu-id="fa8ba-111">Called by:</span></span>  <br/> |<span data-ttu-id="fa8ba-112">客户端应用程序和服务提供程序</span><span class="sxs-lookup"><span data-stu-id="fa8ba-112">Client applications and service providers</span></span>  <br/> |
   
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

## <a name="parameters"></a><span data-ttu-id="fa8ba-113">参数</span><span class="sxs-lookup"><span data-stu-id="fa8ba-113">Parameters</span></span>

 <span data-ttu-id="fa8ba-114">_pmsess_</span><span class="sxs-lookup"><span data-stu-id="fa8ba-114">_pmsess_</span></span>
  
> <span data-ttu-id="fa8ba-115">实时登录的**IMAPISession**。</span><span class="sxs-lookup"><span data-stu-id="fa8ba-115">[in] The logged on **IMAPISession**.</span></span> <span data-ttu-id="fa8ba-116">它不能为 NULL。</span><span class="sxs-lookup"><span data-stu-id="fa8ba-116">It cannot be NULL.</span></span>
    
 <span data-ttu-id="fa8ba-117">_pEmsmdbUID_</span><span class="sxs-lookup"><span data-stu-id="fa8ba-117">_pEmsmdbUID_</span></span>
  
> <span data-ttu-id="fa8ba-118">实时指向**emsmdbUID**的指针, 该链接标识包含此函数应用于显示条目标识符详细信息的 exchange 通讯簿提供程序的 exchange 服务。</span><span class="sxs-lookup"><span data-stu-id="fa8ba-118">[in] A pointer to an **emsmdbUID** that identifies the Exchange Service that contains the Exchange Address Book Provider that this function should use to display details on the entry identifier.</span></span> <span data-ttu-id="fa8ba-119">如果传入条目标识符不是 Exchange 通讯簿提供程序条目标识符, 则此参数将被忽略, 并且函数调用的行为就像[IAddrBook::D etails](iaddrbook-details.md)。</span><span class="sxs-lookup"><span data-stu-id="fa8ba-119">If the incoming entry identifier is not an Exchange Address Book Provider entry identifier, this parameter is ignored and the function call behaves like [IAddrBook::Details](iaddrbook-details.md).</span></span> <span data-ttu-id="fa8ba-120">如果此参数为 NULL 或零 MAPIUID, 则此函数的行为类似于[IAddrBook::D etails](iaddrbook-details.md)。</span><span class="sxs-lookup"><span data-stu-id="fa8ba-120">If this parameter is NULL or a zero MAPIUID, this function behaves like [IAddrBook::Details](iaddrbook-details.md).</span></span>
    
 <span data-ttu-id="fa8ba-121">_pAddrBook_</span><span class="sxs-lookup"><span data-stu-id="fa8ba-121">_pAddrBook_</span></span>
  
> <span data-ttu-id="fa8ba-122">实时用于打开条目标识符的通讯簿。</span><span class="sxs-lookup"><span data-stu-id="fa8ba-122">[in] The address book used to open the entry identifier.</span></span> <span data-ttu-id="fa8ba-123">它不能为 NULL。</span><span class="sxs-lookup"><span data-stu-id="fa8ba-123">It cannot be NULL.</span></span>
    
 <span data-ttu-id="fa8ba-124">_cbEntryID_</span><span class="sxs-lookup"><span data-stu-id="fa8ba-124">_cbEntryID_</span></span>
  
> <span data-ttu-id="fa8ba-125">实时由_lpEntryID_参数指定的条目标识符的字节数。</span><span class="sxs-lookup"><span data-stu-id="fa8ba-125">[in] The byte count of the entry identifier specified by the  _lpEntryID_ parameter.</span></span> 
    
 <span data-ttu-id="fa8ba-126">_lpEntryID_</span><span class="sxs-lookup"><span data-stu-id="fa8ba-126">_lpEntryID_</span></span>
  
>  <span data-ttu-id="fa8ba-127">实时指向表示要打开的通讯簿条目的条目标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="fa8ba-127">[in] A pointer to the entry identifier that represents the address book entry to open.</span></span> 
    
 <span data-ttu-id="fa8ba-128">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="fa8ba-128">_ulFlags_</span></span>
  
> <span data-ttu-id="fa8ba-129">实时用于控制条目打开方式的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="fa8ba-129">[in] A bitmask of flags that controls how the entry is opened.</span></span> <span data-ttu-id="fa8ba-130">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="fa8ba-130">The following flags can be set:</span></span>
    
<span data-ttu-id="fa8ba-131">MAPI_BEST_ACCESS</span><span class="sxs-lookup"><span data-stu-id="fa8ba-131">MAPI_BEST_ACCESS</span></span>
  
> <span data-ttu-id="fa8ba-132">请求使用最大允许的网络和客户端权限打开条目。</span><span class="sxs-lookup"><span data-stu-id="fa8ba-132">Requests that the entry be opened with the maximum allowed network and client permissions.</span></span> <span data-ttu-id="fa8ba-133">例如, 如果客户端具有读取和写入权限, 则通讯簿提供程序将尝试打开具有读取和写入权限的条目。</span><span class="sxs-lookup"><span data-stu-id="fa8ba-133">For example, if the client has read and write permission, the address book provider attempts to open the entry with read and write permission.</span></span> <span data-ttu-id="fa8ba-134">客户端可以通过调用 open 项的[IMAPIProp:: GetProps](imapiprop-getprops.md)方法和检索 PR_ACCESS_LEVEL (PidTagAccessLevel) 属性来检索已授予的访问级别。</span><span class="sxs-lookup"><span data-stu-id="fa8ba-134">The client can retrieve the access level that was granted by calling the [IMAPIProp::GetProps](imapiprop-getprops.md) method of the open entry and retrieving the PR_ACCESS_LEVEL (PidTagAccessLevel) property.</span></span> 
    
<span data-ttu-id="fa8ba-135">MAPI_CACHE_ONLY</span><span class="sxs-lookup"><span data-stu-id="fa8ba-135">MAPI_CACHE_ONLY</span></span>
  
> <span data-ttu-id="fa8ba-136">仅使用脱机通讯簿执行名称解析。</span><span class="sxs-lookup"><span data-stu-id="fa8ba-136">Uses only the offline address book to perform name resolution.</span></span> <span data-ttu-id="fa8ba-137">例如, 可以使用此标志允许客户端应用程序在缓存 exchange 模式中打开全局地址列表 (GAL), 并从缓存中访问该通讯簿中的条目, 而无需在客户端和服务器之间创建流量。</span><span class="sxs-lookup"><span data-stu-id="fa8ba-137">For example, you can use this flag to allow a client application to open the global address list (GAL) in cached exchange mode and access an entry in that address book from the cache without creating traffic between the client and the server.</span></span> <span data-ttu-id="fa8ba-138">仅 Exchange 通讯簿提供程序支持此标志。</span><span class="sxs-lookup"><span data-stu-id="fa8ba-138">This flag is supported only by the Exchange Address Book Provider.</span></span>
    
<span data-ttu-id="fa8ba-139">MAPI_DEFERRED_ERRORS</span><span class="sxs-lookup"><span data-stu-id="fa8ba-139">MAPI_DEFERRED_ERRORS</span></span>
  
> <span data-ttu-id="fa8ba-140">允许调用成功 (可能在条目完全打开且可用之前), 这意味着随后对该条目的调用可能会返回错误。</span><span class="sxs-lookup"><span data-stu-id="fa8ba-140">Allows the call to succeed, potentially before the entry is fully open and available, implying that subsequent calls to the entry might return an error.</span></span>
    
<span data-ttu-id="fa8ba-141">MAPI_GAL_ONLY</span><span class="sxs-lookup"><span data-stu-id="fa8ba-141">MAPI_GAL_ONLY</span></span>
  
> <span data-ttu-id="fa8ba-142">仅使用 GAL 执行名称解析。</span><span class="sxs-lookup"><span data-stu-id="fa8ba-142">Uses only the GAL to perform name resolution.</span></span> <span data-ttu-id="fa8ba-143">仅 Exchange 通讯簿提供程序支持此标志。</span><span class="sxs-lookup"><span data-stu-id="fa8ba-143">This flag is supported only by the Exchange Address Book Provider.</span></span>
    
<span data-ttu-id="fa8ba-144">MAPI_MODIFY</span><span class="sxs-lookup"><span data-stu-id="fa8ba-144">MAPI_MODIFY</span></span>
  
> <span data-ttu-id="fa8ba-145">请求使用 "读取" 和 "写入" 权限打开条目。</span><span class="sxs-lookup"><span data-stu-id="fa8ba-145">Requests that the entry be opened with read and write permission.</span></span> <span data-ttu-id="fa8ba-146">由于默认情况下会打开具有只读访问权限的条目, 因此客户端不应假定已授予 "读取" 和 "写入" 权限, 而不管是否设置了 MAPI_MODIFY。</span><span class="sxs-lookup"><span data-stu-id="fa8ba-146">Because entries are opened with read-only access by default, clients should not assume that read and write permission was granted regardless of whether MAPI_MODIFY is set.</span></span>
    
<span data-ttu-id="fa8ba-147">MAPI_NO_CACHE</span><span class="sxs-lookup"><span data-stu-id="fa8ba-147">MAPI_NO_CACHE</span></span>
  
> <span data-ttu-id="fa8ba-148">不使用脱机通讯簿执行名称解析。</span><span class="sxs-lookup"><span data-stu-id="fa8ba-148">Does not use the offline address book to perform name resolution.</span></span> <span data-ttu-id="fa8ba-149">仅 Exchange 通讯簿提供程序支持此标志。</span><span class="sxs-lookup"><span data-stu-id="fa8ba-149">This flag is supported only by the Exchange Address Book Provider.</span></span>
    

