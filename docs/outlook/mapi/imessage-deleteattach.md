---
title: IMessageDeleteAttach
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMessage.DeleteAttach
api_type:
- COM
ms.assetid: 0a5cb49f-c4f3-4893-8616-80d6332efcfc
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: c14ccac0addbc1288e3507cf549344f75e69cc28
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33430705"
---
# <a name="imessagedeleteattach"></a><span data-ttu-id="e8487-103">IMessage::DeleteAttach</span><span class="sxs-lookup"><span data-stu-id="e8487-103">IMessage::DeleteAttach</span></span>

  
  
<span data-ttu-id="e8487-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="e8487-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="e8487-105">删除附件。</span><span class="sxs-lookup"><span data-stu-id="e8487-105">Deletes an attachment.</span></span>
  
```cpp
HRESULT DeleteAttach(
ULONG ulAttachmentNum,
ULONG_PTR ulUIParam,
LPMAPIPROGRESS lpProgress,
ULONG ulFlags
);
```

## <a name="parameters"></a><span data-ttu-id="e8487-106">参数</span><span class="sxs-lookup"><span data-stu-id="e8487-106">Parameters</span></span>

 <span data-ttu-id="e8487-107">_ulAttachmentNum_</span><span class="sxs-lookup"><span data-stu-id="e8487-107">_ulAttachmentNum_</span></span>
  
> <span data-ttu-id="e8487-108">[in]要删除的附件的索引号。</span><span class="sxs-lookup"><span data-stu-id="e8487-108">[in] Index number of the attachment to delete.</span></span> <span data-ttu-id="e8487-109">这是[PidTagAttachNumber](pidtagattachnumber-canonical-property.md) PR_ATTACH_NUM (附件) 的值。 </span><span class="sxs-lookup"><span data-stu-id="e8487-109">This is the value for the attachment's **PR_ATTACH_NUM** ([PidTagAttachNumber](pidtagattachnumber-canonical-property.md)) property.</span></span>
    
 <span data-ttu-id="e8487-110">_ulUIParam_</span><span class="sxs-lookup"><span data-stu-id="e8487-110">_ulUIParam_</span></span>
  
> <span data-ttu-id="e8487-111">[in]该方法显示的任何对话框或窗口的父窗口的句柄。</span><span class="sxs-lookup"><span data-stu-id="e8487-111">[in] Handle to the parent window of any dialog boxes or windows this method displays.</span></span> <span data-ttu-id="e8487-112">除非  _在 ulFlags_ 参数中设置了 ATTACH_DIALOG 标志，否则将忽略  _ulUIParam_ 参数。</span><span class="sxs-lookup"><span data-stu-id="e8487-112">The  _ulUIParam_ parameter is ignored unless the ATTACH_DIALOG flag is set in the  _ulFlags_ parameter.</span></span> 
    
 <span data-ttu-id="e8487-113">_lpProgress_</span><span class="sxs-lookup"><span data-stu-id="e8487-113">_lpProgress_</span></span>
  
> <span data-ttu-id="e8487-114">[in]指向显示进度指示器的进度对象的指针。</span><span class="sxs-lookup"><span data-stu-id="e8487-114">[in] Pointer to a progress object that displays a progress indicator.</span></span> <span data-ttu-id="e8487-115">如果在  _lpProgress_ 中传递 NULL，则邮件存储提供程序使用 MAPI 进度对象实现显示进度指示器。</span><span class="sxs-lookup"><span data-stu-id="e8487-115">If NULL is passed in  _lpProgress_, the message store provider displays a progress indicator using the MAPI progress object implementation.</span></span> <span data-ttu-id="e8487-116">除非在 _ulFlags_ 中设置了 ATTACH_DIALOG 标志，否则将忽略 _lpProgress_ 参数。</span><span class="sxs-lookup"><span data-stu-id="e8487-116">The  _lpProgress_ parameter is ignored unless the ATTACH_DIALOG flag is set in  _ulFlags_.</span></span>
    
 <span data-ttu-id="e8487-117">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="e8487-117">_ulFlags_</span></span>
  
> <span data-ttu-id="e8487-118">[in]控制用户界面显示的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="e8487-118">[in] Bitmask of flags that controls the display of a user interface.</span></span> <span data-ttu-id="e8487-119">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="e8487-119">The following flag can be set:</span></span>
    
<span data-ttu-id="e8487-120">ATTACH_DIALOG</span><span class="sxs-lookup"><span data-stu-id="e8487-120">ATTACH_DIALOG</span></span> 
  
> <span data-ttu-id="e8487-121">请求在操作继续时显示进度指示器。</span><span class="sxs-lookup"><span data-stu-id="e8487-121">Requests the display of a progress indicator as the operation proceeds.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="e8487-122">返回值</span><span class="sxs-lookup"><span data-stu-id="e8487-122">Return value</span></span>

<span data-ttu-id="e8487-123">S_OK</span><span class="sxs-lookup"><span data-stu-id="e8487-123">S_OK</span></span> 
  
> <span data-ttu-id="e8487-124">附件已成功删除。</span><span class="sxs-lookup"><span data-stu-id="e8487-124">The attachment was successfully deleted.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="e8487-125">备注</span><span class="sxs-lookup"><span data-stu-id="e8487-125">Remarks</span></span>

<span data-ttu-id="e8487-126">**IMessage：:D eleteAttach** 方法从邮件中删除附件。</span><span class="sxs-lookup"><span data-stu-id="e8487-126">The **IMessage::DeleteAttach** method deletes an attachment from within a message.</span></span> 
  
<span data-ttu-id="e8487-127">在调用邮件的 [IMAPIProp：：SaveChanges](imapiprop-savechanges.md) 方法之前，不会永久删除已删除的附件。</span><span class="sxs-lookup"><span data-stu-id="e8487-127">A deleted attachment is not permanently deleted until the message's [IMAPIProp::SaveChanges](imapiprop-savechanges.md) method has been called.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="e8487-128">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="e8487-128">Notes to callers</span></span>

<span data-ttu-id="e8487-129">在调用 **DeleteAttach** 之前，请为附件及其每个流调用 **IUnknown：：Release** 方法。</span><span class="sxs-lookup"><span data-stu-id="e8487-129">Before calling **DeleteAttach**, call the **IUnknown::Release** method for the attachment and each of its streams.</span></span> 
  
<span data-ttu-id="e8487-130">由于删除附件的过程可能很长， **因此 DeleteAttach** 提供了显示进度指示器的机制。</span><span class="sxs-lookup"><span data-stu-id="e8487-130">Because deleting an attachment can be a lengthy process, **DeleteAttach** provides the mechanism that displays a progress indicator.</span></span> <span data-ttu-id="e8487-131">可以通过将指针传递给 [IMAPIProgress ：IUnknown](imapiprogressiunknown.md) 实现或 NULL（如果你没有实现）来请求显示进度指示器。</span><span class="sxs-lookup"><span data-stu-id="e8487-131">You can request the display of a progress indicator by passing a pointer to your [IMAPIProgress : IUnknown](imapiprogressiunknown.md) implementation or NULL if you do not have an implementation.</span></span> <span data-ttu-id="e8487-132">还必须在  _ulUIParam_ 参数中指定窗口句柄，在  _ulFlags_ ATTACH_DIALOG指定该窗口句柄。</span><span class="sxs-lookup"><span data-stu-id="e8487-132">You must also specify a window handle in the  _ulUIParam_ parameter and the ATTACH_DIALOG flag in the  _ulFlags_ parameter.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="e8487-133">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="e8487-133">MFCMAPI reference</span></span>

<span data-ttu-id="e8487-134">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="e8487-134">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="e8487-135">**文件**</span><span class="sxs-lookup"><span data-stu-id="e8487-135">**File**</span></span>|<span data-ttu-id="e8487-136">**函数**</span><span class="sxs-lookup"><span data-stu-id="e8487-136">**Function**</span></span>|<span data-ttu-id="e8487-137">**备注**</span><span class="sxs-lookup"><span data-stu-id="e8487-137">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e8487-138">AttachmentsDlg.cpp</span><span class="sxs-lookup"><span data-stu-id="e8487-138">AttachmentsDlg.cpp</span></span>  <br/> |<span data-ttu-id="e8487-139">CAttachmentsDlg：：OnDeleteSelectedItem</span><span class="sxs-lookup"><span data-stu-id="e8487-139">CAttachmentsDlg::OnDeleteSelectedItem</span></span>  <br/> |<span data-ttu-id="e8487-140">MFCMAPI 使用 **IMessage：:D eleteAttach** 方法删除选定的附件。</span><span class="sxs-lookup"><span data-stu-id="e8487-140">MFCMAPI uses the **IMessage::DeleteAttach** method to delete the selected attachment.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="e8487-141">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e8487-141">See also</span></span>



[<span data-ttu-id="e8487-142">IMAPIProp::SaveChanges</span><span class="sxs-lookup"><span data-stu-id="e8487-142">IMAPIProp::SaveChanges</span></span>](imapiprop-savechanges.md)
  
[<span data-ttu-id="e8487-143">IMessage : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="e8487-143">IMessage : IMAPIProp</span></span>](imessageimapiprop.md)


[<span data-ttu-id="e8487-144">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="e8487-144">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

