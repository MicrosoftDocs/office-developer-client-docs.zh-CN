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
ms.openlocfilehash: 32ebdea3a594b5adf5d46dc081098d3628ae145b
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33437110"
---
# <a name="imsgserviceadminopenprofilesection"></a><span data-ttu-id="f5da7-103">IMsgServiceAdmin::OpenProfileSection</span><span class="sxs-lookup"><span data-stu-id="f5da7-103">IMsgServiceAdmin::OpenProfileSection</span></span>

  
  
<span data-ttu-id="f5da7-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="f5da7-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="f5da7-105">打开当前配置文件的一部分并返回 [IProfSect](iprofsectimapiprop.md) 指针以进一步访问。</span><span class="sxs-lookup"><span data-stu-id="f5da7-105">Opens a section of the current profile and returns an [IProfSect](iprofsectimapiprop.md) pointer for further access.</span></span> 
  
```cpp
HRESULT OpenProfileSection(
  LPMAPIUID lpUID,
  LPCIID lpInterface,
  ULONG ulFlags,
  LPPROFSECT FAR * lppProfSect
);
```

## <a name="parameters"></a><span data-ttu-id="f5da7-106">参数</span><span class="sxs-lookup"><span data-stu-id="f5da7-106">Parameters</span></span>

 <span data-ttu-id="f5da7-107">_lpUID_</span><span class="sxs-lookup"><span data-stu-id="f5da7-107">_lpUID_</span></span>
  
> <span data-ttu-id="f5da7-108">指向标识配置文件节的 [MAPIUID](mapiuid.md) 结构的指针。</span><span class="sxs-lookup"><span data-stu-id="f5da7-108">A pointer to the [MAPIUID](mapiuid.md) structure that identifies the profile section.</span></span> 
    
 <span data-ttu-id="f5da7-109">_lpInterface_</span><span class="sxs-lookup"><span data-stu-id="f5da7-109">_lpInterface_</span></span>
  
> <span data-ttu-id="f5da7-110">[in]指向接口标识符的 (IID) 表示用于访问配置文件节的接口。</span><span class="sxs-lookup"><span data-stu-id="f5da7-110">[in] A pointer to the interface identifier (IID) that represents the interface to be used to access the profile section.</span></span> <span data-ttu-id="f5da7-111">传递 NULL 会导致在  _lppProfSect_ 参数中返回指向其标准接口的指针。</span><span class="sxs-lookup"><span data-stu-id="f5da7-111">Passing NULL results in a pointer to its standard interface being returned in the  _lppProfSect_ parameter.</span></span> <span data-ttu-id="f5da7-112">配置文件部分的标准接口是 **IProfSect**。</span><span class="sxs-lookup"><span data-stu-id="f5da7-112">The standard interface for a profile section is **IProfSect**.</span></span>
    
 <span data-ttu-id="f5da7-113">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="f5da7-113">_ulFlags_</span></span>
  
> <span data-ttu-id="f5da7-114">[in]控制对配置文件节的访问的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="f5da7-114">[in] A bitmask of flags that controls access to the profile section.</span></span> <span data-ttu-id="f5da7-115">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="f5da7-115">The following flags can be set:</span></span>
    
<span data-ttu-id="f5da7-116">MAPI_DEFERRED_ERRORS</span><span class="sxs-lookup"><span data-stu-id="f5da7-116">MAPI_DEFERRED_ERRORS</span></span> 
  
> <span data-ttu-id="f5da7-117">允许 **OpenProfileSection** 成功返回，可能在配置文件部分完全可供调用客户端使用之前。</span><span class="sxs-lookup"><span data-stu-id="f5da7-117">Allows **OpenProfileSection** to return successfully, possibly before the profile section is fully available to the calling client.</span></span> <span data-ttu-id="f5da7-118">如果配置文件部分不可用，则后续调用它可能会引发错误。</span><span class="sxs-lookup"><span data-stu-id="f5da7-118">If the profile section is not available, making a subsequent call to it can raise an error.</span></span> 
    
<span data-ttu-id="f5da7-119">MAPI_MODIFY</span><span class="sxs-lookup"><span data-stu-id="f5da7-119">MAPI_MODIFY</span></span> 
  
> <span data-ttu-id="f5da7-120">请求读/写权限。</span><span class="sxs-lookup"><span data-stu-id="f5da7-120">Requests read/write permission.</span></span> <span data-ttu-id="f5da7-121">默认情况下，使用只读权限打开配置文件节，客户端不应在已授予读/写权限的假设下工作。</span><span class="sxs-lookup"><span data-stu-id="f5da7-121">By default, profile sections are opened with read-only permission, and clients should not work on the assumption that read/write permission has been granted.</span></span> 
    
<span data-ttu-id="f5da7-122">MAPI_FORCE_ACCESS</span><span class="sxs-lookup"><span data-stu-id="f5da7-122">MAPI_FORCE_ACCESS</span></span>
  
> <span data-ttu-id="f5da7-123">允许访问所有配置文件节，甚至是单个服务提供商拥有的内容。</span><span class="sxs-lookup"><span data-stu-id="f5da7-123">Allows access to all profile sections, even those owned by individual service providers.</span></span>
    
 <span data-ttu-id="f5da7-124">_lppProfSect_</span><span class="sxs-lookup"><span data-stu-id="f5da7-124">_lppProfSect_</span></span>
  
> <span data-ttu-id="f5da7-125">[out]指向指向配置文件节的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="f5da7-125">[out] A pointer to a pointer to the profile section.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="f5da7-126">返回值</span><span class="sxs-lookup"><span data-stu-id="f5da7-126">Return value</span></span>

<span data-ttu-id="f5da7-127">S_OK</span><span class="sxs-lookup"><span data-stu-id="f5da7-127">S_OK</span></span> 
  
> <span data-ttu-id="f5da7-128">已成功打开配置文件部分。</span><span class="sxs-lookup"><span data-stu-id="f5da7-128">The profile section was successfully opened.</span></span>
    
<span data-ttu-id="f5da7-129">MAPI_E_NO_ACCESS</span><span class="sxs-lookup"><span data-stu-id="f5da7-129">MAPI_E_NO_ACCESS</span></span> 
  
> <span data-ttu-id="f5da7-130">尝试访问呼叫者权限不足的配置文件部分。</span><span class="sxs-lookup"><span data-stu-id="f5da7-130">An attempt was made to access a profile section for which the caller has insufficient permissions.</span></span>
    
<span data-ttu-id="f5da7-131">MAPI_E_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="f5da7-131">MAPI_E_NOT_FOUND</span></span> 
  
> <span data-ttu-id="f5da7-132">请求的配置文件部分不存在。</span><span class="sxs-lookup"><span data-stu-id="f5da7-132">The requested profile section does not exist.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="f5da7-133">备注</span><span class="sxs-lookup"><span data-stu-id="f5da7-133">Remarks</span></span>

<span data-ttu-id="f5da7-134">**IMsgServiceAdmin：：OpenProfileSection** 方法打开配置文件节，即支持 [IProfSect 接口](iprofsectimapiprop.md)的对象。</span><span class="sxs-lookup"><span data-stu-id="f5da7-134">The **IMsgServiceAdmin::OpenProfileSection** method opens a profile section, an object that supports the [IProfSect](iprofsectimapiprop.md) interface.</span></span> <span data-ttu-id="f5da7-135">配置文件部分用于从会话配置文件读取信息和将信息写入会话配置文件。</span><span class="sxs-lookup"><span data-stu-id="f5da7-135">Profile sections are used for reading information from and writing information to the session profile.</span></span> 
  
 <span data-ttu-id="f5da7-136">**OpenProfileSection** 不能用于打开单个服务提供商拥有的配置文件部分，除非MAPI_FORCE_ACCESS配置文件节。</span><span class="sxs-lookup"><span data-stu-id="f5da7-136">**OpenProfileSection** cannot be used to open profile sections owned by individual service providers unless MAPI_FORCE_ACCESS is used.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="f5da7-137">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="f5da7-137">Notes to callers</span></span>

<span data-ttu-id="f5da7-138">多个客户端可以使用只读权限打开配置文件节，但只有一个客户端可以使用读/写权限打开配置文件节。</span><span class="sxs-lookup"><span data-stu-id="f5da7-138">Multiple clients can open a profile section with read-only permission, but only one client can open a profile section with read/write permission.</span></span> <span data-ttu-id="f5da7-139">如果另一个客户端打开了一个配置文件节，而您尝试通过调用设置了 MAPI_MODIFY 标志的 **OpenProfileSection** 来打开该节，则调用将失败，并返回 MAPI_E_NO_ACCESS。</span><span class="sxs-lookup"><span data-stu-id="f5da7-139">If another client has a profile section open that you attempt to open by calling **OpenProfileSection** with the MAPI_MODIFY flag set, the call will fail, returning MAPI_E_NO_ACCESS.</span></span> 
  
<span data-ttu-id="f5da7-140">如果打开部分进行写入，则只读打开操作将失败。</span><span class="sxs-lookup"><span data-stu-id="f5da7-140">A read-only open operation fails if the section is open for writing.</span></span> 
  
<span data-ttu-id="f5da7-141">您可以通过调用具有 MAPI_MODIFY 标志和 _lpUID_ 参数中不存在 [的 MAPIUID](mapiuid.md)结构的 **OpenProfileSection** 来创建配置文件节。</span><span class="sxs-lookup"><span data-stu-id="f5da7-141">You can create a profile section by calling **OpenProfileSection** with the MAPI_MODIFY flag and a nonexistent [MAPIUID](mapiuid.md) structure in the  _lpUID_ parameter.</span></span> <span data-ttu-id="f5da7-142">请务必指定MAPI_MODIFY。</span><span class="sxs-lookup"><span data-stu-id="f5da7-142">Be sure you specify MAPI_MODIFY.</span></span> <span data-ttu-id="f5da7-143">如果将  _lpUID_ 设置为指向不存在的 **MAPIUID，** 而将 **OpenProfileSection** 设置为使用只读的默认访问模式，则调用将失败，MAPI_E_NOT_FOUND。</span><span class="sxs-lookup"><span data-stu-id="f5da7-143">If you set  _lpUID_ to point to a nonexistent **MAPIUID** and **OpenProfileSection** is set to use the default access mode of read-only, the call will fail with MAPI_E_NOT_FOUND.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="f5da7-144">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="f5da7-144">MFCMAPI reference</span></span>

<span data-ttu-id="f5da7-145">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="f5da7-145">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="f5da7-146">**文件**</span><span class="sxs-lookup"><span data-stu-id="f5da7-146">**File**</span></span>|<span data-ttu-id="f5da7-147">**函数**</span><span class="sxs-lookup"><span data-stu-id="f5da7-147">**Function**</span></span>|<span data-ttu-id="f5da7-148">**备注**</span><span class="sxs-lookup"><span data-stu-id="f5da7-148">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f5da7-149">MAPIProfileFunctions.cpp</span><span class="sxs-lookup"><span data-stu-id="f5da7-149">MAPIProfileFunctions.cpp</span></span>  <br/> |<span data-ttu-id="f5da7-150">OpenProfileSection</span><span class="sxs-lookup"><span data-stu-id="f5da7-150">OpenProfileSection</span></span>  <br/> |<span data-ttu-id="f5da7-151">MFCMAPI 使用 **IMsgServiceAdmin：：OpenProfileSection** 方法打开配置文件节。</span><span class="sxs-lookup"><span data-stu-id="f5da7-151">MFCMAPI uses the **IMsgServiceAdmin::OpenProfileSection** method to open a profile section.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="f5da7-152">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f5da7-152">See also</span></span>



[<span data-ttu-id="f5da7-153">IMAPIProp : IUnknown</span><span class="sxs-lookup"><span data-stu-id="f5da7-153">IMAPIProp : IUnknown</span></span>](imapipropiunknown.md)
  
[<span data-ttu-id="f5da7-154">IMAPISession::OpenProfileSection</span><span class="sxs-lookup"><span data-stu-id="f5da7-154">IMAPISession::OpenProfileSection</span></span>](imapisession-openprofilesection.md)
  
[<span data-ttu-id="f5da7-155">IProfSect : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="f5da7-155">IProfSect : IMAPIProp</span></span>](iprofsectimapiprop.md)
  
[<span data-ttu-id="f5da7-156">MAPIUID</span><span class="sxs-lookup"><span data-stu-id="f5da7-156">MAPIUID</span></span>](mapiuid.md)
  
[<span data-ttu-id="f5da7-157">IMsgServiceAdmin : IUnknown</span><span class="sxs-lookup"><span data-stu-id="f5da7-157">IMsgServiceAdmin : IUnknown</span></span>](imsgserviceadminiunknown.md)


[<span data-ttu-id="f5da7-158">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="f5da7-158">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

