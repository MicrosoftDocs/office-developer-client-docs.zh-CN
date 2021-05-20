---
title: IMAPISessionOpenProfileSection
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISession.OpenProfileSection
api_type:
- COM
ms.assetid: e2757028-27e7-4fc0-9674-e8e30737ef1d
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 9d7c1693dfb22ae89afed8cbe1426c1e186f8b2d
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33439917"
---
# <a name="imapisessionopenprofilesection"></a><span data-ttu-id="914ba-103">IMAPISession::OpenProfileSection</span><span class="sxs-lookup"><span data-stu-id="914ba-103">IMAPISession::OpenProfileSection</span></span>

  
  
<span data-ttu-id="914ba-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="914ba-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="914ba-105">打开当前配置文件的一部分并返回 [IProfSect](iprofsectimapiprop.md) 指针以进一步访问。</span><span class="sxs-lookup"><span data-stu-id="914ba-105">Opens a section of the current profile and returns an [IProfSect](iprofsectimapiprop.md) pointer for further access.</span></span> 
  
```cpp
HRESULT OpenProfileSection(
  LPMAPIUID lpUID,
  LPCIID lpInterface,
  ULONG ulFlags,
  LPPROFSECT FAR * lppProfSect
);
```

## <a name="parameters"></a><span data-ttu-id="914ba-106">参数</span><span class="sxs-lookup"><span data-stu-id="914ba-106">Parameters</span></span>

 <span data-ttu-id="914ba-107">_lpUID_</span><span class="sxs-lookup"><span data-stu-id="914ba-107">_lpUID_</span></span>
  
> <span data-ttu-id="914ba-108">[in]指向标识配置文件节的 [MAPIUID](mapiuid.md) 结构的指针。</span><span class="sxs-lookup"><span data-stu-id="914ba-108">[in] A pointer to the [MAPIUID](mapiuid.md) structure that identifies the profile section.</span></span> 
    
 <span data-ttu-id="914ba-109">_lpInterface_</span><span class="sxs-lookup"><span data-stu-id="914ba-109">_lpInterface_</span></span>
  
> <span data-ttu-id="914ba-110">[in]指向接口标识符的 (IID) 表示用于访问配置文件节的接口。</span><span class="sxs-lookup"><span data-stu-id="914ba-110">[in] A pointer to the interface identifier (IID) that represents the interface to be used to access the profile section.</span></span> <span data-ttu-id="914ba-111">传递 NULL 会导致  _lppProfSect_ 参数返回指向配置文件节的标准接口 **IProfSect** 的指针。</span><span class="sxs-lookup"><span data-stu-id="914ba-111">Passing NULL causes the  _lppProfSect_ parameter to return a pointer to the profile section's standard interface, **IProfSect**.</span></span>
    
 <span data-ttu-id="914ba-112">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="914ba-112">_ulFlags_</span></span>
  
> <span data-ttu-id="914ba-113">[in]控制对配置文件节的访问的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="914ba-113">[in] A bitmask of flags that controls access to the profile section.</span></span> <span data-ttu-id="914ba-114">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="914ba-114">The following flags can be set:</span></span>
    
<span data-ttu-id="914ba-115">MAPI_DEFERRED_ERRORS</span><span class="sxs-lookup"><span data-stu-id="914ba-115">MAPI_DEFERRED_ERRORS</span></span> 
  
> <span data-ttu-id="914ba-116">允许 **OpenProfileSection** 成功返回，可能在配置文件部分完全可供调用客户端使用之前。</span><span class="sxs-lookup"><span data-stu-id="914ba-116">Allows **OpenProfileSection** to return successfully, possibly before the profile section is fully available to the calling client.</span></span> <span data-ttu-id="914ba-117">如果配置文件部分不可用，则对它进行后续调用可能会导致错误。</span><span class="sxs-lookup"><span data-stu-id="914ba-117">If the profile section is not available, making a subsequent call to it can cause an error.</span></span> 
    
<span data-ttu-id="914ba-118">MAPI_FORCE_ACCESS</span><span class="sxs-lookup"><span data-stu-id="914ba-118">MAPI_FORCE_ACCESS</span></span>
  
> <span data-ttu-id="914ba-119">允许访问不属于提供程序的配置文件节。</span><span class="sxs-lookup"><span data-stu-id="914ba-119">Allows access to a profile section that does not belong to the provider.</span></span>
    
<span data-ttu-id="914ba-120">MAPI_MODIFY</span><span class="sxs-lookup"><span data-stu-id="914ba-120">MAPI_MODIFY</span></span> 
  
> <span data-ttu-id="914ba-121">请求读/写权限。</span><span class="sxs-lookup"><span data-stu-id="914ba-121">Requests read/write permission.</span></span> <span data-ttu-id="914ba-122">默认情况下，使用只读权限打开配置文件节，客户端不应在已授予读/写权限的假设下工作。</span><span class="sxs-lookup"><span data-stu-id="914ba-122">By default, profile sections are opened with read-only permission, and clients should not work on the assumption that read/write permission has been granted.</span></span> 
    
 <span data-ttu-id="914ba-123">_lppProfSect_</span><span class="sxs-lookup"><span data-stu-id="914ba-123">_lppProfSect_</span></span>
  
> <span data-ttu-id="914ba-124">[out]指向指向配置文件节的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="914ba-124">[out] A pointer to a pointer to the profile section.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="914ba-125">返回值</span><span class="sxs-lookup"><span data-stu-id="914ba-125">Return value</span></span>

<span data-ttu-id="914ba-126">S_OK</span><span class="sxs-lookup"><span data-stu-id="914ba-126">S_OK</span></span> 
  
> <span data-ttu-id="914ba-127">已成功打开配置文件部分。</span><span class="sxs-lookup"><span data-stu-id="914ba-127">The profile section was successfully opened.</span></span>
    
<span data-ttu-id="914ba-128">MAPI_E_NO_ACCESS</span><span class="sxs-lookup"><span data-stu-id="914ba-128">MAPI_E_NO_ACCESS</span></span> 
  
> <span data-ttu-id="914ba-129">尝试访问呼叫者权限不足的配置文件部分。</span><span class="sxs-lookup"><span data-stu-id="914ba-129">An attempt was made to access a profile section for which the caller has insufficient permissions.</span></span>
    
<span data-ttu-id="914ba-130">MAPI_E_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="914ba-130">MAPI_E_NOT_FOUND</span></span> 
  
> <span data-ttu-id="914ba-131">请求的配置文件部分不存在。</span><span class="sxs-lookup"><span data-stu-id="914ba-131">The requested profile section does not exist.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="914ba-132">备注</span><span class="sxs-lookup"><span data-stu-id="914ba-132">Remarks</span></span>

<span data-ttu-id="914ba-133">**IMAPISession：：OpenProfileSection** 方法打开支持 **IProfSect** 接口的配置文件节或对象。</span><span class="sxs-lookup"><span data-stu-id="914ba-133">The **IMAPISession::OpenProfileSection** method opens a profile section or object that supports the **IProfSect** interface.</span></span> <span data-ttu-id="914ba-134">配置文件部分用于从会话配置文件读取信息和将信息写入会话配置文件。</span><span class="sxs-lookup"><span data-stu-id="914ba-134">Profile sections are used for reading information from and writing information to the session profile.</span></span> 
  
<span data-ttu-id="914ba-135">除非在 _ulFlags_ 参数中指定特定参数，否则不能使用 **OpenProfileSection** 打开单个服务提供商MAPI_FORCE_ACCESS配置文件节。</span><span class="sxs-lookup"><span data-stu-id="914ba-135">You cannot use **OpenProfileSection** to open profile sections that individual service providers own unless you specify MAPI_FORCE_ACCESS in the  _ulFlags_ parameter.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="914ba-136">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="914ba-136">Notes to callers</span></span>

<span data-ttu-id="914ba-137">多个客户端可以使用只读权限打开配置文件节，但只有一个客户端可以使用读/写权限打开配置文件节。</span><span class="sxs-lookup"><span data-stu-id="914ba-137">Multiple clients can open a profile section with read-only permission, but only one client can open a profile section with read/write permission.</span></span> <span data-ttu-id="914ba-138">如果另一个客户端打开了一个配置文件节，而您尝试通过调用设置了 MAPI_MODIFY 标志的 **OpenProfileSection** 来打开该节，则调用将失败，并返回 MAPI_E_NO_ACCESS。</span><span class="sxs-lookup"><span data-stu-id="914ba-138">If another client has a profile section open that you attempt to open by calling **OpenProfileSection** with the MAPI_MODIFY flag set, the call will fail, returning MAPI_E_NO_ACCESS.</span></span> 
  
<span data-ttu-id="914ba-139">如果打开部分进行写入，则只读打开操作将失败。</span><span class="sxs-lookup"><span data-stu-id="914ba-139">A read-only open operation fails if the section is open for writing.</span></span> 
  
<span data-ttu-id="914ba-140">您可以通过调用具有 MAPI_MODIFY 标志和 _lpUID_ 参数中不存在 **的 MAPIUID** 结构的 **OpenProfileSection** 来创建配置文件节。</span><span class="sxs-lookup"><span data-stu-id="914ba-140">You can create a profile section by calling **OpenProfileSection** with the MAPI_MODIFY flag and a nonexistent **MAPIUID** structure in the  _lpUID_ parameter.</span></span> <span data-ttu-id="914ba-141">请确保指定MAPI_MODIFY。</span><span class="sxs-lookup"><span data-stu-id="914ba-141">Be sure that you specify MAPI_MODIFY.</span></span> <span data-ttu-id="914ba-142">如果将  _lpUID_ 设置为指向不存在的 **MAPIUID，** 而将 **OpenProfileSection** 设置为使用只读的默认访问模式，则调用将失败，MAPI_E_NOT_FOUND。</span><span class="sxs-lookup"><span data-stu-id="914ba-142">If you set  _lpUID_ to point to a nonexistent **MAPIUID** and **OpenProfileSection** is set to use the default access mode of read-only, the call will fail with MAPI_E_NOT_FOUND.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="914ba-143">另请参阅</span><span class="sxs-lookup"><span data-stu-id="914ba-143">See also</span></span>



[<span data-ttu-id="914ba-144">IMAPIProp : IUnknown</span><span class="sxs-lookup"><span data-stu-id="914ba-144">IMAPIProp : IUnknown</span></span>](imapipropiunknown.md)
  
[<span data-ttu-id="914ba-145">IProfSect : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="914ba-145">IProfSect : IMAPIProp</span></span>](iprofsectimapiprop.md)
  
[<span data-ttu-id="914ba-146">MAPIUID</span><span class="sxs-lookup"><span data-stu-id="914ba-146">MAPIUID</span></span>](mapiuid.md)
  
[<span data-ttu-id="914ba-147">IMAPISession : IUnknown</span><span class="sxs-lookup"><span data-stu-id="914ba-147">IMAPISession : IUnknown</span></span>](imapisessioniunknown.md)

