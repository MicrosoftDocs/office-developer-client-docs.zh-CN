---
title: IMsgServiceAdminOpenProfileSection
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMsgServiceAdmin.OpenProfileSection
api_type:
- COM
ms.assetid: 7f24910a-e14e-44a1-8477-d8968130ba74
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 8dfa777480af48819e5357fad9b1e7524148a8b7
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22568810"
---
# <a name="imsgserviceadminopenprofilesection"></a><span data-ttu-id="55af2-103">IMsgServiceAdmin::OpenProfileSection</span><span class="sxs-lookup"><span data-stu-id="55af2-103">IMsgServiceAdmin::OpenProfileSection</span></span>

  
  
<span data-ttu-id="55af2-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="55af2-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="55af2-105">打开当前配置文件的节并返回进一步访问[IProfSect](iprofsectimapiprop.md)指针。</span><span class="sxs-lookup"><span data-stu-id="55af2-105">Opens a section of the current profile and returns an [IProfSect](iprofsectimapiprop.md) pointer for further access.</span></span> 
  
```cpp
HRESULT OpenProfileSection(
  LPMAPIUID lpUID,
  LPCIID lpInterface,
  ULONG ulFlags,
  LPPROFSECT FAR * lppProfSect
);
```

## <a name="parameters"></a><span data-ttu-id="55af2-106">参数</span><span class="sxs-lookup"><span data-stu-id="55af2-106">Parameters</span></span>

 <span data-ttu-id="55af2-107">_lpUID_</span><span class="sxs-lookup"><span data-stu-id="55af2-107">_lpUID_</span></span>
  
> <span data-ttu-id="55af2-108">指向标识配置文件部分的[MAPIUID](mapiuid.md)结构的指针。</span><span class="sxs-lookup"><span data-stu-id="55af2-108">A pointer to the [MAPIUID](mapiuid.md) structure that identifies the profile section.</span></span> 
    
 <span data-ttu-id="55af2-109">_lpInterface_</span><span class="sxs-lookup"><span data-stu-id="55af2-109">_lpInterface_</span></span>
  
> <span data-ttu-id="55af2-110">[in]指向接口标识 (IID) 值，该值代表要用于访问配置文件部分的接口的指针。</span><span class="sxs-lookup"><span data-stu-id="55af2-110">[in] A pointer to the interface identifier (IID) that represents the interface to be used to access the profile section.</span></span> <span data-ttu-id="55af2-111">传递 NULL 将导致指向_lppProfSect_参数中要返回其标准接口的指针。</span><span class="sxs-lookup"><span data-stu-id="55af2-111">Passing NULL results in a pointer to its standard interface being returned in the  _lppProfSect_ parameter.</span></span> <span data-ttu-id="55af2-112">配置文件节的标准接口是**IProfSect**。</span><span class="sxs-lookup"><span data-stu-id="55af2-112">The standard interface for a profile section is **IProfSect**.</span></span>
    
 <span data-ttu-id="55af2-113">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="55af2-113">_ulFlags_</span></span>
  
> <span data-ttu-id="55af2-114">[in]Flags 控制访问到配置文件部分的位掩码。</span><span class="sxs-lookup"><span data-stu-id="55af2-114">[in] A bitmask of flags that controls access to the profile section.</span></span> <span data-ttu-id="55af2-115">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="55af2-115">The following flags can be set:</span></span>
    
<span data-ttu-id="55af2-116">MAPI_DEFERRED_ERRORS</span><span class="sxs-lookup"><span data-stu-id="55af2-116">MAPI_DEFERRED_ERRORS</span></span> 
  
> <span data-ttu-id="55af2-117">允许**OpenProfileSection**成功返回可能之前配置文件节是完全可调用客户端。</span><span class="sxs-lookup"><span data-stu-id="55af2-117">Allows **OpenProfileSection** to return successfully, possibly before the profile section is fully available to the calling client.</span></span> <span data-ttu-id="55af2-118">如果配置文件部分不可用，进行后续呼叫到它会引发错误。</span><span class="sxs-lookup"><span data-stu-id="55af2-118">If the profile section is not available, making a subsequent call to it can raise an error.</span></span> 
    
<span data-ttu-id="55af2-119">MAPI_MODIFY</span><span class="sxs-lookup"><span data-stu-id="55af2-119">MAPI_MODIFY</span></span> 
  
> <span data-ttu-id="55af2-120">请求读/写权限。</span><span class="sxs-lookup"><span data-stu-id="55af2-120">Requests read/write permission.</span></span> <span data-ttu-id="55af2-121">默认情况下配置文件部分打开具有只读权限和客户端不应从事的读/写权限授予假设。</span><span class="sxs-lookup"><span data-stu-id="55af2-121">By default, profile sections are opened with read-only permission, and clients should not work on the assumption that read/write permission has been granted.</span></span> 
    
<span data-ttu-id="55af2-122">MAPI_FORCE_ACCESS</span><span class="sxs-lookup"><span data-stu-id="55af2-122">MAPI_FORCE_ACCESS</span></span>
  
> <span data-ttu-id="55af2-123">允许对所有配置文件节，即使他们拥有单独的服务提供程序的访问。</span><span class="sxs-lookup"><span data-stu-id="55af2-123">Allows access to all profile sections, even those owned by individual service providers.</span></span>
    
 <span data-ttu-id="55af2-124">_lppProfSect_</span><span class="sxs-lookup"><span data-stu-id="55af2-124">_lppProfSect_</span></span>
  
> <span data-ttu-id="55af2-125">[输出]指向配置文件部分的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="55af2-125">[out] A pointer to a pointer to the profile section.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="55af2-126">返回值</span><span class="sxs-lookup"><span data-stu-id="55af2-126">Return value</span></span>

<span data-ttu-id="55af2-127">S_OK</span><span class="sxs-lookup"><span data-stu-id="55af2-127">S_OK</span></span> 
  
> <span data-ttu-id="55af2-128">已成功打开配置文件部分。</span><span class="sxs-lookup"><span data-stu-id="55af2-128">The profile section was successfully opened.</span></span>
    
<span data-ttu-id="55af2-129">MAPI_E_NO_ACCESS</span><span class="sxs-lookup"><span data-stu-id="55af2-129">MAPI_E_NO_ACCESS</span></span> 
  
> <span data-ttu-id="55af2-130">尝试访问呼叫者有权限不足，无法配置文件一节。</span><span class="sxs-lookup"><span data-stu-id="55af2-130">An attempt was made to access a profile section for which the caller has insufficient permissions.</span></span>
    
<span data-ttu-id="55af2-131">MAPI_E_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="55af2-131">MAPI_E_NOT_FOUND</span></span> 
  
> <span data-ttu-id="55af2-132">请求的配置文件节不存在。</span><span class="sxs-lookup"><span data-stu-id="55af2-132">The requested profile section does not exist.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="55af2-133">注解</span><span class="sxs-lookup"><span data-stu-id="55af2-133">Remarks</span></span>

<span data-ttu-id="55af2-134">**IMsgServiceAdmin::OpenProfileSection**方法打开配置文件节，支持[IProfSect](iprofsectimapiprop.md)接口的对象。</span><span class="sxs-lookup"><span data-stu-id="55af2-134">The **IMsgServiceAdmin::OpenProfileSection** method opens a profile section, an object that supports the [IProfSect](iprofsectimapiprop.md) interface.</span></span> <span data-ttu-id="55af2-135">配置文件节用于进行读取和写入会话配置文件信息。</span><span class="sxs-lookup"><span data-stu-id="55af2-135">Profile sections are used for reading information from and writing information to the session profile.</span></span> 
  
 <span data-ttu-id="55af2-136">**OpenProfileSection**不能用于打开归单个服务提供程序，除非使用 MAPI_FORCE_ACCESS 的配置文件部分。</span><span class="sxs-lookup"><span data-stu-id="55af2-136">**OpenProfileSection** cannot be used to open profile sections owned by individual service providers unless MAPI_FORCE_ACCESS is used.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="55af2-137">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="55af2-137">Notes to callers</span></span>

<span data-ttu-id="55af2-138">多个客户端可以具有只读权限，打开配置文件一节，但只有一个客户端可以具有读/写权限打开配置文件一节。</span><span class="sxs-lookup"><span data-stu-id="55af2-138">Multiple clients can open a profile section with read-only permission, but only one client can open a profile section with read/write permission.</span></span> <span data-ttu-id="55af2-139">如果另一个客户端打开您尝试通过调用设置了 MAPI_MODIFY 标志**OpenProfileSection**打开配置文件一节，则调用将失败，返回 MAPI_E_NO_ACCESS。</span><span class="sxs-lookup"><span data-stu-id="55af2-139">If another client has a profile section open that you attempt to open by calling **OpenProfileSection** with the MAPI_MODIFY flag set, the call will fail, returning MAPI_E_NO_ACCESS.</span></span> 
  
<span data-ttu-id="55af2-140">只读状态打开操作失败，如果该节为打开以进行写入。</span><span class="sxs-lookup"><span data-stu-id="55af2-140">A read-only open operation fails if the section is open for writing.</span></span> 
  
<span data-ttu-id="55af2-141">您可以通过调用不带 MAPI_MODIFY 标志和_lpUID_参数中的不存在[MAPIUID](mapiuid.md)结构**OpenProfileSection**创建配置文件一节。</span><span class="sxs-lookup"><span data-stu-id="55af2-141">You can create a profile section by calling **OpenProfileSection** with the MAPI_MODIFY flag and a nonexistent [MAPIUID](mapiuid.md) structure in the  _lpUID_ parameter.</span></span> <span data-ttu-id="55af2-142">确保您指定 MAPI_MODIFY。</span><span class="sxs-lookup"><span data-stu-id="55af2-142">Be sure you specify MAPI_MODIFY.</span></span> <span data-ttu-id="55af2-143">如果设置_lpUID_以指向不存在**MAPIUID** **OpenProfileSection**设置为使用默认访问模式的只读的则调用将失败与 MAPI_E_NOT_FOUND。</span><span class="sxs-lookup"><span data-stu-id="55af2-143">If you set  _lpUID_ to point to a nonexistent **MAPIUID** and **OpenProfileSection** is set to use the default access mode of read-only, the call will fail with MAPI_E_NOT_FOUND.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="55af2-144">MFCMAPI 参考 （英文）</span><span class="sxs-lookup"><span data-stu-id="55af2-144">MFCMAPI reference</span></span>

<span data-ttu-id="55af2-145">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="55af2-145">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="55af2-146">**文件**</span><span class="sxs-lookup"><span data-stu-id="55af2-146">**File**</span></span>|<span data-ttu-id="55af2-147">**函数**</span><span class="sxs-lookup"><span data-stu-id="55af2-147">**Function**</span></span>|<span data-ttu-id="55af2-148">**Comment**</span><span class="sxs-lookup"><span data-stu-id="55af2-148">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="55af2-149">MAPIProfileFunctions.cpp</span><span class="sxs-lookup"><span data-stu-id="55af2-149">MAPIProfileFunctions.cpp</span></span>  <br/> |<span data-ttu-id="55af2-150">OpenProfileSection</span><span class="sxs-lookup"><span data-stu-id="55af2-150">OpenProfileSection</span></span>  <br/> |<span data-ttu-id="55af2-151">MFCMAPI 使用**IMsgServiceAdmin::OpenProfileSection**方法打开配置文件一节。</span><span class="sxs-lookup"><span data-stu-id="55af2-151">MFCMAPI uses the **IMsgServiceAdmin::OpenProfileSection** method to open a profile section.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="55af2-152">另请参阅</span><span class="sxs-lookup"><span data-stu-id="55af2-152">See also</span></span>



[<span data-ttu-id="55af2-153">IMAPIProp : IUnknown</span><span class="sxs-lookup"><span data-stu-id="55af2-153">IMAPIProp : IUnknown</span></span>](imapipropiunknown.md)
  
[<span data-ttu-id="55af2-154">IMAPISession::OpenProfileSection</span><span class="sxs-lookup"><span data-stu-id="55af2-154">IMAPISession::OpenProfileSection</span></span>](imapisession-openprofilesection.md)
  
[<span data-ttu-id="55af2-155">IProfSect : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="55af2-155">IProfSect : IMAPIProp</span></span>](iprofsectimapiprop.md)
  
[<span data-ttu-id="55af2-156">MAPIUID</span><span class="sxs-lookup"><span data-stu-id="55af2-156">MAPIUID</span></span>](mapiuid.md)
  
[<span data-ttu-id="55af2-157">IMsgServiceAdmin : IUnknown</span><span class="sxs-lookup"><span data-stu-id="55af2-157">IMsgServiceAdmin : IUnknown</span></span>](imsgserviceadminiunknown.md)


[<span data-ttu-id="55af2-158">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="55af2-158">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

