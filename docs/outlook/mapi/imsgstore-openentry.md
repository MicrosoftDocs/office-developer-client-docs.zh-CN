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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32309693"
---
# <a name="imsgstoreopenentry"></a><span data-ttu-id="dffd3-103">IMsgStore::OpenEntry</span><span class="sxs-lookup"><span data-stu-id="dffd3-103">IMsgStore::OpenEntry</span></span>

  
  
<span data-ttu-id="dffd3-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="dffd3-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="dffd3-105">打开一个文件夹或邮件, 并返回一个接口指针以供进一步访问。</span><span class="sxs-lookup"><span data-stu-id="dffd3-105">Opens a folder or message and returns an interface pointer for further access.</span></span> 
  
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

## <a name="parameters"></a><span data-ttu-id="dffd3-106">参数</span><span class="sxs-lookup"><span data-stu-id="dffd3-106">Parameters</span></span>

 <span data-ttu-id="dffd3-107">_cbEntryID_</span><span class="sxs-lookup"><span data-stu-id="dffd3-107">_cbEntryID_</span></span>
  
> <span data-ttu-id="dffd3-108">实时条目标识符中由_lpEntryID_参数指向的字节数 _。_</span><span class="sxs-lookup"><span data-stu-id="dffd3-108">[in] The byte count in the entry identifier pointed to by the  _lpEntryID_ parameter  _._</span></span>
    
 <span data-ttu-id="dffd3-109">_lpEntryID_</span><span class="sxs-lookup"><span data-stu-id="dffd3-109">_lpEntryID_</span></span>
  
> <span data-ttu-id="dffd3-110">实时指向要打开的对象的条目标识符的指针, 或 NULL。</span><span class="sxs-lookup"><span data-stu-id="dffd3-110">[in] A pointer to the entry identifier of the object to open, or NULL.</span></span> <span data-ttu-id="dffd3-111">如果将_lpEntryID_设置为 NULL, **OpenEntry**将打开邮件存储区的根文件夹。</span><span class="sxs-lookup"><span data-stu-id="dffd3-111">If  _lpEntryID_ is set to NULL, **OpenEntry** opens the root folder for the message store.</span></span> 
    
 <span data-ttu-id="dffd3-112">_lpInterface_</span><span class="sxs-lookup"><span data-stu-id="dffd3-112">_lpInterface_</span></span>
  
> <span data-ttu-id="dffd3-113">实时指向接口标识符 (IID) 的指针, 该接口标识符表示要用于访问打开的对象的接口。</span><span class="sxs-lookup"><span data-stu-id="dffd3-113">[in] A pointer to the interface identifier (IID) that represents the interface to be used to access the opened object.</span></span> <span data-ttu-id="dffd3-114">在对象的标准接口 ([IMAPIFolder](imapifolderimapicontainer.md)文件夹和[IMessage](imessageimapiprop.md)中的邮件) 中传递 NULL 结果。</span><span class="sxs-lookup"><span data-stu-id="dffd3-114">Passing NULL results in the object's standard interface ([IMAPIFolder](imapifolderimapicontainer.md) for folders and [IMessage](imessageimapiprop.md) for messages) being returned.</span></span> 
    
 <span data-ttu-id="dffd3-115">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="dffd3-115">_ulFlags_</span></span>
  
> <span data-ttu-id="dffd3-116">实时用于控制对象打开方式的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="dffd3-116">[in] A bitmask of flags that controls how the object is opened.</span></span> <span data-ttu-id="dffd3-117">可以使用以下标志:</span><span class="sxs-lookup"><span data-stu-id="dffd3-117">The following flags can be used:</span></span>
    
<span data-ttu-id="dffd3-118">MAPI_BEST_ACCESS</span><span class="sxs-lookup"><span data-stu-id="dffd3-118">MAPI_BEST_ACCESS</span></span> 
  
> <span data-ttu-id="dffd3-119">使用用户所允许的最大网络权限和最大客户端应用程序访问权限来请求打开对象。</span><span class="sxs-lookup"><span data-stu-id="dffd3-119">Requests that the object be opened by using the maximum network permissions allowed for the user and the maximum client application access.</span></span> <span data-ttu-id="dffd3-120">例如, 如果客户端具有读/写权限, 则应使用读/写权限打开该对象;如果客户端具有只读权限, 则应使用只读权限打开该对象。</span><span class="sxs-lookup"><span data-stu-id="dffd3-120">For example, if the client has read/write permission, the object should be opened by using read/write permission; if the client has read-only permission, the object should be opened by using read-only permission.</span></span> 
    
<span data-ttu-id="dffd3-121">MAPI_DEFERRED_ERRORS</span><span class="sxs-lookup"><span data-stu-id="dffd3-121">MAPI_DEFERRED_ERRORS</span></span> 
  
> <span data-ttu-id="dffd3-122">允许**OpenEntry**成功返回, 这可能是在对象完全可用于调用客户端之前。</span><span class="sxs-lookup"><span data-stu-id="dffd3-122">Allows **OpenEntry** to return successfully, possibly before the object is fully available to the calling client.</span></span> <span data-ttu-id="dffd3-123">如果该对象不可用, 则进行后续的对象调用可能会引发错误。</span><span class="sxs-lookup"><span data-stu-id="dffd3-123">If the object is not available, making a subsequent object call can raise an error.</span></span> 
    
<span data-ttu-id="dffd3-124">MAPI_MODIFY</span><span class="sxs-lookup"><span data-stu-id="dffd3-124">MAPI_MODIFY</span></span> 
  
> <span data-ttu-id="dffd3-125">请求读取/写入权限。</span><span class="sxs-lookup"><span data-stu-id="dffd3-125">Requests read/write permission.</span></span> <span data-ttu-id="dffd3-126">默认情况下, 将使用只读权限打开对象, 并且客户端不应在假定已授予读/写权限时才起作用。</span><span class="sxs-lookup"><span data-stu-id="dffd3-126">By default, objects are opened with read-only permission, and clients should not work on the assumption that read/write permission is granted.</span></span> 
    
 <span data-ttu-id="dffd3-127">_lpulObjType_</span><span class="sxs-lookup"><span data-stu-id="dffd3-127">_lpulObjType_</span></span>
  
> <span data-ttu-id="dffd3-128">排除一个指针, 指向打开的对象的类型。</span><span class="sxs-lookup"><span data-stu-id="dffd3-128">[out] A pointer to the type of the opened object.</span></span>
    
 <span data-ttu-id="dffd3-129">_lppUnk_</span><span class="sxs-lookup"><span data-stu-id="dffd3-129">_lppUnk_</span></span>
  
> <span data-ttu-id="dffd3-130">排除指向打开的对象的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="dffd3-130">[out] A pointer to a pointer to the opened object.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="dffd3-131">返回值</span><span class="sxs-lookup"><span data-stu-id="dffd3-131">Return value</span></span>

<span data-ttu-id="dffd3-132">S_OK</span><span class="sxs-lookup"><span data-stu-id="dffd3-132">S_OK</span></span> 
  
> <span data-ttu-id="dffd3-133">调用成功, 并返回了所需的值或值。</span><span class="sxs-lookup"><span data-stu-id="dffd3-133">The call succeeded and has returned the expected value or values.</span></span>
    
<span data-ttu-id="dffd3-134">MAPI_E_NO_ACCESS</span><span class="sxs-lookup"><span data-stu-id="dffd3-134">MAPI_E_NO_ACCESS</span></span> 
  
> <span data-ttu-id="dffd3-135">试图修改只读对象或访问用户拥有的对象权限不足的对象。</span><span class="sxs-lookup"><span data-stu-id="dffd3-135">An attempt was made to modify a read-only object or to access an object for which the user has insufficient permissions.</span></span>
    
<span data-ttu-id="dffd3-136">MAPI_NO_CACHE</span><span class="sxs-lookup"><span data-stu-id="dffd3-136">MAPI_NO_CACHE</span></span>
  
> <span data-ttu-id="dffd3-137">在缓存模式下打开存储时, 客户端或服务提供程序可以调用**IMsgStore:: OpenEntry**, 将 MAPI_NO_CACHE 标志设置为打开远程存储上的项目或文件夹。</span><span class="sxs-lookup"><span data-stu-id="dffd3-137">When a store is opened in cached mode, a client or service provider can call **IMsgStore::OpenEntry**, setting the MAPI_NO_CACHE flag to open an item or a folder on the remote store.</span></span> <span data-ttu-id="dffd3-138">如果使用远程服务器上的 MDB_ONLINE 标志打开邮件存储区, 则无需使用 MAPI_NO_CACHE 标志。</span><span class="sxs-lookup"><span data-stu-id="dffd3-138">If you open the message store with the MDB_ONLINE flag on the remote server, you do not have to use the MAPI_NO_CACHE flag.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="dffd3-139">注解</span><span class="sxs-lookup"><span data-stu-id="dffd3-139">Remarks</span></span>

<span data-ttu-id="dffd3-140">**IMsgStore:: OpenEntry**方法打开一个文件夹或邮件, 并返回指向可用于进一步访问的接口的指针。</span><span class="sxs-lookup"><span data-stu-id="dffd3-140">The **IMsgStore::OpenEntry** method opens a folder or message and returns a pointer to an interface that can be used for further access.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="dffd3-141">在公用存储 (如文件夹和邮件) 上打开文件夹条目时, 请使用**IMsgStore:: OpenEntry**而不是[IMAPISession:: OpenEntry](imapisession-openentry.md)。</span><span class="sxs-lookup"><span data-stu-id="dffd3-141">When opening folder entries on a public store, such as folders and messages, use **IMsgStore::OpenEntry** instead of [IMAPISession::OpenEntry](imapisession-openentry.md).</span></span> <span data-ttu-id="dffd3-142">这样可确保公用文件夹在配置文件中定义了多个 Exchange 帐户时能够正常工作。</span><span class="sxs-lookup"><span data-stu-id="dffd3-142">This ensures that public folders function correctly when multiple Exchange accounts are defined in a profile.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="dffd3-143">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="dffd3-143">Notes to callers</span></span>

<span data-ttu-id="dffd3-144">除非您在_ulFlags_参数中设置 MAPI_MODIFY 或 MAPI_BEST_ACCESS 标志, 否则会自动以只读权限打开文件夹和邮件。</span><span class="sxs-lookup"><span data-stu-id="dffd3-144">Folders and messages are automatically opened with read-only permission, unless you set the MAPI_MODIFY or MAPI_BEST_ACCESS flag in the  _ulFlags_ parameter.</span></span> <span data-ttu-id="dffd3-145">设置其中一个标志并不能保证特定类型的权限;您授予的权限取决于邮件存储提供程序、您的访问级别和对象。</span><span class="sxs-lookup"><span data-stu-id="dffd3-145">Setting one of these flags does not guarantee a particular type of permission; the permissions that you are granted depend on the message store provider, your access level, and the object.</span></span> <span data-ttu-id="dffd3-146">若要确定打开的对象的访问级别, 请检索其**PR_ACCESS_LEVEL** ([PidTagAccessLevel](pidtagaccesslevel-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="dffd3-146">To determine the access level of the opened object, retrieve its **PR_ACCESS_LEVEL** ([PidTagAccessLevel](pidtagaccesslevel-canonical-property.md)) property.</span></span>
  
<span data-ttu-id="dffd3-147">虽然**IMsgStore:: OpenEntry**可用于打开任何文件夹或邮件, 但如果您有权访问要打开的文件夹或邮件的父文件夹, 则使用[IMAPIContainer:: OpenEntry](imapicontainer-openentry.md)方法通常会更快。</span><span class="sxs-lookup"><span data-stu-id="dffd3-147">Although **IMsgStore::OpenEntry** can be used to open any folder or message, it is usually faster to use the [IMAPIContainer::OpenEntry](imapicontainer-openentry.md) method if you have access to the parent folder of the folder or message to be opened.</span></span> 
  
<span data-ttu-id="dffd3-148">检查_lpulObjType_参数中返回的值, 以确定返回的对象类型是否符合您的预期。</span><span class="sxs-lookup"><span data-stu-id="dffd3-148">Check the value returned in the  _lpulObjType_ parameter to determine whether the returned object type is what you expected.</span></span> <span data-ttu-id="dffd3-149">如果对象类型不是预期类型, 则将指针从_lppUnk_参数转换为适当类型的指针。</span><span class="sxs-lookup"><span data-stu-id="dffd3-149">If the object type is not the expected type, cast the pointer from the  _lppUnk_ parameter to a pointer of the appropriate type.</span></span> <span data-ttu-id="dffd3-150">例如, 如果您打开一个文件夹, 则会将_lppUnk_转换为**LPMAPIFOLDER**类型的指针。</span><span class="sxs-lookup"><span data-stu-id="dffd3-150">For example, if you are opening a folder, cast  _lppUnk_ to a pointer of type **LPMAPIFOLDER**.</span></span>
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="dffd3-151">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="dffd3-151">MFCMAPI reference</span></span>

<span data-ttu-id="dffd3-152">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="dffd3-152">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="dffd3-153">**文件**</span><span class="sxs-lookup"><span data-stu-id="dffd3-153">**File**</span></span>|<span data-ttu-id="dffd3-154">**函数**</span><span class="sxs-lookup"><span data-stu-id="dffd3-154">**Function**</span></span>|<span data-ttu-id="dffd3-155">**备注**</span><span class="sxs-lookup"><span data-stu-id="dffd3-155">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="dffd3-156">MAPIFunctions</span><span class="sxs-lookup"><span data-stu-id="dffd3-156">MAPIFunctions.cpp</span></span>  <br/> |<span data-ttu-id="dffd3-157">CallOpenEntry</span><span class="sxs-lookup"><span data-stu-id="dffd3-157">CallOpenEntry</span></span>  <br/> |<span data-ttu-id="dffd3-158">MFCMAPI 使用**IMsgStore:: OpenEntry**方法打开与条目 ID 关联的对象。</span><span class="sxs-lookup"><span data-stu-id="dffd3-158">MFCMAPI uses the **IMsgStore::OpenEntry** method to open the object associated with an entry ID.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="dffd3-159">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dffd3-159">See also</span></span>



[<span data-ttu-id="dffd3-160">IMAPIContainer::OpenEntry</span><span class="sxs-lookup"><span data-stu-id="dffd3-160">IMAPIContainer::OpenEntry</span></span>](imapicontainer-openentry.md)
  
[<span data-ttu-id="dffd3-161">IMsgStore : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="dffd3-161">IMsgStore : IMAPIProp</span></span>](imsgstoreimapiprop.md)


[<span data-ttu-id="dffd3-162">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="dffd3-162">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

