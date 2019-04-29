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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 7300c11d5835640fe308430c9bb08d40b397e47b
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33407317"
---
# <a name="imapisupportaddress"></a><span data-ttu-id="c109a-103">IMAPISupport::Address</span><span class="sxs-lookup"><span data-stu-id="c109a-103">IMAPISupport::Address</span></span>

  
  
<span data-ttu-id="c109a-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="c109a-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="c109a-105">显示 "常用地址" 对话框。</span><span class="sxs-lookup"><span data-stu-id="c109a-105">Displays the common address dialog box.</span></span> 
  
```cpp
HRESULT Address(
  ULONG_PTR FAR * lpulUIParam,
  LPADRPARM lpAdrParms,
  LPADRLIST FAR * lppAdrList
);
```

## <a name="parameters"></a><span data-ttu-id="c109a-106">参数</span><span class="sxs-lookup"><span data-stu-id="c109a-106">Parameters</span></span>

 <span data-ttu-id="c109a-107">_lpulUIParam_</span><span class="sxs-lookup"><span data-stu-id="c109a-107">_lpulUIParam_</span></span>
  
> <span data-ttu-id="c109a-108">[in, out]指向对话框父窗口的句柄的指针。</span><span class="sxs-lookup"><span data-stu-id="c109a-108">[in, out] A pointer to the handle of the parent window of the dialog box.</span></span> <span data-ttu-id="c109a-109">在输入时, 必须始终传递窗口句柄。</span><span class="sxs-lookup"><span data-stu-id="c109a-109">On input, a window handle must always be passed.</span></span> <span data-ttu-id="c109a-110">在输出时, 如果在[ADRPARM](adrparm.md)结构中设置了_lpAdrParms_参数指向的 DIALOG_SDI 标志, 则将返回无模式对话框的窗口句柄。</span><span class="sxs-lookup"><span data-stu-id="c109a-110">On output, if the DIALOG_SDI flag is set in the [ADRPARM](adrparm.md) structure pointed to by the  _lpAdrParms_ parameter, the window handle of the modeless dialog box is returned.</span></span> 
    
 <span data-ttu-id="c109a-111">_lpAdrParms_</span><span class="sxs-lookup"><span data-stu-id="c109a-111">_lpAdrParms_</span></span>
  
> <span data-ttu-id="c109a-112">[in, out]指向控制 "地址" 对话框的外观和行为的**ADRPARM**结构的指针。</span><span class="sxs-lookup"><span data-stu-id="c109a-112">[in, out] A pointer to an **ADRPARM** structure that controls the presentation and behavior of the address dialog box.</span></span> 
    
 <span data-ttu-id="c109a-113">_lppAdrList_</span><span class="sxs-lookup"><span data-stu-id="c109a-113">_lppAdrList_</span></span>
  
> <span data-ttu-id="c109a-114">[in, out]指向地址列表的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="c109a-114">[in, out] A pointer to a pointer to an address list.</span></span> <span data-ttu-id="c109a-115">在输入时, 此列表是邮件中的收件人的当前列表, 如果不存在这样的列表, 则为 NULL。</span><span class="sxs-lookup"><span data-stu-id="c109a-115">On input, this list is either the current list of recipients in a message or NULL, if no such list exists.</span></span> <span data-ttu-id="c109a-116">在输出时, _lppAdrList_指向已更新的邮件收件人列表。</span><span class="sxs-lookup"><span data-stu-id="c109a-116">On output,  _lppAdrList_ points to an updated list of message recipients.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="c109a-117">返回值</span><span class="sxs-lookup"><span data-stu-id="c109a-117">Return value</span></span>

<span data-ttu-id="c109a-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="c109a-118">S_OK</span></span> 
  
> <span data-ttu-id="c109a-119">已成功显示 "地址" 对话框。</span><span class="sxs-lookup"><span data-stu-id="c109a-119">The address dialog box was successfully displayed.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="c109a-120">说明</span><span class="sxs-lookup"><span data-stu-id="c109a-120">Remarks</span></span>

<span data-ttu-id="c109a-121">为通讯簿提供程序支持对象实现了**IMAPISupport:: Address**方法。</span><span class="sxs-lookup"><span data-stu-id="c109a-121">The **IMAPISupport::Address** method is implemented for address book provider support objects.</span></span> <span data-ttu-id="c109a-122">通讯簿提供程序呼叫**地址**以创建或更新邮件收件人的列表。</span><span class="sxs-lookup"><span data-stu-id="c109a-122">Address book providers call **Address** to create or update a list of message recipients.</span></span> 
  
<span data-ttu-id="c109a-123">每个收件人都在由_lppAdrList_参数指向的[ADRLIST](adrlist.md)结构中包含的[ADRENTRY](adrentry.md)结构中进行了描述。</span><span class="sxs-lookup"><span data-stu-id="c109a-123">Each recipient is described in an [ADRENTRY](adrentry.md) structure that is included in the [ADRLIST](adrlist.md) structure pointed to by the  _lppAdrList_ parameter.</span></span> <span data-ttu-id="c109a-124">**ADRENTRY**结构包含收件人属性值的数组, 其中一个是收件人的类型或**PR_RECIPIENT_TYPE** ([PidTagRecipientType](pidtagrecipienttype-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="c109a-124">The **ADRENTRY** structure contains an array of recipient property values, one of which is the recipient's type, or **PR_RECIPIENT_TYPE** ([PidTagRecipientType](pidtagrecipienttype-canonical-property.md)) property.</span></span> <span data-ttu-id="c109a-125">在对[IMessage:: ModifyRecipients](imessage-modifyrecipients.md)的调用中, 可以将此**ADRLIST**结构传递给客户端, 以用作_lpMods_参数。</span><span class="sxs-lookup"><span data-stu-id="c109a-125">This **ADRLIST** structure can be passed to a client to use as the  _lpMods_ parameter in a call to [IMessage::ModifyRecipients](imessage-modifyrecipients.md).</span></span>
  
<span data-ttu-id="c109a-126">可以解析**ADRLIST**结构中的每个收件人, 这表示它的属性值之一是其**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 属性或未解析, 这表示**PR_ENTRYID**属性为尚.</span><span class="sxs-lookup"><span data-stu-id="c109a-126">Each recipient in the **ADRLIST** structure can be either resolved, which indicates that one of its property values is its **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) property, or unresolved, which indicates that the **PR_ENTRYID** property is missing.</span></span> 
  
<span data-ttu-id="c109a-127">除了**PR_ENTRYID**, 解析的收件人还包含以下属性:</span><span class="sxs-lookup"><span data-stu-id="c109a-127">In addition to **PR_ENTRYID**, resolved recipients include the following properties:</span></span>
  
- <span data-ttu-id="c109a-128">**PR_RECIPIENT_TYPE**</span><span class="sxs-lookup"><span data-stu-id="c109a-128">**PR_RECIPIENT_TYPE**</span></span>
    
- <span data-ttu-id="c109a-129">**PR_DISPLAY_NAME**([PidTagDisplayName](pidtagdisplayname-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="c109a-129">**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md))</span></span>
    
- <span data-ttu-id="c109a-130">**PR_ADDRTYPE**([PidTagAddressType](pidtagaddresstype-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="c109a-130">**PR_ADDRTYPE** ([PidTagAddressType](pidtagaddresstype-canonical-property.md))</span></span>
    
- <span data-ttu-id="c109a-131">**PR_DISPLAY_TYPE**([PidTagDisplayType](pidtagdisplaytype-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="c109a-131">**PR_DISPLAY_TYPE** ([PidTagDisplayType](pidtagdisplaytype-canonical-property.md))</span></span>
    
<span data-ttu-id="c109a-132">未解析的收件人通常仅包括**PR_DISPLAY_NAME**和**PR_RECIPIENT_TYPE**。</span><span class="sxs-lookup"><span data-stu-id="c109a-132">Unresolved recipients typically include only **PR_DISPLAY_NAME** and **PR_RECIPIENT_TYPE**.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="c109a-133">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="c109a-133">Notes to callers</span></span>

<span data-ttu-id="c109a-134">调用方传入的**ADRLIST**结构的大小可能与 MAPI 返回的结构不同。</span><span class="sxs-lookup"><span data-stu-id="c109a-134">The **ADRLIST** structure that the caller passes in might be a different size from the structure that MAPI returns.</span></span> <span data-ttu-id="c109a-135">为**ADRLIST**结构分配内存时, 请单独为每个[SPropValue](spropvalue.md)结构分配内存。</span><span class="sxs-lookup"><span data-stu-id="c109a-135">When you allocate memory for the **ADRLIST** structure, allocate the memory for each [SPropValue](spropvalue.md) structure separately.</span></span> 
  
<span data-ttu-id="c109a-136">使用指向传递给[ABProviderInit](abproviderinit.md)函数的 MAPI 内存分配函数的指针来分配内存。</span><span class="sxs-lookup"><span data-stu-id="c109a-136">Use the pointers to the MAPI memory allocation functions passed in to your [ABProviderInit](abproviderinit.md) function to allocate memory.</span></span> <span data-ttu-id="c109a-137">使用**ADRLIST**的[MAPIAllocateBuffer](mapiallocatebuffer.md)函数和**ADRLIST**中的**ADRENTRY**结构中的每个属性值结构分配内存。</span><span class="sxs-lookup"><span data-stu-id="c109a-137">Allocate memory with the [MAPIAllocateBuffer](mapiallocatebuffer.md) function for **ADRLIST** and each property value structure in the **ADRENTRY** structures in **ADRLIST**.</span></span> 
  
<span data-ttu-id="c109a-138">如果**address**必须返回一个更大的**ADRLIST**结构, 或者如果您为_lppAdrList_传递了 NULL, 则**address**将释放原始结构并分配一个新的结构。</span><span class="sxs-lookup"><span data-stu-id="c109a-138">If **Address** must return a larger **ADRLIST** structure, or if you have passed NULL for  _lppAdrList_, **Address** frees the original structure and allocates a new one.</span></span> <span data-ttu-id="c109a-139">**Address**还会在**ADRLIST**结构中分配其他属性值结构, 并根据需要释放旧的属性。</span><span class="sxs-lookup"><span data-stu-id="c109a-139">**Address** also allocates additional property value structures in the **ADRLIST** structure and frees old ones as appropriate.</span></span> <span data-ttu-id="c109a-140">有关如何为**ADRLIST**结构管理内存的详细信息, 请参阅[管理内存用于 ADRLIST 和 SRowSet 结构](managing-memory-for-adrlist-and-srowset-structures.md)。</span><span class="sxs-lookup"><span data-stu-id="c109a-140">For more information about how memory is managed for **ADRLIST** structures, see [Managing Memory for ADRLIST and SRowSet Structures](managing-memory-for-adrlist-and-srowset-structures.md).</span></span>
  
 <span data-ttu-id="c109a-141">如果在_lpAdrParms_参数的**ADRPARM**结构中设置了 DIALOG_SDI 标志, 则立即返回**Address** 。</span><span class="sxs-lookup"><span data-stu-id="c109a-141">**Address** returns immediately if the DIALOG_SDI flag was set in the **ADRPARM** structure in the  _lpAdrParms_ parameter.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="c109a-142">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c109a-142">See also</span></span>



[<span data-ttu-id="c109a-143">ABProviderInit</span><span class="sxs-lookup"><span data-stu-id="c109a-143">ABProviderInit</span></span>](abproviderinit.md)
  
[<span data-ttu-id="c109a-144">ADRENTRY</span><span class="sxs-lookup"><span data-stu-id="c109a-144">ADRENTRY</span></span>](adrentry.md)
  
[<span data-ttu-id="c109a-145">ADRLIST</span><span class="sxs-lookup"><span data-stu-id="c109a-145">ADRLIST</span></span>](adrlist.md)
  
[<span data-ttu-id="c109a-146">ADRPARM</span><span class="sxs-lookup"><span data-stu-id="c109a-146">ADRPARM</span></span>](adrparm.md)
  
[<span data-ttu-id="c109a-147">FreePadrlist</span><span class="sxs-lookup"><span data-stu-id="c109a-147">FreePadrlist</span></span>](freepadrlist.md)
  
[<span data-ttu-id="c109a-148">FreeProws</span><span class="sxs-lookup"><span data-stu-id="c109a-148">FreeProws</span></span>](freeprows.md)
  
[<span data-ttu-id="c109a-149">IMAPISupport::GetMemAllocRoutines</span><span class="sxs-lookup"><span data-stu-id="c109a-149">IMAPISupport::GetMemAllocRoutines</span></span>](imapisupport-getmemallocroutines.md)
  
[<span data-ttu-id="c109a-150">IMAPITable::QueryRows</span><span class="sxs-lookup"><span data-stu-id="c109a-150">IMAPITable::QueryRows</span></span>](imapitable-queryrows.md)
  
[<span data-ttu-id="c109a-151">IMessage::ModifyRecipients</span><span class="sxs-lookup"><span data-stu-id="c109a-151">IMessage::ModifyRecipients</span></span>](imessage-modifyrecipients.md)
  
[<span data-ttu-id="c109a-152">MAPIAllocateBuffer</span><span class="sxs-lookup"><span data-stu-id="c109a-152">MAPIAllocateBuffer</span></span>](mapiallocatebuffer.md)
  
[<span data-ttu-id="c109a-153">MAPIAllocateMore</span><span class="sxs-lookup"><span data-stu-id="c109a-153">MAPIAllocateMore</span></span>](mapiallocatemore.md)
  
[<span data-ttu-id="c109a-154">MAPIFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="c109a-154">MAPIFreeBuffer</span></span>](mapifreebuffer.md)
  
[<span data-ttu-id="c109a-155">PidTagAddressType 规范属性</span><span class="sxs-lookup"><span data-stu-id="c109a-155">PidTagAddressType Canonical Property</span></span>](pidtagaddresstype-canonical-property.md)
  
[<span data-ttu-id="c109a-156">PidTagDisplayName 规范属性</span><span class="sxs-lookup"><span data-stu-id="c109a-156">PidTagDisplayName Canonical Property</span></span>](pidtagdisplayname-canonical-property.md)
  
[<span data-ttu-id="c109a-157">PidTagDisplayType 规范属性</span><span class="sxs-lookup"><span data-stu-id="c109a-157">PidTagDisplayType Canonical Property</span></span>](pidtagdisplaytype-canonical-property.md)
  
[<span data-ttu-id="c109a-158">PidTagEntryId 规范属性</span><span class="sxs-lookup"><span data-stu-id="c109a-158">PidTagEntryId Canonical Property</span></span>](pidtagentryid-canonical-property.md)
  
[<span data-ttu-id="c109a-159">PidTagRecipientType 规范属性</span><span class="sxs-lookup"><span data-stu-id="c109a-159">PidTagRecipientType Canonical Property</span></span>](pidtagrecipienttype-canonical-property.md)
  
[<span data-ttu-id="c109a-160">SPropValue</span><span class="sxs-lookup"><span data-stu-id="c109a-160">SPropValue</span></span>](spropvalue.md)
  
[<span data-ttu-id="c109a-161">SRowSet</span><span class="sxs-lookup"><span data-stu-id="c109a-161">SRowSet</span></span>](srowset.md)
  
[<span data-ttu-id="c109a-162">IMAPISupport : IUnknown</span><span class="sxs-lookup"><span data-stu-id="c109a-162">IMAPISupport : IUnknown</span></span>](imapisupportiunknown.md)


[<span data-ttu-id="c109a-163">管理 ADRLIST 和 SRowSet 结构的内存</span><span class="sxs-lookup"><span data-stu-id="c109a-163">Managing Memory for ADRLIST and SRowSet Structures</span></span>](managing-memory-for-adrlist-and-srowset-structures.md)

