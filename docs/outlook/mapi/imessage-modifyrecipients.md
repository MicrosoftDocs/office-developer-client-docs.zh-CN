---
title: IMessageModifyRecipients
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMessage.ModifyRecipients
api_type:
- COM
ms.assetid: 2625f29d-325f-417d-bcec-49d580f9cd7e
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 07e1c2104068a6eb242e8ba81f91655edaa92cd8
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33426238"
---
# <a name="imessagemodifyrecipients"></a><span data-ttu-id="6be82-103">IMessage::ModifyRecipients</span><span class="sxs-lookup"><span data-stu-id="6be82-103">IMessage::ModifyRecipients</span></span>

  
  
<span data-ttu-id="6be82-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="6be82-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="6be82-105">添加、删除或修改邮件收件人。</span><span class="sxs-lookup"><span data-stu-id="6be82-105">Adds, deletes, or modifies message recipients.</span></span>
  
```cpp
HRESULT ModifyRecipients(
  ULONG ulFlags,
  LPADRLIST lpMods
);
```

## <a name="parameters"></a><span data-ttu-id="6be82-106">参数</span><span class="sxs-lookup"><span data-stu-id="6be82-106">Parameters</span></span>

 <span data-ttu-id="6be82-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="6be82-107">_ulFlags_</span></span>
  
> <span data-ttu-id="6be82-108">[in]控制收件人更改的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="6be82-108">[in] Bitmask of flags that controls the recipient changes.</span></span> <span data-ttu-id="6be82-109">如果为  _ulFlags_ 参数传递零 **，ModifyRecipients** 将用  _lpMods_ 参数指向的收件人列表替换所有现有收件人。</span><span class="sxs-lookup"><span data-stu-id="6be82-109">If zero is passed for the  _ulFlags_ parameter, **ModifyRecipients** replaces all existing recipients with the recipient list pointed to by the  _lpMods_ parameter.</span></span> <span data-ttu-id="6be82-110">可以为  _ulFlags_ 设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="6be82-110">The following flags can be set for  _ulFlags_:</span></span>
    
<span data-ttu-id="6be82-111">MODRECIP_ADD</span><span class="sxs-lookup"><span data-stu-id="6be82-111">MODRECIP_ADD</span></span> 
  
> <span data-ttu-id="6be82-112">_lpMods_ 参数指向的收件人应添加到收件人列表中。</span><span class="sxs-lookup"><span data-stu-id="6be82-112">The recipients pointed to by the  _lpMods_ parameter should be added to the recipient list.</span></span> 
    
<span data-ttu-id="6be82-113">MODRECIP_MODIFY</span><span class="sxs-lookup"><span data-stu-id="6be82-113">MODRECIP_MODIFY</span></span> 
  
> <span data-ttu-id="6be82-114">_lpMods_ 参数指向的收件人应替换现有收件人。</span><span class="sxs-lookup"><span data-stu-id="6be82-114">The recipients pointed to by the  _lpMods_ parameter should replace existing recipients.</span></span> <span data-ttu-id="6be82-115">所有现有属性都替换为相应的 [ADRENTRY 结构中](adrentry.md) 的属性。</span><span class="sxs-lookup"><span data-stu-id="6be82-115">All of the existing properties are replaced by those in the corresponding [ADRENTRY](adrentry.md) structure.</span></span> 
    
<span data-ttu-id="6be82-116">MODRECIP_REMOVE</span><span class="sxs-lookup"><span data-stu-id="6be82-116">MODRECIP_REMOVE</span></span> 
  
> <span data-ttu-id="6be82-117">应该将 _lpMods_ 参数中每个收件人条目的属性值数组中包含的 **PR_ROWID** ([PidTagRowid](pidtagrowid-canonical-property.md)) 属性用作索引，从收件人列表中删除现有收件人。</span><span class="sxs-lookup"><span data-stu-id="6be82-117">Existing recipients should be removed from the recipient list using as an index the **PR_ROWID** ([PidTagRowid](pidtagrowid-canonical-property.md)) property included in the property value array of each recipient entry in the  _lpMods_ parameter.</span></span> 
    
 <span data-ttu-id="6be82-118">_lpMods_</span><span class="sxs-lookup"><span data-stu-id="6be82-118">_lpMods_</span></span>
  
> <span data-ttu-id="6be82-119">[in]指向包含邮件中要添加、删除或修改的收件人列表的 [ADRLIST](adrlist.md) 结构的指针。</span><span class="sxs-lookup"><span data-stu-id="6be82-119">[in] Pointer to an [ADRLIST](adrlist.md) structure that contains a list of recipients to be added, deleted, or modified in the message.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="6be82-120">返回值</span><span class="sxs-lookup"><span data-stu-id="6be82-120">Return value</span></span>

<span data-ttu-id="6be82-121">S_OK</span><span class="sxs-lookup"><span data-stu-id="6be82-121">S_OK</span></span> 
  
> <span data-ttu-id="6be82-122">已成功修改收件人列表。</span><span class="sxs-lookup"><span data-stu-id="6be82-122">The recipient list was successfully modified.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="6be82-123">备注</span><span class="sxs-lookup"><span data-stu-id="6be82-123">Remarks</span></span>

<span data-ttu-id="6be82-124">**IMessage：：ModifyRecipients** 方法更改邮件的收件人列表。</span><span class="sxs-lookup"><span data-stu-id="6be82-124">The **IMessage::ModifyRecipients** method changes the message's recipient list.</span></span> <span data-ttu-id="6be82-125">收件人表是在 [ADRLIST](adrlist.md) 结构中基于此列表构建的。</span><span class="sxs-lookup"><span data-stu-id="6be82-125">It is from this list, held in an [ADRLIST](adrlist.md) structure, that the recipient table is built.</span></span> 
  
<span data-ttu-id="6be82-126">**ADRLIST** 结构包含每个收件人的一个 [ADRENTRY](adrentry.md)结构，而每个 **ADRENTRY** 结构包含描述收件人属性的属性值数组。</span><span class="sxs-lookup"><span data-stu-id="6be82-126">The **ADRLIST** structure contains one [ADRENTRY](adrentry.md) structure for each recipient and each **ADRENTRY** structure contains an array of property values describing the recipient properties.</span></span> 
  
<span data-ttu-id="6be82-127">**ADRLIST** 结构的收件人可以解析或解析。</span><span class="sxs-lookup"><span data-stu-id="6be82-127">Recipients in the **ADRLIST** structure can be resolved or unresolved.</span></span> <span data-ttu-id="6be82-128">区别在于所包含属性的数量和类型。</span><span class="sxs-lookup"><span data-stu-id="6be82-128">The difference is in the number and type of properties that are included.</span></span> <span data-ttu-id="6be82-129">未解析的收件人仅包含 **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 和 **PR_RECIPIENT_TYPE** ([PidTagRecipientType](pidtagrecipienttype-canonical-property.md)) 属性，而解析的收件人包含这两个属性以及 **PR_ADDRTYPE** ([PidTagAddressType](pidtagaddresstype-canonical-property.md)) 和 **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 。</span><span class="sxs-lookup"><span data-stu-id="6be82-129">An unresolved recipient contains only the **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) and **PR_RECIPIENT_TYPE** ([PidTagRecipientType](pidtagrecipienttype-canonical-property.md)) properties while a resolved recipient contains those two properties plus **PR_ADDRTYPE** ([PidTagAddressType](pidtagaddresstype-canonical-property.md)) and **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)).</span></span> <span data-ttu-id="6be82-130">如果 **PR_EMAIL_ADDRESS (** PidTagEmailAddress) 可用，则还可以包含该 [PidTagEmailAddress。](pidtagemailaddress-canonical-property.md)</span><span class="sxs-lookup"><span data-stu-id="6be82-130">If **PR_EMAIL_ADDRESS** ([PidTagEmailAddress](pidtagemailaddress-canonical-property.md)) is available, it can be included also.</span></span>
  
<span data-ttu-id="6be82-131">在提交邮件时，邮件必须仅包括收件人列表中已解析的收件人。</span><span class="sxs-lookup"><span data-stu-id="6be82-131">By the time a message is submitted, it must include only resolved recipients in its recipient list.</span></span> <span data-ttu-id="6be82-132">未解析的收件人会导致创建未送达报告，并发送给邮件的原始发件人。</span><span class="sxs-lookup"><span data-stu-id="6be82-132">Unresolved recipients cause nondelivery reports to be created and sent to the original sender of the message.</span></span> <span data-ttu-id="6be82-133">有关从客户端角度解析名称过程的信息，请参阅 [解析名称](resolving-a-recipient-name.md)。</span><span class="sxs-lookup"><span data-stu-id="6be82-133">For more information about the name resolution process from the client perspective, see [Resolving a Name](resolving-a-recipient-name.md).</span></span> <span data-ttu-id="6be82-134">有关通讯簿提供程序方面的信息，请参阅 [实现名称解析](implementing-name-resolution.md)。</span><span class="sxs-lookup"><span data-stu-id="6be82-134">For more information from the perspective of the address book provider, see [Implementing Name Resolution](implementing-name-resolution.md).</span></span>
  
<span data-ttu-id="6be82-135">除了解析和未解析的收件人之外，收件人还可以为 NULL。</span><span class="sxs-lookup"><span data-stu-id="6be82-135">In addition to resolved and unresolved recipients, a recipient can be NULL.</span></span> <span data-ttu-id="6be82-136">收件人 **的 ADRENTRY** 结构的 **cValues** 成员设置为零 **，rgPropVals** 成员设置为 NULL。</span><span class="sxs-lookup"><span data-stu-id="6be82-136">The **cValues** member of the **ADRENTRY** structure for the recipient is set to zero and the **rgPropVals** member is set to NULL.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="6be82-137">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="6be82-137">Notes to callers</span></span>

<span data-ttu-id="6be82-138">您可以通过调用 [IAddrBook：：Address](imapisupport-address.md) 来显示公用对话框并提示用户选择条目来创建收件人列表。</span><span class="sxs-lookup"><span data-stu-id="6be82-138">You can create a recipient list by calling [IAddrBook::Address](imapisupport-address.md) to display the common dialog box and prompt the user to select entries.</span></span> <span data-ttu-id="6be82-139">_lppAdrList_ 参数指向 **Address** 的地址列表可以作为 _lpMods_ 参数传递给 **ModifyRecipients。**</span><span class="sxs-lookup"><span data-stu-id="6be82-139">The address list pointed to by the  _lppAdrList_ parameter to **Address** can be passed to **ModifyRecipients** as the  _lpMods_ parameter.</span></span> 
  
<span data-ttu-id="6be82-140">在 [ADRLIST](adrlist.md) 结构中指定收件人的属性时，请包含收件人的所有属性，而不仅是新的或已更改的属性。</span><span class="sxs-lookup"><span data-stu-id="6be82-140">When you specify properties for a recipient in the [ADRLIST](adrlist.md) structure, include all of the recipient's properties, not only the new or changed ones.</span></span> <span data-ttu-id="6be82-141">修改收件人时，将删除 **ADRLIST** 结构中未包括的任何属性。</span><span class="sxs-lookup"><span data-stu-id="6be82-141">When a recipient is modified, any properties not included in the **ADRLIST** structure are deleted.</span></span> <span data-ttu-id="6be82-142">若要检索邮件的所有收件人的当前属性集，请调用 [GetRecipientTable](imessage-getrecipienttable.md) 并检索所有行。</span><span class="sxs-lookup"><span data-stu-id="6be82-142">To retrieve the current set of properties for all of a message's recipients, call [GetRecipientTable](imessage-getrecipienttable.md) and retrieve all of the rows.</span></span> <span data-ttu-id="6be82-143">由于 **SRowSet** 的结构与 **ADRLIST** 相同，因此可以互换使用。</span><span class="sxs-lookup"><span data-stu-id="6be82-143">Because an **SRowSet** is identical in structure to an **ADRLIST**, you can use them interchangeably.</span></span>
  
 <span data-ttu-id="6be82-144">当 _ulFlags_ 参数中没有设置任何标志时 **，ModifyRecipients** 会用 _lpMods_ 指向的信息替换当前收件人列表中的所有条目。</span><span class="sxs-lookup"><span data-stu-id="6be82-144">**ModifyRecipients** replaces all of the entries in the current recipient list with the information pointed to by  _lpMods_ when none of the flags are set in the  _ulFlags_ parameter.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="6be82-145">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="6be82-145">Notes to callers</span></span>

<span data-ttu-id="6be82-146">当您设置 MODRECIP_MODIFY 标志时 **，ModifyRecipients** 会用传入 _lpMods_ 的 [ADRLIST](adrlist.md)结构中的关联行替换每个收件人行。</span><span class="sxs-lookup"><span data-stu-id="6be82-146">When you set the MODRECIP_MODIFY flag, **ModifyRecipients** replaces each entire recipient row with the associated row in the [ADRLIST](adrlist.md) structure passed in  _lpMods_.</span></span> <span data-ttu-id="6be82-147">请注意指定收件人应具有的所有属性，无论这些属性是否已更改以防止意外删除。</span><span class="sxs-lookup"><span data-stu-id="6be82-147">Be careful to specify all of the properties that a recipient should have regardless of whether they have changed to prevent them from being unintentionally deleted.</span></span>
  
<span data-ttu-id="6be82-148">以下是在 **ADRLIST** 结构中设置收件人属性的一些规则：</span><span class="sxs-lookup"><span data-stu-id="6be82-148">Following are some rules for setting the properties of the recipients in the **ADRLIST** structure:</span></span> 
  
- <span data-ttu-id="6be82-149">请勿将PT_NULL用作属性类型。</span><span class="sxs-lookup"><span data-stu-id="6be82-149">Do not use PT_NULL as a property type.</span></span> <span data-ttu-id="6be82-150">**ModifyRecipients** 在遇到此值时返回错误。</span><span class="sxs-lookup"><span data-stu-id="6be82-150">**ModifyRecipients** returns an error when encountering this value.</span></span> 
    
- <span data-ttu-id="6be82-151">请勿将PT_ERROR用作属性类型。</span><span class="sxs-lookup"><span data-stu-id="6be82-151">Do not use PT_ERROR as a property type.</span></span> <span data-ttu-id="6be82-152">**ModifyRecipients** 将忽略此值。</span><span class="sxs-lookup"><span data-stu-id="6be82-152">**ModifyRecipients** ignores this value.</span></span> 
    
- <span data-ttu-id="6be82-153">在 _ulFlags_ **PR_ROWID** 设置 MODRECIP_REMOVE 或 MODRECIP_MODIFY 标记时，包括所有收件人的 MODRECIP_REMOVE 属性。</span><span class="sxs-lookup"><span data-stu-id="6be82-153">Include the **PR_ROWID** property for all recipients when you set either the MODRECIP_REMOVE or MODRECIP_MODIFY flag in  _ulFlags_.</span></span> 
    
- <span data-ttu-id="6be82-154">在 ulFlags **中** 设置 MODRECIP_ADD 标志或在  _ulFlags_ 中传递零时，请勿包含任何收件人的  _PR_ROWID 属性_。</span><span class="sxs-lookup"><span data-stu-id="6be82-154">Do not include the **PR_ROWID** property for any of the recipients when you set the MODRECIP_ADD flag in  _ulFlags_ or when you pass zero in  _ulFlags_.</span></span>
    
<span data-ttu-id="6be82-155">如果包含收件人的 **PR_ADDRTYPE** 属性或 **PR_EMAIL_ADDRESS** 属性，并且其中一个或两个属性与 PR_ENTRYID 标识的收件人的地址类型和地址不一致，则结果 **未** 定义。</span><span class="sxs-lookup"><span data-stu-id="6be82-155">If you include either the **PR_ADDRTYPE** property or **PR_EMAIL_ADDRESS** property for a recipient and one or both of these properties are inconsistent with the address type and address of the recipient as identified by **PR_ENTRYID**, the results are undefined.</span></span> <span data-ttu-id="6be82-156">也就是说，有三种可能性，具体取决于服务提供商：</span><span class="sxs-lookup"><span data-stu-id="6be82-156">That is, there are three possibilities, depending on the service provider:</span></span>
  
- <span data-ttu-id="6be82-157">邮件将传递到由属性和属性PR_ADDRTYPE PR_EMAIL_ADDRESS地址。 </span><span class="sxs-lookup"><span data-stu-id="6be82-157">The message will be delivered to the address described by the **PR_ADDRTYPE** and **PR_EMAIL_ADDRESS** properties.</span></span> 
    
- <span data-ttu-id="6be82-158">邮件将传递给由收件人标识的 **PR_ENTRYID。**</span><span class="sxs-lookup"><span data-stu-id="6be82-158">The message will be delivered to the recipient identified by **PR_ENTRYID**.</span></span>
    
- <span data-ttu-id="6be82-159">由于地址信息不明确，邮件将被声明为无法送达。</span><span class="sxs-lookup"><span data-stu-id="6be82-159">The message will be declared undeliverable due to the ambiguity of the address information.</span></span>
    
<span data-ttu-id="6be82-160">使用管理 [ADRLIST 和 SRowSet](managing-memory-for-adrlist-and-srowset-structures.md) 结构的内存中概述的分配规则为收件人列表分配内存。</span><span class="sxs-lookup"><span data-stu-id="6be82-160">Use the allocation rules outlined in [Managing Memory for ADRLIST and SRowSet Structures](managing-memory-for-adrlist-and-srowset-structures.md) to allocate memory for the recipient list.</span></span> <span data-ttu-id="6be82-161">**ModifyRecipients** 不会释放 **ADRLIST** 结构及其任何子结构。</span><span class="sxs-lookup"><span data-stu-id="6be82-161">**ModifyRecipients** does not free the **ADRLIST** structure nor any of its substructures.</span></span> <span data-ttu-id="6be82-162">必须使用 [MAPIAllocateBuffer](mapiallocatebuffer.md)函数单独分配 **ADRLIST** 结构和每个 [SPropValue](spropvalue.md)结构，这样可以单独释放每个结构。</span><span class="sxs-lookup"><span data-stu-id="6be82-162">The **ADRLIST** structure and each [SPropValue](spropvalue.md) structure must be separately allocated by using the [MAPIAllocateBuffer](mapiallocatebuffer.md) function such that each can be freed individually.</span></span> <span data-ttu-id="6be82-163">如果该方法需要任何 **SPropValue** 结构的附加空间，它可以将 **SPropValue** 结构替换为一个新结构，稍后可以使用 [MAPIFreeBuffer](mapifreebuffer.md)释放该结构。</span><span class="sxs-lookup"><span data-stu-id="6be82-163">If the method requires additional space for any **SPropValue** structure, it can replace the **SPropValue** structure with a new one that can later be freed using [MAPIFreeBuffer](mapifreebuffer.md).</span></span> <span data-ttu-id="6be82-164">还应该使用 **MAPIFreeBuffer** 释放原始 **SPropValue** 结构。</span><span class="sxs-lookup"><span data-stu-id="6be82-164">The original **SPropValue** structure should also be freed using **MAPIFreeBuffer**.</span></span>
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="6be82-165">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="6be82-165">MFCMAPI reference</span></span>

<span data-ttu-id="6be82-166">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="6be82-166">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="6be82-167">**文件**</span><span class="sxs-lookup"><span data-stu-id="6be82-167">**File**</span></span>|<span data-ttu-id="6be82-168">**函数**</span><span class="sxs-lookup"><span data-stu-id="6be82-168">**Function**</span></span>|<span data-ttu-id="6be82-169">**备注**</span><span class="sxs-lookup"><span data-stu-id="6be82-169">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="6be82-170">MAPIABFunctions.cpp</span><span class="sxs-lookup"><span data-stu-id="6be82-170">MAPIABFunctions.cpp</span></span>  <br/> |<span data-ttu-id="6be82-171">AddRecipient</span><span class="sxs-lookup"><span data-stu-id="6be82-171">AddRecipient</span></span>  <br/> |<span data-ttu-id="6be82-172">MFCMAPI 使用 **IMessage：：ModifyRecipients** 方法向邮件添加新收件人。</span><span class="sxs-lookup"><span data-stu-id="6be82-172">MFCMAPI uses the **IMessage::ModifyRecipients** method to add a new recipient to a message.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="6be82-173">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6be82-173">See also</span></span>



[<span data-ttu-id="6be82-174">ADRENTRY</span><span class="sxs-lookup"><span data-stu-id="6be82-174">ADRENTRY</span></span>](adrentry.md)
  
[<span data-ttu-id="6be82-175">ADRLIST</span><span class="sxs-lookup"><span data-stu-id="6be82-175">ADRLIST</span></span>](adrlist.md)
  
[<span data-ttu-id="6be82-176">IAddrBook::Address</span><span class="sxs-lookup"><span data-stu-id="6be82-176">IAddrBook::Address</span></span>](iaddrbook-address.md)
  
[<span data-ttu-id="6be82-177">IMAPISupport::Address</span><span class="sxs-lookup"><span data-stu-id="6be82-177">IMAPISupport::Address</span></span>](imapisupport-address.md)
  
[<span data-ttu-id="6be82-178">MAPIAllocateBuffer</span><span class="sxs-lookup"><span data-stu-id="6be82-178">MAPIAllocateBuffer</span></span>](mapiallocatebuffer.md)
  
[<span data-ttu-id="6be82-179">MAPIFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="6be82-179">MAPIFreeBuffer</span></span>](mapifreebuffer.md)
  
[<span data-ttu-id="6be82-180">SPropValue</span><span class="sxs-lookup"><span data-stu-id="6be82-180">SPropValue</span></span>](spropvalue.md)
  
[<span data-ttu-id="6be82-181">IMessage : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="6be82-181">IMessage : IMAPIProp</span></span>](imessageimapiprop.md)


[<span data-ttu-id="6be82-182">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="6be82-182">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

