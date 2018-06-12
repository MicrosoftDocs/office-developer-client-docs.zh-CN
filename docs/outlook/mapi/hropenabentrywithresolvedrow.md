---
title: HrOpenABEntryWithResolvedRow
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: ce3a583c-16a9-4268-9476-926d2780eae5
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 0e39f4edc871b49675f1ffcc1bc541345c8829d5
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775202"
---
# <a name="hropenabentrywithresolvedrow"></a><span data-ttu-id="8571d-103">HrOpenABEntryWithResolvedRow</span><span class="sxs-lookup"><span data-stu-id="8571d-103">HrOpenABEntryWithResolvedRow</span></span>

  
  
<span data-ttu-id="8571d-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="8571d-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="8571d-105">在于它会自动从解决的行中获取**emsabpUID**和打开**entryID**执行[HrOpenABEntryWithExchangeContext](hropenabentrywithexchangecontext.md)相同的功能。</span><span class="sxs-lookup"><span data-stu-id="8571d-105">Performs the same function as [HrOpenABEntryWithExchangeContext](hropenabentrywithexchangecontext.md) except that it automatically gets the **emsabpUID** from the resolved row and opens the **entryID**.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="8571d-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="8571d-106">Header file:</span></span>  <br/> |<span data-ttu-id="8571d-107">abhelp.h</span><span class="sxs-lookup"><span data-stu-id="8571d-107">abhelp.h</span></span>  <br/> |
|<span data-ttu-id="8571d-108">通过实现：</span><span class="sxs-lookup"><span data-stu-id="8571d-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="8571d-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="8571d-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="8571d-110">调用：</span><span class="sxs-lookup"><span data-stu-id="8571d-110">Called by:</span></span>  <br/> |<span data-ttu-id="8571d-111">客户端应用程序和服务提供商</span><span class="sxs-lookup"><span data-stu-id="8571d-111">Client applications and service providers</span></span>  <br/> |
   
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

## <a name="parameters"></a><span data-ttu-id="8571d-112">参数</span><span class="sxs-lookup"><span data-stu-id="8571d-112">Parameters</span></span>

 <span data-ttu-id="8571d-113">_prwResolved_</span><span class="sxs-lookup"><span data-stu-id="8571d-113">_prwResolved_</span></span>
  
> <span data-ttu-id="8571d-114">[in]一个指向用于获取**emsabpUID**和打开**entryID**解决的行。</span><span class="sxs-lookup"><span data-stu-id="8571d-114">[in] A pointer to the resolved row that is used to get the **emsabpUID** and open the **entryID**.</span></span>
    
 <span data-ttu-id="8571d-115">_pAddrBook_</span><span class="sxs-lookup"><span data-stu-id="8571d-115">_pAddrBook_</span></span>
  
> <span data-ttu-id="8571d-116">[in]通讯簿用于打开的项标识符。</span><span class="sxs-lookup"><span data-stu-id="8571d-116">[in] The address book used to open the entry identifier.</span></span> <span data-ttu-id="8571d-117">它不能为 NULL。</span><span class="sxs-lookup"><span data-stu-id="8571d-117">It cannot be NULL.</span></span>
    
 <span data-ttu-id="8571d-118">_cbEntryID_</span><span class="sxs-lookup"><span data-stu-id="8571d-118">_cbEntryID_</span></span>
  
> <span data-ttu-id="8571d-119">[in]_LpEntryID_参数指定的项标识符的字节数。</span><span class="sxs-lookup"><span data-stu-id="8571d-119">[in] The byte count of the entry identifier specified by the  _lpEntryID_ parameter.</span></span> 
    
 <span data-ttu-id="8571d-120">_lpEntryID_</span><span class="sxs-lookup"><span data-stu-id="8571d-120">_lpEntryID_</span></span>
  
>  <span data-ttu-id="8571d-121">[in]一个指向代表打开的通讯簿条目的项标识符。</span><span class="sxs-lookup"><span data-stu-id="8571d-121">[in] A pointer to the entry identifier that represents the address book entry to open.</span></span> 
    
 <span data-ttu-id="8571d-122">_lpInterface_</span><span class="sxs-lookup"><span data-stu-id="8571d-122">_lpInterface_</span></span>
  
> <span data-ttu-id="8571d-123">[in]指向用于访问打开条目的接口的接口标识符 (IID) 的指针。</span><span class="sxs-lookup"><span data-stu-id="8571d-123">[in] A pointer to the interface identifier (IID) of the interface that is used to access the open entry.</span></span> <span data-ttu-id="8571d-124">传递 NULL 将返回标准接口的对象。</span><span class="sxs-lookup"><span data-stu-id="8571d-124">Passing NULL returns the standard interface of the object.</span></span> <span data-ttu-id="8571d-125">对于邮件用户，标准接口是[IMailUser: IMAPIProp](imailuserimapiprop.md)。</span><span class="sxs-lookup"><span data-stu-id="8571d-125">For messaging users, the standard interface is [IMailUser : IMAPIProp](imailuserimapiprop.md).</span></span> <span data-ttu-id="8571d-126">对于通讯组列表，它是[IDistList: IMAPIContainer](idistlistimapicontainer.md)而容器，则为： [IABContainer: IMAPIContainer](iabcontainerimapicontainer.md)。</span><span class="sxs-lookup"><span data-stu-id="8571d-126">For distribution lists, it is [IDistList : IMAPIContainer](idistlistimapicontainer.md)and for containers, it is [IABContainer : IMAPIContainer](iabcontainerimapicontainer.md).</span></span> <span data-ttu-id="8571d-127">呼叫者可以设置_lpInterface_为相应的标准接口或继承层次结构中的接口。</span><span class="sxs-lookup"><span data-stu-id="8571d-127">Callers can set  _lpInterface_ to the appropriate standard interface or an interface in the inheritance hierarchy.</span></span> 
    
 <span data-ttu-id="8571d-128">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="8571d-128">_ulFlags_</span></span>
  
> <span data-ttu-id="8571d-129">[in]位掩码的标志，控制如何打开该条目。</span><span class="sxs-lookup"><span data-stu-id="8571d-129">[in] A bitmask of flags that controls how the entry is opened.</span></span> <span data-ttu-id="8571d-130">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="8571d-130">The following flags can be set:</span></span>
    
<span data-ttu-id="8571d-131">MAPI_BEST_ACCESS</span><span class="sxs-lookup"><span data-stu-id="8571d-131">MAPI_BEST_ACCESS</span></span>
  
> <span data-ttu-id="8571d-132">与最大允许网络和客户端权限打开的条目的请求。</span><span class="sxs-lookup"><span data-stu-id="8571d-132">Requests that the entry be opened with the maximum allowed network and client permissions.</span></span> <span data-ttu-id="8571d-133">例如，如果客户端具有读取和写入权限，通讯簿提供程序尝试打开条目具有读取和写入权限。</span><span class="sxs-lookup"><span data-stu-id="8571d-133">For example, if the client has read and write permission, the address book provider attempts to open the entry with read and write permission.</span></span> <span data-ttu-id="8571d-134">客户端可以检索通过调用打开条目的[IMAPIProp::GetProps](imapiprop-getprops.md)方法并检索 PR_ACCESS_LEVEL (PidTagAccessLevel) 属性授予的访问级别。</span><span class="sxs-lookup"><span data-stu-id="8571d-134">The client can retrieve the access level that was granted by calling the [IMAPIProp::GetProps](imapiprop-getprops.md) method of the open entry and retrieving the PR_ACCESS_LEVEL (PidTagAccessLevel) property.</span></span> 
    
<span data-ttu-id="8571d-135">MAPI_CACHE_ONLY</span><span class="sxs-lookup"><span data-stu-id="8571d-135">MAPI_CACHE_ONLY</span></span>
  
> <span data-ttu-id="8571d-136">使用仅脱机通讯簿执行名称解析。</span><span class="sxs-lookup"><span data-stu-id="8571d-136">Uses only the offline address book to perform name resolution.</span></span> <span data-ttu-id="8571d-137">例如，您可以使用此标志以允许将客户端应用程序在缓存的 exchange 模式下打开全局地址列表 (GAL)，而不创建客户端和服务器之间的流量从缓存中访问该通讯簿中的条目。</span><span class="sxs-lookup"><span data-stu-id="8571d-137">For example, you can use this flag to allow a client application to open the global address list (GAL) in cached exchange mode and access an entry in that address book from the cache without creating traffic between the client and the server.</span></span> <span data-ttu-id="8571d-138">此标志仅受 Exchange 通讯簿提供程序支持。</span><span class="sxs-lookup"><span data-stu-id="8571d-138">This flag is supported only by the Exchange Address Book Provider.</span></span>
    
<span data-ttu-id="8571d-139">MAPI_DEFERRED_ERRORS</span><span class="sxs-lookup"><span data-stu-id="8571d-139">MAPI_DEFERRED_ERRORS</span></span>
  
> <span data-ttu-id="8571d-140">允许的调用成功，可能之前该条目是完全打开且可用，这意味着该条目的后面对会返回一个错误。</span><span class="sxs-lookup"><span data-stu-id="8571d-140">Allows the call to succeed, potentially before the entry is fully open and available, implying that subsequent calls to the entry might return an error.</span></span>
    
<span data-ttu-id="8571d-141">MAPI_GAL_ONLY</span><span class="sxs-lookup"><span data-stu-id="8571d-141">MAPI_GAL_ONLY</span></span>
  
> <span data-ttu-id="8571d-142">使用仅 GAL 执行名称解析。</span><span class="sxs-lookup"><span data-stu-id="8571d-142">Uses only the GAL to perform name resolution.</span></span> <span data-ttu-id="8571d-143">此标志仅受 Exchange 通讯簿提供程序支持。</span><span class="sxs-lookup"><span data-stu-id="8571d-143">This flag is supported only by the Exchange Address Book Provider.</span></span>
    
<span data-ttu-id="8571d-144">MAPI_MODIFY</span><span class="sxs-lookup"><span data-stu-id="8571d-144">MAPI_MODIFY</span></span>
  
> <span data-ttu-id="8571d-145">请求项打开的读取和写入权限。</span><span class="sxs-lookup"><span data-stu-id="8571d-145">Requests that the entry be opened with read and write permission.</span></span> <span data-ttu-id="8571d-146">因为条目具有只读访问权限打开默认情况下，客户端不应假定的读取和写入无论是否设置 MAPI_MODIFY 授予了权限。</span><span class="sxs-lookup"><span data-stu-id="8571d-146">Because entries are opened with read-only access by default, clients should not assume that read and write permission was granted regardless of whether MAPI_MODIFY is set.</span></span>
    
<span data-ttu-id="8571d-147">MAPI_NO_CACHE</span><span class="sxs-lookup"><span data-stu-id="8571d-147">MAPI_NO_CACHE</span></span>
  
> <span data-ttu-id="8571d-148">不使用脱机通讯簿执行名称解析。</span><span class="sxs-lookup"><span data-stu-id="8571d-148">Does not use the offline address book to perform name resolution.</span></span> <span data-ttu-id="8571d-149">此标志仅受 Exchange 通讯簿提供程序支持。</span><span class="sxs-lookup"><span data-stu-id="8571d-149">This flag is supported only by the Exchange Address Book Provider.</span></span>
    
 <span data-ttu-id="8571d-150">_lpulObjType_</span><span class="sxs-lookup"><span data-stu-id="8571d-150">_lpulObjType_</span></span>
  
> <span data-ttu-id="8571d-151">[输出]一个指向打开条目的类型。</span><span class="sxs-lookup"><span data-stu-id="8571d-151">[out] A pointer to the type of the opened entry.</span></span>
    
 <span data-ttu-id="8571d-152">_lppUnk_</span><span class="sxs-lookup"><span data-stu-id="8571d-152">_lppUnk_</span></span>
  
> <span data-ttu-id="8571d-153">[输出]指向打开的条目的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="8571d-153">[out] A pointer to a pointer of the opened entry.</span></span>
    

