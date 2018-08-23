---
title: IMAPISupportAddress
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISupport.Address
api_type:
- COM
ms.assetid: 8c22547e-ddf5-47f7-aed3-76e3854688df
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 524bbfe5f40a66585fb4ed4463b057ca6a0c881a
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22586800"
---
# <a name="imapisupportaddress"></a><span data-ttu-id="10970-103">IMAPISupport::Address</span><span class="sxs-lookup"><span data-stu-id="10970-103">IMAPISupport::Address</span></span>

  
  
<span data-ttu-id="10970-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="10970-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="10970-105">显示通用的地址对话框。</span><span class="sxs-lookup"><span data-stu-id="10970-105">Displays the common address dialog box.</span></span> 
  
```cpp
HRESULT Address(
  ULONG_PTR FAR * lpulUIParam,
  LPADRPARM lpAdrParms,
  LPADRLIST FAR * lppAdrList
);
```

## <a name="parameters"></a><span data-ttu-id="10970-106">参数</span><span class="sxs-lookup"><span data-stu-id="10970-106">Parameters</span></span>

 <span data-ttu-id="10970-107">_lpulUIParam_</span><span class="sxs-lookup"><span data-stu-id="10970-107">_lpulUIParam_</span></span>
  
> <span data-ttu-id="10970-108">[传入、 传出]指向对话框中的父窗口的句柄的指针。</span><span class="sxs-lookup"><span data-stu-id="10970-108">[in, out] A pointer to the handle of the parent window of the dialog box.</span></span> <span data-ttu-id="10970-109">在输入时，必须始终传递窗口句柄。</span><span class="sxs-lookup"><span data-stu-id="10970-109">On input, a window handle must always be passed.</span></span> <span data-ttu-id="10970-110">输出，如果 DIALOG_SDI 标志设置在[ADRPARM](adrparm.md)结构中所指的_lpAdrParms_参数，则返回无模式对话框的窗口句柄。</span><span class="sxs-lookup"><span data-stu-id="10970-110">On output, if the DIALOG_SDI flag is set in the [ADRPARM](adrparm.md) structure pointed to by the  _lpAdrParms_ parameter, the window handle of the modeless dialog box is returned.</span></span> 
    
 <span data-ttu-id="10970-111">_lpAdrParms_</span><span class="sxs-lookup"><span data-stu-id="10970-111">_lpAdrParms_</span></span>
  
> <span data-ttu-id="10970-112">[传入、 传出]指向控制的演示文稿和行为的地址对话框的**ADRPARM**结构的指针。</span><span class="sxs-lookup"><span data-stu-id="10970-112">[in, out] A pointer to an **ADRPARM** structure that controls the presentation and behavior of the address dialog box.</span></span> 
    
 <span data-ttu-id="10970-113">_lppAdrList_</span><span class="sxs-lookup"><span data-stu-id="10970-113">_lppAdrList_</span></span>
  
> <span data-ttu-id="10970-114">[传入、 传出]指向地址列表的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="10970-114">[in, out] A pointer to a pointer to an address list.</span></span> <span data-ttu-id="10970-115">在输入时，此列表可是当前列表的邮件中的收件人或 NULL，如果不存在任何此类列表。</span><span class="sxs-lookup"><span data-stu-id="10970-115">On input, this list is either the current list of recipients in a message or NULL, if no such list exists.</span></span> <span data-ttu-id="10970-116">输出， _lppAdrList_指向经过更新的邮件的收件人列表。</span><span class="sxs-lookup"><span data-stu-id="10970-116">On output,  _lppAdrList_ points to an updated list of message recipients.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="10970-117">返回值</span><span class="sxs-lookup"><span data-stu-id="10970-117">Return value</span></span>

<span data-ttu-id="10970-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="10970-118">S_OK</span></span> 
  
> <span data-ttu-id="10970-119">已成功地显示地址对话框。</span><span class="sxs-lookup"><span data-stu-id="10970-119">The address dialog box was successfully displayed.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="10970-120">注解</span><span class="sxs-lookup"><span data-stu-id="10970-120">Remarks</span></span>

<span data-ttu-id="10970-121">对于通讯簿提供程序支持对象实现**IMAPISupport::Address**方法。</span><span class="sxs-lookup"><span data-stu-id="10970-121">The **IMAPISupport::Address** method is implemented for address book provider support objects.</span></span> <span data-ttu-id="10970-122">通讯簿提供程序调用要创建或更新的邮件的收件人列表的**地址**。</span><span class="sxs-lookup"><span data-stu-id="10970-122">Address book providers call **Address** to create or update a list of message recipients.</span></span> 
  
<span data-ttu-id="10970-123">包括在[ADRLIST](adrlist.md)结构_lppAdrList_参数指向[ADRENTRY](adrentry.md)结构中介绍了每个收件人。</span><span class="sxs-lookup"><span data-stu-id="10970-123">Each recipient is described in an [ADRENTRY](adrentry.md) structure that is included in the [ADRLIST](adrlist.md) structure pointed to by the  _lppAdrList_ parameter.</span></span> <span data-ttu-id="10970-124">**ADRENTRY**结构包含收件人属性值数组，其中之一是收件人的类型或**PR_RECIPIENT_TYPE** ([PidTagRecipientType](pidtagrecipienttype-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="10970-124">The **ADRENTRY** structure contains an array of recipient property values, one of which is the recipient's type, or **PR_RECIPIENT_TYPE** ([PidTagRecipientType](pidtagrecipienttype-canonical-property.md)) property.</span></span> <span data-ttu-id="10970-125">此**ADRLIST**结构可以传递给客户端使用作为[IMessage::ModifyRecipients](imessage-modifyrecipients.md)将调用_lpMods_参数。</span><span class="sxs-lookup"><span data-stu-id="10970-125">This **ADRLIST** structure can be passed to a client to use as the  _lpMods_ parameter in a call to [IMessage::ModifyRecipients](imessage-modifyrecipients.md).</span></span>
  
<span data-ttu-id="10970-126">**ADRLIST**结构中的每个收件人可以可以解析，指示其属性值之一是其**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 属性，或无法解析，指示**PR_ENTRYID**属性缺少。</span><span class="sxs-lookup"><span data-stu-id="10970-126">Each recipient in the **ADRLIST** structure can be either resolved, which indicates that one of its property values is its **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) property, or unresolved, which indicates that the **PR_ENTRYID** property is missing.</span></span> 
  
<span data-ttu-id="10970-127">除了**PR_ENTRYID**，已解析的收件人包括以下属性：</span><span class="sxs-lookup"><span data-stu-id="10970-127">In addition to **PR_ENTRYID**, resolved recipients include the following properties:</span></span>
  
- <span data-ttu-id="10970-128">**PR_RECIPIENT_TYPE**</span><span class="sxs-lookup"><span data-stu-id="10970-128">**PR_RECIPIENT_TYPE**</span></span>
    
- <span data-ttu-id="10970-129">**PR_DISPLAY_NAME**([PidTagDisplayName](pidtagdisplayname-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="10970-129">**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md))</span></span>
    
- <span data-ttu-id="10970-130">**PR_ADDRTYPE**([PidTagAddressType](pidtagaddresstype-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="10970-130">**PR_ADDRTYPE** ([PidTagAddressType](pidtagaddresstype-canonical-property.md))</span></span>
    
- <span data-ttu-id="10970-131">**PR_DISPLAY_TYPE**([PidTagDisplayType](pidtagdisplaytype-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="10970-131">**PR_DISPLAY_TYPE** ([PidTagDisplayType](pidtagdisplaytype-canonical-property.md))</span></span>
    
<span data-ttu-id="10970-132">未解析的收件人通常包括只有**PR_DISPLAY_NAME**和**PR_RECIPIENT_TYPE**。</span><span class="sxs-lookup"><span data-stu-id="10970-132">Unresolved recipients typically include only **PR_DISPLAY_NAME** and **PR_RECIPIENT_TYPE**.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="10970-133">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="10970-133">Notes to callers</span></span>

<span data-ttu-id="10970-134">传入呼叫者的**ADRLIST**结构可能从结构的 MAPI 返回不同的大小。</span><span class="sxs-lookup"><span data-stu-id="10970-134">The **ADRLIST** structure that the caller passes in might be a different size from the structure that MAPI returns.</span></span> <span data-ttu-id="10970-135">当您为**ADRLIST**结构分配内存时，将单独为每个[SPropValue](spropvalue.md)结构分配内存。</span><span class="sxs-lookup"><span data-stu-id="10970-135">When you allocate memory for the **ADRLIST** structure, allocate the memory for each [SPropValue](spropvalue.md) structure separately.</span></span> 
  
<span data-ttu-id="10970-136">使用 MAPI 内存分配功能在传递给[ABProviderInit](abproviderinit.md)函数指针分配内存。</span><span class="sxs-lookup"><span data-stu-id="10970-136">Use the pointers to the MAPI memory allocation functions passed in to your [ABProviderInit](abproviderinit.md) function to allocate memory.</span></span> <span data-ttu-id="10970-137">**ADRLIST**和中**ADRLIST** **ADRENTRY**结构中的每个属性值结构分配[MAPIAllocateBuffer](mapiallocatebuffer.md)函数使用的内存。</span><span class="sxs-lookup"><span data-stu-id="10970-137">Allocate memory with the [MAPIAllocateBuffer](mapiallocatebuffer.md) function for **ADRLIST** and each property value structure in the **ADRENTRY** structures in **ADRLIST**.</span></span> 
  
<span data-ttu-id="10970-138">如果**地址**必须返回较大的**ADRLIST**结构，或者如果您已为_lppAdrList_传递 NULL，**地址**释放原始结构，并分配一个新。</span><span class="sxs-lookup"><span data-stu-id="10970-138">If **Address** must return a larger **ADRLIST** structure, or if you have passed NULL for  _lppAdrList_, **Address** frees the original structure and allocates a new one.</span></span> <span data-ttu-id="10970-139">**地址**还分配**ADRLIST**结构中的其他属性值结构并释放根据旧的。</span><span class="sxs-lookup"><span data-stu-id="10970-139">**Address** also allocates additional property value structures in the **ADRLIST** structure and frees old ones as appropriate.</span></span> <span data-ttu-id="10970-140">有关如何将内存管理**ADRLIST**结构的详细信息，请参阅[管理内存 ADRLIST 和 SRowSet 结构](managing-memory-for-adrlist-and-srowset-structures.md)。</span><span class="sxs-lookup"><span data-stu-id="10970-140">For more information about how memory is managed for **ADRLIST** structures, see [Managing Memory for ADRLIST and SRowSet Structures](managing-memory-for-adrlist-and-srowset-structures.md).</span></span>
  
 <span data-ttu-id="10970-141">**地址**立即返回 DIALOG_SDI 标志设置在_lpAdrParms_参数的**ADRPARM**结构中。</span><span class="sxs-lookup"><span data-stu-id="10970-141">**Address** returns immediately if the DIALOG_SDI flag was set in the **ADRPARM** structure in the  _lpAdrParms_ parameter.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="10970-142">另请参阅</span><span class="sxs-lookup"><span data-stu-id="10970-142">See also</span></span>



[<span data-ttu-id="10970-143">ABProviderInit</span><span class="sxs-lookup"><span data-stu-id="10970-143">ABProviderInit</span></span>](abproviderinit.md)
  
[<span data-ttu-id="10970-144">ADRENTRY</span><span class="sxs-lookup"><span data-stu-id="10970-144">ADRENTRY</span></span>](adrentry.md)
  
[<span data-ttu-id="10970-145">ADRLIST</span><span class="sxs-lookup"><span data-stu-id="10970-145">ADRLIST</span></span>](adrlist.md)
  
[<span data-ttu-id="10970-146">ADRPARM</span><span class="sxs-lookup"><span data-stu-id="10970-146">ADRPARM</span></span>](adrparm.md)
  
[<span data-ttu-id="10970-147">FreePadrlist</span><span class="sxs-lookup"><span data-stu-id="10970-147">FreePadrlist</span></span>](freepadrlist.md)
  
[<span data-ttu-id="10970-148">FreeProws</span><span class="sxs-lookup"><span data-stu-id="10970-148">FreeProws</span></span>](freeprows.md)
  
[<span data-ttu-id="10970-149">IMAPISupport::GetMemAllocRoutines</span><span class="sxs-lookup"><span data-stu-id="10970-149">IMAPISupport::GetMemAllocRoutines</span></span>](imapisupport-getmemallocroutines.md)
  
[<span data-ttu-id="10970-150">IMAPITable::QueryRows</span><span class="sxs-lookup"><span data-stu-id="10970-150">IMAPITable::QueryRows</span></span>](imapitable-queryrows.md)
  
[<span data-ttu-id="10970-151">IMessage::ModifyRecipients</span><span class="sxs-lookup"><span data-stu-id="10970-151">IMessage::ModifyRecipients</span></span>](imessage-modifyrecipients.md)
  
[<span data-ttu-id="10970-152">MAPIAllocateBuffer</span><span class="sxs-lookup"><span data-stu-id="10970-152">MAPIAllocateBuffer</span></span>](mapiallocatebuffer.md)
  
[<span data-ttu-id="10970-153">MAPIAllocateMore</span><span class="sxs-lookup"><span data-stu-id="10970-153">MAPIAllocateMore</span></span>](mapiallocatemore.md)
  
[<span data-ttu-id="10970-154">MAPIFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="10970-154">MAPIFreeBuffer</span></span>](mapifreebuffer.md)
  
[<span data-ttu-id="10970-155">PidTagAddressType 规范属性</span><span class="sxs-lookup"><span data-stu-id="10970-155">PidTagAddressType Canonical Property</span></span>](pidtagaddresstype-canonical-property.md)
  
[<span data-ttu-id="10970-156">PidTagDisplayName 规范属性</span><span class="sxs-lookup"><span data-stu-id="10970-156">PidTagDisplayName Canonical Property</span></span>](pidtagdisplayname-canonical-property.md)
  
[<span data-ttu-id="10970-157">PidTagDisplayType 规范属性</span><span class="sxs-lookup"><span data-stu-id="10970-157">PidTagDisplayType Canonical Property</span></span>](pidtagdisplaytype-canonical-property.md)
  
[<span data-ttu-id="10970-158">PidTagEntryId 规范属性</span><span class="sxs-lookup"><span data-stu-id="10970-158">PidTagEntryId Canonical Property</span></span>](pidtagentryid-canonical-property.md)
  
[<span data-ttu-id="10970-159">PidTagRecipientType 规范属性</span><span class="sxs-lookup"><span data-stu-id="10970-159">PidTagRecipientType Canonical Property</span></span>](pidtagrecipienttype-canonical-property.md)
  
[<span data-ttu-id="10970-160">SPropValue</span><span class="sxs-lookup"><span data-stu-id="10970-160">SPropValue</span></span>](spropvalue.md)
  
[<span data-ttu-id="10970-161">SRowSet</span><span class="sxs-lookup"><span data-stu-id="10970-161">SRowSet</span></span>](srowset.md)
  
[<span data-ttu-id="10970-162">IMAPISupport : IUnknown</span><span class="sxs-lookup"><span data-stu-id="10970-162">IMAPISupport : IUnknown</span></span>](imapisupportiunknown.md)


[<span data-ttu-id="10970-163">管理 ADRLIST 和 SRowSet 结构的内存</span><span class="sxs-lookup"><span data-stu-id="10970-163">Managing Memory for ADRLIST and SRowSet Structures</span></span>](managing-memory-for-adrlist-and-srowset-structures.md)

