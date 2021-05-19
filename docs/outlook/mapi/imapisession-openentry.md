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
ms.openlocfilehash: 10992fdf53c416c473b90b5748b9c5fa4f65cffc
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33426385"
---
# <a name="imapisessionopenentry"></a><span data-ttu-id="11026-103">IMAPISession::OpenEntry</span><span class="sxs-lookup"><span data-stu-id="11026-103">IMAPISession::OpenEntry</span></span>

  
  
<span data-ttu-id="11026-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="11026-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="11026-105">打开对象并返回接口指针以用于其他访问。</span><span class="sxs-lookup"><span data-stu-id="11026-105">Opens an object and returns an interface pointer for additional access.</span></span>
  
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

## <a name="parameters"></a><span data-ttu-id="11026-106">参数</span><span class="sxs-lookup"><span data-stu-id="11026-106">Parameters</span></span>

 <span data-ttu-id="11026-107">_cbEntryID_</span><span class="sxs-lookup"><span data-stu-id="11026-107">_cbEntryID_</span></span>
  
> <span data-ttu-id="11026-108">[in]  _lpEntryID_ 参数指向的条目标识符中的字节计数。</span><span class="sxs-lookup"><span data-stu-id="11026-108">[in] The byte count in the entry identifier pointed to by the  _lpEntryID_ parameter.</span></span> 
    
 <span data-ttu-id="11026-109">_lpEntryID_</span><span class="sxs-lookup"><span data-stu-id="11026-109">_lpEntryID_</span></span>
  
> <span data-ttu-id="11026-110">[in]指向要打开的对象的条目标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="11026-110">[in] A pointer to the entry identifier of the object to open.</span></span>
    
 <span data-ttu-id="11026-111">_lpInterface_</span><span class="sxs-lookup"><span data-stu-id="11026-111">_lpInterface_</span></span>
  
> <span data-ttu-id="11026-112">[in]指向接口标识符的指针 (IID) 表示用于访问打开对象的接口。</span><span class="sxs-lookup"><span data-stu-id="11026-112">[in] A pointer to the interface identifier (IID) that represents the interface to be used to access the opened object.</span></span> <span data-ttu-id="11026-113">传递 NULL 将返回对象的标准接口。</span><span class="sxs-lookup"><span data-stu-id="11026-113">Passing NULL returns the object's standard interface.</span></span> <span data-ttu-id="11026-114">例如，如果要打开的对象是一条消息，则标准接口为 [IMessage](imessageimapiprop.md);对于文件夹，它是 [IMAPIFolder](imapifolderimapicontainer.md)。</span><span class="sxs-lookup"><span data-stu-id="11026-114">For example, if the object to be opened is a message, the standard interface is [IMessage](imessageimapiprop.md); for folders, it is [IMAPIFolder](imapifolderimapicontainer.md).</span></span> <span data-ttu-id="11026-115">通讯簿对象的标准接口是通讯组列表的[IDistList](idistlistimapicontainer.md)和邮件用户的[IMailUser。](imailuserimapiprop.md)</span><span class="sxs-lookup"><span data-stu-id="11026-115">The standard interfaces for address book objects are [IDistList](idistlistimapicontainer.md) for a distribution list and [IMailUser](imailuserimapiprop.md) for a messaging user.</span></span> 
    
 <span data-ttu-id="11026-116">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="11026-116">_ulFlags_</span></span>
  
> <span data-ttu-id="11026-117">[in]控制对象打开方式的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="11026-117">[in] A bitmask of flags that controls how the object is opened.</span></span> <span data-ttu-id="11026-118">可以使用以下标志：</span><span class="sxs-lookup"><span data-stu-id="11026-118">The following flags can be used:</span></span>
    
<span data-ttu-id="11026-119">MAPI_BEST_ACCESS</span><span class="sxs-lookup"><span data-stu-id="11026-119">MAPI_BEST_ACCESS</span></span> 
  
> <span data-ttu-id="11026-120">请求使用用户允许的最大网络权限和最大客户端应用程序访问权限打开对象。</span><span class="sxs-lookup"><span data-stu-id="11026-120">Requests that the object be opened by using the maximum network permissions allowed for the user and the maximum client application access.</span></span> <span data-ttu-id="11026-121">例如，如果客户端具有读/写权限，则应该使用读/写权限打开对象;如果客户端具有只读权限，则应该使用只读权限打开对象。</span><span class="sxs-lookup"><span data-stu-id="11026-121">For example, if the client has read/write permission, the object should be opened with read/write permission; if the client has read-only permission, the object should be opened with read-only permission.</span></span> 
    
<span data-ttu-id="11026-122">MAPI_CACHE_OK</span><span class="sxs-lookup"><span data-stu-id="11026-122">MAPI_CACHE_OK</span></span>
  
> <span data-ttu-id="11026-123">使用所有方法（包括脱机通讯簿）执行名称解析。</span><span class="sxs-lookup"><span data-stu-id="11026-123">Use all means, including offline address books, to perform name resolution.</span></span>
    
<span data-ttu-id="11026-124">MAPI_CACHE_ONLY</span><span class="sxs-lookup"><span data-stu-id="11026-124">MAPI_CACHE_ONLY</span></span>
  
> <span data-ttu-id="11026-125">仅使用脱机通讯簿执行名称解析。</span><span class="sxs-lookup"><span data-stu-id="11026-125">Use only the offline address book to perform name resolution.</span></span> <span data-ttu-id="11026-126">例如，您可以使用此标志允许客户端应用程序在缓存 exchange 模式下打开全局地址列表 (GAL) ，并访问缓存中的该通讯簿中的条目，而无需在客户端和服务器之间创建流量。</span><span class="sxs-lookup"><span data-stu-id="11026-126">For example, you can use this flag to allow a client application to open the global address list (GAL) in cached exchange mode and access an entry in that address book from the cache without creating traffic between the client and the server.</span></span> <span data-ttu-id="11026-127">此标志仅受通讯簿Exchange支持。</span><span class="sxs-lookup"><span data-stu-id="11026-127">This flag is supported only by the Exchange Address Book Provider.</span></span>
    
<span data-ttu-id="11026-128">MAPI_DEFERRED_ERRORS</span><span class="sxs-lookup"><span data-stu-id="11026-128">MAPI_DEFERRED_ERRORS</span></span> 
  
> <span data-ttu-id="11026-129">允许 **OpenEntry** 在对象完全可供调用客户端使用之前成功返回。</span><span class="sxs-lookup"><span data-stu-id="11026-129">Allows **OpenEntry** to return successfully, possibly before the object is fully available to the calling client.</span></span> <span data-ttu-id="11026-130">如果该对象不可用，则进行后续的对象调用可能会导致错误。</span><span class="sxs-lookup"><span data-stu-id="11026-130">If the object is not available, making a subsequent object call can cause an error.</span></span> 
    
<span data-ttu-id="11026-131">MAPI_MODIFY</span><span class="sxs-lookup"><span data-stu-id="11026-131">MAPI_MODIFY</span></span> 
  
> <span data-ttu-id="11026-132">请求读/写权限。</span><span class="sxs-lookup"><span data-stu-id="11026-132">Requests read/write permission.</span></span> <span data-ttu-id="11026-133">默认情况下，使用只读权限打开对象，客户端不应在授予读/写权限的假设下工作。</span><span class="sxs-lookup"><span data-stu-id="11026-133">By default, objects are opened with read-only permission, and clients should not work on the assumption that read/write permission is granted.</span></span> 
    
<span data-ttu-id="11026-134">MAPI_NO_CACHE</span><span class="sxs-lookup"><span data-stu-id="11026-134">MAPI_NO_CACHE</span></span>
  
> <span data-ttu-id="11026-135">请勿使用脱机通讯簿执行名称解析。</span><span class="sxs-lookup"><span data-stu-id="11026-135">Do not use the offline address book to perform name resolution.</span></span> <span data-ttu-id="11026-136">此标志仅受通讯簿Exchange支持。</span><span class="sxs-lookup"><span data-stu-id="11026-136">This flag is supported only by the Exchange Address Book Provider.</span></span>
    
<span data-ttu-id="11026-137">SHOW_SOFT_DELETES</span><span class="sxs-lookup"><span data-stu-id="11026-137">SHOW_SOFT_DELETES</span></span>
  
> <span data-ttu-id="11026-138">显示当前标记为软删除的项目 (即它们处于已删除项目保留时间阶段) 。</span><span class="sxs-lookup"><span data-stu-id="11026-138">Show items that are currently marked as soft deleted (that is, they are in the deleted item retention time phase).</span></span>
    
 <span data-ttu-id="11026-139">_lpulObjType_</span><span class="sxs-lookup"><span data-stu-id="11026-139">_lpulObjType_</span></span>
  
> <span data-ttu-id="11026-140">[out]指向已打开对象的类型的指针。</span><span class="sxs-lookup"><span data-stu-id="11026-140">[out] A pointer to the type of the opened object.</span></span>
    
 <span data-ttu-id="11026-141">_lppUnk_</span><span class="sxs-lookup"><span data-stu-id="11026-141">_lppUnk_</span></span>
  
> <span data-ttu-id="11026-142">[out]指向已打开对象的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="11026-142">[out] A pointer to a pointer to the opened object.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="11026-143">返回值</span><span class="sxs-lookup"><span data-stu-id="11026-143">Return value</span></span>

<span data-ttu-id="11026-144">S_OK</span><span class="sxs-lookup"><span data-stu-id="11026-144">S_OK</span></span> 
  
> <span data-ttu-id="11026-145">已成功打开对象。</span><span class="sxs-lookup"><span data-stu-id="11026-145">The object was opened successfully.</span></span>
    
<span data-ttu-id="11026-146">MAPI_E_NO_ACCESS</span><span class="sxs-lookup"><span data-stu-id="11026-146">MAPI_E_NO_ACCESS</span></span> 
  
> <span data-ttu-id="11026-147">试图修改只读对象，或试图访问用户权限不足的对象。</span><span class="sxs-lookup"><span data-stu-id="11026-147">An attempt was made to modify a read-only object or an attempt was made to access an object for which the user has insufficient permissions.</span></span>
    
<span data-ttu-id="11026-148">MAPI_E_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="11026-148">MAPI_E_NOT_FOUND</span></span> 
  
> <span data-ttu-id="11026-149">没有与在  _lpEntryID_ 参数中传递的条目标识符关联的对象。</span><span class="sxs-lookup"><span data-stu-id="11026-149">There is not an object associated with the entry identifier passed in the  _lpEntryID_ parameter.</span></span> 
    
<span data-ttu-id="11026-150">MAPI_E_UNKNOWN_ENTRYID</span><span class="sxs-lookup"><span data-stu-id="11026-150">MAPI_E_UNKNOWN_ENTRYID</span></span> 
  
> <span data-ttu-id="11026-151">在  _lpEntryID_ 参数中传递的条目标识符采用不可识别的格式。</span><span class="sxs-lookup"><span data-stu-id="11026-151">The entry identifier passed in the  _lpEntryID_ parameter is in an unrecognizable format.</span></span> <span data-ttu-id="11026-152">如果包含该对象的服务提供商未打开，则通常返回此值。</span><span class="sxs-lookup"><span data-stu-id="11026-152">This value is typically returned if the service provider that contains the object is not open.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="11026-153">备注</span><span class="sxs-lookup"><span data-stu-id="11026-153">Remarks</span></span>

<span data-ttu-id="11026-154">**IMAPISession：：OpenEntry** 方法打开消息存储或通讯簿对象，返回一个指向可用于访问该对象的接口的指针。</span><span class="sxs-lookup"><span data-stu-id="11026-154">The **IMAPISession::OpenEntry** method opens a message store or address book object, returning a pointer to an interface that can be used to access the object.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="11026-155">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="11026-155">Notes to callers</span></span>

> [!IMPORTANT]
> <span data-ttu-id="11026-156">打开公用存储上的文件夹条目（如文件夹和邮件）时，请使用 [IMsgStore：：OpenEntry](imsgstore-openentry.md) 而不是 **IMAPISession：：OpenEntry**。</span><span class="sxs-lookup"><span data-stu-id="11026-156">When opening folder entries on a public store, such as folders and messages, use [IMsgStore::OpenEntry](imsgstore-openentry.md) instead of **IMAPISession::OpenEntry**.</span></span> <span data-ttu-id="11026-157">这可确保在配置文件中定义多个Exchange时公用文件夹能够正常运行。</span><span class="sxs-lookup"><span data-stu-id="11026-157">This ensures that public folders function correctly when multiple Exchange accounts are defined in a profile.</span></span> 
  
<span data-ttu-id="11026-158">仅在不知道要打开哪种类型的对象时调用 **IMAPISession：：OpenEntry。**</span><span class="sxs-lookup"><span data-stu-id="11026-158">Call **IMAPISession::OpenEntry** only when you do not know what kind of object that you are opening.</span></span> <span data-ttu-id="11026-159">如果您知道要打开文件夹或邮件，请调用 [IMsgStore：：OpenEntry](imsgstore-openentry.md)。</span><span class="sxs-lookup"><span data-stu-id="11026-159">If you know that you are opening a folder or a message, call [IMsgStore::OpenEntry](imsgstore-openentry.md).</span></span> <span data-ttu-id="11026-160">如果您知道要打开通讯簿容器、邮件传递用户或通讯组列表，请调用 [IAddrBook：：OpenEntry](iaddrbook-openentry.md)。</span><span class="sxs-lookup"><span data-stu-id="11026-160">If you know that you are opening an address book container, a messaging user, or a distribution list, call [IAddrBook::OpenEntry](iaddrbook-openentry.md).</span></span> <span data-ttu-id="11026-161">这些更具体的方法比 **IMAPISession：：OpenEntry 快**。</span><span class="sxs-lookup"><span data-stu-id="11026-161">These more specific methods are faster than **IMAPISession::OpenEntry**.</span></span> 
  
<span data-ttu-id="11026-162">MAPI 以只读权限打开所有对象，除非您在  _ulFlags_ 参数中MAPI_MODIFY或 MAPI_BEST_ACCESS 标记。</span><span class="sxs-lookup"><span data-stu-id="11026-162">MAPI opens all objects with read-only permission, unless you set the MAPI_MODIFY or MAPI_BEST_ACCESS flag in the  _ulFlags_ parameter.</span></span> <span data-ttu-id="11026-163">设置其中一个标志并不能保证特殊类型的访问;授予的权限取决于服务提供商、访问级别和对象。</span><span class="sxs-lookup"><span data-stu-id="11026-163">Setting one of these flags does not guarantee a particular type of access; the permissions that are granted depend on the service provider, the access level, and the object.</span></span> <span data-ttu-id="11026-164">若要确定打开的对象的访问级别，请检索该对象PR_ACCESS_LEVEL ( [PidTagAccessLevel](pidtagaccesslevel-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="11026-164">To determine the access level of the opened object, retrieve its **PR_ACCESS_LEVEL** ([PidTagAccessLevel](pidtagaccesslevel-canonical-property.md)) property.</span></span>
  
<span data-ttu-id="11026-165">调用 **IMAPISession：：OpenEntry** 并设置  _lpEntryID_ 以指向邮件存储的条目标识符与调用设置了 MDB_NO_DIALOG 标志的 [IMAPISession：：OpenMsgStore](imapisession-openmsgstore.md) 方法相同。</span><span class="sxs-lookup"><span data-stu-id="11026-165">Calling **IMAPISession::OpenEntry** and setting  _lpEntryID_ to point to the entry identifier of a message store is the same as calling the [IMAPISession::OpenMsgStore](imapisession-openmsgstore.md) method with the MDB_NO_DIALOG flag set.</span></span> <span data-ttu-id="11026-166">标志设置也是等效的，除了使用 **OpenMsgStore** 请求读/写权限外，必须设置 MDB_WRITE 标志，而不是MAPI_MODIFY。</span><span class="sxs-lookup"><span data-stu-id="11026-166">The flag settings are also equivalent, except that to request read/write permission with **OpenMsgStore**, you must set the MDB_WRITE flag instead of MAPI_MODIFY.</span></span> 
  
<span data-ttu-id="11026-167">检查  _lpulObjType_ 参数中返回的值，以确定对象类型返回的值是否如您预期的那样。</span><span class="sxs-lookup"><span data-stu-id="11026-167">Check the value returned in the  _lpulObjType_ parameter to determine whether the object type returned is what you expected.</span></span> <span data-ttu-id="11026-168">如果对象类型不是您预期的类型，请从  _lppUnk_ 参数将指针强制转换到相应类型的指针。</span><span class="sxs-lookup"><span data-stu-id="11026-168">If the object type is not the type that you expected, cast the pointer from the  _lppUnk_ parameter to a pointer of the appropriate type.</span></span> <span data-ttu-id="11026-169">例如，如果要打开文件夹，将  _lppUnk_ 强制转换到类型 LPMAPIFOLDER 的指针。</span><span class="sxs-lookup"><span data-stu-id="11026-169">For example, if you are opening a folder, cast  _lppUnk_ to a pointer of type LPMAPIFOLDER.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="11026-170">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="11026-170">MFCMAPI reference</span></span>

<span data-ttu-id="11026-171">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="11026-171">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="11026-172">**文件**</span><span class="sxs-lookup"><span data-stu-id="11026-172">**File**</span></span>|<span data-ttu-id="11026-173">**函数**</span><span class="sxs-lookup"><span data-stu-id="11026-173">**Function**</span></span>|<span data-ttu-id="11026-174">**备注**</span><span class="sxs-lookup"><span data-stu-id="11026-174">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="11026-175">MAPIFunctions.cpp</span><span class="sxs-lookup"><span data-stu-id="11026-175">MAPIFunctions.cpp</span></span>  <br/> |<span data-ttu-id="11026-176">CallOpenEntry</span><span class="sxs-lookup"><span data-stu-id="11026-176">CallOpenEntry</span></span>  <br/> |<span data-ttu-id="11026-177">MFCMAPI 使用 **IMAPISession：：OpenEntry** 方法打开对象。</span><span class="sxs-lookup"><span data-stu-id="11026-177">MFCMAPI uses the **IMAPISession::OpenEntry** method to open an object.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="11026-178">另请参阅</span><span class="sxs-lookup"><span data-stu-id="11026-178">See also</span></span>



[<span data-ttu-id="11026-179">IAddrBook::OpenEntry</span><span class="sxs-lookup"><span data-stu-id="11026-179">IAddrBook::OpenEntry</span></span>](iaddrbook-openentry.md)
  
[<span data-ttu-id="11026-180">IDistList : IMAPIContainer</span><span class="sxs-lookup"><span data-stu-id="11026-180">IDistList : IMAPIContainer</span></span>](idistlistimapicontainer.md)
  
[<span data-ttu-id="11026-181">IMailUser : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="11026-181">IMailUser : IMAPIProp</span></span>](imailuserimapiprop.md)
  
[<span data-ttu-id="11026-182">IMAPIFolder : IMAPIContainer</span><span class="sxs-lookup"><span data-stu-id="11026-182">IMAPIFolder : IMAPIContainer</span></span>](imapifolderimapicontainer.md)
  
[<span data-ttu-id="11026-183">IMAPISession::OpenMsgStore</span><span class="sxs-lookup"><span data-stu-id="11026-183">IMAPISession::OpenMsgStore</span></span>](imapisession-openmsgstore.md)
  
[<span data-ttu-id="11026-184">IMessage : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="11026-184">IMessage : IMAPIProp</span></span>](imessageimapiprop.md)
  
[<span data-ttu-id="11026-185">IMsgStore::OpenEntry</span><span class="sxs-lookup"><span data-stu-id="11026-185">IMsgStore::OpenEntry</span></span>](imsgstore-openentry.md)
  
[<span data-ttu-id="11026-186">IMAPISession : IUnknown</span><span class="sxs-lookup"><span data-stu-id="11026-186">IMAPISession : IUnknown</span></span>](imapisessioniunknown.md)


[<span data-ttu-id="11026-187">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="11026-187">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

