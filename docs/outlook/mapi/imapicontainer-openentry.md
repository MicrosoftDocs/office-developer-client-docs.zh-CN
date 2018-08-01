---
title: IMAPIContainerOpenEntry
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIContainer.OpenEntry
api_type:
- COM
ms.assetid: 0c46c1fb-dd63-4ac5-960e-80f68e75d8f4
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: c13ab9ce9c2564c39bfe9b2689f05439bc7b74ff
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775314"
---
# <a name="imapicontaineropenentry"></a><span data-ttu-id="2f5f7-103">IMAPIContainer::OpenEntry</span><span class="sxs-lookup"><span data-stu-id="2f5f7-103">IMAPIContainer::OpenEntry</span></span>

  
  
<span data-ttu-id="2f5f7-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="2f5f7-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="2f5f7-105">在该容器，返回进一步访问的接口指针中打开一个对象。</span><span class="sxs-lookup"><span data-stu-id="2f5f7-105">Opens an object in the container, returning an interface pointer for further access.</span></span>
  
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

## <a name="parameters"></a><span data-ttu-id="2f5f7-106">参数</span><span class="sxs-lookup"><span data-stu-id="2f5f7-106">Parameters</span></span>

 <span data-ttu-id="2f5f7-107">_cbEntryID_</span><span class="sxs-lookup"><span data-stu-id="2f5f7-107">_cbEntryID_</span></span>
  
> <span data-ttu-id="2f5f7-108">[in]在_lpEntryID_参数指向的项标识符的字节数。</span><span class="sxs-lookup"><span data-stu-id="2f5f7-108">[in] The byte count in the entry identifier pointed to by the  _lpEntryID_ parameter.</span></span> 
    
 <span data-ttu-id="2f5f7-109">_lpEntryID_</span><span class="sxs-lookup"><span data-stu-id="2f5f7-109">_lpEntryID_</span></span>
  
> <span data-ttu-id="2f5f7-110">[in]指向要打开的对象的项标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="2f5f7-110">[in] A pointer to the entry identifier of the object to open.</span></span> <span data-ttu-id="2f5f7-111">如果_lpEntryID_设置为 NULL，则打开容器的层次结构中的顶级容器。</span><span class="sxs-lookup"><span data-stu-id="2f5f7-111">If  _lpEntryID_ is set to NULL, the top-level container in the container's hierarchy is opened.</span></span> 
    
 <span data-ttu-id="2f5f7-112">_lpInterface_</span><span class="sxs-lookup"><span data-stu-id="2f5f7-112">_lpInterface_</span></span>
  
> <span data-ttu-id="2f5f7-113">[in]指向接口标识 (IID) 值，该值代表要用于访问该对象的接口的指针。</span><span class="sxs-lookup"><span data-stu-id="2f5f7-113">[in] A pointer to the interface identifier (IID) that represents the interface to be used to access the object.</span></span> <span data-ttu-id="2f5f7-114">传递空结果中要返回的对象的标准接口的标识符。</span><span class="sxs-lookup"><span data-stu-id="2f5f7-114">Passing NULL results in the identifier for the object's standard interface being returned.</span></span> <span data-ttu-id="2f5f7-115">对于消息，标准接口是[IMAPIMessageSite: IUnknown](imapimessagesiteiunknown.md);对于文件夹，它是[IMAPIFolder: IMAPIContainer](imapifolderimapicontainer.md)。</span><span class="sxs-lookup"><span data-stu-id="2f5f7-115">For messages, the standard interface is [IMAPIMessageSite : IUnknown](imapimessagesiteiunknown.md); for folders, it is [IMAPIFolder : IMAPIContainer](imapifolderimapicontainer.md).</span></span> <span data-ttu-id="2f5f7-116">标准接口的地址簿对象是[IDistList: IMAPIContainer](idistlistimapicontainer.md)通讯组列表和[IMailUser: IMAPIProp](imailuserimapiprop.md)消息用户。</span><span class="sxs-lookup"><span data-stu-id="2f5f7-116">The standard interfaces for address book objects are [IDistList : IMAPIContainer](idistlistimapicontainer.md) for a distribution list and [IMailUser : IMAPIProp](imailuserimapiprop.md) for a messaging user.</span></span> 
    
 <span data-ttu-id="2f5f7-117">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="2f5f7-117">_ulFlags_</span></span>
  
> <span data-ttu-id="2f5f7-118">[in]位掩码的标志，控制如何打开对象。</span><span class="sxs-lookup"><span data-stu-id="2f5f7-118">[in] A bitmask of flags that controls how the object is opened.</span></span> <span data-ttu-id="2f5f7-119">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="2f5f7-119">The following flags can be set:</span></span>
    
<span data-ttu-id="2f5f7-120">MAPI_BEST_ACCESS</span><span class="sxs-lookup"><span data-stu-id="2f5f7-120">MAPI_BEST_ACCESS</span></span> 
  
> <span data-ttu-id="2f5f7-121">请求将使用用户和最大客户端应用程序访问允许的最大网络权限打开对象。</span><span class="sxs-lookup"><span data-stu-id="2f5f7-121">Requests that the object will be opened with the maximum network permissions allowed for the user and the maximum client application access.</span></span> <span data-ttu-id="2f5f7-122">例如，如果客户端具有读/写权限，该对象应打开具有读/写权限;如果客户端具有只读访问权限，则应具有只读访问权限打开对象。</span><span class="sxs-lookup"><span data-stu-id="2f5f7-122">For example, if the client has read/write permission, the object should be opened with read/write permission; if the client has read-only access, the object should be opened with read-only access.</span></span> 
    
<span data-ttu-id="2f5f7-123">MAPI_DEFERRED_ERRORS</span><span class="sxs-lookup"><span data-stu-id="2f5f7-123">MAPI_DEFERRED_ERRORS</span></span> 
  
> <span data-ttu-id="2f5f7-124">允许**OpenEntry**返回成功，原因可能是完全可调用客户端对象之前。</span><span class="sxs-lookup"><span data-stu-id="2f5f7-124">Allows **OpenEntry** to return successfully, possibly before the object is fully available to the calling client.</span></span> <span data-ttu-id="2f5f7-125">如果对象不可用，则进行后续对象呼叫会引发错误。</span><span class="sxs-lookup"><span data-stu-id="2f5f7-125">If the object is not available, making a subsequent object call can raise an error.</span></span> 
    
<span data-ttu-id="2f5f7-126">MAPI_MODIFY</span><span class="sxs-lookup"><span data-stu-id="2f5f7-126">MAPI_MODIFY</span></span> 
  
> <span data-ttu-id="2f5f7-127">请求读/写权限。</span><span class="sxs-lookup"><span data-stu-id="2f5f7-127">Requests read/write permission.</span></span> <span data-ttu-id="2f5f7-128">默认情况下，对象打开具有只读访问权限和客户端不应以为，读/写权限授予起作用。</span><span class="sxs-lookup"><span data-stu-id="2f5f7-128">By default, objects are opened with read-only access, and clients should not work on the assumption that read/write permission has been granted.</span></span> 
    
<span data-ttu-id="2f5f7-129">SHOW_SOFT_DELETES</span><span class="sxs-lookup"><span data-stu-id="2f5f7-129">SHOW_SOFT_DELETES</span></span>
  
> <span data-ttu-id="2f5f7-130">显示项目的当前标记为软删除 — 即，它们是中已删除的邮件保留时间阶段。</span><span class="sxs-lookup"><span data-stu-id="2f5f7-130">Shows items that are currently marked as soft deleted—that is, they are in the deleted item retention time phase.</span></span>
    
 <span data-ttu-id="2f5f7-131">_lpulObjType_</span><span class="sxs-lookup"><span data-stu-id="2f5f7-131">_lpulObjType_</span></span>
  
> <span data-ttu-id="2f5f7-132">[输出]一个指向打开的对象的类型。</span><span class="sxs-lookup"><span data-stu-id="2f5f7-132">[out] A pointer to the opened object's type.</span></span>
    
 <span data-ttu-id="2f5f7-133">_lppUnk_</span><span class="sxs-lookup"><span data-stu-id="2f5f7-133">_lppUnk_</span></span>
  
> <span data-ttu-id="2f5f7-134">[输出]指向该接口实现用于访问打开的对象的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="2f5f7-134">[out] A pointer to a pointer to the interface implementation to use to access the open object.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="2f5f7-135">返回值</span><span class="sxs-lookup"><span data-stu-id="2f5f7-135">Return value</span></span>

<span data-ttu-id="2f5f7-136">S_OK</span><span class="sxs-lookup"><span data-stu-id="2f5f7-136">S_OK</span></span> 
  
> <span data-ttu-id="2f5f7-137">成功打开对象。</span><span class="sxs-lookup"><span data-stu-id="2f5f7-137">The object was successfully opened.</span></span>
    
<span data-ttu-id="2f5f7-138">MAPI_E_NO_ACCESS</span><span class="sxs-lookup"><span data-stu-id="2f5f7-138">MAPI_E_NO_ACCESS</span></span> 
  
> <span data-ttu-id="2f5f7-139">用户具有权限不足，无法打开的对象，或尝试打开只读对象具有读/写权限。</span><span class="sxs-lookup"><span data-stu-id="2f5f7-139">Either the user has insufficient permissions to open the object or an attempt was made to open a read-only object with read/write permission.</span></span>
    
<span data-ttu-id="2f5f7-140">MAPI_E_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="2f5f7-140">MAPI_E_NOT_FOUND</span></span> 
  
> <span data-ttu-id="2f5f7-141">指定_lpEntryID_的项标识符不代表一个对象。</span><span class="sxs-lookup"><span data-stu-id="2f5f7-141">The entry identifier specified by  _lpEntryID_ does not represent an object.</span></span> 
    
<span data-ttu-id="2f5f7-142">MAPI_E_UNKNOWN_ENTRYID</span><span class="sxs-lookup"><span data-stu-id="2f5f7-142">MAPI_E_UNKNOWN_ENTRYID</span></span> 
  
> <span data-ttu-id="2f5f7-143">_LpEntryID_参数中的项标识符不是格式的容器识别。</span><span class="sxs-lookup"><span data-stu-id="2f5f7-143">The entry identifier in the  _lpEntryID_ parameter is not of a format recognized by the container.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="2f5f7-144">说明</span><span class="sxs-lookup"><span data-stu-id="2f5f7-144">Remarks</span></span>

<span data-ttu-id="2f5f7-145">**IMAPIContainer::OpenEntry**方法打开整个容器对象，并返回到接口实现用于进一步访问的指针。</span><span class="sxs-lookup"><span data-stu-id="2f5f7-145">The **IMAPIContainer::OpenEntry** method opens an object throughout a container and returns a pointer to an interface implementation to use for further access.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="2f5f7-146">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="2f5f7-146">Notes to callers</span></span>

<span data-ttu-id="2f5f7-147">由于无需服务提供程序返回的接口标识符_lpInterface_参数中指定的类型的接口实现，检查指向_lpulObjType_参数的值。</span><span class="sxs-lookup"><span data-stu-id="2f5f7-147">Because service providers are not required to return an interface implementation of the type specified by the interface identifier in the  _lpInterface_ parameter, check the value pointed to by the  _lpulObjType_ parameter.</span></span> <span data-ttu-id="2f5f7-148">如有必要，强制转换中_lppUnk_返回到适当类型的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="2f5f7-148">If necessary, cast the pointer returned in  _lppUnk_ to a pointer of the appropriate type.</span></span> 
  
<span data-ttu-id="2f5f7-149">默认情况下，服务提供商对象使用只读访问权限打开如果设置 MAPI_MODIFY 或 MAPI_BEST_ACCESS 标志。</span><span class="sxs-lookup"><span data-stu-id="2f5f7-149">By default, service providers open objects with read-only access unless you set either the MAPI_MODIFY or MAPI_BEST_ACCESS flag.</span></span> <span data-ttu-id="2f5f7-150">当这些标志之一设置时，服务提供商将尝试返回可修改对象。</span><span class="sxs-lookup"><span data-stu-id="2f5f7-150">When one of these flags is set, service providers attempt to return a modifiable object.</span></span> <span data-ttu-id="2f5f7-151">但是，不假定，因为请求一个可修改的对象，该对象打开的对象具有读/写权限。</span><span class="sxs-lookup"><span data-stu-id="2f5f7-151">However, do not assume that because you requested a modifiable object that the opened object has read/write permission.</span></span> <span data-ttu-id="2f5f7-152">通过规划的后续修改失败或检索对象的**PR_ACCESS_LEVEL**属性确定**OpenEntry**授予的访问级别的机会。</span><span class="sxs-lookup"><span data-stu-id="2f5f7-152">Either plan for the chance of a subsequent modification to fail or retrieve the object's **PR_ACCESS_LEVEL** property to determine the access level granted by **OpenEntry**.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="2f5f7-153">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2f5f7-153">See also</span></span>



[<span data-ttu-id="2f5f7-154">IMAPIContainer : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="2f5f7-154">IMAPIContainer : IMAPIProp</span></span>](imapicontainerimapiprop.md)

