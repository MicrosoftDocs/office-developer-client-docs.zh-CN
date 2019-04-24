---
title: IMAPIFolderCopyFolder
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIFolder.CopyFolder
api_type:
- COM
ms.assetid: 2c1c25c6-1aec-4d9e-a2a3-bf1b4a2908b8
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 3d9c1e88b12baf50593212a3ae3c02907ce6617b
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32280176"
---
# <a name="imapifoldercopyfolder"></a><span data-ttu-id="a6d9c-103">IMAPIFolder::CopyFolder</span><span class="sxs-lookup"><span data-stu-id="a6d9c-103">IMAPIFolder::CopyFolder</span></span>

  
  
<span data-ttu-id="a6d9c-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="a6d9c-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="a6d9c-105">复制或移动子文件夹。</span><span class="sxs-lookup"><span data-stu-id="a6d9c-105">Copies or moves a subfolder.</span></span>
  
```cpp
HRESULT CopyFolder(
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

## <a name="parameters"></a><span data-ttu-id="a6d9c-106">参数</span><span class="sxs-lookup"><span data-stu-id="a6d9c-106">Parameters</span></span>

 <span data-ttu-id="a6d9c-107">_cbEntryID_</span><span class="sxs-lookup"><span data-stu-id="a6d9c-107">_cbEntryID_</span></span>
  
> <span data-ttu-id="a6d9c-108">实时条目标识符中由_lpEntryID_参数指向的字节数。</span><span class="sxs-lookup"><span data-stu-id="a6d9c-108">[in] The byte count in the entry identifier pointed to by the  _lpEntryID_ parameter.</span></span> 
    
 <span data-ttu-id="a6d9c-109">_lpEntryID_</span><span class="sxs-lookup"><span data-stu-id="a6d9c-109">_lpEntryID_</span></span>
  
> <span data-ttu-id="a6d9c-110">实时指向要复制或移动的子文件夹的条目标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="a6d9c-110">[in] A pointer to the entry identifier of the subfolder to copy or move.</span></span>
    
 <span data-ttu-id="a6d9c-111">_lpInterface_</span><span class="sxs-lookup"><span data-stu-id="a6d9c-111">_lpInterface_</span></span>
  
> <span data-ttu-id="a6d9c-112">实时指向接口标识符 (IID) 的指针, 该接口标识符表示要用于访问_lpDestFolder_参数所指向的文件夹的接口。</span><span class="sxs-lookup"><span data-stu-id="a6d9c-112">[in] A pointer to the interface identifier (IID) that represents the interface to be used to access the folder that the  _lpDestFolder_ parameter points to.</span></span> <span data-ttu-id="a6d9c-113">传递 NULL 将导致服务提供程序返回标准文件夹接口[IMAPIFolder: IMAPIContainer](imapifolderimapicontainer.md)。</span><span class="sxs-lookup"><span data-stu-id="a6d9c-113">Passing NULL causes the service provider to return the standard folder interface, [IMAPIFolder : IMAPIContainer](imapifolderimapicontainer.md).</span></span> <span data-ttu-id="a6d9c-114">_lpInterface_的有效值包括 IID_IUnknown、IID_IMAPIProp、IID_IMAPIContainer 和 IID_IMAPIFolder。</span><span class="sxs-lookup"><span data-stu-id="a6d9c-114">Valid values for  _lpInterface_ include IID_IUnknown, IID_IMAPIProp, IID_IMAPIContainer, and IID_IMAPIFolder.</span></span> 
    
 <span data-ttu-id="a6d9c-115">_lpDestFolder_</span><span class="sxs-lookup"><span data-stu-id="a6d9c-115">_lpDestFolder_</span></span>
  
> <span data-ttu-id="a6d9c-116">实时指向用于接收复制或移动的子文件夹的打开文件夹的指针。</span><span class="sxs-lookup"><span data-stu-id="a6d9c-116">[in] A pointer to the open folder to receive the copied or moved subfolder.</span></span>
    
 <span data-ttu-id="a6d9c-117">_lpszNewFolderName_</span><span class="sxs-lookup"><span data-stu-id="a6d9c-117">_lpszNewFolderName_</span></span>
  
> <span data-ttu-id="a6d9c-118">实时一个指针, 指向其新目标中复制或移动的文件夹的名称。</span><span class="sxs-lookup"><span data-stu-id="a6d9c-118">[in] A pointer to the name of the copied or moved folder in its new destination.</span></span> <span data-ttu-id="a6d9c-119">如果将_lpszNewFolderName_设置为 NULL, 则源子文件夹的名称将用于目标文件夹的名称。</span><span class="sxs-lookup"><span data-stu-id="a6d9c-119">If  _lpszNewFolderName_ is set to NULL, the name of the source subfolder is used for the name of the destination folder.</span></span> 
    
 <span data-ttu-id="a6d9c-120">_ulUIParam_</span><span class="sxs-lookup"><span data-stu-id="a6d9c-120">_ulUIParam_</span></span>
  
> <span data-ttu-id="a6d9c-121">实时进度指示器的父窗口的句柄。</span><span class="sxs-lookup"><span data-stu-id="a6d9c-121">[in] A handle to the parent window of the progress indicator.</span></span> <span data-ttu-id="a6d9c-122">除非设置_ulFlags_参数中的 FOLDER_DIALOG 标记, 否则将忽略_ulUIParam_参数。</span><span class="sxs-lookup"><span data-stu-id="a6d9c-122">The  _ulUIParam_ parameter is ignored unless the FOLDER_DIALOG flag in the  _ulFlags_ parameter is set.</span></span> 
    
 <span data-ttu-id="a6d9c-123">_lpProgress_</span><span class="sxs-lookup"><span data-stu-id="a6d9c-123">_lpProgress_</span></span>
  
> <span data-ttu-id="a6d9c-124">实时指向显示进度指示器的进度对象的指针。</span><span class="sxs-lookup"><span data-stu-id="a6d9c-124">[in] A pointer to a progress object that displays a progress indicator.</span></span> <span data-ttu-id="a6d9c-125">如果在_lpProgress_中传递 NULL, 则邮件存储提供程序将使用 MAPI 进度对象实现来显示进度指示器。</span><span class="sxs-lookup"><span data-stu-id="a6d9c-125">If NULL is passed in  _lpProgress_, the message store provider displays a progress indicator by using the MAPI progress object implementation.</span></span> <span data-ttu-id="a6d9c-126">除非在_ulFlags_中设置了 FOLDER_DIALOG 标志, 否则_lpProgress_参数将被忽略。</span><span class="sxs-lookup"><span data-stu-id="a6d9c-126">The  _lpProgress_ parameter is ignored unless the FOLDER_DIALOG flag is set in  _ulFlags_.</span></span>
    
 <span data-ttu-id="a6d9c-127">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="a6d9c-127">_ulFlags_</span></span>
  
> <span data-ttu-id="a6d9c-128">实时用于控制复制或移动操作的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="a6d9c-128">[in] A bitmask of flags that controls the copy or move operation.</span></span> <span data-ttu-id="a6d9c-129">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="a6d9c-129">The following flags can be set:</span></span>
    
<span data-ttu-id="a6d9c-130">COPY_SUBFOLDERS</span><span class="sxs-lookup"><span data-stu-id="a6d9c-130">COPY_SUBFOLDERS</span></span> 
  
> <span data-ttu-id="a6d9c-131">还应复制子文件夹中要复制的所有子文件夹。</span><span class="sxs-lookup"><span data-stu-id="a6d9c-131">All of the subfolders in the subfolder to be copied should also be copied.</span></span> <span data-ttu-id="a6d9c-132">如果 COPY_SUBFOLDERS 不是为复制操作设置的, 则仅复制由_lpEntryID_标识的子文件夹。</span><span class="sxs-lookup"><span data-stu-id="a6d9c-132">When COPY_SUBFOLDERS is not set for a copy operation, only the subfolder identified by  _lpEntryID_ is copied.</span></span> <span data-ttu-id="a6d9c-133">通过移动操作, 无论是否设置了标志, COPY_SUBFOLDERS 行为都是默认行为。</span><span class="sxs-lookup"><span data-stu-id="a6d9c-133">With a move operation, the COPY_SUBFOLDERS behavior is the default regardless of whether the flag is set.</span></span> 
    
<span data-ttu-id="a6d9c-134">FOLDER_DIALOG</span><span class="sxs-lookup"><span data-stu-id="a6d9c-134">FOLDER_DIALOG</span></span> 
  
> <span data-ttu-id="a6d9c-135">请求显示进度指示器。</span><span class="sxs-lookup"><span data-stu-id="a6d9c-135">Requests the display of a progress indicator.</span></span>
    
<span data-ttu-id="a6d9c-136">FOLDER_MOVE</span><span class="sxs-lookup"><span data-stu-id="a6d9c-136">FOLDER_MOVE</span></span> 
  
> <span data-ttu-id="a6d9c-137">移动子文件夹, 而不是复制。</span><span class="sxs-lookup"><span data-stu-id="a6d9c-137">The subfolder is to be moved instead of copied.</span></span> <span data-ttu-id="a6d9c-138">如果未设置 FOLDER_MOVE, 则复制子文件夹。</span><span class="sxs-lookup"><span data-stu-id="a6d9c-138">If FOLDER_MOVE is not set, the subfolder is copied.</span></span>
    
<span data-ttu-id="a6d9c-139">MAPI_DECLINE_OK</span><span class="sxs-lookup"><span data-stu-id="a6d9c-139">MAPI_DECLINE_OK</span></span> 
  
> <span data-ttu-id="a6d9c-140">通过调用其支持对象的 IMAPISupport 来实现**CopyFolder** , 通知邮件存储提供程序[::D ocopyto](imapisupport-docopyto.md)或[IMAPISupport::D ocopyprops](imapisupport-docopyprops.md)方法, **CopyFolder**应立即返回 MAPI_E_DECLINE_COPY。</span><span class="sxs-lookup"><span data-stu-id="a6d9c-140">Informs the message store provider that if it implements **CopyFolder** by calling its support object's [IMAPISupport::DoCopyTo](imapisupport-docopyto.md) or [IMAPISupport::DoCopyProps](imapisupport-docopyprops.md) method, **CopyFolder** should instead immediately return MAPI_E_DECLINE_COPY.</span></span> 
    
<span data-ttu-id="a6d9c-141">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="a6d9c-141">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="a6d9c-142">目标文件夹的名称采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="a6d9c-142">The name of the destination folder is in Unicode format.</span></span> <span data-ttu-id="a6d9c-143">如果未设置 MAPI_UNICODE 标志, 则该文件夹名称为 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="a6d9c-143">If the MAPI_UNICODE flag is not set, the folder name is in ANSI format.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="a6d9c-144">返回值</span><span class="sxs-lookup"><span data-stu-id="a6d9c-144">Return value</span></span>

<span data-ttu-id="a6d9c-145">S_OK</span><span class="sxs-lookup"><span data-stu-id="a6d9c-145">S_OK</span></span> 
  
> <span data-ttu-id="a6d9c-146">已成功复制或移动指定的文件夹。</span><span class="sxs-lookup"><span data-stu-id="a6d9c-146">The specified folder has been successfully copied or moved.</span></span>
    
<span data-ttu-id="a6d9c-147">MAPI_E_BAD_CHARWIDTH</span><span class="sxs-lookup"><span data-stu-id="a6d9c-147">MAPI_E_BAD_CHARWIDTH</span></span> 
  
> <span data-ttu-id="a6d9c-148">设置了 MAPI_UNICODE 标志, 且邮件存储区提供程序不支持 unicode, 或者未设置 MAPI_UNICODE, 且邮件存储区提供程序仅支持 UNICODE。</span><span class="sxs-lookup"><span data-stu-id="a6d9c-148">Either the MAPI_UNICODE flag was set and the message store provider does not support Unicode, or MAPI_UNICODE was not set and the message store provider supports only Unicode.</span></span>
    
<span data-ttu-id="a6d9c-149">MAPI_E_COLLISION</span><span class="sxs-lookup"><span data-stu-id="a6d9c-149">MAPI_E_COLLISION</span></span> 
  
> <span data-ttu-id="a6d9c-150">要移动或复制的文件夹的名称与目标文件夹中的子文件夹的名称相同。</span><span class="sxs-lookup"><span data-stu-id="a6d9c-150">The name of the folder being moved or copied is the same as that of a subfolder in the destination folder.</span></span> <span data-ttu-id="a6d9c-151">邮件存储区提供程序需要唯一的文件夹名称。</span><span class="sxs-lookup"><span data-stu-id="a6d9c-151">The message store provider requires unique folder names.</span></span>
    
<span data-ttu-id="a6d9c-152">MAPI_E_DECLINE_COPY</span><span class="sxs-lookup"><span data-stu-id="a6d9c-152">MAPI_E_DECLINE_COPY</span></span> 
  
> <span data-ttu-id="a6d9c-153">提供程序通过调用支持对象方法来实现此方法, 并且调用方已传递 MAPI_DECLINE_OK 标志。</span><span class="sxs-lookup"><span data-stu-id="a6d9c-153">The provider implements this method by calling a support object method, and the caller has passed the MAPI_DECLINE_OK flag.</span></span>
    
<span data-ttu-id="a6d9c-154">MAPI_E_FOLDER_CYCLE</span><span class="sxs-lookup"><span data-stu-id="a6d9c-154">MAPI_E_FOLDER_CYCLE</span></span> 
  
> <span data-ttu-id="a6d9c-155">源文件夹直接或间接包含目标文件夹。</span><span class="sxs-lookup"><span data-stu-id="a6d9c-155">The source folder directly or indirectly contains the destination folder.</span></span> <span data-ttu-id="a6d9c-156">在发现此条件之前, 可能已经执行了大量的工作, 因此源文件夹和目标文件夹可能被部分修改。</span><span class="sxs-lookup"><span data-stu-id="a6d9c-156">Significant work may have been performed before this condition was discovered, so the source and destination folder may be partially modified.</span></span> 
    
<span data-ttu-id="a6d9c-157">MAPI_W_PARTIAL_COMPLETION</span><span class="sxs-lookup"><span data-stu-id="a6d9c-157">MAPI_W_PARTIAL_COMPLETION</span></span> 
  
> <span data-ttu-id="a6d9c-158">呼叫成功, 但未成功复制所有条目。</span><span class="sxs-lookup"><span data-stu-id="a6d9c-158">The call succeeded, but not all entries were successfully copied.</span></span> <span data-ttu-id="a6d9c-159">返回此警告时, 应以成功的方式处理该调用。</span><span class="sxs-lookup"><span data-stu-id="a6d9c-159">When this warning is returned, the call should be handled as successful.</span></span> <span data-ttu-id="a6d9c-160">若要测试此警告, 请使用**HR_FAILED**宏。</span><span class="sxs-lookup"><span data-stu-id="a6d9c-160">To test for this warning, use the **HR_FAILED** macro.</span></span> <span data-ttu-id="a6d9c-161">有关详细信息, 请参阅[使用宏进行错误处理](using-macros-for-error-handling.md)。</span><span class="sxs-lookup"><span data-stu-id="a6d9c-161">For more information, see [Using Macros for Error Handling](using-macros-for-error-handling.md).</span></span>
    
## <a name="remarks"></a><span data-ttu-id="a6d9c-162">注解</span><span class="sxs-lookup"><span data-stu-id="a6d9c-162">Remarks</span></span>

<span data-ttu-id="a6d9c-163">**IMAPIFolder:: CopyFolder**方法将子文件夹从一个位置复制或移动到另一个位置。</span><span class="sxs-lookup"><span data-stu-id="a6d9c-163">The **IMAPIFolder::CopyFolder** method copies or moves a subfolder from one location to another.</span></span> <span data-ttu-id="a6d9c-164">要复制或移动的子文件夹作为子文件夹添加到目标文件夹中。</span><span class="sxs-lookup"><span data-stu-id="a6d9c-164">The subfolder being copied or moved is added to the destination folder as a subfolder.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="a6d9c-165">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="a6d9c-165">Notes to implementers</span></span>

<span data-ttu-id="a6d9c-166">当复制或移动操作涉及多个文件夹 (如设置 COPY_SUBFOLDERS 标志) 时, 请尽可能为每个文件夹完全执行该操作。</span><span class="sxs-lookup"><span data-stu-id="a6d9c-166">When the copy or move operation involves more than one folder, as indicated by setting the COPY_SUBFOLDERS flag, perform the operation as completely as possible for each folder.</span></span> <span data-ttu-id="a6d9c-167">有时, 要移动或复制的一个文件夹不存在, 或者已将其移动或复制到其他位置。</span><span class="sxs-lookup"><span data-stu-id="a6d9c-167">Sometimes one of the folders to be moved or copied does not exist or has already been moved or copied elsewhere.</span></span> <span data-ttu-id="a6d9c-168">请勿提前停止操作, 除非发生超出控制范围的故障 (如内存不足、磁盘空间不足或邮件存储区损坏)。</span><span class="sxs-lookup"><span data-stu-id="a6d9c-168">Do not stop the operation prematurely unless a failure occurs that is beyond your control, such as running out of memory, running out of disk space, or corruption in the message store.</span></span>
  
<span data-ttu-id="a6d9c-169">尝试将所有邮件条目标识符保留在复制的邮件中。</span><span class="sxs-lookup"><span data-stu-id="a6d9c-169">Try to retain all message entry identifiers in the copied messages.</span></span> <span data-ttu-id="a6d9c-170">您还应尝试保留条目标识符, 但这并不是必需的。</span><span class="sxs-lookup"><span data-stu-id="a6d9c-170">You should also try to preserve entry identifiers, but it is not required.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="a6d9c-171">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="a6d9c-171">Notes to callers</span></span>

<span data-ttu-id="a6d9c-172">在下列情况下, 需要这些返回值。</span><span class="sxs-lookup"><span data-stu-id="a6d9c-172">Expect these return values under the following conditions.</span></span>
  
|<span data-ttu-id="a6d9c-173">**Condition**</span><span class="sxs-lookup"><span data-stu-id="a6d9c-173">**Condition**</span></span>|<span data-ttu-id="a6d9c-174">**返回值**</span><span class="sxs-lookup"><span data-stu-id="a6d9c-174">**Return value**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a6d9c-175">**CopyFolder**已成功复制或移动每个邮件和子文件夹。</span><span class="sxs-lookup"><span data-stu-id="a6d9c-175">**CopyFolder** has successfully copied or moved every message and subfolder.</span></span>  <br/> |<span data-ttu-id="a6d9c-176">S_OK</span><span class="sxs-lookup"><span data-stu-id="a6d9c-176">S_OK</span></span>  <br/> |
|<span data-ttu-id="a6d9c-177">**CopyFolder**无法成功复制或移动每个邮件和子文件夹。</span><span class="sxs-lookup"><span data-stu-id="a6d9c-177">**CopyFolder** was unable to successfully copy or move every message and subfolder.</span></span>  <br/> |<span data-ttu-id="a6d9c-178">MAPI_W_PARTIAL_COMPLETION 或 MAPI_E_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="a6d9c-178">MAPI_W_PARTIAL_COMPLETION or MAPI_E_NOT_FOUND</span></span>  <br/> |
|<span data-ttu-id="a6d9c-179">**CopyFolder**无法完成。</span><span class="sxs-lookup"><span data-stu-id="a6d9c-179">**CopyFolder** was unable to complete.</span></span>  <br/> |<span data-ttu-id="a6d9c-180">除 MAPI_E_NOT_FOUND 外的任何错误值</span><span class="sxs-lookup"><span data-stu-id="a6d9c-180">Any error value except MAPI_E_NOT_FOUND</span></span>  <br/> |
   
<span data-ttu-id="a6d9c-181">当**CopyFolder**无法完成时, 请不要假定没有任何工作已完成。</span><span class="sxs-lookup"><span data-stu-id="a6d9c-181">When **CopyFolder** is unable to complete, do not assume that no work was done.</span></span> <span data-ttu-id="a6d9c-182">在遇到此错误之前, **CopyFolder**可能已能够复制或移动一个或多个邮件和子文件夹。</span><span class="sxs-lookup"><span data-stu-id="a6d9c-182">**CopyFolder** might have been able to copy or move one or more of the messages and subfolders before encountering the error.</span></span> 
  
<span data-ttu-id="a6d9c-183">如果在_lpEntryID_中传递了不存在的文件夹的条目标识符, 则**CopyFolder**将返回 MAPI_W_PARTIAL_COMPLETION 或 MAPI_E_NOT_FOUND, 具体取决于邮件存储的实现。</span><span class="sxs-lookup"><span data-stu-id="a6d9c-183">If an entry identifier for a folder that does not exist is passed in  _lpEntryID_, **CopyFolder** returns MAPI_W_PARTIAL_COMPLETION or MAPI_E_NOT_FOUND, depending on the message store's implementation.</span></span> 
  
<span data-ttu-id="a6d9c-184">根据邮件存储提供程序, 原始邮件的条目标识符可能会保留在复制的邮件中, 也可能不会保留。</span><span class="sxs-lookup"><span data-stu-id="a6d9c-184">Depending on the message store provider, the entry identifier of the original message may or may not be preserved in the copied message.</span></span> <span data-ttu-id="a6d9c-185">应尽可能保留条目标识符, 但这并不是必需的。</span><span class="sxs-lookup"><span data-stu-id="a6d9c-185">You should preserve entry identifiers whenever possible, but it is not a requirement.</span></span> <span data-ttu-id="a6d9c-186">您通常可以依赖于以下方案:</span><span class="sxs-lookup"><span data-stu-id="a6d9c-186">You can generally depend on the following scenarios:</span></span>
  
- <span data-ttu-id="a6d9c-187">在两种不同类型的邮件存储之间移动文件夹时, 可保证条目标识符的变化。</span><span class="sxs-lookup"><span data-stu-id="a6d9c-187">When you move a folder between two different types of message stores, the entry identifier is guaranteed to change.</span></span>
    
- <span data-ttu-id="a6d9c-188">当您在两个相同类型的邮件存储库之间移动文件夹时, 条目标识符几乎总是发生变化。</span><span class="sxs-lookup"><span data-stu-id="a6d9c-188">When you move a folder between two message stores of the same type, the entry identifier almost always changes.</span></span>
    
- <span data-ttu-id="a6d9c-189">将文件夹移动到同一邮件存储区中的其他位置时, 条目标识符可能会更改, 也可能不会更改, 具体取决于邮件存储提供程序。</span><span class="sxs-lookup"><span data-stu-id="a6d9c-189">When you move a folder to another location in the same message store, the entry identifier may or may not change, depending on the message store provider.</span></span>
    
## <a name="mfcmapi-reference"></a><span data-ttu-id="a6d9c-190">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="a6d9c-190">MFCMAPI reference</span></span>

<span data-ttu-id="a6d9c-191">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="a6d9c-191">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="a6d9c-192">**文件**</span><span class="sxs-lookup"><span data-stu-id="a6d9c-192">**File**</span></span>|<span data-ttu-id="a6d9c-193">**函数**</span><span class="sxs-lookup"><span data-stu-id="a6d9c-193">**Function**</span></span>|<span data-ttu-id="a6d9c-194">**备注**</span><span class="sxs-lookup"><span data-stu-id="a6d9c-194">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a6d9c-195">MsgStoreDlg</span><span class="sxs-lookup"><span data-stu-id="a6d9c-195">MsgStoreDlg.cpp</span></span>  <br/> |<span data-ttu-id="a6d9c-196">CMsgStoreDlg:: OnPasteFolder</span><span class="sxs-lookup"><span data-stu-id="a6d9c-196">CMsgStoreDlg::OnPasteFolder</span></span>  <br/> |<span data-ttu-id="a6d9c-197">MFCMAPI 使用**IMAPIFolder:: CopyFolder**方法将文件夹从一个位置复制到另一个位置。</span><span class="sxs-lookup"><span data-stu-id="a6d9c-197">MFCMAPI uses the **IMAPIFolder::CopyFolder** method to copy folders from one location to another.</span></span> <span data-ttu-id="a6d9c-198">MFCMAPI 在复制操作过程中记住源文件夹, 并在粘贴操作过程中实际执行复制操作。</span><span class="sxs-lookup"><span data-stu-id="a6d9c-198">MFCMAPI remembers the source folder during the copy operation and actually performs the copy during the paste operation.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="a6d9c-199">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a6d9c-199">See also</span></span>



[<span data-ttu-id="a6d9c-200">IMAPIFolder : IMAPIContainer</span><span class="sxs-lookup"><span data-stu-id="a6d9c-200">IMAPIFolder : IMAPIContainer</span></span>](imapifolderimapicontainer.md)


[<span data-ttu-id="a6d9c-201">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="a6d9c-201">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

