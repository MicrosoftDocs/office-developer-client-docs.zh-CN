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
ms.openlocfilehash: 3edcef69880dbc2a566a44582113c43802a47324
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775764"
---
# <a name="imessagemodifyrecipients"></a><span data-ttu-id="0e52c-103">IMessage::ModifyRecipients</span><span class="sxs-lookup"><span data-stu-id="0e52c-103">IMessage::ModifyRecipients</span></span>

  
  
<span data-ttu-id="0e52c-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="0e52c-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="0e52c-105">添加、 删除或修改邮件的收件人。</span><span class="sxs-lookup"><span data-stu-id="0e52c-105">Adds, deletes, or modifies message recipients.</span></span>
  
```cpp
HRESULT ModifyRecipients(
  ULONG ulFlags,
  LPADRLIST lpMods
);
```

## <a name="parameters"></a><span data-ttu-id="0e52c-106">参数</span><span class="sxs-lookup"><span data-stu-id="0e52c-106">Parameters</span></span>

 <span data-ttu-id="0e52c-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="0e52c-107">_ulFlags_</span></span>
  
> <span data-ttu-id="0e52c-108">[in]位掩码的标志，控件的收件人的更改。</span><span class="sxs-lookup"><span data-stu-id="0e52c-108">[in] Bitmask of flags that controls the recipient changes.</span></span> <span data-ttu-id="0e52c-109">如果为_ulFlags_参数传递零，则**ModifyRecipients**用_lpMods_参数指向的收件人列表替换所有现有收件人。</span><span class="sxs-lookup"><span data-stu-id="0e52c-109">If zero is passed for the  _ulFlags_ parameter, **ModifyRecipients** replaces all existing recipients with the recipient list pointed to by the  _lpMods_ parameter.</span></span> <span data-ttu-id="0e52c-110">可以为_ulFlags_设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="0e52c-110">The following flags can be set for  _ulFlags_:</span></span>
    
<span data-ttu-id="0e52c-111">MODRECIP_ADD</span><span class="sxs-lookup"><span data-stu-id="0e52c-111">MODRECIP_ADD</span></span> 
  
> <span data-ttu-id="0e52c-112">_LpMods_参数指向的收件人应添加到的收件人列表中。</span><span class="sxs-lookup"><span data-stu-id="0e52c-112">The recipients pointed to by the  _lpMods_ parameter should be added to the recipient list.</span></span> 
    
<span data-ttu-id="0e52c-113">MODRECIP_MODIFY</span><span class="sxs-lookup"><span data-stu-id="0e52c-113">MODRECIP_MODIFY</span></span> 
  
> <span data-ttu-id="0e52c-114">_LpMods_参数指向的收件人应替换现有的收件人。</span><span class="sxs-lookup"><span data-stu-id="0e52c-114">The recipients pointed to by the  _lpMods_ parameter should replace existing recipients.</span></span> <span data-ttu-id="0e52c-115">以免那些相应[ADRENTRY](adrentry.md)结构中替换所有现有属性。</span><span class="sxs-lookup"><span data-stu-id="0e52c-115">All of the existing properties are replaced by those in the corresponding [ADRENTRY](adrentry.md) structure.</span></span> 
    
<span data-ttu-id="0e52c-116">MODRECIP_REMOVE</span><span class="sxs-lookup"><span data-stu-id="0e52c-116">MODRECIP_REMOVE</span></span> 
  
> <span data-ttu-id="0e52c-117">应从作为索引使用**PR_ROWID** ([PidTagRowid](pidtagrowid-canonical-property.md)) 属性包含属性值数组_lpMods_参数中的每个收件人项中的收件人列表中删除现有收件人。</span><span class="sxs-lookup"><span data-stu-id="0e52c-117">Existing recipients should be removed from the recipient list using as an index the **PR_ROWID** ([PidTagRowid](pidtagrowid-canonical-property.md)) property included in the property value array of each recipient entry in the  _lpMods_ parameter.</span></span> 
    
 <span data-ttu-id="0e52c-118">_lpMods_</span><span class="sxs-lookup"><span data-stu-id="0e52c-118">_lpMods_</span></span>
  
> <span data-ttu-id="0e52c-119">[in]指向[ADRLIST](adrlist.md)结构，其中包含要添加、 删除或修改邮件中的收件人列表的指针。</span><span class="sxs-lookup"><span data-stu-id="0e52c-119">[in] Pointer to an [ADRLIST](adrlist.md) structure that contains a list of recipients to be added, deleted, or modified in the message.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="0e52c-120">返回值</span><span class="sxs-lookup"><span data-stu-id="0e52c-120">Return value</span></span>

<span data-ttu-id="0e52c-121">S_OK</span><span class="sxs-lookup"><span data-stu-id="0e52c-121">S_OK</span></span> 
  
> <span data-ttu-id="0e52c-122">已成功修改的收件人列表。</span><span class="sxs-lookup"><span data-stu-id="0e52c-122">The recipient list was successfully modified.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="0e52c-123">说明</span><span class="sxs-lookup"><span data-stu-id="0e52c-123">Remarks</span></span>

<span data-ttu-id="0e52c-124">**IMessage::ModifyRecipients**方法可更改邮件的收件人列表。</span><span class="sxs-lookup"><span data-stu-id="0e52c-124">The **IMessage::ModifyRecipients** method changes the message's recipient list.</span></span> <span data-ttu-id="0e52c-125">它是从该列表中，在[ADRLIST](adrlist.md)结构中，保留收件人表构建。</span><span class="sxs-lookup"><span data-stu-id="0e52c-125">It is from this list, held in an [ADRLIST](adrlist.md) structure, that the recipient table is built.</span></span> 
  
<span data-ttu-id="0e52c-126">**ADRLIST**结构包含一个[ADRENTRY](adrentry.md)结构，每个收件人，并且每个**ADRENTRY**结构包含描述收件人属性的属性值的数组。</span><span class="sxs-lookup"><span data-stu-id="0e52c-126">The **ADRLIST** structure contains one [ADRENTRY](adrentry.md) structure for each recipient and each **ADRENTRY** structure contains an array of property values describing the recipient properties.</span></span> 
  
<span data-ttu-id="0e52c-127">可以解析或无法解析**ADRLIST**结构中的收件人。</span><span class="sxs-lookup"><span data-stu-id="0e52c-127">Recipients in the **ADRLIST** structure can be resolved or unresolved.</span></span> <span data-ttu-id="0e52c-128">区别在于数量和类型所包含的属性。</span><span class="sxs-lookup"><span data-stu-id="0e52c-128">The difference is in the number and type of properties that are included.</span></span> <span data-ttu-id="0e52c-129">无法解析的收件人包含**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 和**PR_RECIPIENT_TYPE** ([PidTagRecipientType](pidtagrecipienttype-canonical-property.md)) 属性解析的收件人包含这些两个属性以及**PR_ADDRTYPE**([PidTagAddressType](pidtagaddresstype-canonical-property.md)) 和**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md))。</span><span class="sxs-lookup"><span data-stu-id="0e52c-129">An unresolved recipient contains only the **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) and **PR_RECIPIENT_TYPE** ([PidTagRecipientType](pidtagrecipienttype-canonical-property.md)) properties while a resolved recipient contains those two properties plus **PR_ADDRTYPE** ([PidTagAddressType](pidtagaddresstype-canonical-property.md)) and **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)).</span></span> <span data-ttu-id="0e52c-130">如果可用**PR_EMAIL_ADDRESS** ([PidTagEmailAddress](pidtagemailaddress-canonical-property.md))，它还可以包含这些属性。</span><span class="sxs-lookup"><span data-stu-id="0e52c-130">If **PR_EMAIL_ADDRESS** ([PidTagEmailAddress](pidtagemailaddress-canonical-property.md)) is available, it can be included also.</span></span>
  
<span data-ttu-id="0e52c-131">邮件提交时，它必须在其收件人列表中包含已解析的收件人。</span><span class="sxs-lookup"><span data-stu-id="0e52c-131">By the time a message is submitted, it must include only resolved recipients in its recipient list.</span></span> <span data-ttu-id="0e52c-132">未解析的收件人导致未送达报告创建和发送到邮件的原始发件人。</span><span class="sxs-lookup"><span data-stu-id="0e52c-132">Unresolved recipients cause nondelivery reports to be created and sent to the original sender of the message.</span></span> <span data-ttu-id="0e52c-133">有关从客户端角度名称解析过程的详细信息，请参阅[解析名称](resolving-a-recipient-name.md)。</span><span class="sxs-lookup"><span data-stu-id="0e52c-133">For more information about the name resolution process from the client perspective, see [Resolving a Name](resolving-a-recipient-name.md).</span></span> <span data-ttu-id="0e52c-134">从通讯簿提供程序的角度来看的详细信息，请参阅[实现名称解析](implementing-name-resolution.md)。</span><span class="sxs-lookup"><span data-stu-id="0e52c-134">For more information from the perspective of the address book provider, see [Implementing Name Resolution](implementing-name-resolution.md).</span></span>
  
<span data-ttu-id="0e52c-135">除了解析和未解析的收件人，收件人可以为 NULL。</span><span class="sxs-lookup"><span data-stu-id="0e52c-135">In addition to resolved and unresolved recipients, a recipient can be NULL.</span></span> <span data-ttu-id="0e52c-136">收件人的**ADRENTRY**结构的**cValues**成员设置为零，并且**rgPropVals**成员设置为 NULL。</span><span class="sxs-lookup"><span data-stu-id="0e52c-136">The **cValues** member of the **ADRENTRY** structure for the recipient is set to zero and the **rgPropVals** member is set to NULL.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="0e52c-137">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="0e52c-137">Notes to callers</span></span>

<span data-ttu-id="0e52c-138">您可以通过调用[IAddrBook::Address](imapisupport-address.md)以显示公共对话框，并提示用户选择条目创建收件人列表。</span><span class="sxs-lookup"><span data-stu-id="0e52c-138">You can create a recipient list by calling [IAddrBook::Address](imapisupport-address.md) to display the common dialog box and prompt the user to select entries.</span></span> <span data-ttu-id="0e52c-139">为**地址** _lppAdrList_参数指向的地址列表可以作为_lpMods_参数传递给**ModifyRecipients** 。</span><span class="sxs-lookup"><span data-stu-id="0e52c-139">The address list pointed to by the  _lppAdrList_ parameter to **Address** can be passed to **ModifyRecipients** as the  _lpMods_ parameter.</span></span> 
  
<span data-ttu-id="0e52c-140">[ADRLIST](adrlist.md)结构中的收件人的指定属性时，包括所有收件人的属性、 不仅新的或更改起来。</span><span class="sxs-lookup"><span data-stu-id="0e52c-140">When you specify properties for a recipient in the [ADRLIST](adrlist.md) structure, include all of the recipient's properties, not only the new or changed ones.</span></span> <span data-ttu-id="0e52c-141">修改收件人时，会删除**ADRLIST**结构中不包含任何属性。</span><span class="sxs-lookup"><span data-stu-id="0e52c-141">When a recipient is modified, any properties not included in the **ADRLIST** structure are deleted.</span></span> <span data-ttu-id="0e52c-142">若要检索所有邮件的收件人，当前的属性集，请调用[GetRecipientTable](imessage-getrecipienttable.md) ，并检索的所有行。</span><span class="sxs-lookup"><span data-stu-id="0e52c-142">To retrieve the current set of properties for all of a message's recipients, call [GetRecipientTable](imessage-getrecipienttable.md) and retrieve all of the rows.</span></span> <span data-ttu-id="0e52c-143">**ADRLIST**结构与**SRowSet** ，因为您可以交替使用它们。</span><span class="sxs-lookup"><span data-stu-id="0e52c-143">Because an **SRowSet** is identical in structure to an **ADRLIST**, you can use them interchangeably.</span></span>
  
 <span data-ttu-id="0e52c-144">**ModifyRecipients**将替换所有当前的收件人列表中的项所指的_lpMods_时无标志设置_ulFlags_参数中的信息。</span><span class="sxs-lookup"><span data-stu-id="0e52c-144">**ModifyRecipients** replaces all of the entries in the current recipient list with the information pointed to by  _lpMods_ when none of the flags are set in the  _ulFlags_ parameter.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="0e52c-145">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="0e52c-145">Notes to callers</span></span>

<span data-ttu-id="0e52c-146">当设置 MODRECIP_MODIFY 标志时， **ModifyRecipients**会将每个收件人的整行替换_lpMods_中传递的[ADRLIST](adrlist.md)结构中的关联行。</span><span class="sxs-lookup"><span data-stu-id="0e52c-146">When you set the MODRECIP_MODIFY flag, **ModifyRecipients** replaces each entire recipient row with the associated row in the [ADRLIST](adrlist.md) structure passed in  _lpMods_.</span></span> <span data-ttu-id="0e52c-147">请注意指定所有收件人都应有而不考虑它们是否已更改可防止意外删除的属性。</span><span class="sxs-lookup"><span data-stu-id="0e52c-147">Be careful to specify all of the properties that a recipient should have regardless of whether they have changed to prevent them from being unintentionally deleted.</span></span>
  
<span data-ttu-id="0e52c-148">下面是一些**ADRLIST**结构中设置属性的收件人的规则：</span><span class="sxs-lookup"><span data-stu-id="0e52c-148">Following are some rules for setting the properties of the recipients in the **ADRLIST** structure:</span></span> 
  
- <span data-ttu-id="0e52c-149">不要使用 PT_NULL 作为属性类型。</span><span class="sxs-lookup"><span data-stu-id="0e52c-149">Do not use PT_NULL as a property type.</span></span> <span data-ttu-id="0e52c-150">在遇到此值时， **ModifyRecipients**将返回错误。</span><span class="sxs-lookup"><span data-stu-id="0e52c-150">**ModifyRecipients** returns an error when encountering this value.</span></span> 
    
- <span data-ttu-id="0e52c-151">不要使用 PT_ERROR 作为属性类型。</span><span class="sxs-lookup"><span data-stu-id="0e52c-151">Do not use PT_ERROR as a property type.</span></span> <span data-ttu-id="0e52c-152">**ModifyRecipients**将忽略此值。</span><span class="sxs-lookup"><span data-stu-id="0e52c-152">**ModifyRecipients** ignores this value.</span></span> 
    
- <span data-ttu-id="0e52c-153">_UlFlags_中设置的 MODRECIP_REMOVE 或 MODRECIP_MODIFY 标志时，应包含所有收件人**PR_ROWID**属性。</span><span class="sxs-lookup"><span data-stu-id="0e52c-153">Include the **PR_ROWID** property for all recipients when you set either the MODRECIP_REMOVE or MODRECIP_MODIFY flag in  _ulFlags_.</span></span> 
    
- <span data-ttu-id="0e52c-154">不包括**PR_ROWID**属性的任何收件人时_ulFlags_或时传递零_ulFlags_中的设置 MODRECIP_ADD 标志。</span><span class="sxs-lookup"><span data-stu-id="0e52c-154">Do not include the **PR_ROWID** property for any of the recipients when you set the MODRECIP_ADD flag in  _ulFlags_ or when you pass zero in  _ulFlags_.</span></span>
    
<span data-ttu-id="0e52c-155">如果收件人和一个包括**PR_ADDRTYPE**属性或**PR_EMAIL_ADDRESS**属性或两个这些属性不一致的地址类型和由**PR_ENTRYID**，标识的收件人地址结果不确定。</span><span class="sxs-lookup"><span data-stu-id="0e52c-155">If you include either the **PR_ADDRTYPE** property or **PR_EMAIL_ADDRESS** property for a recipient and one or both of these properties are inconsistent with the address type and address of the recipient as identified by **PR_ENTRYID**, the results are undefined.</span></span> <span data-ttu-id="0e52c-156">即，有三种可能性，具体取决于服务提供商：</span><span class="sxs-lookup"><span data-stu-id="0e52c-156">That is, there are three possibilities, depending on the service provider:</span></span>
  
- <span data-ttu-id="0e52c-157">邮件将传递到**PR_ADDRTYPE**和**PR_EMAIL_ADDRESS**属性并由它们所述的地址。</span><span class="sxs-lookup"><span data-stu-id="0e52c-157">The message will be delivered to the address described by the **PR_ADDRTYPE** and **PR_EMAIL_ADDRESS** properties.</span></span> 
    
- <span data-ttu-id="0e52c-158">邮件将传递给收件人由**PR_ENTRYID**标识。</span><span class="sxs-lookup"><span data-stu-id="0e52c-158">The message will be delivered to the recipient identified by **PR_ENTRYID**.</span></span>
    
- <span data-ttu-id="0e52c-159">邮件将声明的地址信息歧义由于未送达。</span><span class="sxs-lookup"><span data-stu-id="0e52c-159">The message will be declared undeliverable due to the ambiguity of the address information.</span></span>
    
<span data-ttu-id="0e52c-160">使用[管理内存 ADRLIST 和 SRowSet 结构](managing-memory-for-adrlist-and-srowset-structures.md)中概述的分配规则的收件人列表为分配内存。</span><span class="sxs-lookup"><span data-stu-id="0e52c-160">Use the allocation rules outlined in [Managing Memory for ADRLIST and SRowSet Structures](managing-memory-for-adrlist-and-srowset-structures.md) to allocate memory for the recipient list.</span></span> <span data-ttu-id="0e52c-161">**ModifyRecipients**不释放**ADRLIST**结构也任何子结构。</span><span class="sxs-lookup"><span data-stu-id="0e52c-161">**ModifyRecipients** does not free the **ADRLIST** structure nor any of its substructures.</span></span> <span data-ttu-id="0e52c-162">**ADRLIST**结构和每个[SPropValue](spropvalue.md)结构必须单独分配使用[MAPIAllocateBuffer](mapiallocatebuffer.md)函数，以便可以单独释放每。</span><span class="sxs-lookup"><span data-stu-id="0e52c-162">The **ADRLIST** structure and each [SPropValue](spropvalue.md) structure must be separately allocated by using the [MAPIAllocateBuffer](mapiallocatebuffer.md) function such that each can be freed individually.</span></span> <span data-ttu-id="0e52c-163">如果方法的任何**SPropValue**结构需要额外的空间，它可以与一个更高版本可以通过使用[MAPIFreeBuffer](mapifreebuffer.md)释放的新替换**SPropValue**结构。</span><span class="sxs-lookup"><span data-stu-id="0e52c-163">If the method requires additional space for any **SPropValue** structure, it can replace the **SPropValue** structure with a new one that can later be freed using [MAPIFreeBuffer](mapifreebuffer.md).</span></span> <span data-ttu-id="0e52c-164">此外应使用**MAPIFreeBuffer**释放原始**SPropValue**结构。</span><span class="sxs-lookup"><span data-stu-id="0e52c-164">The original **SPropValue** structure should also be freed using **MAPIFreeBuffer**.</span></span>
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="0e52c-165">MFCMAPI 参考 （英文）</span><span class="sxs-lookup"><span data-stu-id="0e52c-165">MFCMAPI reference</span></span>

<span data-ttu-id="0e52c-166">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="0e52c-166">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="0e52c-167">**文件**</span><span class="sxs-lookup"><span data-stu-id="0e52c-167">**File**</span></span>|<span data-ttu-id="0e52c-168">**函数**</span><span class="sxs-lookup"><span data-stu-id="0e52c-168">**Function**</span></span>|<span data-ttu-id="0e52c-169">**Comment**</span><span class="sxs-lookup"><span data-stu-id="0e52c-169">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="0e52c-170">MAPIABFunctions.cpp</span><span class="sxs-lookup"><span data-stu-id="0e52c-170">MAPIABFunctions.cpp</span></span>  <br/> |<span data-ttu-id="0e52c-171">AddRecipient</span><span class="sxs-lookup"><span data-stu-id="0e52c-171">AddRecipient</span></span>  <br/> |<span data-ttu-id="0e52c-172">MFCMAPI 使用**IMessage::ModifyRecipients**方法将一个新收件人添加到一条消息。</span><span class="sxs-lookup"><span data-stu-id="0e52c-172">MFCMAPI uses the **IMessage::ModifyRecipients** method to add a new recipient to a message.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="0e52c-173">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0e52c-173">See also</span></span>



[<span data-ttu-id="0e52c-174">ADRENTRY</span><span class="sxs-lookup"><span data-stu-id="0e52c-174">ADRENTRY</span></span>](adrentry.md)
  
[<span data-ttu-id="0e52c-175">ADRLIST</span><span class="sxs-lookup"><span data-stu-id="0e52c-175">ADRLIST</span></span>](adrlist.md)
  
[<span data-ttu-id="0e52c-176">IAddrBook::Address</span><span class="sxs-lookup"><span data-stu-id="0e52c-176">IAddrBook::Address</span></span>](iaddrbook-address.md)
  
[<span data-ttu-id="0e52c-177">IMAPISupport::Address</span><span class="sxs-lookup"><span data-stu-id="0e52c-177">IMAPISupport::Address</span></span>](imapisupport-address.md)
  
[<span data-ttu-id="0e52c-178">MAPIAllocateBuffer</span><span class="sxs-lookup"><span data-stu-id="0e52c-178">MAPIAllocateBuffer</span></span>](mapiallocatebuffer.md)
  
[<span data-ttu-id="0e52c-179">MAPIFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="0e52c-179">MAPIFreeBuffer</span></span>](mapifreebuffer.md)
  
[<span data-ttu-id="0e52c-180">SPropValue</span><span class="sxs-lookup"><span data-stu-id="0e52c-180">SPropValue</span></span>](spropvalue.md)
  
[<span data-ttu-id="0e52c-181">IMessage : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="0e52c-181">IMessage : IMAPIProp</span></span>](imessageimapiprop.md)


[<span data-ttu-id="0e52c-182">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="0e52c-182">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

