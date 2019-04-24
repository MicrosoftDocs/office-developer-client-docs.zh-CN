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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32347773"
---
# <a name="hropenabentrywithresolvedrow"></a><span data-ttu-id="7273b-103">HrOpenABEntryWithResolvedRow</span><span class="sxs-lookup"><span data-stu-id="7273b-103">HrOpenABEntryWithResolvedRow</span></span>

  
  
<span data-ttu-id="7273b-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="7273b-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="7273b-105">执行与[HrOpenABEntryWithExchangeContext](hropenabentrywithexchangecontext.md)相同的功能, 只是它会自动从已解析的行中获取**emsabpUID**并打开**entryID**。</span><span class="sxs-lookup"><span data-stu-id="7273b-105">Performs the same function as [HrOpenABEntryWithExchangeContext](hropenabentrywithexchangecontext.md) except that it automatically gets the **emsabpUID** from the resolved row and opens the **entryID**.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="7273b-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="7273b-106">Header file:</span></span>  <br/> |<span data-ttu-id="7273b-107">abhelp</span><span class="sxs-lookup"><span data-stu-id="7273b-107">abhelp.h</span></span>  <br/> |
|<span data-ttu-id="7273b-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="7273b-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="7273b-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="7273b-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="7273b-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="7273b-110">Called by:</span></span>  <br/> |<span data-ttu-id="7273b-111">客户端应用程序和服务提供程序</span><span class="sxs-lookup"><span data-stu-id="7273b-111">Client applications and service providers</span></span>  <br/> |
   
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

## <a name="parameters"></a><span data-ttu-id="7273b-112">参数</span><span class="sxs-lookup"><span data-stu-id="7273b-112">Parameters</span></span>

 <span data-ttu-id="7273b-113">_prwResolved_</span><span class="sxs-lookup"><span data-stu-id="7273b-113">_prwResolved_</span></span>
  
> <span data-ttu-id="7273b-114">实时指向用于获取**emsabpUID**并打开**entryID**的已解析行的指针。</span><span class="sxs-lookup"><span data-stu-id="7273b-114">[in] A pointer to the resolved row that is used to get the **emsabpUID** and open the **entryID**.</span></span>
    
 <span data-ttu-id="7273b-115">_pAddrBook_</span><span class="sxs-lookup"><span data-stu-id="7273b-115">_pAddrBook_</span></span>
  
> <span data-ttu-id="7273b-116">实时用于打开条目标识符的通讯簿。</span><span class="sxs-lookup"><span data-stu-id="7273b-116">[in] The address book used to open the entry identifier.</span></span> <span data-ttu-id="7273b-117">它不能为 NULL。</span><span class="sxs-lookup"><span data-stu-id="7273b-117">It cannot be NULL.</span></span>
    
 <span data-ttu-id="7273b-118">_cbEntryID_</span><span class="sxs-lookup"><span data-stu-id="7273b-118">_cbEntryID_</span></span>
  
> <span data-ttu-id="7273b-119">实时由_lpEntryID_参数指定的条目标识符的字节数。</span><span class="sxs-lookup"><span data-stu-id="7273b-119">[in] The byte count of the entry identifier specified by the  _lpEntryID_ parameter.</span></span> 
    
 <span data-ttu-id="7273b-120">_lpEntryID_</span><span class="sxs-lookup"><span data-stu-id="7273b-120">_lpEntryID_</span></span>
  
>  <span data-ttu-id="7273b-121">实时指向表示要打开的通讯簿条目的条目标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="7273b-121">[in] A pointer to the entry identifier that represents the address book entry to open.</span></span> 
    
 <span data-ttu-id="7273b-122">_lpInterface_</span><span class="sxs-lookup"><span data-stu-id="7273b-122">_lpInterface_</span></span>
  
> <span data-ttu-id="7273b-123">实时指向用于访问打开项的接口的接口标识符 (IID) 的指针。</span><span class="sxs-lookup"><span data-stu-id="7273b-123">[in] A pointer to the interface identifier (IID) of the interface that is used to access the open entry.</span></span> <span data-ttu-id="7273b-124">传递 NULL 将返回对象的标准接口。</span><span class="sxs-lookup"><span data-stu-id="7273b-124">Passing NULL returns the standard interface of the object.</span></span> <span data-ttu-id="7273b-125">对于邮件用户, 标准接口为[IMailUser: IMAPIProp](imailuserimapiprop.md)。</span><span class="sxs-lookup"><span data-stu-id="7273b-125">For messaging users, the standard interface is [IMailUser : IMAPIProp](imailuserimapiprop.md).</span></span> <span data-ttu-id="7273b-126">对于通讯组列表, 它是[IDistList: IMAPIContainer](idistlistimapicontainer.md)和容器, 它是[IABContainer: IMAPIContainer](iabcontainerimapicontainer.md)。</span><span class="sxs-lookup"><span data-stu-id="7273b-126">For distribution lists, it is [IDistList : IMAPIContainer](idistlistimapicontainer.md)and for containers, it is [IABContainer : IMAPIContainer](iabcontainerimapicontainer.md).</span></span> <span data-ttu-id="7273b-127">呼叫者可将_lpInterface_设置为相应的标准接口或继承层次结构中的接口。</span><span class="sxs-lookup"><span data-stu-id="7273b-127">Callers can set  _lpInterface_ to the appropriate standard interface or an interface in the inheritance hierarchy.</span></span> 
    
 <span data-ttu-id="7273b-128">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="7273b-128">_ulFlags_</span></span>
  
> <span data-ttu-id="7273b-129">实时用于控制条目打开方式的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="7273b-129">[in] A bitmask of flags that controls how the entry is opened.</span></span> <span data-ttu-id="7273b-130">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="7273b-130">The following flags can be set:</span></span>
    
<span data-ttu-id="7273b-131">MAPI_BEST_ACCESS</span><span class="sxs-lookup"><span data-stu-id="7273b-131">MAPI_BEST_ACCESS</span></span>
  
> <span data-ttu-id="7273b-132">请求使用最大允许的网络和客户端权限打开条目。</span><span class="sxs-lookup"><span data-stu-id="7273b-132">Requests that the entry be opened with the maximum allowed network and client permissions.</span></span> <span data-ttu-id="7273b-133">例如, 如果客户端具有读取和写入权限, 则通讯簿提供程序将尝试打开具有读取和写入权限的条目。</span><span class="sxs-lookup"><span data-stu-id="7273b-133">For example, if the client has read and write permission, the address book provider attempts to open the entry with read and write permission.</span></span> <span data-ttu-id="7273b-134">客户端可以通过调用 open 项的[IMAPIProp:: GetProps](imapiprop-getprops.md)方法和检索 PR_ACCESS_LEVEL (PidTagAccessLevel) 属性来检索已授予的访问级别。</span><span class="sxs-lookup"><span data-stu-id="7273b-134">The client can retrieve the access level that was granted by calling the [IMAPIProp::GetProps](imapiprop-getprops.md) method of the open entry and retrieving the PR_ACCESS_LEVEL (PidTagAccessLevel) property.</span></span> 
    
<span data-ttu-id="7273b-135">MAPI_CACHE_ONLY</span><span class="sxs-lookup"><span data-stu-id="7273b-135">MAPI_CACHE_ONLY</span></span>
  
> <span data-ttu-id="7273b-136">仅使用脱机通讯簿执行名称解析。</span><span class="sxs-lookup"><span data-stu-id="7273b-136">Uses only the offline address book to perform name resolution.</span></span> <span data-ttu-id="7273b-137">例如, 可以使用此标志允许客户端应用程序在缓存 exchange 模式中打开全局地址列表 (GAL), 并从缓存中访问该通讯簿中的条目, 而无需在客户端和服务器之间创建流量。</span><span class="sxs-lookup"><span data-stu-id="7273b-137">For example, you can use this flag to allow a client application to open the global address list (GAL) in cached exchange mode and access an entry in that address book from the cache without creating traffic between the client and the server.</span></span> <span data-ttu-id="7273b-138">仅 Exchange 通讯簿提供程序支持此标志。</span><span class="sxs-lookup"><span data-stu-id="7273b-138">This flag is supported only by the Exchange Address Book Provider.</span></span>
    
<span data-ttu-id="7273b-139">MAPI_DEFERRED_ERRORS</span><span class="sxs-lookup"><span data-stu-id="7273b-139">MAPI_DEFERRED_ERRORS</span></span>
  
> <span data-ttu-id="7273b-140">允许调用成功 (可能在条目完全打开且可用之前), 这意味着随后对该条目的调用可能会返回错误。</span><span class="sxs-lookup"><span data-stu-id="7273b-140">Allows the call to succeed, potentially before the entry is fully open and available, implying that subsequent calls to the entry might return an error.</span></span>
    
<span data-ttu-id="7273b-141">MAPI_GAL_ONLY</span><span class="sxs-lookup"><span data-stu-id="7273b-141">MAPI_GAL_ONLY</span></span>
  
> <span data-ttu-id="7273b-142">仅使用 GAL 执行名称解析。</span><span class="sxs-lookup"><span data-stu-id="7273b-142">Uses only the GAL to perform name resolution.</span></span> <span data-ttu-id="7273b-143">仅 Exchange 通讯簿提供程序支持此标志。</span><span class="sxs-lookup"><span data-stu-id="7273b-143">This flag is supported only by the Exchange Address Book Provider.</span></span>
    
<span data-ttu-id="7273b-144">MAPI_MODIFY</span><span class="sxs-lookup"><span data-stu-id="7273b-144">MAPI_MODIFY</span></span>
  
> <span data-ttu-id="7273b-145">请求使用 "读取" 和 "写入" 权限打开条目。</span><span class="sxs-lookup"><span data-stu-id="7273b-145">Requests that the entry be opened with read and write permission.</span></span> <span data-ttu-id="7273b-146">由于默认情况下会打开具有只读访问权限的条目, 因此客户端不应假定已授予 "读取" 和 "写入" 权限, 而不管是否设置了 MAPI_MODIFY。</span><span class="sxs-lookup"><span data-stu-id="7273b-146">Because entries are opened with read-only access by default, clients should not assume that read and write permission was granted regardless of whether MAPI_MODIFY is set.</span></span>
    
<span data-ttu-id="7273b-147">MAPI_NO_CACHE</span><span class="sxs-lookup"><span data-stu-id="7273b-147">MAPI_NO_CACHE</span></span>
  
> <span data-ttu-id="7273b-148">不使用脱机通讯簿执行名称解析。</span><span class="sxs-lookup"><span data-stu-id="7273b-148">Does not use the offline address book to perform name resolution.</span></span> <span data-ttu-id="7273b-149">仅 Exchange 通讯簿提供程序支持此标志。</span><span class="sxs-lookup"><span data-stu-id="7273b-149">This flag is supported only by the Exchange Address Book Provider.</span></span>
    
 <span data-ttu-id="7273b-150">_lpulObjType_</span><span class="sxs-lookup"><span data-stu-id="7273b-150">_lpulObjType_</span></span>
  
> <span data-ttu-id="7273b-151">排除指向已打开条目的类型的指针。</span><span class="sxs-lookup"><span data-stu-id="7273b-151">[out] A pointer to the type of the opened entry.</span></span>
    
 <span data-ttu-id="7273b-152">_lppUnk_</span><span class="sxs-lookup"><span data-stu-id="7273b-152">_lppUnk_</span></span>
  
> <span data-ttu-id="7273b-153">排除指向已打开条目的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="7273b-153">[out] A pointer to a pointer of the opened entry.</span></span>
    

