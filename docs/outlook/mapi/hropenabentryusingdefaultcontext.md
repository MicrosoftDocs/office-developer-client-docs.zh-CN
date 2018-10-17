---
title: HrOpenABEntryUsingDefaultContext
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 17cba69b-2b25-4b99-99d9-ec68fb8a35b5
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 879ba4afe85e1f6db31bd829411689b2dad58ed9
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22565464"
---
# <a name="hropenabentryusingdefaultcontext"></a><span data-ttu-id="2d98b-103">HrOpenABEntryUsingDefaultContext</span><span class="sxs-lookup"><span data-stu-id="2d98b-103">HrOpenABEntryUsingDefaultContext</span></span>

  
  
<span data-ttu-id="2d98b-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="2d98b-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="2d98b-105">在于它使用旧**emsmdbUID**作为_pEmsmdbUID_参数，则执行[HrOpenABEntryWithExchangeContext](hropenabentrywithexchangecontext.md)相同的功能。</span><span class="sxs-lookup"><span data-stu-id="2d98b-105">Performs the same function as [HrOpenABEntryWithExchangeContext](hropenabentrywithexchangecontext.md) except that it uses the legacy **emsmdbUID** as the  _pEmsmdbUID_ parameter.</span></span> <span data-ttu-id="2d98b-106">除非您无法获得[HrOpenABEntryWithExchangeContext](hropenabentrywithexchangecontext.md)调用正确**emsmdbUID**不使用此函数。</span><span class="sxs-lookup"><span data-stu-id="2d98b-106">Do not use this function unless you cannot obtain the correct **emsmdbUID** for the call to [HrOpenABEntryWithExchangeContext](hropenabentrywithexchangecontext.md).</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="2d98b-107">头文件：</span><span class="sxs-lookup"><span data-stu-id="2d98b-107">Header file:</span></span>  <br/> |<span data-ttu-id="2d98b-108">abhelp.h</span><span class="sxs-lookup"><span data-stu-id="2d98b-108">abhelp.h</span></span>  <br/> |
|<span data-ttu-id="2d98b-109">通过实现：</span><span class="sxs-lookup"><span data-stu-id="2d98b-109">Implemented by:</span></span>  <br/> |<span data-ttu-id="2d98b-110">MAPI</span><span class="sxs-lookup"><span data-stu-id="2d98b-110">MAPI</span></span>  <br/> |
|<span data-ttu-id="2d98b-111">调用：</span><span class="sxs-lookup"><span data-stu-id="2d98b-111">Called by:</span></span>  <br/> |<span data-ttu-id="2d98b-112">客户端应用程序和服务提供商</span><span class="sxs-lookup"><span data-stu-id="2d98b-112">Client applications and service providers</span></span>  <br/> |
   
```cpp
HRESULT HrOpenABEntryUsingDefaultContext(
  LPMAPISESSION pmsess,
  LPADRBOOK pAddrBook,
  ULONG cbEntryID,
  LPENTRYID lpEntryID,
  LPCIID lpInterface,
  ULONG ulFlags,
  ULONG FAR * lpulObjType,
  LPUNKNOWN FAR * lppUnk
);
```

## <a name="parameters"></a><span data-ttu-id="2d98b-113">参数</span><span class="sxs-lookup"><span data-stu-id="2d98b-113">Parameters</span></span>

 <span data-ttu-id="2d98b-114">_pmsess_</span><span class="sxs-lookup"><span data-stu-id="2d98b-114">_pmsess_</span></span>
  
> <span data-ttu-id="2d98b-115">[in]登录**IMAPISession**。</span><span class="sxs-lookup"><span data-stu-id="2d98b-115">[in] The logged on **IMAPISession**.</span></span> <span data-ttu-id="2d98b-116">它不能为 NULL。</span><span class="sxs-lookup"><span data-stu-id="2d98b-116">It cannot be NULL.</span></span>
    
 <span data-ttu-id="2d98b-117">_pAddrBook_</span><span class="sxs-lookup"><span data-stu-id="2d98b-117">_pAddrBook_</span></span>
  
> <span data-ttu-id="2d98b-118">[in]通讯簿用于打开的项标识符。</span><span class="sxs-lookup"><span data-stu-id="2d98b-118">[in] The address book used to open the entry identifier.</span></span> <span data-ttu-id="2d98b-119">它不能为 NULL。</span><span class="sxs-lookup"><span data-stu-id="2d98b-119">It cannot be NULL.</span></span>
    
 <span data-ttu-id="2d98b-120">_cbEntryID_</span><span class="sxs-lookup"><span data-stu-id="2d98b-120">_cbEntryID_</span></span>
  
> <span data-ttu-id="2d98b-121">[in]_LpEntryID_参数指定的项标识符的字节数。</span><span class="sxs-lookup"><span data-stu-id="2d98b-121">[in] The byte count of the entry identifier specified by the  _lpEntryID_ parameter.</span></span> 
    
 <span data-ttu-id="2d98b-122">_lpEntryID_</span><span class="sxs-lookup"><span data-stu-id="2d98b-122">_lpEntryID_</span></span>
  
>  <span data-ttu-id="2d98b-123">[in]一个指向代表打开的通讯簿条目的项标识符。</span><span class="sxs-lookup"><span data-stu-id="2d98b-123">[in] A pointer to the entry identifier that represents the address book entry to open.</span></span> 
    
 <span data-ttu-id="2d98b-124">_lpInterface_</span><span class="sxs-lookup"><span data-stu-id="2d98b-124">_lpInterface_</span></span>
  
> <span data-ttu-id="2d98b-125">[in]指向用于访问打开条目的接口的接口标识符 (IID) 的指针。</span><span class="sxs-lookup"><span data-stu-id="2d98b-125">[in] A pointer to the interface identifier (IID) of the interface that is used to access the open entry.</span></span> <span data-ttu-id="2d98b-126">传递 NULL 将返回标准接口的对象。</span><span class="sxs-lookup"><span data-stu-id="2d98b-126">Passing NULL returns the standard interface of the object.</span></span> <span data-ttu-id="2d98b-127">对于邮件用户，标准接口是[IMailUser: IMAPIProp](imailuserimapiprop.md)。</span><span class="sxs-lookup"><span data-stu-id="2d98b-127">For messaging users, the standard interface is [IMailUser : IMAPIProp](imailuserimapiprop.md).</span></span> <span data-ttu-id="2d98b-128">对于通讯组列表它是[IDistList: IMAPIContainer](idistlistimapicontainer.md)，以及是的容器[IABContainer: IMAPIContainer](iabcontainerimapicontainer.md)。</span><span class="sxs-lookup"><span data-stu-id="2d98b-128">For distribution lists it is [IDistList : IMAPIContainer](idistlistimapicontainer.md), and for containers it is [IABContainer : IMAPIContainer](iabcontainerimapicontainer.md).</span></span> <span data-ttu-id="2d98b-129">呼叫者可以设置_lpInterface_为相应的标准接口或继承层次结构中的接口。</span><span class="sxs-lookup"><span data-stu-id="2d98b-129">Callers can set  _lpInterface_ to the appropriate standard interface or an interface in the inheritance hierarchy.</span></span> 
    
 <span data-ttu-id="2d98b-130">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="2d98b-130">_ulFlags_</span></span>
  
> <span data-ttu-id="2d98b-131">[in]位掩码的标志，控制如何打开该条目。</span><span class="sxs-lookup"><span data-stu-id="2d98b-131">[in] A bitmask of flags that controls how the entry is opened.</span></span> <span data-ttu-id="2d98b-132">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="2d98b-132">The following flags can be set:</span></span>
    
<span data-ttu-id="2d98b-133">MAPI_BEST_ACCESS</span><span class="sxs-lookup"><span data-stu-id="2d98b-133">MAPI_BEST_ACCESS</span></span>
  
> <span data-ttu-id="2d98b-134">与最大允许网络和客户端权限打开的条目的请求。</span><span class="sxs-lookup"><span data-stu-id="2d98b-134">Requests that the entry be opened with the maximum allowed network and client permissions.</span></span> <span data-ttu-id="2d98b-135">例如，如果客户端具有读取和写入权限，通讯簿提供程序尝试打开条目具有读取和写入权限。</span><span class="sxs-lookup"><span data-stu-id="2d98b-135">For example, if the client has read and write permission, the address book provider attempts to open the entry with read and write permission.</span></span> <span data-ttu-id="2d98b-136">客户端可以检索通过调用打开条目的[IMAPIProp::GetProps](imapiprop-getprops.md)方法并检索 PR_ACCESS_LEVEL (PidTagAccessLevel) 属性授予的访问级别。</span><span class="sxs-lookup"><span data-stu-id="2d98b-136">The client can retrieve the access level that was granted by calling the [IMAPIProp::GetProps](imapiprop-getprops.md) method of the open entry and retrieving the PR_ACCESS_LEVEL (PidTagAccessLevel) property.</span></span> 
    
<span data-ttu-id="2d98b-137">MAPI_CACHE_ONLY</span><span class="sxs-lookup"><span data-stu-id="2d98b-137">MAPI_CACHE_ONLY</span></span>
  
> <span data-ttu-id="2d98b-138">使用仅脱机通讯簿执行名称解析。</span><span class="sxs-lookup"><span data-stu-id="2d98b-138">Uses only the offline address book to perform name resolution.</span></span> <span data-ttu-id="2d98b-139">例如，您可以使用此标志以允许将客户端应用程序在缓存的 exchange 模式下打开全局地址列表 (GAL)，而不创建客户端和服务器之间的流量从缓存中访问该通讯簿中的条目。</span><span class="sxs-lookup"><span data-stu-id="2d98b-139">For example, you can use this flag to allow a client application to open the global address list (GAL) in cached exchange mode and access an entry in that address book from the cache without creating traffic between the client and the server.</span></span> <span data-ttu-id="2d98b-140">此标志仅受 Exchange 通讯簿提供程序支持。</span><span class="sxs-lookup"><span data-stu-id="2d98b-140">This flag is supported only by the Exchange address book provider.</span></span>
    
<span data-ttu-id="2d98b-141">MAPI_DEFERRED_ERRORS</span><span class="sxs-lookup"><span data-stu-id="2d98b-141">MAPI_DEFERRED_ERRORS</span></span>
  
> <span data-ttu-id="2d98b-142">允许的调用成功，可能之前该条目是完全打开且可用，这意味着该条目的后面对会返回一个错误。</span><span class="sxs-lookup"><span data-stu-id="2d98b-142">Allows the call to succeed, potentially before the entry is fully open and available, implying that subsequent calls to the entry might return an error.</span></span>
    
<span data-ttu-id="2d98b-143">MAPI_GAL_ONLY</span><span class="sxs-lookup"><span data-stu-id="2d98b-143">MAPI_GAL_ONLY</span></span>
  
> <span data-ttu-id="2d98b-144">使用仅 GAL 执行名称解析。</span><span class="sxs-lookup"><span data-stu-id="2d98b-144">Uses only the GAL to perform name resolution.</span></span> <span data-ttu-id="2d98b-145">此标志仅受 Exchange 通讯簿提供程序支持。</span><span class="sxs-lookup"><span data-stu-id="2d98b-145">This flag is supported only by the Exchange address book provider.</span></span>
    
<span data-ttu-id="2d98b-146">MAPI_MODIFY</span><span class="sxs-lookup"><span data-stu-id="2d98b-146">MAPI_MODIFY</span></span>
  
> <span data-ttu-id="2d98b-147">请求项打开的读取和写入权限。</span><span class="sxs-lookup"><span data-stu-id="2d98b-147">Requests that the entry be opened with read and write permission.</span></span> <span data-ttu-id="2d98b-148">因为条目具有只读访问权限打开默认情况下，客户端不应假定的读取和写入无论是否设置 MAPI_MODIFY 授予了权限。</span><span class="sxs-lookup"><span data-stu-id="2d98b-148">Because entries are opened with read-only access by default, clients should not assume that read and write permission was granted regardless of whether MAPI_MODIFY is set.</span></span>
    
<span data-ttu-id="2d98b-149">MAPI_NO_CACHE</span><span class="sxs-lookup"><span data-stu-id="2d98b-149">MAPI_NO_CACHE</span></span>
  
> <span data-ttu-id="2d98b-150">不使用脱机通讯簿执行名称解析。</span><span class="sxs-lookup"><span data-stu-id="2d98b-150">Does not use the offline address book to perform name resolution.</span></span> <span data-ttu-id="2d98b-151">此标志仅受 Exchange 通讯簿提供程序支持。</span><span class="sxs-lookup"><span data-stu-id="2d98b-151">This flag is supported only by the Exchange address book provider.</span></span>
    
 <span data-ttu-id="2d98b-152">_lpulObjType_</span><span class="sxs-lookup"><span data-stu-id="2d98b-152">_lpulObjType_</span></span>
  
> <span data-ttu-id="2d98b-153">[输出]一个指向打开条目的类型。</span><span class="sxs-lookup"><span data-stu-id="2d98b-153">[out] A pointer to the type of the opened entry.</span></span>
    
 <span data-ttu-id="2d98b-154">_lppUnk_</span><span class="sxs-lookup"><span data-stu-id="2d98b-154">_lppUnk_</span></span>
  
> <span data-ttu-id="2d98b-155">[输出]指向打开的条目的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="2d98b-155">[out] A pointer to a pointer of the opened entry.</span></span>
    
