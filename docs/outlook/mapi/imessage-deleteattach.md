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
ms.openlocfilehash: de5c98272c08c469acf23b0ecae7eac0a2d1bfe6
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22592512"
---
# <a name="imessagedeleteattach"></a><span data-ttu-id="b893e-103">IMessage::DeleteAttach</span><span class="sxs-lookup"><span data-stu-id="b893e-103">IMessage::DeleteAttach</span></span>

  
  
<span data-ttu-id="b893e-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="b893e-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="b893e-105">删除附件。</span><span class="sxs-lookup"><span data-stu-id="b893e-105">Deletes an attachment.</span></span>
  
```cpp
HRESULT DeleteAttach(
ULONG ulAttachmentNum,
ULONG_PTR ulUIParam,
LPMAPIPROGRESS lpProgress,
ULONG ulFlags
);
```

## <a name="parameters"></a><span data-ttu-id="b893e-106">参数</span><span class="sxs-lookup"><span data-stu-id="b893e-106">Parameters</span></span>

 <span data-ttu-id="b893e-107">_ulAttachmentNum_</span><span class="sxs-lookup"><span data-stu-id="b893e-107">_ulAttachmentNum_</span></span>
  
> <span data-ttu-id="b893e-108">[in]若要删除的附件的索引号。</span><span class="sxs-lookup"><span data-stu-id="b893e-108">[in] Index number of the attachment to delete.</span></span> <span data-ttu-id="b893e-109">这是附件的**PR_ATTACH_NUM** ([PidTagAttachNumber](pidtagattachnumber-canonical-property.md)) 属性的值。</span><span class="sxs-lookup"><span data-stu-id="b893e-109">This is the value for the attachment's **PR_ATTACH_NUM** ([PidTagAttachNumber](pidtagattachnumber-canonical-property.md)) property.</span></span>
    
 <span data-ttu-id="b893e-110">_ulUIParam_</span><span class="sxs-lookup"><span data-stu-id="b893e-110">_ulUIParam_</span></span>
  
> <span data-ttu-id="b893e-111">[in]任何对话框的父窗口或该方法显示的窗口句柄。</span><span class="sxs-lookup"><span data-stu-id="b893e-111">[in] Handle to the parent window of any dialog boxes or windows this method displays.</span></span> <span data-ttu-id="b893e-112">除非 ATTACH_DIALOG 标志设置_ulFlags_参数中，将忽略该_ulUIParam_参数。</span><span class="sxs-lookup"><span data-stu-id="b893e-112">The  _ulUIParam_ parameter is ignored unless the ATTACH_DIALOG flag is set in the  _ulFlags_ parameter.</span></span> 
    
 <span data-ttu-id="b893e-113">_lpProgress_</span><span class="sxs-lookup"><span data-stu-id="b893e-113">_lpProgress_</span></span>
  
> <span data-ttu-id="b893e-114">[in]对显示进度指示器进度对象的指针。</span><span class="sxs-lookup"><span data-stu-id="b893e-114">[in] Pointer to a progress object that displays a progress indicator.</span></span> <span data-ttu-id="b893e-115">如果在_lpProgress_传递 NULL，则消息存储提供程序将显示进度指示器使用 MAPI 进度对象实现。</span><span class="sxs-lookup"><span data-stu-id="b893e-115">If NULL is passed in  _lpProgress_, the message store provider displays a progress indicator using the MAPI progress object implementation.</span></span> <span data-ttu-id="b893e-116">除非_ulFlags_中设置了 ATTACH_DIALOG 标志，则将忽略该_lpProgress_参数。</span><span class="sxs-lookup"><span data-stu-id="b893e-116">The  _lpProgress_ parameter is ignored unless the ATTACH_DIALOG flag is set in  _ulFlags_.</span></span>
    
 <span data-ttu-id="b893e-117">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="b893e-117">_ulFlags_</span></span>
  
> <span data-ttu-id="b893e-118">[in]位掩码的标志，控制的用户界面的显示。</span><span class="sxs-lookup"><span data-stu-id="b893e-118">[in] Bitmask of flags that controls the display of a user interface.</span></span> <span data-ttu-id="b893e-119">可以设置以下标记：</span><span class="sxs-lookup"><span data-stu-id="b893e-119">The following flag can be set:</span></span>
    
<span data-ttu-id="b893e-120">ATTACH_DIALOG</span><span class="sxs-lookup"><span data-stu-id="b893e-120">ATTACH_DIALOG</span></span> 
  
> <span data-ttu-id="b893e-121">随着操作进行请求进度指示器的显示。</span><span class="sxs-lookup"><span data-stu-id="b893e-121">Requests the display of a progress indicator as the operation proceeds.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="b893e-122">返回值</span><span class="sxs-lookup"><span data-stu-id="b893e-122">Return value</span></span>

<span data-ttu-id="b893e-123">S_OK</span><span class="sxs-lookup"><span data-stu-id="b893e-123">S_OK</span></span> 
  
> <span data-ttu-id="b893e-124">已成功删除附件。</span><span class="sxs-lookup"><span data-stu-id="b893e-124">The attachment was successfully deleted.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="b893e-125">注解</span><span class="sxs-lookup"><span data-stu-id="b893e-125">Remarks</span></span>

<span data-ttu-id="b893e-126">**IMessage::DeleteAttach**方法删除从邮件中的附件。</span><span class="sxs-lookup"><span data-stu-id="b893e-126">The **IMessage::DeleteAttach** method deletes an attachment from within a message.</span></span> 
  
<span data-ttu-id="b893e-127">消息的[IMAPIProp::SaveChanges](imapiprop-savechanges.md)方法被调用之前，已删除的附件未被永久删除。</span><span class="sxs-lookup"><span data-stu-id="b893e-127">A deleted attachment is not permanently deleted until the message's [IMAPIProp::SaveChanges](imapiprop-savechanges.md) method has been called.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="b893e-128">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="b893e-128">Notes to callers</span></span>

<span data-ttu-id="b893e-129">调用**DeleteAttach**之前, 的附件和每个其流中调用**IUnknown::Release**方法。</span><span class="sxs-lookup"><span data-stu-id="b893e-129">Before calling **DeleteAttach**, call the **IUnknown::Release** method for the attachment and each of its streams.</span></span> 
  
<span data-ttu-id="b893e-130">由于删除附件可能会很长时间， **DeleteAttach**提供显示进度指示器的机制。</span><span class="sxs-lookup"><span data-stu-id="b893e-130">Because deleting an attachment can be a lengthy process, **DeleteAttach** provides the mechanism that displays a progress indicator.</span></span> <span data-ttu-id="b893e-131">您可以通过传递一个指向请求的进度指示器显示您[IMAPIProgress: IUnknown](imapiprogressiunknown.md)实现或 NULL，如果您没有实施。</span><span class="sxs-lookup"><span data-stu-id="b893e-131">You can request the display of a progress indicator by passing a pointer to your [IMAPIProgress : IUnknown](imapiprogressiunknown.md) implementation or NULL if you do not have an implementation.</span></span> <span data-ttu-id="b893e-132">您还必须在_ulUIParam_参数和 ATTACH_DIALOG 标志_ulFlags_参数中的指定窗口句柄。</span><span class="sxs-lookup"><span data-stu-id="b893e-132">You must also specify a window handle in the  _ulUIParam_ parameter and the ATTACH_DIALOG flag in the  _ulFlags_ parameter.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="b893e-133">MFCMAPI 参考 （英文）</span><span class="sxs-lookup"><span data-stu-id="b893e-133">MFCMAPI reference</span></span>

<span data-ttu-id="b893e-134">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="b893e-134">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="b893e-135">**文件**</span><span class="sxs-lookup"><span data-stu-id="b893e-135">**File**</span></span>|<span data-ttu-id="b893e-136">**函数**</span><span class="sxs-lookup"><span data-stu-id="b893e-136">**Function**</span></span>|<span data-ttu-id="b893e-137">**Comment**</span><span class="sxs-lookup"><span data-stu-id="b893e-137">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b893e-138">AttachmentsDlg.cpp</span><span class="sxs-lookup"><span data-stu-id="b893e-138">AttachmentsDlg.cpp</span></span>  <br/> |<span data-ttu-id="b893e-139">CAttachmentsDlg::OnDeleteSelectedItem</span><span class="sxs-lookup"><span data-stu-id="b893e-139">CAttachmentsDlg::OnDeleteSelectedItem</span></span>  <br/> |<span data-ttu-id="b893e-140">MFCMAPI 使用**IMessage::DeleteAttach**方法删除所选的附件。</span><span class="sxs-lookup"><span data-stu-id="b893e-140">MFCMAPI uses the **IMessage::DeleteAttach** method to delete the selected attachment.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="b893e-141">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b893e-141">See also</span></span>



[<span data-ttu-id="b893e-142">IMAPIProp::SaveChanges</span><span class="sxs-lookup"><span data-stu-id="b893e-142">IMAPIProp::SaveChanges</span></span>](imapiprop-savechanges.md)
  
[<span data-ttu-id="b893e-143">IMessage : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="b893e-143">IMessage : IMAPIProp</span></span>](imessageimapiprop.md)


[<span data-ttu-id="b893e-144">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="b893e-144">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)
