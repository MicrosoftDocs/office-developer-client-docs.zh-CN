---
title: IMsgStoreOpenEntry
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMsgStore.OpenEntry
api_type:
- COM
ms.assetid: a63c42cf-36af-466b-b41e-d6b53ce1c9fb
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 611680db87c02b9370d6c1b3ac7a8d68b47f3050
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22574025"
---
# <a name="imsgstoreopenentry"></a><span data-ttu-id="1196f-103">IMsgStore::OpenEntry</span><span class="sxs-lookup"><span data-stu-id="1196f-103">IMsgStore::OpenEntry</span></span>

  
  
<span data-ttu-id="1196f-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="1196f-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="1196f-105">打开文件夹或消息并返回进一步访问的接口指针。</span><span class="sxs-lookup"><span data-stu-id="1196f-105">Opens a folder or message and returns an interface pointer for further access.</span></span> 
  
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

## <a name="parameters"></a><span data-ttu-id="1196f-106">参数</span><span class="sxs-lookup"><span data-stu-id="1196f-106">Parameters</span></span>

 <span data-ttu-id="1196f-107">_cbEntryID_</span><span class="sxs-lookup"><span data-stu-id="1196f-107">_cbEntryID_</span></span>
  
> <span data-ttu-id="1196f-108">[in]_LpEntryID_参数 _。_ 指向该条目标识符中字节数</span><span class="sxs-lookup"><span data-stu-id="1196f-108">[in] The byte count in the entry identifier pointed to by the  _lpEntryID_ parameter  _._</span></span>
    
 <span data-ttu-id="1196f-109">_lpEntryID_</span><span class="sxs-lookup"><span data-stu-id="1196f-109">_lpEntryID_</span></span>
  
> <span data-ttu-id="1196f-110">[in]指向打开，则为 NULL 对象的项标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="1196f-110">[in] A pointer to the entry identifier of the object to open, or NULL.</span></span> <span data-ttu-id="1196f-111">如果_lpEntryID_设置为 NULL， **OpenEntry**将打开的邮件存储区的根文件夹。</span><span class="sxs-lookup"><span data-stu-id="1196f-111">If  _lpEntryID_ is set to NULL, **OpenEntry** opens the root folder for the message store.</span></span> 
    
 <span data-ttu-id="1196f-112">_lpInterface_</span><span class="sxs-lookup"><span data-stu-id="1196f-112">_lpInterface_</span></span>
  
> <span data-ttu-id="1196f-113">[in]指向接口标识 (IID) 值，该值代表要用于访问打开的对象的接口的指针。</span><span class="sxs-lookup"><span data-stu-id="1196f-113">[in] A pointer to the interface identifier (IID) that represents the interface to be used to access the opened object.</span></span> <span data-ttu-id="1196f-114">传递空结果对象中的返回标准接口 ([IMAPIFolder](imapifolderimapicontainer.md)文件夹) 和[IMessage](imessageimapiprop.md)的邮件。</span><span class="sxs-lookup"><span data-stu-id="1196f-114">Passing NULL results in the object's standard interface ([IMAPIFolder](imapifolderimapicontainer.md) for folders and [IMessage](imessageimapiprop.md) for messages) being returned.</span></span> 
    
 <span data-ttu-id="1196f-115">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="1196f-115">_ulFlags_</span></span>
  
> <span data-ttu-id="1196f-116">[in]位掩码的标志，控制如何打开对象。</span><span class="sxs-lookup"><span data-stu-id="1196f-116">[in] A bitmask of flags that controls how the object is opened.</span></span> <span data-ttu-id="1196f-117">可以使用以下标志：</span><span class="sxs-lookup"><span data-stu-id="1196f-117">The following flags can be used:</span></span>
    
<span data-ttu-id="1196f-118">MAPI_BEST_ACCESS</span><span class="sxs-lookup"><span data-stu-id="1196f-118">MAPI_BEST_ACCESS</span></span> 
  
> <span data-ttu-id="1196f-119">请求，通过使用用户和最大客户端应用程序访问允许的最大网络权限打开对象。</span><span class="sxs-lookup"><span data-stu-id="1196f-119">Requests that the object be opened by using the maximum network permissions allowed for the user and the maximum client application access.</span></span> <span data-ttu-id="1196f-120">例如，如果客户端具有读/写权限，该对象应打开使用读/写权限;如果客户端具有只读权限，则应使用只读权限打开对象。</span><span class="sxs-lookup"><span data-stu-id="1196f-120">For example, if the client has read/write permission, the object should be opened by using read/write permission; if the client has read-only permission, the object should be opened by using read-only permission.</span></span> 
    
<span data-ttu-id="1196f-121">MAPI_DEFERRED_ERRORS</span><span class="sxs-lookup"><span data-stu-id="1196f-121">MAPI_DEFERRED_ERRORS</span></span> 
  
> <span data-ttu-id="1196f-122">允许**OpenEntry**返回成功，原因可能是完全可调用客户端对象之前。</span><span class="sxs-lookup"><span data-stu-id="1196f-122">Allows **OpenEntry** to return successfully, possibly before the object is fully available to the calling client.</span></span> <span data-ttu-id="1196f-123">如果对象不可用，则进行后续对象呼叫会引发错误。</span><span class="sxs-lookup"><span data-stu-id="1196f-123">If the object is not available, making a subsequent object call can raise an error.</span></span> 
    
<span data-ttu-id="1196f-124">MAPI_MODIFY</span><span class="sxs-lookup"><span data-stu-id="1196f-124">MAPI_MODIFY</span></span> 
  
> <span data-ttu-id="1196f-125">请求读/写权限。</span><span class="sxs-lookup"><span data-stu-id="1196f-125">Requests read/write permission.</span></span> <span data-ttu-id="1196f-126">默认情况下，对象打开具有只读权限和客户端应不起作用以为，读/写授予权限。</span><span class="sxs-lookup"><span data-stu-id="1196f-126">By default, objects are opened with read-only permission, and clients should not work on the assumption that read/write permission is granted.</span></span> 
    
 <span data-ttu-id="1196f-127">_lpulObjType_</span><span class="sxs-lookup"><span data-stu-id="1196f-127">_lpulObjType_</span></span>
  
> <span data-ttu-id="1196f-128">[输出]一个指向打开的对象的类型。</span><span class="sxs-lookup"><span data-stu-id="1196f-128">[out] A pointer to the type of the opened object.</span></span>
    
 <span data-ttu-id="1196f-129">_lppUnk_</span><span class="sxs-lookup"><span data-stu-id="1196f-129">_lppUnk_</span></span>
  
> <span data-ttu-id="1196f-130">[输出]指向打开的对象的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="1196f-130">[out] A pointer to a pointer to the opened object.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="1196f-131">返回值</span><span class="sxs-lookup"><span data-stu-id="1196f-131">Return value</span></span>

<span data-ttu-id="1196f-132">S_OK</span><span class="sxs-lookup"><span data-stu-id="1196f-132">S_OK</span></span> 
  
> <span data-ttu-id="1196f-133">呼叫成功或多个预期值返回。</span><span class="sxs-lookup"><span data-stu-id="1196f-133">The call succeeded and has returned the expected value or values.</span></span>
    
<span data-ttu-id="1196f-134">MAPI_E_NO_ACCESS</span><span class="sxs-lookup"><span data-stu-id="1196f-134">MAPI_E_NO_ACCESS</span></span> 
  
> <span data-ttu-id="1196f-135">尝试修改只读对象或访问其用户没有足够的权限的对象。</span><span class="sxs-lookup"><span data-stu-id="1196f-135">An attempt was made to modify a read-only object or to access an object for which the user has insufficient permissions.</span></span>
    
<span data-ttu-id="1196f-136">MAPI_NO_CACHE</span><span class="sxs-lookup"><span data-stu-id="1196f-136">MAPI_NO_CACHE</span></span>
  
> <span data-ttu-id="1196f-137">当在缓存模式下打开存储区时，客户端或服务提供程序可以调用**IMsgStore::OpenEntry**，设置要打开的项目或远程存储上的文件夹的 MAPI_NO_CACHE 标志。</span><span class="sxs-lookup"><span data-stu-id="1196f-137">When a store is opened in cached mode, a client or service provider can call **IMsgStore::OpenEntry**, setting the MAPI_NO_CACHE flag to open an item or a folder on the remote store.</span></span> <span data-ttu-id="1196f-138">如果您使用 MDB_ONLINE 标志远程服务器上打开的消息存储，您不必使用 MAPI_NO_CACHE 标志。</span><span class="sxs-lookup"><span data-stu-id="1196f-138">If you open the message store with the MDB_ONLINE flag on the remote server, you do not have to use the MAPI_NO_CACHE flag.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="1196f-139">注解</span><span class="sxs-lookup"><span data-stu-id="1196f-139">Remarks</span></span>

<span data-ttu-id="1196f-140">**IMsgStore::OpenEntry**方法打开文件夹或消息，并返回可用于进一步访问的接口的指针。</span><span class="sxs-lookup"><span data-stu-id="1196f-140">The **IMsgStore::OpenEntry** method opens a folder or message and returns a pointer to an interface that can be used for further access.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="1196f-141">当打开文件夹释公用的存储，如文件夹和消息，而不是[IMAPISession::OpenEntry](imapisession-openentry.md)使用**IMsgStore::OpenEntry** 。</span><span class="sxs-lookup"><span data-stu-id="1196f-141">When opening folder entries on a public store, such as folders and messages, use **IMsgStore::OpenEntry** instead of [IMAPISession::OpenEntry](imapisession-openentry.md).</span></span> <span data-ttu-id="1196f-142">这确保公用文件夹正常配置文件中定义了多个 Exchange 帐户。</span><span class="sxs-lookup"><span data-stu-id="1196f-142">This ensures that public folders function correctly when multiple Exchange accounts are defined in a profile.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="1196f-143">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="1196f-143">Notes to callers</span></span>

<span data-ttu-id="1196f-144">文件夹和邮件会自动打开具有只读权限，除非_ulFlags_参数中设置 MAPI_MODIFY 或 MAPI_BEST_ACCESS 标志。</span><span class="sxs-lookup"><span data-stu-id="1196f-144">Folders and messages are automatically opened with read-only permission, unless you set the MAPI_MODIFY or MAPI_BEST_ACCESS flag in the  _ulFlags_ parameter.</span></span> <span data-ttu-id="1196f-145">这些标志之一设置不保证特定类型的权限;您已被授予的权限取决于消息存储提供程序、 您的访问级别和的对象。</span><span class="sxs-lookup"><span data-stu-id="1196f-145">Setting one of these flags does not guarantee a particular type of permission; the permissions that you are granted depend on the message store provider, your access level, and the object.</span></span> <span data-ttu-id="1196f-146">若要确定打开的对象的访问级别，检索其**PR_ACCESS_LEVEL** ([PidTagAccessLevel](pidtagaccesslevel-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="1196f-146">To determine the access level of the opened object, retrieve its **PR_ACCESS_LEVEL** ([PidTagAccessLevel](pidtagaccesslevel-canonical-property.md)) property.</span></span>
  
<span data-ttu-id="1196f-147">尽管**IMsgStore::OpenEntry**可用于打开任何文件夹或消息，但它通常是更快地使用[IMAPIContainer::OpenEntry](imapicontainer-openentry.md)方法，如果您具有对打开的邮件的文件夹的父文件夹的访问。</span><span class="sxs-lookup"><span data-stu-id="1196f-147">Although **IMsgStore::OpenEntry** can be used to open any folder or message, it is usually faster to use the [IMAPIContainer::OpenEntry](imapicontainer-openentry.md) method if you have access to the parent folder of the folder or message to be opened.</span></span> 
  
<span data-ttu-id="1196f-148">检查以确定是否返回的对象类型是您的预期_lpulObjType_参数中返回的值。</span><span class="sxs-lookup"><span data-stu-id="1196f-148">Check the value returned in the  _lpulObjType_ parameter to determine whether the returned object type is what you expected.</span></span> <span data-ttu-id="1196f-149">如果对象类型不是预期的类型，强制转换为适当类型的指针的指针从_lppUnk_参数。</span><span class="sxs-lookup"><span data-stu-id="1196f-149">If the object type is not the expected type, cast the pointer from the  _lppUnk_ parameter to a pointer of the appropriate type.</span></span> <span data-ttu-id="1196f-150">例如，如果您打开一个文件夹，强制转换为的类型**LPMAPIFOLDER**指针_lppUnk_ 。</span><span class="sxs-lookup"><span data-stu-id="1196f-150">For example, if you are opening a folder, cast  _lppUnk_ to a pointer of type **LPMAPIFOLDER**.</span></span>
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="1196f-151">MFCMAPI 参考 （英文）</span><span class="sxs-lookup"><span data-stu-id="1196f-151">MFCMAPI reference</span></span>

<span data-ttu-id="1196f-152">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="1196f-152">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="1196f-153">**文件**</span><span class="sxs-lookup"><span data-stu-id="1196f-153">**File**</span></span>|<span data-ttu-id="1196f-154">**函数**</span><span class="sxs-lookup"><span data-stu-id="1196f-154">**Function**</span></span>|<span data-ttu-id="1196f-155">**Comment**</span><span class="sxs-lookup"><span data-stu-id="1196f-155">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="1196f-156">MAPIFunctions.cpp</span><span class="sxs-lookup"><span data-stu-id="1196f-156">MAPIFunctions.cpp</span></span>  <br/> |<span data-ttu-id="1196f-157">CallOpenEntry</span><span class="sxs-lookup"><span data-stu-id="1196f-157">CallOpenEntry</span></span>  <br/> |<span data-ttu-id="1196f-158">MFCMAPI 使用**IMsgStore::OpenEntry**方法打开与条目 ID 关联的对象</span><span class="sxs-lookup"><span data-stu-id="1196f-158">MFCMAPI uses the **IMsgStore::OpenEntry** method to open the object associated with an entry ID.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="1196f-159">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1196f-159">See also</span></span>



[<span data-ttu-id="1196f-160">IMAPIContainer::OpenEntry</span><span class="sxs-lookup"><span data-stu-id="1196f-160">IMAPIContainer::OpenEntry</span></span>](imapicontainer-openentry.md)
  
[<span data-ttu-id="1196f-161">IMsgStore : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="1196f-161">IMsgStore : IMAPIProp</span></span>](imsgstoreimapiprop.md)


[<span data-ttu-id="1196f-162">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="1196f-162">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

