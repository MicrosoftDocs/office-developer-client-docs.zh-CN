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
description: 上次修改时间： 2013 年 2 月 1 日
ms.openlocfilehash: fa279962043f6f7cb7a134b624000c9c7e65369f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775263"
---
# <a name="iaddrbookopenentry"></a><span data-ttu-id="a8ffa-103">IAddrBook::OpenEntry</span><span class="sxs-lookup"><span data-stu-id="a8ffa-103">IAddrBook::OpenEntry</span></span>

<span data-ttu-id="a8ffa-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="a8ffa-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="a8ffa-105">打开的通讯簿条目，并返回可用于访问该条目的接口的指针。</span><span class="sxs-lookup"><span data-stu-id="a8ffa-105">Opens an address book entry and returns a pointer to an interface that can be used to access the entry.</span></span>
  
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

## <a name="parameters"></a><span data-ttu-id="a8ffa-106">参数</span><span class="sxs-lookup"><span data-stu-id="a8ffa-106">Parameters</span></span>

<span data-ttu-id="a8ffa-107">_cbEntryID_</span><span class="sxs-lookup"><span data-stu-id="a8ffa-107">_cbEntryID_</span></span>
  
> <span data-ttu-id="a8ffa-108">[in]在_lpEntryID_参数指向的项标识符的字节数。</span><span class="sxs-lookup"><span data-stu-id="a8ffa-108">[in] The byte count in the entry identifier pointed to by the  _lpEntryID_ parameter.</span></span> 
    
<span data-ttu-id="a8ffa-109">_lpEntryID_</span><span class="sxs-lookup"><span data-stu-id="a8ffa-109">_lpEntryID_</span></span>
  
> <span data-ttu-id="a8ffa-110">[in]一个指向代表打开的通讯簿条目的项标识符。</span><span class="sxs-lookup"><span data-stu-id="a8ffa-110">[in] A pointer to the entry identifier that represents the address book entry to open.</span></span>
    
<span data-ttu-id="a8ffa-111">_lpInterface_</span><span class="sxs-lookup"><span data-stu-id="a8ffa-111">_lpInterface_</span></span>
  
> <span data-ttu-id="a8ffa-112">[in]指向要用于访问打开条目的接口的接口标识符 (IID) 的指针。</span><span class="sxs-lookup"><span data-stu-id="a8ffa-112">[in] A pointer to the interface identifier (IID) of the interface to be used to access the open entry.</span></span> <span data-ttu-id="a8ffa-113">如果传递 NULL 返回对象的标准接口。</span><span class="sxs-lookup"><span data-stu-id="a8ffa-113">Passing NULL returns the object's standard interface.</span></span> <span data-ttu-id="a8ffa-114">对于邮件用户，标准接口是[IMailUser: IMAPIProp](imailuserimapiprop.md)。</span><span class="sxs-lookup"><span data-stu-id="a8ffa-114">For messaging users, the standard interface is [IMailUser : IMAPIProp](imailuserimapiprop.md).</span></span> <span data-ttu-id="a8ffa-115">对于通讯组列表，它是[IDistList: IMAPIContainer](idistlistimapicontainer.md)而容器，则为： [IABContainer: IMAPIContainer](iabcontainerimapicontainer.md)。</span><span class="sxs-lookup"><span data-stu-id="a8ffa-115">For distribution lists, it is [IDistList : IMAPIContainer](idistlistimapicontainer.md) and for containers, it is [IABContainer : IMAPIContainer](iabcontainerimapicontainer.md).</span></span> <span data-ttu-id="a8ffa-116">呼叫者可以设置_lpInterface_为相应的标准接口或继承层次结构中的接口。</span><span class="sxs-lookup"><span data-stu-id="a8ffa-116">Callers can set  _lpInterface_ to the appropriate standard interface or an interface in the inheritance hierarchy.</span></span> 
    
<span data-ttu-id="a8ffa-117">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="a8ffa-117">_ulFlags_</span></span>
  
> <span data-ttu-id="a8ffa-118">[in]位掩码的标志，控制如何打开该条目。</span><span class="sxs-lookup"><span data-stu-id="a8ffa-118">[in] A bitmask of flags that controls how the entry is opened.</span></span> <span data-ttu-id="a8ffa-119">可以设置以下标志。</span><span class="sxs-lookup"><span data-stu-id="a8ffa-119">The following flags can be set.</span></span>
    
<span data-ttu-id="a8ffa-120">MAPI_BEST_ACCESS</span><span class="sxs-lookup"><span data-stu-id="a8ffa-120">MAPI_BEST_ACCESS</span></span> 
  
> <span data-ttu-id="a8ffa-121">与最大允许网络和客户端权限打开的条目的请求。</span><span class="sxs-lookup"><span data-stu-id="a8ffa-121">Requests that the entry be opened with the maximum allowed network and client permissions.</span></span> <span data-ttu-id="a8ffa-122">例如，如果客户端具有读/写权限，通讯簿提供程序应尝试打开具有读/写权限条目。</span><span class="sxs-lookup"><span data-stu-id="a8ffa-122">For example, if the client has read/write permission, the address book provider should attempt to open the entry with read/write permission.</span></span> <span data-ttu-id="a8ffa-123">客户端可以检索通过调用打开条目的[IMAPIProp::GetProps](imapiprop-getprops.md)方法并检索**PR_ACCESS_LEVEL** ([PidTagAccessLevel](pidtagaccesslevel-canonical-property.md)) 属性授予的访问级别。</span><span class="sxs-lookup"><span data-stu-id="a8ffa-123">The client can retrieve the access level that was granted by calling the open entry's [IMAPIProp::GetProps](imapiprop-getprops.md) method and retrieving the **PR_ACCESS_LEVEL** ([PidTagAccessLevel](pidtagaccesslevel-canonical-property.md)) property.</span></span>
    
<span data-ttu-id="a8ffa-124">MAPI_CACHE_ONLY</span><span class="sxs-lookup"><span data-stu-id="a8ffa-124">MAPI_CACHE_ONLY</span></span>
  
> <span data-ttu-id="a8ffa-125">打开的通讯簿条目，并访问仅从缓存。</span><span class="sxs-lookup"><span data-stu-id="a8ffa-125">Opens an address book entry and accesses it only from the cache.</span></span> <span data-ttu-id="a8ffa-126">例如，您可以使用此标志以允许将客户端应用程序在缓存的 exchange 模式下打开全局地址列表 (GAL)，而不创建客户端和服务器之间的流量从缓存中访问该通讯簿中的条目。</span><span class="sxs-lookup"><span data-stu-id="a8ffa-126">For example, you can use this flag to allow a client application to open the global address list (GAL) in cached exchange mode and access an entry in that address book from the cache without creating traffic between the client and the server.</span></span> <span data-ttu-id="a8ffa-127">此标志仅受 Exchange 通讯簿提供程序支持。</span><span class="sxs-lookup"><span data-stu-id="a8ffa-127">This flag is supported only by the Exchange address book provider.</span></span>
    
<span data-ttu-id="a8ffa-128">MAPI_DEFERRED_ERRORS</span><span class="sxs-lookup"><span data-stu-id="a8ffa-128">MAPI_DEFERRED_ERRORS</span></span> 
  
> <span data-ttu-id="a8ffa-129">允许的调用成功，可能之前该条目是完全打开且可用，这意味着更高版本调用条目可能会返回错误。</span><span class="sxs-lookup"><span data-stu-id="a8ffa-129">Allows the call to succeed, potentially before the entry is fully open and available, implying that later calls to the entry might return an error.</span></span>
    
<span data-ttu-id="a8ffa-130">MAPI_GAL_ONLY</span><span class="sxs-lookup"><span data-stu-id="a8ffa-130">MAPI_GAL_ONLY</span></span>
  
> <span data-ttu-id="a8ffa-131">使用仅 GAL 执行名称解析。</span><span class="sxs-lookup"><span data-stu-id="a8ffa-131">Use only the GAL to perform name resolution.</span></span> <span data-ttu-id="a8ffa-132">此标志仅受 Exchange 通讯簿提供程序支持。</span><span class="sxs-lookup"><span data-stu-id="a8ffa-132">This flag is supported only by the Exchange Address Book Provider.</span></span>
    
  > [!NOTE]
  > <span data-ttu-id="a8ffa-133">_UlFlags_ MAPI_GAL_ONLY 可能未定义当前具有可下载头文件中，在这种情况下您可以将其添加到代码中使用以下值： >`#define MAPI_GAL_ONLY (0x00000080)`</span><span class="sxs-lookup"><span data-stu-id="a8ffa-133">The  _ulFlags_ MAPI_GAL_ONLY might not be defined in the downloadable header file you currently have, in which case you can add it to your code using the following value: >  `#define MAPI_GAL_ONLY (0x00000080)`</span></span>
  
<span data-ttu-id="a8ffa-134">MAPI_MODIFY</span><span class="sxs-lookup"><span data-stu-id="a8ffa-134">MAPI_MODIFY</span></span> 
  
> <span data-ttu-id="a8ffa-135">请求项打开的读/写权限。</span><span class="sxs-lookup"><span data-stu-id="a8ffa-135">Requests that the entry be opened with read/write permission.</span></span> <span data-ttu-id="a8ffa-136">因为条目具有只读访问权限打开默认情况下，客户端不应假定无论是否设置 MAPI_MODIFY 授予了读/写权限。</span><span class="sxs-lookup"><span data-stu-id="a8ffa-136">Because entries are opened with read-only access by default, clients should not assume that read/write permission was granted regardless of whether MAPI_MODIFY is set.</span></span>
    
<span data-ttu-id="a8ffa-137">MAPI_NO_CACHE</span><span class="sxs-lookup"><span data-stu-id="a8ffa-137">MAPI_NO_CACHE</span></span>
  
> <span data-ttu-id="a8ffa-138">不使用脱机通讯簿执行名称解析。</span><span class="sxs-lookup"><span data-stu-id="a8ffa-138">Do not use the offline address book to perform name resolution.</span></span> <span data-ttu-id="a8ffa-139">此标志仅受 Exchange 通讯簿提供程序支持。</span><span class="sxs-lookup"><span data-stu-id="a8ffa-139">This flag is supported only by the Exchange Address Book Provider.</span></span>
    
<span data-ttu-id="a8ffa-140">_lpulObjType_</span><span class="sxs-lookup"><span data-stu-id="a8ffa-140">_lpulObjType_</span></span>
  
> <span data-ttu-id="a8ffa-141">[输出]一个指向打开条目的类型。</span><span class="sxs-lookup"><span data-stu-id="a8ffa-141">[out] A pointer to the type of the opened entry.</span></span>
    
<span data-ttu-id="a8ffa-142">_lppUnk_</span><span class="sxs-lookup"><span data-stu-id="a8ffa-142">_lppUnk_</span></span>
  
> <span data-ttu-id="a8ffa-143">[输出]指向于打开项的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="a8ffa-143">[out] A pointer to a pointer to the opened entry.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="a8ffa-144">返回值</span><span class="sxs-lookup"><span data-stu-id="a8ffa-144">Return value</span></span>

<span data-ttu-id="a8ffa-145">S_OK</span><span class="sxs-lookup"><span data-stu-id="a8ffa-145">S_OK</span></span> 
  
> <span data-ttu-id="a8ffa-146">已成功打开该条目。</span><span class="sxs-lookup"><span data-stu-id="a8ffa-146">The entry was successfully opened.</span></span>
    
<span data-ttu-id="a8ffa-147">MAPI_E_NO_ACCESS</span><span class="sxs-lookup"><span data-stu-id="a8ffa-147">MAPI_E_NO_ACCESS</span></span> 
  
> <span data-ttu-id="a8ffa-148">尝试打开其用户没有足够的权限条目。</span><span class="sxs-lookup"><span data-stu-id="a8ffa-148">An attempt was made to open an entry for which the user has insufficient permissions.</span></span>
    
<span data-ttu-id="a8ffa-149">MAPI_E_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="a8ffa-149">MAPI_E_NOT_FOUND</span></span> 
  
> <span data-ttu-id="a8ffa-150">由_lpEntryID_项不存在。</span><span class="sxs-lookup"><span data-stu-id="a8ffa-150">The entry represented by  _lpEntryID_ does not exist.</span></span> 
    
<span data-ttu-id="a8ffa-151">MAPI_E_UNKNOWN_ENTRYID</span><span class="sxs-lookup"><span data-stu-id="a8ffa-151">MAPI_E_UNKNOWN_ENTRYID</span></span> 
  
> <span data-ttu-id="a8ffa-152">无法识别_lpEntryID_中指定的项标识符。</span><span class="sxs-lookup"><span data-stu-id="a8ffa-152">The entry identifier specified in  _lpEntryID_ is not recognized.</span></span> <span data-ttu-id="a8ffa-153">如果负责的相应条目的地址簿提供程序未打开，则通常会返回此值。</span><span class="sxs-lookup"><span data-stu-id="a8ffa-153">This value is typically returned if the address book provider responsible for the corresponding entry is not open.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="a8ffa-154">备注</span><span class="sxs-lookup"><span data-stu-id="a8ffa-154">Remarks</span></span>

<span data-ttu-id="a8ffa-155">客户端和服务提供商调用**IAddrBook::OpenEntry**方法打开的通讯簿条目。</span><span class="sxs-lookup"><span data-stu-id="a8ffa-155">Clients and service providers call the **IAddrBook::OpenEntry** method to open an address book entry.</span></span> <span data-ttu-id="a8ffa-156">MAPI 转发到适当的地址簿提供程序，基于[MAPIUID](mapiuid.md)结构包含传递_lpEntryID_参数中的项标识符的调用。</span><span class="sxs-lookup"><span data-stu-id="a8ffa-156">MAPI forwards the call to the appropriate address book provider, based on the [MAPIUID](mapiuid.md) structure included in the entry identifier passed in the  _lpEntryID_ parameter.</span></span> <span data-ttu-id="a8ffa-157">通讯簿提供程序将打开以只读方式条目，除非设置了_ulFlags_参数中的 MAPI_MODIFY 或 MAPI_BEST_ACCESS 标志。</span><span class="sxs-lookup"><span data-stu-id="a8ffa-157">The address book provider opens the entry as read-only unless the MAPI_MODIFY or MAPI_BEST_ACCESS flag in the  _ulFlags_ parameter is set.</span></span> <span data-ttu-id="a8ffa-158">但是，这些标志为建议。</span><span class="sxs-lookup"><span data-stu-id="a8ffa-158">However, these flags are suggestions.</span></span> <span data-ttu-id="a8ffa-159">如果通讯簿提供程序不允许请求的项的修改，则将返回 MAPI_E_NO_ACCESS。</span><span class="sxs-lookup"><span data-stu-id="a8ffa-159">If the address book provider does not allow modification for the entry requested, it returns MAPI_E_NO_ACCESS.</span></span> 
  
<span data-ttu-id="a8ffa-160">_LpInterface_参数指示应使用哪个接口访问打开的条目。</span><span class="sxs-lookup"><span data-stu-id="a8ffa-160">The  _lpInterface_ parameter indicates which interface should be used to access the opened entry.</span></span> <span data-ttu-id="a8ffa-161">在_lpInterface_传递 NULL 指示应使用标准的 MAPI 接口，该类型的项。</span><span class="sxs-lookup"><span data-stu-id="a8ffa-161">Passing NULL in  _lpInterface_ indicates the standard MAPI interface for that type of entry should be used.</span></span> <span data-ttu-id="a8ffa-162">因为通讯簿提供程序可能返回不同的接口，建议_lpInterface_参数比，呼叫者应检查以确定是否返回的对象类型是在_lpulObjType_参数中返回的值预期的。</span><span class="sxs-lookup"><span data-stu-id="a8ffa-162">Because the address book provider might return a different interface than the one suggested by the  _lpInterface_ parameter, the caller should check the value returned in the  _lpulObjType_ parameter to determine whether the object type returned is what was expected.</span></span> <span data-ttu-id="a8ffa-163">如果对象类型不是预期的类型，调用方可以强制转换更适合的类型_lppUnk_参数。</span><span class="sxs-lookup"><span data-stu-id="a8ffa-163">If the object type is not of the type expected, the caller can cast the  _lppUnk_ parameter to a type that is more appropriate.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="a8ffa-164">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a8ffa-164">See also</span></span>

- [<span data-ttu-id="a8ffa-165">IAddrBook: IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="a8ffa-165">IAddrBook : IMAPIProp</span></span>](iaddrbookimapiprop.md)

