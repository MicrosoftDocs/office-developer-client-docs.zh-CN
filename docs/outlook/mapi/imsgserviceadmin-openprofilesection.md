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
# <a name="imsgserviceadminopenprofilesection"></a><span data-ttu-id="c3016-103">IMsgServiceAdmin::OpenProfileSection</span><span class="sxs-lookup"><span data-stu-id="c3016-103">IMsgServiceAdmin::OpenProfileSection</span></span>

  
  
<span data-ttu-id="c3016-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="c3016-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="c3016-105">打开当前配置文件的一个部分, 并返回一个[IProfSect](iprofsectimapiprop.md)指针以供进一步访问。</span><span class="sxs-lookup"><span data-stu-id="c3016-105">Opens a section of the current profile and returns an [IProfSect](iprofsectimapiprop.md) pointer for further access.</span></span> 
  
```cpp
HRESULT OpenProfileSection(
  LPMAPIUID lpUID,
  LPCIID lpInterface,
  ULONG ulFlags,
  LPPROFSECT FAR * lppProfSect
);
```

## <a name="parameters"></a><span data-ttu-id="c3016-106">参数</span><span class="sxs-lookup"><span data-stu-id="c3016-106">Parameters</span></span>

 <span data-ttu-id="c3016-107">_lpUID_</span><span class="sxs-lookup"><span data-stu-id="c3016-107">_lpUID_</span></span>
  
> <span data-ttu-id="c3016-108">指向标识配置文件节的[MAPIUID](mapiuid.md)结构的指针。</span><span class="sxs-lookup"><span data-stu-id="c3016-108">A pointer to the [MAPIUID](mapiuid.md) structure that identifies the profile section.</span></span> 
    
 <span data-ttu-id="c3016-109">_lpInterface_</span><span class="sxs-lookup"><span data-stu-id="c3016-109">_lpInterface_</span></span>
  
> <span data-ttu-id="c3016-110">实时指向接口标识符 (IID) 的指针, 该接口标识符表示要用于访问配置文件部分的接口。</span><span class="sxs-lookup"><span data-stu-id="c3016-110">[in] A pointer to the interface identifier (IID) that represents the interface to be used to access the profile section.</span></span> <span data-ttu-id="c3016-111">将 NULL 结果传递到在_lppProfSect_参数中返回到其标准接口的指针。</span><span class="sxs-lookup"><span data-stu-id="c3016-111">Passing NULL results in a pointer to its standard interface being returned in the  _lppProfSect_ parameter.</span></span> <span data-ttu-id="c3016-112">配置文件节的标准接口是**IProfSect**。</span><span class="sxs-lookup"><span data-stu-id="c3016-112">The standard interface for a profile section is **IProfSect**.</span></span>
    
 <span data-ttu-id="c3016-113">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="c3016-113">_ulFlags_</span></span>
  
> <span data-ttu-id="c3016-114">实时用于控制对配置文件部分的访问的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="c3016-114">[in] A bitmask of flags that controls access to the profile section.</span></span> <span data-ttu-id="c3016-115">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="c3016-115">The following flags can be set:</span></span>
    
<span data-ttu-id="c3016-116">MAPI_DEFERRED_ERRORS</span><span class="sxs-lookup"><span data-stu-id="c3016-116">MAPI_DEFERRED_ERRORS</span></span> 
  
> <span data-ttu-id="c3016-117">允许**OpenProfileSection**成功返回, 这可能在配置文件部分完全可用于调用客户端之前返回。</span><span class="sxs-lookup"><span data-stu-id="c3016-117">Allows **OpenProfileSection** to return successfully, possibly before the profile section is fully available to the calling client.</span></span> <span data-ttu-id="c3016-118">如果 "配置文件" 部分不可用, 则对其进行后续调用可能会引发错误。</span><span class="sxs-lookup"><span data-stu-id="c3016-118">If the profile section is not available, making a subsequent call to it can raise an error.</span></span> 
    
<span data-ttu-id="c3016-119">MAPI_MODIFY</span><span class="sxs-lookup"><span data-stu-id="c3016-119">MAPI_MODIFY</span></span> 
  
> <span data-ttu-id="c3016-120">请求读取/写入权限。</span><span class="sxs-lookup"><span data-stu-id="c3016-120">Requests read/write permission.</span></span> <span data-ttu-id="c3016-121">默认情况下, 配置文件分区以只读权限打开, 并且客户端不应在假定已授予读/写权限时才起作用。</span><span class="sxs-lookup"><span data-stu-id="c3016-121">By default, profile sections are opened with read-only permission, and clients should not work on the assumption that read/write permission has been granted.</span></span> 
    
<span data-ttu-id="c3016-122">MAPI_FORCE_ACCESS</span><span class="sxs-lookup"><span data-stu-id="c3016-122">MAPI_FORCE_ACCESS</span></span>
  
> <span data-ttu-id="c3016-123">允许访问所有配置文件部分, 甚至包括各个服务提供商拥有的部分。</span><span class="sxs-lookup"><span data-stu-id="c3016-123">Allows access to all profile sections, even those owned by individual service providers.</span></span>
    
 <span data-ttu-id="c3016-124">_lppProfSect_</span><span class="sxs-lookup"><span data-stu-id="c3016-124">_lppProfSect_</span></span>
  
> <span data-ttu-id="c3016-125">排除指向指向配置文件部分的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="c3016-125">[out] A pointer to a pointer to the profile section.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="c3016-126">返回值</span><span class="sxs-lookup"><span data-stu-id="c3016-126">Return value</span></span>

<span data-ttu-id="c3016-127">S_OK</span><span class="sxs-lookup"><span data-stu-id="c3016-127">S_OK</span></span> 
  
> <span data-ttu-id="c3016-128">已成功打开 "配置文件" 部分。</span><span class="sxs-lookup"><span data-stu-id="c3016-128">The profile section was successfully opened.</span></span>
    
<span data-ttu-id="c3016-129">MAPI_E_NO_ACCESS</span><span class="sxs-lookup"><span data-stu-id="c3016-129">MAPI_E_NO_ACCESS</span></span> 
  
> <span data-ttu-id="c3016-130">试图访问呼叫者没有足够权限的配置文件部分。</span><span class="sxs-lookup"><span data-stu-id="c3016-130">An attempt was made to access a profile section for which the caller has insufficient permissions.</span></span>
    
<span data-ttu-id="c3016-131">MAPI_E_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="c3016-131">MAPI_E_NOT_FOUND</span></span> 
  
> <span data-ttu-id="c3016-132">请求的配置文件部分不存在。</span><span class="sxs-lookup"><span data-stu-id="c3016-132">The requested profile section does not exist.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="c3016-133">说明</span><span class="sxs-lookup"><span data-stu-id="c3016-133">Remarks</span></span>

<span data-ttu-id="c3016-134">**IMsgServiceAdmin:: OpenProfileSection**方法打开一个 profile 部分, 该对象支持[IProfSect](iprofsectimapiprop.md)接口。</span><span class="sxs-lookup"><span data-stu-id="c3016-134">The **IMsgServiceAdmin::OpenProfileSection** method opens a profile section, an object that supports the [IProfSect](iprofsectimapiprop.md) interface.</span></span> <span data-ttu-id="c3016-135">配置文件节用于读取信息以及将信息写入会话配置文件。</span><span class="sxs-lookup"><span data-stu-id="c3016-135">Profile sections are used for reading information from and writing information to the session profile.</span></span> 
  
 <span data-ttu-id="c3016-136">**OpenProfileSection**不能用于打开由单个服务提供商拥有的配置文件节, 除非使用 MAPI_FORCE_ACCESS。</span><span class="sxs-lookup"><span data-stu-id="c3016-136">**OpenProfileSection** cannot be used to open profile sections owned by individual service providers unless MAPI_FORCE_ACCESS is used.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="c3016-137">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="c3016-137">Notes to callers</span></span>

<span data-ttu-id="c3016-138">多个客户端可以打开具有只读权限的配置文件部分, 但只有一台客户端可以打开具有读/写权限的配置文件节。</span><span class="sxs-lookup"><span data-stu-id="c3016-138">Multiple clients can open a profile section with read-only permission, but only one client can open a profile section with read/write permission.</span></span> <span data-ttu-id="c3016-139">如果另一个客户端有一个配置文件节打开, 您试图通过调用**OpenProfileSection**并设置 MAPI_MODIFY 标志来打开, 则该调用将失败, 返回 MAPI_E_NO_ACCESS。</span><span class="sxs-lookup"><span data-stu-id="c3016-139">If another client has a profile section open that you attempt to open by calling **OpenProfileSection** with the MAPI_MODIFY flag set, the call will fail, returning MAPI_E_NO_ACCESS.</span></span> 
  
<span data-ttu-id="c3016-140">如果为写入打开了该节, 则只读打开操作将失败。</span><span class="sxs-lookup"><span data-stu-id="c3016-140">A read-only open operation fails if the section is open for writing.</span></span> 
  
<span data-ttu-id="c3016-141">您可以通过在_lpUID_参数中调用带有 MAPI_MODIFY 标志的**OpenProfileSection**和不存在的[MAPIUID](mapiuid.md)结构来创建配置文件节。</span><span class="sxs-lookup"><span data-stu-id="c3016-141">You can create a profile section by calling **OpenProfileSection** with the MAPI_MODIFY flag and a nonexistent [MAPIUID](mapiuid.md) structure in the  _lpUID_ parameter.</span></span> <span data-ttu-id="c3016-142">确保指定 MAPI_MODIFY。</span><span class="sxs-lookup"><span data-stu-id="c3016-142">Be sure you specify MAPI_MODIFY.</span></span> <span data-ttu-id="c3016-143">如果将_lpUID_设置为指向不存在的**MAPIUID** , 并且将**OpenProfileSection**设置为使用只读的默认访问模式, 则调用将会因 MAPI_E_NOT_FOUND 而失败。</span><span class="sxs-lookup"><span data-stu-id="c3016-143">If you set  _lpUID_ to point to a nonexistent **MAPIUID** and **OpenProfileSection** is set to use the default access mode of read-only, the call will fail with MAPI_E_NOT_FOUND.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="c3016-144">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="c3016-144">MFCMAPI reference</span></span>

<span data-ttu-id="c3016-145">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="c3016-145">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="c3016-146">**文件**</span><span class="sxs-lookup"><span data-stu-id="c3016-146">**File**</span></span>|<span data-ttu-id="c3016-147">**函数**</span><span class="sxs-lookup"><span data-stu-id="c3016-147">**Function**</span></span>|<span data-ttu-id="c3016-148">**备注**</span><span class="sxs-lookup"><span data-stu-id="c3016-148">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c3016-149">MAPIProfileFunctions</span><span class="sxs-lookup"><span data-stu-id="c3016-149">MAPIProfileFunctions.cpp</span></span>  <br/> |<span data-ttu-id="c3016-150">OpenProfileSection</span><span class="sxs-lookup"><span data-stu-id="c3016-150">OpenProfileSection</span></span>  <br/> |<span data-ttu-id="c3016-151">MFCMAPI 使用**IMsgServiceAdmin:: OpenProfileSection**方法打开配置文件部分。</span><span class="sxs-lookup"><span data-stu-id="c3016-151">MFCMAPI uses the **IMsgServiceAdmin::OpenProfileSection** method to open a profile section.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="c3016-152">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c3016-152">See also</span></span>



[<span data-ttu-id="c3016-153">IMAPIProp : IUnknown</span><span class="sxs-lookup"><span data-stu-id="c3016-153">IMAPIProp : IUnknown</span></span>](imapipropiunknown.md)
  
[<span data-ttu-id="c3016-154">IMAPISession::OpenProfileSection</span><span class="sxs-lookup"><span data-stu-id="c3016-154">IMAPISession::OpenProfileSection</span></span>](imapisession-openprofilesection.md)
  
[<span data-ttu-id="c3016-155">IProfSect : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="c3016-155">IProfSect : IMAPIProp</span></span>](iprofsectimapiprop.md)
  
[<span data-ttu-id="c3016-156">MAPIUID</span><span class="sxs-lookup"><span data-stu-id="c3016-156">MAPIUID</span></span>](mapiuid.md)
  
[<span data-ttu-id="c3016-157">IMsgServiceAdmin : IUnknown</span><span class="sxs-lookup"><span data-stu-id="c3016-157">IMsgServiceAdmin : IUnknown</span></span>](imsgserviceadminiunknown.md)


[<span data-ttu-id="c3016-158">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="c3016-158">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

