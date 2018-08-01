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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: e5f329ef0d3483683d5c94ed38c6631d86e77b93
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775575"
---
# <a name="imapisessionopenprofilesection"></a><span data-ttu-id="5940f-103">IMAPISession::OpenProfileSection</span><span class="sxs-lookup"><span data-stu-id="5940f-103">IMAPISession::OpenProfileSection</span></span>

  
  
<span data-ttu-id="5940f-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="5940f-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="5940f-105">打开当前配置文件的节并返回进一步访问[IProfSect](iprofsectimapiprop.md)指针。</span><span class="sxs-lookup"><span data-stu-id="5940f-105">Opens a section of the current profile and returns an [IProfSect](iprofsectimapiprop.md) pointer for further access.</span></span> 
  
```cpp
HRESULT OpenProfileSection(
  LPMAPIUID lpUID,
  LPCIID lpInterface,
  ULONG ulFlags,
  LPPROFSECT FAR * lppProfSect
);
```

## <a name="parameters"></a><span data-ttu-id="5940f-106">参数</span><span class="sxs-lookup"><span data-stu-id="5940f-106">Parameters</span></span>

 <span data-ttu-id="5940f-107">_lpUID_</span><span class="sxs-lookup"><span data-stu-id="5940f-107">_lpUID_</span></span>
  
> <span data-ttu-id="5940f-108">[in]指向标识配置文件部分的[MAPIUID](mapiuid.md)结构的指针。</span><span class="sxs-lookup"><span data-stu-id="5940f-108">[in] A pointer to the [MAPIUID](mapiuid.md) structure that identifies the profile section.</span></span> 
    
 <span data-ttu-id="5940f-109">_lpInterface_</span><span class="sxs-lookup"><span data-stu-id="5940f-109">_lpInterface_</span></span>
  
> <span data-ttu-id="5940f-110">[in]指向接口标识 (IID) 值，该值代表要用于访问配置文件部分的接口的指针。</span><span class="sxs-lookup"><span data-stu-id="5940f-110">[in] A pointer to the interface identifier (IID) that represents the interface to be used to access the profile section.</span></span> <span data-ttu-id="5940f-111">传递 NULL 会导致_lppProfSect_参数，以返回到配置文件部分的标准接口， **IProfSect**的指针。</span><span class="sxs-lookup"><span data-stu-id="5940f-111">Passing NULL causes the  _lppProfSect_ parameter to return a pointer to the profile section's standard interface, **IProfSect**.</span></span>
    
 <span data-ttu-id="5940f-112">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="5940f-112">_ulFlags_</span></span>
  
> <span data-ttu-id="5940f-113">[in]Flags 控制访问到配置文件部分的位掩码。</span><span class="sxs-lookup"><span data-stu-id="5940f-113">[in] A bitmask of flags that controls access to the profile section.</span></span> <span data-ttu-id="5940f-114">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="5940f-114">The following flags can be set:</span></span>
    
<span data-ttu-id="5940f-115">MAPI_DEFERRED_ERRORS</span><span class="sxs-lookup"><span data-stu-id="5940f-115">MAPI_DEFERRED_ERRORS</span></span> 
  
> <span data-ttu-id="5940f-116">允许**OpenProfileSection**成功返回可能之前配置文件节是完全可调用客户端。</span><span class="sxs-lookup"><span data-stu-id="5940f-116">Allows **OpenProfileSection** to return successfully, possibly before the profile section is fully available to the calling client.</span></span> <span data-ttu-id="5940f-117">如果配置文件部分不可用，请进行后续呼叫到它会导致错误。</span><span class="sxs-lookup"><span data-stu-id="5940f-117">If the profile section is not available, making a subsequent call to it can cause an error.</span></span> 
    
<span data-ttu-id="5940f-118">MAPI_FORCE_ACCESS</span><span class="sxs-lookup"><span data-stu-id="5940f-118">MAPI_FORCE_ACCESS</span></span>
  
> <span data-ttu-id="5940f-119">允许访问不属于提供程序的配置文件内容。</span><span class="sxs-lookup"><span data-stu-id="5940f-119">Allows access to a profile section that does not belong to the provider.</span></span>
    
<span data-ttu-id="5940f-120">MAPI_MODIFY</span><span class="sxs-lookup"><span data-stu-id="5940f-120">MAPI_MODIFY</span></span> 
  
> <span data-ttu-id="5940f-121">请求读/写权限。</span><span class="sxs-lookup"><span data-stu-id="5940f-121">Requests read/write permission.</span></span> <span data-ttu-id="5940f-122">默认情况下配置文件部分打开具有只读权限和客户端不应从事的读/写权限授予假设。</span><span class="sxs-lookup"><span data-stu-id="5940f-122">By default, profile sections are opened with read-only permission, and clients should not work on the assumption that read/write permission has been granted.</span></span> 
    
 <span data-ttu-id="5940f-123">_lppProfSect_</span><span class="sxs-lookup"><span data-stu-id="5940f-123">_lppProfSect_</span></span>
  
> <span data-ttu-id="5940f-124">[输出]指向配置文件部分的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="5940f-124">[out] A pointer to a pointer to the profile section.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="5940f-125">返回值</span><span class="sxs-lookup"><span data-stu-id="5940f-125">Return value</span></span>

<span data-ttu-id="5940f-126">S_OK</span><span class="sxs-lookup"><span data-stu-id="5940f-126">S_OK</span></span> 
  
> <span data-ttu-id="5940f-127">已成功打开配置文件部分。</span><span class="sxs-lookup"><span data-stu-id="5940f-127">The profile section was successfully opened.</span></span>
    
<span data-ttu-id="5940f-128">MAPI_E_NO_ACCESS</span><span class="sxs-lookup"><span data-stu-id="5940f-128">MAPI_E_NO_ACCESS</span></span> 
  
> <span data-ttu-id="5940f-129">尝试访问呼叫者有权限不足，无法配置文件一节。</span><span class="sxs-lookup"><span data-stu-id="5940f-129">An attempt was made to access a profile section for which the caller has insufficient permissions.</span></span>
    
<span data-ttu-id="5940f-130">MAPI_E_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="5940f-130">MAPI_E_NOT_FOUND</span></span> 
  
> <span data-ttu-id="5940f-131">请求的配置文件节不存在。</span><span class="sxs-lookup"><span data-stu-id="5940f-131">The requested profile section does not exist.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="5940f-132">说明</span><span class="sxs-lookup"><span data-stu-id="5940f-132">Remarks</span></span>

<span data-ttu-id="5940f-133">**IMAPISession::OpenProfileSection**方法打开一个配置文件节或支持**IProfSect**接口的对象。</span><span class="sxs-lookup"><span data-stu-id="5940f-133">The **IMAPISession::OpenProfileSection** method opens a profile section or object that supports the **IProfSect** interface.</span></span> <span data-ttu-id="5940f-134">配置文件节用于进行读取和写入会话配置文件信息。</span><span class="sxs-lookup"><span data-stu-id="5940f-134">Profile sections are used for reading information from and writing information to the session profile.</span></span> 
  
<span data-ttu-id="5940f-135">不能使用**OpenProfileSection**打开配置文件部分自己的单个服务提供程序，除非_ulFlags_参数中指定 MAPI_FORCE_ACCESS。</span><span class="sxs-lookup"><span data-stu-id="5940f-135">You cannot use **OpenProfileSection** to open profile sections that individual service providers own unless you specify MAPI_FORCE_ACCESS in the  _ulFlags_ parameter.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="5940f-136">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="5940f-136">Notes to callers</span></span>

<span data-ttu-id="5940f-137">多个客户端可以具有只读权限，打开配置文件一节，但只有一个客户端可以具有读/写权限打开配置文件一节。</span><span class="sxs-lookup"><span data-stu-id="5940f-137">Multiple clients can open a profile section with read-only permission, but only one client can open a profile section with read/write permission.</span></span> <span data-ttu-id="5940f-138">如果另一个客户端打开您尝试通过调用设置了 MAPI_MODIFY 标志**OpenProfileSection**打开配置文件一节，则调用将失败，返回 MAPI_E_NO_ACCESS。</span><span class="sxs-lookup"><span data-stu-id="5940f-138">If another client has a profile section open that you attempt to open by calling **OpenProfileSection** with the MAPI_MODIFY flag set, the call will fail, returning MAPI_E_NO_ACCESS.</span></span> 
  
<span data-ttu-id="5940f-139">只读状态打开操作失败，如果该节为打开以进行写入。</span><span class="sxs-lookup"><span data-stu-id="5940f-139">A read-only open operation fails if the section is open for writing.</span></span> 
  
<span data-ttu-id="5940f-140">您可以通过调用不带 MAPI_MODIFY 标志和_lpUID_参数中的不存在**MAPIUID**结构**OpenProfileSection**创建配置文件一节。</span><span class="sxs-lookup"><span data-stu-id="5940f-140">You can create a profile section by calling **OpenProfileSection** with the MAPI_MODIFY flag and a nonexistent **MAPIUID** structure in the  _lpUID_ parameter.</span></span> <span data-ttu-id="5940f-141">确保您指定 MAPI_MODIFY。</span><span class="sxs-lookup"><span data-stu-id="5940f-141">Be sure that you specify MAPI_MODIFY.</span></span> <span data-ttu-id="5940f-142">如果设置_lpUID_以指向不存在**MAPIUID** **OpenProfileSection**设置为使用默认访问模式的只读的则调用将失败与 MAPI_E_NOT_FOUND。</span><span class="sxs-lookup"><span data-stu-id="5940f-142">If you set  _lpUID_ to point to a nonexistent **MAPIUID** and **OpenProfileSection** is set to use the default access mode of read-only, the call will fail with MAPI_E_NOT_FOUND.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="5940f-143">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5940f-143">See also</span></span>



[<span data-ttu-id="5940f-144">IMAPIProp : IUnknown</span><span class="sxs-lookup"><span data-stu-id="5940f-144">IMAPIProp : IUnknown</span></span>](imapipropiunknown.md)
  
[<span data-ttu-id="5940f-145">IProfSect : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="5940f-145">IProfSect : IMAPIProp</span></span>](iprofsectimapiprop.md)
  
[<span data-ttu-id="5940f-146">MAPIUID</span><span class="sxs-lookup"><span data-stu-id="5940f-146">MAPIUID</span></span>](mapiuid.md)
  
[<span data-ttu-id="5940f-147">IMAPISession : IUnknown</span><span class="sxs-lookup"><span data-stu-id="5940f-147">IMAPISession : IUnknown</span></span>](imapisessioniunknown.md)

