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
ms.openlocfilehash: 15cf8ff7e282035ddff53565aa92e81e3886729c
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775339"
---
# <a name="imapifolderdeletefolder"></a><span data-ttu-id="aa6cc-103">IMAPIFolder::DeleteFolder</span><span class="sxs-lookup"><span data-stu-id="aa6cc-103">IMAPIFolder::DeleteFolder</span></span>

  
  
<span data-ttu-id="aa6cc-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="aa6cc-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="aa6cc-105">删除子文件夹。</span><span class="sxs-lookup"><span data-stu-id="aa6cc-105">Deletes a subfolder.</span></span>
  
```cpp
HRESULT DeleteFolder(
  ULONG_PTR cbEntryID,
  LPENTRYID lpEntryID,
  ULONG_PTR ulUIParam,
  LPMAPIPROGRESS lpProgress,
  ULONG ulFlags
);
```

## <a name="parameters"></a><span data-ttu-id="aa6cc-106">参数</span><span class="sxs-lookup"><span data-stu-id="aa6cc-106">Parameters</span></span>

 <span data-ttu-id="aa6cc-107">_cbEntryID_</span><span class="sxs-lookup"><span data-stu-id="aa6cc-107">_cbEntryID_</span></span>
  
> <span data-ttu-id="aa6cc-108">[in]在_lpEntryID_参数指向的项标识符的字节数。</span><span class="sxs-lookup"><span data-stu-id="aa6cc-108">[in] The byte count in the entry identifier pointed to by the  _lpEntryID_ parameter.</span></span> 
    
 <span data-ttu-id="aa6cc-109">_lpEntryID_</span><span class="sxs-lookup"><span data-stu-id="aa6cc-109">_lpEntryID_</span></span>
  
> <span data-ttu-id="aa6cc-110">[in]指向要删除的子文件夹的项标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="aa6cc-110">[in] A pointer to the entry identifier of the subfolder to delete.</span></span>
    
 <span data-ttu-id="aa6cc-111">_ulUIParam_</span><span class="sxs-lookup"><span data-stu-id="aa6cc-111">_ulUIParam_</span></span>
  
> <span data-ttu-id="aa6cc-112">[in]进度指示器的父窗口句柄。</span><span class="sxs-lookup"><span data-stu-id="aa6cc-112">[in] A handle to the parent window of the progress indicator.</span></span> <span data-ttu-id="aa6cc-113">除非 FOLDER_DIALOG 标志设置_ulFlags_参数中，将忽略该_ulUIParam_参数。</span><span class="sxs-lookup"><span data-stu-id="aa6cc-113">The  _ulUIParam_ parameter is ignored unless the FOLDER_DIALOG flag is set in the  _ulFlags_ parameter.</span></span> 
    
 <span data-ttu-id="aa6cc-114">_lpProgress_</span><span class="sxs-lookup"><span data-stu-id="aa6cc-114">_lpProgress_</span></span>
  
> <span data-ttu-id="aa6cc-115">[in]指向显示进度指示器进度对象的指针。</span><span class="sxs-lookup"><span data-stu-id="aa6cc-115">[in] A pointer to a progress object that displays a progress indicator.</span></span> <span data-ttu-id="aa6cc-116">如果在_lpProgress_传递 NULL，则消息存储提供程序将使用 MAPI 进度对象实现显示进度指示器。</span><span class="sxs-lookup"><span data-stu-id="aa6cc-116">If NULL is passed in  _lpProgress_, the message store provider displays a progress indicator by using the MAPI progress object implementation.</span></span> <span data-ttu-id="aa6cc-117">除非_ulFlags_中设置了 FOLDER_DIALOG 标志，则将忽略该_lpProgress_参数。</span><span class="sxs-lookup"><span data-stu-id="aa6cc-117">The  _lpProgress_ parameter is ignored unless the FOLDER_DIALOG flag is set in  _ulFlags_.</span></span>
    
 <span data-ttu-id="aa6cc-118">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="aa6cc-118">_ulFlags_</span></span>
  
> <span data-ttu-id="aa6cc-119">[in]位掩码的标志控制删除的子文件夹。</span><span class="sxs-lookup"><span data-stu-id="aa6cc-119">[in] A bitmask of flags that controls the deletion of the subfolder.</span></span> <span data-ttu-id="aa6cc-120">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="aa6cc-120">The following flags can be set:</span></span>
    
<span data-ttu-id="aa6cc-121">DEL_FOLDERS</span><span class="sxs-lookup"><span data-stu-id="aa6cc-121">DEL_FOLDERS</span></span> 
  
> <span data-ttu-id="aa6cc-122">应删除的子文件夹指向的_lpEntryID_的所有子文件夹。</span><span class="sxs-lookup"><span data-stu-id="aa6cc-122">All subfolders of the subfolder pointed to by  _lpEntryID_ should be deleted.</span></span> 
    
<span data-ttu-id="aa6cc-123">DEL_MESSAGES</span><span class="sxs-lookup"><span data-stu-id="aa6cc-123">DEL_MESSAGES</span></span> 
  
> <span data-ttu-id="aa6cc-124">应删除指向_lpEntryID_的子文件夹中的所有邮件。</span><span class="sxs-lookup"><span data-stu-id="aa6cc-124">All messages in the subfolder pointed to by  _lpEntryID_ should be deleted.</span></span> 
    
<span data-ttu-id="aa6cc-125">FOLDER_DIALOG</span><span class="sxs-lookup"><span data-stu-id="aa6cc-125">FOLDER_DIALOG</span></span> 
  
> <span data-ttu-id="aa6cc-126">继续操作时，应显示进度指示器。</span><span class="sxs-lookup"><span data-stu-id="aa6cc-126">A progress indicator should be displayed while the operation proceeds.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="aa6cc-127">返回值</span><span class="sxs-lookup"><span data-stu-id="aa6cc-127">Return value</span></span>

<span data-ttu-id="aa6cc-128">S_OK</span><span class="sxs-lookup"><span data-stu-id="aa6cc-128">S_OK</span></span> 
  
> <span data-ttu-id="aa6cc-129">已成功删除指定的文件夹。</span><span class="sxs-lookup"><span data-stu-id="aa6cc-129">The specified folder has been successfully deleted.</span></span>
    
<span data-ttu-id="aa6cc-130">MAPI_E_HAS_FOLDERS</span><span class="sxs-lookup"><span data-stu-id="aa6cc-130">MAPI_E_HAS_FOLDERS</span></span> 
  
> <span data-ttu-id="aa6cc-131">正在删除的子文件夹包含子文件夹，并且未设置 DEL_FOLDERS 标志。</span><span class="sxs-lookup"><span data-stu-id="aa6cc-131">The subfolder being deleted contains subfolders, and the DEL_FOLDERS flag was not set.</span></span> <span data-ttu-id="aa6cc-132">子文件夹未被删除。</span><span class="sxs-lookup"><span data-stu-id="aa6cc-132">The subfolders were not deleted.</span></span>
    
<span data-ttu-id="aa6cc-133">MAPI_E_HAS_MESSAGES</span><span class="sxs-lookup"><span data-stu-id="aa6cc-133">MAPI_E_HAS_MESSAGES</span></span> 
  
> <span data-ttu-id="aa6cc-134">正在删除的子文件夹包含邮件和未设置 DEL_MESSAGES 标志。</span><span class="sxs-lookup"><span data-stu-id="aa6cc-134">The subfolder being deleted contains messages, and the DEL_MESSAGES flag was not set.</span></span> <span data-ttu-id="aa6cc-135">未删除子文件夹。</span><span class="sxs-lookup"><span data-stu-id="aa6cc-135">The subfolder was not deleted.</span></span>
    
<span data-ttu-id="aa6cc-136">MAPI_W_PARTIAL_COMPLETION</span><span class="sxs-lookup"><span data-stu-id="aa6cc-136">MAPI_W_PARTIAL_COMPLETION</span></span> 
  
> <span data-ttu-id="aa6cc-137">调用成功，但不是所有项都已成功删除。</span><span class="sxs-lookup"><span data-stu-id="aa6cc-137">The call succeeded, but not all of the entries were successfully deleted.</span></span> <span data-ttu-id="aa6cc-138">返回此警告时，应处理呼叫为成功。</span><span class="sxs-lookup"><span data-stu-id="aa6cc-138">When this warning is returned, the call should be handled as successful.</span></span> <span data-ttu-id="aa6cc-139">若要测试此警告，请使用**HR_FAILED**宏。</span><span class="sxs-lookup"><span data-stu-id="aa6cc-139">To test for this warning, use the **HR_FAILED** macro.</span></span> <span data-ttu-id="aa6cc-140">有关详细信息，请参阅[使用宏的错误处理](using-macros-for-error-handling.md)。</span><span class="sxs-lookup"><span data-stu-id="aa6cc-140">For more information, see [Using Macros for Error Handling](using-macros-for-error-handling.md).</span></span>
    
## <a name="remarks"></a><span data-ttu-id="aa6cc-141">说明</span><span class="sxs-lookup"><span data-stu-id="aa6cc-141">Remarks</span></span>

<span data-ttu-id="aa6cc-142">**IMAPIFolder::DeleteFolder**方法删除子文件夹。</span><span class="sxs-lookup"><span data-stu-id="aa6cc-142">The **IMAPIFolder::DeleteFolder** method deletes a subfolder.</span></span> <span data-ttu-id="aa6cc-143">默认情况下**DeleteFolder**运行只能在空文件夹，但您可以使用它成功对非空文件夹通过设置两个标志： DEL_FOLDERS 和 DEL_MESSAGES。</span><span class="sxs-lookup"><span data-stu-id="aa6cc-143">By default, **DeleteFolder** operates only on empty folders, but you can use it successfully on non-empty folders by setting two flags: DEL_FOLDERS and DEL_MESSAGES.</span></span> <span data-ttu-id="aa6cc-144">可以删除仅空文件夹或**DeleteFolder**呼叫的设置的 DEL_FOLDERS 和 DEL_MESSAGES 标志设置的文件夹。</span><span class="sxs-lookup"><span data-stu-id="aa6cc-144">Only empty folders or folders that set both the DEL_FOLDERS and DEL_MESSAGES flags on the **DeleteFolder** call can be deleted.</span></span> <span data-ttu-id="aa6cc-145">DEL_FOLDERS 使所有文件夹的子文件夹要删除;DEL_MESSAGES 启用的所有文件夹的邮件中删除。</span><span class="sxs-lookup"><span data-stu-id="aa6cc-145">DEL_FOLDERS enables all of the folder's subfolders to be removed; DEL_MESSAGES enables all of the folder's messages to be removed.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="aa6cc-146">针对实施者的注释</span><span class="sxs-lookup"><span data-stu-id="aa6cc-146">Notes to implementers</span></span>

<span data-ttu-id="aa6cc-147">当删除操作涉及多个文件夹时，每个文件夹尽可能完整执行操作。</span><span class="sxs-lookup"><span data-stu-id="aa6cc-147">When the delete operation involves more than one folder, perform the operation as completely as possible for each folder.</span></span> <span data-ttu-id="aa6cc-148">有时之一要删除的文件夹不存在或已移动或复制到其他位置。</span><span class="sxs-lookup"><span data-stu-id="aa6cc-148">Sometimes one of the folders to be deleted does not exist or has been moved or copied elsewhere.</span></span> <span data-ttu-id="aa6cc-149">不停止操作提前除非超过了您的控件，如运行内存不足、 不足磁盘空间或损坏消息存储区中的出现故障。</span><span class="sxs-lookup"><span data-stu-id="aa6cc-149">Do not stop the operation prematurely unless a failure occurs that is beyond your control, such as running out of memory, running out of disk space, or corruption in the message store.</span></span>
  
## <a name="notes-to-callers"></a><span data-ttu-id="aa6cc-150">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="aa6cc-150">Notes to callers</span></span>

<span data-ttu-id="aa6cc-151">希望在下列情况下的这些返回值。</span><span class="sxs-lookup"><span data-stu-id="aa6cc-151">Expect these return values under the following conditions.</span></span>
  
|<span data-ttu-id="aa6cc-152">**条件**</span><span class="sxs-lookup"><span data-stu-id="aa6cc-152">**Condition**</span></span>|<span data-ttu-id="aa6cc-153">**返回值**</span><span class="sxs-lookup"><span data-stu-id="aa6cc-153">**Return value**</span></span>|
|:-----|:-----|
|<span data-ttu-id="aa6cc-154">**DeleteFolder**已成功删除每封邮件和子文件夹。</span><span class="sxs-lookup"><span data-stu-id="aa6cc-154">**DeleteFolder** has successfully deleted every message and subfolder.</span></span>  <br/> |<span data-ttu-id="aa6cc-155">S_OK</span><span class="sxs-lookup"><span data-stu-id="aa6cc-155">S_OK</span></span>  <br/> |
|<span data-ttu-id="aa6cc-156">**DeleteFolder**程序无法成功删除每封邮件和子文件夹。</span><span class="sxs-lookup"><span data-stu-id="aa6cc-156">**DeleteFolder** was unable to successfully delete every message and subfolder.</span></span>  <br/> |<span data-ttu-id="aa6cc-157">MAPI_W_PARTIAL_COMPLETION 或 MAPI_E_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="aa6cc-157">MAPI_W_PARTIAL_COMPLETION or MAPI_E_NOT_FOUND</span></span>  <br/> |
|<span data-ttu-id="aa6cc-158">**DeleteFolder**无法完成。</span><span class="sxs-lookup"><span data-stu-id="aa6cc-158">**DeleteFolder** was unable to complete.</span></span>  <br/> |<span data-ttu-id="aa6cc-159">除 MAPI_E_NOT_FOUND 任何错误值</span><span class="sxs-lookup"><span data-stu-id="aa6cc-159">Any error value except MAPI_E_NOT_FOUND</span></span>  <br/> |
   
<span data-ttu-id="aa6cc-160">**DeleteFolder**无法完成后，请假定已完成任何工时。</span><span class="sxs-lookup"><span data-stu-id="aa6cc-160">When **DeleteFolder** is unable to complete, do not assume that no work was done.</span></span> <span data-ttu-id="aa6cc-161">**DeleteFolder**可能已经能够删除一个或多个邮件和子文件夹，然后再遇到错误。</span><span class="sxs-lookup"><span data-stu-id="aa6cc-161">**DeleteFolder** might have been able to delete one or more of the messages and subfolders before encountering the error.</span></span> 
  
<span data-ttu-id="aa6cc-162">如果不能删除一个或多个子文件夹， **DeleteFolder**返回 MAPI_W_PARTIAL_COMPLETION 或 MAPI_E_NOT_FOUND，具体取决于消息存储提供程序的实现。</span><span class="sxs-lookup"><span data-stu-id="aa6cc-162">If one or more subfolders cannot be deleted, **DeleteFolder** returns MAPI_W_PARTIAL_COMPLETION or MAPI_E_NOT_FOUND, depending on the message store provider's implementation.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="aa6cc-163">MFCMAPI 参考 （英文）</span><span class="sxs-lookup"><span data-stu-id="aa6cc-163">MFCMAPI reference</span></span>

<span data-ttu-id="aa6cc-164">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="aa6cc-164">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="aa6cc-165">**文件**</span><span class="sxs-lookup"><span data-stu-id="aa6cc-165">**File**</span></span>|<span data-ttu-id="aa6cc-166">**函数**</span><span class="sxs-lookup"><span data-stu-id="aa6cc-166">**Function**</span></span>|<span data-ttu-id="aa6cc-167">**Comment**</span><span class="sxs-lookup"><span data-stu-id="aa6cc-167">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="aa6cc-168">MsgStoreDlg.cpp</span><span class="sxs-lookup"><span data-stu-id="aa6cc-168">MsgStoreDlg.cpp</span></span>  <br/> |<span data-ttu-id="aa6cc-169">CMsgStoreDlg::OnDeleteSelectedItem</span><span class="sxs-lookup"><span data-stu-id="aa6cc-169">CMsgStoreDlg::OnDeleteSelectedItem</span></span>  <br/> |<span data-ttu-id="aa6cc-170">MFCMAPI 使用**IMAPIFolder::DeleteFolder**方法删除文件夹。</span><span class="sxs-lookup"><span data-stu-id="aa6cc-170">MFCMAPI uses the **IMAPIFolder::DeleteFolder** method to delete folders.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="aa6cc-171">另请参阅</span><span class="sxs-lookup"><span data-stu-id="aa6cc-171">See also</span></span>



[<span data-ttu-id="aa6cc-172">IMAPIFolder : IMAPIContainer</span><span class="sxs-lookup"><span data-stu-id="aa6cc-172">IMAPIFolder : IMAPIContainer</span></span>](imapifolderimapicontainer.md)


[<span data-ttu-id="aa6cc-173">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="aa6cc-173">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

