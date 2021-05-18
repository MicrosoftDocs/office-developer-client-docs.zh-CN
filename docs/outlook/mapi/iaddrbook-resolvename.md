---
title: IAddrBookResolveName
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IAddrBook.ResolveName
api_type:
- COM
ms.assetid: a7823c16-efda-45c2-b931-3e1fbc823b0b
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 8a6a73153b857078cb37d94a634a6b0215a0a8c5
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33408129"
---
# <a name="iaddrbookresolvename"></a><span data-ttu-id="7711c-103">IAddrBook::ResolveName</span><span class="sxs-lookup"><span data-stu-id="7711c-103">IAddrBook::ResolveName</span></span>

  
  
<span data-ttu-id="7711c-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="7711c-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="7711c-105">执行名称解析，将条目标识符分配给收件人列表中的收件人。</span><span class="sxs-lookup"><span data-stu-id="7711c-105">Performs name resolution, assigning entry identifiers to recipients in a recipient list.</span></span>
  
```cpp
HRESULT ResolveName(
  ULONG_PTR ulUIParam,
  ULONG ulFlags,
  LPSTR lpszNewEntryTitle,
  LPADRLIST lpAdrList
);
```

## <a name="parameters"></a><span data-ttu-id="7711c-106">参数</span><span class="sxs-lookup"><span data-stu-id="7711c-106">Parameters</span></span>

 <span data-ttu-id="7711c-107">_ulUIParam_</span><span class="sxs-lookup"><span data-stu-id="7711c-107">_ulUIParam_</span></span>
  
> <span data-ttu-id="7711c-108">[in]对话框的父窗口的句柄，如果已指定，则显示该句柄以提示用户解决歧义问题。</span><span class="sxs-lookup"><span data-stu-id="7711c-108">[in] A handle to the parent window of a dialog box that is shown, if specified, to prompt the user to resolve ambiguity.</span></span>
    
 <span data-ttu-id="7711c-109">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="7711c-109">_ulFlags_</span></span>
  
> <span data-ttu-id="7711c-110">[in]控制解决方案过程各个方面的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="7711c-110">[in] A bitmask of flags that control various aspects of the resolution process.</span></span> <span data-ttu-id="7711c-111">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="7711c-111">The following flags can be set:</span></span>
    
<span data-ttu-id="7711c-112">AB_UNICODEUI</span><span class="sxs-lookup"><span data-stu-id="7711c-112">AB_UNICODEUI</span></span>
  
> <span data-ttu-id="7711c-113">指示  _lpszNewEntryTitle_ 是 UNICODE 字符串。</span><span class="sxs-lookup"><span data-stu-id="7711c-113">Indicates that  _lpszNewEntryTitle_ is a UNICODE string.</span></span> 
    
<span data-ttu-id="7711c-114">MAPI_CACHE_ONLY</span><span class="sxs-lookup"><span data-stu-id="7711c-114">MAPI_CACHE_ONLY</span></span>
  
> <span data-ttu-id="7711c-115">仅使用脱机通讯簿执行名称解析。</span><span class="sxs-lookup"><span data-stu-id="7711c-115">Use only the offline address book to perform name resolution.</span></span> <span data-ttu-id="7711c-116">例如，您可以使用此标志允许客户端应用程序在缓存 exchange 模式下打开全局地址列表 (GAL) ，并访问缓存中的该通讯簿中的条目，而无需在客户端和服务器之间创建流量。</span><span class="sxs-lookup"><span data-stu-id="7711c-116">For example, you can use this flag to allow a client application to open the global address list (GAL) in cached exchange mode and access an entry in that address book from the cache without creating traffic between the client and the server.</span></span> <span data-ttu-id="7711c-117">此标志仅受通讯簿Exchange支持。</span><span class="sxs-lookup"><span data-stu-id="7711c-117">This flag is supported only by the Exchange Address Book Provider.</span></span>
    
<span data-ttu-id="7711c-118">MAPI_DIALOG</span><span class="sxs-lookup"><span data-stu-id="7711c-118">MAPI_DIALOG</span></span> 
  
> <span data-ttu-id="7711c-119">显示一个对话框，提示用户输入其他名称解析信息。</span><span class="sxs-lookup"><span data-stu-id="7711c-119">Displays a dialog box to prompt the user for additional name resolution information.</span></span> <span data-ttu-id="7711c-120">如果未设置此标志，则不显示任何对话框。</span><span class="sxs-lookup"><span data-stu-id="7711c-120">If this flag is not set, no dialog box is displayed.</span></span> 
    
<span data-ttu-id="7711c-121">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="7711c-121">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="7711c-122">指示地址列表中返回的属性的类型应为 PT_UNICODE 而不是 PT_STRING8。</span><span class="sxs-lookup"><span data-stu-id="7711c-122">Indicates that the properties returned in the address list should be of type PT_UNICODE instead of PT_STRING8.</span></span> 
    
 <span data-ttu-id="7711c-123">_lpszNewEntryTitle_</span><span class="sxs-lookup"><span data-stu-id="7711c-123">_lpszNewEntryTitle_</span></span>
  
> <span data-ttu-id="7711c-124">[in]指向对话框中控件标题的文本的指针，提示用户输入收件人。</span><span class="sxs-lookup"><span data-stu-id="7711c-124">[in] A pointer to text for the title of the control in the dialog box that prompts the user to enter a recipient.</span></span> <span data-ttu-id="7711c-125">标题因收件人类型而异。</span><span class="sxs-lookup"><span data-stu-id="7711c-125">The title varies depending on the type of recipient.</span></span> <span data-ttu-id="7711c-126">_lpszNewEntryTitle_ 参数可以是 NULL。</span><span class="sxs-lookup"><span data-stu-id="7711c-126">The  _lpszNewEntryTitle_ parameter can be NULL.</span></span> 
    
 <span data-ttu-id="7711c-127">_lpAdrList_</span><span class="sxs-lookup"><span data-stu-id="7711c-127">_lpAdrList_</span></span>
  
> <span data-ttu-id="7711c-128">[in-out]指向包含要解析的收件人姓名列表的 [ADRLIST](adrlist.md) 结构的指针。</span><span class="sxs-lookup"><span data-stu-id="7711c-128">[in-out] A pointer to an [ADRLIST](adrlist.md) structure that contains the list of recipient names to be resolved.</span></span> <span data-ttu-id="7711c-129">此 **ADRLIST** 结构可通过 [IAddrBook：：Address 方法](iaddrbook-address.md) 创建。</span><span class="sxs-lookup"><span data-stu-id="7711c-129">This **ADRLIST** structure can be created by the [IAddrBook::Address](iaddrbook-address.md) method.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="7711c-130">返回值</span><span class="sxs-lookup"><span data-stu-id="7711c-130">Return value</span></span>

<span data-ttu-id="7711c-131">S_OK</span><span class="sxs-lookup"><span data-stu-id="7711c-131">S_OK</span></span> 
  
> <span data-ttu-id="7711c-132">名称解析过程成功。</span><span class="sxs-lookup"><span data-stu-id="7711c-132">The name resolution process succeeded.</span></span>
    
<span data-ttu-id="7711c-133">MAPI_E_AMBIGUOUS_RECIP</span><span class="sxs-lookup"><span data-stu-id="7711c-133">MAPI_E_AMBIGUOUS_RECIP</span></span> 
  
> <span data-ttu-id="7711c-134">_lpAdrList_ 参数中至少有一个收件人与通讯簿中的多个条目匹配。</span><span class="sxs-lookup"><span data-stu-id="7711c-134">At least one recipient in the  _lpAdrList_ parameter matched more than one entry in the address book.</span></span> <span data-ttu-id="7711c-135">通常，此值在设置 MAPI_DIALOG 标志时返回，禁止显示对话框。</span><span class="sxs-lookup"><span data-stu-id="7711c-135">Usually, this value is returned when the MAPI_DIALOG flag is set, prohibiting the display of a dialog box.</span></span> 
    
<span data-ttu-id="7711c-136">MAPI_E_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="7711c-136">MAPI_E_NOT_FOUND</span></span> 
  
> <span data-ttu-id="7711c-137">_lpAdrList_ 参数中至少有一个收件人无法解析。</span><span class="sxs-lookup"><span data-stu-id="7711c-137">At least one recipient in the  _lpAdrList_ parameter cannot be resolved.</span></span> <span data-ttu-id="7711c-138">通常，此值在设置 MAPI_DIALOG 标志时返回，禁止显示对话框。</span><span class="sxs-lookup"><span data-stu-id="7711c-138">Usually, this value is returned when the MAPI_DIALOG flag is set, prohibiting the display of a dialog box.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="7711c-139">备注</span><span class="sxs-lookup"><span data-stu-id="7711c-139">Remarks</span></span>

<span data-ttu-id="7711c-140">客户端和服务提供商调用 **ResolveName** 方法以启动名称解析过程。</span><span class="sxs-lookup"><span data-stu-id="7711c-140">Clients and service providers call the **ResolveName** method to initiate the name resolution process.</span></span> <span data-ttu-id="7711c-141">未解析的条目是尚没有条目标识符或PR_ENTRYID ([PidTagEntryId](pidtagentryid-canonical-property.md)) 条目。 </span><span class="sxs-lookup"><span data-stu-id="7711c-141">An unresolved entry is an entry that does not yet have an entry identifier or **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) property.</span></span>
  
 <span data-ttu-id="7711c-142">**ResolveName** 将针对在  _lpAdrList_ 参数中传递的地址列表中的每个未解析条目执行以下过程。</span><span class="sxs-lookup"><span data-stu-id="7711c-142">**ResolveName** goes through the following process for each unresolved entry in the address list passed in the  _lpAdrList_ parameter.</span></span> 
  
1. <span data-ttu-id="7711c-143">如果收件人的地址类型符合 SMTP 地址 ( _displayname_ @  _domain.top-level-domain_) 的格式 **，ResolveName** 会为其分配一次条目标识符。</span><span class="sxs-lookup"><span data-stu-id="7711c-143">If the address type of the recipient adheres to the format of an SMTP address ( _displayname_@ _domain.top-level-domain_), **ResolveName** assigns it a one-off entry identifier.</span></span> 
    
2. <span data-ttu-id="7711c-144">对于 [PidTagAbSearchPath](pidtagabsearchpath-canonical-property.md) PR_AB_SEARCH_PATH (的每个容器 **，ResolveName**) [IABContainer：：ResolveNames](iabcontainer-resolvenames.md)方法。 </span><span class="sxs-lookup"><span data-stu-id="7711c-144">For each container in the **PR_AB_SEARCH_PATH** ([PidTagAbSearchPath](pidtagabsearchpath-canonical-property.md)) property, **ResolveName** calls the [IABContainer::ResolveNames](iabcontainer-resolvenames.md) method.</span></span> <span data-ttu-id="7711c-145">**ResolveNames** 尝试将每个未显示名称收件人的收件人与属于显示名称条目之一的收件人匹配。</span><span class="sxs-lookup"><span data-stu-id="7711c-145">**ResolveNames** tries to match the display name of each unresolved recipient with a display name that belongs to one of its entries.</span></span> 
    
3. <span data-ttu-id="7711c-146">如果容器不支持 **ResolveNames，ResolveName** 将通过使用 PR_ANR ([PidTagAnr](pidtaganr-canonical-property.md) ) 限制来限制容器的内容表。 </span><span class="sxs-lookup"><span data-stu-id="7711c-146">If a container does not support **ResolveNames**, **ResolveName** restricts the container's contents table by using a **PR_ANR** ([PidTagAnr](pidtaganr-canonical-property.md)) property restriction.</span></span> <span data-ttu-id="7711c-147">此限制会导致容器执行"最佳猜测"类型的搜索以查找匹配的收件人。</span><span class="sxs-lookup"><span data-stu-id="7711c-147">This restriction causes the container to perform a "best guess" type of search to locate a matching recipient.</span></span> <span data-ttu-id="7711c-148">所有容器 **都必须支持PR_ANR** 限制。</span><span class="sxs-lookup"><span data-stu-id="7711c-148">All containers must support the **PR_ANR** property restriction.</span></span> 
    
4. <span data-ttu-id="7711c-149">当容器返回与多个名称匹配的收件人时，如果设置了 MAPI_DIALOG 标志 **，ResolveName** 将显示一个对话框，允许用户选择正确的名称。</span><span class="sxs-lookup"><span data-stu-id="7711c-149">When a container returns a recipient that matches multiple names, **ResolveName** displays a dialog box if the MAPI_DIALOG flag is set, which lets the user select the correct name.</span></span> 
    
5. <span data-ttu-id="7711c-150">如果已调用 PR_AB_SEARCH_PATH **所有容器** ，并且未找到匹配项，则收件人将保持未解析。</span><span class="sxs-lookup"><span data-stu-id="7711c-150">If all of the containers in the **PR_AB_SEARCH_PATH** property have been called and no match has been found, the recipient remains unresolved.</span></span> 
    
<span data-ttu-id="7711c-151">如果一个或多个收件人未解析 **，ResolveName** 将返回MAPI_E_NOT_FOUND。</span><span class="sxs-lookup"><span data-stu-id="7711c-151">If one or more recipients are unresolved, **ResolveName** returns MAPI_E_NOT_FOUND.</span></span> <span data-ttu-id="7711c-152">如果一个或多个收件人具有无法通过对话框解析的不明确解析，或者由于未设置 MAPI_DIALOG 标志 **，ResolveName** 将返回 MAPI_E_AMBIGUOUS_RECIP。</span><span class="sxs-lookup"><span data-stu-id="7711c-152">If one or more recipients had ambiguous resolution that could not be resolved with a dialog box, or because the MAPI_DIALOG flag was not set, **ResolveName** returns MAPI_E_AMBIGUOUS_RECIP.</span></span> <span data-ttu-id="7711c-153">当某些收件人不明确且某些收件人无法解析时 **，ResolveName** 可能会返回任一错误值。</span><span class="sxs-lookup"><span data-stu-id="7711c-153">When some of the recipients are ambiguous and some cannot be resolved, **ResolveName** can return either error value.</span></span> 
  
<span data-ttu-id="7711c-154">如果无法解析名称，客户端可以创建具有特殊格式的地址和条目标识符的一次使用地址。</span><span class="sxs-lookup"><span data-stu-id="7711c-154">If a name cannot be resolved, the client can create a one-off address that has a specially formatted address and entry identifier.</span></span> <span data-ttu-id="7711c-155">有关一次输入标识符格式的信息，请参阅 [一次使用条目标识符](one-off-entry-identifiers.md)。</span><span class="sxs-lookup"><span data-stu-id="7711c-155">For more information about the format of one-off entry identifiers, see [One-Off Entry Identifiers](one-off-entry-identifiers.md).</span></span> <span data-ttu-id="7711c-156">有关一次使用地址格式的信息，请参阅 [一次使用地址](one-off-addresses.md)。</span><span class="sxs-lookup"><span data-stu-id="7711c-156">For more information about the format of one-off addresses, see [One-Off Addresses](one-off-addresses.md).</span></span>
  
<span data-ttu-id="7711c-157">MAPI 支持 **ADRLIST** 的 Unicode 字符字符串和 **ResolveName** 的新条目标题参数;如果设置 MAPI_UNICODE 标志，则以下属性作为 [ADRENTRY](adrentry.md) PT_UNICODE类型返回：</span><span class="sxs-lookup"><span data-stu-id="7711c-157">MAPI supports Unicode character strings for the **ADRLIST** and the new entry title parameters to **ResolveName**; if you set the MAPI_UNICODE flag, the following properties are returned as type PT_UNICODE in the [ADRENTRY](adrentry.md) structures:</span></span> 
  
- <span data-ttu-id="7711c-158">**PR_ADDRTYPE (** [PidTagAddressType](pidtagaddresstype-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="7711c-158">**PR_ADDRTYPE** ([PidTagAddressType](pidtagaddresstype-canonical-property.md))</span></span>
    
- <span data-ttu-id="7711c-159">**PR_DISPLAY_NAME (** [PidTagDisplayName](pidtagdisplayname-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="7711c-159">**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md))</span></span>
    
- <span data-ttu-id="7711c-160">**PR_EMAIL_ADDRESS (** [PidTagEmailAddress)](pidtagemailaddress-canonical-property.md)</span><span class="sxs-lookup"><span data-stu-id="7711c-160">**PR_EMAIL_ADDRESS** ([PidTagEmailAddress](pidtagemailaddress-canonical-property.md))</span></span>
    
- <span data-ttu-id="7711c-161">**PR_TRANSMITABLE_DISPLAY_NAME (** [PidTagTransmittableDisplayName](pidtagtransmittabledisplayname-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="7711c-161">**PR_TRANSMITABLE_DISPLAY_NAME** ([PidTagTransmittableDisplayName](pidtagtransmittabledisplayname-canonical-property.md))</span></span>
    
<span data-ttu-id="7711c-162">但是 **，PR_7BIT_DISPLAY_NAME (** [PidTag7BitDisplayName](pidtag7bitdisplayname-canonical-property.md)) 属性始终作为类型PT_STRING8。</span><span class="sxs-lookup"><span data-stu-id="7711c-162">However, the **PR_7BIT_DISPLAY_NAME** ([PidTag7BitDisplayName](pidtag7bitdisplayname-canonical-property.md)) property is always returned as type PT_STRING8.</span></span>
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="7711c-163">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="7711c-163">MFCMAPI reference</span></span>

<span data-ttu-id="7711c-164">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="7711c-164">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="7711c-165">**文件**</span><span class="sxs-lookup"><span data-stu-id="7711c-165">**File**</span></span>|<span data-ttu-id="7711c-166">**函数**</span><span class="sxs-lookup"><span data-stu-id="7711c-166">**Function**</span></span>|<span data-ttu-id="7711c-167">**备注**</span><span class="sxs-lookup"><span data-stu-id="7711c-167">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="7711c-168">MAPIABFunctions.cpp</span><span class="sxs-lookup"><span data-stu-id="7711c-168">MAPIABFunctions.cpp</span></span>  <br/> |<span data-ttu-id="7711c-169">AddOneOffAddress</span><span class="sxs-lookup"><span data-stu-id="7711c-169">AddOneOffAddress</span></span>  <br/> |<span data-ttu-id="7711c-170">MFCMAPI 在将地址添加到邮件之前，使用 **ResolveName** 方法解析该地址。</span><span class="sxs-lookup"><span data-stu-id="7711c-170">MFCMAPI uses the **ResolveName** method to resolve a one-off address before adding it to a message.</span></span>  <br/> |
|<span data-ttu-id="7711c-171">MAPIABFunctions.cpp</span><span class="sxs-lookup"><span data-stu-id="7711c-171">MAPIABFunctions.cpp</span></span>  <br/> |<span data-ttu-id="7711c-172">AddRecipient</span><span class="sxs-lookup"><span data-stu-id="7711c-172">AddRecipient</span></span>  <br/> |<span data-ttu-id="7711c-173">MFCMAPI 使用 **ResolveName** 方法来查找通讯簿条目，显示名称。</span><span class="sxs-lookup"><span data-stu-id="7711c-173">MFCMAPI uses the **ResolveName** method to look up an address book entry by display name.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="7711c-174">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7711c-174">See also</span></span>



[<span data-ttu-id="7711c-175">ADRLIST</span><span class="sxs-lookup"><span data-stu-id="7711c-175">ADRLIST</span></span>](adrlist.md)
  
[<span data-ttu-id="7711c-176">IABContainer::ResolveNames</span><span class="sxs-lookup"><span data-stu-id="7711c-176">IABContainer::ResolveNames</span></span>](iabcontainer-resolvenames.md)
  
[<span data-ttu-id="7711c-177">IAddrBook::Address</span><span class="sxs-lookup"><span data-stu-id="7711c-177">IAddrBook::Address</span></span>](iaddrbook-address.md)
  
[<span data-ttu-id="7711c-178">IAddrBook : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="7711c-178">IAddrBook : IMAPIProp</span></span>](iaddrbookimapiprop.md)


[<span data-ttu-id="7711c-179">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="7711c-179">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

