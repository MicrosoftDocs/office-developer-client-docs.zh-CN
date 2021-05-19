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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 9598e0c90c16db14cdc3a46d2b2ae74e0d9a9300
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33423634"
---
# <a name="imapicontaineropenentry"></a><span data-ttu-id="c59a7-103">IMAPIContainer::OpenEntry</span><span class="sxs-lookup"><span data-stu-id="c59a7-103">IMAPIContainer::OpenEntry</span></span>

  
  
<span data-ttu-id="c59a7-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="c59a7-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="c59a7-105">打开容器中的对象，返回接口指针以进一步访问。</span><span class="sxs-lookup"><span data-stu-id="c59a7-105">Opens an object in the container, returning an interface pointer for further access.</span></span>
  
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

## <a name="parameters"></a><span data-ttu-id="c59a7-106">参数</span><span class="sxs-lookup"><span data-stu-id="c59a7-106">Parameters</span></span>

 <span data-ttu-id="c59a7-107">_cbEntryID_</span><span class="sxs-lookup"><span data-stu-id="c59a7-107">_cbEntryID_</span></span>
  
> <span data-ttu-id="c59a7-108">[in]  _lpEntryID_ 参数指向的条目标识符中的字节计数。</span><span class="sxs-lookup"><span data-stu-id="c59a7-108">[in] The byte count in the entry identifier pointed to by the  _lpEntryID_ parameter.</span></span> 
    
 <span data-ttu-id="c59a7-109">_lpEntryID_</span><span class="sxs-lookup"><span data-stu-id="c59a7-109">_lpEntryID_</span></span>
  
> <span data-ttu-id="c59a7-110">[in]指向要打开的对象的条目标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="c59a7-110">[in] A pointer to the entry identifier of the object to open.</span></span> <span data-ttu-id="c59a7-111">如果  _lpEntryID_ 设置为 NULL，则打开容器层次结构中的顶级容器。</span><span class="sxs-lookup"><span data-stu-id="c59a7-111">If  _lpEntryID_ is set to NULL, the top-level container in the container's hierarchy is opened.</span></span> 
    
 <span data-ttu-id="c59a7-112">_lpInterface_</span><span class="sxs-lookup"><span data-stu-id="c59a7-112">_lpInterface_</span></span>
  
> <span data-ttu-id="c59a7-113">[in]指向接口标识符的指针 (IID) 表示用于访问对象的接口。</span><span class="sxs-lookup"><span data-stu-id="c59a7-113">[in] A pointer to the interface identifier (IID) that represents the interface to be used to access the object.</span></span> <span data-ttu-id="c59a7-114">传递 NULL 会导致返回对象的标准接口的标识符。</span><span class="sxs-lookup"><span data-stu-id="c59a7-114">Passing NULL results in the identifier for the object's standard interface being returned.</span></span> <span data-ttu-id="c59a7-115">对于消息，标准接口是 [IMAPIMessageSite ： IUnknown](imapimessagesiteiunknown.md);对于文件夹，它是 [IMAPIFolder ： IMAPIContainer](imapifolderimapicontainer.md)。</span><span class="sxs-lookup"><span data-stu-id="c59a7-115">For messages, the standard interface is [IMAPIMessageSite : IUnknown](imapimessagesiteiunknown.md); for folders, it is [IMAPIFolder : IMAPIContainer](imapifolderimapicontainer.md).</span></span> <span data-ttu-id="c59a7-116">通讯簿对象的标准接口是 [IDistList ： IMAPIContainer](idistlistimapicontainer.md) 表示通讯组列表和 [IMailUser ： IMAPIProp](imailuserimapiprop.md) 消息用户。</span><span class="sxs-lookup"><span data-stu-id="c59a7-116">The standard interfaces for address book objects are [IDistList : IMAPIContainer](idistlistimapicontainer.md) for a distribution list and [IMailUser : IMAPIProp](imailuserimapiprop.md) for a messaging user.</span></span> 
    
 <span data-ttu-id="c59a7-117">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="c59a7-117">_ulFlags_</span></span>
  
> <span data-ttu-id="c59a7-118">[in]控制对象打开方式的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="c59a7-118">[in] A bitmask of flags that controls how the object is opened.</span></span> <span data-ttu-id="c59a7-119">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="c59a7-119">The following flags can be set:</span></span>
    
<span data-ttu-id="c59a7-120">MAPI_BEST_ACCESS</span><span class="sxs-lookup"><span data-stu-id="c59a7-120">MAPI_BEST_ACCESS</span></span> 
  
> <span data-ttu-id="c59a7-121">请求以用户允许的最大网络权限和最大客户端应用程序访问权限打开对象。</span><span class="sxs-lookup"><span data-stu-id="c59a7-121">Requests that the object will be opened with the maximum network permissions allowed for the user and the maximum client application access.</span></span> <span data-ttu-id="c59a7-122">例如，如果客户端具有读/写权限，则应该使用读/写权限打开对象;如果客户端具有只读访问权限，则应该以只读访问权限打开对象。</span><span class="sxs-lookup"><span data-stu-id="c59a7-122">For example, if the client has read/write permission, the object should be opened with read/write permission; if the client has read-only access, the object should be opened with read-only access.</span></span> 
    
<span data-ttu-id="c59a7-123">MAPI_DEFERRED_ERRORS</span><span class="sxs-lookup"><span data-stu-id="c59a7-123">MAPI_DEFERRED_ERRORS</span></span> 
  
> <span data-ttu-id="c59a7-124">允许 **OpenEntry** 在对象完全可供调用客户端使用之前成功返回。</span><span class="sxs-lookup"><span data-stu-id="c59a7-124">Allows **OpenEntry** to return successfully, possibly before the object is fully available to the calling client.</span></span> <span data-ttu-id="c59a7-125">如果该对象不可用，则进行后续对象调用可能会引发错误。</span><span class="sxs-lookup"><span data-stu-id="c59a7-125">If the object is not available, making a subsequent object call can raise an error.</span></span> 
    
<span data-ttu-id="c59a7-126">MAPI_MODIFY</span><span class="sxs-lookup"><span data-stu-id="c59a7-126">MAPI_MODIFY</span></span> 
  
> <span data-ttu-id="c59a7-127">请求读/写权限。</span><span class="sxs-lookup"><span data-stu-id="c59a7-127">Requests read/write permission.</span></span> <span data-ttu-id="c59a7-128">默认情况下，使用只读访问权限打开对象，客户端不应在已授予读/写权限的假设下工作。</span><span class="sxs-lookup"><span data-stu-id="c59a7-128">By default, objects are opened with read-only access, and clients should not work on the assumption that read/write permission has been granted.</span></span> 
    
<span data-ttu-id="c59a7-129">SHOW_SOFT_DELETES</span><span class="sxs-lookup"><span data-stu-id="c59a7-129">SHOW_SOFT_DELETES</span></span>
  
> <span data-ttu-id="c59a7-130">显示当前标记为软删除的项目，即它们处于已删除项目的保留时间阶段。</span><span class="sxs-lookup"><span data-stu-id="c59a7-130">Shows items that are currently marked as soft deleted—that is, they are in the deleted item retention time phase.</span></span>
    
 <span data-ttu-id="c59a7-131">_lpulObjType_</span><span class="sxs-lookup"><span data-stu-id="c59a7-131">_lpulObjType_</span></span>
  
> <span data-ttu-id="c59a7-132">[out]指向已打开对象的类型的指针。</span><span class="sxs-lookup"><span data-stu-id="c59a7-132">[out] A pointer to the opened object's type.</span></span>
    
 <span data-ttu-id="c59a7-133">_lppUnk_</span><span class="sxs-lookup"><span data-stu-id="c59a7-133">_lppUnk_</span></span>
  
> <span data-ttu-id="c59a7-134">[out]指向用于访问打开对象的接口实现指针的指针。</span><span class="sxs-lookup"><span data-stu-id="c59a7-134">[out] A pointer to a pointer to the interface implementation to use to access the open object.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="c59a7-135">返回值</span><span class="sxs-lookup"><span data-stu-id="c59a7-135">Return value</span></span>

<span data-ttu-id="c59a7-136">S_OK</span><span class="sxs-lookup"><span data-stu-id="c59a7-136">S_OK</span></span> 
  
> <span data-ttu-id="c59a7-137">已成功打开对象。</span><span class="sxs-lookup"><span data-stu-id="c59a7-137">The object was successfully opened.</span></span>
    
<span data-ttu-id="c59a7-138">MAPI_E_NO_ACCESS</span><span class="sxs-lookup"><span data-stu-id="c59a7-138">MAPI_E_NO_ACCESS</span></span> 
  
> <span data-ttu-id="c59a7-139">用户没有足够的权限打开对象，或者试图打开具有读/写权限的只读对象。</span><span class="sxs-lookup"><span data-stu-id="c59a7-139">Either the user has insufficient permissions to open the object or an attempt was made to open a read-only object with read/write permission.</span></span>
    
<span data-ttu-id="c59a7-140">MAPI_E_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="c59a7-140">MAPI_E_NOT_FOUND</span></span> 
  
> <span data-ttu-id="c59a7-141">_lpEntryID_ 指定的条目标识符不表示对象。</span><span class="sxs-lookup"><span data-stu-id="c59a7-141">The entry identifier specified by  _lpEntryID_ does not represent an object.</span></span> 
    
<span data-ttu-id="c59a7-142">MAPI_E_UNKNOWN_ENTRYID</span><span class="sxs-lookup"><span data-stu-id="c59a7-142">MAPI_E_UNKNOWN_ENTRYID</span></span> 
  
> <span data-ttu-id="c59a7-143">_lpEntryID_ 参数中的条目标识符不是容器识别的格式。</span><span class="sxs-lookup"><span data-stu-id="c59a7-143">The entry identifier in the  _lpEntryID_ parameter is not of a format recognized by the container.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="c59a7-144">备注</span><span class="sxs-lookup"><span data-stu-id="c59a7-144">Remarks</span></span>

<span data-ttu-id="c59a7-145">**IMAPIContainer：：OpenEntry** 方法在整个容器中打开一个对象，并返回指向接口实现以用于进一步访问的指针。</span><span class="sxs-lookup"><span data-stu-id="c59a7-145">The **IMAPIContainer::OpenEntry** method opens an object throughout a container and returns a pointer to an interface implementation to use for further access.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="c59a7-146">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="c59a7-146">Notes to callers</span></span>

<span data-ttu-id="c59a7-147">由于服务提供商不需要返回  _由 lpInterface_ 参数中的接口标识符指定的类型的接口实现，请检查  _lpulObjType_ 参数指向的值。</span><span class="sxs-lookup"><span data-stu-id="c59a7-147">Because service providers are not required to return an interface implementation of the type specified by the interface identifier in the  _lpInterface_ parameter, check the value pointed to by the  _lpulObjType_ parameter.</span></span> <span data-ttu-id="c59a7-148">如有必要，将  _lppUnk_ 中返回的指针强制转换到相应类型的指针。</span><span class="sxs-lookup"><span data-stu-id="c59a7-148">If necessary, cast the pointer returned in  _lppUnk_ to a pointer of the appropriate type.</span></span> 
  
<span data-ttu-id="c59a7-149">默认情况下，服务提供商打开具有只读访问权限的对象，除非您设置 MAPI_MODIFY 或 MAPI_BEST_ACCESS 标志。</span><span class="sxs-lookup"><span data-stu-id="c59a7-149">By default, service providers open objects with read-only access unless you set either the MAPI_MODIFY or MAPI_BEST_ACCESS flag.</span></span> <span data-ttu-id="c59a7-150">当设置其中一个标志时，服务提供商会尝试返回一个可修改的对象。</span><span class="sxs-lookup"><span data-stu-id="c59a7-150">When one of these flags is set, service providers attempt to return a modifiable object.</span></span> <span data-ttu-id="c59a7-151">但是，不要假定由于您请求了一个可修改对象，而打开的对象具有读/写权限。</span><span class="sxs-lookup"><span data-stu-id="c59a7-151">However, do not assume that because you requested a modifiable object that the opened object has read/write permission.</span></span> <span data-ttu-id="c59a7-152">无论是规划后续修改失败的可能性，还是检索对象的 **PR_ACCESS_LEVEL** 属性来确定 **OpenEntry 授予的访问级别**。</span><span class="sxs-lookup"><span data-stu-id="c59a7-152">Either plan for the chance of a subsequent modification to fail or retrieve the object's **PR_ACCESS_LEVEL** property to determine the access level granted by **OpenEntry**.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="c59a7-153">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c59a7-153">See also</span></span>



[<span data-ttu-id="c59a7-154">IMAPIContainer : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="c59a7-154">IMAPIContainer : IMAPIProp</span></span>](imapicontainerimapiprop.md)

