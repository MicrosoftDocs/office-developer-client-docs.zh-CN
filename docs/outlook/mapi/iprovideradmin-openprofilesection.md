---
title: IProviderAdminOpenProfileSection
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IProviderAdmin.OpenProfileSection
api_type:
- COM
ms.assetid: b73cf770-8817-4a23-bd14-7b76fedef214
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: b3ac1b2cf8335c5e0953fdcf61b2b5d466fbb724
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33405658"
---
# <a name="iprovideradminopenprofilesection"></a><span data-ttu-id="d64e0-103">IProviderAdmin::OpenProfileSection</span><span class="sxs-lookup"><span data-stu-id="d64e0-103">IProviderAdmin::OpenProfileSection</span></span>

  
  
<span data-ttu-id="d64e0-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="d64e0-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="d64e0-105">从当前配置文件中打开配置文件部分，并返回 [IProfSect](iprofsectimapiprop.md) 指针以进一步访问。</span><span class="sxs-lookup"><span data-stu-id="d64e0-105">Opens a profile section from the current profile and returns an [IProfSect](iprofsectimapiprop.md) pointer for further access.</span></span> 
  
```cpp
HRESULT OpenProfileSection(
  LPMAPIUID lpUID,
  LPCIID lpInterface,
  ULONG ulFlags,
  LPPROFSECT FAR * lppProfSect
);
```

## <a name="parameters"></a><span data-ttu-id="d64e0-106">参数</span><span class="sxs-lookup"><span data-stu-id="d64e0-106">Parameters</span></span>

 <span data-ttu-id="d64e0-107">_lpUID_</span><span class="sxs-lookup"><span data-stu-id="d64e0-107">_lpUID_</span></span>
  
> <span data-ttu-id="d64e0-108">[in]指向 [MAPIUID](mapiuid.md) 结构的指针，其中包含要打开的配置文件节的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="d64e0-108">[in] A pointer to the [MAPIUID](mapiuid.md) structure that contains the unique identifier for the profile section to be opened.</span></span> <span data-ttu-id="d64e0-109">客户端不得为  _lpUID_ 参数传递 NULL。</span><span class="sxs-lookup"><span data-stu-id="d64e0-109">Clients must not pass NULL for the  _lpUID_ parameter.</span></span> <span data-ttu-id="d64e0-110">服务提供商可以传递 NULL，以在从邮件服务入口点函数调用时检索 **MAPIUID。**</span><span class="sxs-lookup"><span data-stu-id="d64e0-110">Service providers can pass NULL to retrieve the **MAPIUID** when they call from their message service entry point functions.</span></span> 
    
 <span data-ttu-id="d64e0-111">_lpInterface_</span><span class="sxs-lookup"><span data-stu-id="d64e0-111">_lpInterface_</span></span>
  
> <span data-ttu-id="d64e0-112">[in]指向接口标识符的 (IID) 表示用于访问配置文件节的接口。</span><span class="sxs-lookup"><span data-stu-id="d64e0-112">[in] A pointer to the interface identifier (IID) that represents the interface to be used to access the profile section.</span></span> <span data-ttu-id="d64e0-113">传递 NULL 会导致返回的 **IProfSect** (配置文件) 接口。</span><span class="sxs-lookup"><span data-stu-id="d64e0-113">Passing NULL results in the profile section's standard interface (**IProfSect**) being returned.</span></span> 
    
 <span data-ttu-id="d64e0-114">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="d64e0-114">_ulFlags_</span></span>
  
> <span data-ttu-id="d64e0-115">[in]控制配置文件节打开方式的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="d64e0-115">[in] A bitmask of flags that controls how the profile section is opened.</span></span> <span data-ttu-id="d64e0-116">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="d64e0-116">The following flags can be set:</span></span>
    
<span data-ttu-id="d64e0-117">MAPI_DEFERRED_ERRORS</span><span class="sxs-lookup"><span data-stu-id="d64e0-117">MAPI_DEFERRED_ERRORS</span></span> 
  
> <span data-ttu-id="d64e0-118">启用 **OpenProfileSection** 以成功返回，可能在配置文件部分对调用方完全可用之前。</span><span class="sxs-lookup"><span data-stu-id="d64e0-118">Enables **OpenProfileSection** to return successfully, possibly before the profile section is fully available to the caller.</span></span> <span data-ttu-id="d64e0-119">如果配置文件部分不可用，则后续调用它可能会引发错误。</span><span class="sxs-lookup"><span data-stu-id="d64e0-119">If the profile section is not available, making a subsequent call to it can raise an error.</span></span> 
    
<span data-ttu-id="d64e0-120">MAPI_MODIFY</span><span class="sxs-lookup"><span data-stu-id="d64e0-120">MAPI_MODIFY</span></span> 
  
> <span data-ttu-id="d64e0-121">请求读/写权限。</span><span class="sxs-lookup"><span data-stu-id="d64e0-121">Requests read/write permission.</span></span> <span data-ttu-id="d64e0-122">默认情况下，使用只读权限打开对象，调用方不应假定已授予读/写权限。</span><span class="sxs-lookup"><span data-stu-id="d64e0-122">By default, objects are opened with read-only permission, and callers should not work on the assumption that read/write permission has been granted.</span></span> <span data-ttu-id="d64e0-123">不允许客户端对配置文件的提供程序分区具有读/写权限。</span><span class="sxs-lookup"><span data-stu-id="d64e0-123">Clients are not allowed read/write permission to provider sections of the profile.</span></span>
    
<span data-ttu-id="d64e0-124">MAPI_FORCE_ACCESS</span><span class="sxs-lookup"><span data-stu-id="d64e0-124">MAPI_FORCE_ACCESS</span></span>
  
> <span data-ttu-id="d64e0-125">允许访问所有配置文件节，甚至是单个服务提供商拥有的内容。</span><span class="sxs-lookup"><span data-stu-id="d64e0-125">Allows access to all profile sections, even those owned by individual service providers.</span></span>
    
 <span data-ttu-id="d64e0-126">_lppProfSect_</span><span class="sxs-lookup"><span data-stu-id="d64e0-126">_lppProfSect_</span></span>
  
> <span data-ttu-id="d64e0-127">[out]指向指向配置文件节的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="d64e0-127">[out] A pointer to a pointer to the profile section.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="d64e0-128">返回值</span><span class="sxs-lookup"><span data-stu-id="d64e0-128">Return value</span></span>

<span data-ttu-id="d64e0-129">S_OK</span><span class="sxs-lookup"><span data-stu-id="d64e0-129">S_OK</span></span> 
  
> <span data-ttu-id="d64e0-130">已成功打开配置文件部分。</span><span class="sxs-lookup"><span data-stu-id="d64e0-130">The profile section was successfully opened.</span></span>
    
<span data-ttu-id="d64e0-131">MAPI_E_NO_ACCESS</span><span class="sxs-lookup"><span data-stu-id="d64e0-131">MAPI_E_NO_ACCESS</span></span> 
  
> <span data-ttu-id="d64e0-132">试图修改只读配置文件节或访问用户权限不足的对象。</span><span class="sxs-lookup"><span data-stu-id="d64e0-132">An attempt was made to modify a read-only profile section or to access an object for which the user has insufficient permissions.</span></span>
    
<span data-ttu-id="d64e0-133">MAPI_E_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="d64e0-133">MAPI_E_NOT_FOUND</span></span> 
  
> <span data-ttu-id="d64e0-134">请求的配置文件部分不存在。</span><span class="sxs-lookup"><span data-stu-id="d64e0-134">The requested profile section does not exist.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="d64e0-135">备注</span><span class="sxs-lookup"><span data-stu-id="d64e0-135">Remarks</span></span>

<span data-ttu-id="d64e0-136">**IProviderAdmin：：OpenProfileSection** 方法打开配置文件部分，使呼叫者能够读取活动配置文件的信息，并可能向活动配置文件中写入信息。</span><span class="sxs-lookup"><span data-stu-id="d64e0-136">The **IProviderAdmin::OpenProfileSection** method opens a profile section, enabling the caller to read information from and possibly write information to the active profile.</span></span> 
  
<span data-ttu-id="d64e0-137">客户端无法使用 **OpenProfileSection** 方法打开属于提供程序的配置文件节。</span><span class="sxs-lookup"><span data-stu-id="d64e0-137">Clients cannot open profile sections that belong to providers by using the **OpenProfileSection** method.</span></span> 
  
<span data-ttu-id="d64e0-138">多个客户端或服务提供商可以同时打开具有只读权限的配置文件部分。</span><span class="sxs-lookup"><span data-stu-id="d64e0-138">Multiple clients or service providers can simultaneously open a profile section with read-only permission.</span></span> <span data-ttu-id="d64e0-139">但是，当使用读/写权限打开配置文件节时，无论访问类型如何，都不得进行其他调用来打开该节。</span><span class="sxs-lookup"><span data-stu-id="d64e0-139">However, when a profile section is open with read/write permission, no other calls can be made to open the section, regardless of the type of access.</span></span> <span data-ttu-id="d64e0-140">如果使用只读权限打开配置文件节，则后续调用请求读/写权限将失败，MAPI_E_NO_ACCESS。</span><span class="sxs-lookup"><span data-stu-id="d64e0-140">If a profile section is open with read-only permission, a subsequent call to request read/write permission will fail with MAPI_E_NO_ACCESS.</span></span> <span data-ttu-id="d64e0-141">同样，如果分区以读/写权限打开，则后续调用请求只读权限也将失败。</span><span class="sxs-lookup"><span data-stu-id="d64e0-141">Likewise, if a section is open with read/write permission, a subsequent call to request read-only permission will also fail.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="d64e0-142">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="d64e0-142">Notes to callers</span></span>

<span data-ttu-id="d64e0-143">如果请求 **OpenProfileSection** 在 _ulFlags_ 中传递 MAPI_MODIFY，在 _lpUID_ 中传递未知 **MAPIUID，** 打开不存在的配置文件节，将创建配置文件节。</span><span class="sxs-lookup"><span data-stu-id="d64e0-143">If you request that **OpenProfileSection** open a nonexistent profile section by passing MAPI_MODIFY in  _ulFlags_ and an unknown **MAPIUID** in  _lpUID_, the profile section will be created.</span></span> 
  
<span data-ttu-id="d64e0-144">如果请求 **OpenProfileSection** 打开具有只读权限的不存在的节，它将返回MAPI_E_NOT_FOUND。</span><span class="sxs-lookup"><span data-stu-id="d64e0-144">If you request that **OpenProfileSection** open a nonexistent section with read-only permission, it returns MAPI_E_NOT_FOUND.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="d64e0-145">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="d64e0-145">MFCMAPI reference</span></span>

<span data-ttu-id="d64e0-146">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="d64e0-146">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="d64e0-147">**文件**</span><span class="sxs-lookup"><span data-stu-id="d64e0-147">**File**</span></span>|<span data-ttu-id="d64e0-148">**函数**</span><span class="sxs-lookup"><span data-stu-id="d64e0-148">**Function**</span></span>|<span data-ttu-id="d64e0-149">**备注**</span><span class="sxs-lookup"><span data-stu-id="d64e0-149">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d64e0-150">MAPIProfileFunctions.cpp</span><span class="sxs-lookup"><span data-stu-id="d64e0-150">MAPIProfileFunctions.cpp</span></span>  <br/> |<span data-ttu-id="d64e0-151">OpenProfileSection</span><span class="sxs-lookup"><span data-stu-id="d64e0-151">OpenProfileSection</span></span>  <br/> |<span data-ttu-id="d64e0-152">MFCMAPI 使用 **IProviderAdmin：：OpenProfileSection** 方法从当前配置文件打开配置文件节。</span><span class="sxs-lookup"><span data-stu-id="d64e0-152">MFCMAPI uses the **IProviderAdmin::OpenProfileSection** method to open a profile section from the current profile.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="d64e0-153">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d64e0-153">See also</span></span>



[<span data-ttu-id="d64e0-154">IMAPIProp : IUnknown</span><span class="sxs-lookup"><span data-stu-id="d64e0-154">IMAPIProp : IUnknown</span></span>](imapipropiunknown.md)
  
[<span data-ttu-id="d64e0-155">IProfSect : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="d64e0-155">IProfSect : IMAPIProp</span></span>](iprofsectimapiprop.md)
  
[<span data-ttu-id="d64e0-156">MAPIUID</span><span class="sxs-lookup"><span data-stu-id="d64e0-156">MAPIUID</span></span>](mapiuid.md)
  
[<span data-ttu-id="d64e0-157">IProviderAdmin : IUnknown</span><span class="sxs-lookup"><span data-stu-id="d64e0-157">IProviderAdmin : IUnknown</span></span>](iprovideradminiunknown.md)


[<span data-ttu-id="d64e0-158">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="d64e0-158">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

