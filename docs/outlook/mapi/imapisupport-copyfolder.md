---
title: IMAPISupportCopyFolder
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISupport.CopyFolder
api_type:
- COM
ms.assetid: c2e0939f-0668-473f-856c-a27af094070b
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 6ffbf74496d4b61357a0fb473b82deedf39ee576
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22570672"
---
# <a name="imapisupportcopyfolder"></a><span data-ttu-id="ce811-103">IMAPISupport::CopyFolder</span><span class="sxs-lookup"><span data-stu-id="ce811-103">IMAPISupport::CopyFolder</span></span>

  
  
<span data-ttu-id="ce811-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="ce811-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="ce811-105">复制或移动到另一个父文件夹的从其当前的父文件夹的文件夹。</span><span class="sxs-lookup"><span data-stu-id="ce811-105">Copies or moves a folder from its current parent folder to another parent folder.</span></span>
  
```cpp
HRESULT CopyFolder(
  LPCIID lpSrcInterface,
  LPVOID lpSrcFolder,
  ULONG cbEntryID,
  LPENTRYID lpEntryID,
  LPCIID lpInterface,
  LPVOID lpDestFolder,
  LPSTR lpszNewFolderName,
  ULONG_PTR ulUIParam,
  LPMAPIPROGRESS lpProgress,
  ULONG ulFlags
);
```

## <a name="parameters"></a><span data-ttu-id="ce811-106">参数</span><span class="sxs-lookup"><span data-stu-id="ce811-106">Parameters</span></span>

 <span data-ttu-id="ce811-107">_lpSrcInterface_</span><span class="sxs-lookup"><span data-stu-id="ce811-107">_lpSrcInterface_</span></span>
  
> <span data-ttu-id="ce811-108">[in]指向接口标识 (IID) 值，该值代表要用于访问复制或移动的文件夹的父文件夹的接口的指针。</span><span class="sxs-lookup"><span data-stu-id="ce811-108">[in] A pointer to the interface identifier (IID) that represents the interface to be used to access the parent folder of the folder to be copied or moved.</span></span>
    
 <span data-ttu-id="ce811-109">_lpSrcFolder_</span><span class="sxs-lookup"><span data-stu-id="ce811-109">_lpSrcFolder_</span></span>
  
> <span data-ttu-id="ce811-110">[in]指向要复制或移动的文件夹的父文件夹的指针。</span><span class="sxs-lookup"><span data-stu-id="ce811-110">[in] A pointer to the parent folder of the folder to be copied or moved.</span></span> 
    
 <span data-ttu-id="ce811-111">_cbEntryID_</span><span class="sxs-lookup"><span data-stu-id="ce811-111">_cbEntryID_</span></span>
  
> <span data-ttu-id="ce811-112">[in]由_lpEntryID_指向该条目标识符中字节数。</span><span class="sxs-lookup"><span data-stu-id="ce811-112">[in] The byte count in the entry identifier pointed to by  _lpEntryID_.</span></span>
    
 <span data-ttu-id="ce811-113">_lpEntryID_</span><span class="sxs-lookup"><span data-stu-id="ce811-113">_lpEntryID_</span></span>
  
> <span data-ttu-id="ce811-114">[in]指向要复制或移动的文件夹的项标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="ce811-114">[in] A pointer to the entry identifier of the folder to be copied or moved.</span></span> 
    
 <span data-ttu-id="ce811-115">_lpInterface_</span><span class="sxs-lookup"><span data-stu-id="ce811-115">_lpInterface_</span></span>
  
> <span data-ttu-id="ce811-116">[in]保留;必须为 NULL。</span><span class="sxs-lookup"><span data-stu-id="ce811-116">[in] Reserved; must be NULL.</span></span>
    
 <span data-ttu-id="ce811-117">_lpDestFolder_</span><span class="sxs-lookup"><span data-stu-id="ce811-117">_lpDestFolder_</span></span>
  
> <span data-ttu-id="ce811-118">[in]指向接收复制或移动的文件夹的文件夹的指针。</span><span class="sxs-lookup"><span data-stu-id="ce811-118">[in] A pointer to the folder that is to receive the folder to be copied or moved.</span></span>
    
 <span data-ttu-id="ce811-119">_lpszNewFolderName_</span><span class="sxs-lookup"><span data-stu-id="ce811-119">_lpszNewFolderName_</span></span>
  
> <span data-ttu-id="ce811-120">[in]一个指向复制或移动的文件夹; 的名称否则，为 NULL，表示复制或移动文件夹应与源文件夹 （由_lpEntryID_指向的文件夹） 中具有相同的名称。</span><span class="sxs-lookup"><span data-stu-id="ce811-120">[in] A pointer to the name of the copied or moved folder; otherwise, NULL, which indicates that the copied or moved folder should have the same name as the source folder (the folder pointed to by  _lpEntryID_).</span></span>
    
 <span data-ttu-id="ce811-121">_ulUIParam_</span><span class="sxs-lookup"><span data-stu-id="ce811-121">_ulUIParam_</span></span>
  
> <span data-ttu-id="ce811-122">[in]的进度指示器对话框中窗口和相关的窗口的句柄。</span><span class="sxs-lookup"><span data-stu-id="ce811-122">[in] A handle of the window for the progress indicator dialog box and related windows.</span></span> <span data-ttu-id="ce811-123">除非 FOLDER_DIALOG 标志设置_ulFlags_参数中，将忽略该_ulUIParam_参数。</span><span class="sxs-lookup"><span data-stu-id="ce811-123">The  _ulUIParam_ parameter is ignored unless the FOLDER_DIALOG flag is set in the  _ulFlags_ parameter.</span></span> 
    
 <span data-ttu-id="ce811-124">_lpProgress_</span><span class="sxs-lookup"><span data-stu-id="ce811-124">_lpProgress_</span></span>
  
> <span data-ttu-id="ce811-125">[in]指向显示进度指示器进度对象的指针。</span><span class="sxs-lookup"><span data-stu-id="ce811-125">[in] A pointer to a progress object that displays a progress indicator.</span></span> <span data-ttu-id="ce811-126">如果在_lpProgress_传递 NULL，则消息存储提供程序将使用 MAPI 进度对象实现显示进度指示器。</span><span class="sxs-lookup"><span data-stu-id="ce811-126">If NULL is passed in  _lpProgress_, the message store provider displays a progress indicator by using the MAPI progress object implementation.</span></span> <span data-ttu-id="ce811-127">除非_ulFlags_中设置了 FOLDER_DIALOG 标志，则将忽略该_lpProgress_参数。</span><span class="sxs-lookup"><span data-stu-id="ce811-127">The  _lpProgress_ parameter is ignored unless the FOLDER_DIALOG flag is set in  _ulFlags_.</span></span>
    
 <span data-ttu-id="ce811-128">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="ce811-128">_ulFlags_</span></span>
  
> <span data-ttu-id="ce811-129">[in]位掩码的标志，控制如何完成复制或移动操作。</span><span class="sxs-lookup"><span data-stu-id="ce811-129">[in] A bitmask of flags that controls how the copy or move operation is accomplished.</span></span> <span data-ttu-id="ce811-130">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="ce811-130">The following flags can be set:</span></span>
    
<span data-ttu-id="ce811-131">COPY_SUBFOLDERS</span><span class="sxs-lookup"><span data-stu-id="ce811-131">COPY_SUBFOLDERS</span></span> 
  
> <span data-ttu-id="ce811-132">应复制或移动所有文件夹的子文件夹。</span><span class="sxs-lookup"><span data-stu-id="ce811-132">All of the folder's subfolders should be copied or moved.</span></span> <span data-ttu-id="ce811-133">当 COPY_SUBFOLDERS 未设置的复制操作时，将复制仅由_lpEntryID_标识的文件夹。</span><span class="sxs-lookup"><span data-stu-id="ce811-133">When COPY_SUBFOLDERS is not set for a copy operation, only the folder identified by  _lpEntryID_ is copied.</span></span> <span data-ttu-id="ce811-134">移动操作，COPY_SUBFOLDERS 行为是默认的无论是否设置了标志。</span><span class="sxs-lookup"><span data-stu-id="ce811-134">With a move operation, the COPY_SUBFOLDERS behavior is the default regardless of whether the flag is set.</span></span> 
    
<span data-ttu-id="ce811-135">FOLDER_DIALOG</span><span class="sxs-lookup"><span data-stu-id="ce811-135">FOLDER_DIALOG</span></span> 
  
> <span data-ttu-id="ce811-136">请求进度指示器的显示。</span><span class="sxs-lookup"><span data-stu-id="ce811-136">Requests the display of a progress indicator.</span></span>
    
<span data-ttu-id="ce811-137">FOLDER_MOVE</span><span class="sxs-lookup"><span data-stu-id="ce811-137">FOLDER_MOVE</span></span> 
  
> <span data-ttu-id="ce811-138">应移动文件夹而不是复制。</span><span class="sxs-lookup"><span data-stu-id="ce811-138">The folder should be moved instead of copied.</span></span> <span data-ttu-id="ce811-139">如果未设置 FOLDER_MOVE，复制该文件夹。</span><span class="sxs-lookup"><span data-stu-id="ce811-139">If FOLDER_MOVE is not set, the folder is copied.</span></span>
    
<span data-ttu-id="ce811-140">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="ce811-140">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="ce811-141">Unicode 格式的文件夹的名称。</span><span class="sxs-lookup"><span data-stu-id="ce811-141">The name of the folder is in Unicode format.</span></span> <span data-ttu-id="ce811-142">如果未设置 MAPI_UNICODE 标志，文件夹的名称是 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="ce811-142">If the MAPI_UNICODE flag is not set, the name of the folder is in ANSI format.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="ce811-143">返回值</span><span class="sxs-lookup"><span data-stu-id="ce811-143">Return value</span></span>

<span data-ttu-id="ce811-144">S_OK</span><span class="sxs-lookup"><span data-stu-id="ce811-144">S_OK</span></span> 
  
> <span data-ttu-id="ce811-145">已成功复制或移动的文件夹。</span><span class="sxs-lookup"><span data-stu-id="ce811-145">The folder has been successfully copied or moved.</span></span>
    
<span data-ttu-id="ce811-146">MAPI_E_COLLISION</span><span class="sxs-lookup"><span data-stu-id="ce811-146">MAPI_E_COLLISION</span></span> 
  
> <span data-ttu-id="ce811-147">正在移动或复制的文件夹的名称为相同的目标文件夹中的子文件夹。</span><span class="sxs-lookup"><span data-stu-id="ce811-147">The name of the folder being moved or copied is the same as that of a subfolder in the destination folder.</span></span> <span data-ttu-id="ce811-148">消息存储提供程序需要唯一文件夹名称。</span><span class="sxs-lookup"><span data-stu-id="ce811-148">The message store provider requires that folder names be unique.</span></span> <span data-ttu-id="ce811-149">操作停止不完成。</span><span class="sxs-lookup"><span data-stu-id="ce811-149">The operation stops without completing.</span></span>
    
<span data-ttu-id="ce811-150">MAPI_W_PARTIAL_COMPLETION</span><span class="sxs-lookup"><span data-stu-id="ce811-150">MAPI_W_PARTIAL_COMPLETION</span></span> 
  
> <span data-ttu-id="ce811-151">调用成功，但并非所有的项目复制成功。</span><span class="sxs-lookup"><span data-stu-id="ce811-151">The call succeeded, but not all entries were successfully copied.</span></span> <span data-ttu-id="ce811-152">返回此警告时，应处理呼叫为成功。</span><span class="sxs-lookup"><span data-stu-id="ce811-152">When this warning is returned, the call should be handled as successful.</span></span> <span data-ttu-id="ce811-153">若要测试此警告，请使用**HR_FAILED**宏。</span><span class="sxs-lookup"><span data-stu-id="ce811-153">To test for this warning, use the **HR_FAILED** macro.</span></span> <span data-ttu-id="ce811-154">有关详细信息，请参阅[使用宏的错误处理](using-macros-for-error-handling.md)。</span><span class="sxs-lookup"><span data-stu-id="ce811-154">For more information, see [Using Macros for Error Handling](using-macros-for-error-handling.md).</span></span>
    
## <a name="remarks"></a><span data-ttu-id="ce811-155">注解</span><span class="sxs-lookup"><span data-stu-id="ce811-155">Remarks</span></span>

<span data-ttu-id="ce811-156">消息存储提供程序支持对象的实现**IMAPISupport::CopyFolder**方法。</span><span class="sxs-lookup"><span data-stu-id="ce811-156">The **IMAPISupport::CopyFolder** method is implemented for message store provider support objects.</span></span> <span data-ttu-id="ce811-157">消息存储提供程序可以调用**IMAPISupport::CopyFolder**其实现[IMAPIFolder::CopyFolder](imapifolder-copyfolder.md)复制或移动到另一个父文件夹中的单个文件夹中。</span><span class="sxs-lookup"><span data-stu-id="ce811-157">Message store providers can call **IMAPISupport::CopyFolder** in their implementation of [IMAPIFolder::CopyFolder](imapifolder-copyfolder.md) to copy or move a single folder from one parent folder to another.</span></span> 
  
 <span data-ttu-id="ce811-158">**IMAPISupport::CopyFolder**将复制或移动文件夹添加为目标文件夹的子文件夹。</span><span class="sxs-lookup"><span data-stu-id="ce811-158">**IMAPISupport::CopyFolder** adds the copied or moved folder as a subfolder of the destination folder.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="ce811-159">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="ce811-159">Notes to callers</span></span>

 <span data-ttu-id="ce811-160">**IMAPISupport::CopyFolder**允许同时重命名或移动的文件夹和复制或移动的受影响的文件夹的子文件夹。</span><span class="sxs-lookup"><span data-stu-id="ce811-160">**IMAPISupport::CopyFolder** allows simultaneous renaming and moving of folders and the copying or moving of subfolders of the affected folder.</span></span> <span data-ttu-id="ce811-161">若要复制或移动嵌套在复制或移动的文件夹中的所有子文件夹，请在_ulFlags_传递 COPY_SUBFOLDERS 标志。</span><span class="sxs-lookup"><span data-stu-id="ce811-161">To copy or move all subfolders nested in the copied or moved folder, pass the COPY_SUBFOLDERS flag in  _ulFlags_.</span></span> 
  
<span data-ttu-id="ce811-162">预期以下返回值在下列情况下：</span><span class="sxs-lookup"><span data-stu-id="ce811-162">Expect the following return values under the following conditions:</span></span>
  
|<span data-ttu-id="ce811-163">**条件**</span><span class="sxs-lookup"><span data-stu-id="ce811-163">**Condition**</span></span>|<span data-ttu-id="ce811-164">**返回值**</span><span class="sxs-lookup"><span data-stu-id="ce811-164">**Return value**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ce811-165">**CopyFolder**成功复制或移动的文件夹和所有子文件夹，如果适用。</span><span class="sxs-lookup"><span data-stu-id="ce811-165">**CopyFolder** successfully copied or moved the folder and all its subfolders, if applicable.</span></span>  <br/> |<span data-ttu-id="ce811-166">S_OK</span><span class="sxs-lookup"><span data-stu-id="ce811-166">S_OK</span></span>  <br/> |
|<span data-ttu-id="ce811-167">**CopyFolder**程序无法成功复制或移动的所有文件夹。</span><span class="sxs-lookup"><span data-stu-id="ce811-167">**CopyFolder** was unable to successfully copy or move all of the folders.</span></span>  <br/> |<span data-ttu-id="ce811-168">MAPI_W_PARTIAL_COMPLETION</span><span class="sxs-lookup"><span data-stu-id="ce811-168">MAPI_W_PARTIAL_COMPLETION</span></span>  <br/> |
|<span data-ttu-id="ce811-169">**CopyFolder**无法完成。</span><span class="sxs-lookup"><span data-stu-id="ce811-169">**CopyFolder** was unable to complete.</span></span>  <br/> |<span data-ttu-id="ce811-170">任何错误值</span><span class="sxs-lookup"><span data-stu-id="ce811-170">Any error value</span></span>  <br/> |
   
<span data-ttu-id="ce811-171">**CopyFolder**返回错误值，如果不继续执行假设不完成了任何工作中。</span><span class="sxs-lookup"><span data-stu-id="ce811-171">If **CopyFolder** returns an error value, do not proceed on the assumption that no work was done.</span></span> <span data-ttu-id="ce811-172">一个或多个文件夹可能已复制或移动之前**CopyFolder**遇到故障。</span><span class="sxs-lookup"><span data-stu-id="ce811-172">One or more folders could have been copied or moved before **CopyFolder** experienced the failure.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="ce811-173">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ce811-173">See also</span></span>



[<span data-ttu-id="ce811-174">IMAPISupport : IUnknown</span><span class="sxs-lookup"><span data-stu-id="ce811-174">IMAPISupport : IUnknown</span></span>](imapisupportiunknown.md)

