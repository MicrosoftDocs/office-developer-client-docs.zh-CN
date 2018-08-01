---
title: IMAPISessionOpenEntry
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISession.OpenEntry
api_type:
- COM
ms.assetid: a4df4860-cf4f-4e97-97c4-fcd89b7f1f91
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: f23b4855b7e2faeb599868f8c2db52ae9cbfbfd8
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775556"
---
# <a name="imapisessionopenentry"></a><span data-ttu-id="b9745-103">IMAPISession::OpenEntry</span><span class="sxs-lookup"><span data-stu-id="b9745-103">IMAPISession::OpenEntry</span></span>

  
  
<span data-ttu-id="b9745-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="b9745-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="b9745-105">打开一个对象并返回的额外访问的接口指针。</span><span class="sxs-lookup"><span data-stu-id="b9745-105">Opens an object and returns an interface pointer for additional access.</span></span>
  
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

## <a name="parameters"></a><span data-ttu-id="b9745-106">参数</span><span class="sxs-lookup"><span data-stu-id="b9745-106">Parameters</span></span>

 <span data-ttu-id="b9745-107">_cbEntryID_</span><span class="sxs-lookup"><span data-stu-id="b9745-107">_cbEntryID_</span></span>
  
> <span data-ttu-id="b9745-108">[in]在_lpEntryID_参数指向的项标识符的字节数。</span><span class="sxs-lookup"><span data-stu-id="b9745-108">[in] The byte count in the entry identifier pointed to by the  _lpEntryID_ parameter.</span></span> 
    
 <span data-ttu-id="b9745-109">_lpEntryID_</span><span class="sxs-lookup"><span data-stu-id="b9745-109">_lpEntryID_</span></span>
  
> <span data-ttu-id="b9745-110">[in]指向要打开的对象的项标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="b9745-110">[in] A pointer to the entry identifier of the object to open.</span></span>
    
 <span data-ttu-id="b9745-111">_lpInterface_</span><span class="sxs-lookup"><span data-stu-id="b9745-111">_lpInterface_</span></span>
  
> <span data-ttu-id="b9745-112">[in]指向接口标识 (IID) 值，该值代表要用于访问打开的对象的接口的指针。</span><span class="sxs-lookup"><span data-stu-id="b9745-112">[in] A pointer to the interface identifier (IID) that represents the interface to be used to access the opened object.</span></span> <span data-ttu-id="b9745-113">如果传递 NULL 返回对象的标准接口。</span><span class="sxs-lookup"><span data-stu-id="b9745-113">Passing NULL returns the object's standard interface.</span></span> <span data-ttu-id="b9745-114">例如，如果要在打开的对象是一条消息，标准接口是[IMessage](imessageimapiprop.md);对于文件夹，则[IMAPIFolder](imapifolderimapicontainer.md)。</span><span class="sxs-lookup"><span data-stu-id="b9745-114">For example, if the object to be opened is a message, the standard interface is [IMessage](imessageimapiprop.md); for folders, it is [IMAPIFolder](imapifolderimapicontainer.md).</span></span> <span data-ttu-id="b9745-115">地址簿对象的标准接口是[IDistList](idistlistimapicontainer.md)通讯组列表和[IMailUser](imailuserimapiprop.md)消息用户。</span><span class="sxs-lookup"><span data-stu-id="b9745-115">The standard interfaces for address book objects are [IDistList](idistlistimapicontainer.md) for a distribution list and [IMailUser](imailuserimapiprop.md) for a messaging user.</span></span> 
    
 <span data-ttu-id="b9745-116">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="b9745-116">_ulFlags_</span></span>
  
> <span data-ttu-id="b9745-117">[in]位掩码的标志，控制如何打开对象。</span><span class="sxs-lookup"><span data-stu-id="b9745-117">[in] A bitmask of flags that controls how the object is opened.</span></span> <span data-ttu-id="b9745-118">可以使用以下标志：</span><span class="sxs-lookup"><span data-stu-id="b9745-118">The following flags can be used:</span></span>
    
<span data-ttu-id="b9745-119">MAPI_BEST_ACCESS</span><span class="sxs-lookup"><span data-stu-id="b9745-119">MAPI_BEST_ACCESS</span></span> 
  
> <span data-ttu-id="b9745-120">请求，通过使用用户和最大客户端应用程序访问允许的最大网络权限打开对象。</span><span class="sxs-lookup"><span data-stu-id="b9745-120">Requests that the object be opened by using the maximum network permissions allowed for the user and the maximum client application access.</span></span> <span data-ttu-id="b9745-121">例如，如果客户端具有读/写权限，该对象应打开具有读/写权限;如果客户端具有只读权限，则应具有只读权限打开对象。</span><span class="sxs-lookup"><span data-stu-id="b9745-121">For example, if the client has read/write permission, the object should be opened with read/write permission; if the client has read-only permission, the object should be opened with read-only permission.</span></span> 
    
<span data-ttu-id="b9745-122">MAPI_CACHE_OK</span><span class="sxs-lookup"><span data-stu-id="b9745-122">MAPI_CACHE_OK</span></span>
  
> <span data-ttu-id="b9745-123">使用所有表示，包括脱机通讯簿执行名称解析。</span><span class="sxs-lookup"><span data-stu-id="b9745-123">Use all means, including offline address books, to perform name resolution.</span></span>
    
<span data-ttu-id="b9745-124">MAPI_CACHE_ONLY</span><span class="sxs-lookup"><span data-stu-id="b9745-124">MAPI_CACHE_ONLY</span></span>
  
> <span data-ttu-id="b9745-125">使用仅脱机通讯簿执行名称解析。</span><span class="sxs-lookup"><span data-stu-id="b9745-125">Use only the offline address book to perform name resolution.</span></span> <span data-ttu-id="b9745-126">例如，您可以使用此标志以允许将客户端应用程序在缓存的 exchange 模式下打开全局地址列表 (GAL)，而不创建客户端和服务器之间的流量从缓存中访问该通讯簿中的条目。</span><span class="sxs-lookup"><span data-stu-id="b9745-126">For example, you can use this flag to allow a client application to open the global address list (GAL) in cached exchange mode and access an entry in that address book from the cache without creating traffic between the client and the server.</span></span> <span data-ttu-id="b9745-127">此标志仅受 Exchange 通讯簿提供程序支持。</span><span class="sxs-lookup"><span data-stu-id="b9745-127">This flag is supported only by the Exchange Address Book Provider.</span></span>
    
<span data-ttu-id="b9745-128">MAPI_DEFERRED_ERRORS</span><span class="sxs-lookup"><span data-stu-id="b9745-128">MAPI_DEFERRED_ERRORS</span></span> 
  
> <span data-ttu-id="b9745-129">允许**OpenEntry**返回成功，原因可能是完全可调用客户端对象之前。</span><span class="sxs-lookup"><span data-stu-id="b9745-129">Allows **OpenEntry** to return successfully, possibly before the object is fully available to the calling client.</span></span> <span data-ttu-id="b9745-130">如果对象不可用，则进行后续对象呼叫会导致错误。</span><span class="sxs-lookup"><span data-stu-id="b9745-130">If the object is not available, making a subsequent object call can cause an error.</span></span> 
    
<span data-ttu-id="b9745-131">MAPI_MODIFY</span><span class="sxs-lookup"><span data-stu-id="b9745-131">MAPI_MODIFY</span></span> 
  
> <span data-ttu-id="b9745-132">请求读/写权限。</span><span class="sxs-lookup"><span data-stu-id="b9745-132">Requests read/write permission.</span></span> <span data-ttu-id="b9745-133">默认情况下，对象打开具有只读权限和客户端应不起作用以为，读/写授予权限。</span><span class="sxs-lookup"><span data-stu-id="b9745-133">By default, objects are opened with read-only permission, and clients should not work on the assumption that read/write permission is granted.</span></span> 
    
<span data-ttu-id="b9745-134">MAPI_NO_CACHE</span><span class="sxs-lookup"><span data-stu-id="b9745-134">MAPI_NO_CACHE</span></span>
  
> <span data-ttu-id="b9745-135">不使用脱机通讯簿执行名称解析。</span><span class="sxs-lookup"><span data-stu-id="b9745-135">Do not use the offline address book to perform name resolution.</span></span> <span data-ttu-id="b9745-136">此标志仅受 Exchange 通讯簿提供程序支持。</span><span class="sxs-lookup"><span data-stu-id="b9745-136">This flag is supported only by the Exchange Address Book Provider.</span></span>
    
<span data-ttu-id="b9745-137">SHOW_SOFT_DELETES</span><span class="sxs-lookup"><span data-stu-id="b9745-137">SHOW_SOFT_DELETES</span></span>
  
> <span data-ttu-id="b9745-138">显示项目的当前标记为软删除 （即，它们是中已删除的邮件保留时间阶段）。</span><span class="sxs-lookup"><span data-stu-id="b9745-138">Show items that are currently marked as soft deleted (that is, they are in the deleted item retention time phase).</span></span>
    
 <span data-ttu-id="b9745-139">_lpulObjType_</span><span class="sxs-lookup"><span data-stu-id="b9745-139">_lpulObjType_</span></span>
  
> <span data-ttu-id="b9745-140">[输出]一个指向打开的对象的类型。</span><span class="sxs-lookup"><span data-stu-id="b9745-140">[out] A pointer to the type of the opened object.</span></span>
    
 <span data-ttu-id="b9745-141">_lppUnk_</span><span class="sxs-lookup"><span data-stu-id="b9745-141">_lppUnk_</span></span>
  
> <span data-ttu-id="b9745-142">[输出]指向打开的对象的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="b9745-142">[out] A pointer to a pointer to the opened object.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="b9745-143">返回值</span><span class="sxs-lookup"><span data-stu-id="b9745-143">Return value</span></span>

<span data-ttu-id="b9745-144">S_OK</span><span class="sxs-lookup"><span data-stu-id="b9745-144">S_OK</span></span> 
  
> <span data-ttu-id="b9745-145">已成功打开对象。</span><span class="sxs-lookup"><span data-stu-id="b9745-145">The object was opened successfully.</span></span>
    
<span data-ttu-id="b9745-146">MAPI_E_NO_ACCESS</span><span class="sxs-lookup"><span data-stu-id="b9745-146">MAPI_E_NO_ACCESS</span></span> 
  
> <span data-ttu-id="b9745-147">尝试修改只读对象或尝试访问其用户没有足够的权限的对象。</span><span class="sxs-lookup"><span data-stu-id="b9745-147">An attempt was made to modify a read-only object or an attempt was made to access an object for which the user has insufficient permissions.</span></span>
    
<span data-ttu-id="b9745-148">MAPI_E_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="b9745-148">MAPI_E_NOT_FOUND</span></span> 
  
> <span data-ttu-id="b9745-149">没有与_lpEntryID_参数中传递的项标识符关联的对象。</span><span class="sxs-lookup"><span data-stu-id="b9745-149">There is not an object associated with the entry identifier passed in the  _lpEntryID_ parameter.</span></span> 
    
<span data-ttu-id="b9745-150">MAPI_E_UNKNOWN_ENTRYID</span><span class="sxs-lookup"><span data-stu-id="b9745-150">MAPI_E_UNKNOWN_ENTRYID</span></span> 
  
> <span data-ttu-id="b9745-151">无法识别格式_lpEntryID_参数中传递的项标识符。</span><span class="sxs-lookup"><span data-stu-id="b9745-151">The entry identifier passed in the  _lpEntryID_ parameter is in an unrecognizable format.</span></span> <span data-ttu-id="b9745-152">如果服务提供商的包含对象未打开，则通常会返回此值。</span><span class="sxs-lookup"><span data-stu-id="b9745-152">This value is typically returned if the service provider that contains the object is not open.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="b9745-153">说明</span><span class="sxs-lookup"><span data-stu-id="b9745-153">Remarks</span></span>

<span data-ttu-id="b9745-154">**IMAPISession::OpenEntry**方法打开邮件存储或通讯簿对象，为接口返回指针可用于访问该对象。</span><span class="sxs-lookup"><span data-stu-id="b9745-154">The **IMAPISession::OpenEntry** method opens a message store or address book object, returning a pointer to an interface that can be used to access the object.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="b9745-155">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="b9745-155">Notes to callers</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b9745-156">当打开文件夹释公用的存储，如文件夹和消息，而不是**IMAPISession::OpenEntry**使用[IMsgStore::OpenEntry](imsgstore-openentry.md) 。</span><span class="sxs-lookup"><span data-stu-id="b9745-156">When opening folder entries on a public store, such as folders and messages, use [IMsgStore::OpenEntry](imsgstore-openentry.md) instead of **IMAPISession::OpenEntry**.</span></span> <span data-ttu-id="b9745-157">这确保公用文件夹正常配置文件中定义了多个 Exchange 帐户。</span><span class="sxs-lookup"><span data-stu-id="b9745-157">This ensures that public folders function correctly when multiple Exchange accounts are defined in a profile.</span></span> 
  
<span data-ttu-id="b9745-158">仅当您不知道哪种类型的对象，您打开时，请调用**IMAPISession::OpenEntry** 。</span><span class="sxs-lookup"><span data-stu-id="b9745-158">Call **IMAPISession::OpenEntry** only when you do not know what kind of object that you are opening.</span></span> <span data-ttu-id="b9745-159">如果您知道您打开文件夹或一条消息，请调用[IMsgStore::OpenEntry](imsgstore-openentry.md)。</span><span class="sxs-lookup"><span data-stu-id="b9745-159">If you know that you are opening a folder or a message, call [IMsgStore::OpenEntry](imsgstore-openentry.md).</span></span> <span data-ttu-id="b9745-160">如果您知道您要打开通讯簿容器、 邮件用户或通讯组列表，请调用[IAddrBook::OpenEntry](iaddrbook-openentry.md)。</span><span class="sxs-lookup"><span data-stu-id="b9745-160">If you know that you are opening an address book container, a messaging user, or a distribution list, call [IAddrBook::OpenEntry](iaddrbook-openentry.md).</span></span> <span data-ttu-id="b9745-161">这些更加具体方法是比**IMAPISession::OpenEntry**速度更快。</span><span class="sxs-lookup"><span data-stu-id="b9745-161">These more specific methods are faster than **IMAPISession::OpenEntry**.</span></span> 
  
<span data-ttu-id="b9745-162">MAPI 具有只读权限，除非您将 MAPI_MODIFY 或 MAPI_BEST_ACCESS 标志设置_ulFlags_参数中，将打开所有对象。</span><span class="sxs-lookup"><span data-stu-id="b9745-162">MAPI opens all objects with read-only permission, unless you set the MAPI_MODIFY or MAPI_BEST_ACCESS flag in the  _ulFlags_ parameter.</span></span> <span data-ttu-id="b9745-163">这些标志之一设置不保证特定类型的访问;授予的权限取决于服务提供程序、 的访问级别，和的对象。</span><span class="sxs-lookup"><span data-stu-id="b9745-163">Setting one of these flags does not guarantee a particular type of access; the permissions that are granted depend on the service provider, the access level, and the object.</span></span> <span data-ttu-id="b9745-164">若要确定打开的对象的访问级别，检索其**PR_ACCESS_LEVEL** ([PidTagAccessLevel](pidtagaccesslevel-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="b9745-164">To determine the access level of the opened object, retrieve its **PR_ACCESS_LEVEL** ([PidTagAccessLevel](pidtagaccesslevel-canonical-property.md)) property.</span></span>
  
<span data-ttu-id="b9745-165">调用**IMAPISession::OpenEntry**和设置_lpEntryID_以指向的消息存储的项标识符调用与 MDB_NO_DIALOG 标志[IMAPISession::OpenMsgStore](imapisession-openmsgstore.md)方法相同设置。</span><span class="sxs-lookup"><span data-stu-id="b9745-165">Calling **IMAPISession::OpenEntry** and setting  _lpEntryID_ to point to the entry identifier of a message store is the same as calling the [IMAPISession::OpenMsgStore](imapisession-openmsgstore.md) method with the MDB_NO_DIALOG flag set.</span></span> <span data-ttu-id="b9745-166">标志设置也是等效的只不过到与**OpenMsgStore**请求读/写权限，则必须设置而不是 MAPI_MODIFY MDB_WRITE 标志。</span><span class="sxs-lookup"><span data-stu-id="b9745-166">The flag settings are also equivalent, except that to request read/write permission with **OpenMsgStore**, you must set the MDB_WRITE flag instead of MAPI_MODIFY.</span></span> 
  
<span data-ttu-id="b9745-167">检查以确定是否返回的对象类型是您的预期_lpulObjType_参数中返回的值。</span><span class="sxs-lookup"><span data-stu-id="b9745-167">Check the value returned in the  _lpulObjType_ parameter to determine whether the object type returned is what you expected.</span></span> <span data-ttu-id="b9745-168">如果对象类型不是预期的类型，强制转换为适当类型的指针的指针从_lppUnk_参数。</span><span class="sxs-lookup"><span data-stu-id="b9745-168">If the object type is not the type that you expected, cast the pointer from the  _lppUnk_ parameter to a pointer of the appropriate type.</span></span> <span data-ttu-id="b9745-169">例如，如果您打开一个文件夹，强制转换为的类型 LPMAPIFOLDER 指针_lppUnk_ 。</span><span class="sxs-lookup"><span data-stu-id="b9745-169">For example, if you are opening a folder, cast  _lppUnk_ to a pointer of type LPMAPIFOLDER.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="b9745-170">MFCMAPI 参考 （英文）</span><span class="sxs-lookup"><span data-stu-id="b9745-170">MFCMAPI reference</span></span>

<span data-ttu-id="b9745-171">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="b9745-171">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="b9745-172">**文件**</span><span class="sxs-lookup"><span data-stu-id="b9745-172">**File**</span></span>|<span data-ttu-id="b9745-173">**函数**</span><span class="sxs-lookup"><span data-stu-id="b9745-173">**Function**</span></span>|<span data-ttu-id="b9745-174">**Comment**</span><span class="sxs-lookup"><span data-stu-id="b9745-174">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b9745-175">MAPIFunctions.cpp</span><span class="sxs-lookup"><span data-stu-id="b9745-175">MAPIFunctions.cpp</span></span>  <br/> |<span data-ttu-id="b9745-176">CallOpenEntry</span><span class="sxs-lookup"><span data-stu-id="b9745-176">CallOpenEntry</span></span>  <br/> |<span data-ttu-id="b9745-177">MFCMAPI 使用**IMAPISession::OpenEntry**方法打开一个对象。</span><span class="sxs-lookup"><span data-stu-id="b9745-177">MFCMAPI uses the **IMAPISession::OpenEntry** method to open an object.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="b9745-178">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b9745-178">See also</span></span>



[<span data-ttu-id="b9745-179">IAddrBook::OpenEntry</span><span class="sxs-lookup"><span data-stu-id="b9745-179">IAddrBook::OpenEntry</span></span>](iaddrbook-openentry.md)
  
[<span data-ttu-id="b9745-180">IDistList : IMAPIContainer</span><span class="sxs-lookup"><span data-stu-id="b9745-180">IDistList : IMAPIContainer</span></span>](idistlistimapicontainer.md)
  
[<span data-ttu-id="b9745-181">IMailUser : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="b9745-181">IMailUser : IMAPIProp</span></span>](imailuserimapiprop.md)
  
[<span data-ttu-id="b9745-182">IMAPIFolder : IMAPIContainer</span><span class="sxs-lookup"><span data-stu-id="b9745-182">IMAPIFolder : IMAPIContainer</span></span>](imapifolderimapicontainer.md)
  
[<span data-ttu-id="b9745-183">IMAPISession::OpenMsgStore</span><span class="sxs-lookup"><span data-stu-id="b9745-183">IMAPISession::OpenMsgStore</span></span>](imapisession-openmsgstore.md)
  
[<span data-ttu-id="b9745-184">IMessage : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="b9745-184">IMessage : IMAPIProp</span></span>](imessageimapiprop.md)
  
[<span data-ttu-id="b9745-185">IMsgStore::OpenEntry</span><span class="sxs-lookup"><span data-stu-id="b9745-185">IMsgStore::OpenEntry</span></span>](imsgstore-openentry.md)
  
[<span data-ttu-id="b9745-186">IMAPISession : IUnknown</span><span class="sxs-lookup"><span data-stu-id="b9745-186">IMAPISession : IUnknown</span></span>](imapisessioniunknown.md)


[<span data-ttu-id="b9745-187">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="b9745-187">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

