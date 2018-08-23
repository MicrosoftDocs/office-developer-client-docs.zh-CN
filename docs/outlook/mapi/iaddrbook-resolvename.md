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
ms.openlocfilehash: 1f09c88d9bd6720720e2d30ac24fa4a19aed5538
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22567228"
---
# <a name="iaddrbookresolvename"></a><span data-ttu-id="ea541-103">IAddrBook::ResolveName</span><span class="sxs-lookup"><span data-stu-id="ea541-103">IAddrBook::ResolveName</span></span>

  
  
<span data-ttu-id="ea541-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="ea541-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="ea541-105">执行名称解析，分配给收件人列表中的收件人的项标识符。</span><span class="sxs-lookup"><span data-stu-id="ea541-105">Performs name resolution, assigning entry identifiers to recipients in a recipient list.</span></span>
  
```cpp
HRESULT ResolveName(
  ULONG_PTR ulUIParam,
  ULONG ulFlags,
  LPSTR lpszNewEntryTitle,
  LPADRLIST lpAdrList
);
```

## <a name="parameters"></a><span data-ttu-id="ea541-106">参数</span><span class="sxs-lookup"><span data-stu-id="ea541-106">Parameters</span></span>

 <span data-ttu-id="ea541-107">_ulUIParam_</span><span class="sxs-lookup"><span data-stu-id="ea541-107">_ulUIParam_</span></span>
  
> <span data-ttu-id="ea541-108">[in]显示一个对话框的父窗口的句柄如果指定，以提示用户解决歧义。</span><span class="sxs-lookup"><span data-stu-id="ea541-108">[in] A handle to the parent window of a dialog box that is shown, if specified, to prompt the user to resolve ambiguity.</span></span>
    
 <span data-ttu-id="ea541-109">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="ea541-109">_ulFlags_</span></span>
  
> <span data-ttu-id="ea541-110">[in]控制决策过程的各个方面的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="ea541-110">[in] A bitmask of flags that control various aspects of the resolution process.</span></span> <span data-ttu-id="ea541-111">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="ea541-111">The following flags can be set:</span></span>
    
<span data-ttu-id="ea541-112">AB_UNICODEUI</span><span class="sxs-lookup"><span data-stu-id="ea541-112">AB_UNICODEUI</span></span>
  
> <span data-ttu-id="ea541-113">指示该_lpszNewEntryTitle_是 UNICODE 字符串。</span><span class="sxs-lookup"><span data-stu-id="ea541-113">Indicates that  _lpszNewEntryTitle_ is a UNICODE string.</span></span> 
    
<span data-ttu-id="ea541-114">MAPI_CACHE_ONLY</span><span class="sxs-lookup"><span data-stu-id="ea541-114">MAPI_CACHE_ONLY</span></span>
  
> <span data-ttu-id="ea541-115">使用仅脱机通讯簿执行名称解析。</span><span class="sxs-lookup"><span data-stu-id="ea541-115">Use only the offline address book to perform name resolution.</span></span> <span data-ttu-id="ea541-116">例如，您可以使用此标志以允许将客户端应用程序在缓存的 exchange 模式下打开全局地址列表 (GAL)，而不创建客户端和服务器之间的流量从缓存中访问该通讯簿中的条目。</span><span class="sxs-lookup"><span data-stu-id="ea541-116">For example, you can use this flag to allow a client application to open the global address list (GAL) in cached exchange mode and access an entry in that address book from the cache without creating traffic between the client and the server.</span></span> <span data-ttu-id="ea541-117">此标志仅受 Exchange 通讯簿提供程序支持。</span><span class="sxs-lookup"><span data-stu-id="ea541-117">This flag is supported only by the Exchange Address Book Provider.</span></span>
    
<span data-ttu-id="ea541-118">MAPI_DIALOG</span><span class="sxs-lookup"><span data-stu-id="ea541-118">MAPI_DIALOG</span></span> 
  
> <span data-ttu-id="ea541-119">显示一个对话框，提示用户输入其他名称解析信息。</span><span class="sxs-lookup"><span data-stu-id="ea541-119">Displays a dialog box to prompt the user for additional name resolution information.</span></span> <span data-ttu-id="ea541-120">如果未设置此标志，则不显示任何对话框。</span><span class="sxs-lookup"><span data-stu-id="ea541-120">If this flag is not set, no dialog box is displayed.</span></span> 
    
<span data-ttu-id="ea541-121">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="ea541-121">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="ea541-122">指示应类型而不是 PT_STRING8 PT_UNICODE 的地址列表中返回的属性。</span><span class="sxs-lookup"><span data-stu-id="ea541-122">Indicates that the properties returned in the address list should be of type PT_UNICODE instead of PT_STRING8.</span></span> 
    
 <span data-ttu-id="ea541-123">_lpszNewEntryTitle_</span><span class="sxs-lookup"><span data-stu-id="ea541-123">_lpszNewEntryTitle_</span></span>
  
> <span data-ttu-id="ea541-124">[in]一个指向提示用户输入收件人的对话框中的控件的标题文本。</span><span class="sxs-lookup"><span data-stu-id="ea541-124">[in] A pointer to text for the title of the control in the dialog box that prompts the user to enter a recipient.</span></span> <span data-ttu-id="ea541-125">标题根据收件人的类型而有所不同。</span><span class="sxs-lookup"><span data-stu-id="ea541-125">The title varies depending on the type of recipient.</span></span> <span data-ttu-id="ea541-126">_LpszNewEntryTitle_参数可以是 NULL。</span><span class="sxs-lookup"><span data-stu-id="ea541-126">The  _lpszNewEntryTitle_ parameter can be NULL.</span></span> 
    
 <span data-ttu-id="ea541-127">_lpAdrList_</span><span class="sxs-lookup"><span data-stu-id="ea541-127">_lpAdrList_</span></span>
  
> <span data-ttu-id="ea541-128">[out]一个指向[ADRLIST](adrlist.md)结构，其中包含要解析的收件人姓名的列表。</span><span class="sxs-lookup"><span data-stu-id="ea541-128">[in-out] A pointer to an [ADRLIST](adrlist.md) structure that contains the list of recipient names to be resolved.</span></span> <span data-ttu-id="ea541-129">可以通过[IAddrBook::Address](iaddrbook-address.md)方法创建该**ADRLIST**结构。</span><span class="sxs-lookup"><span data-stu-id="ea541-129">This **ADRLIST** structure can be created by the [IAddrBook::Address](iaddrbook-address.md) method.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="ea541-130">返回值</span><span class="sxs-lookup"><span data-stu-id="ea541-130">Return value</span></span>

<span data-ttu-id="ea541-131">S_OK</span><span class="sxs-lookup"><span data-stu-id="ea541-131">S_OK</span></span> 
  
> <span data-ttu-id="ea541-132">名称解析过程成功。</span><span class="sxs-lookup"><span data-stu-id="ea541-132">The name resolution process succeeded.</span></span>
    
<span data-ttu-id="ea541-133">MAPI_E_AMBIGUOUS_RECIP</span><span class="sxs-lookup"><span data-stu-id="ea541-133">MAPI_E_AMBIGUOUS_RECIP</span></span> 
  
> <span data-ttu-id="ea541-134">至少一个收件人的_lpAdrList_参数中匹配在通讯簿中的多个条目。</span><span class="sxs-lookup"><span data-stu-id="ea541-134">At least one recipient in the  _lpAdrList_ parameter matched more than one entry in the address book.</span></span> <span data-ttu-id="ea541-135">通常，当设置 MAPI_DIALOG 标志，禁止显示的对话框中，则返回此值。</span><span class="sxs-lookup"><span data-stu-id="ea541-135">Usually, this value is returned when the MAPI_DIALOG flag is set, prohibiting the display of a dialog box.</span></span> 
    
<span data-ttu-id="ea541-136">MAPI_E_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="ea541-136">MAPI_E_NOT_FOUND</span></span> 
  
> <span data-ttu-id="ea541-137">无法解析_lpAdrList_参数中的至少一个收件人。</span><span class="sxs-lookup"><span data-stu-id="ea541-137">At least one recipient in the  _lpAdrList_ parameter cannot be resolved.</span></span> <span data-ttu-id="ea541-138">通常，当设置 MAPI_DIALOG 标志，禁止显示的对话框中，则返回此值。</span><span class="sxs-lookup"><span data-stu-id="ea541-138">Usually, this value is returned when the MAPI_DIALOG flag is set, prohibiting the display of a dialog box.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="ea541-139">注解</span><span class="sxs-lookup"><span data-stu-id="ea541-139">Remarks</span></span>

<span data-ttu-id="ea541-140">客户端和服务提供商调用**ResolveName**方法以启动名称解析过程。</span><span class="sxs-lookup"><span data-stu-id="ea541-140">Clients and service providers call the **ResolveName** method to initiate the name resolution process.</span></span> <span data-ttu-id="ea541-141">未解析的项是尚不具有条目标识符或**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 属性的一个条目。</span><span class="sxs-lookup"><span data-stu-id="ea541-141">An unresolved entry is an entry that does not yet have an entry identifier or **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) property.</span></span>
  
 <span data-ttu-id="ea541-142">**ResolveName**经历_lpAdrList_参数中传递的地址列表中每个未解析项的以下过程。</span><span class="sxs-lookup"><span data-stu-id="ea541-142">**ResolveName** goes through the following process for each unresolved entry in the address list passed in the  _lpAdrList_ parameter.</span></span> 
  
1. <span data-ttu-id="ea541-143">如果收件人的地址类型符合 SMTP 地址的格式 ( _displayname_@ _domain.top 级别域_)， **ResolveName**将其分配一个一次性条目标识符。</span><span class="sxs-lookup"><span data-stu-id="ea541-143">If the address type of the recipient adheres to the format of an SMTP address ( _displayname_@ _domain.top-level-domain_), **ResolveName** assigns it a one-off entry identifier.</span></span> 
    
2. <span data-ttu-id="ea541-144">对于每个容器中的**PR_AB_SEARCH_PATH** ([PidTagAbSearchPath](pidtagabsearchpath-canonical-property.md)) 属性， **ResolveName**调用[IABContainer::ResolveNames](iabcontainer-resolvenames.md)方法。</span><span class="sxs-lookup"><span data-stu-id="ea541-144">For each container in the **PR_AB_SEARCH_PATH** ([PidTagAbSearchPath](pidtagabsearchpath-canonical-property.md)) property, **ResolveName** calls the [IABContainer::ResolveNames](iabcontainer-resolvenames.md) method.</span></span> <span data-ttu-id="ea541-145">**ResolveNames**尝试匹配属于其项之一的显示名称与每个未解析的收件人的显示名称。</span><span class="sxs-lookup"><span data-stu-id="ea541-145">**ResolveNames** tries to match the display name of each unresolved recipient with a display name that belongs to one of its entries.</span></span> 
    
3. <span data-ttu-id="ea541-146">如果容器不支持**ResolveNames**， **ResolveName**将限制使用**PR_ANR** ([PidTagAnr](pidtaganr-canonical-property.md)) 属性限制的容器的内容表。</span><span class="sxs-lookup"><span data-stu-id="ea541-146">If a container does not support **ResolveNames**, **ResolveName** restricts the container's contents table by using a **PR_ANR** ([PidTagAnr](pidtaganr-canonical-property.md)) property restriction.</span></span> <span data-ttu-id="ea541-147">此限制将会导致容器来执行"最佳猜测"搜索来查找匹配的收件人类型。</span><span class="sxs-lookup"><span data-stu-id="ea541-147">This restriction causes the container to perform a "best guess" type of search to locate a matching recipient.</span></span> <span data-ttu-id="ea541-148">所有容器都必须都支持**PR_ANR**属性限制。</span><span class="sxs-lookup"><span data-stu-id="ea541-148">All containers must support the **PR_ANR** property restriction.</span></span> 
    
4. <span data-ttu-id="ea541-149">当容器返回与多个名称相匹配的收件人时， **ResolveName**将显示一个对话框，如果设置 MAPI_DIALOG 标志是，它允许用户选择正确的名称。</span><span class="sxs-lookup"><span data-stu-id="ea541-149">When a container returns a recipient that matches multiple names, **ResolveName** displays a dialog box if the MAPI_DIALOG flag is set, which lets the user select the correct name.</span></span> 
    
5. <span data-ttu-id="ea541-150">如果调用了所有**PR_AB_SEARCH_PATH**属性中的容器，并且已找到不匹配，仍无法解析收件人。</span><span class="sxs-lookup"><span data-stu-id="ea541-150">If all of the containers in the **PR_AB_SEARCH_PATH** property have been called and no match has been found, the recipient remains unresolved.</span></span> 
    
<span data-ttu-id="ea541-151">如果一个或多个收件人无法解析， **ResolveName**返回 MAPI_E_NOT_FOUND。</span><span class="sxs-lookup"><span data-stu-id="ea541-151">If one or more recipients are unresolved, **ResolveName** returns MAPI_E_NOT_FOUND.</span></span> <span data-ttu-id="ea541-152">如果一个或多个收件人具有与对话框中，无法解析的不明确解决方案或由于未设置 MAPI_DIALOG 标志， **ResolveName**返回 MAPI_E_AMBIGUOUS_RECIP。</span><span class="sxs-lookup"><span data-stu-id="ea541-152">If one or more recipients had ambiguous resolution that could not be resolved with a dialog box, or because the MAPI_DIALOG flag was not set, **ResolveName** returns MAPI_E_AMBIGUOUS_RECIP.</span></span> <span data-ttu-id="ea541-153">当某些收件人不明确而无法解析一些时， **ResolveName**可以返回其中任何一个错误值。</span><span class="sxs-lookup"><span data-stu-id="ea541-153">When some of the recipients are ambiguous and some cannot be resolved, **ResolveName** can return either error value.</span></span> 
  
<span data-ttu-id="ea541-154">如果无法解析名称，客户端可以创建具有特殊格式的地址以及条目标识符一次性地址。</span><span class="sxs-lookup"><span data-stu-id="ea541-154">If a name cannot be resolved, the client can create a one-off address that has a specially formatted address and entry identifier.</span></span> <span data-ttu-id="ea541-155">一次性条目标识符的格式的详细信息，请参阅[一次性条目标识符](one-off-entry-identifiers.md)。</span><span class="sxs-lookup"><span data-stu-id="ea541-155">For more information about the format of one-off entry identifiers, see [One-Off Entry Identifiers](one-off-entry-identifiers.md).</span></span> <span data-ttu-id="ea541-156">一次性地址的格式的详细信息，请参阅[一次性地址](one-off-addresses.md)。</span><span class="sxs-lookup"><span data-stu-id="ea541-156">For more information about the format of one-off addresses, see [One-Off Addresses](one-off-addresses.md).</span></span>
  
<span data-ttu-id="ea541-157">MAPI **ADRLIST**和**ResolveName**; 的新条目标题参数中支持 Unicode 字符串如果设置 MAPI_UNICODE 标志，作为类型 PT_UNICODE [ADRENTRY](adrentry.md)结构中会返回以下属性：</span><span class="sxs-lookup"><span data-stu-id="ea541-157">MAPI supports Unicode character strings for the **ADRLIST** and the new entry title parameters to **ResolveName**; if you set the MAPI_UNICODE flag, the following properties are returned as type PT_UNICODE in the [ADRENTRY](adrentry.md) structures:</span></span> 
  
- <span data-ttu-id="ea541-158">**PR_ADDRTYPE**([PidTagAddressType](pidtagaddresstype-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="ea541-158">**PR_ADDRTYPE** ([PidTagAddressType](pidtagaddresstype-canonical-property.md))</span></span>
    
- <span data-ttu-id="ea541-159">**PR_DISPLAY_NAME**([PidTagDisplayName](pidtagdisplayname-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="ea541-159">**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md))</span></span>
    
- <span data-ttu-id="ea541-160">**PR_EMAIL_ADDRESS**([PidTagEmailAddress](pidtagemailaddress-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="ea541-160">**PR_EMAIL_ADDRESS** ([PidTagEmailAddress](pidtagemailaddress-canonical-property.md))</span></span>
    
- <span data-ttu-id="ea541-161">**PR_TRANSMITABLE_DISPLAY_NAME**([PidTagTransmittableDisplayName](pidtagtransmittabledisplayname-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="ea541-161">**PR_TRANSMITABLE_DISPLAY_NAME** ([PidTagTransmittableDisplayName](pidtagtransmittabledisplayname-canonical-property.md))</span></span>
    
<span data-ttu-id="ea541-162">但是， **PR_7BIT_DISPLAY_NAME** ([PidTag7BitDisplayName](pidtag7bitdisplayname-canonical-property.md)) 属性始终返回键入 PT_STRING8。</span><span class="sxs-lookup"><span data-stu-id="ea541-162">However, the **PR_7BIT_DISPLAY_NAME** ([PidTag7BitDisplayName](pidtag7bitdisplayname-canonical-property.md)) property is always returned as type PT_STRING8.</span></span>
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="ea541-163">MFCMAPI 参考 （英文）</span><span class="sxs-lookup"><span data-stu-id="ea541-163">MFCMAPI reference</span></span>

<span data-ttu-id="ea541-164">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="ea541-164">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="ea541-165">**文件**</span><span class="sxs-lookup"><span data-stu-id="ea541-165">**File**</span></span>|<span data-ttu-id="ea541-166">**函数**</span><span class="sxs-lookup"><span data-stu-id="ea541-166">**Function**</span></span>|<span data-ttu-id="ea541-167">**Comment**</span><span class="sxs-lookup"><span data-stu-id="ea541-167">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ea541-168">MAPIABFunctions.cpp</span><span class="sxs-lookup"><span data-stu-id="ea541-168">MAPIABFunctions.cpp</span></span>  <br/> |<span data-ttu-id="ea541-169">AddOneOffAddress</span><span class="sxs-lookup"><span data-stu-id="ea541-169">AddOneOffAddress</span></span>  <br/> |<span data-ttu-id="ea541-170">MFCMAPI 使用**ResolveName**方法来解析一次性地址之前将其添加到一条消息。</span><span class="sxs-lookup"><span data-stu-id="ea541-170">MFCMAPI uses the **ResolveName** method to resolve a one-off address before adding it to a message.</span></span>  <br/> |
|<span data-ttu-id="ea541-171">MAPIABFunctions.cpp</span><span class="sxs-lookup"><span data-stu-id="ea541-171">MAPIABFunctions.cpp</span></span>  <br/> |<span data-ttu-id="ea541-172">AddRecipient</span><span class="sxs-lookup"><span data-stu-id="ea541-172">AddRecipient</span></span>  <br/> |<span data-ttu-id="ea541-173">MFCMAPI 使用**ResolveName**方法查找按显示名称的通讯簿条目。</span><span class="sxs-lookup"><span data-stu-id="ea541-173">MFCMAPI uses the **ResolveName** method to look up an address book entry by display name.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="ea541-174">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ea541-174">See also</span></span>



[<span data-ttu-id="ea541-175">ADRLIST</span><span class="sxs-lookup"><span data-stu-id="ea541-175">ADRLIST</span></span>](adrlist.md)
  
[<span data-ttu-id="ea541-176">IABContainer::ResolveNames</span><span class="sxs-lookup"><span data-stu-id="ea541-176">IABContainer::ResolveNames</span></span>](iabcontainer-resolvenames.md)
  
[<span data-ttu-id="ea541-177">IAddrBook::Address</span><span class="sxs-lookup"><span data-stu-id="ea541-177">IAddrBook::Address</span></span>](iaddrbook-address.md)
  
[<span data-ttu-id="ea541-178">IAddrBook : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="ea541-178">IAddrBook : IMAPIProp</span></span>](iaddrbookimapiprop.md)


[<span data-ttu-id="ea541-179">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="ea541-179">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

