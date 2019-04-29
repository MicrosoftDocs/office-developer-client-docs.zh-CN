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
# <a name="iablogonopenentry"></a><span data-ttu-id="90c91-103">IABLogon::OpenEntry</span><span class="sxs-lookup"><span data-stu-id="90c91-103">IABLogon::OpenEntry</span></span>

  
  
<span data-ttu-id="90c91-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="90c91-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="90c91-105">打开容器、邮件用户或通讯组列表, 并返回指向接口实现的指针, 以提供进一步的访问权限。</span><span class="sxs-lookup"><span data-stu-id="90c91-105">Opens a container, messaging user, or distribution list, and returns a pointer to an interface implementation to provide further access.</span></span>
  
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

## <a name="parameters"></a><span data-ttu-id="90c91-106">参数</span><span class="sxs-lookup"><span data-stu-id="90c91-106">Parameters</span></span>

 <span data-ttu-id="90c91-107">_cbEntryID_</span><span class="sxs-lookup"><span data-stu-id="90c91-107">_cbEntryID_</span></span>
  
> <span data-ttu-id="90c91-108">实时条目标识符中由_lpEntryID_参数指向的字节数。</span><span class="sxs-lookup"><span data-stu-id="90c91-108">[in] The byte count in the entry identifier pointed to by the  _lpEntryID_ parameter.</span></span> 
    
 <span data-ttu-id="90c91-109">_lpEntryID_</span><span class="sxs-lookup"><span data-stu-id="90c91-109">_lpEntryID_</span></span>
  
> <span data-ttu-id="90c91-110">实时指向要打开的容器、邮件用户或通讯组列表的条目标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="90c91-110">[in] A pointer to the entry identifier of the container, messaging user, or distribution list to open.</span></span>
    
 <span data-ttu-id="90c91-111">_lpInterface_</span><span class="sxs-lookup"><span data-stu-id="90c91-111">_lpInterface_</span></span>
  
> <span data-ttu-id="90c91-112">实时指向接口标识符 (IID) 的指针, 该接口标识符表示要用于访问打开的对象的接口。</span><span class="sxs-lookup"><span data-stu-id="90c91-112">[in] A pointer to the interface identifier (IID) that represents the interface to be used to access the open object.</span></span> <span data-ttu-id="90c91-113">传递 NULL 将返回对象的标准接口的标识符。</span><span class="sxs-lookup"><span data-stu-id="90c91-113">Passing NULL returns the identifier for the object's standard interface.</span></span> <span data-ttu-id="90c91-114">对于容器, 标准接口为[IABContainer: IMAPIContainer](iabcontainerimapicontainer.md)。</span><span class="sxs-lookup"><span data-stu-id="90c91-114">For containers, the standard interface is [IABContainer : IMAPIContainer](iabcontainerimapicontainer.md).</span></span> <span data-ttu-id="90c91-115">通讯簿对象的标准接口为[IDistList: IMAPIContainer](idistlistimapicontainer.md)对于邮件用户的通讯组列表和[IMailUser: IMAPIProp](imailuserimapiprop.md) 。</span><span class="sxs-lookup"><span data-stu-id="90c91-115">The standard interfaces for address book objects are [IDistList : IMAPIContainer](idistlistimapicontainer.md) for a distribution list and [IMailUser : IMAPIProp](imailuserimapiprop.md) for a messaging user.</span></span> 
    
 <span data-ttu-id="90c91-116">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="90c91-116">_ulFlags_</span></span>
  
> <span data-ttu-id="90c91-117">实时用于控制对象打开方式的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="90c91-117">[in] A bitmask of flags that controls how the object is opened.</span></span> <span data-ttu-id="90c91-118">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="90c91-118">The following flags can be set:</span></span>
    
<span data-ttu-id="90c91-119">MAPI_BEST_ACCESS</span><span class="sxs-lookup"><span data-stu-id="90c91-119">MAPI_BEST_ACCESS</span></span> 
  
> <span data-ttu-id="90c91-120">请求使用用户允许的最大网络权限和最大客户端应用程序访问权限打开对象。</span><span class="sxs-lookup"><span data-stu-id="90c91-120">Requests that the object be opened with the maximum network permissions allowed for the user and the maximum client application access.</span></span> <span data-ttu-id="90c91-121">例如, 如果客户端具有读/写权限, 则应以读/写权限打开该对象;如果客户端具有只读权限, 则应以只读权限打开该对象。</span><span class="sxs-lookup"><span data-stu-id="90c91-121">For example, if the client has read/write permission, the object should be opened with read/write permission; if the client has read-only permission, the object should be opened with read-only permission.</span></span>
    
<span data-ttu-id="90c91-122">MAPI_DEFERRED_ERRORS</span><span class="sxs-lookup"><span data-stu-id="90c91-122">MAPI_DEFERRED_ERRORS</span></span> 
  
> <span data-ttu-id="90c91-123">允许**OpenEntry**方法成功返回, 这可能是在调用客户端完全访问了该对象之前。</span><span class="sxs-lookup"><span data-stu-id="90c91-123">Allows the **OpenEntry** method to return successfully, possibly before the calling client has fully accessed the object.</span></span> <span data-ttu-id="90c91-124">如果不访问该对象, 进行后续的对象调用可能会引发错误。</span><span class="sxs-lookup"><span data-stu-id="90c91-124">If the object is not accessed, making a subsequent object call can raise an error.</span></span> 
    
<span data-ttu-id="90c91-125">MAPI_MODIFY</span><span class="sxs-lookup"><span data-stu-id="90c91-125">MAPI_MODIFY</span></span> 
  
> <span data-ttu-id="90c91-126">请求读取/写入权限。</span><span class="sxs-lookup"><span data-stu-id="90c91-126">Requests read/write permission.</span></span> <span data-ttu-id="90c91-127">默认情况下, 将使用只读访问权限打开对象, 并且客户端不应假定已授予读/写权限。</span><span class="sxs-lookup"><span data-stu-id="90c91-127">By default, objects are opened with read-only access, and clients should not assume that read/write permission has been granted.</span></span>
    
 <span data-ttu-id="90c91-128">_lpulObjType_</span><span class="sxs-lookup"><span data-stu-id="90c91-128">_lpulObjType_</span></span>
  
> <span data-ttu-id="90c91-129">排除一个指针, 指向打开的对象的类型。</span><span class="sxs-lookup"><span data-stu-id="90c91-129">[out] A pointer to the type of the opened object.</span></span>
    
 <span data-ttu-id="90c91-130">_lppUnk_</span><span class="sxs-lookup"><span data-stu-id="90c91-130">_lppUnk_</span></span>
  
> <span data-ttu-id="90c91-131">排除指向打开的对象的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="90c91-131">[out] A pointer to a pointer to the opened object.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="90c91-132">说明</span><span class="sxs-lookup"><span data-stu-id="90c91-132">Remarks</span></span>

<span data-ttu-id="90c91-133">S_OK</span><span class="sxs-lookup"><span data-stu-id="90c91-133">S_OK</span></span> 
  
> <span data-ttu-id="90c91-134">已成功打开对象。</span><span class="sxs-lookup"><span data-stu-id="90c91-134">The object was successfully opened.</span></span>
    
<span data-ttu-id="90c91-135">MAPI_E_NO_ACCESS</span><span class="sxs-lookup"><span data-stu-id="90c91-135">MAPI_E_NO_ACCESS</span></span> 
  
> <span data-ttu-id="90c91-136">用户的权限不足, 无法打开该对象, 或试图打开具有读/写权限的只读对象。</span><span class="sxs-lookup"><span data-stu-id="90c91-136">Either the user has insufficient permissions to open the object, or an attempt was made to open a read-only object with read/write permission.</span></span>
    
<span data-ttu-id="90c91-137">MAPI_E_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="90c91-137">MAPI_E_NOT_FOUND</span></span> 
  
> <span data-ttu-id="90c91-138">_lpEntryID_指定的条目标识符不代表对象。</span><span class="sxs-lookup"><span data-stu-id="90c91-138">The entry identifier specified by  _lpEntryID_ does not represent an object.</span></span> 
    
<span data-ttu-id="90c91-139">MAPI_E_UNKNOWN_ENTRYID</span><span class="sxs-lookup"><span data-stu-id="90c91-139">MAPI_E_UNKNOWN_ENTRYID</span></span> 
  
> <span data-ttu-id="90c91-140">_lpEntryID_参数中的条目标识符不是通讯簿提供程序可识别的格式。</span><span class="sxs-lookup"><span data-stu-id="90c91-140">The entry identifier in the  _lpEntryID_ parameter is not of a format recognized by the address book provider.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="90c91-141">说明</span><span class="sxs-lookup"><span data-stu-id="90c91-141">Remarks</span></span>

<span data-ttu-id="90c91-142">MAPI 调用**OpenEntry**方法来打开容器、邮件用户或通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="90c91-142">MAPI calls the **OpenEntry** method to open a container, messaging user, or distribution list.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="90c91-143">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="90c91-143">Notes to implementers</span></span>

<span data-ttu-id="90c91-144">在 MAPI 调用您的**OpenEntry**方法之前, 它确定_lpEntryID_参数中的条目标识符属于您而不是另一个提供程序。</span><span class="sxs-lookup"><span data-stu-id="90c91-144">Before MAPI calls your **OpenEntry** method, it determines that the entry identifier in the  _lpEntryID_ parameter belongs to you and not to another provider.</span></span> <span data-ttu-id="90c91-145">MAPI 通过将条目标识符中的[MAPIUID](mapiuid.md)结构与您在启动时调用[IMAPISupport:: SetProviderUID](imapisupport-setprovideruid.md)方法注册的**MAPIUID**相匹配的条目标识符来实现此操作。</span><span class="sxs-lookup"><span data-stu-id="90c91-145">MAPI does this by matching the [MAPIUID](mapiuid.md) structure in the entry identifier with the **MAPIUID** that you registered by calling the [IMAPISupport::SetProviderUID](imapisupport-setprovideruid.md) method at startup.</span></span> 
  
<span data-ttu-id="90c91-146">将对象以只读方式打开, 除非在_ulFlags_参数中设置了 MAPI_MODIFY 或 MAPI_BEST_ACCESS 标志。</span><span class="sxs-lookup"><span data-stu-id="90c91-146">Open the object as read-only, unless the MAPI_MODIFY or MAPI_BEST_ACCESS flag is set in the  _ulFlags_ parameter.</span></span> <span data-ttu-id="90c91-147">如果不允许对所请求的对象进行修改, 请不要打开所有对象, 并返回 MAPI_E_NO_ACCESS。</span><span class="sxs-lookup"><span data-stu-id="90c91-147">If you do not allow modification for the requested object, do not open the object at all and return MAPI_E_NO_ACCESS.</span></span> 
  
<span data-ttu-id="90c91-148">如果 MAPI 为_lpEntryID_传递了 NULL, 请打开容器层次结构中的根容器。</span><span class="sxs-lookup"><span data-stu-id="90c91-148">If MAPI passes NULL for  _lpEntryID_, open the root container in your container hierarchy.</span></span>
  
<span data-ttu-id="90c91-149">要求您打开的对象可能是从另一个提供程序复制的对象。</span><span class="sxs-lookup"><span data-stu-id="90c91-149">The object that you are being asked to open might be an object copied from another provider.</span></span> <span data-ttu-id="90c91-150">在这种情况下, 它将支持**PR_TEMPLATEID** ([PidTagTemplateid](pidtagtemplateid-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="90c91-150">In this case, it will support the **PR_TEMPLATEID** ([PidTagTemplateid](pidtagtemplateid-canonical-property.md)) property.</span></span> <span data-ttu-id="90c91-151">如果该对象不支持此属性, 请调用[IMAPISupport:: OpenTemplateID](imapisupport-opentemplateid.md)方法, 以在外部提供程序中绑定到此条目的代码, 在_lpTemplateID_参数中传递**PR_TEMPLATEID** , 在 ulTemplateFlags 中传递 0 __ 参数。</span><span class="sxs-lookup"><span data-stu-id="90c91-151">If the object does support this property, call the [IMAPISupport::OpenTemplateID](imapisupport-opentemplateid.md) method to bind to code for this entry in the foreign provider, passing **PR_TEMPLATEID** in the  _lpTemplateID_ parameter and 0 in the  _ulTemplateFlags_ parameter.</span></span> <span data-ttu-id="90c91-152">**IMAPISupport:: OpenTemplateID**在对外部提供程序的[IABLogon:: OpenTemplateID](iablogon-opentemplateid.md)方法的调用中将此信息传递给外部提供程序。</span><span class="sxs-lookup"><span data-stu-id="90c91-152">**IMAPISupport::OpenTemplateID** passes this information to the foreign provider in a call to the foreign provider's [IABLogon::OpenTemplateID](iablogon-opentemplateid.md) method.</span></span> <span data-ttu-id="90c91-153">如果**IMAPISupport:: OpenTemplateID**引发错误, 通常是因为外部提供程序不可用或不包含在配置文件中, 请尝试通过将未绑定项视为只读来继续操作。</span><span class="sxs-lookup"><span data-stu-id="90c91-153">If **IMAPISupport::OpenTemplateID** raises an error, usually because the foreign provider is unavailable or not included in the profile, try to continue by treating the unbound entry as read-only.</span></span> <span data-ttu-id="90c91-154">有关打开外部通讯簿条目的详细信息, 请参阅[作为主机通讯簿提供程序](acting-as-a-host-address-book-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="90c91-154">For more information about opening foreign address book entries, see [Acting as a Host Address Book Provider](acting-as-a-host-address-book-provider.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="90c91-155">另请参阅</span><span class="sxs-lookup"><span data-stu-id="90c91-155">See also</span></span>



[<span data-ttu-id="90c91-156">IABLogon : IUnknown</span><span class="sxs-lookup"><span data-stu-id="90c91-156">IABLogon : IUnknown</span></span>](iablogoniunknown.md)

