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
ms.openlocfilehash: 0f0523c01e163b57d9ed37d9b324ec858adbd685
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33426070"
---
# <a name="imapifolderdeletemessages"></a><span data-ttu-id="7d68b-103">IMAPIFolder::DeleteMessages</span><span class="sxs-lookup"><span data-stu-id="7d68b-103">IMAPIFolder::DeleteMessages</span></span>

  
  
<span data-ttu-id="7d68b-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="7d68b-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="7d68b-105">删除一个或多个邮件。</span><span class="sxs-lookup"><span data-stu-id="7d68b-105">Deletes one or more messages.</span></span>
  
```cpp
HRESULT DeleteMessages(
  LPENTRYLIST lpMsgList,
  ULONG_PTR ulUIParam,
  LPMAPIPROGRESS lpProgress,
  ULONG ulFlags
);
```

## <a name="parameters"></a><span data-ttu-id="7d68b-106">参数</span><span class="sxs-lookup"><span data-stu-id="7d68b-106">Parameters</span></span>

 <span data-ttu-id="7d68b-107">_lpMsgList_</span><span class="sxs-lookup"><span data-stu-id="7d68b-107">_lpMsgList_</span></span>
  
> <span data-ttu-id="7d68b-108">[in]指向包含要删除的消息数的 [ENTRYLIST](entrylist.md) 结构的指针，以及标识这些邮件的 [ENTRYID](entryid.md) 结构的数组。</span><span class="sxs-lookup"><span data-stu-id="7d68b-108">[in] A pointer to an [ENTRYLIST](entrylist.md) structure that contains the number of messages to delete and an array of [ENTRYID](entryid.md) structures that identify the messages.</span></span> 
    
 <span data-ttu-id="7d68b-109">_ulUIParam_</span><span class="sxs-lookup"><span data-stu-id="7d68b-109">_ulUIParam_</span></span>
  
> <span data-ttu-id="7d68b-110">[in]进度指示器的父窗口的句柄。</span><span class="sxs-lookup"><span data-stu-id="7d68b-110">[in] A handle to the parent window of the progress indicator.</span></span> <span data-ttu-id="7d68b-111">除非  _在 ulFlags_ 参数中设置了 MESSAGE_DIALOG 标志，否则将忽略  _ulUIParam_ 参数。</span><span class="sxs-lookup"><span data-stu-id="7d68b-111">The  _ulUIParam_ parameter is ignored unless the MESSAGE_DIALOG flag is set in the  _ulFlags_ parameter.</span></span> 
    
 <span data-ttu-id="7d68b-112">_lpProgress_</span><span class="sxs-lookup"><span data-stu-id="7d68b-112">_lpProgress_</span></span>
  
> <span data-ttu-id="7d68b-113">[in]指向显示进度指示器的进度对象的指针。</span><span class="sxs-lookup"><span data-stu-id="7d68b-113">[in] A pointer to a progress object that displays a progress indicator.</span></span> <span data-ttu-id="7d68b-114">如果在  _lpProgress_ 中传递 NULL，则邮件存储提供程序使用 MAPI 进度对象实现显示进度指示器。</span><span class="sxs-lookup"><span data-stu-id="7d68b-114">If NULL is passed in  _lpProgress_, the message store provider displays a progress indicator by using the MAPI progress object implementation.</span></span> <span data-ttu-id="7d68b-115">除非在 _ulFlags_ 参数中设置了 MESSAGE_DIALOG 标志，否则将忽略 _lpProgress_ 参数。</span><span class="sxs-lookup"><span data-stu-id="7d68b-115">The  _lpProgress_ parameter is ignored unless the MESSAGE_DIALOG flag is set in the  _ulFlags_ parameter.</span></span> 
    
 <span data-ttu-id="7d68b-116">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="7d68b-116">_ulFlags_</span></span>
  
> <span data-ttu-id="7d68b-117">[in]控制邮件删除方式的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="7d68b-117">[in] A bitmask of flags that controls how the messages are deleted.</span></span> <span data-ttu-id="7d68b-118">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="7d68b-118">The following flags can be set:</span></span>
    
<span data-ttu-id="7d68b-119">DELETE_HARD_DELETE</span><span class="sxs-lookup"><span data-stu-id="7d68b-119">DELETE_HARD_DELETE</span></span>
  
> <span data-ttu-id="7d68b-120">永久删除所有邮件，包括软删除的邮件。</span><span class="sxs-lookup"><span data-stu-id="7d68b-120">Permanently removes all messages, including soft-deleted ones.</span></span>
    
<span data-ttu-id="7d68b-121">MESSAGE_DIALOG</span><span class="sxs-lookup"><span data-stu-id="7d68b-121">MESSAGE_DIALOG</span></span> 
  
> <span data-ttu-id="7d68b-122">在操作继续时显示进度指示器。</span><span class="sxs-lookup"><span data-stu-id="7d68b-122">Displays a progress indicator as the operation proceeds.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="7d68b-123">返回值</span><span class="sxs-lookup"><span data-stu-id="7d68b-123">Return value</span></span>

<span data-ttu-id="7d68b-124">S_OK</span><span class="sxs-lookup"><span data-stu-id="7d68b-124">S_OK</span></span> 
  
> <span data-ttu-id="7d68b-125">指定的一个或多个邮件已成功删除。</span><span class="sxs-lookup"><span data-stu-id="7d68b-125">The specified message or messages were successfully deleted.</span></span>
    
<span data-ttu-id="7d68b-126">MAPI_W_PARTIAL_COMPLETION</span><span class="sxs-lookup"><span data-stu-id="7d68b-126">MAPI_W_PARTIAL_COMPLETION</span></span> 
  
> <span data-ttu-id="7d68b-127">调用成功，但并非所有邮件都已成功删除。</span><span class="sxs-lookup"><span data-stu-id="7d68b-127">The call succeeded, but not all of the messages were successfully deleted.</span></span> <span data-ttu-id="7d68b-128">返回此警告时，应成功处理呼叫。</span><span class="sxs-lookup"><span data-stu-id="7d68b-128">When this warning is returned, the call should be handled as successful.</span></span> <span data-ttu-id="7d68b-129">若要测试此警告，请使用 **HR_FAILED** 宏。</span><span class="sxs-lookup"><span data-stu-id="7d68b-129">To test for this warning, use the **HR_FAILED** macro.</span></span> <span data-ttu-id="7d68b-130">有关详细信息，请参阅使用 [宏处理错误](using-macros-for-error-handling.md)。</span><span class="sxs-lookup"><span data-stu-id="7d68b-130">For more information, see [Using Macros for Error Handling](using-macros-for-error-handling.md).</span></span>
    
## <a name="remarks"></a><span data-ttu-id="7d68b-131">备注</span><span class="sxs-lookup"><span data-stu-id="7d68b-131">Remarks</span></span>

<span data-ttu-id="7d68b-132">**IMAPIFolder：:D eleteMessages** 方法从文件夹中删除邮件。</span><span class="sxs-lookup"><span data-stu-id="7d68b-132">The **IMAPIFolder::DeleteMessages** method deletes messages from a folder.</span></span> <span data-ttu-id="7d68b-133">无法删除不存在、已移动到其他位置、具有读/写权限打开或当前已提交的邮件。</span><span class="sxs-lookup"><span data-stu-id="7d68b-133">Messages that do not exist, that have been moved elsewhere, that are open with read/write permission, or that are currently submitted cannot be deleted.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="7d68b-134">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="7d68b-134">Notes to implementers</span></span>

<span data-ttu-id="7d68b-135">当删除操作涉及多封邮件时，请尽可能完全地执行每个文件夹的操作，即使一个或多个邮件无法删除。</span><span class="sxs-lookup"><span data-stu-id="7d68b-135">When the delete operation involves more than one message, perform the operation as completely as possible for each folder, even if one or more of the messages cannot be deleted.</span></span> <span data-ttu-id="7d68b-136">除非发生超出你的控制范围（如内存不足、磁盘空间不足或邮件存储损坏）发生的故障，否则不要提前停止操作。</span><span class="sxs-lookup"><span data-stu-id="7d68b-136">Do not stop the operation prematurely unless a failure occurs that is beyond your control, such as running out of memory, running out of disk space, or corruption in the message store.</span></span>
  
## <a name="notes-to-callers"></a><span data-ttu-id="7d68b-137">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="7d68b-137">Notes to callers</span></span>

<span data-ttu-id="7d68b-138">预计以下情况下会返回这些值。</span><span class="sxs-lookup"><span data-stu-id="7d68b-138">Expect these return values under the following conditions.</span></span>
  
|<span data-ttu-id="7d68b-139">**Condition**</span><span class="sxs-lookup"><span data-stu-id="7d68b-139">**Condition**</span></span>|<span data-ttu-id="7d68b-140">**返回值**</span><span class="sxs-lookup"><span data-stu-id="7d68b-140">**Return value**</span></span>|
|:-----|:-----|
|<span data-ttu-id="7d68b-141">**DeleteMessages** 已成功删除每封邮件。</span><span class="sxs-lookup"><span data-stu-id="7d68b-141">**DeleteMessages** has successfully deleted every message.</span></span>  <br/> |<span data-ttu-id="7d68b-142">S_OK</span><span class="sxs-lookup"><span data-stu-id="7d68b-142">S_OK</span></span>  <br/> |
|<span data-ttu-id="7d68b-143">**DeleteMessages** 无法成功删除每封邮件和子文件夹。</span><span class="sxs-lookup"><span data-stu-id="7d68b-143">**DeleteMessages** was unable to successfully delete every message and subfolder.</span></span>  <br/> |<span data-ttu-id="7d68b-144">MAPI_W_PARTIAL_COMPLETION 或 MAPI_E_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="7d68b-144">MAPI_W_PARTIAL_COMPLETION or MAPI_E_NOT_FOUND</span></span>  <br/> |
|<span data-ttu-id="7d68b-145">**DeleteMessages** 无法完成。</span><span class="sxs-lookup"><span data-stu-id="7d68b-145">**DeleteMessages** was unable to complete.</span></span>  <br/> |<span data-ttu-id="7d68b-146">任何错误值（MAPI_E_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="7d68b-146">Any error value except MAPI_E_NOT_FOUND</span></span>  <br/> |
   
<span data-ttu-id="7d68b-147">当 **DeleteMessages** 无法完成时，不要假定未完成任何工作。</span><span class="sxs-lookup"><span data-stu-id="7d68b-147">When **DeleteMessages** is unable to complete, do not assume that no work was done.</span></span> <span data-ttu-id="7d68b-148">**DeleteMessages** 可能能够在遇到错误之前删除一个或多个邮件。</span><span class="sxs-lookup"><span data-stu-id="7d68b-148">**DeleteMessages** might have been able to delete one or more of the messages before encountering the error.</span></span> 
  
 <span data-ttu-id="7d68b-149">**DeleteMessages** MAPI_W_PARTIAL_COMPLETION或MAPI_E_NOT_FOUND，具体取决于邮件存储的实现。</span><span class="sxs-lookup"><span data-stu-id="7d68b-149">**DeleteMessages** returns MAPI_W_PARTIAL_COMPLETION or MAPI_E_NOT_FOUND, depending on the message store's implementation.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="7d68b-150">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="7d68b-150">MFCMAPI reference</span></span>

<span data-ttu-id="7d68b-151">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="7d68b-151">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="7d68b-152">**文件**</span><span class="sxs-lookup"><span data-stu-id="7d68b-152">**File**</span></span>|<span data-ttu-id="7d68b-153">**函数**</span><span class="sxs-lookup"><span data-stu-id="7d68b-153">**Function**</span></span>|<span data-ttu-id="7d68b-154">**备注**</span><span class="sxs-lookup"><span data-stu-id="7d68b-154">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="7d68b-155">FolderDlg.cpp</span><span class="sxs-lookup"><span data-stu-id="7d68b-155">FolderDlg.cpp</span></span>  <br/> |<span data-ttu-id="7d68b-156">CFolderDlg：：OnDeleteSelectedItem</span><span class="sxs-lookup"><span data-stu-id="7d68b-156">CFolderDlg::OnDeleteSelectedItem</span></span>  <br/> |<span data-ttu-id="7d68b-157">MFCMAPI 使用 **IMAPIFolder：:D eleteMessages** 方法删除指定的邮件。</span><span class="sxs-lookup"><span data-stu-id="7d68b-157">MFCMAPI uses the **IMAPIFolder::DeleteMessages** method to delete the specified messages.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="7d68b-158">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7d68b-158">See also</span></span>



[<span data-ttu-id="7d68b-159">ENTRYID</span><span class="sxs-lookup"><span data-stu-id="7d68b-159">ENTRYID</span></span>](entryid.md)
  
[<span data-ttu-id="7d68b-160">ENTRYLIST</span><span class="sxs-lookup"><span data-stu-id="7d68b-160">ENTRYLIST</span></span>](entrylist.md)
  
[<span data-ttu-id="7d68b-161">IMAPIFolder : IMAPIContainer</span><span class="sxs-lookup"><span data-stu-id="7d68b-161">IMAPIFolder : IMAPIContainer</span></span>](imapifolderimapicontainer.md)


[<span data-ttu-id="7d68b-162">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="7d68b-162">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)
  
[<span data-ttu-id="7d68b-163">使用宏处理错误</span><span class="sxs-lookup"><span data-stu-id="7d68b-163">Using Macros for Error Handling</span></span>](using-macros-for-error-handling.md)

