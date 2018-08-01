---
title: IMAPISupportOpenEntry
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISupport.OpenEntry
api_type:
- COM
ms.assetid: 84662230-6a25-4403-b87e-871427a40c6e
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 04bf7f2ddda7377df72417df2472246a2cf329bf
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775649"
---
# <a name="imapisupportopenentry"></a><span data-ttu-id="97e1e-103">IMAPISupport::OpenEntry</span><span class="sxs-lookup"><span data-stu-id="97e1e-103">IMAPISupport::OpenEntry</span></span>

  
  
<span data-ttu-id="97e1e-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="97e1e-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="97e1e-105">打开一个对象并返回进一步访问的接口指针。</span><span class="sxs-lookup"><span data-stu-id="97e1e-105">Opens an object and returns an interface pointer for further access.</span></span> 
  
```cpp
HRESULT OpenEntry(
ULONG cbEntryID,
LPENTRYID lpEntryID,
LPCIID lpInterface,
ULONG ulOpenFlags,
ULONG FAR * lpulObjType,
LPUNKNOWN FAR * lppUnk
);
```

## <a name="parameters"></a><span data-ttu-id="97e1e-106">参数</span><span class="sxs-lookup"><span data-stu-id="97e1e-106">Parameters</span></span>

 <span data-ttu-id="97e1e-107">_cbEntryID_</span><span class="sxs-lookup"><span data-stu-id="97e1e-107">_cbEntryID_</span></span>
  
> <span data-ttu-id="97e1e-108">[in]在_lpEntryID_参数指向的项标识符的字节数。</span><span class="sxs-lookup"><span data-stu-id="97e1e-108">[in] The byte count in the entry identifier pointed to by the  _lpEntryID_ parameter.</span></span> 
    
 <span data-ttu-id="97e1e-109">_lpEntryID_</span><span class="sxs-lookup"><span data-stu-id="97e1e-109">_lpEntryID_</span></span>
  
> <span data-ttu-id="97e1e-110">[in]指向要打开的对象的项标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="97e1e-110">[in] A pointer to the entry identifier of the object to open.</span></span>
    
 <span data-ttu-id="97e1e-111">_lpInterface_</span><span class="sxs-lookup"><span data-stu-id="97e1e-111">_lpInterface_</span></span>
  
> <span data-ttu-id="97e1e-112">[in]指向接口标识 (IID) 值，该值代表要用于访问该对象的接口的指针。</span><span class="sxs-lookup"><span data-stu-id="97e1e-112">[in] A pointer to the interface identifier (IID) that represents the interface to be used to access the object.</span></span> <span data-ttu-id="97e1e-113">传递空结果中要返回的对象的标准接口。</span><span class="sxs-lookup"><span data-stu-id="97e1e-113">Passing NULL results in the object's standard interface being returned.</span></span> <span data-ttu-id="97e1e-114">例如，如果要在打开的对象是一条消息，标准接口是[IMessage](imessageimapiprop.md);对于文件夹，则[IMAPIFolder](imapifolderimapicontainer.md)。</span><span class="sxs-lookup"><span data-stu-id="97e1e-114">For example, if the object to be opened is a message, the standard interface is [IMessage](imessageimapiprop.md); for folders, it is [IMAPIFolder](imapifolderimapicontainer.md).</span></span> <span data-ttu-id="97e1e-115">地址簿对象的标准接口是[IDistList](idistlistimapicontainer.md)通讯组列表和[IMailUser](imailuserimapiprop.md)消息用户。</span><span class="sxs-lookup"><span data-stu-id="97e1e-115">The standard interfaces for address book objects are [IDistList](idistlistimapicontainer.md) for a distribution list and [IMailUser](imailuserimapiprop.md) for a messaging user.</span></span> 
    
 <span data-ttu-id="97e1e-116">_ulOpenFlags_</span><span class="sxs-lookup"><span data-stu-id="97e1e-116">_ulOpenFlags_</span></span>
  
> <span data-ttu-id="97e1e-117">[in]位掩码的标志，控制如何打开对象。</span><span class="sxs-lookup"><span data-stu-id="97e1e-117">[in] A bitmask of flags that controls how the object is opened.</span></span> <span data-ttu-id="97e1e-118">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="97e1e-118">The following flags can be set:</span></span>
    
<span data-ttu-id="97e1e-119">MAPI_BEST_ACCESS</span><span class="sxs-lookup"><span data-stu-id="97e1e-119">MAPI_BEST_ACCESS</span></span> 
  
> <span data-ttu-id="97e1e-120">请求，与呼叫者允许的最大网络权限打开对象。</span><span class="sxs-lookup"><span data-stu-id="97e1e-120">Requests that the object be opened with the maximum network permissions allowed for the caller.</span></span> <span data-ttu-id="97e1e-121">例如，如果呼叫者具有读/写权限，该对象应打开以读/写;如果呼叫者具有只读权限，则应以只读方式打开对象。</span><span class="sxs-lookup"><span data-stu-id="97e1e-121">For example, if the caller has read/write permission, the object should be opened as read/write; if the caller has read-only permission, the object should be opened as read-only.</span></span> 
    
<span data-ttu-id="97e1e-122">MAPI_DEFERRED_ERRORS</span><span class="sxs-lookup"><span data-stu-id="97e1e-122">MAPI_DEFERRED_ERRORS</span></span> 
  
> <span data-ttu-id="97e1e-123">允许**OpenEntry**返回成功，原因可能是完全可与呼叫者访问对象之前。</span><span class="sxs-lookup"><span data-stu-id="97e1e-123">Allows **OpenEntry** to return successfully, possibly before the object is fully accessible to the caller.</span></span> <span data-ttu-id="97e1e-124">如果对象不是可访问的则进行后续对象呼叫会导致出错。</span><span class="sxs-lookup"><span data-stu-id="97e1e-124">If the object is not accessible, making a subsequent object call can result in an error.</span></span> 
    
<span data-ttu-id="97e1e-125">MAPI_MODIFY</span><span class="sxs-lookup"><span data-stu-id="97e1e-125">MAPI_MODIFY</span></span> 
  
> <span data-ttu-id="97e1e-126">请求读/写权限。</span><span class="sxs-lookup"><span data-stu-id="97e1e-126">Requests read/write permission.</span></span> <span data-ttu-id="97e1e-127">默认情况下，以只读方式打开对象和呼叫者以为，读/写权限授予不起作用。</span><span class="sxs-lookup"><span data-stu-id="97e1e-127">By default, objects are opened as read-only, and callers should not work on the assumption that read/write permission has been granted.</span></span> 
    
 <span data-ttu-id="97e1e-128">_lpulObjType_</span><span class="sxs-lookup"><span data-stu-id="97e1e-128">_lpulObjType_</span></span>
  
> <span data-ttu-id="97e1e-129">[输出]一个指向打开的对象的类型。</span><span class="sxs-lookup"><span data-stu-id="97e1e-129">[out] A pointer to the type of the opened object.</span></span>
    
 <span data-ttu-id="97e1e-130">_lppUnk_</span><span class="sxs-lookup"><span data-stu-id="97e1e-130">_lppUnk_</span></span>
  
> <span data-ttu-id="97e1e-131">[输出]指向打开的对象的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="97e1e-131">[out] A pointer to a pointer to the opened object.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="97e1e-132">返回值</span><span class="sxs-lookup"><span data-stu-id="97e1e-132">Return value</span></span>

<span data-ttu-id="97e1e-133">S_OK</span><span class="sxs-lookup"><span data-stu-id="97e1e-133">S_OK</span></span> 
  
> <span data-ttu-id="97e1e-134">成功打开对象。</span><span class="sxs-lookup"><span data-stu-id="97e1e-134">The object was successfully opened.</span></span>
    
<span data-ttu-id="97e1e-135">MAPI_E_NO_ACCESS</span><span class="sxs-lookup"><span data-stu-id="97e1e-135">MAPI_E_NO_ACCESS</span></span> 
  
> <span data-ttu-id="97e1e-136">尝试修改只读对象，或尝试访问其用户没有足够的权限的对象。</span><span class="sxs-lookup"><span data-stu-id="97e1e-136">An attempt was made to modify a read-only object, or an attempt was made to access an object for which the user has insufficient permissions.</span></span>
    
<span data-ttu-id="97e1e-137">MAPI_E_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="97e1e-137">MAPI_E_NOT_FOUND</span></span> 
  
> <span data-ttu-id="97e1e-138">没有与_lpEntryID_参数中传递的项标识符关联的对象。</span><span class="sxs-lookup"><span data-stu-id="97e1e-138">There is not an object associated with the entry identifier passed in the  _lpEntryID_ parameter.</span></span> 
    
<span data-ttu-id="97e1e-139">MAPI_E_UNKNOWN_ENTRYID</span><span class="sxs-lookup"><span data-stu-id="97e1e-139">MAPI_E_UNKNOWN_ENTRYID</span></span> 
  
> <span data-ttu-id="97e1e-140">无法识别格式_lpEntryID_参数中传递的项标识符。</span><span class="sxs-lookup"><span data-stu-id="97e1e-140">The entry identifier passed in the  _lpEntryID_ parameter is in an unrecognizable format.</span></span> <span data-ttu-id="97e1e-141">如果包含对象的通讯簿提供程序未打开，则通常会返回此值。</span><span class="sxs-lookup"><span data-stu-id="97e1e-141">This value is typically returned if the address book provider that contains the object is not open.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="97e1e-142">说明</span><span class="sxs-lookup"><span data-stu-id="97e1e-142">Remarks</span></span>

<span data-ttu-id="97e1e-143">**IMAPISupport::OpenEntry**方法将执行所有服务提供商支持对象。</span><span class="sxs-lookup"><span data-stu-id="97e1e-143">The **IMAPISupport::OpenEntry** method is implemented for all service provider support objects.</span></span> <span data-ttu-id="97e1e-144">服务提供商调用**IMAPISupport::OpenEntry**检索可用于访问特定对象的接口的指针。</span><span class="sxs-lookup"><span data-stu-id="97e1e-144">Service providers call **IMAPISupport::OpenEntry** to retrieve a pointer to an interface that can be used to access a particular object.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="97e1e-145">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="97e1e-145">Notes to callers</span></span>

<span data-ttu-id="97e1e-146">仅当您不知道您打开哪种类型的对象时，请调用**IMAPISupport::OpenEntry** 。</span><span class="sxs-lookup"><span data-stu-id="97e1e-146">Call **IMAPISupport::OpenEntry** only when you do not know what kind of object you are opening.</span></span> <span data-ttu-id="97e1e-147">如果您知道要打开文件夹或一条消息，请改为呼叫[IMsgStore::OpenEntry](imsgstore-openentry.md) 。</span><span class="sxs-lookup"><span data-stu-id="97e1e-147">If you know you are opening a folder or a message, call [IMsgStore::OpenEntry](imsgstore-openentry.md) instead.</span></span> <span data-ttu-id="97e1e-148">如果您知道要打开通讯簿容器、 邮件用户或通讯组列表，请调用[IAddrBook::OpenEntry](iaddrbook-openentry.md)。</span><span class="sxs-lookup"><span data-stu-id="97e1e-148">If you know you are opening an address book container, a messaging user, or a distribution list, call [IAddrBook::OpenEntry](iaddrbook-openentry.md).</span></span> <span data-ttu-id="97e1e-149">这些更加具体方法是比**IMAPISupport::OpenEntry**速度更快。</span><span class="sxs-lookup"><span data-stu-id="97e1e-149">These more specific methods are faster than **IMAPISupport::OpenEntry**.</span></span> 
  
 <span data-ttu-id="97e1e-150">**IMAPISupport::OpenEntry**打开所有对象为只读，除非_ulFlags_参数中设置 MAPI_MODIFY 或 MAPI_BEST_ACCESS 标志并且您的权限不足。</span><span class="sxs-lookup"><span data-stu-id="97e1e-150">**IMAPISupport::OpenEntry** opens all objects as read-only, unless you set the MAPI_MODIFY or MAPI_BEST_ACCESS flag in the  _ulFlags_ parameter and your permissions are sufficient.</span></span> <span data-ttu-id="97e1e-151">这些标志之一设置不保证特定类型的访问;您已被授予的权限取决于您的访问级别、 对象和拥有该对象的服务提供程序。</span><span class="sxs-lookup"><span data-stu-id="97e1e-151">Setting one of these flags does not guarantee a particular type of access; the permissions that you are granted depend on your access level, the object, and the service provider that owns the object.</span></span> <span data-ttu-id="97e1e-152">若要确定打开的对象的访问级别，检索其**PR_ACCESS_LEVEL** ([PidTagAccessLevel](pidtagaccesslevel-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="97e1e-152">To determine the access level of the opened object, retrieve its **PR_ACCESS_LEVEL** ([PidTagAccessLevel](pidtagaccesslevel-canonical-property.md)) property.</span></span>
  
<span data-ttu-id="97e1e-153">检查以确定返回的对象类型是您的预期_lpulObjType_参数中返回的值。</span><span class="sxs-lookup"><span data-stu-id="97e1e-153">Check the value returned in the  _lpulObjType_ parameter to determine that the object type returned is what you expected.</span></span> <span data-ttu-id="97e1e-154">如果对象类型是预期，强制转换为适当类型的指针的指针从_lppUnk_参数。</span><span class="sxs-lookup"><span data-stu-id="97e1e-154">If the object type is as expected, cast the pointer from the  _lppUnk_ parameter to a pointer of the appropriate type.</span></span> <span data-ttu-id="97e1e-155">例如，如果您打开一个文件夹，强制转换为的类型 LPMAPIFOLDER 指针_lppUnk_ 。</span><span class="sxs-lookup"><span data-stu-id="97e1e-155">For example, if you are opening a folder, cast  _lppUnk_ to a pointer of type LPMAPIFOLDER.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="97e1e-156">另请参阅</span><span class="sxs-lookup"><span data-stu-id="97e1e-156">See also</span></span>



[<span data-ttu-id="97e1e-157">IMAPISupport : IUnknown</span><span class="sxs-lookup"><span data-stu-id="97e1e-157">IMAPISupport : IUnknown</span></span>](imapisupportiunknown.md)

