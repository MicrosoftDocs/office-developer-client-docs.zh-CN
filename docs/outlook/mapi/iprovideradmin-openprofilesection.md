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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32301545"
---
# <a name="iprovideradminopenprofilesection"></a><span data-ttu-id="92372-103">IProviderAdmin::OpenProfileSection</span><span class="sxs-lookup"><span data-stu-id="92372-103">IProviderAdmin::OpenProfileSection</span></span>

  
  
<span data-ttu-id="92372-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="92372-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="92372-105">从当前配置文件打开一个配置文件部分, 并返回一个[IProfSect](iprofsectimapiprop.md)指针以供进一步访问。</span><span class="sxs-lookup"><span data-stu-id="92372-105">Opens a profile section from the current profile and returns an [IProfSect](iprofsectimapiprop.md) pointer for further access.</span></span> 
  
```cpp
HRESULT OpenProfileSection(
  LPMAPIUID lpUID,
  LPCIID lpInterface,
  ULONG ulFlags,
  LPPROFSECT FAR * lppProfSect
);
```

## <a name="parameters"></a><span data-ttu-id="92372-106">参数</span><span class="sxs-lookup"><span data-stu-id="92372-106">Parameters</span></span>

 <span data-ttu-id="92372-107">_lpUID_</span><span class="sxs-lookup"><span data-stu-id="92372-107">_lpUID_</span></span>
  
> <span data-ttu-id="92372-108">实时指向[MAPIUID](mapiuid.md)结构的指针, 该结构包含要打开的配置文件部分的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="92372-108">[in] A pointer to the [MAPIUID](mapiuid.md) structure that contains the unique identifier for the profile section to be opened.</span></span> <span data-ttu-id="92372-109">客户端不得为_lpUID_参数传递 NULL。</span><span class="sxs-lookup"><span data-stu-id="92372-109">Clients must not pass NULL for the  _lpUID_ parameter.</span></span> <span data-ttu-id="92372-110">服务提供程序可以传递 NULL 以在其邮件服务入口点函数调用时检索**MAPIUID** 。</span><span class="sxs-lookup"><span data-stu-id="92372-110">Service providers can pass NULL to retrieve the **MAPIUID** when they call from their message service entry point functions.</span></span> 
    
 <span data-ttu-id="92372-111">_lpInterface_</span><span class="sxs-lookup"><span data-stu-id="92372-111">_lpInterface_</span></span>
  
> <span data-ttu-id="92372-112">实时指向接口标识符 (IID) 的指针, 该接口标识符表示要用于访问配置文件部分的接口。</span><span class="sxs-lookup"><span data-stu-id="92372-112">[in] A pointer to the interface identifier (IID) that represents the interface to be used to access the profile section.</span></span> <span data-ttu-id="92372-113">在要返回的配置文件节的标准接口 (**IProfSect**) 中传递 NULL 结果。</span><span class="sxs-lookup"><span data-stu-id="92372-113">Passing NULL results in the profile section's standard interface (**IProfSect**) being returned.</span></span> 
    
 <span data-ttu-id="92372-114">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="92372-114">_ulFlags_</span></span>
  
> <span data-ttu-id="92372-115">实时用于控制如何打开 profile 节的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="92372-115">[in] A bitmask of flags that controls how the profile section is opened.</span></span> <span data-ttu-id="92372-116">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="92372-116">The following flags can be set:</span></span>
    
<span data-ttu-id="92372-117">MAPI_DEFERRED_ERRORS</span><span class="sxs-lookup"><span data-stu-id="92372-117">MAPI_DEFERRED_ERRORS</span></span> 
  
> <span data-ttu-id="92372-118">使**OpenProfileSection**能够成功返回, 这可能在配置文件部分完全可用于调用程序之前。</span><span class="sxs-lookup"><span data-stu-id="92372-118">Enables **OpenProfileSection** to return successfully, possibly before the profile section is fully available to the caller.</span></span> <span data-ttu-id="92372-119">如果 "配置文件" 部分不可用, 则对其进行后续调用可能会引发错误。</span><span class="sxs-lookup"><span data-stu-id="92372-119">If the profile section is not available, making a subsequent call to it can raise an error.</span></span> 
    
<span data-ttu-id="92372-120">MAPI_MODIFY</span><span class="sxs-lookup"><span data-stu-id="92372-120">MAPI_MODIFY</span></span> 
  
> <span data-ttu-id="92372-121">请求读取/写入权限。</span><span class="sxs-lookup"><span data-stu-id="92372-121">Requests read/write permission.</span></span> <span data-ttu-id="92372-122">默认情况下, 使用只读权限打开对象, 并且调用方不应在假定已授予读/写权限时才起作用。</span><span class="sxs-lookup"><span data-stu-id="92372-122">By default, objects are opened with read-only permission, and callers should not work on the assumption that read/write permission has been granted.</span></span> <span data-ttu-id="92372-123">不允许客户端对配置文件的提供程序部分执行读/写权限。</span><span class="sxs-lookup"><span data-stu-id="92372-123">Clients are not allowed read/write permission to provider sections of the profile.</span></span>
    
<span data-ttu-id="92372-124">MAPI_FORCE_ACCESS</span><span class="sxs-lookup"><span data-stu-id="92372-124">MAPI_FORCE_ACCESS</span></span>
  
> <span data-ttu-id="92372-125">允许访问所有配置文件部分, 甚至包括各个服务提供商拥有的部分。</span><span class="sxs-lookup"><span data-stu-id="92372-125">Allows access to all profile sections, even those owned by individual service providers.</span></span>
    
 <span data-ttu-id="92372-126">_lppProfSect_</span><span class="sxs-lookup"><span data-stu-id="92372-126">_lppProfSect_</span></span>
  
> <span data-ttu-id="92372-127">排除指向指向配置文件部分的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="92372-127">[out] A pointer to a pointer to the profile section.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="92372-128">返回值</span><span class="sxs-lookup"><span data-stu-id="92372-128">Return value</span></span>

<span data-ttu-id="92372-129">S_OK</span><span class="sxs-lookup"><span data-stu-id="92372-129">S_OK</span></span> 
  
> <span data-ttu-id="92372-130">已成功打开 "配置文件" 部分。</span><span class="sxs-lookup"><span data-stu-id="92372-130">The profile section was successfully opened.</span></span>
    
<span data-ttu-id="92372-131">MAPI_E_NO_ACCESS</span><span class="sxs-lookup"><span data-stu-id="92372-131">MAPI_E_NO_ACCESS</span></span> 
  
> <span data-ttu-id="92372-132">试图修改只读配置文件部分或访问用户具有的权限不足的对象。</span><span class="sxs-lookup"><span data-stu-id="92372-132">An attempt was made to modify a read-only profile section or to access an object for which the user has insufficient permissions.</span></span>
    
<span data-ttu-id="92372-133">MAPI_E_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="92372-133">MAPI_E_NOT_FOUND</span></span> 
  
> <span data-ttu-id="92372-134">请求的配置文件部分不存在。</span><span class="sxs-lookup"><span data-stu-id="92372-134">The requested profile section does not exist.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="92372-135">注解</span><span class="sxs-lookup"><span data-stu-id="92372-135">Remarks</span></span>

<span data-ttu-id="92372-136">**IProviderAdmin:: OpenProfileSection**方法打开一个配置文件部分, 使呼叫者能够从活动配置文件中读取信息, 也可能将信息写入到活动配置文件。</span><span class="sxs-lookup"><span data-stu-id="92372-136">The **IProviderAdmin::OpenProfileSection** method opens a profile section, enabling the caller to read information from and possibly write information to the active profile.</span></span> 
  
<span data-ttu-id="92372-137">客户端无法使用**OpenProfileSection**方法打开属于提供程序的配置文件部分。</span><span class="sxs-lookup"><span data-stu-id="92372-137">Clients cannot open profile sections that belong to providers by using the **OpenProfileSection** method.</span></span> 
  
<span data-ttu-id="92372-138">多个客户端或服务提供商可以同时打开具有只读权限的配置文件节。</span><span class="sxs-lookup"><span data-stu-id="92372-138">Multiple clients or service providers can simultaneously open a profile section with read-only permission.</span></span> <span data-ttu-id="92372-139">但是, 当使用读/写权限打开配置文件节时, 不能进行任何其他调用来打开该节, 而不管 access 的类型如何。</span><span class="sxs-lookup"><span data-stu-id="92372-139">However, when a profile section is open with read/write permission, no other calls can be made to open the section, regardless of the type of access.</span></span> <span data-ttu-id="92372-140">如果使用只读权限打开配置文件部分, 则对请求读/写权限的后续调用将会失败, 并出现 MAPI_E_NO_ACCESS。</span><span class="sxs-lookup"><span data-stu-id="92372-140">If a profile section is open with read-only permission, a subsequent call to request read/write permission will fail with MAPI_E_NO_ACCESS.</span></span> <span data-ttu-id="92372-141">同样, 如果某个部分是以读/写权限打开的, 则对请求只读权限的后续调用也会失败。</span><span class="sxs-lookup"><span data-stu-id="92372-141">Likewise, if a section is open with read/write permission, a subsequent call to request read-only permission will also fail.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="92372-142">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="92372-142">Notes to callers</span></span>

<span data-ttu-id="92372-143">如果您通过在_ulFlags_中传递 MAPI_MODIFY 和_lpUID_中的未知**MAPIUID**来请求**OpenProfileSection**打开不存在的配置文件部分, 则将创建该配置文件部分。</span><span class="sxs-lookup"><span data-stu-id="92372-143">If you request that **OpenProfileSection** open a nonexistent profile section by passing MAPI_MODIFY in  _ulFlags_ and an unknown **MAPIUID** in  _lpUID_, the profile section will be created.</span></span> 
  
<span data-ttu-id="92372-144">如果您请求**OpenProfileSection**打开一个具有只读权限的不存在的节, 则它将返回 MAPI_E_NOT_FOUND。</span><span class="sxs-lookup"><span data-stu-id="92372-144">If you request that **OpenProfileSection** open a nonexistent section with read-only permission, it returns MAPI_E_NOT_FOUND.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="92372-145">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="92372-145">MFCMAPI reference</span></span>

<span data-ttu-id="92372-146">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="92372-146">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="92372-147">**文件**</span><span class="sxs-lookup"><span data-stu-id="92372-147">**File**</span></span>|<span data-ttu-id="92372-148">**函数**</span><span class="sxs-lookup"><span data-stu-id="92372-148">**Function**</span></span>|<span data-ttu-id="92372-149">**备注**</span><span class="sxs-lookup"><span data-stu-id="92372-149">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="92372-150">MAPIProfileFunctions</span><span class="sxs-lookup"><span data-stu-id="92372-150">MAPIProfileFunctions.cpp</span></span>  <br/> |<span data-ttu-id="92372-151">OpenProfileSection</span><span class="sxs-lookup"><span data-stu-id="92372-151">OpenProfileSection</span></span>  <br/> |<span data-ttu-id="92372-152">MFCMAPI 使用**IProviderAdmin:: OpenProfileSection**方法从当前配置文件中打开配置文件节。</span><span class="sxs-lookup"><span data-stu-id="92372-152">MFCMAPI uses the **IProviderAdmin::OpenProfileSection** method to open a profile section from the current profile.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="92372-153">另请参阅</span><span class="sxs-lookup"><span data-stu-id="92372-153">See also</span></span>



[<span data-ttu-id="92372-154">IMAPIProp : IUnknown</span><span class="sxs-lookup"><span data-stu-id="92372-154">IMAPIProp : IUnknown</span></span>](imapipropiunknown.md)
  
[<span data-ttu-id="92372-155">IProfSect : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="92372-155">IProfSect : IMAPIProp</span></span>](iprofsectimapiprop.md)
  
[<span data-ttu-id="92372-156">MAPIUID</span><span class="sxs-lookup"><span data-stu-id="92372-156">MAPIUID</span></span>](mapiuid.md)
  
[<span data-ttu-id="92372-157">IProviderAdmin : IUnknown</span><span class="sxs-lookup"><span data-stu-id="92372-157">IProviderAdmin : IUnknown</span></span>](iprovideradminiunknown.md)


[<span data-ttu-id="92372-158">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="92372-158">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

