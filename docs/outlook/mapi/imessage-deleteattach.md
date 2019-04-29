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
# <a name="imessagedeleteattach"></a><span data-ttu-id="061f1-103">IMessage::DeleteAttach</span><span class="sxs-lookup"><span data-stu-id="061f1-103">IMessage::DeleteAttach</span></span>

  
  
<span data-ttu-id="061f1-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="061f1-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="061f1-105">删除附件。</span><span class="sxs-lookup"><span data-stu-id="061f1-105">Deletes an attachment.</span></span>
  
```cpp
HRESULT DeleteAttach(
ULONG ulAttachmentNum,
ULONG_PTR ulUIParam,
LPMAPIPROGRESS lpProgress,
ULONG ulFlags
);
```

## <a name="parameters"></a><span data-ttu-id="061f1-106">参数</span><span class="sxs-lookup"><span data-stu-id="061f1-106">Parameters</span></span>

 <span data-ttu-id="061f1-107">_ulAttachmentNum_</span><span class="sxs-lookup"><span data-stu-id="061f1-107">_ulAttachmentNum_</span></span>
  
> <span data-ttu-id="061f1-108">实时要删除的附件的索引号。</span><span class="sxs-lookup"><span data-stu-id="061f1-108">[in] Index number of the attachment to delete.</span></span> <span data-ttu-id="061f1-109">这是附件的**PR_ATTACH_NUM** ([PidTagAttachNumber](pidtagattachnumber-canonical-property.md)) 属性的值。</span><span class="sxs-lookup"><span data-stu-id="061f1-109">This is the value for the attachment's **PR_ATTACH_NUM** ([PidTagAttachNumber](pidtagattachnumber-canonical-property.md)) property.</span></span>
    
 <span data-ttu-id="061f1-110">_ulUIParam_</span><span class="sxs-lookup"><span data-stu-id="061f1-110">_ulUIParam_</span></span>
  
> <span data-ttu-id="061f1-111">实时此方法显示的任何对话框或窗口的父窗口的句柄。</span><span class="sxs-lookup"><span data-stu-id="061f1-111">[in] Handle to the parent window of any dialog boxes or windows this method displays.</span></span> <span data-ttu-id="061f1-112">除非在_ulFlags_参数中设置了 ATTACH_DIALOG 标志, 否则将忽略_ulUIParam_参数。</span><span class="sxs-lookup"><span data-stu-id="061f1-112">The  _ulUIParam_ parameter is ignored unless the ATTACH_DIALOG flag is set in the  _ulFlags_ parameter.</span></span> 
    
 <span data-ttu-id="061f1-113">_lpProgress_</span><span class="sxs-lookup"><span data-stu-id="061f1-113">_lpProgress_</span></span>
  
> <span data-ttu-id="061f1-114">实时指向显示进度指示器的进度对象的指针。</span><span class="sxs-lookup"><span data-stu-id="061f1-114">[in] Pointer to a progress object that displays a progress indicator.</span></span> <span data-ttu-id="061f1-115">如果在_lpProgress_中传递 NULL, 则邮件存储提供程序将使用 MAPI 进度对象实现显示进度指示器。</span><span class="sxs-lookup"><span data-stu-id="061f1-115">If NULL is passed in  _lpProgress_, the message store provider displays a progress indicator using the MAPI progress object implementation.</span></span> <span data-ttu-id="061f1-116">除非在_ulFlags_中设置了 ATTACH_DIALOG 标志, 否则_lpProgress_参数将被忽略。</span><span class="sxs-lookup"><span data-stu-id="061f1-116">The  _lpProgress_ parameter is ignored unless the ATTACH_DIALOG flag is set in  _ulFlags_.</span></span>
    
 <span data-ttu-id="061f1-117">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="061f1-117">_ulFlags_</span></span>
  
> <span data-ttu-id="061f1-118">实时用于控制用户界面显示的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="061f1-118">[in] Bitmask of flags that controls the display of a user interface.</span></span> <span data-ttu-id="061f1-119">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="061f1-119">The following flag can be set:</span></span>
    
<span data-ttu-id="061f1-120">ATTACH_DIALOG</span><span class="sxs-lookup"><span data-stu-id="061f1-120">ATTACH_DIALOG</span></span> 
  
> <span data-ttu-id="061f1-121">在操作进行过程中请求显示进度指示器。</span><span class="sxs-lookup"><span data-stu-id="061f1-121">Requests the display of a progress indicator as the operation proceeds.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="061f1-122">返回值</span><span class="sxs-lookup"><span data-stu-id="061f1-122">Return value</span></span>

<span data-ttu-id="061f1-123">S_OK</span><span class="sxs-lookup"><span data-stu-id="061f1-123">S_OK</span></span> 
  
> <span data-ttu-id="061f1-124">已成功删除附件。</span><span class="sxs-lookup"><span data-stu-id="061f1-124">The attachment was successfully deleted.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="061f1-125">说明</span><span class="sxs-lookup"><span data-stu-id="061f1-125">Remarks</span></span>

<span data-ttu-id="061f1-126">**IMessage::D eleteattach**方法可从邮件中删除附件。</span><span class="sxs-lookup"><span data-stu-id="061f1-126">The **IMessage::DeleteAttach** method deletes an attachment from within a message.</span></span> 
  
<span data-ttu-id="061f1-127">在调用邮件的[IMAPIProp:: SaveChanges](imapiprop-savechanges.md)方法之前, 不会永久删除已删除的附件。</span><span class="sxs-lookup"><span data-stu-id="061f1-127">A deleted attachment is not permanently deleted until the message's [IMAPIProp::SaveChanges](imapiprop-savechanges.md) method has been called.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="061f1-128">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="061f1-128">Notes to callers</span></span>

<span data-ttu-id="061f1-129">在调用**DeleteAttach**之前, 请先调用附件及其每个流的**IUnknown:: Release**方法。</span><span class="sxs-lookup"><span data-stu-id="061f1-129">Before calling **DeleteAttach**, call the **IUnknown::Release** method for the attachment and each of its streams.</span></span> 
  
<span data-ttu-id="061f1-130">由于删除附件可能是一个漫长的过程, 因此**DeleteAttach**提供了显示进度指示器的机制。</span><span class="sxs-lookup"><span data-stu-id="061f1-130">Because deleting an attachment can be a lengthy process, **DeleteAttach** provides the mechanism that displays a progress indicator.</span></span> <span data-ttu-id="061f1-131">您可以通过以下方式请求显示进度指示器: 将指针传递给您的[IMAPIProgress: IUnknown](imapiprogressiunknown.md)实现; 如果没有实现, 则为 NULL。</span><span class="sxs-lookup"><span data-stu-id="061f1-131">You can request the display of a progress indicator by passing a pointer to your [IMAPIProgress : IUnknown](imapiprogressiunknown.md) implementation or NULL if you do not have an implementation.</span></span> <span data-ttu-id="061f1-132">您还必须在_ulUIParam_参数中指定窗口句柄, 并在_ulFlags_参数中指定 ATTACH_DIALOG 标志。</span><span class="sxs-lookup"><span data-stu-id="061f1-132">You must also specify a window handle in the  _ulUIParam_ parameter and the ATTACH_DIALOG flag in the  _ulFlags_ parameter.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="061f1-133">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="061f1-133">MFCMAPI reference</span></span>

<span data-ttu-id="061f1-134">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="061f1-134">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="061f1-135">**文件**</span><span class="sxs-lookup"><span data-stu-id="061f1-135">**File**</span></span>|<span data-ttu-id="061f1-136">**函数**</span><span class="sxs-lookup"><span data-stu-id="061f1-136">**Function**</span></span>|<span data-ttu-id="061f1-137">**备注**</span><span class="sxs-lookup"><span data-stu-id="061f1-137">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="061f1-138">AttachmentsDlg</span><span class="sxs-lookup"><span data-stu-id="061f1-138">AttachmentsDlg.cpp</span></span>  <br/> |<span data-ttu-id="061f1-139">CAttachmentsDlg:: OnDeleteSelectedItem</span><span class="sxs-lookup"><span data-stu-id="061f1-139">CAttachmentsDlg::OnDeleteSelectedItem</span></span>  <br/> |<span data-ttu-id="061f1-140">MFCMAPI 使用**IMessage::D eleteattach**方法删除选定附件。</span><span class="sxs-lookup"><span data-stu-id="061f1-140">MFCMAPI uses the **IMessage::DeleteAttach** method to delete the selected attachment.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="061f1-141">另请参阅</span><span class="sxs-lookup"><span data-stu-id="061f1-141">See also</span></span>



[<span data-ttu-id="061f1-142">IMAPIProp::SaveChanges</span><span class="sxs-lookup"><span data-stu-id="061f1-142">IMAPIProp::SaveChanges</span></span>](imapiprop-savechanges.md)
  
[<span data-ttu-id="061f1-143">IMessage : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="061f1-143">IMessage : IMAPIProp</span></span>](imessageimapiprop.md)


[<span data-ttu-id="061f1-144">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="061f1-144">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

