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
ms.openlocfilehash: 5961e7a2118a46bdc9c0e66138363976ae2f7154
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775346"
---
# <a name="imapifoldercopyfolder"></a><span data-ttu-id="20250-103">IMAPIFolder::CopyFolder</span><span class="sxs-lookup"><span data-stu-id="20250-103">IMAPIFolder::CopyFolder</span></span>

  
  
<span data-ttu-id="20250-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="20250-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="20250-105">复制或移动的子文件夹。</span><span class="sxs-lookup"><span data-stu-id="20250-105">Copies or moves a subfolder.</span></span>
  
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

## <a name="parameters"></a><span data-ttu-id="20250-106">参数</span><span class="sxs-lookup"><span data-stu-id="20250-106">Parameters</span></span>

 <span data-ttu-id="20250-107">_cbEntryID_</span><span class="sxs-lookup"><span data-stu-id="20250-107">_cbEntryID_</span></span>
  
> <span data-ttu-id="20250-108">[in]在_lpEntryID_参数指向的项标识符的字节数。</span><span class="sxs-lookup"><span data-stu-id="20250-108">[in] The byte count in the entry identifier pointed to by the  _lpEntryID_ parameter.</span></span> 
    
 <span data-ttu-id="20250-109">_lpEntryID_</span><span class="sxs-lookup"><span data-stu-id="20250-109">_lpEntryID_</span></span>
  
> <span data-ttu-id="20250-110">[in]指向要复制或移动的子文件夹的项标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="20250-110">[in] A pointer to the entry identifier of the subfolder to copy or move.</span></span>
    
 <span data-ttu-id="20250-111">_lpInterface_</span><span class="sxs-lookup"><span data-stu-id="20250-111">_lpInterface_</span></span>
  
> <span data-ttu-id="20250-112">[in]指向接口标识 (IID) 值，该值代表要用于访问_lpDestFolder_参数指向的文件夹的接口的指针。</span><span class="sxs-lookup"><span data-stu-id="20250-112">[in] A pointer to the interface identifier (IID) that represents the interface to be used to access the folder that the  _lpDestFolder_ parameter points to.</span></span> <span data-ttu-id="20250-113">传递 NULL 将导致服务提供程序返回的标准文件夹接口， [IMAPIFolder: IMAPIContainer](imapifolderimapicontainer.md)。</span><span class="sxs-lookup"><span data-stu-id="20250-113">Passing NULL causes the service provider to return the standard folder interface, [IMAPIFolder : IMAPIContainer](imapifolderimapicontainer.md).</span></span> <span data-ttu-id="20250-114">_LpInterface_的有效值包括 IID_IUnknown、 IID_IMAPIProp、 IID_IMAPIContainer 和 IID_IMAPIFolder。</span><span class="sxs-lookup"><span data-stu-id="20250-114">Valid values for  _lpInterface_ include IID_IUnknown, IID_IMAPIProp, IID_IMAPIContainer, and IID_IMAPIFolder.</span></span> 
    
 <span data-ttu-id="20250-115">_lpDestFolder_</span><span class="sxs-lookup"><span data-stu-id="20250-115">_lpDestFolder_</span></span>
  
> <span data-ttu-id="20250-116">[in]打开接收的复制或移动的子文件夹的文件夹指向的指针。</span><span class="sxs-lookup"><span data-stu-id="20250-116">[in] A pointer to the open folder to receive the copied or moved subfolder.</span></span>
    
 <span data-ttu-id="20250-117">_lpszNewFolderName_</span><span class="sxs-lookup"><span data-stu-id="20250-117">_lpszNewFolderName_</span></span>
  
> <span data-ttu-id="20250-118">[in]一个指向其新的目标中复制或移动的文件夹的名称。</span><span class="sxs-lookup"><span data-stu-id="20250-118">[in] A pointer to the name of the copied or moved folder in its new destination.</span></span> <span data-ttu-id="20250-119">如果_lpszNewFolderName_设置为 NULL，则源子文件夹名称用于目标文件夹的名称。</span><span class="sxs-lookup"><span data-stu-id="20250-119">If  _lpszNewFolderName_ is set to NULL, the name of the source subfolder is used for the name of the destination folder.</span></span> 
    
 <span data-ttu-id="20250-120">_ulUIParam_</span><span class="sxs-lookup"><span data-stu-id="20250-120">_ulUIParam_</span></span>
  
> <span data-ttu-id="20250-121">[in]进度指示器的父窗口句柄。</span><span class="sxs-lookup"><span data-stu-id="20250-121">[in] A handle to the parent window of the progress indicator.</span></span> <span data-ttu-id="20250-122">除非设置了 FOLDER_DIALOG 标志_ulFlags_参数中的，将忽略该_ulUIParam_参数。</span><span class="sxs-lookup"><span data-stu-id="20250-122">The  _ulUIParam_ parameter is ignored unless the FOLDER_DIALOG flag in the  _ulFlags_ parameter is set.</span></span> 
    
 <span data-ttu-id="20250-123">_lpProgress_</span><span class="sxs-lookup"><span data-stu-id="20250-123">_lpProgress_</span></span>
  
> <span data-ttu-id="20250-124">[in]指向显示进度指示器进度对象的指针。</span><span class="sxs-lookup"><span data-stu-id="20250-124">[in] A pointer to a progress object that displays a progress indicator.</span></span> <span data-ttu-id="20250-125">如果在_lpProgress_传递 NULL，则消息存储提供程序将使用 MAPI 进度对象实现显示进度指示器。</span><span class="sxs-lookup"><span data-stu-id="20250-125">If NULL is passed in  _lpProgress_, the message store provider displays a progress indicator by using the MAPI progress object implementation.</span></span> <span data-ttu-id="20250-126">除非_ulFlags_中设置了 FOLDER_DIALOG 标志，则将忽略该_lpProgress_参数。</span><span class="sxs-lookup"><span data-stu-id="20250-126">The  _lpProgress_ parameter is ignored unless the FOLDER_DIALOG flag is set in  _ulFlags_.</span></span>
    
 <span data-ttu-id="20250-127">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="20250-127">_ulFlags_</span></span>
  
> <span data-ttu-id="20250-128">[in]位掩码的标志，用于控制复制或移动操作。</span><span class="sxs-lookup"><span data-stu-id="20250-128">[in] A bitmask of flags that controls the copy or move operation.</span></span> <span data-ttu-id="20250-129">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="20250-129">The following flags can be set:</span></span>
    
<span data-ttu-id="20250-130">COPY_SUBFOLDERS</span><span class="sxs-lookup"><span data-stu-id="20250-130">COPY_SUBFOLDERS</span></span> 
  
> <span data-ttu-id="20250-131">所有要复制的子文件夹中的子文件夹也应复制。</span><span class="sxs-lookup"><span data-stu-id="20250-131">All of the subfolders in the subfolder to be copied should also be copied.</span></span> <span data-ttu-id="20250-132">当 COPY_SUBFOLDERS 未设置的复制操作时，将复制仅由_lpEntryID_标识的子文件夹。</span><span class="sxs-lookup"><span data-stu-id="20250-132">When COPY_SUBFOLDERS is not set for a copy operation, only the subfolder identified by  _lpEntryID_ is copied.</span></span> <span data-ttu-id="20250-133">移动操作，COPY_SUBFOLDERS 行为是默认的无论是否设置了标志。</span><span class="sxs-lookup"><span data-stu-id="20250-133">With a move operation, the COPY_SUBFOLDERS behavior is the default regardless of whether the flag is set.</span></span> 
    
<span data-ttu-id="20250-134">FOLDER_DIALOG</span><span class="sxs-lookup"><span data-stu-id="20250-134">FOLDER_DIALOG</span></span> 
  
> <span data-ttu-id="20250-135">请求进度指示器的显示。</span><span class="sxs-lookup"><span data-stu-id="20250-135">Requests the display of a progress indicator.</span></span>
    
<span data-ttu-id="20250-136">FOLDER_MOVE</span><span class="sxs-lookup"><span data-stu-id="20250-136">FOLDER_MOVE</span></span> 
  
> <span data-ttu-id="20250-137">Subfolder 是要移动而不是复制。</span><span class="sxs-lookup"><span data-stu-id="20250-137">The subfolder is to be moved instead of copied.</span></span> <span data-ttu-id="20250-138">如果未设置 FOLDER_MOVE，复制的子文件夹。</span><span class="sxs-lookup"><span data-stu-id="20250-138">If FOLDER_MOVE is not set, the subfolder is copied.</span></span>
    
<span data-ttu-id="20250-139">MAPI_DECLINE_OK</span><span class="sxs-lookup"><span data-stu-id="20250-139">MAPI_DECLINE_OK</span></span> 
  
> <span data-ttu-id="20250-140">通知的消息存储提供程序，它通过调用其支持对象[IMAPISupport::DoCopyTo](imapisupport-docopyto.md)或[IMAPISupport::DoCopyProps](imapisupport-docopyprops.md)方法实现**CopyFolder** ，如果**CopyFolder**应改为立即返回 MAPI_E_DECLINE_COPY。</span><span class="sxs-lookup"><span data-stu-id="20250-140">Informs the message store provider that if it implements **CopyFolder** by calling its support object's [IMAPISupport::DoCopyTo](imapisupport-docopyto.md) or [IMAPISupport::DoCopyProps](imapisupport-docopyprops.md) method, **CopyFolder** should instead immediately return MAPI_E_DECLINE_COPY.</span></span> 
    
<span data-ttu-id="20250-141">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="20250-141">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="20250-142">目标文件夹的名称为 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="20250-142">The name of the destination folder is in Unicode format.</span></span> <span data-ttu-id="20250-143">如果未设置 MAPI_UNICODE 标志，文件夹名称是 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="20250-143">If the MAPI_UNICODE flag is not set, the folder name is in ANSI format.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="20250-144">返回值</span><span class="sxs-lookup"><span data-stu-id="20250-144">Return value</span></span>

<span data-ttu-id="20250-145">S_OK</span><span class="sxs-lookup"><span data-stu-id="20250-145">S_OK</span></span> 
  
> <span data-ttu-id="20250-146">已成功复制或移动指定的文件夹。</span><span class="sxs-lookup"><span data-stu-id="20250-146">The specified folder has been successfully copied or moved.</span></span>
    
<span data-ttu-id="20250-147">MAPI_E_BAD_CHARWIDTH</span><span class="sxs-lookup"><span data-stu-id="20250-147">MAPI_E_BAD_CHARWIDTH</span></span> 
  
> <span data-ttu-id="20250-148">既设置了 MAPI_UNICODE 标志消息存储提供程序不支持 Unicode，或未设置 MAPI_UNICODE 和消息存储提供程序支持仅 Unicode。</span><span class="sxs-lookup"><span data-stu-id="20250-148">Either the MAPI_UNICODE flag was set and the message store provider does not support Unicode, or MAPI_UNICODE was not set and the message store provider supports only Unicode.</span></span>
    
<span data-ttu-id="20250-149">MAPI_E_COLLISION</span><span class="sxs-lookup"><span data-stu-id="20250-149">MAPI_E_COLLISION</span></span> 
  
> <span data-ttu-id="20250-150">正在移动或复制的文件夹的名称为相同的目标文件夹中的子文件夹。</span><span class="sxs-lookup"><span data-stu-id="20250-150">The name of the folder being moved or copied is the same as that of a subfolder in the destination folder.</span></span> <span data-ttu-id="20250-151">消息存储提供程序需要唯一文件夹名称。</span><span class="sxs-lookup"><span data-stu-id="20250-151">The message store provider requires unique folder names.</span></span>
    
<span data-ttu-id="20250-152">MAPI_E_DECLINE_COPY</span><span class="sxs-lookup"><span data-stu-id="20250-152">MAPI_E_DECLINE_COPY</span></span> 
  
> <span data-ttu-id="20250-153">提供程序实现此方法通过调用支持对象方法，并且将呼叫者已传递 MAPI_DECLINE_OK 标志。</span><span class="sxs-lookup"><span data-stu-id="20250-153">The provider implements this method by calling a support object method, and the caller has passed the MAPI_DECLINE_OK flag.</span></span>
    
<span data-ttu-id="20250-154">MAPI_E_FOLDER_CYCLE</span><span class="sxs-lookup"><span data-stu-id="20250-154">MAPI_E_FOLDER_CYCLE</span></span> 
  
> <span data-ttu-id="20250-155">源文件夹直接或间接包含目标文件夹。</span><span class="sxs-lookup"><span data-stu-id="20250-155">The source folder directly or indirectly contains the destination folder.</span></span> <span data-ttu-id="20250-156">重要工作可能已执行之前已发现这种情况，因此可能部分修改源和目标文件夹。</span><span class="sxs-lookup"><span data-stu-id="20250-156">Significant work may have been performed before this condition was discovered, so the source and destination folder may be partially modified.</span></span> 
    
<span data-ttu-id="20250-157">MAPI_W_PARTIAL_COMPLETION</span><span class="sxs-lookup"><span data-stu-id="20250-157">MAPI_W_PARTIAL_COMPLETION</span></span> 
  
> <span data-ttu-id="20250-158">调用成功，但并非所有的项目复制成功。</span><span class="sxs-lookup"><span data-stu-id="20250-158">The call succeeded, but not all entries were successfully copied.</span></span> <span data-ttu-id="20250-159">返回此警告时，应处理呼叫为成功。</span><span class="sxs-lookup"><span data-stu-id="20250-159">When this warning is returned, the call should be handled as successful.</span></span> <span data-ttu-id="20250-160">若要测试此警告，请使用**HR_FAILED**宏。</span><span class="sxs-lookup"><span data-stu-id="20250-160">To test for this warning, use the **HR_FAILED** macro.</span></span> <span data-ttu-id="20250-161">有关详细信息，请参阅[使用宏的错误处理](using-macros-for-error-handling.md)。</span><span class="sxs-lookup"><span data-stu-id="20250-161">For more information, see [Using Macros for Error Handling](using-macros-for-error-handling.md).</span></span>
    
## <a name="remarks"></a><span data-ttu-id="20250-162">说明</span><span class="sxs-lookup"><span data-stu-id="20250-162">Remarks</span></span>

<span data-ttu-id="20250-163">**IMAPIFolder::CopyFolder**方法复制，或将子文件夹从一个位置移至另一个。</span><span class="sxs-lookup"><span data-stu-id="20250-163">The **IMAPIFolder::CopyFolder** method copies or moves a subfolder from one location to another.</span></span> <span data-ttu-id="20250-164">正在复制或移动的子文件夹为子文件夹添加到目标文件夹中。</span><span class="sxs-lookup"><span data-stu-id="20250-164">The subfolder being copied or moved is added to the destination folder as a subfolder.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="20250-165">针对实施者的注释</span><span class="sxs-lookup"><span data-stu-id="20250-165">Notes to implementers</span></span>

<span data-ttu-id="20250-166">当复制或移动操作通过设置 COPY_SUBFOLDERS 标志指示涉及多个文件夹时，每个文件夹尽可能完整执行操作。</span><span class="sxs-lookup"><span data-stu-id="20250-166">When the copy or move operation involves more than one folder, as indicated by setting the COPY_SUBFOLDERS flag, perform the operation as completely as possible for each folder.</span></span> <span data-ttu-id="20250-167">有时之一要移动或复制的文件夹不存在或已移动或复制到其他位置。</span><span class="sxs-lookup"><span data-stu-id="20250-167">Sometimes one of the folders to be moved or copied does not exist or has already been moved or copied elsewhere.</span></span> <span data-ttu-id="20250-168">不停止操作提前除非超过了您的控件，如运行内存不足、 不足磁盘空间或损坏消息存储区中的出现故障。</span><span class="sxs-lookup"><span data-stu-id="20250-168">Do not stop the operation prematurely unless a failure occurs that is beyond your control, such as running out of memory, running out of disk space, or corruption in the message store.</span></span>
  
<span data-ttu-id="20250-169">尝试保留复制邮件中的所有邮件项标识符。</span><span class="sxs-lookup"><span data-stu-id="20250-169">Try to retain all message entry identifiers in the copied messages.</span></span> <span data-ttu-id="20250-170">您还应尝试保留项标识符，但它并不需要。</span><span class="sxs-lookup"><span data-stu-id="20250-170">You should also try to preserve entry identifiers, but it is not required.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="20250-171">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="20250-171">Notes to callers</span></span>

<span data-ttu-id="20250-172">希望在下列情况下的这些返回值。</span><span class="sxs-lookup"><span data-stu-id="20250-172">Expect these return values under the following conditions.</span></span>
  
|<span data-ttu-id="20250-173">**条件**</span><span class="sxs-lookup"><span data-stu-id="20250-173">**Condition**</span></span>|<span data-ttu-id="20250-174">**返回值**</span><span class="sxs-lookup"><span data-stu-id="20250-174">**Return value**</span></span>|
|:-----|:-----|
|<span data-ttu-id="20250-175">**CopyFolder**成功复制或移动的每个邮件和子文件夹。</span><span class="sxs-lookup"><span data-stu-id="20250-175">**CopyFolder** has successfully copied or moved every message and subfolder.</span></span>  <br/> |<span data-ttu-id="20250-176">S_OK</span><span class="sxs-lookup"><span data-stu-id="20250-176">S_OK</span></span>  <br/> |
|<span data-ttu-id="20250-177">**CopyFolder**程序无法成功复制或移动的每个邮件和子文件夹。</span><span class="sxs-lookup"><span data-stu-id="20250-177">**CopyFolder** was unable to successfully copy or move every message and subfolder.</span></span>  <br/> |<span data-ttu-id="20250-178">MAPI_W_PARTIAL_COMPLETION 或 MAPI_E_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="20250-178">MAPI_W_PARTIAL_COMPLETION or MAPI_E_NOT_FOUND</span></span>  <br/> |
|<span data-ttu-id="20250-179">**CopyFolder**无法完成。</span><span class="sxs-lookup"><span data-stu-id="20250-179">**CopyFolder** was unable to complete.</span></span>  <br/> |<span data-ttu-id="20250-180">除 MAPI_E_NOT_FOUND 任何错误值</span><span class="sxs-lookup"><span data-stu-id="20250-180">Any error value except MAPI_E_NOT_FOUND</span></span>  <br/> |
   
<span data-ttu-id="20250-181">**CopyFolder**无法完成后，请假定已完成任何工时。</span><span class="sxs-lookup"><span data-stu-id="20250-181">When **CopyFolder** is unable to complete, do not assume that no work was done.</span></span> <span data-ttu-id="20250-182">**CopyFolder**可能已经能够复制或移动遇到错误之前的一个或多个邮件和子文件夹。</span><span class="sxs-lookup"><span data-stu-id="20250-182">**CopyFolder** might have been able to copy or move one or more of the messages and subfolders before encountering the error.</span></span> 
  
<span data-ttu-id="20250-183">_LpEntryID_中传递的文件夹不存在的项标识符，如果**CopyFolder**返回 MAPI_W_PARTIAL_COMPLETION 或 MAPI_E_NOT_FOUND，具体取决于邮件存储的实现。</span><span class="sxs-lookup"><span data-stu-id="20250-183">If an entry identifier for a folder that does not exist is passed in  _lpEntryID_, **CopyFolder** returns MAPI_W_PARTIAL_COMPLETION or MAPI_E_NOT_FOUND, depending on the message store's implementation.</span></span> 
  
<span data-ttu-id="20250-184">消息存储提供程序，根据原始邮件的项标识符可能或可能不会保留复制邮件中。</span><span class="sxs-lookup"><span data-stu-id="20250-184">Depending on the message store provider, the entry identifier of the original message may or may not be preserved in the copied message.</span></span> <span data-ttu-id="20250-185">您应保留项标识符，只要有可能，但它并不要求。</span><span class="sxs-lookup"><span data-stu-id="20250-185">You should preserve entry identifiers whenever possible, but it is not a requirement.</span></span> <span data-ttu-id="20250-186">您通常取决于以下方案：</span><span class="sxs-lookup"><span data-stu-id="20250-186">You can generally depend on the following scenarios:</span></span>
  
- <span data-ttu-id="20250-187">消息存储的两种不同类型之间移动文件夹时，项标识符保证更改。</span><span class="sxs-lookup"><span data-stu-id="20250-187">When you move a folder between two different types of message stores, the entry identifier is guaranteed to change.</span></span>
    
- <span data-ttu-id="20250-188">属于同一字段类型的两个邮件存储之间移动文件夹时，始终更改的项标识符。</span><span class="sxs-lookup"><span data-stu-id="20250-188">When you move a folder between two message stores of the same type, the entry identifier almost always changes.</span></span>
    
- <span data-ttu-id="20250-189">当将文件夹移到另一位置相同的邮件存储区中时，条目标识符可能或可能不更改，具体取决于消息存储提供程序。</span><span class="sxs-lookup"><span data-stu-id="20250-189">When you move a folder to another location in the same message store, the entry identifier may or may not change, depending on the message store provider.</span></span>
    
## <a name="mfcmapi-reference"></a><span data-ttu-id="20250-190">MFCMAPI 参考 （英文）</span><span class="sxs-lookup"><span data-stu-id="20250-190">MFCMAPI reference</span></span>

<span data-ttu-id="20250-191">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="20250-191">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="20250-192">**文件**</span><span class="sxs-lookup"><span data-stu-id="20250-192">**File**</span></span>|<span data-ttu-id="20250-193">**函数**</span><span class="sxs-lookup"><span data-stu-id="20250-193">**Function**</span></span>|<span data-ttu-id="20250-194">**Comment**</span><span class="sxs-lookup"><span data-stu-id="20250-194">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="20250-195">MsgStoreDlg.cpp</span><span class="sxs-lookup"><span data-stu-id="20250-195">MsgStoreDlg.cpp</span></span>  <br/> |<span data-ttu-id="20250-196">CMsgStoreDlg::OnPasteFolder</span><span class="sxs-lookup"><span data-stu-id="20250-196">CMsgStoreDlg::OnPasteFolder</span></span>  <br/> |<span data-ttu-id="20250-197">MFCMAPI 使用**IMAPIFolder::CopyFolder**方法将文件夹从一个位置复制到另一个。</span><span class="sxs-lookup"><span data-stu-id="20250-197">MFCMAPI uses the **IMAPIFolder::CopyFolder** method to copy folders from one location to another.</span></span> <span data-ttu-id="20250-198">MFCMAPI 复制操作期间记住源文件夹，并在粘贴操作过程中实际执行该副本。</span><span class="sxs-lookup"><span data-stu-id="20250-198">MFCMAPI remembers the source folder during the copy operation and actually performs the copy during the paste operation.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="20250-199">另请参阅</span><span class="sxs-lookup"><span data-stu-id="20250-199">See also</span></span>



[<span data-ttu-id="20250-200">IMAPIFolder : IMAPIContainer</span><span class="sxs-lookup"><span data-stu-id="20250-200">IMAPIFolder : IMAPIContainer</span></span>](imapifolderimapicontainer.md)


[<span data-ttu-id="20250-201">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="20250-201">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

