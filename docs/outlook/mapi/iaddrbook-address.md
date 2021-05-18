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
ms.openlocfilehash: c2546fc990169526361f2c452c50212123d8284d
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33407905"
---
# <a name="iaddrbookaddress"></a><span data-ttu-id="9240a-103">IAddrBook::Address</span><span class="sxs-lookup"><span data-stu-id="9240a-103">IAddrBook::Address</span></span>

  
  
<span data-ttu-id="9240a-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="9240a-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="9240a-105">显示 Outlook 通讯簿对话框。</span><span class="sxs-lookup"><span data-stu-id="9240a-105">Displays the Outlook address book dialog box.</span></span> 
  
```cpp
HRESULT Address(
  ULONG_PTR FAR * lpulUIParam,
  LPADRPARM lpAdrParms,
  LPADRLIST FAR * lppAdrList
);
```

## <a name="parameters"></a><span data-ttu-id="9240a-106">参数</span><span class="sxs-lookup"><span data-stu-id="9240a-106">Parameters</span></span>

 <span data-ttu-id="9240a-107">_lpulUIParam_</span><span class="sxs-lookup"><span data-stu-id="9240a-107">_lpulUIParam_</span></span>
  
> <span data-ttu-id="9240a-108">[in， out]指向对话框父窗口的句柄的指针。</span><span class="sxs-lookup"><span data-stu-id="9240a-108">[in, out] A pointer to a handle of the parent window of the dialog box.</span></span> <span data-ttu-id="9240a-109">在输入时，必须始终传递窗口句柄。</span><span class="sxs-lookup"><span data-stu-id="9240a-109">On input, a window handle must always be passed.</span></span> <span data-ttu-id="9240a-110">在输出时，如果 _lpAdrParms_ 参数的 **ulFlags** 成员设置为 DIALOG_SDI，则返回无模式对话框的窗口句柄。</span><span class="sxs-lookup"><span data-stu-id="9240a-110">On output, if the **ulFlags** member of the  _lpAdrParms_ parameter is set to DIALOG_SDI, the window handle of the modeless dialog box is returned.</span></span> <span data-ttu-id="9240a-111">请参阅注解。</span><span class="sxs-lookup"><span data-stu-id="9240a-111">See Remarks.</span></span> 
    
 <span data-ttu-id="9240a-112">_lpAdrParms_</span><span class="sxs-lookup"><span data-stu-id="9240a-112">_lpAdrParms_</span></span>
  
> <span data-ttu-id="9240a-113">[in， out]指向控制地址对话框的显示和行为 [的 ADRPARM](adrparm.md) 结构的指针。</span><span class="sxs-lookup"><span data-stu-id="9240a-113">[in, out] A pointer to an [ADRPARM](adrparm.md) structure that controls the presentation and behavior of the address dialog box.</span></span> 
    
 <span data-ttu-id="9240a-114">_lppAdrList_</span><span class="sxs-lookup"><span data-stu-id="9240a-114">_lppAdrList_</span></span>
  
> <span data-ttu-id="9240a-115">[in， out]指向包含收件人信息的 [ADRLIST](adrlist.md) 结构的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="9240a-115">[in, out] A pointer to a pointer to an [ADRLIST](adrlist.md) structure that contains recipient information.</span></span> <span data-ttu-id="9240a-116">在输入时，此参数可以是 NULL 或指向有效的指针。</span><span class="sxs-lookup"><span data-stu-id="9240a-116">On input, this parameter can be NULL or point to a valid pointer.</span></span> <span data-ttu-id="9240a-117">在输出上，此参数指向指向有效收件人信息的指针。</span><span class="sxs-lookup"><span data-stu-id="9240a-117">On output, this parameter points to a pointer to valid recipient information.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="9240a-118">返回值</span><span class="sxs-lookup"><span data-stu-id="9240a-118">Return value</span></span>

<span data-ttu-id="9240a-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="9240a-119">S_OK</span></span> 
  
> <span data-ttu-id="9240a-120">已成功显示公用地址对话框。</span><span class="sxs-lookup"><span data-stu-id="9240a-120">The common address dialog box was successfully displayed.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="9240a-121">备注</span><span class="sxs-lookup"><span data-stu-id="9240a-121">Remarks</span></span>

<span data-ttu-id="9240a-122">如果 _lpAdrParms_ 参数的 **ulFlags** 成员设置为 DIALOG_SDI预期在输出上返回无模式对话框的窗口句柄，则 Outlook 中将忽略该成员;对话框的模式版本始终显示在非 Outlook 客户端中。</span><span class="sxs-lookup"><span data-stu-id="9240a-122">If the **ulFlags** member of the  _lpAdrParms_ parameter is set to DIALOG_SDI anticipating the return of the window handle of the modeless dialog box on output, it is ignored in Outlook; the modal version of the dialog is always shown in non-Outlook clients.</span></span> 
  
<span data-ttu-id="9240a-123">MAPI 通过 _lppAdrList_ 参数传递回调用方的 **ADRLIST** 结构包含 [ADRENTRY](adrentry.md)结构数组，每个收件人一个结构。</span><span class="sxs-lookup"><span data-stu-id="9240a-123">The **ADRLIST** structure passed back by MAPI to the caller through the  _lppAdrList_ parameter contains an array of [ADRENTRY](adrentry.md) structures, one structure for each recipient.</span></span> <span data-ttu-id="9240a-124">当传递到 _lpMods_ 参数中的传出邮件 [的 IMessage：：ModifyRecipients](imessage-modifyrecipients.md)方法时，**可以使用 ADRLIST** 结构更新其收件人列表。</span><span class="sxs-lookup"><span data-stu-id="9240a-124">When passed to an outgoing message's [IMessage::ModifyRecipients](imessage-modifyrecipients.md) method in the  _lpMods_ parameter, the **ADRLIST** structure can be used to update its recipient list.</span></span> 
  
<span data-ttu-id="9240a-125">**ADRLIST** 结构中的每个 **ADRENTRY** 结构包含零个或多个 [SPropValue](spropvalue.md)结构，一个针对收件人的每个属性集的结构。</span><span class="sxs-lookup"><span data-stu-id="9240a-125">Each **ADRENTRY** structure in the **ADRLIST** structure contains zero or more [SPropValue](spropvalue.md) structures, one structure for every property set for the recipient.</span></span> <span data-ttu-id="9240a-126">使用 Address 方法呈现的对话框删除收件人时，可以有零个 **SPropValue** 结构。</span><span class="sxs-lookup"><span data-stu-id="9240a-126">There can be zero **SPropValue** structures when the dialog box presented by the **Address** method is used to remove a recipient.</span></span> <span data-ttu-id="9240a-127">当存在一个或多个 **SPropValue** 结构时，相应的 **ADRENTRY** 结构用于添加或更新收件人。</span><span class="sxs-lookup"><span data-stu-id="9240a-127">When there are one or more **SPropValue** structures, the corresponding **ADRENTRY** structure is used to add or update a recipient.</span></span> <span data-ttu-id="9240a-128">可以解析收件人，这表示其中一个 **SPropValue** 结构描述收件人的 **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 属性或 unresolved，这表示 **缺少 PR_ENTRYID** 属性。</span><span class="sxs-lookup"><span data-stu-id="9240a-128">The recipient can be resolved, which indicates that one of the **SPropValue** structures describes the recipient's **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) property, or unresolved, which indicates that the **PR_ENTRYID** property is missing.</span></span> 
  
<span data-ttu-id="9240a-129">除了 **PR_ENTRYID**，已解析的收件人还包括以下属性：</span><span class="sxs-lookup"><span data-stu-id="9240a-129">In addition to **PR_ENTRYID**, resolved recipients include the following properties:</span></span>
  
- <span data-ttu-id="9240a-130">**PR_RECIPIENT_TYPE (** [PidTagRecipientType](pidtagrecipienttype-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="9240a-130">**PR_RECIPIENT_TYPE** ([PidTagRecipientType](pidtagrecipienttype-canonical-property.md))</span></span>
    
- <span data-ttu-id="9240a-131">**PR_DISPLAY_NAME (** [PidTagDisplayName](pidtagdisplayname-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="9240a-131">**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md))</span></span>
    
- <span data-ttu-id="9240a-132">**PR_ADDRTYPE (** [PidTagAddressType](pidtagaddresstype-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="9240a-132">**PR_ADDRTYPE** ([PidTagAddressType](pidtagaddresstype-canonical-property.md))</span></span>
    
- <span data-ttu-id="9240a-133">**PR_DISPLAY_TYPE (** [PidTagDisplayType](pidtagdisplaytype-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="9240a-133">**PR_DISPLAY_TYPE** ([PidTagDisplayType](pidtagdisplaytype-canonical-property.md))</span></span>
    
<span data-ttu-id="9240a-134">调用方 **传递的 ADRLIST** 结构的大小可能不同于 MAPI 返回的结构。</span><span class="sxs-lookup"><span data-stu-id="9240a-134">The **ADRLIST** structure that the caller passes in might be a different size from the structure that MAPI returns.</span></span> <span data-ttu-id="9240a-135">如果 MAPI 必须返回更大的 **ADRLIST** 结构，它将释放原始结构并分配一个新结构。</span><span class="sxs-lookup"><span data-stu-id="9240a-135">If MAPI must return a larger **ADRLIST** structure, it frees the original structure and allocates a new one.</span></span> <span data-ttu-id="9240a-136">为 **ADRLIST** 结构分配内存时，请单独为每个 **SPropValue** 结构分配内存。</span><span class="sxs-lookup"><span data-stu-id="9240a-136">When you allocate memory for the **ADRLIST** structure, allocate the memory for each **SPropValue** structure separately.</span></span> <span data-ttu-id="9240a-137">若要详细了解如何分配和释放 **ADRLIST** 结构，请参阅管理 [ADRLIST 和 SRowSet 结构的内存](managing-memory-for-adrlist-and-srowset-structures.md)</span><span class="sxs-lookup"><span data-stu-id="9240a-137">For more information about how to allocate and free **ADRLIST** structures, see [Managing Memory for ADRLIST and SRowSet Structures](managing-memory-for-adrlist-and-srowset-structures.md)</span></span>
  
 <span data-ttu-id="9240a-138">**如果在** _lpAdrParms_ 参数的 **ADRPARM** 结构的 **ulFlags** 成员中设置了 DIALOG_SDI 标志，则 Address 将立即返回。</span><span class="sxs-lookup"><span data-stu-id="9240a-138">**Address** returns immediately if the DIALOG_SDI flag is set in the **ulFlags** member of the **ADRPARM** structure in the  _lpAdrParms_ parameter.</span></span> <span data-ttu-id="9240a-139">对于DIALOG_SDI Outlook 客户端，将忽略该标记。</span><span class="sxs-lookup"><span data-stu-id="9240a-139">The DIALOG_SDI flag is ignored for non-Outlook clients.</span></span> <span data-ttu-id="9240a-140">如果DIALOG_SDI，将显示对话框的模式版本，并且不应在  _lpulUIParam_ 中期望指向句柄的指针。</span><span class="sxs-lookup"><span data-stu-id="9240a-140">If DIALOG_SDI is ignored, the modal version of the dialog will be displayed and a pointer to a handle should not be expected in  _lpulUIParam_.</span></span>
  
 <span data-ttu-id="9240a-141">**如果** aDRPARM 的 **ulFlags** 成员在 _lpAdrParms_ 参数中指定了 AB_UNICODEUI，则 Address 支持 **ADRPARM** 结构中的 Unicode 字符字符串，并支持 **ADRLIST** 中的 Unicode 字符字符串。 </span><span class="sxs-lookup"><span data-stu-id="9240a-141">**Address** supports Unicode character strings in the **ADRPARM** structure if AB_UNICODEUI was specified in the **ulFlags** member of **ADRPARM** in the  _lpAdrParms_ parameter, and it supports Unicode character strings in **ADRLIST**.</span></span> <span data-ttu-id="9240a-142">在 Outlook 通讯簿对话框中显示 Unicode 字符串 (MBCS) 格式转换为多字节字符串。</span><span class="sxs-lookup"><span data-stu-id="9240a-142">The Unicode strings are converted to the multibyte character string (MBCS) format before they are displayed in the Outlook address book dialog box.</span></span>
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="9240a-143">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="9240a-143">MFCMAPI reference</span></span>

<span data-ttu-id="9240a-144">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="9240a-144">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="9240a-145">**文件**</span><span class="sxs-lookup"><span data-stu-id="9240a-145">**File**</span></span>|<span data-ttu-id="9240a-146">**函数**</span><span class="sxs-lookup"><span data-stu-id="9240a-146">**Function**</span></span>|<span data-ttu-id="9240a-147">**备注**</span><span class="sxs-lookup"><span data-stu-id="9240a-147">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="9240a-148">MAPIStoreFunctions.cpp</span><span class="sxs-lookup"><span data-stu-id="9240a-148">MAPIStoreFunctions.cpp</span></span>  <br/> |<span data-ttu-id="9240a-149">OpenOtherUsersMailboxFromGal</span><span class="sxs-lookup"><span data-stu-id="9240a-149">OpenOtherUsersMailboxFromGal</span></span>  <br/> |<span data-ttu-id="9240a-150">MFCMAPI 使用 **Address** 方法允许用户选择要打开的邮箱。</span><span class="sxs-lookup"><span data-stu-id="9240a-150">MFCMAPI uses the **Address** method to allow the user to select which mailbox to open.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="9240a-151">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9240a-151">See also</span></span>



[<span data-ttu-id="9240a-152">ADRENTRY</span><span class="sxs-lookup"><span data-stu-id="9240a-152">ADRENTRY</span></span>](adrentry.md)
  
[<span data-ttu-id="9240a-153">ADRLIST</span><span class="sxs-lookup"><span data-stu-id="9240a-153">ADRLIST</span></span>](adrlist.md)
  
[<span data-ttu-id="9240a-154">ADRPARM</span><span class="sxs-lookup"><span data-stu-id="9240a-154">ADRPARM</span></span>](adrparm.md)
  
[<span data-ttu-id="9240a-155">FreePadrlist</span><span class="sxs-lookup"><span data-stu-id="9240a-155">FreePadrlist</span></span>](freepadrlist.md)
  
[<span data-ttu-id="9240a-156">FreeProws</span><span class="sxs-lookup"><span data-stu-id="9240a-156">FreeProws</span></span>](freeprows.md)
  
[<span data-ttu-id="9240a-157">IMAPITable::QueryRows</span><span class="sxs-lookup"><span data-stu-id="9240a-157">IMAPITable::QueryRows</span></span>](imapitable-queryrows.md)
  
[<span data-ttu-id="9240a-158">IMessage::ModifyRecipients</span><span class="sxs-lookup"><span data-stu-id="9240a-158">IMessage::ModifyRecipients</span></span>](imessage-modifyrecipients.md)
  
[<span data-ttu-id="9240a-159">MAPIAllocateBuffer</span><span class="sxs-lookup"><span data-stu-id="9240a-159">MAPIAllocateBuffer</span></span>](mapiallocatebuffer.md)
  
[<span data-ttu-id="9240a-160">MAPIAllocateMore</span><span class="sxs-lookup"><span data-stu-id="9240a-160">MAPIAllocateMore</span></span>](mapiallocatemore.md)
  
[<span data-ttu-id="9240a-161">MAPIFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="9240a-161">MAPIFreeBuffer</span></span>](mapifreebuffer.md)
  
[<span data-ttu-id="9240a-162">SPropValue</span><span class="sxs-lookup"><span data-stu-id="9240a-162">SPropValue</span></span>](spropvalue.md)
  
[<span data-ttu-id="9240a-163">SRowSet</span><span class="sxs-lookup"><span data-stu-id="9240a-163">SRowSet</span></span>](srowset.md)
  
[<span data-ttu-id="9240a-164">IAddrBook : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="9240a-164">IAddrBook : IMAPIProp</span></span>](iaddrbookimapiprop.md)


[<span data-ttu-id="9240a-165">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="9240a-165">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)
  
[<span data-ttu-id="9240a-166">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="9240a-166">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

