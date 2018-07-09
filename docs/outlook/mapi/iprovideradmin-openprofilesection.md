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
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 276a2bd84156e9b396df71f51130e6704ad7c7fb
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776030"
---
# <a name="iprovideradminopenprofilesection"></a><span data-ttu-id="08ed9-103">IProviderAdmin::OpenProfileSection</span><span class="sxs-lookup"><span data-stu-id="08ed9-103">IProviderAdmin::OpenProfileSection</span></span>

  
  
<span data-ttu-id="08ed9-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="08ed9-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="08ed9-105">从当前配置文件中打开配置文件一节并返回进一步访问[IProfSect](iprofsectimapiprop.md)指针。</span><span class="sxs-lookup"><span data-stu-id="08ed9-105">Opens a profile section from the current profile and returns an [IProfSect](iprofsectimapiprop.md) pointer for further access.</span></span> 
  
```cpp
HRESULT OpenProfileSection(
  LPMAPIUID lpUID,
  LPCIID lpInterface,
  ULONG ulFlags,
  LPPROFSECT FAR * lppProfSect
);
```

## <a name="parameters"></a><span data-ttu-id="08ed9-106">参数</span><span class="sxs-lookup"><span data-stu-id="08ed9-106">Parameters</span></span>

 <span data-ttu-id="08ed9-107">_lpUID_</span><span class="sxs-lookup"><span data-stu-id="08ed9-107">_lpUID_</span></span>
  
> <span data-ttu-id="08ed9-108">[in]一个指向[MAPIUID](mapiuid.md)结构，其中包含要打开的配置文件节的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="08ed9-108">[in] A pointer to the [MAPIUID](mapiuid.md) structure that contains the unique identifier for the profile section to be opened.</span></span> <span data-ttu-id="08ed9-109">客户端必须_lpUID_参数传递 NULL。</span><span class="sxs-lookup"><span data-stu-id="08ed9-109">Clients must not pass NULL for the  _lpUID_ parameter.</span></span> <span data-ttu-id="08ed9-110">服务提供商可以传递 NULL 时从其消息服务入口点函数检索**MAPIUID** 。</span><span class="sxs-lookup"><span data-stu-id="08ed9-110">Service providers can pass NULL to retrieve the **MAPIUID** when they call from their message service entry point functions.</span></span> 
    
 <span data-ttu-id="08ed9-111">_lpInterface_</span><span class="sxs-lookup"><span data-stu-id="08ed9-111">_lpInterface_</span></span>
  
> <span data-ttu-id="08ed9-112">[in]指向接口标识 (IID) 值，该值代表要用于访问配置文件部分的接口的指针。</span><span class="sxs-lookup"><span data-stu-id="08ed9-112">[in] A pointer to the interface identifier (IID) that represents the interface to be used to access the profile section.</span></span> <span data-ttu-id="08ed9-113">在配置文件部分的标准界面，(**IProfSect**) 返回结果传递 NULL。</span><span class="sxs-lookup"><span data-stu-id="08ed9-113">Passing NULL results in the profile section's standard interface (**IProfSect**) being returned.</span></span> 
    
 <span data-ttu-id="08ed9-114">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="08ed9-114">_ulFlags_</span></span>
  
> <span data-ttu-id="08ed9-115">[in]位掩码的标志，控制如何打开配置文件部分。</span><span class="sxs-lookup"><span data-stu-id="08ed9-115">[in] A bitmask of flags that controls how the profile section is opened.</span></span> <span data-ttu-id="08ed9-116">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="08ed9-116">The following flags can be set:</span></span>
    
<span data-ttu-id="08ed9-117">MAPI_DEFERRED_ERRORS</span><span class="sxs-lookup"><span data-stu-id="08ed9-117">MAPI_DEFERRED_ERRORS</span></span> 
  
> <span data-ttu-id="08ed9-118">使**OpenProfileSection**返回成功，可能之前在配置文件部分，对呼叫者完全可用。</span><span class="sxs-lookup"><span data-stu-id="08ed9-118">Enables **OpenProfileSection** to return successfully, possibly before the profile section is fully available to the caller.</span></span> <span data-ttu-id="08ed9-119">如果配置文件部分不可用，进行后续呼叫到它会引发错误。</span><span class="sxs-lookup"><span data-stu-id="08ed9-119">If the profile section is not available, making a subsequent call to it can raise an error.</span></span> 
    
<span data-ttu-id="08ed9-120">MAPI_MODIFY</span><span class="sxs-lookup"><span data-stu-id="08ed9-120">MAPI_MODIFY</span></span> 
  
> <span data-ttu-id="08ed9-121">请求读/写权限。</span><span class="sxs-lookup"><span data-stu-id="08ed9-121">Requests read/write permission.</span></span> <span data-ttu-id="08ed9-122">默认情况下，对象打开具有只读权限，并以为，读/写权限授予不起作用呼叫者。</span><span class="sxs-lookup"><span data-stu-id="08ed9-122">By default, objects are opened with read-only permission, and callers should not work on the assumption that read/write permission has been granted.</span></span> <span data-ttu-id="08ed9-123">客户端不允许提供程序的配置文件的分区的读/写权限。</span><span class="sxs-lookup"><span data-stu-id="08ed9-123">Clients are not allowed read/write permission to provider sections of the profile.</span></span>
    
<span data-ttu-id="08ed9-124">MAPI_FORCE_ACCESS</span><span class="sxs-lookup"><span data-stu-id="08ed9-124">MAPI_FORCE_ACCESS</span></span>
  
> <span data-ttu-id="08ed9-125">允许对所有配置文件节，即使他们拥有单独的服务提供程序的访问。</span><span class="sxs-lookup"><span data-stu-id="08ed9-125">Allows access to all profile sections, even those owned by individual service providers.</span></span>
    
 <span data-ttu-id="08ed9-126">_lppProfSect_</span><span class="sxs-lookup"><span data-stu-id="08ed9-126">_lppProfSect_</span></span>
  
> <span data-ttu-id="08ed9-127">[输出]指向配置文件部分的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="08ed9-127">[out] A pointer to a pointer to the profile section.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="08ed9-128">返回值</span><span class="sxs-lookup"><span data-stu-id="08ed9-128">Return value</span></span>

<span data-ttu-id="08ed9-129">S_OK</span><span class="sxs-lookup"><span data-stu-id="08ed9-129">S_OK</span></span> 
  
> <span data-ttu-id="08ed9-130">已成功打开配置文件部分。</span><span class="sxs-lookup"><span data-stu-id="08ed9-130">The profile section was successfully opened.</span></span>
    
<span data-ttu-id="08ed9-131">MAPI_E_NO_ACCESS</span><span class="sxs-lookup"><span data-stu-id="08ed9-131">MAPI_E_NO_ACCESS</span></span> 
  
> <span data-ttu-id="08ed9-132">尝试来修改只读的配置文件节或访问其用户没有足够的权限的对象。</span><span class="sxs-lookup"><span data-stu-id="08ed9-132">An attempt was made to modify a read-only profile section or to access an object for which the user has insufficient permissions.</span></span>
    
<span data-ttu-id="08ed9-133">MAPI_E_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="08ed9-133">MAPI_E_NOT_FOUND</span></span> 
  
> <span data-ttu-id="08ed9-134">请求的配置文件节不存在。</span><span class="sxs-lookup"><span data-stu-id="08ed9-134">The requested profile section does not exist.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="08ed9-135">备注</span><span class="sxs-lookup"><span data-stu-id="08ed9-135">Remarks</span></span>

<span data-ttu-id="08ed9-136">**IProviderAdmin::OpenProfileSection**方法将打开配置文件部分，使呼叫者读取信息和可能在当前配置文件中写入信息。</span><span class="sxs-lookup"><span data-stu-id="08ed9-136">The **IProviderAdmin::OpenProfileSection** method opens a profile section, enabling the caller to read information from and possibly write information to the active profile.</span></span> 
  
<span data-ttu-id="08ed9-137">客户端无法打开使用**OpenProfileSection**方法属于提供程序的配置文件部分。</span><span class="sxs-lookup"><span data-stu-id="08ed9-137">Clients cannot open profile sections that belong to providers by using the **OpenProfileSection** method.</span></span> 
  
<span data-ttu-id="08ed9-138">多个客户端或服务提供商可以同时打开配置文件部分具有只读权限。</span><span class="sxs-lookup"><span data-stu-id="08ed9-138">Multiple clients or service providers can simultaneously open a profile section with read-only permission.</span></span> <span data-ttu-id="08ed9-139">但是，具有读/写权限打开配置文件部分时，可以不进行任何其他呼叫以打开部分，而不考虑的访问类型。</span><span class="sxs-lookup"><span data-stu-id="08ed9-139">However, when a profile section is open with read/write permission, no other calls can be made to open the section, regardless of the type of access.</span></span> <span data-ttu-id="08ed9-140">如果具有只读权限打开配置文件一节，以请求读/写权限的后续调用将失败并 MAPI_E_NO_ACCESS。</span><span class="sxs-lookup"><span data-stu-id="08ed9-140">If a profile section is open with read-only permission, a subsequent call to request read/write permission will fail with MAPI_E_NO_ACCESS.</span></span> <span data-ttu-id="08ed9-141">同样，如果部分具有读/写权限打开，也将失败的后续调用以请求只读权限。</span><span class="sxs-lookup"><span data-stu-id="08ed9-141">Likewise, if a section is open with read/write permission, a subsequent call to request read-only permission will also fail.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="08ed9-142">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="08ed9-142">Notes to callers</span></span>

<span data-ttu-id="08ed9-143">如果您请求的**OpenProfileSection**打开不存在配置文件一节中_ulFlags_传递 MAPI_MODIFY，并将创建未知的**MAPIUID** _lpUID_，配置文件部分中。</span><span class="sxs-lookup"><span data-stu-id="08ed9-143">If you request that **OpenProfileSection** open a nonexistent profile section by passing MAPI_MODIFY in  _ulFlags_ and an unknown **MAPIUID** in  _lpUID_, the profile section will be created.</span></span> 
  
<span data-ttu-id="08ed9-144">如果您请求**OpenProfileSection**具有只读权限打开不存在的节，则将返回 MAPI_E_NOT_FOUND。</span><span class="sxs-lookup"><span data-stu-id="08ed9-144">If you request that **OpenProfileSection** open a nonexistent section with read-only permission, it returns MAPI_E_NOT_FOUND.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="08ed9-145">MFCMAPI 参考</span><span class="sxs-lookup"><span data-stu-id="08ed9-145">MFCMAPI reference</span></span>

<span data-ttu-id="08ed9-146">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="08ed9-146">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="08ed9-147">**文件**</span><span class="sxs-lookup"><span data-stu-id="08ed9-147">**File**</span></span>|<span data-ttu-id="08ed9-148">**函数**</span><span class="sxs-lookup"><span data-stu-id="08ed9-148">**Function**</span></span>|<span data-ttu-id="08ed9-149">**Comment**</span><span class="sxs-lookup"><span data-stu-id="08ed9-149">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="08ed9-150">MAPIProfileFunctions.cpp</span><span class="sxs-lookup"><span data-stu-id="08ed9-150">MAPIProfileFunctions.cpp</span></span>  <br/> |<span data-ttu-id="08ed9-151">OpenProfileSection</span><span class="sxs-lookup"><span data-stu-id="08ed9-151">OpenProfileSection</span></span>  <br/> |<span data-ttu-id="08ed9-152">MFCMAPI 使用**IProviderAdmin::OpenProfileSection**方法从当前配置文件中打开配置文件一节。</span><span class="sxs-lookup"><span data-stu-id="08ed9-152">MFCMAPI uses the **IProviderAdmin::OpenProfileSection** method to open a profile section from the current profile.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="08ed9-153">另请参阅</span><span class="sxs-lookup"><span data-stu-id="08ed9-153">See also</span></span>



[<span data-ttu-id="08ed9-154">IMAPIProp: IUnknown</span><span class="sxs-lookup"><span data-stu-id="08ed9-154">IMAPIProp : IUnknown</span></span>](imapipropiunknown.md)
  
[<span data-ttu-id="08ed9-155">IProfSect: IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="08ed9-155">IProfSect : IMAPIProp</span></span>](iprofsectimapiprop.md)
  
[<span data-ttu-id="08ed9-156">MAPIUID</span><span class="sxs-lookup"><span data-stu-id="08ed9-156">MAPIUID</span></span>](mapiuid.md)
  
[<span data-ttu-id="08ed9-157">IProviderAdmin: IUnknown</span><span class="sxs-lookup"><span data-stu-id="08ed9-157">IProviderAdmin : IUnknown</span></span>](iprovideradminiunknown.md)


[<span data-ttu-id="08ed9-158">MFCMAPI 作为的代码示例</span><span class="sxs-lookup"><span data-stu-id="08ed9-158">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

