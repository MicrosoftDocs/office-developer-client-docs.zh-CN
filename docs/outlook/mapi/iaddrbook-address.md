---
title: IAddrBookAddress
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IAddrBook.Address
api_type:
- COM
ms.assetid: ef2112c7-35cd-4106-ad18-a45e1dbe07d6
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 10f8f2cf44bf1a8e00f8c2b1a76826db5fc07161
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775233"
---
# <a name="iaddrbookaddress"></a><span data-ttu-id="76bf9-103">IAddrBook::Address</span><span class="sxs-lookup"><span data-stu-id="76bf9-103">IAddrBook::Address</span></span>

  
  
<span data-ttu-id="76bf9-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="76bf9-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="76bf9-105">显示 Outlook 通讯簿对话框。</span><span class="sxs-lookup"><span data-stu-id="76bf9-105">Displays the Outlook address book dialog box.</span></span> 
  
```cpp
HRESULT Address(
  ULONG_PTR FAR * lpulUIParam,
  LPADRPARM lpAdrParms,
  LPADRLIST FAR * lppAdrList
);
```

## <a name="parameters"></a><span data-ttu-id="76bf9-106">参数</span><span class="sxs-lookup"><span data-stu-id="76bf9-106">Parameters</span></span>

 <span data-ttu-id="76bf9-107">_lpulUIParam_</span><span class="sxs-lookup"><span data-stu-id="76bf9-107">_lpulUIParam_</span></span>
  
> <span data-ttu-id="76bf9-108">[传入、 传出]指向对话框中的父窗口的句柄的指针。</span><span class="sxs-lookup"><span data-stu-id="76bf9-108">[in, out] A pointer to a handle of the parent window of the dialog box.</span></span> <span data-ttu-id="76bf9-109">在输入时，必须始终传递窗口句柄。</span><span class="sxs-lookup"><span data-stu-id="76bf9-109">On input, a window handle must always be passed.</span></span> <span data-ttu-id="76bf9-110">输出，如果_lpAdrParms_参数的**ulFlags**成员设置为 DIALOG_SDI，则返回无模式对话框的窗口句柄。</span><span class="sxs-lookup"><span data-stu-id="76bf9-110">On output, if the **ulFlags** member of the  _lpAdrParms_ parameter is set to DIALOG_SDI, the window handle of the modeless dialog box is returned.</span></span> <span data-ttu-id="76bf9-111">请参阅注解。</span><span class="sxs-lookup"><span data-stu-id="76bf9-111">See Remarks.</span></span> 
    
 <span data-ttu-id="76bf9-112">_lpAdrParms_</span><span class="sxs-lookup"><span data-stu-id="76bf9-112">_lpAdrParms_</span></span>
  
> <span data-ttu-id="76bf9-113">[传入、 传出]指向控制的演示文稿和行为的地址对话框的[ADRPARM](adrparm.md)结构的指针。</span><span class="sxs-lookup"><span data-stu-id="76bf9-113">[in, out] A pointer to an [ADRPARM](adrparm.md) structure that controls the presentation and behavior of the address dialog box.</span></span> 
    
 <span data-ttu-id="76bf9-114">_lppAdrList_</span><span class="sxs-lookup"><span data-stu-id="76bf9-114">_lppAdrList_</span></span>
  
> <span data-ttu-id="76bf9-115">[传入、 传出]指向[ADRLIST](adrlist.md)结构包含收件人信息的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="76bf9-115">[in, out] A pointer to a pointer to an [ADRLIST](adrlist.md) structure that contains recipient information.</span></span> <span data-ttu-id="76bf9-116">在输入时，此参数可以为 NULL 或指向一个有效的指针。</span><span class="sxs-lookup"><span data-stu-id="76bf9-116">On input, this parameter can be NULL or point to a valid pointer.</span></span> <span data-ttu-id="76bf9-117">输出，此参数是指向对有效收件人信息的指针。</span><span class="sxs-lookup"><span data-stu-id="76bf9-117">On output, this parameter points to a pointer to valid recipient information.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="76bf9-118">返回值</span><span class="sxs-lookup"><span data-stu-id="76bf9-118">Return value</span></span>

<span data-ttu-id="76bf9-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="76bf9-119">S_OK</span></span> 
  
> <span data-ttu-id="76bf9-120">已成功显示常见的地址对话框。</span><span class="sxs-lookup"><span data-stu-id="76bf9-120">The common address dialog box was successfully displayed.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="76bf9-121">说明</span><span class="sxs-lookup"><span data-stu-id="76bf9-121">Remarks</span></span>

<span data-ttu-id="76bf9-122">如果_lpAdrParms_参数的**ulFlags**成员设置为 DIALOG_SDI 预见无模式对话框的窗口句柄回报输出，则将被忽略; 在 Outlook 中非 Outlook 客户端中始终显示模式对话框的版本。</span><span class="sxs-lookup"><span data-stu-id="76bf9-122">If the **ulFlags** member of the  _lpAdrParms_ parameter is set to DIALOG_SDI anticipating the return of the window handle of the modeless dialog box on output, it is ignored in Outlook; the modal version of the dialog is always shown in non-Outlook clients.</span></span> 
  
<span data-ttu-id="76bf9-123">**ADRLIST**结构后通过 MAPI 传递给呼叫者通过_lppAdrList_参数包含一个数组[ADRENTRY](adrentry.md)结构，每个收件人的一个结构。</span><span class="sxs-lookup"><span data-stu-id="76bf9-123">The **ADRLIST** structure passed back by MAPI to the caller through the  _lppAdrList_ parameter contains an array of [ADRENTRY](adrentry.md) structures, one structure for each recipient.</span></span> <span data-ttu-id="76bf9-124">传递给_lpMods_参数中的传出消息的[IMessage::ModifyRecipients](imessage-modifyrecipients.md)方法时， **ADRLIST**结构可用于更新其收件人列表。</span><span class="sxs-lookup"><span data-stu-id="76bf9-124">When passed to an outgoing message's [IMessage::ModifyRecipients](imessage-modifyrecipients.md) method in the  _lpMods_ parameter, the **ADRLIST** structure can be used to update its recipient list.</span></span> 
  
<span data-ttu-id="76bf9-125">**ADRLIST**结构中的每个**ADRENTRY**结构包含零个或多个[SPropValue](spropvalue.md)结构、 一个结构收件人设置每个属性。</span><span class="sxs-lookup"><span data-stu-id="76bf9-125">Each **ADRENTRY** structure in the **ADRLIST** structure contains zero or more [SPropValue](spropvalue.md) structures, one structure for every property set for the recipient.</span></span> <span data-ttu-id="76bf9-126">使用演示者的**地址**方法对话框中删除收件人时，可以是零**SPropValue**结构。</span><span class="sxs-lookup"><span data-stu-id="76bf9-126">There can be zero **SPropValue** structures when the dialog box presented by the **Address** method is used to remove a recipient.</span></span> <span data-ttu-id="76bf9-127">当存在一个或多个**SPropValue**结构时，相应**ADRENTRY**结构用于添加或更新收件人。</span><span class="sxs-lookup"><span data-stu-id="76bf9-127">When there are one or more **SPropValue** structures, the corresponding **ADRENTRY** structure is used to add or update a recipient.</span></span> <span data-ttu-id="76bf9-128">收件人可以解析，指示**SPropValue**结构之一描述收件人的**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 属性，或无法解析，指示**PR_ENTRYID**属性缺少。</span><span class="sxs-lookup"><span data-stu-id="76bf9-128">The recipient can be resolved, which indicates that one of the **SPropValue** structures describes the recipient's **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) property, or unresolved, which indicates that the **PR_ENTRYID** property is missing.</span></span> 
  
<span data-ttu-id="76bf9-129">除了**PR_ENTRYID**，已解析的收件人包括以下属性：</span><span class="sxs-lookup"><span data-stu-id="76bf9-129">In addition to **PR_ENTRYID**, resolved recipients include the following properties:</span></span>
  
- <span data-ttu-id="76bf9-130">**PR_RECIPIENT_TYPE**([PidTagRecipientType](pidtagrecipienttype-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="76bf9-130">**PR_RECIPIENT_TYPE** ([PidTagRecipientType](pidtagrecipienttype-canonical-property.md))</span></span>
    
- <span data-ttu-id="76bf9-131">**PR_DISPLAY_NAME**([PidTagDisplayName](pidtagdisplayname-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="76bf9-131">**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md))</span></span>
    
- <span data-ttu-id="76bf9-132">**PR_ADDRTYPE**([PidTagAddressType](pidtagaddresstype-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="76bf9-132">**PR_ADDRTYPE** ([PidTagAddressType](pidtagaddresstype-canonical-property.md))</span></span>
    
- <span data-ttu-id="76bf9-133">**PR_DISPLAY_TYPE**([PidTagDisplayType](pidtagdisplaytype-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="76bf9-133">**PR_DISPLAY_TYPE** ([PidTagDisplayType](pidtagdisplaytype-canonical-property.md))</span></span>
    
<span data-ttu-id="76bf9-134">传入呼叫者的**ADRLIST**结构可能从结构的 MAPI 返回不同的大小。</span><span class="sxs-lookup"><span data-stu-id="76bf9-134">The **ADRLIST** structure that the caller passes in might be a different size from the structure that MAPI returns.</span></span> <span data-ttu-id="76bf9-135">如果 MAPI 必须返回较大的**ADRLIST**结构，它释放原始结构，并分配一个新。</span><span class="sxs-lookup"><span data-stu-id="76bf9-135">If MAPI must return a larger **ADRLIST** structure, it frees the original structure and allocates a new one.</span></span> <span data-ttu-id="76bf9-136">当您为**ADRLIST**结构分配内存时，将单独为每个**SPropValue**结构分配内存。</span><span class="sxs-lookup"><span data-stu-id="76bf9-136">When you allocate memory for the **ADRLIST** structure, allocate the memory for each **SPropValue** structure separately.</span></span> <span data-ttu-id="76bf9-137">有关如何分配和释放**ADRLIST**结构的详细信息，请参阅[管理内存 ADRLIST 和 SRowSet 结构](managing-memory-for-adrlist-and-srowset-structures.md)</span><span class="sxs-lookup"><span data-stu-id="76bf9-137">For more information about how to allocate and free **ADRLIST** structures, see [Managing Memory for ADRLIST and SRowSet Structures](managing-memory-for-adrlist-and-srowset-structures.md)</span></span>
  
 <span data-ttu-id="76bf9-138">**地址**立即返回如果_lpAdrParms_参数中的**ADRPARM**结构的**ulFlags**成员中设置 DIALOG_SDI 标志。</span><span class="sxs-lookup"><span data-stu-id="76bf9-138">**Address** returns immediately if the DIALOG_SDI flag is set in the **ulFlags** member of the **ADRPARM** structure in the  _lpAdrParms_ parameter.</span></span> <span data-ttu-id="76bf9-139">非 Outlook 客户端的情况下，将忽略 DIALOG_SDI 标志。</span><span class="sxs-lookup"><span data-stu-id="76bf9-139">The DIALOG_SDI flag is ignored for non-Outlook clients.</span></span> <span data-ttu-id="76bf9-140">如果 DIALOG_SDI 将被忽略，将显示模式对话框的版本并不应该在_lpulUIParam_要求的句柄的指针。</span><span class="sxs-lookup"><span data-stu-id="76bf9-140">If DIALOG_SDI is ignored, the modal version of the dialog will be displayed and a pointer to a handle should not be expected in  _lpulUIParam_.</span></span>
  
 <span data-ttu-id="76bf9-141">**地址** **ADRPARM**结构中支持 Unicode 字符的字符串，如果在**ADRPARM**的**ulFlags**成员_lpAdrParms_参数中指定 AB_UNICODEUI 而它支持**中的 Unicode 字符串ADRLIST**。</span><span class="sxs-lookup"><span data-stu-id="76bf9-141">**Address** supports Unicode character strings in the **ADRPARM** structure if AB_UNICODEUI was specified in the **ulFlags** member of **ADRPARM** in the  _lpAdrParms_ parameter, and it supports Unicode character strings in **ADRLIST**.</span></span> <span data-ttu-id="76bf9-142">Unicode 字符串转换为多字节字符的字符串 (MBCS) 格式显示在 Outlook 通讯簿对话框之前。</span><span class="sxs-lookup"><span data-stu-id="76bf9-142">The Unicode strings are converted to the multibyte character string (MBCS) format before they are displayed in the Outlook address book dialog box.</span></span>
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="76bf9-143">MFCMAPI 参考 （英文）</span><span class="sxs-lookup"><span data-stu-id="76bf9-143">MFCMAPI reference</span></span>

<span data-ttu-id="76bf9-144">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="76bf9-144">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="76bf9-145">**文件**</span><span class="sxs-lookup"><span data-stu-id="76bf9-145">**File**</span></span>|<span data-ttu-id="76bf9-146">**函数**</span><span class="sxs-lookup"><span data-stu-id="76bf9-146">**Function**</span></span>|<span data-ttu-id="76bf9-147">**Comment**</span><span class="sxs-lookup"><span data-stu-id="76bf9-147">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="76bf9-148">MAPIStoreFunctions.cpp</span><span class="sxs-lookup"><span data-stu-id="76bf9-148">MAPIStoreFunctions.cpp</span></span>  <br/> |<span data-ttu-id="76bf9-149">OpenOtherUsersMailboxFromGal</span><span class="sxs-lookup"><span data-stu-id="76bf9-149">OpenOtherUsersMailboxFromGal</span></span>  <br/> |<span data-ttu-id="76bf9-150">MFCMAPI 使用**地址**方法允许用户选择要打开的邮箱。</span><span class="sxs-lookup"><span data-stu-id="76bf9-150">MFCMAPI uses the **Address** method to allow the user to select which mailbox to open.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="76bf9-151">另请参阅</span><span class="sxs-lookup"><span data-stu-id="76bf9-151">See also</span></span>



[<span data-ttu-id="76bf9-152">ADRENTRY</span><span class="sxs-lookup"><span data-stu-id="76bf9-152">ADRENTRY</span></span>](adrentry.md)
  
[<span data-ttu-id="76bf9-153">ADRLIST</span><span class="sxs-lookup"><span data-stu-id="76bf9-153">ADRLIST</span></span>](adrlist.md)
  
[<span data-ttu-id="76bf9-154">ADRPARM</span><span class="sxs-lookup"><span data-stu-id="76bf9-154">ADRPARM</span></span>](adrparm.md)
  
[<span data-ttu-id="76bf9-155">FreePadrlist</span><span class="sxs-lookup"><span data-stu-id="76bf9-155">FreePadrlist</span></span>](freepadrlist.md)
  
[<span data-ttu-id="76bf9-156">FreeProws</span><span class="sxs-lookup"><span data-stu-id="76bf9-156">FreeProws</span></span>](freeprows.md)
  
[<span data-ttu-id="76bf9-157">IMAPITable::QueryRows</span><span class="sxs-lookup"><span data-stu-id="76bf9-157">IMAPITable::QueryRows</span></span>](imapitable-queryrows.md)
  
[<span data-ttu-id="76bf9-158">IMessage::ModifyRecipients</span><span class="sxs-lookup"><span data-stu-id="76bf9-158">IMessage::ModifyRecipients</span></span>](imessage-modifyrecipients.md)
  
[<span data-ttu-id="76bf9-159">MAPIAllocateBuffer</span><span class="sxs-lookup"><span data-stu-id="76bf9-159">MAPIAllocateBuffer</span></span>](mapiallocatebuffer.md)
  
[<span data-ttu-id="76bf9-160">MAPIAllocateMore</span><span class="sxs-lookup"><span data-stu-id="76bf9-160">MAPIAllocateMore</span></span>](mapiallocatemore.md)
  
[<span data-ttu-id="76bf9-161">MAPIFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="76bf9-161">MAPIFreeBuffer</span></span>](mapifreebuffer.md)
  
[<span data-ttu-id="76bf9-162">SPropValue</span><span class="sxs-lookup"><span data-stu-id="76bf9-162">SPropValue</span></span>](spropvalue.md)
  
[<span data-ttu-id="76bf9-163">SRowSet</span><span class="sxs-lookup"><span data-stu-id="76bf9-163">SRowSet</span></span>](srowset.md)
  
[<span data-ttu-id="76bf9-164">IAddrBook : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="76bf9-164">IAddrBook : IMAPIProp</span></span>](iaddrbookimapiprop.md)


[<span data-ttu-id="76bf9-165">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="76bf9-165">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)
  
[<span data-ttu-id="76bf9-166">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="76bf9-166">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

