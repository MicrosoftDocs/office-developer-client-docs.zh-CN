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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: cfbb799336aa1e75fa36e03e55d82c3af3409f10
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32326343"
---
# <a name="imapisupportopenentry"></a><span data-ttu-id="f65c4-103">IMAPISupport::OpenEntry</span><span class="sxs-lookup"><span data-stu-id="f65c4-103">IMAPISupport::OpenEntry</span></span>

  
  
<span data-ttu-id="f65c4-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="f65c4-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="f65c4-105">打开一个对象并返回一个接口指针以供进一步访问。</span><span class="sxs-lookup"><span data-stu-id="f65c4-105">Opens an object and returns an interface pointer for further access.</span></span> 
  
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

## <a name="parameters"></a><span data-ttu-id="f65c4-106">参数</span><span class="sxs-lookup"><span data-stu-id="f65c4-106">Parameters</span></span>

 <span data-ttu-id="f65c4-107">_cbEntryID_</span><span class="sxs-lookup"><span data-stu-id="f65c4-107">_cbEntryID_</span></span>
  
> <span data-ttu-id="f65c4-108">实时条目标识符中由_lpEntryID_参数指向的字节数。</span><span class="sxs-lookup"><span data-stu-id="f65c4-108">[in] The byte count in the entry identifier pointed to by the  _lpEntryID_ parameter.</span></span> 
    
 <span data-ttu-id="f65c4-109">_lpEntryID_</span><span class="sxs-lookup"><span data-stu-id="f65c4-109">_lpEntryID_</span></span>
  
> <span data-ttu-id="f65c4-110">实时指向要打开的对象的条目标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="f65c4-110">[in] A pointer to the entry identifier of the object to open.</span></span>
    
 <span data-ttu-id="f65c4-111">_lpInterface_</span><span class="sxs-lookup"><span data-stu-id="f65c4-111">_lpInterface_</span></span>
  
> <span data-ttu-id="f65c4-112">实时指向接口标识符 (IID) 的指针, 该接口标识符表示要用于访问对象的接口。</span><span class="sxs-lookup"><span data-stu-id="f65c4-112">[in] A pointer to the interface identifier (IID) that represents the interface to be used to access the object.</span></span> <span data-ttu-id="f65c4-113">在返回的对象的标准接口中传递 NULL 结果。</span><span class="sxs-lookup"><span data-stu-id="f65c4-113">Passing NULL results in the object's standard interface being returned.</span></span> <span data-ttu-id="f65c4-114">例如, 如果要打开的对象是一条消息, 则标准接口是[IMessage](imessageimapiprop.md);对于文件夹, 它是[IMAPIFolder](imapifolderimapicontainer.md)。</span><span class="sxs-lookup"><span data-stu-id="f65c4-114">For example, if the object to be opened is a message, the standard interface is [IMessage](imessageimapiprop.md); for folders, it is [IMAPIFolder](imapifolderimapicontainer.md).</span></span> <span data-ttu-id="f65c4-115">通讯簿对象的标准接口是[IDistList](idistlistimapicontainer.md)用于邮件用户的通讯组列表和[IMailUser](imailuserimapiprop.md) 。</span><span class="sxs-lookup"><span data-stu-id="f65c4-115">The standard interfaces for address book objects are [IDistList](idistlistimapicontainer.md) for a distribution list and [IMailUser](imailuserimapiprop.md) for a messaging user.</span></span> 
    
 <span data-ttu-id="f65c4-116">_ulOpenFlags_</span><span class="sxs-lookup"><span data-stu-id="f65c4-116">_ulOpenFlags_</span></span>
  
> <span data-ttu-id="f65c4-117">实时用于控制对象打开方式的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="f65c4-117">[in] A bitmask of flags that controls how the object is opened.</span></span> <span data-ttu-id="f65c4-118">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="f65c4-118">The following flags can be set:</span></span>
    
<span data-ttu-id="f65c4-119">MAPI_BEST_ACCESS</span><span class="sxs-lookup"><span data-stu-id="f65c4-119">MAPI_BEST_ACCESS</span></span> 
  
> <span data-ttu-id="f65c4-120">请求使用呼叫者允许的最大网络权限打开对象。</span><span class="sxs-lookup"><span data-stu-id="f65c4-120">Requests that the object be opened with the maximum network permissions allowed for the caller.</span></span> <span data-ttu-id="f65c4-121">例如, 如果调用方具有读/写权限, 则应以读/写方式打开对象;如果调用方具有只读权限, 则应以只读方式打开该对象。</span><span class="sxs-lookup"><span data-stu-id="f65c4-121">For example, if the caller has read/write permission, the object should be opened as read/write; if the caller has read-only permission, the object should be opened as read-only.</span></span> 
    
<span data-ttu-id="f65c4-122">MAPI_DEFERRED_ERRORS</span><span class="sxs-lookup"><span data-stu-id="f65c4-122">MAPI_DEFERRED_ERRORS</span></span> 
  
> <span data-ttu-id="f65c4-123">允许**OpenEntry**成功返回, 在调用方完全可以访问对象之前。</span><span class="sxs-lookup"><span data-stu-id="f65c4-123">Allows **OpenEntry** to return successfully, possibly before the object is fully accessible to the caller.</span></span> <span data-ttu-id="f65c4-124">如果对象不可访问, 则进行后续的对象调用会导致错误。</span><span class="sxs-lookup"><span data-stu-id="f65c4-124">If the object is not accessible, making a subsequent object call can result in an error.</span></span> 
    
<span data-ttu-id="f65c4-125">MAPI_MODIFY</span><span class="sxs-lookup"><span data-stu-id="f65c4-125">MAPI_MODIFY</span></span> 
  
> <span data-ttu-id="f65c4-126">请求读取/写入权限。</span><span class="sxs-lookup"><span data-stu-id="f65c4-126">Requests read/write permission.</span></span> <span data-ttu-id="f65c4-127">默认情况下, 对象以只读方式打开, 并且在假定已授予读/写权限时, 调用方不应这样做。</span><span class="sxs-lookup"><span data-stu-id="f65c4-127">By default, objects are opened as read-only, and callers should not work on the assumption that read/write permission has been granted.</span></span> 
    
 <span data-ttu-id="f65c4-128">_lpulObjType_</span><span class="sxs-lookup"><span data-stu-id="f65c4-128">_lpulObjType_</span></span>
  
> <span data-ttu-id="f65c4-129">排除一个指针, 指向打开的对象的类型。</span><span class="sxs-lookup"><span data-stu-id="f65c4-129">[out] A pointer to the type of the opened object.</span></span>
    
 <span data-ttu-id="f65c4-130">_lppUnk_</span><span class="sxs-lookup"><span data-stu-id="f65c4-130">_lppUnk_</span></span>
  
> <span data-ttu-id="f65c4-131">排除指向打开的对象的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="f65c4-131">[out] A pointer to a pointer to the opened object.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="f65c4-132">返回值</span><span class="sxs-lookup"><span data-stu-id="f65c4-132">Return value</span></span>

<span data-ttu-id="f65c4-133">S_OK</span><span class="sxs-lookup"><span data-stu-id="f65c4-133">S_OK</span></span> 
  
> <span data-ttu-id="f65c4-134">已成功打开对象。</span><span class="sxs-lookup"><span data-stu-id="f65c4-134">The object was successfully opened.</span></span>
    
<span data-ttu-id="f65c4-135">MAPI_E_NO_ACCESS</span><span class="sxs-lookup"><span data-stu-id="f65c4-135">MAPI_E_NO_ACCESS</span></span> 
  
> <span data-ttu-id="f65c4-136">试图修改只读对象, 或试图访问用户对其没有足够权限的对象的访问权限。</span><span class="sxs-lookup"><span data-stu-id="f65c4-136">An attempt was made to modify a read-only object, or an attempt was made to access an object for which the user has insufficient permissions.</span></span>
    
<span data-ttu-id="f65c4-137">MAPI_E_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="f65c4-137">MAPI_E_NOT_FOUND</span></span> 
  
> <span data-ttu-id="f65c4-138">没有与_lpEntryID_参数中传递的条目标识符关联的对象。</span><span class="sxs-lookup"><span data-stu-id="f65c4-138">There is not an object associated with the entry identifier passed in the  _lpEntryID_ parameter.</span></span> 
    
<span data-ttu-id="f65c4-139">MAPI_E_UNKNOWN_ENTRYID</span><span class="sxs-lookup"><span data-stu-id="f65c4-139">MAPI_E_UNKNOWN_ENTRYID</span></span> 
  
> <span data-ttu-id="f65c4-140">在_lpEntryID_参数中传递的条目标识符的格式无法识别。</span><span class="sxs-lookup"><span data-stu-id="f65c4-140">The entry identifier passed in the  _lpEntryID_ parameter is in an unrecognizable format.</span></span> <span data-ttu-id="f65c4-141">如果包含该对象的通讯簿提供程序未打开, 通常会返回此值。</span><span class="sxs-lookup"><span data-stu-id="f65c4-141">This value is typically returned if the address book provider that contains the object is not open.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="f65c4-142">注解</span><span class="sxs-lookup"><span data-stu-id="f65c4-142">Remarks</span></span>

<span data-ttu-id="f65c4-143">**IMAPISupport:: OpenEntry**方法是为所有服务提供程序支持对象实现的。</span><span class="sxs-lookup"><span data-stu-id="f65c4-143">The **IMAPISupport::OpenEntry** method is implemented for all service provider support objects.</span></span> <span data-ttu-id="f65c4-144">服务提供程序调用**IMAPISupport:: OpenEntry**以检索指向可用于访问特定对象的接口的指针。</span><span class="sxs-lookup"><span data-stu-id="f65c4-144">Service providers call **IMAPISupport::OpenEntry** to retrieve a pointer to an interface that can be used to access a particular object.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="f65c4-145">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="f65c4-145">Notes to callers</span></span>

<span data-ttu-id="f65c4-146">仅当您不知道要打开的对象类型时, 才会调用**IMAPISupport:: OpenEntry** 。</span><span class="sxs-lookup"><span data-stu-id="f65c4-146">Call **IMAPISupport::OpenEntry** only when you do not know what kind of object you are opening.</span></span> <span data-ttu-id="f65c4-147">如果您知道要打开文件夹或邮件, 请调用[IMsgStore:: OpenEntry](imsgstore-openentry.md) 。</span><span class="sxs-lookup"><span data-stu-id="f65c4-147">If you know you are opening a folder or a message, call [IMsgStore::OpenEntry](imsgstore-openentry.md) instead.</span></span> <span data-ttu-id="f65c4-148">如果您知道要打开通讯簿容器、邮件用户或通讯组列表, 请调用[IAddrBook:: OpenEntry](iaddrbook-openentry.md)。</span><span class="sxs-lookup"><span data-stu-id="f65c4-148">If you know you are opening an address book container, a messaging user, or a distribution list, call [IAddrBook::OpenEntry](iaddrbook-openentry.md).</span></span> <span data-ttu-id="f65c4-149">这些更具体的方法比**IMAPISupport:: OpenEntry**更快。</span><span class="sxs-lookup"><span data-stu-id="f65c4-149">These more specific methods are faster than **IMAPISupport::OpenEntry**.</span></span> 
  
 <span data-ttu-id="f65c4-150">**IMAPISupport:: OpenEntry**以只读方式打开所有对象, 除非您在_ulFlags_参数中设置 MAPI_MODIFY 或 MAPI_BEST_ACCESS 标志, 并且您的权限足够。</span><span class="sxs-lookup"><span data-stu-id="f65c4-150">**IMAPISupport::OpenEntry** opens all objects as read-only, unless you set the MAPI_MODIFY or MAPI_BEST_ACCESS flag in the  _ulFlags_ parameter and your permissions are sufficient.</span></span> <span data-ttu-id="f65c4-151">设置其中一个标志并不能保证特定类型的访问权限;您授予的权限取决于您的访问级别、对象和拥有该对象的服务提供程序。</span><span class="sxs-lookup"><span data-stu-id="f65c4-151">Setting one of these flags does not guarantee a particular type of access; the permissions that you are granted depend on your access level, the object, and the service provider that owns the object.</span></span> <span data-ttu-id="f65c4-152">若要确定打开的对象的访问级别, 请检索其**PR_ACCESS_LEVEL** ([PidTagAccessLevel](pidtagaccesslevel-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="f65c4-152">To determine the access level of the opened object, retrieve its **PR_ACCESS_LEVEL** ([PidTagAccessLevel](pidtagaccesslevel-canonical-property.md)) property.</span></span>
  
<span data-ttu-id="f65c4-153">检查_lpulObjType_参数中返回的值, 以确定返回的对象类型是您所期望的。</span><span class="sxs-lookup"><span data-stu-id="f65c4-153">Check the value returned in the  _lpulObjType_ parameter to determine that the object type returned is what you expected.</span></span> <span data-ttu-id="f65c4-154">如果对象类型是预期的, 则将指针从_lppUnk_参数转换为适当类型的指针。</span><span class="sxs-lookup"><span data-stu-id="f65c4-154">If the object type is as expected, cast the pointer from the  _lppUnk_ parameter to a pointer of the appropriate type.</span></span> <span data-ttu-id="f65c4-155">例如, 如果您打开一个文件夹, 则会将_lppUnk_转换为 LPMAPIFOLDER 类型的指针。</span><span class="sxs-lookup"><span data-stu-id="f65c4-155">For example, if you are opening a folder, cast  _lppUnk_ to a pointer of type LPMAPIFOLDER.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="f65c4-156">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f65c4-156">See also</span></span>



[<span data-ttu-id="f65c4-157">IMAPISupport : IUnknown</span><span class="sxs-lookup"><span data-stu-id="f65c4-157">IMAPISupport : IUnknown</span></span>](imapisupportiunknown.md)

