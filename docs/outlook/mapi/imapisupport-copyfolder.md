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
ms.openlocfilehash: 11ee944a14f8c9bd881b9c79a4ce66817275e73a
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33420883"
---
# <a name="imapisupportcopyfolder"></a><span data-ttu-id="52cc1-103">IMAPISupport::CopyFolder</span><span class="sxs-lookup"><span data-stu-id="52cc1-103">IMAPISupport::CopyFolder</span></span>

  
  
<span data-ttu-id="52cc1-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="52cc1-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="52cc1-105">将文件夹从其当前父文件夹复制或移动到另一个父文件夹。</span><span class="sxs-lookup"><span data-stu-id="52cc1-105">Copies or moves a folder from its current parent folder to another parent folder.</span></span>
  
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

## <a name="parameters"></a><span data-ttu-id="52cc1-106">参数</span><span class="sxs-lookup"><span data-stu-id="52cc1-106">Parameters</span></span>

 <span data-ttu-id="52cc1-107">_lpSrcInterface_</span><span class="sxs-lookup"><span data-stu-id="52cc1-107">_lpSrcInterface_</span></span>
  
> <span data-ttu-id="52cc1-108">实时指向接口标识符 (IID) 的指针, 该接口标识符表示用于访问要复制或移动的文件夹的父文件夹的接口。</span><span class="sxs-lookup"><span data-stu-id="52cc1-108">[in] A pointer to the interface identifier (IID) that represents the interface to be used to access the parent folder of the folder to be copied or moved.</span></span>
    
 <span data-ttu-id="52cc1-109">_lpSrcFolder_</span><span class="sxs-lookup"><span data-stu-id="52cc1-109">_lpSrcFolder_</span></span>
  
> <span data-ttu-id="52cc1-110">实时指向要复制或移动的文件夹的父文件夹的指针。</span><span class="sxs-lookup"><span data-stu-id="52cc1-110">[in] A pointer to the parent folder of the folder to be copied or moved.</span></span> 
    
 <span data-ttu-id="52cc1-111">_cbEntryID_</span><span class="sxs-lookup"><span data-stu-id="52cc1-111">_cbEntryID_</span></span>
  
> <span data-ttu-id="52cc1-112">实时条目标识符中由_lpEntryID_指向的字节数。</span><span class="sxs-lookup"><span data-stu-id="52cc1-112">[in] The byte count in the entry identifier pointed to by  _lpEntryID_.</span></span>
    
 <span data-ttu-id="52cc1-113">_lpEntryID_</span><span class="sxs-lookup"><span data-stu-id="52cc1-113">_lpEntryID_</span></span>
  
> <span data-ttu-id="52cc1-114">实时指向要复制或移动的文件夹的条目标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="52cc1-114">[in] A pointer to the entry identifier of the folder to be copied or moved.</span></span> 
    
 <span data-ttu-id="52cc1-115">_lpInterface_</span><span class="sxs-lookup"><span data-stu-id="52cc1-115">_lpInterface_</span></span>
  
> <span data-ttu-id="52cc1-116">实时保留必须为 NULL。</span><span class="sxs-lookup"><span data-stu-id="52cc1-116">[in] Reserved; must be NULL.</span></span>
    
 <span data-ttu-id="52cc1-117">_lpDestFolder_</span><span class="sxs-lookup"><span data-stu-id="52cc1-117">_lpDestFolder_</span></span>
  
> <span data-ttu-id="52cc1-118">实时指向接收要复制或移动的文件夹的文件夹的指针。</span><span class="sxs-lookup"><span data-stu-id="52cc1-118">[in] A pointer to the folder that is to receive the folder to be copied or moved.</span></span>
    
 <span data-ttu-id="52cc1-119">_lpszNewFolderName_</span><span class="sxs-lookup"><span data-stu-id="52cc1-119">_lpszNewFolderName_</span></span>
  
> <span data-ttu-id="52cc1-120">实时指向已复制或已移动文件夹的名称的指针;否则为 NULL, 表示复制或移动的文件夹应具有与源文件夹相同的名称 (由_lpEntryID_指向的文件夹)。</span><span class="sxs-lookup"><span data-stu-id="52cc1-120">[in] A pointer to the name of the copied or moved folder; otherwise, NULL, which indicates that the copied or moved folder should have the same name as the source folder (the folder pointed to by  _lpEntryID_).</span></span>
    
 <span data-ttu-id="52cc1-121">_ulUIParam_</span><span class="sxs-lookup"><span data-stu-id="52cc1-121">_ulUIParam_</span></span>
  
> <span data-ttu-id="52cc1-122">实时进度指示器对话框和相关窗口的窗口句柄。</span><span class="sxs-lookup"><span data-stu-id="52cc1-122">[in] A handle of the window for the progress indicator dialog box and related windows.</span></span> <span data-ttu-id="52cc1-123">除非在_ulFlags_参数中设置了 FOLDER_DIALOG 标志, 否则将忽略_ulUIParam_参数。</span><span class="sxs-lookup"><span data-stu-id="52cc1-123">The  _ulUIParam_ parameter is ignored unless the FOLDER_DIALOG flag is set in the  _ulFlags_ parameter.</span></span> 
    
 <span data-ttu-id="52cc1-124">_lpProgress_</span><span class="sxs-lookup"><span data-stu-id="52cc1-124">_lpProgress_</span></span>
  
> <span data-ttu-id="52cc1-125">实时指向显示进度指示器的进度对象的指针。</span><span class="sxs-lookup"><span data-stu-id="52cc1-125">[in] A pointer to a progress object that displays a progress indicator.</span></span> <span data-ttu-id="52cc1-126">如果在_lpProgress_中传递 NULL, 则邮件存储提供程序将使用 MAPI 进度对象实现来显示进度指示器。</span><span class="sxs-lookup"><span data-stu-id="52cc1-126">If NULL is passed in  _lpProgress_, the message store provider displays a progress indicator by using the MAPI progress object implementation.</span></span> <span data-ttu-id="52cc1-127">除非在_ulFlags_中设置了 FOLDER_DIALOG 标志, 否则_lpProgress_参数将被忽略。</span><span class="sxs-lookup"><span data-stu-id="52cc1-127">The  _lpProgress_ parameter is ignored unless the FOLDER_DIALOG flag is set in  _ulFlags_.</span></span>
    
 <span data-ttu-id="52cc1-128">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="52cc1-128">_ulFlags_</span></span>
  
> <span data-ttu-id="52cc1-129">实时用于控制如何完成复制或移动操作的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="52cc1-129">[in] A bitmask of flags that controls how the copy or move operation is accomplished.</span></span> <span data-ttu-id="52cc1-130">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="52cc1-130">The following flags can be set:</span></span>
    
<span data-ttu-id="52cc1-131">COPY_SUBFOLDERS</span><span class="sxs-lookup"><span data-stu-id="52cc1-131">COPY_SUBFOLDERS</span></span> 
  
> <span data-ttu-id="52cc1-132">应复制或移动文件夹的所有子文件夹。</span><span class="sxs-lookup"><span data-stu-id="52cc1-132">All of the folder's subfolders should be copied or moved.</span></span> <span data-ttu-id="52cc1-133">如果没有为复制操作设置 COPY_SUBFOLDERS, 则仅复制由_lpEntryID_标识的文件夹。</span><span class="sxs-lookup"><span data-stu-id="52cc1-133">When COPY_SUBFOLDERS is not set for a copy operation, only the folder identified by  _lpEntryID_ is copied.</span></span> <span data-ttu-id="52cc1-134">通过移动操作, 无论是否设置了标志, COPY_SUBFOLDERS 行为都是默认行为。</span><span class="sxs-lookup"><span data-stu-id="52cc1-134">With a move operation, the COPY_SUBFOLDERS behavior is the default regardless of whether the flag is set.</span></span> 
    
<span data-ttu-id="52cc1-135">FOLDER_DIALOG</span><span class="sxs-lookup"><span data-stu-id="52cc1-135">FOLDER_DIALOG</span></span> 
  
> <span data-ttu-id="52cc1-136">请求显示进度指示器。</span><span class="sxs-lookup"><span data-stu-id="52cc1-136">Requests the display of a progress indicator.</span></span>
    
<span data-ttu-id="52cc1-137">FOLDER_MOVE</span><span class="sxs-lookup"><span data-stu-id="52cc1-137">FOLDER_MOVE</span></span> 
  
> <span data-ttu-id="52cc1-138">应移动而不是复制文件夹。</span><span class="sxs-lookup"><span data-stu-id="52cc1-138">The folder should be moved instead of copied.</span></span> <span data-ttu-id="52cc1-139">如果未设置 FOLDER_MOVE, 则复制文件夹。</span><span class="sxs-lookup"><span data-stu-id="52cc1-139">If FOLDER_MOVE is not set, the folder is copied.</span></span>
    
<span data-ttu-id="52cc1-140">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="52cc1-140">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="52cc1-141">该文件夹的名称采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="52cc1-141">The name of the folder is in Unicode format.</span></span> <span data-ttu-id="52cc1-142">如果未设置 MAPI_UNICODE 标志, 则该文件夹的名称为 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="52cc1-142">If the MAPI_UNICODE flag is not set, the name of the folder is in ANSI format.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="52cc1-143">返回值</span><span class="sxs-lookup"><span data-stu-id="52cc1-143">Return value</span></span>

<span data-ttu-id="52cc1-144">S_OK</span><span class="sxs-lookup"><span data-stu-id="52cc1-144">S_OK</span></span> 
  
> <span data-ttu-id="52cc1-145">已成功复制或移动文件夹。</span><span class="sxs-lookup"><span data-stu-id="52cc1-145">The folder has been successfully copied or moved.</span></span>
    
<span data-ttu-id="52cc1-146">MAPI_E_COLLISION</span><span class="sxs-lookup"><span data-stu-id="52cc1-146">MAPI_E_COLLISION</span></span> 
  
> <span data-ttu-id="52cc1-147">要移动或复制的文件夹的名称与目标文件夹中的子文件夹的名称相同。</span><span class="sxs-lookup"><span data-stu-id="52cc1-147">The name of the folder being moved or copied is the same as that of a subfolder in the destination folder.</span></span> <span data-ttu-id="52cc1-148">邮件存储区提供程序要求文件夹名称是唯一的。</span><span class="sxs-lookup"><span data-stu-id="52cc1-148">The message store provider requires that folder names be unique.</span></span> <span data-ttu-id="52cc1-149">操作在未完成的情况下停止。</span><span class="sxs-lookup"><span data-stu-id="52cc1-149">The operation stops without completing.</span></span>
    
<span data-ttu-id="52cc1-150">MAPI_W_PARTIAL_COMPLETION</span><span class="sxs-lookup"><span data-stu-id="52cc1-150">MAPI_W_PARTIAL_COMPLETION</span></span> 
  
> <span data-ttu-id="52cc1-151">呼叫成功, 但未成功复制所有条目。</span><span class="sxs-lookup"><span data-stu-id="52cc1-151">The call succeeded, but not all entries were successfully copied.</span></span> <span data-ttu-id="52cc1-152">返回此警告时, 应以成功的方式处理该调用。</span><span class="sxs-lookup"><span data-stu-id="52cc1-152">When this warning is returned, the call should be handled as successful.</span></span> <span data-ttu-id="52cc1-153">若要测试此警告, 请使用**HR_FAILED**宏。</span><span class="sxs-lookup"><span data-stu-id="52cc1-153">To test for this warning, use the **HR_FAILED** macro.</span></span> <span data-ttu-id="52cc1-154">有关详细信息, 请参阅[使用宏进行错误处理](using-macros-for-error-handling.md)。</span><span class="sxs-lookup"><span data-stu-id="52cc1-154">For more information, see [Using Macros for Error Handling](using-macros-for-error-handling.md).</span></span>
    
## <a name="remarks"></a><span data-ttu-id="52cc1-155">说明</span><span class="sxs-lookup"><span data-stu-id="52cc1-155">Remarks</span></span>

<span data-ttu-id="52cc1-156">为邮件存储提供程序支持对象实现了**IMAPISupport:: CopyFolder**方法。</span><span class="sxs-lookup"><span data-stu-id="52cc1-156">The **IMAPISupport::CopyFolder** method is implemented for message store provider support objects.</span></span> <span data-ttu-id="52cc1-157">邮件存储提供程序可以在其[IMAPIFolder:: CopyFolder](imapifolder-copyfolder.md)的实现中调用**IMAPISupport::** , 将单个文件夹从一个父文件夹复制或移动到另一个文件夹。</span><span class="sxs-lookup"><span data-stu-id="52cc1-157">Message store providers can call **IMAPISupport::CopyFolder** in their implementation of [IMAPIFolder::CopyFolder](imapifolder-copyfolder.md) to copy or move a single folder from one parent folder to another.</span></span> 
  
 <span data-ttu-id="52cc1-158">**IMAPISupport:: CopyFolder**将已复制或移动的文件夹添加为目标文件夹的子文件夹。</span><span class="sxs-lookup"><span data-stu-id="52cc1-158">**IMAPISupport::CopyFolder** adds the copied or moved folder as a subfolder of the destination folder.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="52cc1-159">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="52cc1-159">Notes to callers</span></span>

 <span data-ttu-id="52cc1-160">**IMAPISupport:: CopyFolder**允许同时重命名和移动文件夹以及受影响文件夹的子文件夹的复制或移动。</span><span class="sxs-lookup"><span data-stu-id="52cc1-160">**IMAPISupport::CopyFolder** allows simultaneous renaming and moving of folders and the copying or moving of subfolders of the affected folder.</span></span> <span data-ttu-id="52cc1-161">若要复制或移动嵌套在复制或移动的文件夹中的所有子文件夹, 请在_ulFlags_中传递 COPY_SUBFOLDERS 标志。</span><span class="sxs-lookup"><span data-stu-id="52cc1-161">To copy or move all subfolders nested in the copied or moved folder, pass the COPY_SUBFOLDERS flag in  _ulFlags_.</span></span> 
  
<span data-ttu-id="52cc1-162">在下列情况下, 预期以下返回值:</span><span class="sxs-lookup"><span data-stu-id="52cc1-162">Expect the following return values under the following conditions:</span></span>
  
|<span data-ttu-id="52cc1-163">**条件**</span><span class="sxs-lookup"><span data-stu-id="52cc1-163">**Condition**</span></span>|<span data-ttu-id="52cc1-164">**返回值**</span><span class="sxs-lookup"><span data-stu-id="52cc1-164">**Return value**</span></span>|
|:-----|:-----|
|<span data-ttu-id="52cc1-165">**CopyFolder**成功复制或移动文件夹及其所有子文件夹 (如果适用)。</span><span class="sxs-lookup"><span data-stu-id="52cc1-165">**CopyFolder** successfully copied or moved the folder and all its subfolders, if applicable.</span></span>  <br/> |<span data-ttu-id="52cc1-166">S_OK</span><span class="sxs-lookup"><span data-stu-id="52cc1-166">S_OK</span></span>  <br/> |
|<span data-ttu-id="52cc1-167">**CopyFolder**无法成功复制或移动所有文件夹。</span><span class="sxs-lookup"><span data-stu-id="52cc1-167">**CopyFolder** was unable to successfully copy or move all of the folders.</span></span>  <br/> |<span data-ttu-id="52cc1-168">MAPI_W_PARTIAL_COMPLETION</span><span class="sxs-lookup"><span data-stu-id="52cc1-168">MAPI_W_PARTIAL_COMPLETION</span></span>  <br/> |
|<span data-ttu-id="52cc1-169">**CopyFolder**无法完成。</span><span class="sxs-lookup"><span data-stu-id="52cc1-169">**CopyFolder** was unable to complete.</span></span>  <br/> |<span data-ttu-id="52cc1-170">任何错误值</span><span class="sxs-lookup"><span data-stu-id="52cc1-170">Any error value</span></span>  <br/> |
   
<span data-ttu-id="52cc1-171">如果**CopyFolder**返回一个错误值, 请勿在假设尚未完成任何工作的情况下继续进行。</span><span class="sxs-lookup"><span data-stu-id="52cc1-171">If **CopyFolder** returns an error value, do not proceed on the assumption that no work was done.</span></span> <span data-ttu-id="52cc1-172">在**CopyFolder**遇到故障之前, 一个或多个文件夹可能已被复制或移动。</span><span class="sxs-lookup"><span data-stu-id="52cc1-172">One or more folders could have been copied or moved before **CopyFolder** experienced the failure.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="52cc1-173">另请参阅</span><span class="sxs-lookup"><span data-stu-id="52cc1-173">See also</span></span>



[<span data-ttu-id="52cc1-174">IMAPISupport : IUnknown</span><span class="sxs-lookup"><span data-stu-id="52cc1-174">IMAPISupport : IUnknown</span></span>](imapisupportiunknown.md)

