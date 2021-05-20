---
title: HrOpenABEntryWithResolvedRow
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: ce3a583c-16a9-4268-9476-926d2780eae5
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 2eb643e0002e2159e3197d66e021aba0bb8c126f
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33429906"
---
# <a name="hropenabentrywithresolvedrow"></a><span data-ttu-id="cf1e1-103">HrOpenABEntryWithResolvedRow</span><span class="sxs-lookup"><span data-stu-id="cf1e1-103">HrOpenABEntryWithResolvedRow</span></span>

  
  
<span data-ttu-id="cf1e1-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="cf1e1-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="cf1e1-105">执行与 [HrOpenABEntryWithExchangeContext](hropenabentrywithexchangecontext.md) 相同的函数，只是它会自动从解析的行获取 **emsabpUID** 并打开 **entryID**。</span><span class="sxs-lookup"><span data-stu-id="cf1e1-105">Performs the same function as [HrOpenABEntryWithExchangeContext](hropenabentrywithexchangecontext.md) except that it automatically gets the **emsabpUID** from the resolved row and opens the **entryID**.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="cf1e1-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="cf1e1-106">Header file:</span></span>  <br/> |<span data-ttu-id="cf1e1-107">abhelp.h</span><span class="sxs-lookup"><span data-stu-id="cf1e1-107">abhelp.h</span></span>  <br/> |
|<span data-ttu-id="cf1e1-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="cf1e1-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="cf1e1-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="cf1e1-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="cf1e1-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="cf1e1-110">Called by:</span></span>  <br/> |<span data-ttu-id="cf1e1-111">客户端应用程序和服务提供商</span><span class="sxs-lookup"><span data-stu-id="cf1e1-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
HRESULT HrOpenABEntryWithResolvedRow(
  LPSRow prwResolved,
  LPADRBOOK pAddrBook,
  ULONG cbEntryID,
  LPENTRYID lpEntryID,
  LPCIID lpInterface,
  ULONG ulFlags,
  ULONG FAR * lpulObjType,
  LPUNKNOWN FAR * lppUnk
);
```

## <a name="parameters"></a><span data-ttu-id="cf1e1-112">参数</span><span class="sxs-lookup"><span data-stu-id="cf1e1-112">Parameters</span></span>

 <span data-ttu-id="cf1e1-113">_prwResolved_</span><span class="sxs-lookup"><span data-stu-id="cf1e1-113">_prwResolved_</span></span>
  
> <span data-ttu-id="cf1e1-114">[in]指向解析的行的指针，用于获取 **emsabpUID** 并打开 **entryID**。</span><span class="sxs-lookup"><span data-stu-id="cf1e1-114">[in] A pointer to the resolved row that is used to get the **emsabpUID** and open the **entryID**.</span></span>
    
 <span data-ttu-id="cf1e1-115">_pAddrBook_</span><span class="sxs-lookup"><span data-stu-id="cf1e1-115">_pAddrBook_</span></span>
  
> <span data-ttu-id="cf1e1-116">[in]用于打开条目标识符的通讯簿。</span><span class="sxs-lookup"><span data-stu-id="cf1e1-116">[in] The address book used to open the entry identifier.</span></span> <span data-ttu-id="cf1e1-117">它不能为 NULL。</span><span class="sxs-lookup"><span data-stu-id="cf1e1-117">It cannot be NULL.</span></span>
    
 <span data-ttu-id="cf1e1-118">_cbEntryID_</span><span class="sxs-lookup"><span data-stu-id="cf1e1-118">_cbEntryID_</span></span>
  
> <span data-ttu-id="cf1e1-119">[in]  _lpEntryID_ 参数指定的条目标识符的字节计数。</span><span class="sxs-lookup"><span data-stu-id="cf1e1-119">[in] The byte count of the entry identifier specified by the  _lpEntryID_ parameter.</span></span> 
    
 <span data-ttu-id="cf1e1-120">_lpEntryID_</span><span class="sxs-lookup"><span data-stu-id="cf1e1-120">_lpEntryID_</span></span>
  
>  <span data-ttu-id="cf1e1-121">[in]指向表示要打开的通讯簿条目的条目标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="cf1e1-121">[in] A pointer to the entry identifier that represents the address book entry to open.</span></span> 
    
 <span data-ttu-id="cf1e1-122">_lpInterface_</span><span class="sxs-lookup"><span data-stu-id="cf1e1-122">_lpInterface_</span></span>
  
> <span data-ttu-id="cf1e1-123">[in]指向用于访问打开 (的) 接口的 IID 标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="cf1e1-123">[in] A pointer to the interface identifier (IID) of the interface that is used to access the open entry.</span></span> <span data-ttu-id="cf1e1-124">传递 NULL 将返回对象的标准接口。</span><span class="sxs-lookup"><span data-stu-id="cf1e1-124">Passing NULL returns the standard interface of the object.</span></span> <span data-ttu-id="cf1e1-125">对于邮件用户，标准接口是 [IMailUser ： IMAPIProp](imailuserimapiprop.md)。</span><span class="sxs-lookup"><span data-stu-id="cf1e1-125">For messaging users, the standard interface is [IMailUser : IMAPIProp](imailuserimapiprop.md).</span></span> <span data-ttu-id="cf1e1-126">对于通讯组列表，它是 [IDistList ： IMAPIContainer，](idistlistimapicontainer.md)对于容器，它是 [IABContainer ： IMAPIContainer](iabcontainerimapicontainer.md)。</span><span class="sxs-lookup"><span data-stu-id="cf1e1-126">For distribution lists, it is [IDistList : IMAPIContainer](idistlistimapicontainer.md)and for containers, it is [IABContainer : IMAPIContainer](iabcontainerimapicontainer.md).</span></span> <span data-ttu-id="cf1e1-127">调用方可以将  _lpInterface_ 设置为相应的标准接口或继承层次结构中的接口。</span><span class="sxs-lookup"><span data-stu-id="cf1e1-127">Callers can set  _lpInterface_ to the appropriate standard interface or an interface in the inheritance hierarchy.</span></span> 
    
 <span data-ttu-id="cf1e1-128">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="cf1e1-128">_ulFlags_</span></span>
  
> <span data-ttu-id="cf1e1-129">[in]控制条目打开方式的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="cf1e1-129">[in] A bitmask of flags that controls how the entry is opened.</span></span> <span data-ttu-id="cf1e1-130">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="cf1e1-130">The following flags can be set:</span></span>
    
<span data-ttu-id="cf1e1-131">MAPI_BEST_ACCESS</span><span class="sxs-lookup"><span data-stu-id="cf1e1-131">MAPI_BEST_ACCESS</span></span>
  
> <span data-ttu-id="cf1e1-132">请求以允许的最大网络和客户端权限打开条目。</span><span class="sxs-lookup"><span data-stu-id="cf1e1-132">Requests that the entry be opened with the maximum allowed network and client permissions.</span></span> <span data-ttu-id="cf1e1-133">例如，如果客户端具有读取和写入权限，通讯簿提供程序将尝试打开具有读取和写入权限的条目。</span><span class="sxs-lookup"><span data-stu-id="cf1e1-133">For example, if the client has read and write permission, the address book provider attempts to open the entry with read and write permission.</span></span> <span data-ttu-id="cf1e1-134">客户端可以检索通过调用打开条目的 [IMAPIProp：：GetProps](imapiprop-getprops.md) 方法并检索 PR_ACCESS_LEVEL (PidTagAccessLevel) 属性授予的访问级别。</span><span class="sxs-lookup"><span data-stu-id="cf1e1-134">The client can retrieve the access level that was granted by calling the [IMAPIProp::GetProps](imapiprop-getprops.md) method of the open entry and retrieving the PR_ACCESS_LEVEL (PidTagAccessLevel) property.</span></span> 
    
<span data-ttu-id="cf1e1-135">MAPI_CACHE_ONLY</span><span class="sxs-lookup"><span data-stu-id="cf1e1-135">MAPI_CACHE_ONLY</span></span>
  
> <span data-ttu-id="cf1e1-136">仅使用脱机通讯簿来执行名称解析。</span><span class="sxs-lookup"><span data-stu-id="cf1e1-136">Uses only the offline address book to perform name resolution.</span></span> <span data-ttu-id="cf1e1-137">例如，您可以使用此标志允许客户端应用程序在缓存 exchange 模式下打开全局地址列表 (GAL) ，并访问缓存中的该通讯簿中的条目，而无需在客户端和服务器之间创建流量。</span><span class="sxs-lookup"><span data-stu-id="cf1e1-137">For example, you can use this flag to allow a client application to open the global address list (GAL) in cached exchange mode and access an entry in that address book from the cache without creating traffic between the client and the server.</span></span> <span data-ttu-id="cf1e1-138">此标志仅受通讯簿Exchange支持。</span><span class="sxs-lookup"><span data-stu-id="cf1e1-138">This flag is supported only by the Exchange Address Book Provider.</span></span>
    
<span data-ttu-id="cf1e1-139">MAPI_DEFERRED_ERRORS</span><span class="sxs-lookup"><span data-stu-id="cf1e1-139">MAPI_DEFERRED_ERRORS</span></span>
  
> <span data-ttu-id="cf1e1-140">允许在条目完全打开且可用之前成功调用，这意味着对条目的后续调用可能会返回错误。</span><span class="sxs-lookup"><span data-stu-id="cf1e1-140">Allows the call to succeed, potentially before the entry is fully open and available, implying that subsequent calls to the entry might return an error.</span></span>
    
<span data-ttu-id="cf1e1-141">MAPI_GAL_ONLY</span><span class="sxs-lookup"><span data-stu-id="cf1e1-141">MAPI_GAL_ONLY</span></span>
  
> <span data-ttu-id="cf1e1-142">仅使用 GAL 执行名称解析。</span><span class="sxs-lookup"><span data-stu-id="cf1e1-142">Uses only the GAL to perform name resolution.</span></span> <span data-ttu-id="cf1e1-143">此标志仅受通讯簿Exchange支持。</span><span class="sxs-lookup"><span data-stu-id="cf1e1-143">This flag is supported only by the Exchange Address Book Provider.</span></span>
    
<span data-ttu-id="cf1e1-144">MAPI_MODIFY</span><span class="sxs-lookup"><span data-stu-id="cf1e1-144">MAPI_MODIFY</span></span>
  
> <span data-ttu-id="cf1e1-145">请求使用读取和写入权限打开条目。</span><span class="sxs-lookup"><span data-stu-id="cf1e1-145">Requests that the entry be opened with read and write permission.</span></span> <span data-ttu-id="cf1e1-146">由于默认情况下使用只读访问权限打开条目，因此客户端不应假定已授予读取和写入权限，MAPI_MODIFY权限。</span><span class="sxs-lookup"><span data-stu-id="cf1e1-146">Because entries are opened with read-only access by default, clients should not assume that read and write permission was granted regardless of whether MAPI_MODIFY is set.</span></span>
    
<span data-ttu-id="cf1e1-147">MAPI_NO_CACHE</span><span class="sxs-lookup"><span data-stu-id="cf1e1-147">MAPI_NO_CACHE</span></span>
  
> <span data-ttu-id="cf1e1-148">不使用脱机通讯簿执行名称解析。</span><span class="sxs-lookup"><span data-stu-id="cf1e1-148">Does not use the offline address book to perform name resolution.</span></span> <span data-ttu-id="cf1e1-149">此标志仅受通讯簿Exchange支持。</span><span class="sxs-lookup"><span data-stu-id="cf1e1-149">This flag is supported only by the Exchange Address Book Provider.</span></span>
    
 <span data-ttu-id="cf1e1-150">_lpulObjType_</span><span class="sxs-lookup"><span data-stu-id="cf1e1-150">_lpulObjType_</span></span>
  
> <span data-ttu-id="cf1e1-151">[out]指向打开的条目类型的指针。</span><span class="sxs-lookup"><span data-stu-id="cf1e1-151">[out] A pointer to the type of the opened entry.</span></span>
    
 <span data-ttu-id="cf1e1-152">_lppUnk_</span><span class="sxs-lookup"><span data-stu-id="cf1e1-152">_lppUnk_</span></span>
  
> <span data-ttu-id="cf1e1-153">[out]指向已打开条目的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="cf1e1-153">[out] A pointer to a pointer of the opened entry.</span></span>
    

