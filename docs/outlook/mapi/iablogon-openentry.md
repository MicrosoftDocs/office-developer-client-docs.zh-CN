---
title: IABLogonOpenEntry
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IABLogon.OpenEntry
api_type:
- COM
ms.assetid: 1cfb82f7-5215-4faa-af25-5b1da7e31209
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 70f61ef553350f08eed96c1ee4e9ab790359d1fc
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33409228"
---
# <a name="iablogonopenentry"></a><span data-ttu-id="c7b71-103">IABLogon::OpenEntry</span><span class="sxs-lookup"><span data-stu-id="c7b71-103">IABLogon::OpenEntry</span></span>

  
  
<span data-ttu-id="c7b71-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="c7b71-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="c7b71-105">打开容器、消息传送用户或通讯组列表，并返回指向接口实现以进一步访问的指针。</span><span class="sxs-lookup"><span data-stu-id="c7b71-105">Opens a container, messaging user, or distribution list, and returns a pointer to an interface implementation to provide further access.</span></span>
  
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

## <a name="parameters"></a><span data-ttu-id="c7b71-106">参数</span><span class="sxs-lookup"><span data-stu-id="c7b71-106">Parameters</span></span>

 <span data-ttu-id="c7b71-107">_cbEntryID_</span><span class="sxs-lookup"><span data-stu-id="c7b71-107">_cbEntryID_</span></span>
  
> <span data-ttu-id="c7b71-108">[in]  _lpEntryID_ 参数指向的条目标识符中的字节计数。</span><span class="sxs-lookup"><span data-stu-id="c7b71-108">[in] The byte count in the entry identifier pointed to by the  _lpEntryID_ parameter.</span></span> 
    
 <span data-ttu-id="c7b71-109">_lpEntryID_</span><span class="sxs-lookup"><span data-stu-id="c7b71-109">_lpEntryID_</span></span>
  
> <span data-ttu-id="c7b71-110">[in]指向要打开的容器、消息传送用户或通讯组列表的条目标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="c7b71-110">[in] A pointer to the entry identifier of the container, messaging user, or distribution list to open.</span></span>
    
 <span data-ttu-id="c7b71-111">_lpInterface_</span><span class="sxs-lookup"><span data-stu-id="c7b71-111">_lpInterface_</span></span>
  
> <span data-ttu-id="c7b71-112">[in]指向接口标识符的指针 (IID) 表示用于访问打开对象的接口。</span><span class="sxs-lookup"><span data-stu-id="c7b71-112">[in] A pointer to the interface identifier (IID) that represents the interface to be used to access the open object.</span></span> <span data-ttu-id="c7b71-113">传递 NULL 将返回对象的标准接口的标识符。</span><span class="sxs-lookup"><span data-stu-id="c7b71-113">Passing NULL returns the identifier for the object's standard interface.</span></span> <span data-ttu-id="c7b71-114">对于容器，标准接口是 [IABContainer ： IMAPIContainer](iabcontainerimapicontainer.md)。</span><span class="sxs-lookup"><span data-stu-id="c7b71-114">For containers, the standard interface is [IABContainer : IMAPIContainer](iabcontainerimapicontainer.md).</span></span> <span data-ttu-id="c7b71-115">通讯簿对象的标准接口是 [IDistList ： IMAPIContainer](idistlistimapicontainer.md) 表示通讯组列表和 [IMailUser ： IMAPIProp](imailuserimapiprop.md) 消息用户。</span><span class="sxs-lookup"><span data-stu-id="c7b71-115">The standard interfaces for address book objects are [IDistList : IMAPIContainer](idistlistimapicontainer.md) for a distribution list and [IMailUser : IMAPIProp](imailuserimapiprop.md) for a messaging user.</span></span> 
    
 <span data-ttu-id="c7b71-116">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="c7b71-116">_ulFlags_</span></span>
  
> <span data-ttu-id="c7b71-117">[in]控制对象打开方式的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="c7b71-117">[in] A bitmask of flags that controls how the object is opened.</span></span> <span data-ttu-id="c7b71-118">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="c7b71-118">The following flags can be set:</span></span>
    
<span data-ttu-id="c7b71-119">MAPI_BEST_ACCESS</span><span class="sxs-lookup"><span data-stu-id="c7b71-119">MAPI_BEST_ACCESS</span></span> 
  
> <span data-ttu-id="c7b71-120">请求使用用户允许的最大网络权限和最大客户端应用程序访问权限打开对象。</span><span class="sxs-lookup"><span data-stu-id="c7b71-120">Requests that the object be opened with the maximum network permissions allowed for the user and the maximum client application access.</span></span> <span data-ttu-id="c7b71-121">例如，如果客户端具有读/写权限，则应该使用读/写权限打开对象;如果客户端具有只读权限，则应该使用只读权限打开对象。</span><span class="sxs-lookup"><span data-stu-id="c7b71-121">For example, if the client has read/write permission, the object should be opened with read/write permission; if the client has read-only permission, the object should be opened with read-only permission.</span></span>
    
<span data-ttu-id="c7b71-122">MAPI_DEFERRED_ERRORS</span><span class="sxs-lookup"><span data-stu-id="c7b71-122">MAPI_DEFERRED_ERRORS</span></span> 
  
> <span data-ttu-id="c7b71-123">允许 **OpenEntry** 方法成功返回，可能在调用客户端完全访问对象之前。</span><span class="sxs-lookup"><span data-stu-id="c7b71-123">Allows the **OpenEntry** method to return successfully, possibly before the calling client has fully accessed the object.</span></span> <span data-ttu-id="c7b71-124">如果未访问该对象，则进行后续对象调用可能会引发错误。</span><span class="sxs-lookup"><span data-stu-id="c7b71-124">If the object is not accessed, making a subsequent object call can raise an error.</span></span> 
    
<span data-ttu-id="c7b71-125">MAPI_MODIFY</span><span class="sxs-lookup"><span data-stu-id="c7b71-125">MAPI_MODIFY</span></span> 
  
> <span data-ttu-id="c7b71-126">请求读/写权限。</span><span class="sxs-lookup"><span data-stu-id="c7b71-126">Requests read/write permission.</span></span> <span data-ttu-id="c7b71-127">默认情况下，使用只读访问权限打开对象，客户端不应假定已授予读/写权限。</span><span class="sxs-lookup"><span data-stu-id="c7b71-127">By default, objects are opened with read-only access, and clients should not assume that read/write permission has been granted.</span></span>
    
 <span data-ttu-id="c7b71-128">_lpulObjType_</span><span class="sxs-lookup"><span data-stu-id="c7b71-128">_lpulObjType_</span></span>
  
> <span data-ttu-id="c7b71-129">[out]指向已打开对象的类型的指针。</span><span class="sxs-lookup"><span data-stu-id="c7b71-129">[out] A pointer to the type of the opened object.</span></span>
    
 <span data-ttu-id="c7b71-130">_lppUnk_</span><span class="sxs-lookup"><span data-stu-id="c7b71-130">_lppUnk_</span></span>
  
> <span data-ttu-id="c7b71-131">[out]指向已打开对象的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="c7b71-131">[out] A pointer to a pointer to the opened object.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="c7b71-132">备注</span><span class="sxs-lookup"><span data-stu-id="c7b71-132">Remarks</span></span>

<span data-ttu-id="c7b71-133">S_OK</span><span class="sxs-lookup"><span data-stu-id="c7b71-133">S_OK</span></span> 
  
> <span data-ttu-id="c7b71-134">已成功打开对象。</span><span class="sxs-lookup"><span data-stu-id="c7b71-134">The object was successfully opened.</span></span>
    
<span data-ttu-id="c7b71-135">MAPI_E_NO_ACCESS</span><span class="sxs-lookup"><span data-stu-id="c7b71-135">MAPI_E_NO_ACCESS</span></span> 
  
> <span data-ttu-id="c7b71-136">用户没有足够的权限打开对象，或者试图打开具有读/写权限的只读对象。</span><span class="sxs-lookup"><span data-stu-id="c7b71-136">Either the user has insufficient permissions to open the object, or an attempt was made to open a read-only object with read/write permission.</span></span>
    
<span data-ttu-id="c7b71-137">MAPI_E_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="c7b71-137">MAPI_E_NOT_FOUND</span></span> 
  
> <span data-ttu-id="c7b71-138">_lpEntryID_ 指定的条目标识符不表示对象。</span><span class="sxs-lookup"><span data-stu-id="c7b71-138">The entry identifier specified by  _lpEntryID_ does not represent an object.</span></span> 
    
<span data-ttu-id="c7b71-139">MAPI_E_UNKNOWN_ENTRYID</span><span class="sxs-lookup"><span data-stu-id="c7b71-139">MAPI_E_UNKNOWN_ENTRYID</span></span> 
  
> <span data-ttu-id="c7b71-140">_lpEntryID_ 参数中的条目标识符不是通讯簿提供程序识别的格式。</span><span class="sxs-lookup"><span data-stu-id="c7b71-140">The entry identifier in the  _lpEntryID_ parameter is not of a format recognized by the address book provider.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="c7b71-141">备注</span><span class="sxs-lookup"><span data-stu-id="c7b71-141">Remarks</span></span>

<span data-ttu-id="c7b71-142">MAPI 调用 **OpenEntry** 方法打开容器、邮件传递用户或通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="c7b71-142">MAPI calls the **OpenEntry** method to open a container, messaging user, or distribution list.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="c7b71-143">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="c7b71-143">Notes to implementers</span></span>

<span data-ttu-id="c7b71-144">在 MAPI 调用 **OpenEntry** 方法之前，它确定  _lpEntryID_ 参数中的条目标识符属于您而不是其他提供程序。</span><span class="sxs-lookup"><span data-stu-id="c7b71-144">Before MAPI calls your **OpenEntry** method, it determines that the entry identifier in the  _lpEntryID_ parameter belongs to you and not to another provider.</span></span> <span data-ttu-id="c7b71-145">MAPI 通过以下方法实现此操作：将条目标识符中的 [MAPIUID](mapiuid.md)结构与在启动时通过调用 [IMAPISupport：：SetProviderUID](imapisupport-setprovideruid.md)方法注册的 **MAPIUID** 相匹配。</span><span class="sxs-lookup"><span data-stu-id="c7b71-145">MAPI does this by matching the [MAPIUID](mapiuid.md) structure in the entry identifier with the **MAPIUID** that you registered by calling the [IMAPISupport::SetProviderUID](imapisupport-setprovideruid.md) method at startup.</span></span> 
  
<span data-ttu-id="c7b71-146">除非在  _ulFlags_ 参数中设置了 MAPI_MODIFY 或 MAPI_BEST_ACCESS 标志，否则以只读状态打开该对象。</span><span class="sxs-lookup"><span data-stu-id="c7b71-146">Open the object as read-only, unless the MAPI_MODIFY or MAPI_BEST_ACCESS flag is set in the  _ulFlags_ parameter.</span></span> <span data-ttu-id="c7b71-147">如果您不允许对请求的对象进行修改，则完全不要打开该对象并返回MAPI_E_NO_ACCESS。</span><span class="sxs-lookup"><span data-stu-id="c7b71-147">If you do not allow modification for the requested object, do not open the object at all and return MAPI_E_NO_ACCESS.</span></span> 
  
<span data-ttu-id="c7b71-148">如果 MAPI 为  _lpEntryID_ 传递 NULL，请打开容器层次结构中的根容器。</span><span class="sxs-lookup"><span data-stu-id="c7b71-148">If MAPI passes NULL for  _lpEntryID_, open the root container in your container hierarchy.</span></span>
  
<span data-ttu-id="c7b71-149">要求您打开的对象可能是从另一个提供程序复制的对象。</span><span class="sxs-lookup"><span data-stu-id="c7b71-149">The object that you are being asked to open might be an object copied from another provider.</span></span> <span data-ttu-id="c7b71-150">在这种情况下，它将支持[PidTagTemplateid PR_TEMPLATEID (PidTagTemplateid](pidtagtemplateid-canonical-property.md)) 属性。 </span><span class="sxs-lookup"><span data-stu-id="c7b71-150">In this case, it will support the **PR_TEMPLATEID** ([PidTagTemplateid](pidtagtemplateid-canonical-property.md)) property.</span></span> <span data-ttu-id="c7b71-151">如果对象支持此属性，请调用 [IMAPISupport：：OpenTemplateID](imapisupport-opentemplateid.md)方法以绑定到在外提供程序中为此条目的代码，在 _lpTemplateID_ 参数中传递 **PR_TEMPLATEID，** 在 _ulTemplateFlags_ 参数中传递 0。</span><span class="sxs-lookup"><span data-stu-id="c7b71-151">If the object does support this property, call the [IMAPISupport::OpenTemplateID](imapisupport-opentemplateid.md) method to bind to code for this entry in the foreign provider, passing **PR_TEMPLATEID** in the  _lpTemplateID_ parameter and 0 in the  _ulTemplateFlags_ parameter.</span></span> <span data-ttu-id="c7b71-152">**IMAPISupport：：OpenTemplateID** 在调用外提供程序 [的 IABLogon：：OpenTemplateID](iablogon-opentemplateid.md) 方法时将此信息传递给该外提供程序。</span><span class="sxs-lookup"><span data-stu-id="c7b71-152">**IMAPISupport::OpenTemplateID** passes this information to the foreign provider in a call to the foreign provider's [IABLogon::OpenTemplateID](iablogon-opentemplateid.md) method.</span></span> <span data-ttu-id="c7b71-153">如果 **IMAPISupport：：OpenTemplateID** 引发错误（通常是由于配置文件中的外提供程序不可用或未包含在配置文件中）尝试继续，将未绑定条目视为只读。</span><span class="sxs-lookup"><span data-stu-id="c7b71-153">If **IMAPISupport::OpenTemplateID** raises an error, usually because the foreign provider is unavailable or not included in the profile, try to continue by treating the unbound entry as read-only.</span></span> <span data-ttu-id="c7b71-154">有关打开外通讯簿条目的信息，请参阅代理 [主机通讯簿提供程序](acting-as-a-host-address-book-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="c7b71-154">For more information about opening foreign address book entries, see [Acting as a Host Address Book Provider](acting-as-a-host-address-book-provider.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="c7b71-155">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c7b71-155">See also</span></span>



[<span data-ttu-id="c7b71-156">IABLogon : IUnknown</span><span class="sxs-lookup"><span data-stu-id="c7b71-156">IABLogon : IUnknown</span></span>](iablogoniunknown.md)

