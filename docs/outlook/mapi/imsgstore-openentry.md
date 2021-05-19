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
ms.openlocfilehash: 07667558a21a9110d684164d2e6c143d6a519368
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33409333"
---
# <a name="imsgstoreopenentry"></a><span data-ttu-id="70357-103">IMsgStore::OpenEntry</span><span class="sxs-lookup"><span data-stu-id="70357-103">IMsgStore::OpenEntry</span></span>

  
  
<span data-ttu-id="70357-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="70357-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="70357-105">打开文件夹或邮件并返回接口指针以进一步访问。</span><span class="sxs-lookup"><span data-stu-id="70357-105">Opens a folder or message and returns an interface pointer for further access.</span></span> 
  
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

## <a name="parameters"></a><span data-ttu-id="70357-106">参数</span><span class="sxs-lookup"><span data-stu-id="70357-106">Parameters</span></span>

 <span data-ttu-id="70357-107">_cbEntryID_</span><span class="sxs-lookup"><span data-stu-id="70357-107">_cbEntryID_</span></span>
  
> <span data-ttu-id="70357-108">[in]  _lpEntryID_ 参数指向的条目标识符中的字节计数  _。_</span><span class="sxs-lookup"><span data-stu-id="70357-108">[in] The byte count in the entry identifier pointed to by the  _lpEntryID_ parameter  _._</span></span>
    
 <span data-ttu-id="70357-109">_lpEntryID_</span><span class="sxs-lookup"><span data-stu-id="70357-109">_lpEntryID_</span></span>
  
> <span data-ttu-id="70357-110">[in]指向要打开的对象的条目标识符的指针，或 NULL。</span><span class="sxs-lookup"><span data-stu-id="70357-110">[in] A pointer to the entry identifier of the object to open, or NULL.</span></span> <span data-ttu-id="70357-111">如果  _lpEntryID_ 设置为 **NULL，OpenEntry** 将打开邮件存储的根文件夹。</span><span class="sxs-lookup"><span data-stu-id="70357-111">If  _lpEntryID_ is set to NULL, **OpenEntry** opens the root folder for the message store.</span></span> 
    
 <span data-ttu-id="70357-112">_lpInterface_</span><span class="sxs-lookup"><span data-stu-id="70357-112">_lpInterface_</span></span>
  
> <span data-ttu-id="70357-113">[in]指向接口标识符的指针 (IID) 表示用于访问打开对象的接口。</span><span class="sxs-lookup"><span data-stu-id="70357-113">[in] A pointer to the interface identifier (IID) that represents the interface to be used to access the opened object.</span></span> <span data-ttu-id="70357-114">传递 NULL 会导致对象的标准接口为 ([IMAPIFolder，](imapifolderimapicontainer.md)对于要返回的邮件，则[) IMessage。](imessageimapiprop.md)</span><span class="sxs-lookup"><span data-stu-id="70357-114">Passing NULL results in the object's standard interface ([IMAPIFolder](imapifolderimapicontainer.md) for folders and [IMessage](imessageimapiprop.md) for messages) being returned.</span></span> 
    
 <span data-ttu-id="70357-115">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="70357-115">_ulFlags_</span></span>
  
> <span data-ttu-id="70357-116">[in]控制对象打开方式的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="70357-116">[in] A bitmask of flags that controls how the object is opened.</span></span> <span data-ttu-id="70357-117">可以使用以下标志：</span><span class="sxs-lookup"><span data-stu-id="70357-117">The following flags can be used:</span></span>
    
<span data-ttu-id="70357-118">MAPI_BEST_ACCESS</span><span class="sxs-lookup"><span data-stu-id="70357-118">MAPI_BEST_ACCESS</span></span> 
  
> <span data-ttu-id="70357-119">请求使用用户允许的最大网络权限和最大客户端应用程序访问权限打开对象。</span><span class="sxs-lookup"><span data-stu-id="70357-119">Requests that the object be opened by using the maximum network permissions allowed for the user and the maximum client application access.</span></span> <span data-ttu-id="70357-120">例如，如果客户端具有读/写权限，则应该使用读/写权限打开对象;如果客户端具有只读权限，则应该使用只读权限打开对象。</span><span class="sxs-lookup"><span data-stu-id="70357-120">For example, if the client has read/write permission, the object should be opened by using read/write permission; if the client has read-only permission, the object should be opened by using read-only permission.</span></span> 
    
<span data-ttu-id="70357-121">MAPI_DEFERRED_ERRORS</span><span class="sxs-lookup"><span data-stu-id="70357-121">MAPI_DEFERRED_ERRORS</span></span> 
  
> <span data-ttu-id="70357-122">允许 **OpenEntry** 在对象完全可供调用客户端使用之前成功返回。</span><span class="sxs-lookup"><span data-stu-id="70357-122">Allows **OpenEntry** to return successfully, possibly before the object is fully available to the calling client.</span></span> <span data-ttu-id="70357-123">如果该对象不可用，则进行后续对象调用可能会引发错误。</span><span class="sxs-lookup"><span data-stu-id="70357-123">If the object is not available, making a subsequent object call can raise an error.</span></span> 
    
<span data-ttu-id="70357-124">MAPI_MODIFY</span><span class="sxs-lookup"><span data-stu-id="70357-124">MAPI_MODIFY</span></span> 
  
> <span data-ttu-id="70357-125">请求读/写权限。</span><span class="sxs-lookup"><span data-stu-id="70357-125">Requests read/write permission.</span></span> <span data-ttu-id="70357-126">默认情况下，使用只读权限打开对象，客户端不应在授予读/写权限的假设下工作。</span><span class="sxs-lookup"><span data-stu-id="70357-126">By default, objects are opened with read-only permission, and clients should not work on the assumption that read/write permission is granted.</span></span> 
    
 <span data-ttu-id="70357-127">_lpulObjType_</span><span class="sxs-lookup"><span data-stu-id="70357-127">_lpulObjType_</span></span>
  
> <span data-ttu-id="70357-128">[out]指向已打开对象的类型的指针。</span><span class="sxs-lookup"><span data-stu-id="70357-128">[out] A pointer to the type of the opened object.</span></span>
    
 <span data-ttu-id="70357-129">_lppUnk_</span><span class="sxs-lookup"><span data-stu-id="70357-129">_lppUnk_</span></span>
  
> <span data-ttu-id="70357-130">[out]指向已打开对象的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="70357-130">[out] A pointer to a pointer to the opened object.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="70357-131">返回值</span><span class="sxs-lookup"><span data-stu-id="70357-131">Return value</span></span>

<span data-ttu-id="70357-132">S_OK</span><span class="sxs-lookup"><span data-stu-id="70357-132">S_OK</span></span> 
  
> <span data-ttu-id="70357-133">调用成功并返回了预期值。</span><span class="sxs-lookup"><span data-stu-id="70357-133">The call succeeded and has returned the expected value or values.</span></span>
    
<span data-ttu-id="70357-134">MAPI_E_NO_ACCESS</span><span class="sxs-lookup"><span data-stu-id="70357-134">MAPI_E_NO_ACCESS</span></span> 
  
> <span data-ttu-id="70357-135">试图修改只读对象或访问用户权限不足的对象。</span><span class="sxs-lookup"><span data-stu-id="70357-135">An attempt was made to modify a read-only object or to access an object for which the user has insufficient permissions.</span></span>
    
<span data-ttu-id="70357-136">MAPI_NO_CACHE</span><span class="sxs-lookup"><span data-stu-id="70357-136">MAPI_NO_CACHE</span></span>
  
> <span data-ttu-id="70357-137">在缓存模式下打开存储区时，客户端或服务提供商可以调用 **IMsgStore：：OpenEntry，** 设置 MAPI_NO_CACHE 标志以打开远程存储上的项目或文件夹。</span><span class="sxs-lookup"><span data-stu-id="70357-137">When a store is opened in cached mode, a client or service provider can call **IMsgStore::OpenEntry**, setting the MAPI_NO_CACHE flag to open an item or a folder on the remote store.</span></span> <span data-ttu-id="70357-138">如果在远程服务器上使用 MDB_ONLINE 标志打开邮件存储，则不需要使用 MAPI_NO_CACHE 标志。</span><span class="sxs-lookup"><span data-stu-id="70357-138">If you open the message store with the MDB_ONLINE flag on the remote server, you do not have to use the MAPI_NO_CACHE flag.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="70357-139">备注</span><span class="sxs-lookup"><span data-stu-id="70357-139">Remarks</span></span>

<span data-ttu-id="70357-140">**IMsgStore：：OpenEntry** 方法打开文件夹或邮件，并返回一个指向可用于进一步访问的接口的指针。</span><span class="sxs-lookup"><span data-stu-id="70357-140">The **IMsgStore::OpenEntry** method opens a folder or message and returns a pointer to an interface that can be used for further access.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="70357-141">打开公用存储上的文件夹条目（如文件夹和邮件）时，请使用 **IMsgStore：：OpenEntry** 而不是 [IMAPISession：：OpenEntry](imapisession-openentry.md)。</span><span class="sxs-lookup"><span data-stu-id="70357-141">When opening folder entries on a public store, such as folders and messages, use **IMsgStore::OpenEntry** instead of [IMAPISession::OpenEntry](imapisession-openentry.md).</span></span> <span data-ttu-id="70357-142">这可确保在配置文件中定义多个Exchange时公用文件夹能够正常运行。</span><span class="sxs-lookup"><span data-stu-id="70357-142">This ensures that public folders function correctly when multiple Exchange accounts are defined in a profile.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="70357-143">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="70357-143">Notes to callers</span></span>

<span data-ttu-id="70357-144">除非您在  _ulFlags_ 参数中设置了 MAPI_MODIFY 或 MAPI_BEST_ACCESS 标志，否则文件夹和邮件将自动以只读权限打开。</span><span class="sxs-lookup"><span data-stu-id="70357-144">Folders and messages are automatically opened with read-only permission, unless you set the MAPI_MODIFY or MAPI_BEST_ACCESS flag in the  _ulFlags_ parameter.</span></span> <span data-ttu-id="70357-145">设置其中一个标志并不能保证特定类型的权限;授予的权限取决于邮件存储提供程序、访问级别和对象。</span><span class="sxs-lookup"><span data-stu-id="70357-145">Setting one of these flags does not guarantee a particular type of permission; the permissions that you are granted depend on the message store provider, your access level, and the object.</span></span> <span data-ttu-id="70357-146">若要确定打开的对象的访问级别，请检索该对象PR_ACCESS_LEVEL ( [PidTagAccessLevel](pidtagaccesslevel-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="70357-146">To determine the access level of the opened object, retrieve its **PR_ACCESS_LEVEL** ([PidTagAccessLevel](pidtagaccesslevel-canonical-property.md)) property.</span></span>
  
<span data-ttu-id="70357-147">虽然 **IMsgStore：：OpenEntry** 可用于打开任何文件夹或邮件，但如果可以访问要打开的文件夹或邮件的父文件夹，则使用 [IMAPIContainer：：OpenEntry](imapicontainer-openentry.md) 方法通常更快。</span><span class="sxs-lookup"><span data-stu-id="70357-147">Although **IMsgStore::OpenEntry** can be used to open any folder or message, it is usually faster to use the [IMAPIContainer::OpenEntry](imapicontainer-openentry.md) method if you have access to the parent folder of the folder or message to be opened.</span></span> 
  
<span data-ttu-id="70357-148">检查  _lpulObjType_ 参数中返回的值，以确定返回对象类型的值是否如您预期的那样。</span><span class="sxs-lookup"><span data-stu-id="70357-148">Check the value returned in the  _lpulObjType_ parameter to determine whether the returned object type is what you expected.</span></span> <span data-ttu-id="70357-149">如果对象类型不是预期类型，将指针从  _lppUnk_ 参数强制转换到相应类型的指针。</span><span class="sxs-lookup"><span data-stu-id="70357-149">If the object type is not the expected type, cast the pointer from the  _lppUnk_ parameter to a pointer of the appropriate type.</span></span> <span data-ttu-id="70357-150">例如，如果要打开文件夹，将  _lppUnk_ 强制转换到 **类型 LPMAPIFOLDER 的指针**。</span><span class="sxs-lookup"><span data-stu-id="70357-150">For example, if you are opening a folder, cast  _lppUnk_ to a pointer of type **LPMAPIFOLDER**.</span></span>
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="70357-151">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="70357-151">MFCMAPI reference</span></span>

<span data-ttu-id="70357-152">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="70357-152">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="70357-153">**文件**</span><span class="sxs-lookup"><span data-stu-id="70357-153">**File**</span></span>|<span data-ttu-id="70357-154">**函数**</span><span class="sxs-lookup"><span data-stu-id="70357-154">**Function**</span></span>|<span data-ttu-id="70357-155">**备注**</span><span class="sxs-lookup"><span data-stu-id="70357-155">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="70357-156">MAPIFunctions.cpp</span><span class="sxs-lookup"><span data-stu-id="70357-156">MAPIFunctions.cpp</span></span>  <br/> |<span data-ttu-id="70357-157">CallOpenEntry</span><span class="sxs-lookup"><span data-stu-id="70357-157">CallOpenEntry</span></span>  <br/> |<span data-ttu-id="70357-158">MFCMAPI 使用 **IMsgStore：：OpenEntry** 方法打开与条目 ID 关联的对象。</span><span class="sxs-lookup"><span data-stu-id="70357-158">MFCMAPI uses the **IMsgStore::OpenEntry** method to open the object associated with an entry ID.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="70357-159">另请参阅</span><span class="sxs-lookup"><span data-stu-id="70357-159">See also</span></span>



[<span data-ttu-id="70357-160">IMAPIContainer::OpenEntry</span><span class="sxs-lookup"><span data-stu-id="70357-160">IMAPIContainer::OpenEntry</span></span>](imapicontainer-openentry.md)
  
[<span data-ttu-id="70357-161">IMsgStore : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="70357-161">IMsgStore : IMAPIProp</span></span>](imsgstoreimapiprop.md)


[<span data-ttu-id="70357-162">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="70357-162">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

