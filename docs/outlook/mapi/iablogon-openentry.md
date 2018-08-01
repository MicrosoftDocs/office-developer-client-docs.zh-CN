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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 53dfb62bb33a4941e2b5627e729763101e24319d
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775211"
---
# <a name="iablogonopenentry"></a><span data-ttu-id="ac8e3-103">IABLogon::OpenEntry</span><span class="sxs-lookup"><span data-stu-id="ac8e3-103">IABLogon::OpenEntry</span></span>

  
  
<span data-ttu-id="ac8e3-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="ac8e3-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="ac8e3-105">打开的容器，消息用户或通讯组列表，并返回指向接口实现，以提供更多访问的指针。</span><span class="sxs-lookup"><span data-stu-id="ac8e3-105">Opens a container, messaging user, or distribution list, and returns a pointer to an interface implementation to provide further access.</span></span>
  
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

## <a name="parameters"></a><span data-ttu-id="ac8e3-106">参数</span><span class="sxs-lookup"><span data-stu-id="ac8e3-106">Parameters</span></span>

 <span data-ttu-id="ac8e3-107">_cbEntryID_</span><span class="sxs-lookup"><span data-stu-id="ac8e3-107">_cbEntryID_</span></span>
  
> <span data-ttu-id="ac8e3-108">[in]在_lpEntryID_参数指向的项标识符的字节数。</span><span class="sxs-lookup"><span data-stu-id="ac8e3-108">[in] The byte count in the entry identifier pointed to by the  _lpEntryID_ parameter.</span></span> 
    
 <span data-ttu-id="ac8e3-109">_lpEntryID_</span><span class="sxs-lookup"><span data-stu-id="ac8e3-109">_lpEntryID_</span></span>
  
> <span data-ttu-id="ac8e3-110">[in]指向该容器，消息用户或通讯组列表，以打开的项标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="ac8e3-110">[in] A pointer to the entry identifier of the container, messaging user, or distribution list to open.</span></span>
    
 <span data-ttu-id="ac8e3-111">_lpInterface_</span><span class="sxs-lookup"><span data-stu-id="ac8e3-111">_lpInterface_</span></span>
  
> <span data-ttu-id="ac8e3-112">[in]指向接口标识 (IID) 值，该值代表要用于访问打开的对象的接口的指针。</span><span class="sxs-lookup"><span data-stu-id="ac8e3-112">[in] A pointer to the interface identifier (IID) that represents the interface to be used to access the open object.</span></span> <span data-ttu-id="ac8e3-113">如果传递 NULL 返回对象的标准接口的标识符。</span><span class="sxs-lookup"><span data-stu-id="ac8e3-113">Passing NULL returns the identifier for the object's standard interface.</span></span> <span data-ttu-id="ac8e3-114">对于容器，标准接口是[IABContainer: IMAPIContainer](iabcontainerimapicontainer.md)。</span><span class="sxs-lookup"><span data-stu-id="ac8e3-114">For containers, the standard interface is [IABContainer : IMAPIContainer](iabcontainerimapicontainer.md).</span></span> <span data-ttu-id="ac8e3-115">标准接口的地址簿对象是[IDistList: IMAPIContainer](idistlistimapicontainer.md)通讯组列表和[IMailUser: IMAPIProp](imailuserimapiprop.md)消息用户。</span><span class="sxs-lookup"><span data-stu-id="ac8e3-115">The standard interfaces for address book objects are [IDistList : IMAPIContainer](idistlistimapicontainer.md) for a distribution list and [IMailUser : IMAPIProp](imailuserimapiprop.md) for a messaging user.</span></span> 
    
 <span data-ttu-id="ac8e3-116">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="ac8e3-116">_ulFlags_</span></span>
  
> <span data-ttu-id="ac8e3-117">[in]位掩码的标志，控制如何打开对象。</span><span class="sxs-lookup"><span data-stu-id="ac8e3-117">[in] A bitmask of flags that controls how the object is opened.</span></span> <span data-ttu-id="ac8e3-118">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="ac8e3-118">The following flags can be set:</span></span>
    
<span data-ttu-id="ac8e3-119">MAPI_BEST_ACCESS</span><span class="sxs-lookup"><span data-stu-id="ac8e3-119">MAPI_BEST_ACCESS</span></span> 
  
> <span data-ttu-id="ac8e3-120">请求的用户和最大客户端应用程序访问允许的最大网络权限打开对象。</span><span class="sxs-lookup"><span data-stu-id="ac8e3-120">Requests that the object be opened with the maximum network permissions allowed for the user and the maximum client application access.</span></span> <span data-ttu-id="ac8e3-121">例如，如果客户端具有读/写权限，该对象应打开具有读/写权限;如果客户端具有只读权限，则应具有只读权限打开对象。</span><span class="sxs-lookup"><span data-stu-id="ac8e3-121">For example, if the client has read/write permission, the object should be opened with read/write permission; if the client has read-only permission, the object should be opened with read-only permission.</span></span>
    
<span data-ttu-id="ac8e3-122">MAPI_DEFERRED_ERRORS</span><span class="sxs-lookup"><span data-stu-id="ac8e3-122">MAPI_DEFERRED_ERRORS</span></span> 
  
> <span data-ttu-id="ac8e3-123">允许**OpenEntry**方法可返回成功，可能之前调用客户端具有完全访问对象。</span><span class="sxs-lookup"><span data-stu-id="ac8e3-123">Allows the **OpenEntry** method to return successfully, possibly before the calling client has fully accessed the object.</span></span> <span data-ttu-id="ac8e3-124">如果对象不能访问，则进行后续对象呼叫会引发错误。</span><span class="sxs-lookup"><span data-stu-id="ac8e3-124">If the object is not accessed, making a subsequent object call can raise an error.</span></span> 
    
<span data-ttu-id="ac8e3-125">MAPI_MODIFY</span><span class="sxs-lookup"><span data-stu-id="ac8e3-125">MAPI_MODIFY</span></span> 
  
> <span data-ttu-id="ac8e3-126">请求读/写权限。</span><span class="sxs-lookup"><span data-stu-id="ac8e3-126">Requests read/write permission.</span></span> <span data-ttu-id="ac8e3-127">默认情况下，对象打开具有只读访问权限和客户端不应假定已被授予读/写权限。</span><span class="sxs-lookup"><span data-stu-id="ac8e3-127">By default, objects are opened with read-only access, and clients should not assume that read/write permission has been granted.</span></span>
    
 <span data-ttu-id="ac8e3-128">_lpulObjType_</span><span class="sxs-lookup"><span data-stu-id="ac8e3-128">_lpulObjType_</span></span>
  
> <span data-ttu-id="ac8e3-129">[输出]一个指向打开的对象的类型。</span><span class="sxs-lookup"><span data-stu-id="ac8e3-129">[out] A pointer to the type of the opened object.</span></span>
    
 <span data-ttu-id="ac8e3-130">_lppUnk_</span><span class="sxs-lookup"><span data-stu-id="ac8e3-130">_lppUnk_</span></span>
  
> <span data-ttu-id="ac8e3-131">[输出]指向打开的对象的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="ac8e3-131">[out] A pointer to a pointer to the opened object.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="ac8e3-132">说明</span><span class="sxs-lookup"><span data-stu-id="ac8e3-132">Remarks</span></span>

<span data-ttu-id="ac8e3-133">S_OK</span><span class="sxs-lookup"><span data-stu-id="ac8e3-133">S_OK</span></span> 
  
> <span data-ttu-id="ac8e3-134">成功打开对象。</span><span class="sxs-lookup"><span data-stu-id="ac8e3-134">The object was successfully opened.</span></span>
    
<span data-ttu-id="ac8e3-135">MAPI_E_NO_ACCESS</span><span class="sxs-lookup"><span data-stu-id="ac8e3-135">MAPI_E_NO_ACCESS</span></span> 
  
> <span data-ttu-id="ac8e3-136">用户具有权限不足，无法打开对象，或尝试打开只读对象具有读/写权限。</span><span class="sxs-lookup"><span data-stu-id="ac8e3-136">Either the user has insufficient permissions to open the object, or an attempt was made to open a read-only object with read/write permission.</span></span>
    
<span data-ttu-id="ac8e3-137">MAPI_E_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="ac8e3-137">MAPI_E_NOT_FOUND</span></span> 
  
> <span data-ttu-id="ac8e3-138">指定_lpEntryID_的项标识符不代表一个对象。</span><span class="sxs-lookup"><span data-stu-id="ac8e3-138">The entry identifier specified by  _lpEntryID_ does not represent an object.</span></span> 
    
<span data-ttu-id="ac8e3-139">MAPI_E_UNKNOWN_ENTRYID</span><span class="sxs-lookup"><span data-stu-id="ac8e3-139">MAPI_E_UNKNOWN_ENTRYID</span></span> 
  
> <span data-ttu-id="ac8e3-140">_LpEntryID_参数中的项标识符不是格式的识别通讯簿提供程序。</span><span class="sxs-lookup"><span data-stu-id="ac8e3-140">The entry identifier in the  _lpEntryID_ parameter is not of a format recognized by the address book provider.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="ac8e3-141">说明</span><span class="sxs-lookup"><span data-stu-id="ac8e3-141">Remarks</span></span>

<span data-ttu-id="ac8e3-142">MAPI 调用**OpenEntry**方法打开容器中，消息用户或通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="ac8e3-142">MAPI calls the **OpenEntry** method to open a container, messaging user, or distribution list.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="ac8e3-143">针对实施者的注释</span><span class="sxs-lookup"><span data-stu-id="ac8e3-143">Notes to implementers</span></span>

<span data-ttu-id="ac8e3-144">MAPI 调用**OpenEntry**方法之前，它确定_lpEntryID_参数中的项标识符所属给您，而不适用于其他提供程序。</span><span class="sxs-lookup"><span data-stu-id="ac8e3-144">Before MAPI calls your **OpenEntry** method, it determines that the entry identifier in the  _lpEntryID_ parameter belongs to you and not to another provider.</span></span> <span data-ttu-id="ac8e3-145">MAPI 匹配具有在启动时调用[IMAPISupport::SetProviderUID](imapisupport-setprovideruid.md)方法来注册**MAPIUID**的项标识符的[MAPIUID](mapiuid.md)结构来达到此目的。</span><span class="sxs-lookup"><span data-stu-id="ac8e3-145">MAPI does this by matching the [MAPIUID](mapiuid.md) structure in the entry identifier with the **MAPIUID** that you registered by calling the [IMAPISupport::SetProviderUID](imapisupport-setprovideruid.md) method at startup.</span></span> 
  
<span data-ttu-id="ac8e3-146">除非 MAPI_MODIFY 或 MAPI_BEST_ACCESS 标志设置_ulFlags_参数中打开以只读方式，该对象。</span><span class="sxs-lookup"><span data-stu-id="ac8e3-146">Open the object as read-only, unless the MAPI_MODIFY or MAPI_BEST_ACCESS flag is set in the  _ulFlags_ parameter.</span></span> <span data-ttu-id="ac8e3-147">如果不允许请求的对象的修改，不要在所有打开的对象并返回 MAPI_E_NO_ACCESS。</span><span class="sxs-lookup"><span data-stu-id="ac8e3-147">If you do not allow modification for the requested object, do not open the object at all and return MAPI_E_NO_ACCESS.</span></span> 
  
<span data-ttu-id="ac8e3-148">MAPI 的_lpEntryID_传递 NULL，如果您容器层次结构中打开根容器。</span><span class="sxs-lookup"><span data-stu-id="ac8e3-148">If MAPI passes NULL for  _lpEntryID_, open the root container in your container hierarchy.</span></span>
  
<span data-ttu-id="ac8e3-149">您需要打开的对象可能是其他提供程序从复制的对象。</span><span class="sxs-lookup"><span data-stu-id="ac8e3-149">The object that you are being asked to open might be an object copied from another provider.</span></span> <span data-ttu-id="ac8e3-150">在这种情况下，它将支持**PR_TEMPLATEID** ([PidTagTemplateid](pidtagtemplateid-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="ac8e3-150">In this case, it will support the **PR_TEMPLATEID** ([PidTagTemplateid](pidtagtemplateid-canonical-property.md)) property.</span></span> <span data-ttu-id="ac8e3-151">如果对象不支持此属性，调用[IMAPISupport::OpenTemplateID](imapisupport-opentemplateid.md)方法以绑定到此项在外的提供程序，传递**PR_TEMPLATEID** _lpTemplateID_参数和_ulTemplateFlags 0 中的代码_参数。</span><span class="sxs-lookup"><span data-stu-id="ac8e3-151">If the object does support this property, call the [IMAPISupport::OpenTemplateID](imapisupport-opentemplateid.md) method to bind to code for this entry in the foreign provider, passing **PR_TEMPLATEID** in the  _lpTemplateID_ parameter and 0 in the  _ulTemplateFlags_ parameter.</span></span> <span data-ttu-id="ac8e3-152">**IMAPISupport::OpenTemplateID**将此信息传递给外提供程序的[IABLogon::OpenTemplateID](iablogon-opentemplateid.md)方法调用中的外提供程序。</span><span class="sxs-lookup"><span data-stu-id="ac8e3-152">**IMAPISupport::OpenTemplateID** passes this information to the foreign provider in a call to the foreign provider's [IABLogon::OpenTemplateID](iablogon-opentemplateid.md) method.</span></span> <span data-ttu-id="ac8e3-153">如果**IMAPISupport::OpenTemplateID**将引发错误，通常外的提供程序是不可用或不包含在该配置文件，因为尝试继续通过将视为只读的绑定的条目。</span><span class="sxs-lookup"><span data-stu-id="ac8e3-153">If **IMAPISupport::OpenTemplateID** raises an error, usually because the foreign provider is unavailable or not included in the profile, try to continue by treating the unbound entry as read-only.</span></span> <span data-ttu-id="ac8e3-154">打开外的通讯簿条目的详细信息，请参阅[充当主机通讯簿提供程序](acting-as-a-host-address-book-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="ac8e3-154">For more information about opening foreign address book entries, see [Acting as a Host Address Book Provider](acting-as-a-host-address-book-provider.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="ac8e3-155">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ac8e3-155">See also</span></span>



[<span data-ttu-id="ac8e3-156">IABLogon : IUnknown</span><span class="sxs-lookup"><span data-stu-id="ac8e3-156">IABLogon : IUnknown</span></span>](iablogoniunknown.md)

