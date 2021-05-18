---
title: IABContainerResolveNames
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IABContainer.ResolveNames
api_type:
- COM
ms.assetid: 27474af2-29a2-4cfb-b94f-72eb91562dac
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: fac4978bef94650f85ac3179acd3858602f933ec
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33405812"
---
# <a name="iabcontainerresolvenames"></a><span data-ttu-id="560aa-103">IABContainer::ResolveNames</span><span class="sxs-lookup"><span data-stu-id="560aa-103">IABContainer::ResolveNames</span></span>

  
  
<span data-ttu-id="560aa-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="560aa-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="560aa-105">对一个或多个收件人条目执行名称解析。</span><span class="sxs-lookup"><span data-stu-id="560aa-105">Performs name resolution for one or more recipient entries.</span></span>
  
```cpp
HRESULT ResolveNames(
  LPSPropTagArray lpPropTagArray,
  ULONG ulFlags,
  LPADRLIST lpAdrList,
  LPFlagList lpFlagList
);
```

## <a name="parameters"></a><span data-ttu-id="560aa-106">参数</span><span class="sxs-lookup"><span data-stu-id="560aa-106">Parameters</span></span>

 <span data-ttu-id="560aa-107">_lpPropTagArray_</span><span class="sxs-lookup"><span data-stu-id="560aa-107">_lpPropTagArray_</span></span>
  
> <span data-ttu-id="560aa-108">[in]指向 [SPropTagArray](sproptagarray.md) 结构的指针，该结构包含一组属性标记，用于描述提供程序返回 [的 ADRLIST](adrlist.md) 结构中包含的属性。</span><span class="sxs-lookup"><span data-stu-id="560aa-108">[in] A pointer to an [SPropTagArray](sproptagarray.md) structure that contains an array of property tags describing the properties to be included in the [ADRLIST](adrlist.md) structure returned by the provider.</span></span> <span data-ttu-id="560aa-109">若要请求提供程序的默认属性集，请传递  _lpPropTagArray_ 参数中的 NULL。</span><span class="sxs-lookup"><span data-stu-id="560aa-109">To request the provider's default set of properties, pass NULL in the  _lpPropTagArray_ parameter.</span></span> 
    
 <span data-ttu-id="560aa-110">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="560aa-110">_ulFlags_</span></span>
  
> <span data-ttu-id="560aa-111">[in]控制返回的字符串中的文本类型的标志位掩码。</span><span class="sxs-lookup"><span data-stu-id="560aa-111">[in] A bitmask of flags that controls the type of the text in the returned strings.</span></span> <span data-ttu-id="560aa-112">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="560aa-112">The following flags can be set:</span></span>
    
<span data-ttu-id="560aa-113">EMS_AB_ADDRESS_LOOKUP</span><span class="sxs-lookup"><span data-stu-id="560aa-113">EMS_AB_ADDRESS_LOOKUP</span></span>
  
> <span data-ttu-id="560aa-114">将仅找到确切的代理地址匹配项;部分匹配将被忽略。</span><span class="sxs-lookup"><span data-stu-id="560aa-114">Only exact proxy address matches will be found; partial matches are ignored.</span></span> <span data-ttu-id="560aa-115">此标志仅受通讯簿Exchange支持。</span><span class="sxs-lookup"><span data-stu-id="560aa-115">This flag is supported only by the Exchange Address Book Provider.</span></span>
    
<span data-ttu-id="560aa-116">MAPI_CACHE_ONLY</span><span class="sxs-lookup"><span data-stu-id="560aa-116">MAPI_CACHE_ONLY</span></span>
  
> <span data-ttu-id="560aa-117">只有脱机通讯簿将用于执行名称解析。</span><span class="sxs-lookup"><span data-stu-id="560aa-117">Only the offline address book will be used to perform name resolution.</span></span> <span data-ttu-id="560aa-118">例如，您可以使用此标志使客户端应用程序在缓存 exchange 模式下打开全局地址列表 (GAL) ，并访问缓存中的该通讯簿中的条目，而无需在客户端和服务器之间创建流量。</span><span class="sxs-lookup"><span data-stu-id="560aa-118">For example, you can use this flag to enable a client application to open the global address list (GAL) in cached exchange mode and access an entry in that address book from the cache without creating traffic between the client and the server.</span></span> <span data-ttu-id="560aa-119">此标志仅受通讯簿Exchange支持。</span><span class="sxs-lookup"><span data-stu-id="560aa-119">This flag is supported only by the Exchange Address Book Provider.</span></span> 
    
<span data-ttu-id="560aa-120">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="560aa-120">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="560aa-121">返回的字符串属性采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="560aa-121">The returned string properties are in Unicode format.</span></span> <span data-ttu-id="560aa-122">如果未MAPI_UNICODE，则字符串采用 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="560aa-122">If the MAPI_UNICODE flag is not set, the strings are in ANSI format.</span></span>
    
 <span data-ttu-id="560aa-123">_lpAdrList_</span><span class="sxs-lookup"><span data-stu-id="560aa-123">_lpAdrList_</span></span>
  
> <span data-ttu-id="560aa-124">[in， out]输入时，指向包含要解析的收件人列表的 **ADRLIST** 结构的指针。</span><span class="sxs-lookup"><span data-stu-id="560aa-124">[in, out] On input, a pointer to an **ADRLIST** structure that contains the list of recipients to be resolved.</span></span> <span data-ttu-id="560aa-125">输出时，指向包含已解析名称 **的 ADRLIST** 结构的指针。</span><span class="sxs-lookup"><span data-stu-id="560aa-125">On output, a pointer to an **ADRLIST** structure that contains the resolved names.</span></span> 
    
 <span data-ttu-id="560aa-126">_lpFlagList_</span><span class="sxs-lookup"><span data-stu-id="560aa-126">_lpFlagList_</span></span>
  
> <span data-ttu-id="560aa-127">[in， out]指向标志数组的指针，每个标志对应于 _lpAdrList_ 参数中的 [ADRENTRY](adrentry.md)结构，该指针为收件人提供名称解析操作的状态。</span><span class="sxs-lookup"><span data-stu-id="560aa-127">[in, out] A pointer to an array of flags, each flag corresponding to an [ADRENTRY](adrentry.md) structure in the  _lpAdrList_ parameter, that provides the status of the name resolution operation for the recipient.</span></span> <span data-ttu-id="560aa-128">_lpFlagList_ 参数中的标志与 _lpAdrList_ 中的条目的顺序相同。</span><span class="sxs-lookup"><span data-stu-id="560aa-128">The flags in the  _lpFlagList_ parameter are in the same order as the entries in  _lpAdrList_.</span></span> <span data-ttu-id="560aa-129">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="560aa-129">The following flags can be set:</span></span>
    
<span data-ttu-id="560aa-130">MAPI_AMBIGUOUS</span><span class="sxs-lookup"><span data-stu-id="560aa-130">MAPI_AMBIGUOUS</span></span> 
  
> <span data-ttu-id="560aa-131">已解析相应的收件人，但没有解析为唯一条目标识符。</span><span class="sxs-lookup"><span data-stu-id="560aa-131">The corresponding recipient has been resolved, but not to a unique entry identifier.</span></span> <span data-ttu-id="560aa-132">其他容器不应尝试解析此收件人。</span><span class="sxs-lookup"><span data-stu-id="560aa-132">Other containers should not try to resolve this recipient.</span></span> 
    
<span data-ttu-id="560aa-133">MAPI_RESOLVED</span><span class="sxs-lookup"><span data-stu-id="560aa-133">MAPI_RESOLVED</span></span> 
  
> <span data-ttu-id="560aa-134">相应的收件人已解析为唯一条目标识符。</span><span class="sxs-lookup"><span data-stu-id="560aa-134">The corresponding recipient has been resolved to a unique entry identifier.</span></span> <span data-ttu-id="560aa-135">其他容器不应尝试解析此收件人。</span><span class="sxs-lookup"><span data-stu-id="560aa-135">Other containers should not try to resolve this recipient.</span></span> 
    
<span data-ttu-id="560aa-136">MAPI_UNRESOLVED</span><span class="sxs-lookup"><span data-stu-id="560aa-136">MAPI_UNRESOLVED</span></span> 
  
> <span data-ttu-id="560aa-137">尚未解析相应的条目。</span><span class="sxs-lookup"><span data-stu-id="560aa-137">The corresponding entry has not been resolved.</span></span> <span data-ttu-id="560aa-138">其他容器应尝试解析此收件人。</span><span class="sxs-lookup"><span data-stu-id="560aa-138">Other containers should try to resolve this recipient.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="560aa-139">返回值</span><span class="sxs-lookup"><span data-stu-id="560aa-139">Return value</span></span>

<span data-ttu-id="560aa-140">S_OK</span><span class="sxs-lookup"><span data-stu-id="560aa-140">S_OK</span></span> 
  
> <span data-ttu-id="560aa-141">名称解析过程已成功。</span><span class="sxs-lookup"><span data-stu-id="560aa-141">The name resolution process was successful.</span></span>
    
<span data-ttu-id="560aa-142">MAPI_E_BAD_CHARWIDTH</span><span class="sxs-lookup"><span data-stu-id="560aa-142">MAPI_E_BAD_CHARWIDTH</span></span> 
  
> <span data-ttu-id="560aa-143">设置 MAPI_UNICODE 标志，而实现不支持 Unicode，或者MAPI_UNICODE未设置，并且实现仅支持 Unicode。</span><span class="sxs-lookup"><span data-stu-id="560aa-143">Either the MAPI_UNICODE flag was set and the implementation does not support Unicode, or MAPI_UNICODE was not set and the implementation supports only Unicode.</span></span>
    
<span data-ttu-id="560aa-144">MAPI_E_NO_SUPPORT</span><span class="sxs-lookup"><span data-stu-id="560aa-144">MAPI_E_NO_SUPPORT</span></span> 
  
> <span data-ttu-id="560aa-145">通讯簿提供程序不支持使用此方法进行批量名称解析。</span><span class="sxs-lookup"><span data-stu-id="560aa-145">The address book provider does not support bulk name resolution by using this method.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="560aa-146">备注</span><span class="sxs-lookup"><span data-stu-id="560aa-146">Remarks</span></span>

<span data-ttu-id="560aa-147">**ResolveNames** 方法尝试将 _lpAdrList_ 参数中的条目数组中的未解析收件人匹配到此通讯簿容器中的收件人。</span><span class="sxs-lookup"><span data-stu-id="560aa-147">The **ResolveNames** method attempts to match unresolved recipients from the array of entries in the  _lpAdrList_ parameter to recipients in this address book container.</span></span> <span data-ttu-id="560aa-148">未解析的收件人通常仅具有 PR_DISPLAY_NAME  ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 属性和一些其他属性。</span><span class="sxs-lookup"><span data-stu-id="560aa-148">An unresolved recipient typically has only the **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) property and possibly a few other properties.</span></span> <span data-ttu-id="560aa-149">未解析的收件人没有 PR_ENTRYID  ([PidTagEntryId](pidtagentryid-canonical-property.md)) 属性，并且 _其 lpFlagList_ 参数中的相应标志设置为 MAPI_UNRESOLVED。</span><span class="sxs-lookup"><span data-stu-id="560aa-149">An unresolved recipient does not have the **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) property, and its corresponding flag in the  _lpFlagList_ parameter is set to MAPI_UNRESOLVED.</span></span> <span data-ttu-id="560aa-150">相反，解析的收件人始终至少具有 **PR_ENTRYID** 属性以及几个其他属性，如 **PR_EMAIL_ADDRESS** ([PidTagEmailAddress](pidtagemailaddress-canonical-property.md) **) 、PR_DISPLAY_NAME** 和 **PR_ADDRTYPE** ([PidTagAddressType](pidtagaddresstype-canonical-property.md)) 。</span><span class="sxs-lookup"><span data-stu-id="560aa-150">Conversely, a resolved recipient always has at least the **PR_ENTRYID** property plus several other properties such as **PR_EMAIL_ADDRESS** ([PidTagEmailAddress](pidtagemailaddress-canonical-property.md)), **PR_DISPLAY_NAME**, and **PR_ADDRTYPE** ([PidTagAddressType](pidtagaddresstype-canonical-property.md)).</span></span>
  
<span data-ttu-id="560aa-151">名称解析通常在客户端调用 [IAddrBook：：ResolveName](iaddrbook-resolvename.md) 方法时启动。</span><span class="sxs-lookup"><span data-stu-id="560aa-151">Name resolution typically starts when a client calls the [IAddrBook::ResolveName](iaddrbook-resolvename.md) method.</span></span> <span data-ttu-id="560aa-152">OutlookMAPI 通过调用通讯簿搜索路径中包含的每个通讯簿容器的 **ResolveNames** 方法进行响应，该路径由 **PR_AB_SEARCH_PATH** ([PidTagAbSearchPath](pidtagabsearchpath-canonical-property.md)) 属性指定。</span><span class="sxs-lookup"><span data-stu-id="560aa-152">Outlook MAPI responds by calling the **ResolveNames** method of each address book container included in the address book search path, specified by the **PR_AB_SEARCH_PATH** ([PidTagAbSearchPath](pidtagabsearchpath-canonical-property.md)) property.</span></span> <span data-ttu-id="560aa-153">_lpAdrList_ 参数中的条目包括已解析的收件人，因为它们在 MAPI 已调用 **ResolveNames** 的容器中，因为这些条目之前显示在搜索路径中。</span><span class="sxs-lookup"><span data-stu-id="560aa-153">The entries in the  _lpAdrList_ parameter include recipients already resolved because they are in containers for which MAPI has already called **ResolveNames**, because the entries appear earlier in the search path.</span></span> 
  
<span data-ttu-id="560aa-154">每个容器尝试解析未解析的条目，显示名称收件人的收件人地址与显示名称条目之一匹配。</span><span class="sxs-lookup"><span data-stu-id="560aa-154">Each container attempts to resolve the unresolved entries by matching the display name of the recipient with the display name of one of its entries.</span></span> <span data-ttu-id="560aa-155">当找到唯一匹配项时 **，ResolveNames** 会将 **PR_ENTRYID** 属性和  _lpPropTagArray_ 参数中包含的其他属性添加到传出 **ADRLIST** 结构中的相应条目。</span><span class="sxs-lookup"><span data-stu-id="560aa-155">When a unique match is found, **ResolveNames** adds the **PR_ENTRYID** property and other properties that are included in the  _lpPropTagArray_ parameter to the corresponding entry in the outgoing **ADRLIST** structure.</span></span> <span data-ttu-id="560aa-156">**然后 ResolveNames** 将  _lpFlagList_ 参数中的条目MAPI_RESOLVED。</span><span class="sxs-lookup"><span data-stu-id="560aa-156">**ResolveNames** then sets the entry in the  _lpFlagList_ parameter to MAPI_RESOLVED.</span></span> <span data-ttu-id="560aa-157">存储在 PR_ENTRYID **属性中的** 条目标识符可以是短期的或长期。</span><span class="sxs-lookup"><span data-stu-id="560aa-157">The entry identifier stored in the **PR_ENTRYID** property can be short-term or long-term.</span></span> 
  
<span data-ttu-id="560aa-158">在搜索路径中的所有容器尝试名称解析过程后，MAPI 将打开一个对话框（如果可能）以提示用户帮助解决任何剩余的冲突。</span><span class="sxs-lookup"><span data-stu-id="560aa-158">After all of the containers in the search path have attempted the name resolution process, MAPI opens a dialog box, if possible, to prompt the user for help in resolving any remaining conflicts.</span></span> 
  
<span data-ttu-id="560aa-159">客户端还可以在调用 [IMessage：：ModifyRecipients](imessage-modifyrecipients.md)方法时使用返回的 **ADRLIST** 结构。</span><span class="sxs-lookup"><span data-stu-id="560aa-159">Clients can also use the returned **ADRLIST** structure in calls to the [IMessage::ModifyRecipients](imessage-modifyrecipients.md) method.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="560aa-160">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="560aa-160">Notes to implementers</span></span>

<span data-ttu-id="560aa-161">无需使用 **ResolveNames** 方法支持名称解析。</span><span class="sxs-lookup"><span data-stu-id="560aa-161">You are not required to support name resolution with the **ResolveNames** method.</span></span> <span data-ttu-id="560aa-162">相反，或者另外，可以使用 PidTagAnr **PR_ANR (** [PidTagAnr](pidtaganr-canonical-property.md)) 支持它。</span><span class="sxs-lookup"><span data-stu-id="560aa-162">Instead, or additionally, you can support it with the **PR_ANR** ([PidTagAnr](pidtaganr-canonical-property.md)) property restriction.</span></span> <span data-ttu-id="560aa-163">如果您决定依赖于名称解析 **PR_ANR** 限制，可以返回MAPI_E_NO_SUPPORT。</span><span class="sxs-lookup"><span data-stu-id="560aa-163">If you decide to rely on the **PR_ANR** restriction for name resolution, you can return MAPI_E_NO_SUPPORT.</span></span> <span data-ttu-id="560aa-164">有关详细信息，请参阅 [实现名称解析](implementing-name-resolution.md)。</span><span class="sxs-lookup"><span data-stu-id="560aa-164">For more information, see [Implementing Name Resolution](implementing-name-resolution.md).</span></span>
  
<span data-ttu-id="560aa-165">在  _lpFlagList_ 参数中设置收件人的标记条目MAPI_UNRESOLVED如果收件人与容器的任何收件人都不匹配，则设置该条目。</span><span class="sxs-lookup"><span data-stu-id="560aa-165">Set a recipient's flag entry in the  _lpFlagList_ parameter to MAPI_UNRESOLVED if the recipient does not match any of the container's recipients.</span></span> 
  
<span data-ttu-id="560aa-166">当收件人与多个收件人匹配时，请设置其标志MAPI_AMBIGUOUS不要更改 **其 ADRENTRY** 结构。</span><span class="sxs-lookup"><span data-stu-id="560aa-166">When a recipient matches multiple recipients, set its flag to MAPI_AMBIGUOUS and do not change its **ADRENTRY** structure.</span></span> 
  
<span data-ttu-id="560aa-167">MAPI 要求邮件的收件人列表中包含的收件人的某些属性。</span><span class="sxs-lookup"><span data-stu-id="560aa-167">MAPI requires certain properties for recipients that are included in a message's recipient list.</span></span> <span data-ttu-id="560aa-168">可以在名称解析过程中将它们包括在 **ADRENTRY** 结构中，或者等待 MAPI 通过调用 [IAddrBook：:P repareRecips](iaddrbook-preparerecips.md) 和 [IMAPISupport：：ExpandRecips](imapisupport-expandrecips.md) 方法来请求它们。</span><span class="sxs-lookup"><span data-stu-id="560aa-168">You can include them in the **ADRENTRY** structure as part of the name resolution process or wait for MAPI to request them with calls to the [IAddrBook::PrepareRecips](iaddrbook-preparerecips.md) and [IMAPISupport::ExpandRecips](imapisupport-expandrecips.md) methods.</span></span> <span data-ttu-id="560aa-169">通过在所有解析的收件人的 **ADRENTRY** 结构中包括以下属性，可以消除这些额外的呼叫并提高性能：</span><span class="sxs-lookup"><span data-stu-id="560aa-169">You can eliminate these extra calls and improve performance by including the following properties in the **ADRENTRY** structures of all resolved recipients:</span></span> 
  
- <span data-ttu-id="560aa-170">**PR_ADDRTYPE**</span><span class="sxs-lookup"><span data-stu-id="560aa-170">**PR_ADDRTYPE**</span></span>
    
- <span data-ttu-id="560aa-171">**PR_DISPLAY_NAME**</span><span class="sxs-lookup"><span data-stu-id="560aa-171">**PR_DISPLAY_NAME**</span></span>
    
- <span data-ttu-id="560aa-172">**PR_EMAIL_ADDRESS**</span><span class="sxs-lookup"><span data-stu-id="560aa-172">**PR_EMAIL_ADDRESS**</span></span>
    
- <span data-ttu-id="560aa-173">**PR_ENTRYID**</span><span class="sxs-lookup"><span data-stu-id="560aa-173">**PR_ENTRYID**</span></span>
    
- <span data-ttu-id="560aa-174">**PR_OBJECT_TYPE (** [PidTagObjectType](pidtagobjecttype-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="560aa-174">**PR_OBJECT_TYPE** ([PidTagObjectType](pidtagobjecttype-canonical-property.md))</span></span>
    
- <span data-ttu-id="560aa-175">**PR_SEARCH_KEY (** [PidTagSearchKey](pidtagsearchkey-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="560aa-175">**PR_SEARCH_KEY** ([PidTagSearchKey](pidtagsearchkey-canonical-property.md))</span></span>
    
- <span data-ttu-id="560aa-176">**PR_TRANSMITABLE_DISPLAY_NAME (** [PidTagTransmittableDisplayName](pidtagtransmittabledisplayname-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="560aa-176">**PR_TRANSMITABLE_DISPLAY_NAME** ([PidTagTransmittableDisplayName](pidtagtransmittabledisplayname-canonical-property.md))</span></span>
    
<span data-ttu-id="560aa-177">如果 _lpPropTagArray_ 参数中的某些属性不可用（通常是因为容器条目不支持这些属性，并且这些属性不包含在 **ADRLIST** 结构中收件人的 **ADRENTRY** 成员中）将每个不可用属性的属性类型设置为 PT_ERROR。</span><span class="sxs-lookup"><span data-stu-id="560aa-177">If some of the properties in the  _lpPropTagArray_ parameter are unavailable—typically because the container entry does not support the properties and they are not included in the recipient's **ADRENTRY** member in the **ADRLIST** structure—set the property type of each unavailable property to PT_ERROR.</span></span> 
  
<span data-ttu-id="560aa-178">不要从解析的收件人的 **ADRENTRY** 结构中删除任何属性。</span><span class="sxs-lookup"><span data-stu-id="560aa-178">Do not remove any properties from a resolved recipient's **ADRENTRY** structure.</span></span> 
  
<span data-ttu-id="560aa-179">如果必须替换而不是修改 **ADRENTRY** 结构，请首先通过调用 [MAPIFreeBuffer](mapifreebuffer.md)函数释放原始 **ADRENTRY** 结构，然后使用 [MAPIAllocateBuffer](mapiallocatebuffer.md)分配替换 **ADRENTRY** 结构。</span><span class="sxs-lookup"><span data-stu-id="560aa-179">If you must replace rather than modify an **ADRENTRY** structure, free the original **ADRENTRY** structure first by calling the [MAPIFreeBuffer](mapifreebuffer.md) function, and then allocate the replacement **ADRENTRY** structure with [MAPIAllocateBuffer](mapiallocatebuffer.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="560aa-180">另请参阅</span><span class="sxs-lookup"><span data-stu-id="560aa-180">See also</span></span>



[<span data-ttu-id="560aa-181">ADRENTRY</span><span class="sxs-lookup"><span data-stu-id="560aa-181">ADRENTRY</span></span>](adrentry.md)
  
[<span data-ttu-id="560aa-182">ADRLIST</span><span class="sxs-lookup"><span data-stu-id="560aa-182">ADRLIST</span></span>](adrlist.md)
  
[<span data-ttu-id="560aa-183">IAddrBook::PrepareRecips</span><span class="sxs-lookup"><span data-stu-id="560aa-183">IAddrBook::PrepareRecips</span></span>](iaddrbook-preparerecips.md)
  
[<span data-ttu-id="560aa-184">IAddrBook::ResolveName</span><span class="sxs-lookup"><span data-stu-id="560aa-184">IAddrBook::ResolveName</span></span>](iaddrbook-resolvename.md)
  
[<span data-ttu-id="560aa-185">IMAPISupport::ExpandRecips</span><span class="sxs-lookup"><span data-stu-id="560aa-185">IMAPISupport::ExpandRecips</span></span>](imapisupport-expandrecips.md)
  
[<span data-ttu-id="560aa-186">IMessage::ModifyRecipients</span><span class="sxs-lookup"><span data-stu-id="560aa-186">IMessage::ModifyRecipients</span></span>](imessage-modifyrecipients.md)
  
[<span data-ttu-id="560aa-187">PidTagAnr 规范属性</span><span class="sxs-lookup"><span data-stu-id="560aa-187">PidTagAnr Canonical Property</span></span>](pidtaganr-canonical-property.md)
  
[<span data-ttu-id="560aa-188">SPropertyRestriction</span><span class="sxs-lookup"><span data-stu-id="560aa-188">SPropertyRestriction</span></span>](spropertyrestriction.md)
  
[<span data-ttu-id="560aa-189">IABContainer : IMAPIContainer</span><span class="sxs-lookup"><span data-stu-id="560aa-189">IABContainer : IMAPIContainer</span></span>](iabcontainerimapicontainer.md)

