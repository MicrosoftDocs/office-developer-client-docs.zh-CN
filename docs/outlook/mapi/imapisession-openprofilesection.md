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
# <a name="imapisessionopenprofilesection"></a><span data-ttu-id="9d868-103">IMAPISession::OpenProfileSection</span><span class="sxs-lookup"><span data-stu-id="9d868-103">IMAPISession::OpenProfileSection</span></span>

  
  
<span data-ttu-id="9d868-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="9d868-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="9d868-105">打开当前配置文件的一个部分, 并返回一个[IProfSect](iprofsectimapiprop.md)指针以供进一步访问。</span><span class="sxs-lookup"><span data-stu-id="9d868-105">Opens a section of the current profile and returns an [IProfSect](iprofsectimapiprop.md) pointer for further access.</span></span> 
  
```cpp
HRESULT OpenProfileSection(
  LPMAPIUID lpUID,
  LPCIID lpInterface,
  ULONG ulFlags,
  LPPROFSECT FAR * lppProfSect
);
```

## <a name="parameters"></a><span data-ttu-id="9d868-106">参数</span><span class="sxs-lookup"><span data-stu-id="9d868-106">Parameters</span></span>

 <span data-ttu-id="9d868-107">_lpUID_</span><span class="sxs-lookup"><span data-stu-id="9d868-107">_lpUID_</span></span>
  
> <span data-ttu-id="9d868-108">实时指向标识配置文件节的[MAPIUID](mapiuid.md)结构的指针。</span><span class="sxs-lookup"><span data-stu-id="9d868-108">[in] A pointer to the [MAPIUID](mapiuid.md) structure that identifies the profile section.</span></span> 
    
 <span data-ttu-id="9d868-109">_lpInterface_</span><span class="sxs-lookup"><span data-stu-id="9d868-109">_lpInterface_</span></span>
  
> <span data-ttu-id="9d868-110">实时指向接口标识符 (IID) 的指针, 该接口标识符表示要用于访问配置文件部分的接口。</span><span class="sxs-lookup"><span data-stu-id="9d868-110">[in] A pointer to the interface identifier (IID) that represents the interface to be used to access the profile section.</span></span> <span data-ttu-id="9d868-111">传递 NULL 会导致_lppProfSect_参数返回指向配置文件节的标准接口**IProfSect**的指针。</span><span class="sxs-lookup"><span data-stu-id="9d868-111">Passing NULL causes the  _lppProfSect_ parameter to return a pointer to the profile section's standard interface, **IProfSect**.</span></span>
    
 <span data-ttu-id="9d868-112">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="9d868-112">_ulFlags_</span></span>
  
> <span data-ttu-id="9d868-113">实时用于控制对配置文件部分的访问的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="9d868-113">[in] A bitmask of flags that controls access to the profile section.</span></span> <span data-ttu-id="9d868-114">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="9d868-114">The following flags can be set:</span></span>
    
<span data-ttu-id="9d868-115">MAPI_DEFERRED_ERRORS</span><span class="sxs-lookup"><span data-stu-id="9d868-115">MAPI_DEFERRED_ERRORS</span></span> 
  
> <span data-ttu-id="9d868-116">允许**OpenProfileSection**成功返回, 这可能在配置文件部分完全可用于调用客户端之前返回。</span><span class="sxs-lookup"><span data-stu-id="9d868-116">Allows **OpenProfileSection** to return successfully, possibly before the profile section is fully available to the calling client.</span></span> <span data-ttu-id="9d868-117">如果 "配置文件" 部分不可用, 则对其进行后续调用可能会导致出错。</span><span class="sxs-lookup"><span data-stu-id="9d868-117">If the profile section is not available, making a subsequent call to it can cause an error.</span></span> 
    
<span data-ttu-id="9d868-118">MAPI_FORCE_ACCESS</span><span class="sxs-lookup"><span data-stu-id="9d868-118">MAPI_FORCE_ACCESS</span></span>
  
> <span data-ttu-id="9d868-119">允许访问不属于提供程序的配置文件部分。</span><span class="sxs-lookup"><span data-stu-id="9d868-119">Allows access to a profile section that does not belong to the provider.</span></span>
    
<span data-ttu-id="9d868-120">MAPI_MODIFY</span><span class="sxs-lookup"><span data-stu-id="9d868-120">MAPI_MODIFY</span></span> 
  
> <span data-ttu-id="9d868-121">请求读取/写入权限。</span><span class="sxs-lookup"><span data-stu-id="9d868-121">Requests read/write permission.</span></span> <span data-ttu-id="9d868-122">默认情况下, 配置文件分区以只读权限打开, 并且客户端不应在假定已授予读/写权限时才起作用。</span><span class="sxs-lookup"><span data-stu-id="9d868-122">By default, profile sections are opened with read-only permission, and clients should not work on the assumption that read/write permission has been granted.</span></span> 
    
 <span data-ttu-id="9d868-123">_lppProfSect_</span><span class="sxs-lookup"><span data-stu-id="9d868-123">_lppProfSect_</span></span>
  
> <span data-ttu-id="9d868-124">排除指向指向配置文件部分的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="9d868-124">[out] A pointer to a pointer to the profile section.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="9d868-125">返回值</span><span class="sxs-lookup"><span data-stu-id="9d868-125">Return value</span></span>

<span data-ttu-id="9d868-126">S_OK</span><span class="sxs-lookup"><span data-stu-id="9d868-126">S_OK</span></span> 
  
> <span data-ttu-id="9d868-127">已成功打开 "配置文件" 部分。</span><span class="sxs-lookup"><span data-stu-id="9d868-127">The profile section was successfully opened.</span></span>
    
<span data-ttu-id="9d868-128">MAPI_E_NO_ACCESS</span><span class="sxs-lookup"><span data-stu-id="9d868-128">MAPI_E_NO_ACCESS</span></span> 
  
> <span data-ttu-id="9d868-129">试图访问呼叫者没有足够权限的配置文件部分。</span><span class="sxs-lookup"><span data-stu-id="9d868-129">An attempt was made to access a profile section for which the caller has insufficient permissions.</span></span>
    
<span data-ttu-id="9d868-130">MAPI_E_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="9d868-130">MAPI_E_NOT_FOUND</span></span> 
  
> <span data-ttu-id="9d868-131">请求的配置文件部分不存在。</span><span class="sxs-lookup"><span data-stu-id="9d868-131">The requested profile section does not exist.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="9d868-132">说明</span><span class="sxs-lookup"><span data-stu-id="9d868-132">Remarks</span></span>

<span data-ttu-id="9d868-133">**IMAPISession:: OpenProfileSection**方法打开一个配置文件节或支持**IProfSect**接口的对象。</span><span class="sxs-lookup"><span data-stu-id="9d868-133">The **IMAPISession::OpenProfileSection** method opens a profile section or object that supports the **IProfSect** interface.</span></span> <span data-ttu-id="9d868-134">配置文件节用于读取信息以及将信息写入会话配置文件。</span><span class="sxs-lookup"><span data-stu-id="9d868-134">Profile sections are used for reading information from and writing information to the session profile.</span></span> 
  
<span data-ttu-id="9d868-135">除非在_ulFlags_参数中指定 MAPI_FORCE_ACCESS, 否则, 不能使用**OpenProfileSection**打开单个服务提供程序所拥有的配置文件部分。</span><span class="sxs-lookup"><span data-stu-id="9d868-135">You cannot use **OpenProfileSection** to open profile sections that individual service providers own unless you specify MAPI_FORCE_ACCESS in the  _ulFlags_ parameter.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="9d868-136">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="9d868-136">Notes to callers</span></span>

<span data-ttu-id="9d868-137">多个客户端可以打开具有只读权限的配置文件部分, 但只有一台客户端可以打开具有读/写权限的配置文件节。</span><span class="sxs-lookup"><span data-stu-id="9d868-137">Multiple clients can open a profile section with read-only permission, but only one client can open a profile section with read/write permission.</span></span> <span data-ttu-id="9d868-138">如果另一个客户端有一个配置文件节打开, 您试图通过调用**OpenProfileSection**并设置 MAPI_MODIFY 标志来打开, 则该调用将失败, 返回 MAPI_E_NO_ACCESS。</span><span class="sxs-lookup"><span data-stu-id="9d868-138">If another client has a profile section open that you attempt to open by calling **OpenProfileSection** with the MAPI_MODIFY flag set, the call will fail, returning MAPI_E_NO_ACCESS.</span></span> 
  
<span data-ttu-id="9d868-139">如果为写入打开了该节, 则只读打开操作将失败。</span><span class="sxs-lookup"><span data-stu-id="9d868-139">A read-only open operation fails if the section is open for writing.</span></span> 
  
<span data-ttu-id="9d868-140">您可以通过在_lpUID_参数中调用带有 MAPI_MODIFY 标志的**OpenProfileSection**和不存在的**MAPIUID**结构来创建配置文件节。</span><span class="sxs-lookup"><span data-stu-id="9d868-140">You can create a profile section by calling **OpenProfileSection** with the MAPI_MODIFY flag and a nonexistent **MAPIUID** structure in the  _lpUID_ parameter.</span></span> <span data-ttu-id="9d868-141">确保指定 MAPI_MODIFY。</span><span class="sxs-lookup"><span data-stu-id="9d868-141">Be sure that you specify MAPI_MODIFY.</span></span> <span data-ttu-id="9d868-142">如果将_lpUID_设置为指向不存在的**MAPIUID** , 并且将**OpenProfileSection**设置为使用只读的默认访问模式, 则调用将会因 MAPI_E_NOT_FOUND 而失败。</span><span class="sxs-lookup"><span data-stu-id="9d868-142">If you set  _lpUID_ to point to a nonexistent **MAPIUID** and **OpenProfileSection** is set to use the default access mode of read-only, the call will fail with MAPI_E_NOT_FOUND.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="9d868-143">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9d868-143">See also</span></span>



[<span data-ttu-id="9d868-144">IMAPIProp : IUnknown</span><span class="sxs-lookup"><span data-stu-id="9d868-144">IMAPIProp : IUnknown</span></span>](imapipropiunknown.md)
  
[<span data-ttu-id="9d868-145">IProfSect : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="9d868-145">IProfSect : IMAPIProp</span></span>](iprofsectimapiprop.md)
  
[<span data-ttu-id="9d868-146">MAPIUID</span><span class="sxs-lookup"><span data-stu-id="9d868-146">MAPIUID</span></span>](mapiuid.md)
  
[<span data-ttu-id="9d868-147">IMAPISession : IUnknown</span><span class="sxs-lookup"><span data-stu-id="9d868-147">IMAPISession : IUnknown</span></span>](imapisessioniunknown.md)

