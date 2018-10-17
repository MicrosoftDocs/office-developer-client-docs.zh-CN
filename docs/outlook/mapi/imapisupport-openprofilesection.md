---
title: IMAPISupportOpenProfileSection
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISupport.OpenProfileSection
api_type:
- COM
ms.assetid: cd1fa994-9531-46c4-94e5-505e7f90b884
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 2e1f546d33d4781f60df56b12fce437d1e7bd675
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22588221"
---
# <a name="imapisupportopenprofilesection"></a><span data-ttu-id="94fb4-103">IMAPISupport::OpenProfileSection</span><span class="sxs-lookup"><span data-stu-id="94fb4-103">IMAPISupport::OpenProfileSection</span></span>

  
  
<span data-ttu-id="94fb4-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="94fb4-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="94fb4-105">打开当前配置文件的节并返回进一步访问[IProfSect](iprofsectimapiprop.md)指针。</span><span class="sxs-lookup"><span data-stu-id="94fb4-105">Opens a section of the current profile and returns an [IProfSect](iprofsectimapiprop.md) pointer for further access.</span></span> 
  
```cpp
HRESULT OpenProfileSection(
LPMAPIUID lpUid,
ULONG ulFlags,
LPPROFSECT FAR * lppProfileObj
);
```

## <a name="parameters"></a><span data-ttu-id="94fb4-106">参数</span><span class="sxs-lookup"><span data-stu-id="94fb4-106">Parameters</span></span>

 <span data-ttu-id="94fb4-107">_lpUid_</span><span class="sxs-lookup"><span data-stu-id="94fb4-107">_lpUid_</span></span>
  
> <span data-ttu-id="94fb4-108">[in]指向标识配置文件部分，要打开的[MAPIUID](mapiuid.md)结构的指针。</span><span class="sxs-lookup"><span data-stu-id="94fb4-108">[in] A pointer to the [MAPIUID](mapiuid.md) structure that identifies the profile section to be opened.</span></span> <span data-ttu-id="94fb4-109">_LpUid_参数传递 NULL 将打开呼叫者的配置文件一节。</span><span class="sxs-lookup"><span data-stu-id="94fb4-109">Passing NULL for the  _lpUid_ parameter opens the caller's profile section.</span></span> 
    
 <span data-ttu-id="94fb4-110">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="94fb4-110">_ulFlags_</span></span>
  
> <span data-ttu-id="94fb4-111">[in]位掩码的标志，控制如何打开配置文件部分。</span><span class="sxs-lookup"><span data-stu-id="94fb4-111">[in] A bitmask of flags that controls how the profile section is opened.</span></span> <span data-ttu-id="94fb4-112">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="94fb4-112">The following flags can be set:</span></span>
    
<span data-ttu-id="94fb4-113">MAPI_DEFERRED_ERRORS</span><span class="sxs-lookup"><span data-stu-id="94fb4-113">MAPI_DEFERRED_ERRORS</span></span> 
  
> <span data-ttu-id="94fb4-114">允许**OpenProfileSection**成功返回可能之前配置文件节是完全访问呼叫者。</span><span class="sxs-lookup"><span data-stu-id="94fb4-114">Allows **OpenProfileSection** to return successfully, possibly before the profile section is fully accessible to the caller.</span></span> <span data-ttu-id="94fb4-115">如果配置文件部分不可访问，则进行后续对象呼叫会导致错误。</span><span class="sxs-lookup"><span data-stu-id="94fb4-115">If the profile section is not accessible, making a subsequent object call can result in an error.</span></span> 
    
<span data-ttu-id="94fb4-116">MAPI_MODIFY</span><span class="sxs-lookup"><span data-stu-id="94fb4-116">MAPI_MODIFY</span></span> 
  
> <span data-ttu-id="94fb4-117">请求读/写权限。</span><span class="sxs-lookup"><span data-stu-id="94fb4-117">Requests read/write permission.</span></span> <span data-ttu-id="94fb4-118">默认情况下，以只读方式打开对象和呼叫者以为，读/写权限授予不起作用。</span><span class="sxs-lookup"><span data-stu-id="94fb4-118">By default, objects are opened as read-only, and callers should not work on the assumption that read/write permission has been granted.</span></span> 
    
 <span data-ttu-id="94fb4-119">_lppProfileObj_</span><span class="sxs-lookup"><span data-stu-id="94fb4-119">_lppProfileObj_</span></span>
  
> <span data-ttu-id="94fb4-120">[输出]指向打开配置文件部分的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="94fb4-120">[out] A pointer to a pointer to the opened profile section.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="94fb4-121">返回值</span><span class="sxs-lookup"><span data-stu-id="94fb4-121">Return value</span></span>

<span data-ttu-id="94fb4-122">S_OK</span><span class="sxs-lookup"><span data-stu-id="94fb4-122">S_OK</span></span> 
  
> <span data-ttu-id="94fb4-123">已成功打开配置文件部分。</span><span class="sxs-lookup"><span data-stu-id="94fb4-123">The profile section was successfully opened.</span></span>
    
<span data-ttu-id="94fb4-124">MAPI_E_NO_ACCESS</span><span class="sxs-lookup"><span data-stu-id="94fb4-124">MAPI_E_NO_ACCESS</span></span> 
  
> <span data-ttu-id="94fb4-125">尝试来修改只读的配置文件节或访问其呼叫者没有足够的权限的对象。</span><span class="sxs-lookup"><span data-stu-id="94fb4-125">An attempt was made to modify a read-only profile section or to access an object for which the caller has insufficient permissions.</span></span>
    
<span data-ttu-id="94fb4-126">MAPI_E_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="94fb4-126">MAPI_E_NOT_FOUND</span></span> 
  
> <span data-ttu-id="94fb4-127">没有与_lpEntryID_中传递的项标识符的配置文件一节。</span><span class="sxs-lookup"><span data-stu-id="94fb4-127">There is not a profile section associated with the entry identifier passed in  _lpEntryID_.</span></span>
    
<span data-ttu-id="94fb4-128">MAPI_E_UNKNOWN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="94fb4-128">MAPI_E_UNKNOWN_FLAGS</span></span> 
  
> <span data-ttu-id="94fb4-129">使用保留或不受支持的标志，而且，因此，该操作未完成。</span><span class="sxs-lookup"><span data-stu-id="94fb4-129">Reserved or unsupported flags were used and, therefore, the operation did not complete.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="94fb4-130">注解</span><span class="sxs-lookup"><span data-stu-id="94fb4-130">Remarks</span></span>

<span data-ttu-id="94fb4-131">对于所有支持对象实现**IMAPISupport::OpenProfileSection**方法。</span><span class="sxs-lookup"><span data-stu-id="94fb4-131">The **IMAPISupport::OpenProfileSection** method is implemented for all support objects.</span></span> <span data-ttu-id="94fb4-132">服务提供商和消息服务调用**OpenProfileSection**以打开配置文件一节并检索指向其**IProfSect**接口实现。</span><span class="sxs-lookup"><span data-stu-id="94fb4-132">Service providers and message services call **OpenProfileSection** to open a profile section and retrieve a pointer to its **IProfSect** interface implementation.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="94fb4-133">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="94fb4-133">Notes to callers</span></span>

 <span data-ttu-id="94fb4-134">**OpenProfileSection**打开配置文件部分作为只读的除非_ulFlags_参数中设置 MAPI_MODIFY 标记和您的权限就足够了。</span><span class="sxs-lookup"><span data-stu-id="94fb4-134">**OpenProfileSection** opens profile sections as read-only, unless you set the MAPI_MODIFY flag in the  _ulFlags_ parameter and your permission is sufficient.</span></span> <span data-ttu-id="94fb4-135">设置此标志不保证读/写权限;您已被授予的权限取决于您的访问级别和对象。</span><span class="sxs-lookup"><span data-stu-id="94fb4-135">Setting this flag does not guarantee read/write permission; the permissions that you are granted depend on your access level and the object.</span></span> 
  
<span data-ttu-id="94fb4-136">如果**OpenProfileSection**尝试打开以只读方式不存在配置文件一节，则将返回 MAPI_E_NOT_FOUND。</span><span class="sxs-lookup"><span data-stu-id="94fb4-136">If **OpenProfileSection** attempts to open a nonexistent profile section as read-only, it returns MAPI_E_NOT_FOUND.</span></span> <span data-ttu-id="94fb4-137">如果**OpenProfileSection**尝试打开以读/写不存在配置文件部分，它会创建配置文件部分，并返回**IProfSect**指针。</span><span class="sxs-lookup"><span data-stu-id="94fb4-137">If **OpenProfileSection** attempts to open a nonexistent profile section as read/write, it creates the profile section and returns the **IProfSect** pointer.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="94fb4-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="94fb4-138">See also</span></span>



[<span data-ttu-id="94fb4-139">IMAPIProp : IUnknown</span><span class="sxs-lookup"><span data-stu-id="94fb4-139">IMAPIProp : IUnknown</span></span>](imapipropiunknown.md)
  
[<span data-ttu-id="94fb4-140">IProfSect : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="94fb4-140">IProfSect : IMAPIProp</span></span>](iprofsectimapiprop.md)
  
[<span data-ttu-id="94fb4-141">MAPIUID</span><span class="sxs-lookup"><span data-stu-id="94fb4-141">MAPIUID</span></span>](mapiuid.md)
  
[<span data-ttu-id="94fb4-142">IMAPISupport : IUnknown</span><span class="sxs-lookup"><span data-stu-id="94fb4-142">IMAPISupport : IUnknown</span></span>](imapisupportiunknown.md)
