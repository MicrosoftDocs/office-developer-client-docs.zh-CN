---
title: IMAPIFolderDeleteMessages
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIFolder.DeleteMessages
api_type:
- COM
ms.assetid: 5a16e62b-9d33-41cd-af2b-9abd403b6f2e
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 7845abc4f3010daf8e13d56ac4b13d0333bad07e
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775360"
---
# <a name="imapifolderdeletemessages"></a><span data-ttu-id="52c4a-103">IMAPIFolder::DeleteMessages</span><span class="sxs-lookup"><span data-stu-id="52c4a-103">IMAPIFolder::DeleteMessages</span></span>

  
  
<span data-ttu-id="52c4a-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="52c4a-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="52c4a-105">删除一个或多个邮件。</span><span class="sxs-lookup"><span data-stu-id="52c4a-105">Deletes one or more messages.</span></span>
  
```cpp
HRESULT DeleteMessages(
  LPENTRYLIST lpMsgList,
  ULONG_PTR ulUIParam,
  LPMAPIPROGRESS lpProgress,
  ULONG ulFlags
);
```

## <a name="parameters"></a><span data-ttu-id="52c4a-106">参数</span><span class="sxs-lookup"><span data-stu-id="52c4a-106">Parameters</span></span>

 <span data-ttu-id="52c4a-107">_lpMsgList_</span><span class="sxs-lookup"><span data-stu-id="52c4a-107">_lpMsgList_</span></span>
  
> <span data-ttu-id="52c4a-108">[in]一个指向[ENTRYLIST](entrylist.md)结构，其中包含要删除的消息的数目和确定邮件的[ENTRYID](entryid.md)结构的数组。</span><span class="sxs-lookup"><span data-stu-id="52c4a-108">[in] A pointer to an [ENTRYLIST](entrylist.md) structure that contains the number of messages to delete and an array of [ENTRYID](entryid.md) structures that identify the messages.</span></span> 
    
 <span data-ttu-id="52c4a-109">_ulUIParam_</span><span class="sxs-lookup"><span data-stu-id="52c4a-109">_ulUIParam_</span></span>
  
> <span data-ttu-id="52c4a-110">[in]进度指示器的父窗口句柄。</span><span class="sxs-lookup"><span data-stu-id="52c4a-110">[in] A handle to the parent window of the progress indicator.</span></span> <span data-ttu-id="52c4a-111">除非 MESSAGE_DIALOG 标志设置_ulFlags_参数中，将忽略该_ulUIParam_参数。</span><span class="sxs-lookup"><span data-stu-id="52c4a-111">The  _ulUIParam_ parameter is ignored unless the MESSAGE_DIALOG flag is set in the  _ulFlags_ parameter.</span></span> 
    
 <span data-ttu-id="52c4a-112">_lpProgress_</span><span class="sxs-lookup"><span data-stu-id="52c4a-112">_lpProgress_</span></span>
  
> <span data-ttu-id="52c4a-113">[in]指向显示进度指示器进度对象的指针。</span><span class="sxs-lookup"><span data-stu-id="52c4a-113">[in] A pointer to a progress object that displays a progress indicator.</span></span> <span data-ttu-id="52c4a-114">如果在_lpProgress_传递 NULL，则消息存储提供程序将使用 MAPI 进度对象实现显示进度指示器。</span><span class="sxs-lookup"><span data-stu-id="52c4a-114">If NULL is passed in  _lpProgress_, the message store provider displays a progress indicator by using the MAPI progress object implementation.</span></span> <span data-ttu-id="52c4a-115">除非 MESSAGE_DIALOG 标志设置_ulFlags_参数中，将忽略该_lpProgress_参数。</span><span class="sxs-lookup"><span data-stu-id="52c4a-115">The  _lpProgress_ parameter is ignored unless the MESSAGE_DIALOG flag is set in the  _ulFlags_ parameter.</span></span> 
    
 <span data-ttu-id="52c4a-116">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="52c4a-116">_ulFlags_</span></span>
  
> <span data-ttu-id="52c4a-117">[in]位掩码的标志，控制如何删除邮件。</span><span class="sxs-lookup"><span data-stu-id="52c4a-117">[in] A bitmask of flags that controls how the messages are deleted.</span></span> <span data-ttu-id="52c4a-118">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="52c4a-118">The following flags can be set:</span></span>
    
<span data-ttu-id="52c4a-119">DELETE_HARD_DELETE</span><span class="sxs-lookup"><span data-stu-id="52c4a-119">DELETE_HARD_DELETE</span></span>
  
> <span data-ttu-id="52c4a-120">永久删除所有邮件，包括软删除的。</span><span class="sxs-lookup"><span data-stu-id="52c4a-120">Permanently removes all messages, including soft-deleted ones.</span></span>
    
<span data-ttu-id="52c4a-121">MESSAGE_DIALOG</span><span class="sxs-lookup"><span data-stu-id="52c4a-121">MESSAGE_DIALOG</span></span> 
  
> <span data-ttu-id="52c4a-122">随着进行操作，则显示进度指示器。</span><span class="sxs-lookup"><span data-stu-id="52c4a-122">Displays a progress indicator as the operation proceeds.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="52c4a-123">返回值</span><span class="sxs-lookup"><span data-stu-id="52c4a-123">Return value</span></span>

<span data-ttu-id="52c4a-124">S_OK</span><span class="sxs-lookup"><span data-stu-id="52c4a-124">S_OK</span></span> 
  
> <span data-ttu-id="52c4a-125">指定的邮件或消息已成功删除。</span><span class="sxs-lookup"><span data-stu-id="52c4a-125">The specified message or messages were successfully deleted.</span></span>
    
<span data-ttu-id="52c4a-126">MAPI_W_PARTIAL_COMPLETION</span><span class="sxs-lookup"><span data-stu-id="52c4a-126">MAPI_W_PARTIAL_COMPLETION</span></span> 
  
> <span data-ttu-id="52c4a-127">调用成功，但不是所有的邮件已成功删除。</span><span class="sxs-lookup"><span data-stu-id="52c4a-127">The call succeeded, but not all of the messages were successfully deleted.</span></span> <span data-ttu-id="52c4a-128">返回此警告时，应处理呼叫为成功。</span><span class="sxs-lookup"><span data-stu-id="52c4a-128">When this warning is returned, the call should be handled as successful.</span></span> <span data-ttu-id="52c4a-129">若要测试此警告，请使用**HR_FAILED**宏。</span><span class="sxs-lookup"><span data-stu-id="52c4a-129">To test for this warning, use the **HR_FAILED** macro.</span></span> <span data-ttu-id="52c4a-130">有关详细信息，请参阅[使用宏的错误处理](using-macros-for-error-handling.md)。</span><span class="sxs-lookup"><span data-stu-id="52c4a-130">For more information, see [Using Macros for Error Handling](using-macros-for-error-handling.md).</span></span>
    
## <a name="remarks"></a><span data-ttu-id="52c4a-131">说明</span><span class="sxs-lookup"><span data-stu-id="52c4a-131">Remarks</span></span>

<span data-ttu-id="52c4a-132">**IMAPIFolder::DeleteMessages**方法从文件夹中删除邮件。</span><span class="sxs-lookup"><span data-stu-id="52c4a-132">The **IMAPIFolder::DeleteMessages** method deletes messages from a folder.</span></span> <span data-ttu-id="52c4a-133">无法删除的邮件的不存在、 已在其他地方移动的、 具有读/写权限打开或当前提交。</span><span class="sxs-lookup"><span data-stu-id="52c4a-133">Messages that do not exist, that have been moved elsewhere, that are open with read/write permission, or that are currently submitted cannot be deleted.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="52c4a-134">针对实施者的注释</span><span class="sxs-lookup"><span data-stu-id="52c4a-134">Notes to implementers</span></span>

<span data-ttu-id="52c4a-135">时删除操作涉及多个邮件，执行操作完全尽可能对于每个文件夹中，即使不能删除一个或多条消息。</span><span class="sxs-lookup"><span data-stu-id="52c4a-135">When the delete operation involves more than one message, perform the operation as completely as possible for each folder, even if one or more of the messages cannot be deleted.</span></span> <span data-ttu-id="52c4a-136">不停止操作提前除非超过了您的控件，如运行内存不足、 不足磁盘空间或损坏消息存储区中的出现故障。</span><span class="sxs-lookup"><span data-stu-id="52c4a-136">Do not stop the operation prematurely unless a failure occurs that is beyond your control, such as running out of memory, running out of disk space, or corruption in the message store.</span></span>
  
## <a name="notes-to-callers"></a><span data-ttu-id="52c4a-137">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="52c4a-137">Notes to callers</span></span>

<span data-ttu-id="52c4a-138">希望在下列情况下的这些返回值。</span><span class="sxs-lookup"><span data-stu-id="52c4a-138">Expect these return values under the following conditions.</span></span>
  
|<span data-ttu-id="52c4a-139">**条件**</span><span class="sxs-lookup"><span data-stu-id="52c4a-139">**Condition**</span></span>|<span data-ttu-id="52c4a-140">**返回值**</span><span class="sxs-lookup"><span data-stu-id="52c4a-140">**Return value**</span></span>|
|:-----|:-----|
|<span data-ttu-id="52c4a-141">**DeleteMessages**已成功删除每条消息。</span><span class="sxs-lookup"><span data-stu-id="52c4a-141">**DeleteMessages** has successfully deleted every message.</span></span>  <br/> |<span data-ttu-id="52c4a-142">S_OK</span><span class="sxs-lookup"><span data-stu-id="52c4a-142">S_OK</span></span>  <br/> |
|<span data-ttu-id="52c4a-143">**DeleteMessages**程序无法成功删除每封邮件和子文件夹。</span><span class="sxs-lookup"><span data-stu-id="52c4a-143">**DeleteMessages** was unable to successfully delete every message and subfolder.</span></span>  <br/> |<span data-ttu-id="52c4a-144">MAPI_W_PARTIAL_COMPLETION 或 MAPI_E_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="52c4a-144">MAPI_W_PARTIAL_COMPLETION or MAPI_E_NOT_FOUND</span></span>  <br/> |
|<span data-ttu-id="52c4a-145">**DeleteMessages**无法完成。</span><span class="sxs-lookup"><span data-stu-id="52c4a-145">**DeleteMessages** was unable to complete.</span></span>  <br/> |<span data-ttu-id="52c4a-146">除 MAPI_E_NOT_FOUND 任何错误值</span><span class="sxs-lookup"><span data-stu-id="52c4a-146">Any error value except MAPI_E_NOT_FOUND</span></span>  <br/> |
   
<span data-ttu-id="52c4a-147">无法完成**DeleteMessages**时，不假定任何工作已完成。</span><span class="sxs-lookup"><span data-stu-id="52c4a-147">When **DeleteMessages** is unable to complete, do not assume that no work was done.</span></span> <span data-ttu-id="52c4a-148">**DeleteMessages**可能已经能够删除一个或多条消息，然后再遇到错误。</span><span class="sxs-lookup"><span data-stu-id="52c4a-148">**DeleteMessages** might have been able to delete one or more of the messages before encountering the error.</span></span> 
  
 <span data-ttu-id="52c4a-149">**DeleteMessages**返回 MAPI_W_PARTIAL_COMPLETION 或 MAPI_E_NOT_FOUND，具体取决于邮件存储的实现。</span><span class="sxs-lookup"><span data-stu-id="52c4a-149">**DeleteMessages** returns MAPI_W_PARTIAL_COMPLETION or MAPI_E_NOT_FOUND, depending on the message store's implementation.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="52c4a-150">MFCMAPI 参考 （英文）</span><span class="sxs-lookup"><span data-stu-id="52c4a-150">MFCMAPI reference</span></span>

<span data-ttu-id="52c4a-151">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="52c4a-151">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="52c4a-152">**文件**</span><span class="sxs-lookup"><span data-stu-id="52c4a-152">**File**</span></span>|<span data-ttu-id="52c4a-153">**函数**</span><span class="sxs-lookup"><span data-stu-id="52c4a-153">**Function**</span></span>|<span data-ttu-id="52c4a-154">**Comment**</span><span class="sxs-lookup"><span data-stu-id="52c4a-154">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="52c4a-155">FolderDlg.cpp</span><span class="sxs-lookup"><span data-stu-id="52c4a-155">FolderDlg.cpp</span></span>  <br/> |<span data-ttu-id="52c4a-156">CFolderDlg::OnDeleteSelectedItem</span><span class="sxs-lookup"><span data-stu-id="52c4a-156">CFolderDlg::OnDeleteSelectedItem</span></span>  <br/> |<span data-ttu-id="52c4a-157">MFCMAPI 使用**IMAPIFolder::DeleteMessages**方法删除指定的邮件。</span><span class="sxs-lookup"><span data-stu-id="52c4a-157">MFCMAPI uses the **IMAPIFolder::DeleteMessages** method to delete the specified messages.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="52c4a-158">另请参阅</span><span class="sxs-lookup"><span data-stu-id="52c4a-158">See also</span></span>



[<span data-ttu-id="52c4a-159">ENTRYID</span><span class="sxs-lookup"><span data-stu-id="52c4a-159">ENTRYID</span></span>](entryid.md)
  
[<span data-ttu-id="52c4a-160">ENTRYLIST</span><span class="sxs-lookup"><span data-stu-id="52c4a-160">ENTRYLIST</span></span>](entrylist.md)
  
[<span data-ttu-id="52c4a-161">IMAPIFolder : IMAPIContainer</span><span class="sxs-lookup"><span data-stu-id="52c4a-161">IMAPIFolder : IMAPIContainer</span></span>](imapifolderimapicontainer.md)


[<span data-ttu-id="52c4a-162">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="52c4a-162">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)
  
[<span data-ttu-id="52c4a-163">使用宏进行错误处理</span><span class="sxs-lookup"><span data-stu-id="52c4a-163">Using Macros for Error Handling</span></span>](using-macros-for-error-handling.md)

