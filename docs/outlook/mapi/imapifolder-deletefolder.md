---
title: IMAPIFolderDeleteFolder
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIFolder.DeleteFolder
api_type:
- COM
ms.assetid: 6c3e883c-80c0-4eda-8f81-8277d933a74b
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: a476607927f3563ede94a04ccfe4f7a3749c978e
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33417404"
---
# <a name="imapifolderdeletefolder"></a><span data-ttu-id="e3006-103">IMAPIFolder::DeleteFolder</span><span class="sxs-lookup"><span data-stu-id="e3006-103">IMAPIFolder::DeleteFolder</span></span>

  
  
<span data-ttu-id="e3006-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="e3006-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="e3006-105">删除子文件夹。</span><span class="sxs-lookup"><span data-stu-id="e3006-105">Deletes a subfolder.</span></span>
  
```cpp
HRESULT DeleteFolder(
  ULONG_PTR cbEntryID,
  LPENTRYID lpEntryID,
  ULONG_PTR ulUIParam,
  LPMAPIPROGRESS lpProgress,
  ULONG ulFlags
);
```

## <a name="parameters"></a><span data-ttu-id="e3006-106">参数</span><span class="sxs-lookup"><span data-stu-id="e3006-106">Parameters</span></span>

 <span data-ttu-id="e3006-107">_cbEntryID_</span><span class="sxs-lookup"><span data-stu-id="e3006-107">_cbEntryID_</span></span>
  
> <span data-ttu-id="e3006-108">[in]  _lpEntryID_ 参数指向的条目标识符中的字节计数。</span><span class="sxs-lookup"><span data-stu-id="e3006-108">[in] The byte count in the entry identifier pointed to by the  _lpEntryID_ parameter.</span></span> 
    
 <span data-ttu-id="e3006-109">_lpEntryID_</span><span class="sxs-lookup"><span data-stu-id="e3006-109">_lpEntryID_</span></span>
  
> <span data-ttu-id="e3006-110">[in]指向要删除的子文件夹的条目标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="e3006-110">[in] A pointer to the entry identifier of the subfolder to delete.</span></span>
    
 <span data-ttu-id="e3006-111">_ulUIParam_</span><span class="sxs-lookup"><span data-stu-id="e3006-111">_ulUIParam_</span></span>
  
> <span data-ttu-id="e3006-112">[in]进度指示器的父窗口的句柄。</span><span class="sxs-lookup"><span data-stu-id="e3006-112">[in] A handle to the parent window of the progress indicator.</span></span> <span data-ttu-id="e3006-113">除非  _在 ulFlags_ 参数中设置了 FOLDER_DIALOG 标志，否则将忽略  _ulUIParam_ 参数。</span><span class="sxs-lookup"><span data-stu-id="e3006-113">The  _ulUIParam_ parameter is ignored unless the FOLDER_DIALOG flag is set in the  _ulFlags_ parameter.</span></span> 
    
 <span data-ttu-id="e3006-114">_lpProgress_</span><span class="sxs-lookup"><span data-stu-id="e3006-114">_lpProgress_</span></span>
  
> <span data-ttu-id="e3006-115">[in]指向显示进度指示器的进度对象的指针。</span><span class="sxs-lookup"><span data-stu-id="e3006-115">[in] A pointer to a progress object that displays a progress indicator.</span></span> <span data-ttu-id="e3006-116">如果在  _lpProgress_ 中传递 NULL，则邮件存储提供程序使用 MAPI 进度对象实现显示进度指示器。</span><span class="sxs-lookup"><span data-stu-id="e3006-116">If NULL is passed in  _lpProgress_, the message store provider displays a progress indicator by using the MAPI progress object implementation.</span></span> <span data-ttu-id="e3006-117">除非在 _ulFlags_ 中设置了 FOLDER_DIALOG 标志，否则将忽略 _lpProgress_ 参数。</span><span class="sxs-lookup"><span data-stu-id="e3006-117">The  _lpProgress_ parameter is ignored unless the FOLDER_DIALOG flag is set in  _ulFlags_.</span></span>
    
 <span data-ttu-id="e3006-118">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="e3006-118">_ulFlags_</span></span>
  
> <span data-ttu-id="e3006-119">[in]控制子文件夹删除的标记位掩码。</span><span class="sxs-lookup"><span data-stu-id="e3006-119">[in] A bitmask of flags that controls the deletion of the subfolder.</span></span> <span data-ttu-id="e3006-120">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="e3006-120">The following flags can be set:</span></span>
    
<span data-ttu-id="e3006-121">DEL_FOLDERS</span><span class="sxs-lookup"><span data-stu-id="e3006-121">DEL_FOLDERS</span></span> 
  
> <span data-ttu-id="e3006-122">应删除  _lpEntryID_ 指向的子文件夹的所有子文件夹。</span><span class="sxs-lookup"><span data-stu-id="e3006-122">All subfolders of the subfolder pointed to by  _lpEntryID_ should be deleted.</span></span> 
    
<span data-ttu-id="e3006-123">DEL_MESSAGES</span><span class="sxs-lookup"><span data-stu-id="e3006-123">DEL_MESSAGES</span></span> 
  
> <span data-ttu-id="e3006-124">应删除  _lpEntryID_ 指向的子文件夹内的所有邮件。</span><span class="sxs-lookup"><span data-stu-id="e3006-124">All messages in the subfolder pointed to by  _lpEntryID_ should be deleted.</span></span> 
    
<span data-ttu-id="e3006-125">FOLDER_DIALOG</span><span class="sxs-lookup"><span data-stu-id="e3006-125">FOLDER_DIALOG</span></span> 
  
> <span data-ttu-id="e3006-126">在操作进行时，应显示进度指示器。</span><span class="sxs-lookup"><span data-stu-id="e3006-126">A progress indicator should be displayed while the operation proceeds.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="e3006-127">返回值</span><span class="sxs-lookup"><span data-stu-id="e3006-127">Return value</span></span>

<span data-ttu-id="e3006-128">S_OK</span><span class="sxs-lookup"><span data-stu-id="e3006-128">S_OK</span></span> 
  
> <span data-ttu-id="e3006-129">指定的文件夹已成功删除。</span><span class="sxs-lookup"><span data-stu-id="e3006-129">The specified folder has been successfully deleted.</span></span>
    
<span data-ttu-id="e3006-130">MAPI_E_HAS_FOLDERS</span><span class="sxs-lookup"><span data-stu-id="e3006-130">MAPI_E_HAS_FOLDERS</span></span> 
  
> <span data-ttu-id="e3006-131">要删除的子文件夹包含子文件夹，并且未DEL_FOLDERS子文件夹标记。</span><span class="sxs-lookup"><span data-stu-id="e3006-131">The subfolder being deleted contains subfolders, and the DEL_FOLDERS flag was not set.</span></span> <span data-ttu-id="e3006-132">未删除子文件夹。</span><span class="sxs-lookup"><span data-stu-id="e3006-132">The subfolders were not deleted.</span></span>
    
<span data-ttu-id="e3006-133">MAPI_E_HAS_MESSAGES</span><span class="sxs-lookup"><span data-stu-id="e3006-133">MAPI_E_HAS_MESSAGES</span></span> 
  
> <span data-ttu-id="e3006-134">要删除的子文件夹包含邮件，并且未DEL_MESSAGES子文件夹标记。</span><span class="sxs-lookup"><span data-stu-id="e3006-134">The subfolder being deleted contains messages, and the DEL_MESSAGES flag was not set.</span></span> <span data-ttu-id="e3006-135">未删除子文件夹。</span><span class="sxs-lookup"><span data-stu-id="e3006-135">The subfolder was not deleted.</span></span>
    
<span data-ttu-id="e3006-136">MAPI_W_PARTIAL_COMPLETION</span><span class="sxs-lookup"><span data-stu-id="e3006-136">MAPI_W_PARTIAL_COMPLETION</span></span> 
  
> <span data-ttu-id="e3006-137">调用成功，但并非所有条目都已成功删除。</span><span class="sxs-lookup"><span data-stu-id="e3006-137">The call succeeded, but not all of the entries were successfully deleted.</span></span> <span data-ttu-id="e3006-138">返回此警告时，应成功处理呼叫。</span><span class="sxs-lookup"><span data-stu-id="e3006-138">When this warning is returned, the call should be handled as successful.</span></span> <span data-ttu-id="e3006-139">若要测试此警告，请使用 **HR_FAILED** 宏。</span><span class="sxs-lookup"><span data-stu-id="e3006-139">To test for this warning, use the **HR_FAILED** macro.</span></span> <span data-ttu-id="e3006-140">有关详细信息，请参阅使用 [宏处理错误](using-macros-for-error-handling.md)。</span><span class="sxs-lookup"><span data-stu-id="e3006-140">For more information, see [Using Macros for Error Handling](using-macros-for-error-handling.md).</span></span>
    
## <a name="remarks"></a><span data-ttu-id="e3006-141">备注</span><span class="sxs-lookup"><span data-stu-id="e3006-141">Remarks</span></span>

<span data-ttu-id="e3006-142">**IMAPIFolder：:D eleteFolder** 方法删除子文件夹。</span><span class="sxs-lookup"><span data-stu-id="e3006-142">The **IMAPIFolder::DeleteFolder** method deletes a subfolder.</span></span> <span data-ttu-id="e3006-143">默认情况下 **，DeleteFolder** 仅对空文件夹运行，但您可以通过设置两个标志成功在非空文件夹上使用它：DEL_FOLDERS 和 DEL_MESSAGES。</span><span class="sxs-lookup"><span data-stu-id="e3006-143">By default, **DeleteFolder** operates only on empty folders, but you can use it successfully on non-empty folders by setting two flags: DEL_FOLDERS and DEL_MESSAGES.</span></span> <span data-ttu-id="e3006-144">只有在 **DeleteFolder** 调用上同时设置 DEL_FOLDERS 和 DEL_MESSAGES 标记的空文件夹或文件夹才能删除。</span><span class="sxs-lookup"><span data-stu-id="e3006-144">Only empty folders or folders that set both the DEL_FOLDERS and DEL_MESSAGES flags on the **DeleteFolder** call can be deleted.</span></span> <span data-ttu-id="e3006-145">DEL_FOLDERS可删除文件夹的所有子文件夹;DEL_MESSAGES可删除文件夹的所有邮件。</span><span class="sxs-lookup"><span data-stu-id="e3006-145">DEL_FOLDERS enables all of the folder's subfolders to be removed; DEL_MESSAGES enables all of the folder's messages to be removed.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="e3006-146">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="e3006-146">Notes to implementers</span></span>

<span data-ttu-id="e3006-147">当删除操作涉及多个文件夹时，请尽可能完全地执行每个文件夹的操作。</span><span class="sxs-lookup"><span data-stu-id="e3006-147">When the delete operation involves more than one folder, perform the operation as completely as possible for each folder.</span></span> <span data-ttu-id="e3006-148">有时，要删除的文件夹之一不存在，或者已移动到其他位置或已将其复制。</span><span class="sxs-lookup"><span data-stu-id="e3006-148">Sometimes one of the folders to be deleted does not exist or has been moved or copied elsewhere.</span></span> <span data-ttu-id="e3006-149">除非发生超出你的控制范围（如内存不足、磁盘空间不足或邮件存储损坏）发生的故障，否则不要提前停止操作。</span><span class="sxs-lookup"><span data-stu-id="e3006-149">Do not stop the operation prematurely unless a failure occurs that is beyond your control, such as running out of memory, running out of disk space, or corruption in the message store.</span></span>
  
## <a name="notes-to-callers"></a><span data-ttu-id="e3006-150">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="e3006-150">Notes to callers</span></span>

<span data-ttu-id="e3006-151">预计以下情况下会返回这些值。</span><span class="sxs-lookup"><span data-stu-id="e3006-151">Expect these return values under the following conditions.</span></span>
  
|<span data-ttu-id="e3006-152">**Condition**</span><span class="sxs-lookup"><span data-stu-id="e3006-152">**Condition**</span></span>|<span data-ttu-id="e3006-153">**返回值**</span><span class="sxs-lookup"><span data-stu-id="e3006-153">**Return value**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e3006-154">**DeleteFolder** 已成功删除每封邮件和子文件夹。</span><span class="sxs-lookup"><span data-stu-id="e3006-154">**DeleteFolder** has successfully deleted every message and subfolder.</span></span>  <br/> |<span data-ttu-id="e3006-155">S_OK</span><span class="sxs-lookup"><span data-stu-id="e3006-155">S_OK</span></span>  <br/> |
|<span data-ttu-id="e3006-156">**DeleteFolder** 无法成功删除每封邮件和子文件夹。</span><span class="sxs-lookup"><span data-stu-id="e3006-156">**DeleteFolder** was unable to successfully delete every message and subfolder.</span></span>  <br/> |<span data-ttu-id="e3006-157">MAPI_W_PARTIAL_COMPLETION 或 MAPI_E_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="e3006-157">MAPI_W_PARTIAL_COMPLETION or MAPI_E_NOT_FOUND</span></span>  <br/> |
|<span data-ttu-id="e3006-158">**DeleteFolder** 无法完成。</span><span class="sxs-lookup"><span data-stu-id="e3006-158">**DeleteFolder** was unable to complete.</span></span>  <br/> |<span data-ttu-id="e3006-159">任何错误值（MAPI_E_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="e3006-159">Any error value except MAPI_E_NOT_FOUND</span></span>  <br/> |
   
<span data-ttu-id="e3006-160">当 **DeleteFolder** 无法完成时，不要假定未完成任何工作。</span><span class="sxs-lookup"><span data-stu-id="e3006-160">When **DeleteFolder** is unable to complete, do not assume that no work was done.</span></span> <span data-ttu-id="e3006-161">**DeleteFolder** 可能能够在遇到错误之前删除一个或多个邮件和子文件夹。</span><span class="sxs-lookup"><span data-stu-id="e3006-161">**DeleteFolder** might have been able to delete one or more of the messages and subfolders before encountering the error.</span></span> 
  
<span data-ttu-id="e3006-162">如果无法删除一个或多个子文件夹 **，DeleteFolder** MAPI_W_PARTIAL_COMPLETION或MAPI_E_NOT_FOUND，具体取决于邮件存储提供程序的实现。</span><span class="sxs-lookup"><span data-stu-id="e3006-162">If one or more subfolders cannot be deleted, **DeleteFolder** returns MAPI_W_PARTIAL_COMPLETION or MAPI_E_NOT_FOUND, depending on the message store provider's implementation.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="e3006-163">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="e3006-163">MFCMAPI reference</span></span>

<span data-ttu-id="e3006-164">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="e3006-164">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="e3006-165">**文件**</span><span class="sxs-lookup"><span data-stu-id="e3006-165">**File**</span></span>|<span data-ttu-id="e3006-166">**函数**</span><span class="sxs-lookup"><span data-stu-id="e3006-166">**Function**</span></span>|<span data-ttu-id="e3006-167">**备注**</span><span class="sxs-lookup"><span data-stu-id="e3006-167">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e3006-168">MsgStoreDlg.cpp</span><span class="sxs-lookup"><span data-stu-id="e3006-168">MsgStoreDlg.cpp</span></span>  <br/> |<span data-ttu-id="e3006-169">CMsgStoreDlg：：OnDeleteSelectedItem</span><span class="sxs-lookup"><span data-stu-id="e3006-169">CMsgStoreDlg::OnDeleteSelectedItem</span></span>  <br/> |<span data-ttu-id="e3006-170">MFCMAPI 使用 **IMAPIFolder：:D eleteFolder** 方法删除文件夹。</span><span class="sxs-lookup"><span data-stu-id="e3006-170">MFCMAPI uses the **IMAPIFolder::DeleteFolder** method to delete folders.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="e3006-171">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e3006-171">See also</span></span>



[<span data-ttu-id="e3006-172">IMAPIFolder : IMAPIContainer</span><span class="sxs-lookup"><span data-stu-id="e3006-172">IMAPIFolder : IMAPIContainer</span></span>](imapifolderimapicontainer.md)


[<span data-ttu-id="e3006-173">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="e3006-173">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

