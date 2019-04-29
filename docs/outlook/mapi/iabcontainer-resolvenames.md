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
# <a name="iabcontainerresolvenames"></a><span data-ttu-id="b33c9-103">IABContainer::ResolveNames</span><span class="sxs-lookup"><span data-stu-id="b33c9-103">IABContainer::ResolveNames</span></span>

  
  
<span data-ttu-id="b33c9-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="b33c9-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="b33c9-105">为一个或多个收件人条目执行名称解析。</span><span class="sxs-lookup"><span data-stu-id="b33c9-105">Performs name resolution for one or more recipient entries.</span></span>
  
```cpp
HRESULT ResolveNames(
  LPSPropTagArray lpPropTagArray,
  ULONG ulFlags,
  LPADRLIST lpAdrList,
  LPFlagList lpFlagList
);
```

## <a name="parameters"></a><span data-ttu-id="b33c9-106">参数</span><span class="sxs-lookup"><span data-stu-id="b33c9-106">Parameters</span></span>

 <span data-ttu-id="b33c9-107">_lpPropTagArray_</span><span class="sxs-lookup"><span data-stu-id="b33c9-107">_lpPropTagArray_</span></span>
  
> <span data-ttu-id="b33c9-108">实时一个指向[SPropTagArray](sproptagarray.md)结构的指针, 该结构包含一个属性标记数组, 这些标记描述提供程序返回的[ADRLIST](adrlist.md)结构中要包含的属性。</span><span class="sxs-lookup"><span data-stu-id="b33c9-108">[in] A pointer to an [SPropTagArray](sproptagarray.md) structure that contains an array of property tags describing the properties to be included in the [ADRLIST](adrlist.md) structure returned by the provider.</span></span> <span data-ttu-id="b33c9-109">若要请求提供程序的默认属性集, 请在_lpPropTagArray_参数中传递 NULL。</span><span class="sxs-lookup"><span data-stu-id="b33c9-109">To request the provider's default set of properties, pass NULL in the  _lpPropTagArray_ parameter.</span></span> 
    
 <span data-ttu-id="b33c9-110">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="b33c9-110">_ulFlags_</span></span>
  
> <span data-ttu-id="b33c9-111">实时用于控制返回的字符串中的文本类型的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="b33c9-111">[in] A bitmask of flags that controls the type of the text in the returned strings.</span></span> <span data-ttu-id="b33c9-112">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="b33c9-112">The following flags can be set:</span></span>
    
<span data-ttu-id="b33c9-113">EMS_AB_ADDRESS_LOOKUP</span><span class="sxs-lookup"><span data-stu-id="b33c9-113">EMS_AB_ADDRESS_LOOKUP</span></span>
  
> <span data-ttu-id="b33c9-114">仅找到精确的代理地址匹配项;忽略部分匹配项。</span><span class="sxs-lookup"><span data-stu-id="b33c9-114">Only exact proxy address matches will be found; partial matches are ignored.</span></span> <span data-ttu-id="b33c9-115">仅 Exchange 通讯簿提供程序支持此标志。</span><span class="sxs-lookup"><span data-stu-id="b33c9-115">This flag is supported only by the Exchange Address Book Provider.</span></span>
    
<span data-ttu-id="b33c9-116">MAPI_CACHE_ONLY</span><span class="sxs-lookup"><span data-stu-id="b33c9-116">MAPI_CACHE_ONLY</span></span>
  
> <span data-ttu-id="b33c9-117">仅将脱机通讯簿用于执行名称解析。</span><span class="sxs-lookup"><span data-stu-id="b33c9-117">Only the offline address book will be used to perform name resolution.</span></span> <span data-ttu-id="b33c9-118">例如, 可以使用此标志启用客户端应用程序, 以在缓存 exchange 模式下打开全局地址列表 (GAL), 并从缓存中访问该通讯簿中的条目, 而无需在客户端和服务器之间创建流量。</span><span class="sxs-lookup"><span data-stu-id="b33c9-118">For example, you can use this flag to enable a client application to open the global address list (GAL) in cached exchange mode and access an entry in that address book from the cache without creating traffic between the client and the server.</span></span> <span data-ttu-id="b33c9-119">仅 Exchange 通讯簿提供程序支持此标志。</span><span class="sxs-lookup"><span data-stu-id="b33c9-119">This flag is supported only by the Exchange Address Book Provider.</span></span> 
    
<span data-ttu-id="b33c9-120">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="b33c9-120">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="b33c9-121">返回的字符串属性采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="b33c9-121">The returned string properties are in Unicode format.</span></span> <span data-ttu-id="b33c9-122">如果未设置 MAPI_UNICODE 标志, 则字符串将采用 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="b33c9-122">If the MAPI_UNICODE flag is not set, the strings are in ANSI format.</span></span>
    
 <span data-ttu-id="b33c9-123">_lpAdrList_</span><span class="sxs-lookup"><span data-stu-id="b33c9-123">_lpAdrList_</span></span>
  
> <span data-ttu-id="b33c9-124">[in, out]在输入时, 指向包含要解析的收件人列表的**ADRLIST**结构的指针。</span><span class="sxs-lookup"><span data-stu-id="b33c9-124">[in, out] On input, a pointer to an **ADRLIST** structure that contains the list of recipients to be resolved.</span></span> <span data-ttu-id="b33c9-125">在输出时, 指向包含解析的名称的**ADRLIST**结构的指针。</span><span class="sxs-lookup"><span data-stu-id="b33c9-125">On output, a pointer to an **ADRLIST** structure that contains the resolved names.</span></span> 
    
 <span data-ttu-id="b33c9-126">_lpFlagList_</span><span class="sxs-lookup"><span data-stu-id="b33c9-126">_lpFlagList_</span></span>
  
> <span data-ttu-id="b33c9-127">[in, out]指向标志数组的指针, 每个与_lpAdrList_参数中的[ADRENTRY](adrentry.md)结构对应的标记, 该标记提供收件人的名称解析操作的状态。</span><span class="sxs-lookup"><span data-stu-id="b33c9-127">[in, out] A pointer to an array of flags, each flag corresponding to an [ADRENTRY](adrentry.md) structure in the  _lpAdrList_ parameter, that provides the status of the name resolution operation for the recipient.</span></span> <span data-ttu-id="b33c9-128">_lpFlagList_参数中的标志与_lpAdrList_中的条目的顺序相同。</span><span class="sxs-lookup"><span data-stu-id="b33c9-128">The flags in the  _lpFlagList_ parameter are in the same order as the entries in  _lpAdrList_.</span></span> <span data-ttu-id="b33c9-129">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="b33c9-129">The following flags can be set:</span></span>
    
<span data-ttu-id="b33c9-130">MAPI_AMBIGUOUS</span><span class="sxs-lookup"><span data-stu-id="b33c9-130">MAPI_AMBIGUOUS</span></span> 
  
> <span data-ttu-id="b33c9-131">已解决相应的收件人, 但不是唯一的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="b33c9-131">The corresponding recipient has been resolved, but not to a unique entry identifier.</span></span> <span data-ttu-id="b33c9-132">其他容器不应尝试解析该收件人。</span><span class="sxs-lookup"><span data-stu-id="b33c9-132">Other containers should not try to resolve this recipient.</span></span> 
    
<span data-ttu-id="b33c9-133">MAPI_RESOLVED</span><span class="sxs-lookup"><span data-stu-id="b33c9-133">MAPI_RESOLVED</span></span> 
  
> <span data-ttu-id="b33c9-134">相应的收件人已解析为唯一条目标识符。</span><span class="sxs-lookup"><span data-stu-id="b33c9-134">The corresponding recipient has been resolved to a unique entry identifier.</span></span> <span data-ttu-id="b33c9-135">其他容器不应尝试解析该收件人。</span><span class="sxs-lookup"><span data-stu-id="b33c9-135">Other containers should not try to resolve this recipient.</span></span> 
    
<span data-ttu-id="b33c9-136">MAPI_UNRESOLVED</span><span class="sxs-lookup"><span data-stu-id="b33c9-136">MAPI_UNRESOLVED</span></span> 
  
> <span data-ttu-id="b33c9-137">尚未解析对应的条目。</span><span class="sxs-lookup"><span data-stu-id="b33c9-137">The corresponding entry has not been resolved.</span></span> <span data-ttu-id="b33c9-138">其他容器应尝试解析该收件人。</span><span class="sxs-lookup"><span data-stu-id="b33c9-138">Other containers should try to resolve this recipient.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="b33c9-139">返回值</span><span class="sxs-lookup"><span data-stu-id="b33c9-139">Return value</span></span>

<span data-ttu-id="b33c9-140">S_OK</span><span class="sxs-lookup"><span data-stu-id="b33c9-140">S_OK</span></span> 
  
> <span data-ttu-id="b33c9-141">名称解析过程成功完成。</span><span class="sxs-lookup"><span data-stu-id="b33c9-141">The name resolution process was successful.</span></span>
    
<span data-ttu-id="b33c9-142">MAPI_E_BAD_CHARWIDTH</span><span class="sxs-lookup"><span data-stu-id="b33c9-142">MAPI_E_BAD_CHARWIDTH</span></span> 
  
> <span data-ttu-id="b33c9-143">设置了 MAPI_UNICODE 标志, 且实现不支持 unicode, 或者未设置 MAPI_UNICODE, 且实现仅支持 UNICODE。</span><span class="sxs-lookup"><span data-stu-id="b33c9-143">Either the MAPI_UNICODE flag was set and the implementation does not support Unicode, or MAPI_UNICODE was not set and the implementation supports only Unicode.</span></span>
    
<span data-ttu-id="b33c9-144">MAPI_E_NO_SUPPORT</span><span class="sxs-lookup"><span data-stu-id="b33c9-144">MAPI_E_NO_SUPPORT</span></span> 
  
> <span data-ttu-id="b33c9-145">通讯簿提供程序不支持通过使用此方法进行批量名称解析。</span><span class="sxs-lookup"><span data-stu-id="b33c9-145">The address book provider does not support bulk name resolution by using this method.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="b33c9-146">说明</span><span class="sxs-lookup"><span data-stu-id="b33c9-146">Remarks</span></span>

<span data-ttu-id="b33c9-147">**ResolveNames**方法尝试将未解析的收件人从_lpAdrList_参数中的条目数组与此通讯簿容器中的收件人进行匹配。</span><span class="sxs-lookup"><span data-stu-id="b33c9-147">The **ResolveNames** method attempts to match unresolved recipients from the array of entries in the  _lpAdrList_ parameter to recipients in this address book container.</span></span> <span data-ttu-id="b33c9-148">未解析的收件人通常仅具有**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 属性, 并且可能还有其他一些属性。</span><span class="sxs-lookup"><span data-stu-id="b33c9-148">An unresolved recipient typically has only the **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) property and possibly a few other properties.</span></span> <span data-ttu-id="b33c9-149">未解析的收件人不具有**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 属性, 并且_lpFlagList_参数中的相应标志设置为 MAPI_UNRESOLVED。</span><span class="sxs-lookup"><span data-stu-id="b33c9-149">An unresolved recipient does not have the **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) property, and its corresponding flag in the  _lpFlagList_ parameter is set to MAPI_UNRESOLVED.</span></span> <span data-ttu-id="b33c9-150">相反, 解析的收件人始终至少具有**PR_ENTRYID**属性和其他几个属性, 如**PR_EMAIL_ADDRESS** ([PidTagEmailAddress](pidtagemailaddress-canonical-property.md))、 **PR_DISPLAY_NAME**和**PR_ADDRTYPE** ([PidTagAddressType](pidtagaddresstype-canonical-property.md))。</span><span class="sxs-lookup"><span data-stu-id="b33c9-150">Conversely, a resolved recipient always has at least the **PR_ENTRYID** property plus several other properties such as **PR_EMAIL_ADDRESS** ([PidTagEmailAddress](pidtagemailaddress-canonical-property.md)), **PR_DISPLAY_NAME**, and **PR_ADDRTYPE** ([PidTagAddressType](pidtagaddresstype-canonical-property.md)).</span></span>
  
<span data-ttu-id="b33c9-151">名称解析通常在客户端调用[IAddrBook:: ResolveName](iaddrbook-resolvename.md)方法时启动。</span><span class="sxs-lookup"><span data-stu-id="b33c9-151">Name resolution typically starts when a client calls the [IAddrBook::ResolveName](iaddrbook-resolvename.md) method.</span></span> <span data-ttu-id="b33c9-152">Outlook MAPI 通过调用通讯簿搜索路径中包含的每个通讯簿容器的**ResolveNames**方法进行响应, 由**PR_AB_SEARCH_PATH** ([PidTagAbSearchPath](pidtagabsearchpath-canonical-property.md)) 属性指定。</span><span class="sxs-lookup"><span data-stu-id="b33c9-152">Outlook MAPI responds by calling the **ResolveNames** method of each address book container included in the address book search path, specified by the **PR_AB_SEARCH_PATH** ([PidTagAbSearchPath](pidtagabsearchpath-canonical-property.md)) property.</span></span> <span data-ttu-id="b33c9-153">_lpAdrList_参数中的条目包含已解决的收件人, 因为它们位于 MAPI 已被调用**ResolveNames**的容器中, 因为这些条目显示在搜索路径的前面。</span><span class="sxs-lookup"><span data-stu-id="b33c9-153">The entries in the  _lpAdrList_ parameter include recipients already resolved because they are in containers for which MAPI has already called **ResolveNames**, because the entries appear earlier in the search path.</span></span> 
  
<span data-ttu-id="b33c9-154">每个容器都尝试通过将收件人的显示名称与它的一个条目的显示名称相匹配来解析未解析的条目。</span><span class="sxs-lookup"><span data-stu-id="b33c9-154">Each container attempts to resolve the unresolved entries by matching the display name of the recipient with the display name of one of its entries.</span></span> <span data-ttu-id="b33c9-155">找到唯一匹配时, **ResolveNames**会将_lpPropTagArray_参数中包含的**PR_ENTRYID**属性和其他属性添加到传出**ADRLIST**结构中的相应条目。</span><span class="sxs-lookup"><span data-stu-id="b33c9-155">When a unique match is found, **ResolveNames** adds the **PR_ENTRYID** property and other properties that are included in the  _lpPropTagArray_ parameter to the corresponding entry in the outgoing **ADRLIST** structure.</span></span> <span data-ttu-id="b33c9-156">**ResolveNames**然后将_lpFlagList_参数中的条目设置为 MAPI_RESOLVED。</span><span class="sxs-lookup"><span data-stu-id="b33c9-156">**ResolveNames** then sets the entry in the  _lpFlagList_ parameter to MAPI_RESOLVED.</span></span> <span data-ttu-id="b33c9-157">存储在**PR_ENTRYID**属性中的条目标识符可以是短期的, 也可以是长期的。</span><span class="sxs-lookup"><span data-stu-id="b33c9-157">The entry identifier stored in the **PR_ENTRYID** property can be short-term or long-term.</span></span> 
  
<span data-ttu-id="b33c9-158">在搜索路径中的所有容器都试图进行名称解析过程之后, MAPI 将打开一个对话框, 以提示用户解决其余冲突的帮助信息。</span><span class="sxs-lookup"><span data-stu-id="b33c9-158">After all of the containers in the search path have attempted the name resolution process, MAPI opens a dialog box, if possible, to prompt the user for help in resolving any remaining conflicts.</span></span> 
  
<span data-ttu-id="b33c9-159">客户端也可以在对[IMessage:: ModifyRecipients](imessage-modifyrecipients.md)方法的调用中使用返回的**ADRLIST**结构。</span><span class="sxs-lookup"><span data-stu-id="b33c9-159">Clients can also use the returned **ADRLIST** structure in calls to the [IMessage::ModifyRecipients](imessage-modifyrecipients.md) method.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="b33c9-160">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="b33c9-160">Notes to implementers</span></span>

<span data-ttu-id="b33c9-161">不需要使用**ResolveNames**方法支持名称解析。</span><span class="sxs-lookup"><span data-stu-id="b33c9-161">You are not required to support name resolution with the **ResolveNames** method.</span></span> <span data-ttu-id="b33c9-162">相反, 或者, 也可以使用**PR_ANR** ([PidTagAnr](pidtaganr-canonical-property.md)) 属性限制来支持它。</span><span class="sxs-lookup"><span data-stu-id="b33c9-162">Instead, or additionally, you can support it with the **PR_ANR** ([PidTagAnr](pidtaganr-canonical-property.md)) property restriction.</span></span> <span data-ttu-id="b33c9-163">如果决定依赖**PR_ANR**限制进行名称解析, 则可以返回 MAPI_E_NO_SUPPORT。</span><span class="sxs-lookup"><span data-stu-id="b33c9-163">If you decide to rely on the **PR_ANR** restriction for name resolution, you can return MAPI_E_NO_SUPPORT.</span></span> <span data-ttu-id="b33c9-164">有关详细信息, 请参阅[实现名称解析](implementing-name-resolution.md)。</span><span class="sxs-lookup"><span data-stu-id="b33c9-164">For more information, see [Implementing Name Resolution](implementing-name-resolution.md).</span></span>
  
<span data-ttu-id="b33c9-165">如果收件人与容器的任何收件人都不匹配, 则将_lpFlagList_参数中的收件人的标志条目设置为 MAPI_UNRESOLVED。</span><span class="sxs-lookup"><span data-stu-id="b33c9-165">Set a recipient's flag entry in the  _lpFlagList_ parameter to MAPI_UNRESOLVED if the recipient does not match any of the container's recipients.</span></span> 
  
<span data-ttu-id="b33c9-166">当收件人匹配多个收件人时, 将其标志设置为 "MAPI_AMBIGUOUS", 并且不更改其**ADRENTRY**结构。</span><span class="sxs-lookup"><span data-stu-id="b33c9-166">When a recipient matches multiple recipients, set its flag to MAPI_AMBIGUOUS and do not change its **ADRENTRY** structure.</span></span> 
  
<span data-ttu-id="b33c9-167">对于邮件的收件人列表中包含的收件人, MAPI 需要特定的属性。</span><span class="sxs-lookup"><span data-stu-id="b33c9-167">MAPI requires certain properties for recipients that are included in a message's recipient list.</span></span> <span data-ttu-id="b33c9-168">您可以将它们作为名称解析过程的一部分包含在**ADRENTRY**结构中, 或等待 MAPI 请求调用[IAddrBook::P reparerecips](iaddrbook-preparerecips.md)和[IMAPISupport:: ExpandRecips](imapisupport-expandrecips.md)方法。</span><span class="sxs-lookup"><span data-stu-id="b33c9-168">You can include them in the **ADRENTRY** structure as part of the name resolution process or wait for MAPI to request them with calls to the [IAddrBook::PrepareRecips](iaddrbook-preparerecips.md) and [IMAPISupport::ExpandRecips](imapisupport-expandrecips.md) methods.</span></span> <span data-ttu-id="b33c9-169">您可以通过在所有解析的收件人的**ADRENTRY**结构中包括以下属性来消除这些额外的调用并提高性能。</span><span class="sxs-lookup"><span data-stu-id="b33c9-169">You can eliminate these extra calls and improve performance by including the following properties in the **ADRENTRY** structures of all resolved recipients:</span></span> 
  
- <span data-ttu-id="b33c9-170">**PR_ADDRTYPE**</span><span class="sxs-lookup"><span data-stu-id="b33c9-170">**PR_ADDRTYPE**</span></span>
    
- <span data-ttu-id="b33c9-171">**PR_DISPLAY_NAME**</span><span class="sxs-lookup"><span data-stu-id="b33c9-171">**PR_DISPLAY_NAME**</span></span>
    
- <span data-ttu-id="b33c9-172">**PR_EMAIL_ADDRESS**</span><span class="sxs-lookup"><span data-stu-id="b33c9-172">**PR_EMAIL_ADDRESS**</span></span>
    
- <span data-ttu-id="b33c9-173">**PR_ENTRYID**</span><span class="sxs-lookup"><span data-stu-id="b33c9-173">**PR_ENTRYID**</span></span>
    
- <span data-ttu-id="b33c9-174">**PR_OBJECT_TYPE**([PidTagObjectType](pidtagobjecttype-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="b33c9-174">**PR_OBJECT_TYPE** ([PidTagObjectType](pidtagobjecttype-canonical-property.md))</span></span>
    
- <span data-ttu-id="b33c9-175">**PR_SEARCH_KEY**([PidTagSearchKey](pidtagsearchkey-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="b33c9-175">**PR_SEARCH_KEY** ([PidTagSearchKey](pidtagsearchkey-canonical-property.md))</span></span>
    
- <span data-ttu-id="b33c9-176">**PR_TRANSMITABLE_DISPLAY_NAME**([PidTagTransmittableDisplayName](pidtagtransmittabledisplayname-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="b33c9-176">**PR_TRANSMITABLE_DISPLAY_NAME** ([PidTagTransmittableDisplayName](pidtagtransmittabledisplayname-canonical-property.md))</span></span>
    
<span data-ttu-id="b33c9-177">如果_lpPropTagArray_参数中的某些属性不可用 (通常是因为容器条目不支持属性, 并且它们不包含在**ADRLIST**结构的收件人的**ADRENTRY**成员中) 中。将每个不可用属性的属性类型设置为 PT_ERROR。</span><span class="sxs-lookup"><span data-stu-id="b33c9-177">If some of the properties in the  _lpPropTagArray_ parameter are unavailable—typically because the container entry does not support the properties and they are not included in the recipient's **ADRENTRY** member in the **ADRLIST** structure—set the property type of each unavailable property to PT_ERROR.</span></span> 
  
<span data-ttu-id="b33c9-178">请勿从解析的收件人的**ADRENTRY**结构中删除任何属性。</span><span class="sxs-lookup"><span data-stu-id="b33c9-178">Do not remove any properties from a resolved recipient's **ADRENTRY** structure.</span></span> 
  
<span data-ttu-id="b33c9-179">如果您必须替换而不是修改**ADRENTRY**结构, 请先通过调用[MAPIFreeBuffer](mapifreebuffer.md)函数释放原始**ADRENTRY**结构, 然后将替换的**ADRENTRY**结构[分配给MAPIAllocateBuffer](mapiallocatebuffer.md)。</span><span class="sxs-lookup"><span data-stu-id="b33c9-179">If you must replace rather than modify an **ADRENTRY** structure, free the original **ADRENTRY** structure first by calling the [MAPIFreeBuffer](mapifreebuffer.md) function, and then allocate the replacement **ADRENTRY** structure with [MAPIAllocateBuffer](mapiallocatebuffer.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="b33c9-180">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b33c9-180">See also</span></span>



[<span data-ttu-id="b33c9-181">ADRENTRY</span><span class="sxs-lookup"><span data-stu-id="b33c9-181">ADRENTRY</span></span>](adrentry.md)
  
[<span data-ttu-id="b33c9-182">ADRLIST</span><span class="sxs-lookup"><span data-stu-id="b33c9-182">ADRLIST</span></span>](adrlist.md)
  
[<span data-ttu-id="b33c9-183">IAddrBook::PrepareRecips</span><span class="sxs-lookup"><span data-stu-id="b33c9-183">IAddrBook::PrepareRecips</span></span>](iaddrbook-preparerecips.md)
  
[<span data-ttu-id="b33c9-184">IAddrBook::ResolveName</span><span class="sxs-lookup"><span data-stu-id="b33c9-184">IAddrBook::ResolveName</span></span>](iaddrbook-resolvename.md)
  
[<span data-ttu-id="b33c9-185">IMAPISupport::ExpandRecips</span><span class="sxs-lookup"><span data-stu-id="b33c9-185">IMAPISupport::ExpandRecips</span></span>](imapisupport-expandrecips.md)
  
[<span data-ttu-id="b33c9-186">IMessage::ModifyRecipients</span><span class="sxs-lookup"><span data-stu-id="b33c9-186">IMessage::ModifyRecipients</span></span>](imessage-modifyrecipients.md)
  
[<span data-ttu-id="b33c9-187">PidTagAnr 规范属性</span><span class="sxs-lookup"><span data-stu-id="b33c9-187">PidTagAnr Canonical Property</span></span>](pidtaganr-canonical-property.md)
  
[<span data-ttu-id="b33c9-188">SPropertyRestriction</span><span class="sxs-lookup"><span data-stu-id="b33c9-188">SPropertyRestriction</span></span>](spropertyrestriction.md)
  
[<span data-ttu-id="b33c9-189">IABContainer : IMAPIContainer</span><span class="sxs-lookup"><span data-stu-id="b33c9-189">IABContainer : IMAPIContainer</span></span>](iabcontainerimapicontainer.md)

