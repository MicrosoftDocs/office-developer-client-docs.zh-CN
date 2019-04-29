---
title: IAddrBookOpenEntry
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IAddrBook.OpenEntry
api_type:
- COM
ms.assetid: bd7746f4-8070-4cc5-8b8e-c527c5847545
description: 上次修改时间：2013 年 2 月 1 日
ms.openlocfilehash: 293fe5a65c760f61ab0073e0eafc1a606c69050f
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33434163"
---
# <a name="iaddrbookopenentry"></a><span data-ttu-id="47f72-103">IAddrBook::OpenEntry</span><span class="sxs-lookup"><span data-stu-id="47f72-103">IAddrBook::OpenEntry</span></span>

<span data-ttu-id="47f72-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="47f72-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="47f72-105">打开通讯簿条目并返回指向可用于访问该条目的接口的指针。</span><span class="sxs-lookup"><span data-stu-id="47f72-105">Opens an address book entry and returns a pointer to an interface that can be used to access the entry.</span></span>
  
```cpp
HRESULT OpenEntry(
  ULONG cbEntryID,
  LPENTRYID lpEntryID,
  LPCIID lpInterface,
  ULONG ulFlags,
  ULONG FAR * lpulObjType,
  LPUNKNOWN FAR * lppUnk
);
```

## <a name="parameters"></a><span data-ttu-id="47f72-106">参数</span><span class="sxs-lookup"><span data-stu-id="47f72-106">Parameters</span></span>

<span data-ttu-id="47f72-107">_cbEntryID_</span><span class="sxs-lookup"><span data-stu-id="47f72-107">_cbEntryID_</span></span>
  
> <span data-ttu-id="47f72-108">实时条目标识符中由_lpEntryID_参数指向的字节数。</span><span class="sxs-lookup"><span data-stu-id="47f72-108">[in] The byte count in the entry identifier pointed to by the  _lpEntryID_ parameter.</span></span> 
    
<span data-ttu-id="47f72-109">_lpEntryID_</span><span class="sxs-lookup"><span data-stu-id="47f72-109">_lpEntryID_</span></span>
  
> <span data-ttu-id="47f72-110">实时指向表示要打开的通讯簿条目的条目标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="47f72-110">[in] A pointer to the entry identifier that represents the address book entry to open.</span></span>
    
<span data-ttu-id="47f72-111">_lpInterface_</span><span class="sxs-lookup"><span data-stu-id="47f72-111">_lpInterface_</span></span>
  
> <span data-ttu-id="47f72-112">实时指向接口标识符 (IID) 的指针, 该接口用于访问打开的条目。</span><span class="sxs-lookup"><span data-stu-id="47f72-112">[in] A pointer to the interface identifier (IID) of the interface to be used to access the open entry.</span></span> <span data-ttu-id="47f72-113">传递 NULL 将返回对象的标准接口。</span><span class="sxs-lookup"><span data-stu-id="47f72-113">Passing NULL returns the object's standard interface.</span></span> <span data-ttu-id="47f72-114">对于邮件用户, 标准接口为[IMailUser: IMAPIProp](imailuserimapiprop.md)。</span><span class="sxs-lookup"><span data-stu-id="47f72-114">For messaging users, the standard interface is [IMailUser : IMAPIProp](imailuserimapiprop.md).</span></span> <span data-ttu-id="47f72-115">对于通讯组列表, 它是[IDistList: IMAPIContainer](idistlistimapicontainer.md)和容器, 它是[IABContainer: IMAPIContainer](iabcontainerimapicontainer.md)。</span><span class="sxs-lookup"><span data-stu-id="47f72-115">For distribution lists, it is [IDistList : IMAPIContainer](idistlistimapicontainer.md) and for containers, it is [IABContainer : IMAPIContainer](iabcontainerimapicontainer.md).</span></span> <span data-ttu-id="47f72-116">呼叫者可将_lpInterface_设置为相应的标准接口或继承层次结构中的接口。</span><span class="sxs-lookup"><span data-stu-id="47f72-116">Callers can set  _lpInterface_ to the appropriate standard interface or an interface in the inheritance hierarchy.</span></span> 
    
<span data-ttu-id="47f72-117">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="47f72-117">_ulFlags_</span></span>
  
> <span data-ttu-id="47f72-118">实时用于控制条目打开方式的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="47f72-118">[in] A bitmask of flags that controls how the entry is opened.</span></span> <span data-ttu-id="47f72-119">可以设置以下标志。</span><span class="sxs-lookup"><span data-stu-id="47f72-119">The following flags can be set.</span></span>
    
<span data-ttu-id="47f72-120">MAPI_BEST_ACCESS</span><span class="sxs-lookup"><span data-stu-id="47f72-120">MAPI_BEST_ACCESS</span></span> 
  
> <span data-ttu-id="47f72-121">请求使用最大允许的网络和客户端权限打开条目。</span><span class="sxs-lookup"><span data-stu-id="47f72-121">Requests that the entry be opened with the maximum allowed network and client permissions.</span></span> <span data-ttu-id="47f72-122">例如, 如果客户端具有读/写权限, 则通讯簿提供程序应尝试打开具有读/写权限的条目。</span><span class="sxs-lookup"><span data-stu-id="47f72-122">For example, if the client has read/write permission, the address book provider should attempt to open the entry with read/write permission.</span></span> <span data-ttu-id="47f72-123">客户端可以通过调用 open 项的[IMAPIProp:: GetProps](imapiprop-getprops.md)方法和检索**PR_ACCESS_LEVEL** ([PidTagAccessLevel](pidtagaccesslevel-canonical-property.md)) 属性来检索已授予的访问级别。</span><span class="sxs-lookup"><span data-stu-id="47f72-123">The client can retrieve the access level that was granted by calling the open entry's [IMAPIProp::GetProps](imapiprop-getprops.md) method and retrieving the **PR_ACCESS_LEVEL** ([PidTagAccessLevel](pidtagaccesslevel-canonical-property.md)) property.</span></span>
    
<span data-ttu-id="47f72-124">MAPI_CACHE_ONLY</span><span class="sxs-lookup"><span data-stu-id="47f72-124">MAPI_CACHE_ONLY</span></span>
  
> <span data-ttu-id="47f72-125">打开通讯簿条目并仅从缓存访问。</span><span class="sxs-lookup"><span data-stu-id="47f72-125">Opens an address book entry and accesses it only from the cache.</span></span> <span data-ttu-id="47f72-126">例如, 可以使用此标志允许客户端应用程序在缓存 exchange 模式中打开全局地址列表 (GAL), 并从缓存中访问该通讯簿中的条目, 而无需在客户端和服务器之间创建流量。</span><span class="sxs-lookup"><span data-stu-id="47f72-126">For example, you can use this flag to allow a client application to open the global address list (GAL) in cached exchange mode and access an entry in that address book from the cache without creating traffic between the client and the server.</span></span> <span data-ttu-id="47f72-127">仅 Exchange 通讯簿提供程序支持此标志。</span><span class="sxs-lookup"><span data-stu-id="47f72-127">This flag is supported only by the Exchange address book provider.</span></span>
    
<span data-ttu-id="47f72-128">MAPI_DEFERRED_ERRORS</span><span class="sxs-lookup"><span data-stu-id="47f72-128">MAPI_DEFERRED_ERRORS</span></span> 
  
> <span data-ttu-id="47f72-129">允许调用成功 (可能是在条目完全打开且可用之前), 这意味着稍后对该条目的调用可能会返回错误。</span><span class="sxs-lookup"><span data-stu-id="47f72-129">Allows the call to succeed, potentially before the entry is fully open and available, implying that later calls to the entry might return an error.</span></span>
    
<span data-ttu-id="47f72-130">MAPI_GAL_ONLY</span><span class="sxs-lookup"><span data-stu-id="47f72-130">MAPI_GAL_ONLY</span></span>
  
> <span data-ttu-id="47f72-131">仅使用 GAL 执行名称解析。</span><span class="sxs-lookup"><span data-stu-id="47f72-131">Use only the GAL to perform name resolution.</span></span> <span data-ttu-id="47f72-132">仅 Exchange 通讯簿提供程序支持此标志。</span><span class="sxs-lookup"><span data-stu-id="47f72-132">This flag is supported only by the Exchange Address Book Provider.</span></span>
    
  > [!NOTE]
  > <span data-ttu-id="47f72-133">_ulFlags_ MAPI_GAL_ONLY 可能未在您当前拥有的可下载头文件中定义, 在这种情况下, 您可以使用以下值将其添加到代码中: >`#define MAPI_GAL_ONLY (0x00000080)`</span><span class="sxs-lookup"><span data-stu-id="47f72-133">The  _ulFlags_ MAPI_GAL_ONLY might not be defined in the downloadable header file you currently have, in which case you can add it to your code using the following value: >  `#define MAPI_GAL_ONLY (0x00000080)`</span></span>
  
<span data-ttu-id="47f72-134">MAPI_MODIFY</span><span class="sxs-lookup"><span data-stu-id="47f72-134">MAPI_MODIFY</span></span> 
  
> <span data-ttu-id="47f72-135">请求以读/写权限打开条目。</span><span class="sxs-lookup"><span data-stu-id="47f72-135">Requests that the entry be opened with read/write permission.</span></span> <span data-ttu-id="47f72-136">由于默认情况下会打开具有只读访问权限的条目, 因此客户端不应假定已授予读/写权限, 而不管是否设置了 MAPI_MODIFY。</span><span class="sxs-lookup"><span data-stu-id="47f72-136">Because entries are opened with read-only access by default, clients should not assume that read/write permission was granted regardless of whether MAPI_MODIFY is set.</span></span>
    
<span data-ttu-id="47f72-137">MAPI_NO_CACHE</span><span class="sxs-lookup"><span data-stu-id="47f72-137">MAPI_NO_CACHE</span></span>
  
> <span data-ttu-id="47f72-138">请勿使用脱机通讯簿执行名称解析。</span><span class="sxs-lookup"><span data-stu-id="47f72-138">Do not use the offline address book to perform name resolution.</span></span> <span data-ttu-id="47f72-139">仅 Exchange 通讯簿提供程序支持此标志。</span><span class="sxs-lookup"><span data-stu-id="47f72-139">This flag is supported only by the Exchange Address Book Provider.</span></span>
    
<span data-ttu-id="47f72-140">_lpulObjType_</span><span class="sxs-lookup"><span data-stu-id="47f72-140">_lpulObjType_</span></span>
  
> <span data-ttu-id="47f72-141">排除指向已打开条目的类型的指针。</span><span class="sxs-lookup"><span data-stu-id="47f72-141">[out] A pointer to the type of the opened entry.</span></span>
    
<span data-ttu-id="47f72-142">_lppUnk_</span><span class="sxs-lookup"><span data-stu-id="47f72-142">_lppUnk_</span></span>
  
> <span data-ttu-id="47f72-143">排除指向打开的项的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="47f72-143">[out] A pointer to a pointer to the opened entry.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="47f72-144">返回值</span><span class="sxs-lookup"><span data-stu-id="47f72-144">Return value</span></span>

<span data-ttu-id="47f72-145">S_OK</span><span class="sxs-lookup"><span data-stu-id="47f72-145">S_OK</span></span> 
  
> <span data-ttu-id="47f72-146">已成功打开条目。</span><span class="sxs-lookup"><span data-stu-id="47f72-146">The entry was successfully opened.</span></span>
    
<span data-ttu-id="47f72-147">MAPI_E_NO_ACCESS</span><span class="sxs-lookup"><span data-stu-id="47f72-147">MAPI_E_NO_ACCESS</span></span> 
  
> <span data-ttu-id="47f72-148">试图打开用户没有足够权限的条目。</span><span class="sxs-lookup"><span data-stu-id="47f72-148">An attempt was made to open an entry for which the user has insufficient permissions.</span></span>
    
<span data-ttu-id="47f72-149">MAPI_E_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="47f72-149">MAPI_E_NOT_FOUND</span></span> 
  
> <span data-ttu-id="47f72-150">_lpEntryID_所代表的条目不存在。</span><span class="sxs-lookup"><span data-stu-id="47f72-150">The entry represented by  _lpEntryID_ does not exist.</span></span> 
    
<span data-ttu-id="47f72-151">MAPI_E_UNKNOWN_ENTRYID</span><span class="sxs-lookup"><span data-stu-id="47f72-151">MAPI_E_UNKNOWN_ENTRYID</span></span> 
  
> <span data-ttu-id="47f72-152">无法识别_lpEntryID_中指定的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="47f72-152">The entry identifier specified in  _lpEntryID_ is not recognized.</span></span> <span data-ttu-id="47f72-153">如果负责相应条目的通讯簿提供程序未打开, 则通常会返回此值。</span><span class="sxs-lookup"><span data-stu-id="47f72-153">This value is typically returned if the address book provider responsible for the corresponding entry is not open.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="47f72-154">说明</span><span class="sxs-lookup"><span data-stu-id="47f72-154">Remarks</span></span>

<span data-ttu-id="47f72-155">客户端和服务提供程序调用**IAddrBook:: OpenEntry**方法以打开通讯簿条目。</span><span class="sxs-lookup"><span data-stu-id="47f72-155">Clients and service providers call the **IAddrBook::OpenEntry** method to open an address book entry.</span></span> <span data-ttu-id="47f72-156">MAPI 将根据在_lpEntryID_参数中传递的条目标识符中包含的[MAPIUID](mapiuid.md)结构, 将呼叫转发到相应的通讯簿提供程序。</span><span class="sxs-lookup"><span data-stu-id="47f72-156">MAPI forwards the call to the appropriate address book provider, based on the [MAPIUID](mapiuid.md) structure included in the entry identifier passed in the  _lpEntryID_ parameter.</span></span> <span data-ttu-id="47f72-157">除非设置了_ulFlags_参数中的 MAPI_MODIFY 或 MAPI_BEST_ACCESS 标志, 否则通讯簿提供程序将以只读方式打开该条目。</span><span class="sxs-lookup"><span data-stu-id="47f72-157">The address book provider opens the entry as read-only unless the MAPI_MODIFY or MAPI_BEST_ACCESS flag in the  _ulFlags_ parameter is set.</span></span> <span data-ttu-id="47f72-158">但是, 这些标志是建议的。</span><span class="sxs-lookup"><span data-stu-id="47f72-158">However, these flags are suggestions.</span></span> <span data-ttu-id="47f72-159">如果通讯簿提供程序不允许对所请求的条目进行修改, 则返回 MAPI_E_NO_ACCESS。</span><span class="sxs-lookup"><span data-stu-id="47f72-159">If the address book provider does not allow modification for the entry requested, it returns MAPI_E_NO_ACCESS.</span></span> 
  
<span data-ttu-id="47f72-160">_lpInterface_参数指示应使用哪个接口来访问打开的条目。</span><span class="sxs-lookup"><span data-stu-id="47f72-160">The  _lpInterface_ parameter indicates which interface should be used to access the opened entry.</span></span> <span data-ttu-id="47f72-161">在_lpInterface_中传递 NULL 表示应使用该类型条目的标准 MAPI 接口。</span><span class="sxs-lookup"><span data-stu-id="47f72-161">Passing NULL in  _lpInterface_ indicates the standard MAPI interface for that type of entry should be used.</span></span> <span data-ttu-id="47f72-162">由于通讯簿提供程序可能返回一个与_lpInterface_参数所建议的接口不同的接口, 因此调用方应检查_lpulObjType_参数中返回的值, 以确定返回的对象类型是否为预期的内容。</span><span class="sxs-lookup"><span data-stu-id="47f72-162">Because the address book provider might return a different interface than the one suggested by the  _lpInterface_ parameter, the caller should check the value returned in the  _lpulObjType_ parameter to determine whether the object type returned is what was expected.</span></span> <span data-ttu-id="47f72-163">如果对象类型不是预期的类型, 则调用方可以将_lppUnk_参数转换为更合适的类型。</span><span class="sxs-lookup"><span data-stu-id="47f72-163">If the object type is not of the type expected, the caller can cast the  _lppUnk_ parameter to a type that is more appropriate.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="47f72-164">另请参阅</span><span class="sxs-lookup"><span data-stu-id="47f72-164">See also</span></span>

- [<span data-ttu-id="47f72-165">IAddrBook : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="47f72-165">IAddrBook : IMAPIProp</span></span>](iaddrbookimapiprop.md)

