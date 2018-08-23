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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 81f35f659342d6258d60f40b12bd0a3ac2dc20b2
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22588473"
---
# <a name="iabcontainerresolvenames"></a><span data-ttu-id="ab656-103">IABContainer::ResolveNames</span><span class="sxs-lookup"><span data-stu-id="ab656-103">IABContainer::ResolveNames</span></span>

  
  
<span data-ttu-id="ab656-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="ab656-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="ab656-105">执行一个或多个收件人的条目的名称解析。</span><span class="sxs-lookup"><span data-stu-id="ab656-105">Performs name resolution for one or more recipient entries.</span></span>
  
```cpp
HRESULT ResolveNames(
  LPSPropTagArray lpPropTagArray,
  ULONG ulFlags,
  LPADRLIST lpAdrList,
  LPFlagList lpFlagList
);
```

## <a name="parameters"></a><span data-ttu-id="ab656-106">参数</span><span class="sxs-lookup"><span data-stu-id="ab656-106">Parameters</span></span>

 <span data-ttu-id="ab656-107">_lpPropTagArray_</span><span class="sxs-lookup"><span data-stu-id="ab656-107">_lpPropTagArray_</span></span>
  
> <span data-ttu-id="ab656-108">[in]一个指向[SPropTagArray](sproptagarray.md)结构，其中包含数组属性标记描述要包括在[ADRLIST](adrlist.md)结构提供程序返回的属性。</span><span class="sxs-lookup"><span data-stu-id="ab656-108">[in] A pointer to an [SPropTagArray](sproptagarray.md) structure that contains an array of property tags describing the properties to be included in the [ADRLIST](adrlist.md) structure returned by the provider.</span></span> <span data-ttu-id="ab656-109">若要请求提供程序的默认属性集，请_lpPropTagArray_参数中传递 NULL。</span><span class="sxs-lookup"><span data-stu-id="ab656-109">To request the provider's default set of properties, pass NULL in the  _lpPropTagArray_ parameter.</span></span> 
    
 <span data-ttu-id="ab656-110">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="ab656-110">_ulFlags_</span></span>
  
> <span data-ttu-id="ab656-111">[in]位掩码的标志的控制返回的字符串中的文本的类型。</span><span class="sxs-lookup"><span data-stu-id="ab656-111">[in] A bitmask of flags that controls the type of the text in the returned strings.</span></span> <span data-ttu-id="ab656-112">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="ab656-112">The following flags can be set:</span></span>
    
<span data-ttu-id="ab656-113">EMS_AB_ADDRESS_LOOKUP</span><span class="sxs-lookup"><span data-stu-id="ab656-113">EMS_AB_ADDRESS_LOOKUP</span></span>
  
> <span data-ttu-id="ab656-114">将找到仅确切代理地址匹配;部分匹配项将被忽略。</span><span class="sxs-lookup"><span data-stu-id="ab656-114">Only exact proxy address matches will be found; partial matches are ignored.</span></span> <span data-ttu-id="ab656-115">此标志仅受 Exchange 通讯簿提供程序支持。</span><span class="sxs-lookup"><span data-stu-id="ab656-115">This flag is supported only by the Exchange Address Book Provider.</span></span>
    
<span data-ttu-id="ab656-116">MAPI_CACHE_ONLY</span><span class="sxs-lookup"><span data-stu-id="ab656-116">MAPI_CACHE_ONLY</span></span>
  
> <span data-ttu-id="ab656-117">仅在脱机通讯簿将用于执行名称解析。</span><span class="sxs-lookup"><span data-stu-id="ab656-117">Only the offline address book will be used to perform name resolution.</span></span> <span data-ttu-id="ab656-118">例如，您可以使用此标志若要将客户端应用程序在缓存的 exchange 模式下打开全局地址列表 (GAL)，而不创建客户端和服务器之间的流量从缓存中访问该通讯簿中的条目。</span><span class="sxs-lookup"><span data-stu-id="ab656-118">For example, you can use this flag to enable a client application to open the global address list (GAL) in cached exchange mode and access an entry in that address book from the cache without creating traffic between the client and the server.</span></span> <span data-ttu-id="ab656-119">此标志仅受 Exchange 通讯簿提供程序支持。</span><span class="sxs-lookup"><span data-stu-id="ab656-119">This flag is supported only by the Exchange Address Book Provider.</span></span> 
    
<span data-ttu-id="ab656-120">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="ab656-120">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="ab656-121">返回的字符串属性采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="ab656-121">The returned string properties are in Unicode format.</span></span> <span data-ttu-id="ab656-122">如果未设置 MAPI_UNICODE 标志的字符串是以 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="ab656-122">If the MAPI_UNICODE flag is not set, the strings are in ANSI format.</span></span>
    
 <span data-ttu-id="ab656-123">_lpAdrList_</span><span class="sxs-lookup"><span data-stu-id="ab656-123">_lpAdrList_</span></span>
  
> <span data-ttu-id="ab656-124">[传入、 传出]在输入，指向**ADRLIST**结构，其中包含要解析的收件人列表的指针。</span><span class="sxs-lookup"><span data-stu-id="ab656-124">[in, out] On input, a pointer to an **ADRLIST** structure that contains the list of recipients to be resolved.</span></span> <span data-ttu-id="ab656-125">在输出，指向包含解析的名称**ADRLIST**结构的指针。</span><span class="sxs-lookup"><span data-stu-id="ab656-125">On output, a pointer to an **ADRLIST** structure that contains the resolved names.</span></span> 
    
 <span data-ttu-id="ab656-126">_lpFlagList_</span><span class="sxs-lookup"><span data-stu-id="ab656-126">_lpFlagList_</span></span>
  
> <span data-ttu-id="ab656-127">[传入、 传出]为数组标志的指针，对应于[ADRENTRY](adrentry.md)结构_lpAdrList_参数中每个标志提供收件人的名称解析操作的状态。</span><span class="sxs-lookup"><span data-stu-id="ab656-127">[in, out] A pointer to an array of flags, each flag corresponding to an [ADRENTRY](adrentry.md) structure in the  _lpAdrList_ parameter, that provides the status of the name resolution operation for the recipient.</span></span> <span data-ttu-id="ab656-128">_LpFlagList_参数中的标志处于_lpAdrList_中的项的顺序相同。</span><span class="sxs-lookup"><span data-stu-id="ab656-128">The flags in the  _lpFlagList_ parameter are in the same order as the entries in  _lpAdrList_.</span></span> <span data-ttu-id="ab656-129">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="ab656-129">The following flags can be set:</span></span>
    
<span data-ttu-id="ab656-130">MAPI_AMBIGUOUS</span><span class="sxs-lookup"><span data-stu-id="ab656-130">MAPI_AMBIGUOUS</span></span> 
  
> <span data-ttu-id="ab656-131">相应的接收人已得到解决，但不适用于唯一项标识符。</span><span class="sxs-lookup"><span data-stu-id="ab656-131">The corresponding recipient has been resolved, but not to a unique entry identifier.</span></span> <span data-ttu-id="ab656-132">其他容器不应尝试解析该收件人。</span><span class="sxs-lookup"><span data-stu-id="ab656-132">Other containers should not try to resolve this recipient.</span></span> 
    
<span data-ttu-id="ab656-133">MAPI_RESOLVED</span><span class="sxs-lookup"><span data-stu-id="ab656-133">MAPI_RESOLVED</span></span> 
  
> <span data-ttu-id="ab656-134">已为唯一条目标识符解决了相应的收件人。</span><span class="sxs-lookup"><span data-stu-id="ab656-134">The corresponding recipient has been resolved to a unique entry identifier.</span></span> <span data-ttu-id="ab656-135">其他容器不应尝试解析该收件人。</span><span class="sxs-lookup"><span data-stu-id="ab656-135">Other containers should not try to resolve this recipient.</span></span> 
    
<span data-ttu-id="ab656-136">MAPI_UNRESOLVED</span><span class="sxs-lookup"><span data-stu-id="ab656-136">MAPI_UNRESOLVED</span></span> 
  
> <span data-ttu-id="ab656-137">尚未解决的相应项。</span><span class="sxs-lookup"><span data-stu-id="ab656-137">The corresponding entry has not been resolved.</span></span> <span data-ttu-id="ab656-138">其他容器应尝试解析该收件人。</span><span class="sxs-lookup"><span data-stu-id="ab656-138">Other containers should try to resolve this recipient.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="ab656-139">返回值</span><span class="sxs-lookup"><span data-stu-id="ab656-139">Return value</span></span>

<span data-ttu-id="ab656-140">S_OK</span><span class="sxs-lookup"><span data-stu-id="ab656-140">S_OK</span></span> 
  
> <span data-ttu-id="ab656-141">名称解析过程成功。</span><span class="sxs-lookup"><span data-stu-id="ab656-141">The name resolution process was successful.</span></span>
    
<span data-ttu-id="ab656-142">MAPI_E_BAD_CHARWIDTH</span><span class="sxs-lookup"><span data-stu-id="ab656-142">MAPI_E_BAD_CHARWIDTH</span></span> 
  
> <span data-ttu-id="ab656-143">既设置了 MAPI_UNICODE 标志实现不支持 Unicode，或未设置 MAPI_UNICODE 并实现支持仅 Unicode。</span><span class="sxs-lookup"><span data-stu-id="ab656-143">Either the MAPI_UNICODE flag was set and the implementation does not support Unicode, or MAPI_UNICODE was not set and the implementation supports only Unicode.</span></span>
    
<span data-ttu-id="ab656-144">MAPI_E_NO_SUPPORT</span><span class="sxs-lookup"><span data-stu-id="ab656-144">MAPI_E_NO_SUPPORT</span></span> 
  
> <span data-ttu-id="ab656-145">通讯簿提供程序不支持批量名称解析使用此方法。</span><span class="sxs-lookup"><span data-stu-id="ab656-145">The address book provider does not support bulk name resolution by using this method.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="ab656-146">注解</span><span class="sxs-lookup"><span data-stu-id="ab656-146">Remarks</span></span>

<span data-ttu-id="ab656-147">**ResolveNames**方法尝试匹配未解析的收件人，数组中的条目_lpAdrList_参数中向此通讯簿容器中的收件人。</span><span class="sxs-lookup"><span data-stu-id="ab656-147">The **ResolveNames** method attempts to match unresolved recipients from the array of entries in the  _lpAdrList_ parameter to recipients in this address book container.</span></span> <span data-ttu-id="ab656-148">无法解析的收件人通常具有仅**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 属性和可能的一些其他属性。</span><span class="sxs-lookup"><span data-stu-id="ab656-148">An unresolved recipient typically has only the **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) property and possibly a few other properties.</span></span> <span data-ttu-id="ab656-149">无法解析的收件人没有**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 属性，而且其_lpFlagList_参数中的相应标志设置为 MAPI_UNRESOLVED。</span><span class="sxs-lookup"><span data-stu-id="ab656-149">An unresolved recipient does not have the **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) property, and its corresponding flag in the  _lpFlagList_ parameter is set to MAPI_UNRESOLVED.</span></span> <span data-ttu-id="ab656-150">相反，解析的收件人总是至少具有**PR_ENTRYID**属性以及**PR_EMAIL_ADDRESS** ([PidTagEmailAddress](pidtagemailaddress-canonical-property.md))、 **PR_DISPLAY_NAME**，等**PR_ADDRTYPE** ([的其他几个属性PidTagAddressType](pidtagaddresstype-canonical-property.md))。</span><span class="sxs-lookup"><span data-stu-id="ab656-150">Conversely, a resolved recipient always has at least the **PR_ENTRYID** property plus several other properties such as **PR_EMAIL_ADDRESS** ([PidTagEmailAddress](pidtagemailaddress-canonical-property.md)), **PR_DISPLAY_NAME**, and **PR_ADDRTYPE** ([PidTagAddressType](pidtagaddresstype-canonical-property.md)).</span></span>
  
<span data-ttu-id="ab656-151">通常，当在客户端调用[IAddrBook::ResolveName](iaddrbook-resolvename.md)方法时，将启动名称解析。</span><span class="sxs-lookup"><span data-stu-id="ab656-151">Name resolution typically starts when a client calls the [IAddrBook::ResolveName](iaddrbook-resolvename.md) method.</span></span> <span data-ttu-id="ab656-152">Outlook MAPI 响应通过调用**PR_AB_SEARCH_PATH** ([PidTagAbSearchPath](pidtagabsearchpath-canonical-property.md)) 属性指定的通讯簿搜索路径中包含每个通讯簿容器的**ResolveNames**方法。</span><span class="sxs-lookup"><span data-stu-id="ab656-152">Outlook MAPI responds by calling the **ResolveNames** method of each address book container included in the address book search path, specified by the **PR_AB_SEARCH_PATH** ([PidTagAbSearchPath](pidtagabsearchpath-canonical-property.md)) property.</span></span> <span data-ttu-id="ab656-153">_LpAdrList_参数中的项包括因为它们在容器为其 MAPI 已调用**ResolveNames**，因为在搜索路径的前面部分中显示的项已成功解析的收件人。</span><span class="sxs-lookup"><span data-stu-id="ab656-153">The entries in the  _lpAdrList_ parameter include recipients already resolved because they are in containers for which MAPI has already called **ResolveNames**, because the entries appear earlier in the search path.</span></span> 
  
<span data-ttu-id="ab656-154">每个容器尝试解析的未解决的条目匹配收件人的显示名称，其条目之一的显示名称。</span><span class="sxs-lookup"><span data-stu-id="ab656-154">Each container attempts to resolve the unresolved entries by matching the display name of the recipient with the display name of one of its entries.</span></span> <span data-ttu-id="ab656-155">当找到唯一的匹配项时， **ResolveNames**添加**PR_ENTRYID**属性和传出**ADRLIST**结构中的相应条目的_lpPropTagArray_参数中包含其他属性。</span><span class="sxs-lookup"><span data-stu-id="ab656-155">When a unique match is found, **ResolveNames** adds the **PR_ENTRYID** property and other properties that are included in the  _lpPropTagArray_ parameter to the corresponding entry in the outgoing **ADRLIST** structure.</span></span> <span data-ttu-id="ab656-156">然后， **ResolveNames** MAPI_RESOLVED 的_lpFlagList_参数中设置该条目。</span><span class="sxs-lookup"><span data-stu-id="ab656-156">**ResolveNames** then sets the entry in the  _lpFlagList_ parameter to MAPI_RESOLVED.</span></span> <span data-ttu-id="ab656-157">短期或长期，可以是存储在**PR_ENTRYID**属性中的项标识符。</span><span class="sxs-lookup"><span data-stu-id="ab656-157">The entry identifier stored in the **PR_ENTRYID** property can be short-term or long-term.</span></span> 
  
<span data-ttu-id="ab656-158">毕竟中搜索的容器的路径具有尝试名称解析过程、 MAPI 打开一个对话框，如果可能，以提示用户输入帮助解决任何剩余的冲突。</span><span class="sxs-lookup"><span data-stu-id="ab656-158">After all of the containers in the search path have attempted the name resolution process, MAPI opens a dialog box, if possible, to prompt the user for help in resolving any remaining conflicts.</span></span> 
  
<span data-ttu-id="ab656-159">客户端还可以对[IMessage::ModifyRecipients](imessage-modifyrecipients.md)方法调用中使用返回的**ADRLIST**结构。</span><span class="sxs-lookup"><span data-stu-id="ab656-159">Clients can also use the returned **ADRLIST** structure in calls to the [IMessage::ModifyRecipients](imessage-modifyrecipients.md) method.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="ab656-160">针对实施者的注释</span><span class="sxs-lookup"><span data-stu-id="ab656-160">Notes to implementers</span></span>

<span data-ttu-id="ab656-161">您无需使用**ResolveNames**方法支持名称解析。</span><span class="sxs-lookup"><span data-stu-id="ab656-161">You are not required to support name resolution with the **ResolveNames** method.</span></span> <span data-ttu-id="ab656-162">相反，或此外，您可以与**PR_ANR** ([PidTagAnr](pidtaganr-canonical-property.md)) 属性限制来支持它。</span><span class="sxs-lookup"><span data-stu-id="ab656-162">Instead, or additionally, you can support it with the **PR_ANR** ([PidTagAnr](pidtaganr-canonical-property.md)) property restriction.</span></span> <span data-ttu-id="ab656-163">如果您决定依赖于**PR_ANR**限制的名称解析，您可以返回 MAPI_E_NO_SUPPORT。</span><span class="sxs-lookup"><span data-stu-id="ab656-163">If you decide to rely on the **PR_ANR** restriction for name resolution, you can return MAPI_E_NO_SUPPORT.</span></span> <span data-ttu-id="ab656-164">有关详细信息，请参阅[实现名称解析](implementing-name-resolution.md)。</span><span class="sxs-lookup"><span data-stu-id="ab656-164">For more information, see [Implementing Name Resolution](implementing-name-resolution.md).</span></span>
  
<span data-ttu-id="ab656-165">如果收件人不匹配的任何容器的收件人，请在 MAPI_UNRESOLVED _lpFlagList_参数设置收件人的标志条目。</span><span class="sxs-lookup"><span data-stu-id="ab656-165">Set a recipient's flag entry in the  _lpFlagList_ parameter to MAPI_UNRESOLVED if the recipient does not match any of the container's recipients.</span></span> 
  
<span data-ttu-id="ab656-166">收件人匹配时多个收件人，将其标志设置为 MAPI_AMBIGUOUS，而不更改其**ADRENTRY**结构。</span><span class="sxs-lookup"><span data-stu-id="ab656-166">When a recipient matches multiple recipients, set its flag to MAPI_AMBIGUOUS and do not change its **ADRENTRY** structure.</span></span> 
  
<span data-ttu-id="ab656-167">MAPI 要求对收件人的邮件的收件人列表中包含的某些属性。</span><span class="sxs-lookup"><span data-stu-id="ab656-167">MAPI requires certain properties for recipients that are included in a message's recipient list.</span></span> <span data-ttu-id="ab656-168">您可以将它们作为名称解析过程的一部分包含**ADRENTRY**结构中或等待 MAPI 请求它们通过[IAddrBook::PrepareRecips](iaddrbook-preparerecips.md)和[IMAPISupport::ExpandRecips](imapisupport-expandrecips.md)方法的调用。</span><span class="sxs-lookup"><span data-stu-id="ab656-168">You can include them in the **ADRENTRY** structure as part of the name resolution process or wait for MAPI to request them with calls to the [IAddrBook::PrepareRecips](iaddrbook-preparerecips.md) and [IMAPISupport::ExpandRecips](imapisupport-expandrecips.md) methods.</span></span> <span data-ttu-id="ab656-169">您可以消除这些额外的呼叫和提高性能，通过将所有已解析的收件人的**ADRENTRY**结构包括以下属性：</span><span class="sxs-lookup"><span data-stu-id="ab656-169">You can eliminate these extra calls and improve performance by including the following properties in the **ADRENTRY** structures of all resolved recipients:</span></span> 
  
- <span data-ttu-id="ab656-170">**PR_ADDRTYPE**</span><span class="sxs-lookup"><span data-stu-id="ab656-170">**PR_ADDRTYPE**</span></span>
    
- <span data-ttu-id="ab656-171">**PR_DISPLAY_NAME**</span><span class="sxs-lookup"><span data-stu-id="ab656-171">**PR_DISPLAY_NAME**</span></span>
    
- <span data-ttu-id="ab656-172">**PR_EMAIL_ADDRESS**</span><span class="sxs-lookup"><span data-stu-id="ab656-172">**PR_EMAIL_ADDRESS**</span></span>
    
- <span data-ttu-id="ab656-173">**PR_ENTRYID**</span><span class="sxs-lookup"><span data-stu-id="ab656-173">**PR_ENTRYID**</span></span>
    
- <span data-ttu-id="ab656-174">**PR_OBJECT_TYPE**([PidTagObjectType](pidtagobjecttype-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="ab656-174">**PR_OBJECT_TYPE** ([PidTagObjectType](pidtagobjecttype-canonical-property.md))</span></span>
    
- <span data-ttu-id="ab656-175">**PR_SEARCH_KEY**([PidTagSearchKey](pidtagsearchkey-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="ab656-175">**PR_SEARCH_KEY** ([PidTagSearchKey](pidtagsearchkey-canonical-property.md))</span></span>
    
- <span data-ttu-id="ab656-176">**PR_TRANSMITABLE_DISPLAY_NAME**([PidTagTransmittableDisplayName](pidtagtransmittabledisplayname-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="ab656-176">**PR_TRANSMITABLE_DISPLAY_NAME** ([PidTagTransmittableDisplayName](pidtagtransmittabledisplayname-canonical-property.md))</span></span>
    
<span data-ttu-id="ab656-177">如果_lpPropTagArray_参数中的属性的一些不可 — 通常因为容器条目不支持的属性，并且它们不包括在**ADRLIST**结构中的收件人的**ADRENTRY**成员 —设置为 PT_ERROR 不可用的每个属性的属性类型。</span><span class="sxs-lookup"><span data-stu-id="ab656-177">If some of the properties in the  _lpPropTagArray_ parameter are unavailable—typically because the container entry does not support the properties and they are not included in the recipient's **ADRENTRY** member in the **ADRLIST** structure—set the property type of each unavailable property to PT_ERROR.</span></span> 
  
<span data-ttu-id="ab656-178">不要从解析的收件人的**ADRENTRY**结构中删除任何属性。</span><span class="sxs-lookup"><span data-stu-id="ab656-178">Do not remove any properties from a resolved recipient's **ADRENTRY** structure.</span></span> 
  
<span data-ttu-id="ab656-179">如果必须替换，而不是修改**ADRENTRY**结构，释放首先通过调用[MAPIFreeBuffer](mapifreebuffer.md)函数，原始**ADRENTRY**结构，然后将分配替换[**ADRENTRY**结构MAPIAllocateBuffer](mapiallocatebuffer.md)。</span><span class="sxs-lookup"><span data-stu-id="ab656-179">If you must replace rather than modify an **ADRENTRY** structure, free the original **ADRENTRY** structure first by calling the [MAPIFreeBuffer](mapifreebuffer.md) function, and then allocate the replacement **ADRENTRY** structure with [MAPIAllocateBuffer](mapiallocatebuffer.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="ab656-180">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ab656-180">See also</span></span>



[<span data-ttu-id="ab656-181">ADRENTRY</span><span class="sxs-lookup"><span data-stu-id="ab656-181">ADRENTRY</span></span>](adrentry.md)
  
[<span data-ttu-id="ab656-182">ADRLIST</span><span class="sxs-lookup"><span data-stu-id="ab656-182">ADRLIST</span></span>](adrlist.md)
  
[<span data-ttu-id="ab656-183">IAddrBook::PrepareRecips</span><span class="sxs-lookup"><span data-stu-id="ab656-183">IAddrBook::PrepareRecips</span></span>](iaddrbook-preparerecips.md)
  
[<span data-ttu-id="ab656-184">IAddrBook::ResolveName</span><span class="sxs-lookup"><span data-stu-id="ab656-184">IAddrBook::ResolveName</span></span>](iaddrbook-resolvename.md)
  
[<span data-ttu-id="ab656-185">IMAPISupport::ExpandRecips</span><span class="sxs-lookup"><span data-stu-id="ab656-185">IMAPISupport::ExpandRecips</span></span>](imapisupport-expandrecips.md)
  
[<span data-ttu-id="ab656-186">IMessage::ModifyRecipients</span><span class="sxs-lookup"><span data-stu-id="ab656-186">IMessage::ModifyRecipients</span></span>](imessage-modifyrecipients.md)
  
[<span data-ttu-id="ab656-187">PidTagAnr 规范属性</span><span class="sxs-lookup"><span data-stu-id="ab656-187">PidTagAnr Canonical Property</span></span>](pidtaganr-canonical-property.md)
  
[<span data-ttu-id="ab656-188">SPropertyRestriction</span><span class="sxs-lookup"><span data-stu-id="ab656-188">SPropertyRestriction</span></span>](spropertyrestriction.md)
  
[<span data-ttu-id="ab656-189">IABContainer : IMAPIContainer</span><span class="sxs-lookup"><span data-stu-id="ab656-189">IABContainer : IMAPIContainer</span></span>](iabcontainerimapicontainer.md)

