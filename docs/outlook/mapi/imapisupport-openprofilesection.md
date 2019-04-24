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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: e7f13acc34a77b79057d32fd4049db7222dadf49
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32326444"
---
# <a name="imapisupportopenprofilesection"></a><span data-ttu-id="d7d4c-103">IMAPISupport::OpenProfileSection</span><span class="sxs-lookup"><span data-stu-id="d7d4c-103">IMAPISupport::OpenProfileSection</span></span>

  
  
<span data-ttu-id="d7d4c-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="d7d4c-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="d7d4c-105">打开当前配置文件的一个部分, 并返回一个[IProfSect](iprofsectimapiprop.md)指针以供进一步访问。</span><span class="sxs-lookup"><span data-stu-id="d7d4c-105">Opens a section of the current profile and returns an [IProfSect](iprofsectimapiprop.md) pointer for further access.</span></span> 
  
```cpp
HRESULT OpenProfileSection(
LPMAPIUID lpUid,
ULONG ulFlags,
LPPROFSECT FAR * lppProfileObj
);
```

## <a name="parameters"></a><span data-ttu-id="d7d4c-106">参数</span><span class="sxs-lookup"><span data-stu-id="d7d4c-106">Parameters</span></span>

 <span data-ttu-id="d7d4c-107">_lpUid_</span><span class="sxs-lookup"><span data-stu-id="d7d4c-107">_lpUid_</span></span>
  
> <span data-ttu-id="d7d4c-108">实时指向标识要打开的配置文件部分的[MAPIUID](mapiuid.md)结构的指针。</span><span class="sxs-lookup"><span data-stu-id="d7d4c-108">[in] A pointer to the [MAPIUID](mapiuid.md) structure that identifies the profile section to be opened.</span></span> <span data-ttu-id="d7d4c-109">为_lpUid_参数传递 NULL 将打开调用者的配置文件部分。</span><span class="sxs-lookup"><span data-stu-id="d7d4c-109">Passing NULL for the  _lpUid_ parameter opens the caller's profile section.</span></span> 
    
 <span data-ttu-id="d7d4c-110">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="d7d4c-110">_ulFlags_</span></span>
  
> <span data-ttu-id="d7d4c-111">实时用于控制如何打开 profile 节的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="d7d4c-111">[in] A bitmask of flags that controls how the profile section is opened.</span></span> <span data-ttu-id="d7d4c-112">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="d7d4c-112">The following flags can be set:</span></span>
    
<span data-ttu-id="d7d4c-113">MAPI_DEFERRED_ERRORS</span><span class="sxs-lookup"><span data-stu-id="d7d4c-113">MAPI_DEFERRED_ERRORS</span></span> 
  
> <span data-ttu-id="d7d4c-114">允许**OpenProfileSection**在配置文件节对调用方完全可访问之前成功返回。</span><span class="sxs-lookup"><span data-stu-id="d7d4c-114">Allows **OpenProfileSection** to return successfully, possibly before the profile section is fully accessible to the caller.</span></span> <span data-ttu-id="d7d4c-115">如果 profile 节不可访问, 则进行后续的对象调用可能会导致错误。</span><span class="sxs-lookup"><span data-stu-id="d7d4c-115">If the profile section is not accessible, making a subsequent object call can result in an error.</span></span> 
    
<span data-ttu-id="d7d4c-116">MAPI_MODIFY</span><span class="sxs-lookup"><span data-stu-id="d7d4c-116">MAPI_MODIFY</span></span> 
  
> <span data-ttu-id="d7d4c-117">请求读取/写入权限。</span><span class="sxs-lookup"><span data-stu-id="d7d4c-117">Requests read/write permission.</span></span> <span data-ttu-id="d7d4c-118">默认情况下, 对象以只读方式打开, 并且在假定已授予读/写权限时, 调用方不应这样做。</span><span class="sxs-lookup"><span data-stu-id="d7d4c-118">By default, objects are opened as read-only, and callers should not work on the assumption that read/write permission has been granted.</span></span> 
    
 <span data-ttu-id="d7d4c-119">_lppProfileObj_</span><span class="sxs-lookup"><span data-stu-id="d7d4c-119">_lppProfileObj_</span></span>
  
> <span data-ttu-id="d7d4c-120">排除指向打开的配置文件部分的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="d7d4c-120">[out] A pointer to a pointer to the opened profile section.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="d7d4c-121">返回值</span><span class="sxs-lookup"><span data-stu-id="d7d4c-121">Return value</span></span>

<span data-ttu-id="d7d4c-122">S_OK</span><span class="sxs-lookup"><span data-stu-id="d7d4c-122">S_OK</span></span> 
  
> <span data-ttu-id="d7d4c-123">已成功打开 "配置文件" 部分。</span><span class="sxs-lookup"><span data-stu-id="d7d4c-123">The profile section was successfully opened.</span></span>
    
<span data-ttu-id="d7d4c-124">MAPI_E_NO_ACCESS</span><span class="sxs-lookup"><span data-stu-id="d7d4c-124">MAPI_E_NO_ACCESS</span></span> 
  
> <span data-ttu-id="d7d4c-125">试图修改只读配置文件部分或访问呼叫者具有的权限不足的对象。</span><span class="sxs-lookup"><span data-stu-id="d7d4c-125">An attempt was made to modify a read-only profile section or to access an object for which the caller has insufficient permissions.</span></span>
    
<span data-ttu-id="d7d4c-126">MAPI_E_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="d7d4c-126">MAPI_E_NOT_FOUND</span></span> 
  
> <span data-ttu-id="d7d4c-127">没有与_lpEntryID_中传递的条目标识符相关联的配置文件部分。</span><span class="sxs-lookup"><span data-stu-id="d7d4c-127">There is not a profile section associated with the entry identifier passed in  _lpEntryID_.</span></span>
    
<span data-ttu-id="d7d4c-128">MAPI_E_UNKNOWN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="d7d4c-128">MAPI_E_UNKNOWN_FLAGS</span></span> 
  
> <span data-ttu-id="d7d4c-129">使用了保留或不受支持的标志, 因此操作未完成。</span><span class="sxs-lookup"><span data-stu-id="d7d4c-129">Reserved or unsupported flags were used and, therefore, the operation did not complete.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="d7d4c-130">注解</span><span class="sxs-lookup"><span data-stu-id="d7d4c-130">Remarks</span></span>

<span data-ttu-id="d7d4c-131">**IMAPISupport:: OpenProfileSection**方法是为所有支持对象实现的。</span><span class="sxs-lookup"><span data-stu-id="d7d4c-131">The **IMAPISupport::OpenProfileSection** method is implemented for all support objects.</span></span> <span data-ttu-id="d7d4c-132">服务提供程序和邮件服务调用**OpenProfileSection**以打开配置文件部分, 并检索指向其**IProfSect**接口实现的指针。</span><span class="sxs-lookup"><span data-stu-id="d7d4c-132">Service providers and message services call **OpenProfileSection** to open a profile section and retrieve a pointer to its **IProfSect** interface implementation.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="d7d4c-133">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="d7d4c-133">Notes to callers</span></span>

 <span data-ttu-id="d7d4c-134">**OpenProfileSection**将配置文件节以只读方式打开, 除非您在_ulFlags_参数中设置了 MAPI_MODIFY 标志, 并且您的权限已足够。</span><span class="sxs-lookup"><span data-stu-id="d7d4c-134">**OpenProfileSection** opens profile sections as read-only, unless you set the MAPI_MODIFY flag in the  _ulFlags_ parameter and your permission is sufficient.</span></span> <span data-ttu-id="d7d4c-135">设置此标志不能保证读/写权限;您授予的权限取决于您的访问级别和对象。</span><span class="sxs-lookup"><span data-stu-id="d7d4c-135">Setting this flag does not guarantee read/write permission; the permissions that you are granted depend on your access level and the object.</span></span> 
  
<span data-ttu-id="d7d4c-136">如果**OpenProfileSection**尝试以只读方式打开不存在的配置文件节, 则它将返回 MAPI_E_NOT_FOUND。</span><span class="sxs-lookup"><span data-stu-id="d7d4c-136">If **OpenProfileSection** attempts to open a nonexistent profile section as read-only, it returns MAPI_E_NOT_FOUND.</span></span> <span data-ttu-id="d7d4c-137">如果**OpenProfileSection**尝试以读/写方式打开不存在的配置文件节, 则它会创建 "配置文件" 部分并返回**IProfSect**指针。</span><span class="sxs-lookup"><span data-stu-id="d7d4c-137">If **OpenProfileSection** attempts to open a nonexistent profile section as read/write, it creates the profile section and returns the **IProfSect** pointer.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="d7d4c-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d7d4c-138">See also</span></span>



[<span data-ttu-id="d7d4c-139">IMAPIProp : IUnknown</span><span class="sxs-lookup"><span data-stu-id="d7d4c-139">IMAPIProp : IUnknown</span></span>](imapipropiunknown.md)
  
[<span data-ttu-id="d7d4c-140">IProfSect : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="d7d4c-140">IProfSect : IMAPIProp</span></span>](iprofsectimapiprop.md)
  
[<span data-ttu-id="d7d4c-141">MAPIUID</span><span class="sxs-lookup"><span data-stu-id="d7d4c-141">MAPIUID</span></span>](mapiuid.md)
  
[<span data-ttu-id="d7d4c-142">IMAPISupport : IUnknown</span><span class="sxs-lookup"><span data-stu-id="d7d4c-142">IMAPISupport : IUnknown</span></span>](imapisupportiunknown.md)

