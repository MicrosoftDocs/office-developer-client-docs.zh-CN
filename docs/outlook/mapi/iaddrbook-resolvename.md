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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32287005"
---
# <a name="iaddrbookresolvename"></a><span data-ttu-id="9a5ab-103">IAddrBook::ResolveName</span><span class="sxs-lookup"><span data-stu-id="9a5ab-103">IAddrBook::ResolveName</span></span>

  
  
<span data-ttu-id="9a5ab-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="9a5ab-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="9a5ab-105">执行名称解析, 将条目标识符分配给收件人列表中的收件人。</span><span class="sxs-lookup"><span data-stu-id="9a5ab-105">Performs name resolution, assigning entry identifiers to recipients in a recipient list.</span></span>
  
```cpp
HRESULT ResolveName(
  ULONG_PTR ulUIParam,
  ULONG ulFlags,
  LPSTR lpszNewEntryTitle,
  LPADRLIST lpAdrList
);
```

## <a name="parameters"></a><span data-ttu-id="9a5ab-106">参数</span><span class="sxs-lookup"><span data-stu-id="9a5ab-106">Parameters</span></span>

 <span data-ttu-id="9a5ab-107">_ulUIParam_</span><span class="sxs-lookup"><span data-stu-id="9a5ab-107">_ulUIParam_</span></span>
  
> <span data-ttu-id="9a5ab-108">实时显示的对话框的父窗口的句柄 (如果指定), 以提示用户解决多义性问题。</span><span class="sxs-lookup"><span data-stu-id="9a5ab-108">[in] A handle to the parent window of a dialog box that is shown, if specified, to prompt the user to resolve ambiguity.</span></span>
    
 <span data-ttu-id="9a5ab-109">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="9a5ab-109">_ulFlags_</span></span>
  
> <span data-ttu-id="9a5ab-110">实时用于控制解决过程各个方面的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="9a5ab-110">[in] A bitmask of flags that control various aspects of the resolution process.</span></span> <span data-ttu-id="9a5ab-111">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="9a5ab-111">The following flags can be set:</span></span>
    
<span data-ttu-id="9a5ab-112">AB_UNICODEUI</span><span class="sxs-lookup"><span data-stu-id="9a5ab-112">AB_UNICODEUI</span></span>
  
> <span data-ttu-id="9a5ab-113">指示_lpszNewEntryTitle_是一个 UNICODE 字符串。</span><span class="sxs-lookup"><span data-stu-id="9a5ab-113">Indicates that  _lpszNewEntryTitle_ is a UNICODE string.</span></span> 
    
<span data-ttu-id="9a5ab-114">MAPI_CACHE_ONLY</span><span class="sxs-lookup"><span data-stu-id="9a5ab-114">MAPI_CACHE_ONLY</span></span>
  
> <span data-ttu-id="9a5ab-115">仅使用脱机通讯簿执行名称解析。</span><span class="sxs-lookup"><span data-stu-id="9a5ab-115">Use only the offline address book to perform name resolution.</span></span> <span data-ttu-id="9a5ab-116">例如, 可以使用此标志允许客户端应用程序在缓存 exchange 模式中打开全局地址列表 (GAL), 并从缓存中访问该通讯簿中的条目, 而无需在客户端和服务器之间创建流量。</span><span class="sxs-lookup"><span data-stu-id="9a5ab-116">For example, you can use this flag to allow a client application to open the global address list (GAL) in cached exchange mode and access an entry in that address book from the cache without creating traffic between the client and the server.</span></span> <span data-ttu-id="9a5ab-117">仅 Exchange 通讯簿提供程序支持此标志。</span><span class="sxs-lookup"><span data-stu-id="9a5ab-117">This flag is supported only by the Exchange Address Book Provider.</span></span>
    
<span data-ttu-id="9a5ab-118">MAPI_DIALOG</span><span class="sxs-lookup"><span data-stu-id="9a5ab-118">MAPI_DIALOG</span></span> 
  
> <span data-ttu-id="9a5ab-119">显示一个对话框, 提示用户输入其他名称解析信息。</span><span class="sxs-lookup"><span data-stu-id="9a5ab-119">Displays a dialog box to prompt the user for additional name resolution information.</span></span> <span data-ttu-id="9a5ab-120">如果未设置此标志, 则不会显示任何对话框。</span><span class="sxs-lookup"><span data-stu-id="9a5ab-120">If this flag is not set, no dialog box is displayed.</span></span> 
    
<span data-ttu-id="9a5ab-121">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="9a5ab-121">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="9a5ab-122">指示在地址列表中返回的属性的类型应为 PT_UNICODE 而不是 PT_STRING8。</span><span class="sxs-lookup"><span data-stu-id="9a5ab-122">Indicates that the properties returned in the address list should be of type PT_UNICODE instead of PT_STRING8.</span></span> 
    
 <span data-ttu-id="9a5ab-123">_lpszNewEntryTitle_</span><span class="sxs-lookup"><span data-stu-id="9a5ab-123">_lpszNewEntryTitle_</span></span>
  
> <span data-ttu-id="9a5ab-124">实时一个指针, 指向用于提示用户输入收件人的对话框中控件标题的文本。</span><span class="sxs-lookup"><span data-stu-id="9a5ab-124">[in] A pointer to text for the title of the control in the dialog box that prompts the user to enter a recipient.</span></span> <span data-ttu-id="9a5ab-125">标题根据收件人类型的不同而不同。</span><span class="sxs-lookup"><span data-stu-id="9a5ab-125">The title varies depending on the type of recipient.</span></span> <span data-ttu-id="9a5ab-126">_lpszNewEntryTitle_参数可以为 NULL。</span><span class="sxs-lookup"><span data-stu-id="9a5ab-126">The  _lpszNewEntryTitle_ parameter can be NULL.</span></span> 
    
 <span data-ttu-id="9a5ab-127">_lpAdrList_</span><span class="sxs-lookup"><span data-stu-id="9a5ab-127">_lpAdrList_</span></span>
  
> <span data-ttu-id="9a5ab-128">[输出]指向[ADRLIST](adrlist.md)结构的指针, 该结构包含要解析的收件人姓名的列表。</span><span class="sxs-lookup"><span data-stu-id="9a5ab-128">[in-out] A pointer to an [ADRLIST](adrlist.md) structure that contains the list of recipient names to be resolved.</span></span> <span data-ttu-id="9a5ab-129">此**ADRLIST**结构可通过[IAddrBook:: Address](iaddrbook-address.md)方法创建。</span><span class="sxs-lookup"><span data-stu-id="9a5ab-129">This **ADRLIST** structure can be created by the [IAddrBook::Address](iaddrbook-address.md) method.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="9a5ab-130">返回值</span><span class="sxs-lookup"><span data-stu-id="9a5ab-130">Return value</span></span>

<span data-ttu-id="9a5ab-131">S_OK</span><span class="sxs-lookup"><span data-stu-id="9a5ab-131">S_OK</span></span> 
  
> <span data-ttu-id="9a5ab-132">名称解析过程已成功。</span><span class="sxs-lookup"><span data-stu-id="9a5ab-132">The name resolution process succeeded.</span></span>
    
<span data-ttu-id="9a5ab-133">MAPI_E_AMBIGUOUS_RECIP</span><span class="sxs-lookup"><span data-stu-id="9a5ab-133">MAPI_E_AMBIGUOUS_RECIP</span></span> 
  
> <span data-ttu-id="9a5ab-134">_lpAdrList_参数中至少有一个收件人与通讯簿中的一个或多个条目匹配。</span><span class="sxs-lookup"><span data-stu-id="9a5ab-134">At least one recipient in the  _lpAdrList_ parameter matched more than one entry in the address book.</span></span> <span data-ttu-id="9a5ab-135">通常情况下, 在设置 MAPI_DIALOG 标志时, 将会返回此值, 禁止显示对话框。</span><span class="sxs-lookup"><span data-stu-id="9a5ab-135">Usually, this value is returned when the MAPI_DIALOG flag is set, prohibiting the display of a dialog box.</span></span> 
    
<span data-ttu-id="9a5ab-136">MAPI_E_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="9a5ab-136">MAPI_E_NOT_FOUND</span></span> 
  
> <span data-ttu-id="9a5ab-137">_lpAdrList_参数中至少有一个收件人无法解析。</span><span class="sxs-lookup"><span data-stu-id="9a5ab-137">At least one recipient in the  _lpAdrList_ parameter cannot be resolved.</span></span> <span data-ttu-id="9a5ab-138">通常情况下, 在设置 MAPI_DIALOG 标志时, 将会返回此值, 禁止显示对话框。</span><span class="sxs-lookup"><span data-stu-id="9a5ab-138">Usually, this value is returned when the MAPI_DIALOG flag is set, prohibiting the display of a dialog box.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="9a5ab-139">注解</span><span class="sxs-lookup"><span data-stu-id="9a5ab-139">Remarks</span></span>

<span data-ttu-id="9a5ab-140">客户端和服务提供程序调用**ResolveName**方法以启动名称解析过程。</span><span class="sxs-lookup"><span data-stu-id="9a5ab-140">Clients and service providers call the **ResolveName** method to initiate the name resolution process.</span></span> <span data-ttu-id="9a5ab-141">未解析的条目是尚不具有条目标识符或**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 属性的条目。</span><span class="sxs-lookup"><span data-stu-id="9a5ab-141">An unresolved entry is an entry that does not yet have an entry identifier or **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) property.</span></span>
  
 <span data-ttu-id="9a5ab-142">对于在_lpAdrList_参数中传递的地址列表中的每个未解析条目, **ResolveName**将完成以下过程。</span><span class="sxs-lookup"><span data-stu-id="9a5ab-142">**ResolveName** goes through the following process for each unresolved entry in the address list passed in the  _lpAdrList_ parameter.</span></span> 
  
1. <span data-ttu-id="9a5ab-143">如果收件人的地址类型遵循 SMTP 地址 ( _displayname_@ _domain_) 的格式, 则**ResolveName**将为其分配一次性条目标识符。</span><span class="sxs-lookup"><span data-stu-id="9a5ab-143">If the address type of the recipient adheres to the format of an SMTP address ( _displayname_@ _domain.top-level-domain_), **ResolveName** assigns it a one-off entry identifier.</span></span> 
    
2. <span data-ttu-id="9a5ab-144">对于**PR_AB_SEARCH_PATH** ([PidTagAbSearchPath](pidtagabsearchpath-canonical-property.md)) 属性中的每个容器, **ResolveName**调用[IABContainer:: ResolveNames](iabcontainer-resolvenames.md)方法。</span><span class="sxs-lookup"><span data-stu-id="9a5ab-144">For each container in the **PR_AB_SEARCH_PATH** ([PidTagAbSearchPath](pidtagabsearchpath-canonical-property.md)) property, **ResolveName** calls the [IABContainer::ResolveNames](iabcontainer-resolvenames.md) method.</span></span> <span data-ttu-id="9a5ab-145">**ResolveNames**尝试将每个未解析收件人的显示名称与其某个条目所属的显示名称进行匹配。</span><span class="sxs-lookup"><span data-stu-id="9a5ab-145">**ResolveNames** tries to match the display name of each unresolved recipient with a display name that belongs to one of its entries.</span></span> 
    
3. <span data-ttu-id="9a5ab-146">如果容器不支持**ResolveNames**, 则**ResolveName**使用**PR_ANR** ([PidTagAnr](pidtaganr-canonical-property.md)) 属性限制来限制容器的内容表。</span><span class="sxs-lookup"><span data-stu-id="9a5ab-146">If a container does not support **ResolveNames**, **ResolveName** restricts the container's contents table by using a **PR_ANR** ([PidTagAnr](pidtaganr-canonical-property.md)) property restriction.</span></span> <span data-ttu-id="9a5ab-147">此限制会导致容器执行 "最佳推测" 类型的搜索以查找匹配的收件人。</span><span class="sxs-lookup"><span data-stu-id="9a5ab-147">This restriction causes the container to perform a "best guess" type of search to locate a matching recipient.</span></span> <span data-ttu-id="9a5ab-148">所有容器都必须支持**PR_ANR**属性限制。</span><span class="sxs-lookup"><span data-stu-id="9a5ab-148">All containers must support the **PR_ANR** property restriction.</span></span> 
    
4. <span data-ttu-id="9a5ab-149">当容器返回与多个名称匹配的收件人时, 如果设置了 MAPI_DIALOG 标志, **ResolveName**将显示一个对话框, 允许用户选择正确的名称。</span><span class="sxs-lookup"><span data-stu-id="9a5ab-149">When a container returns a recipient that matches multiple names, **ResolveName** displays a dialog box if the MAPI_DIALOG flag is set, which lets the user select the correct name.</span></span> 
    
5. <span data-ttu-id="9a5ab-150">如果已调用**PR_AB_SEARCH_PATH**属性中的所有容器, 但未找到匹配项, 则不会保持收件人的解析。</span><span class="sxs-lookup"><span data-stu-id="9a5ab-150">If all of the containers in the **PR_AB_SEARCH_PATH** property have been called and no match has been found, the recipient remains unresolved.</span></span> 
    
<span data-ttu-id="9a5ab-151">如果一个或多个收件人未解析, **ResolveName**将返回 MAPI_E_NOT_FOUND。</span><span class="sxs-lookup"><span data-stu-id="9a5ab-151">If one or more recipients are unresolved, **ResolveName** returns MAPI_E_NOT_FOUND.</span></span> <span data-ttu-id="9a5ab-152">如果一个或多个收件人具有不明确的分辨率, 无法通过对话框进行解析, 或者因为未设置 MAPI_DIALOG 标志, 则**ResolveName**将返回 MAPI_E_AMBIGUOUS_RECIP。</span><span class="sxs-lookup"><span data-stu-id="9a5ab-152">If one or more recipients had ambiguous resolution that could not be resolved with a dialog box, or because the MAPI_DIALOG flag was not set, **ResolveName** returns MAPI_E_AMBIGUOUS_RECIP.</span></span> <span data-ttu-id="9a5ab-153">当某些收件人不明确且无法解析时, **ResolveName**可能会返回任一错误值。</span><span class="sxs-lookup"><span data-stu-id="9a5ab-153">When some of the recipients are ambiguous and some cannot be resolved, **ResolveName** can return either error value.</span></span> 
  
<span data-ttu-id="9a5ab-154">如果无法解析某个名称, 客户端可以创建一个具有特殊格式地址和条目标识符的一次性地址。</span><span class="sxs-lookup"><span data-stu-id="9a5ab-154">If a name cannot be resolved, the client can create a one-off address that has a specially formatted address and entry identifier.</span></span> <span data-ttu-id="9a5ab-155">有关一次性条目标识符的格式的详细信息, 请参阅[一次性条目标识符](one-off-entry-identifiers.md)。</span><span class="sxs-lookup"><span data-stu-id="9a5ab-155">For more information about the format of one-off entry identifiers, see [One-Off Entry Identifiers](one-off-entry-identifiers.md).</span></span> <span data-ttu-id="9a5ab-156">有关一次性地址的格式的详细信息, 请参阅[一次性地址](one-off-addresses.md)。</span><span class="sxs-lookup"><span data-stu-id="9a5ab-156">For more information about the format of one-off addresses, see [One-Off Addresses](one-off-addresses.md).</span></span>
  
<span data-ttu-id="9a5ab-157">MAPI 支持**ADRLIST**的 Unicode 字符字符串和**ResolveName**的新条目标题参数;如果设置了 MAPI_UNICODE 标志, 以下属性将作为[ADRENTRY](adrentry.md)结构中的类型 PT_UNICODE 返回:</span><span class="sxs-lookup"><span data-stu-id="9a5ab-157">MAPI supports Unicode character strings for the **ADRLIST** and the new entry title parameters to **ResolveName**; if you set the MAPI_UNICODE flag, the following properties are returned as type PT_UNICODE in the [ADRENTRY](adrentry.md) structures:</span></span> 
  
- <span data-ttu-id="9a5ab-158">**PR_ADDRTYPE**([PidTagAddressType](pidtagaddresstype-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="9a5ab-158">**PR_ADDRTYPE** ([PidTagAddressType](pidtagaddresstype-canonical-property.md))</span></span>
    
- <span data-ttu-id="9a5ab-159">**PR_DISPLAY_NAME**([PidTagDisplayName](pidtagdisplayname-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="9a5ab-159">**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md))</span></span>
    
- <span data-ttu-id="9a5ab-160">**PR_EMAIL_ADDRESS**([PidTagEmailAddress](pidtagemailaddress-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="9a5ab-160">**PR_EMAIL_ADDRESS** ([PidTagEmailAddress](pidtagemailaddress-canonical-property.md))</span></span>
    
- <span data-ttu-id="9a5ab-161">**PR_TRANSMITABLE_DISPLAY_NAME**([PidTagTransmittableDisplayName](pidtagtransmittabledisplayname-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="9a5ab-161">**PR_TRANSMITABLE_DISPLAY_NAME** ([PidTagTransmittableDisplayName](pidtagtransmittabledisplayname-canonical-property.md))</span></span>
    
<span data-ttu-id="9a5ab-162">但是, **PR_7BIT_DISPLAY_NAME** ([PidTag7BitDisplayName](pidtag7bitdisplayname-canonical-property.md)) 属性始终返回为类型 PT_STRING8。</span><span class="sxs-lookup"><span data-stu-id="9a5ab-162">However, the **PR_7BIT_DISPLAY_NAME** ([PidTag7BitDisplayName](pidtag7bitdisplayname-canonical-property.md)) property is always returned as type PT_STRING8.</span></span>
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="9a5ab-163">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="9a5ab-163">MFCMAPI reference</span></span>

<span data-ttu-id="9a5ab-164">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="9a5ab-164">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="9a5ab-165">**文件**</span><span class="sxs-lookup"><span data-stu-id="9a5ab-165">**File**</span></span>|<span data-ttu-id="9a5ab-166">**函数**</span><span class="sxs-lookup"><span data-stu-id="9a5ab-166">**Function**</span></span>|<span data-ttu-id="9a5ab-167">**备注**</span><span class="sxs-lookup"><span data-stu-id="9a5ab-167">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="9a5ab-168">MAPIABFunctions</span><span class="sxs-lookup"><span data-stu-id="9a5ab-168">MAPIABFunctions.cpp</span></span>  <br/> |<span data-ttu-id="9a5ab-169">AddOneOffAddress</span><span class="sxs-lookup"><span data-stu-id="9a5ab-169">AddOneOffAddress</span></span>  <br/> |<span data-ttu-id="9a5ab-170">MFCMAPI 使用**ResolveName**方法在将一个一次性地址添加到邮件之前对其进行解析。</span><span class="sxs-lookup"><span data-stu-id="9a5ab-170">MFCMAPI uses the **ResolveName** method to resolve a one-off address before adding it to a message.</span></span>  <br/> |
|<span data-ttu-id="9a5ab-171">MAPIABFunctions</span><span class="sxs-lookup"><span data-stu-id="9a5ab-171">MAPIABFunctions.cpp</span></span>  <br/> |<span data-ttu-id="9a5ab-172">AddRecipient</span><span class="sxs-lookup"><span data-stu-id="9a5ab-172">AddRecipient</span></span>  <br/> |<span data-ttu-id="9a5ab-173">MFCMAPI 使用**ResolveName**方法按显示名称查找通讯簿条目。</span><span class="sxs-lookup"><span data-stu-id="9a5ab-173">MFCMAPI uses the **ResolveName** method to look up an address book entry by display name.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="9a5ab-174">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9a5ab-174">See also</span></span>



[<span data-ttu-id="9a5ab-175">ADRLIST</span><span class="sxs-lookup"><span data-stu-id="9a5ab-175">ADRLIST</span></span>](adrlist.md)
  
[<span data-ttu-id="9a5ab-176">IABContainer::ResolveNames</span><span class="sxs-lookup"><span data-stu-id="9a5ab-176">IABContainer::ResolveNames</span></span>](iabcontainer-resolvenames.md)
  
[<span data-ttu-id="9a5ab-177">IAddrBook::Address</span><span class="sxs-lookup"><span data-stu-id="9a5ab-177">IAddrBook::Address</span></span>](iaddrbook-address.md)
  
[<span data-ttu-id="9a5ab-178">IAddrBook : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="9a5ab-178">IAddrBook : IMAPIProp</span></span>](iaddrbookimapiprop.md)


[<span data-ttu-id="9a5ab-179">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="9a5ab-179">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

