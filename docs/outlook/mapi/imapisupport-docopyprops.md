---
title: IMAPISupportDoCopyProps
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISupport.DoCopyProps
api_type:
- COM
ms.assetid: 2446ef52-578a-4004-9719-de9b0207ccad
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 24107ae1926c8590da6a823a354eeae72d72f248
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33405581"
---
# <a name="imapisupportdocopyprops"></a><span data-ttu-id="311d2-103">IMAPISupport::DoCopyProps</span><span class="sxs-lookup"><span data-stu-id="311d2-103">IMAPISupport::DoCopyProps</span></span>

  
  
<span data-ttu-id="311d2-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="311d2-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="311d2-105">将对象的一个或多个属性复制或移动到另一个对象。</span><span class="sxs-lookup"><span data-stu-id="311d2-105">Copies or moves one or more properties of an object to another object.</span></span>
  
```cpp
HRESULT DoCopyProps(
  LPCIID lpSrcInterface,
  LPVOID lpSrcObj,
  LPSPropTagArray lpIncludeProps,
  ULONG_PTR ulUIParam,
  LPMAPIPROGRESS lpProgress,
  LPCIID lpDestInterface,
  LPVOID lpDestObj,
  ULONG ulFlags,
  LPSPropProblemArray FAR * lppProblems
);
```

## <a name="parameters"></a><span data-ttu-id="311d2-106">参数</span><span class="sxs-lookup"><span data-stu-id="311d2-106">Parameters</span></span>

 <span data-ttu-id="311d2-107">_lpSrcInterface_</span><span class="sxs-lookup"><span data-stu-id="311d2-107">_lpSrcInterface_</span></span>
  
> <span data-ttu-id="311d2-108">[in]指向接口标识符的指针 (IID) 表示用于访问包含要复制或移动的属性的对象的接口。</span><span class="sxs-lookup"><span data-stu-id="311d2-108">[in] A pointer to the interface identifier (IID) that represents the interface to be used to access the object with the properties to be copied or moved.</span></span>
    
 <span data-ttu-id="311d2-109">_lpSrcObj_</span><span class="sxs-lookup"><span data-stu-id="311d2-109">_lpSrcObj_</span></span>
  
> <span data-ttu-id="311d2-110">[in]指向包含要复制或移动的属性的对象的指针。</span><span class="sxs-lookup"><span data-stu-id="311d2-110">[in] A pointer to the object that contains the properties to be copied or moved.</span></span>
    
 <span data-ttu-id="311d2-111">_lpIncludeProps_</span><span class="sxs-lookup"><span data-stu-id="311d2-111">_lpIncludeProps_</span></span>
  
> <span data-ttu-id="311d2-112">[in]指向 [SPropTagArray](sproptagarray.md) 结构的指针，其中包含指示要复制或移动的属性标记的计数数组。</span><span class="sxs-lookup"><span data-stu-id="311d2-112">[in] A pointer to an [SPropTagArray](sproptagarray.md) structure that contains a counted array of property tags that indicate the properties to copy or move.</span></span> <span data-ttu-id="311d2-113">_lpIncludeProps_ 参数不能为 NULL。</span><span class="sxs-lookup"><span data-stu-id="311d2-113">The  _lpIncludeProps_ parameter cannot be NULL.</span></span> 
    
 <span data-ttu-id="311d2-114">_ulUIParam_</span><span class="sxs-lookup"><span data-stu-id="311d2-114">_ulUIParam_</span></span>
  
> <span data-ttu-id="311d2-115">[in]进度指示器的父窗口的句柄。</span><span class="sxs-lookup"><span data-stu-id="311d2-115">[in] A handle to the parent window of the progress indicator.</span></span>
    
 <span data-ttu-id="311d2-116">_lpProgress_</span><span class="sxs-lookup"><span data-stu-id="311d2-116">_lpProgress_</span></span>
  
> <span data-ttu-id="311d2-117">[in]指向进度指示器的实现指针。</span><span class="sxs-lookup"><span data-stu-id="311d2-117">[in] A pointer to an implementation of a progress indicator.</span></span> <span data-ttu-id="311d2-118">如果在  _lpProgress_ 参数中传递 NULL，则使用 MAPI 实现显示进度指示器。</span><span class="sxs-lookup"><span data-stu-id="311d2-118">If NULL is passed in the  _lpProgress_ parameter, the progress indicator is displayed by using the MAPI implementation.</span></span> <span data-ttu-id="311d2-119">除非在 _ulFlags_ 参数中设置了 MAPI_DIALOG 标志，否则将忽略 _lpProgress_ 参数。</span><span class="sxs-lookup"><span data-stu-id="311d2-119">The  _lpProgress_ parameter is ignored unless the MAPI_DIALOG flag is set in the  _ulFlags_ parameter.</span></span> 
    
 <span data-ttu-id="311d2-120">_lpDestInterface_</span><span class="sxs-lookup"><span data-stu-id="311d2-120">_lpDestInterface_</span></span>
  
> <span data-ttu-id="311d2-121">[in]指向接口标识符的指针，该标识符表示用于访问对象以接收复制或移动的属性的接口。</span><span class="sxs-lookup"><span data-stu-id="311d2-121">[in] A pointer to the interface identifier that represents the interface to be used to access the object to receive the properties that are copied or moved.</span></span>
    
 <span data-ttu-id="311d2-122">_lpDestObj_</span><span class="sxs-lookup"><span data-stu-id="311d2-122">_lpDestObj_</span></span>
  
> <span data-ttu-id="311d2-123">[in]指向接收复制或移动的属性的对象的指针。</span><span class="sxs-lookup"><span data-stu-id="311d2-123">[in] A pointer to the object to receive the copied or moved properties.</span></span>
    
 <span data-ttu-id="311d2-124">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="311d2-124">_ulFlags_</span></span>
  
> <span data-ttu-id="311d2-125">[in]控制复制或移动操作执行方式的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="311d2-125">[in] A bitmask of flags that controls how the copy or move operation is performed.</span></span> <span data-ttu-id="311d2-126">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="311d2-126">The following flags can be set:</span></span>
    
<span data-ttu-id="311d2-127">MAPI_DIALOG</span><span class="sxs-lookup"><span data-stu-id="311d2-127">MAPI_DIALOG</span></span> 
  
> <span data-ttu-id="311d2-128">显示进度指示器。</span><span class="sxs-lookup"><span data-stu-id="311d2-128">Displays a progress indicator.</span></span>
    
<span data-ttu-id="311d2-129">MAPI_MOVE</span><span class="sxs-lookup"><span data-stu-id="311d2-129">MAPI_MOVE</span></span> 
  
> <span data-ttu-id="311d2-130">**DoCopyProps** 应执行移动操作，而不是复制操作。</span><span class="sxs-lookup"><span data-stu-id="311d2-130">**DoCopyProps** should perform a move operation instead of a copy operation.</span></span> <span data-ttu-id="311d2-131">未设置此标志时 **，DoCopyProps** 将执行复制操作。</span><span class="sxs-lookup"><span data-stu-id="311d2-131">When this flag is not set, **DoCopyProps** performs a copy operation.</span></span> 
    
<span data-ttu-id="311d2-132">MAPI_NOREPLACE</span><span class="sxs-lookup"><span data-stu-id="311d2-132">MAPI_NOREPLACE</span></span> 
  
> <span data-ttu-id="311d2-133">不应覆盖目标对象中的现有属性。</span><span class="sxs-lookup"><span data-stu-id="311d2-133">Existing properties in the destination object should not be overwritten.</span></span> <span data-ttu-id="311d2-134">未设置此标志时 **，DoCopyProps** 将覆盖现有属性。</span><span class="sxs-lookup"><span data-stu-id="311d2-134">When this flag is not set, **DoCopyProps** overwrites existing properties.</span></span> 
    
 <span data-ttu-id="311d2-135">_lppProblems_</span><span class="sxs-lookup"><span data-stu-id="311d2-135">_lppProblems_</span></span>
  
> <span data-ttu-id="311d2-136">[in， out]在输入时，指向指向 [SPropProblemArray 结构的指针的](spropproblemarray.md) 指针;否则为 NULL，表示不需要错误信息。</span><span class="sxs-lookup"><span data-stu-id="311d2-136">[in, out] On input, a pointer to a pointer to an [SPropProblemArray](spropproblemarray.md) structure; otherwise, NULL, which indicates no need for error information.</span></span> <span data-ttu-id="311d2-137">如果  _lppProblems_ 是输入的有效指针， **则 DoCopyProps** 将返回有关复制一个或多个属性时错误的详细信息。</span><span class="sxs-lookup"><span data-stu-id="311d2-137">If  _lppProblems_ is a valid pointer on input, **DoCopyProps** returns detailed information about errors in copying one or more properties.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="311d2-138">返回值</span><span class="sxs-lookup"><span data-stu-id="311d2-138">Return value</span></span>

<span data-ttu-id="311d2-139">S_OK</span><span class="sxs-lookup"><span data-stu-id="311d2-139">S_OK</span></span> 
  
> <span data-ttu-id="311d2-140">已成功复制或移动属性。</span><span class="sxs-lookup"><span data-stu-id="311d2-140">Properties were successfully copied or moved.</span></span>
    
<span data-ttu-id="311d2-141">MAPI_E_COLLISION</span><span class="sxs-lookup"><span data-stu-id="311d2-141">MAPI_E_COLLISION</span></span> 
  
> <span data-ttu-id="311d2-142">要复制或移动的属性在目标对象中已存在，MAPI_NOREPLACE标记。</span><span class="sxs-lookup"><span data-stu-id="311d2-142">A property to be copied or moved already exists in the destination object and the MAPI_NOREPLACE flag is set.</span></span> 
    
<span data-ttu-id="311d2-143">MAPI_E_FOLDER_CYCLE</span><span class="sxs-lookup"><span data-stu-id="311d2-143">MAPI_E_FOLDER_CYCLE</span></span> 
  
> <span data-ttu-id="311d2-144">源对象直接或间接包含目标对象。</span><span class="sxs-lookup"><span data-stu-id="311d2-144">The source object directly or indirectly contains the destination object.</span></span> <span data-ttu-id="311d2-145">在发现此条件之前，可能执行了大量工作，因此可能会部分修改源对象和目标对象。</span><span class="sxs-lookup"><span data-stu-id="311d2-145">Significant work might have been performed before this condition was discovered, so the source and destination objects might be partially modified.</span></span> 
    
<span data-ttu-id="311d2-146">MAPI_E_INTERFACE_NOT_SUPPORTED</span><span class="sxs-lookup"><span data-stu-id="311d2-146">MAPI_E_INTERFACE_NOT_SUPPORTED</span></span> 
  
> <span data-ttu-id="311d2-147">源对象不支持由  _lpSrcInterface_ 参数标识的接口，或者目标对象不支持  _由 lpDestInterface_ 参数标识的接口。</span><span class="sxs-lookup"><span data-stu-id="311d2-147">The interface identified by the  _lpSrcInterface_ parameter is not supported by the source object, or the interface identified by the  _lpDestInterface_ parameter is not supported by the destination object.</span></span> 
    
<span data-ttu-id="311d2-148">MAPI_E_NO_ACCESS</span><span class="sxs-lookup"><span data-stu-id="311d2-148">MAPI_E_NO_ACCESS</span></span> 
  
> <span data-ttu-id="311d2-149">试图访问调用方权限不足的对象。</span><span class="sxs-lookup"><span data-stu-id="311d2-149">An attempt was made to access an object for which the caller has insufficient permissions.</span></span> <span data-ttu-id="311d2-150">如果目标对象与源对象相同，则返回此错误。</span><span class="sxs-lookup"><span data-stu-id="311d2-150">This error is returned if the destination object is the same as the source object.</span></span>
    
<span data-ttu-id="311d2-151">以下值可以在 **SPropProblemArray** 结构中返回，但不能作为 **DoCopyProps 的返回值**。</span><span class="sxs-lookup"><span data-stu-id="311d2-151">The following values can be returned in the **SPropProblemArray** structure, but not as return values for **DoCopyProps**.</span></span> <span data-ttu-id="311d2-152">这些错误适用于单个属性。</span><span class="sxs-lookup"><span data-stu-id="311d2-152">These errors apply to a single property.</span></span>
  
<span data-ttu-id="311d2-153">MAPI_E_BAD_CHARWIDTH</span><span class="sxs-lookup"><span data-stu-id="311d2-153">MAPI_E_BAD_CHARWIDTH</span></span> 
  
> <span data-ttu-id="311d2-154">设置MAPI_UNICODE **DoCopyProps** 不支持 Unicode，或者未MAPI_UNICODE **DoCopyProps** 仅支持 Unicode。</span><span class="sxs-lookup"><span data-stu-id="311d2-154">Either the MAPI_UNICODE flag was set and **DoCopyProps** does not support Unicode, or MAPI_UNICODE was not set and **DoCopyProps** supports only Unicode.</span></span> 
    
<span data-ttu-id="311d2-155">MAPI_E_COMPUTED</span><span class="sxs-lookup"><span data-stu-id="311d2-155">MAPI_E_COMPUTED</span></span> 
  
> <span data-ttu-id="311d2-156">调用方无法修改该属性，因为它是一个只读属性，由目标对象的所有者计算。</span><span class="sxs-lookup"><span data-stu-id="311d2-156">The property cannot be modified by the caller because it is a read-only property, computed by the owner of the destination object.</span></span> <span data-ttu-id="311d2-157">此错误并不严重;调用方应允许复制操作继续。</span><span class="sxs-lookup"><span data-stu-id="311d2-157">This error is not severe; the caller should allow the copy operation to continue.</span></span>
    
<span data-ttu-id="311d2-158">MAPI_E_INVALID_TYPE</span><span class="sxs-lookup"><span data-stu-id="311d2-158">MAPI_E_INVALID_TYPE</span></span> 
  
> <span data-ttu-id="311d2-159">属性类型无效。</span><span class="sxs-lookup"><span data-stu-id="311d2-159">The property type is invalid.</span></span>
    
<span data-ttu-id="311d2-160">MAPI_E_UNEXPECTED_TYPE</span><span class="sxs-lookup"><span data-stu-id="311d2-160">MAPI_E_UNEXPECTED_TYPE</span></span> 
  
> <span data-ttu-id="311d2-161">属性类型不是调用方预期的类型。</span><span class="sxs-lookup"><span data-stu-id="311d2-161">The property type is not the type that the caller expects.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="311d2-162">备注</span><span class="sxs-lookup"><span data-stu-id="311d2-162">Remarks</span></span>

<span data-ttu-id="311d2-163">**IMAPISupport：:D oCopyProps** 方法为邮件存储提供程序支持对象实现。</span><span class="sxs-lookup"><span data-stu-id="311d2-163">The **IMAPISupport::DoCopyProps** method is implemented for message store provider support objects.</span></span> <span data-ttu-id="311d2-164">邮件存储提供程序可以调用 **DoCopyProps** 来实现其文件夹和消息的 [IMAPIProp：：CopyProps](imapiprop-copyprops.md) 方法。</span><span class="sxs-lookup"><span data-stu-id="311d2-164">Message store providers can call **DoCopyProps** to implement the [IMAPIProp::CopyProps](imapiprop-copyprops.md) method for their folders and messages.</span></span> <span data-ttu-id="311d2-165">**DoCopyProps** 复制或移动由  _lpIncludeProps_ 指向的属性标记数组中标识的属性，以及存在于  _lpSrcObj_ 指向的对象中的属性。</span><span class="sxs-lookup"><span data-stu-id="311d2-165">**DoCopyProps** copies or moves the properties that are identified in the property tag array pointed to by  _lpIncludeProps_ and that are present in the object pointed to by  _lpSrcObj_.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="311d2-166">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="311d2-166">Notes to callers</span></span>

<span data-ttu-id="311d2-167">在相同类型的对象（如两条消息）之间复制属性时  _，lpSrcInterface_ 和  _lpDestInterface_ 参数必须包含相同的接口标识符，  _并且 lpSrcObj_ 和  _lpDestObj_ 参数必须指向相同类型的对象。</span><span class="sxs-lookup"><span data-stu-id="311d2-167">When you copy properties between objects of the same type, such as two messages, the  _lpSrcInterface_ and  _lpDestInterface_ parameters must contain the same interface identifier, and the  _lpSrcObj_ and  _lpDestObj_ parameters must point to objects of the same type.</span></span> <span data-ttu-id="311d2-168">如果  _lpDestInterface_ 设置为 NULL， **则 DoCopyProps** MAPI_E_INVALID_PARAMETER。</span><span class="sxs-lookup"><span data-stu-id="311d2-168">If  _lpDestInterface_ is set to NULL, **DoCopyProps** returns MAPI_E_INVALID_PARAMETER.</span></span> <span data-ttu-id="311d2-169">如果将  _lpDestInterface_ 设置为可接受的接口标识符，但将  _lpDestObj_ 设置为无效指针，则结果不可预测。</span><span class="sxs-lookup"><span data-stu-id="311d2-169">If you set  _lpDestInterface_ to an acceptable interface identifier, but set  _lpDestObj_ to an invalid pointer, the results are unpredictable.</span></span> <span data-ttu-id="311d2-170">你的提供程序很可能失败。</span><span class="sxs-lookup"><span data-stu-id="311d2-170">Most likely your provider will fail.</span></span> 
  
<span data-ttu-id="311d2-171">如果MAPI_NOREPLACE对象中任何属性都将被覆盖，则设置该标志。</span><span class="sxs-lookup"><span data-stu-id="311d2-171">Set the MAPI_NOREPLACE flag if you do not want any of the properties in the destination object to be overwritten.</span></span> <span data-ttu-id="311d2-172">不会删除或修改目标对象中存在于源对象中且未覆盖的属性。</span><span class="sxs-lookup"><span data-stu-id="311d2-172">Properties in the destination object that exist in the source object and are not overwritten are not deleted or modified.</span></span>
  
<span data-ttu-id="311d2-173">若要复制邮件的收件人列表，在 _lpIncludeProps_ 参数指向的属性标记数组中包括 **PR_MESSAGE_RECIPIENTS** ([PidTagMessageRecipients](pidtagmessagerecipients-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="311d2-173">To copy a message's recipient list, include the **PR_MESSAGE_RECIPIENTS** ([PidTagMessageRecipients](pidtagmessagerecipients-canonical-property.md)) property in the property tag array pointed to by the  _lpIncludeProps_ parameter.</span></span> <span data-ttu-id="311d2-174">若要复制邮件的附件，请包含 PR_MESSAGE_ATTACHMENTS  ([PidTagMessageAttachments](pidtagmessageattachments-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="311d2-174">To copy the message's attachments, include the **PR_MESSAGE_ATTACHMENTS** ([PidTagMessageAttachments](pidtagmessageattachments-canonical-property.md)) property.</span></span> 
  
<span data-ttu-id="311d2-175">若要复制文件夹或通讯簿容器的层次结构或内容表，在属性标记数组中包括 **PR_CONTAINER_HIERARCHY** ([PidTagContainerHierarchy](pidtagcontainerhierarchy-canonical-property.md)) 或 **PR_CONTAINER_CONTENTS** ([PidTagContainerContents](pidtagcontainercontents-canonical-property.md)) 。</span><span class="sxs-lookup"><span data-stu-id="311d2-175">To copy a folder or address book container's hierarchy or contents table, include **PR_CONTAINER_HIERARCHY** ([PidTagContainerHierarchy](pidtagcontainerhierarchy-canonical-property.md)) or **PR_CONTAINER_CONTENTS** ([PidTagContainerContents](pidtagcontainercontents-canonical-property.md)) in the property tag array.</span></span> <span data-ttu-id="311d2-176">若要包含文件夹的关联内容表，PR_FOLDER_ASSOCIATED_CONTENTS ([PidTagFolderAssociatedContents](pidtagfolderassociatedcontents-canonical-property.md)) 属性。 </span><span class="sxs-lookup"><span data-stu-id="311d2-176">To include a folder's associated contents table, include the **PR_FOLDER_ASSOCIATED_CONTENTS** ([PidTagFolderAssociatedContents](pidtagfolderassociatedcontents-canonical-property.md)) property in the array.</span></span>
  
<span data-ttu-id="311d2-177">如果复制或移动子文件夹，则无论 **使用 SPropTagArray** 结构指示的属性如何，其内容都将完整复制或移动。</span><span class="sxs-lookup"><span data-stu-id="311d2-177">If subfolders are copied or moved, their contents are copied or moved in their entirety, regardless of the use of properties indicated by the **SPropTagArray** structure.</span></span> 
  
 <span data-ttu-id="311d2-178">**DoCopyProps** 报告作为一个整体操作发生的全局错误，以及一个或多个属性发生的单个错误。</span><span class="sxs-lookup"><span data-stu-id="311d2-178">**DoCopyProps** reports global errors that occur with the operation as a whole, and individual errors that occur with one or more of the properties.</span></span> <span data-ttu-id="311d2-179">这些单个错误将放入 **SPropProblemArray** 结构中。</span><span class="sxs-lookup"><span data-stu-id="311d2-179">These individual errors are put in an **SPropProblemArray** structure.</span></span> <span data-ttu-id="311d2-180">可以通过为属性问题数组结构参数传递 NULL（而不是有效指针）来禁止在属性级别报告错误。</span><span class="sxs-lookup"><span data-stu-id="311d2-180">You can suppress error reporting at the property level by passing NULL, rather than a valid pointer, for the property problem array structure parameter.</span></span> 
  
<span data-ttu-id="311d2-181">如果要接收有关错误的信息，请传递 _lppProblems_ 参数中的有效 **SPropProblemArray** 结构指针。</span><span class="sxs-lookup"><span data-stu-id="311d2-181">If you want to receive information about errors, pass a valid **SPropProblemArray** structure pointer in the  _lppProblems_ parameter.</span></span> <span data-ttu-id="311d2-182">当 **DoCopyProps** 返回S_OK时，请检查结构中各个属性的可能错误。</span><span class="sxs-lookup"><span data-stu-id="311d2-182">When **DoCopyProps** returns S_OK, check for possible errors with individual properties in the structure.</span></span> <span data-ttu-id="311d2-183">当 **DoCopyProps** 返回错误时 **，SPropProblemArray** 结构中不会返回任何信息。</span><span class="sxs-lookup"><span data-stu-id="311d2-183">When **DoCopyProps** returns an error, no information is returned in the **SPropProblemArray** structure.</span></span> <span data-ttu-id="311d2-184">相反，请调用 [IMAPISupport：：GetLastError](imapisupport-getlasterror.md) 方法来检索详细的错误信息。</span><span class="sxs-lookup"><span data-stu-id="311d2-184">Instead, call the [IMAPISupport::GetLastError](imapisupport-getlasterror.md) method to retrieve detailed error information.</span></span> 
  
<span data-ttu-id="311d2-185">如果 **DoCopyProps** S_OK，请通过调用 [MAPIFreeBuffer](mapifreebuffer.md)函数释放返回的 **SPropProblemArray** 结构。</span><span class="sxs-lookup"><span data-stu-id="311d2-185">If **DoCopyProps** returns S_OK, free the returned **SPropProblemArray** structure by calling the [MAPIFreeBuffer](mapifreebuffer.md) function.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="311d2-186">另请参阅</span><span class="sxs-lookup"><span data-stu-id="311d2-186">See also</span></span>



[<span data-ttu-id="311d2-187">IMAPIProp::CopyProps</span><span class="sxs-lookup"><span data-stu-id="311d2-187">IMAPIProp::CopyProps</span></span>](imapiprop-copyprops.md)
  
[<span data-ttu-id="311d2-188">IMAPISupport::CopyMessages</span><span class="sxs-lookup"><span data-stu-id="311d2-188">IMAPISupport::CopyMessages</span></span>](imapisupport-copymessages.md)
  
[<span data-ttu-id="311d2-189">IMAPISupport::DoCopyTo</span><span class="sxs-lookup"><span data-stu-id="311d2-189">IMAPISupport::DoCopyTo</span></span>](imapisupport-docopyto.md)
  
[<span data-ttu-id="311d2-190">IMAPISupport::GetLastError</span><span class="sxs-lookup"><span data-stu-id="311d2-190">IMAPISupport::GetLastError</span></span>](imapisupport-getlasterror.md)
  
[<span data-ttu-id="311d2-191">PidTagContainerContents 规范属性</span><span class="sxs-lookup"><span data-stu-id="311d2-191">PidTagContainerContents Canonical Property</span></span>](pidtagcontainercontents-canonical-property.md)
  
[<span data-ttu-id="311d2-192">PidTagContainerHierarchy 规范属性</span><span class="sxs-lookup"><span data-stu-id="311d2-192">PidTagContainerHierarchy Canonical Property</span></span>](pidtagcontainerhierarchy-canonical-property.md)
  
[<span data-ttu-id="311d2-193">PidTagFolderAssociatedContents 规范属性</span><span class="sxs-lookup"><span data-stu-id="311d2-193">PidTagFolderAssociatedContents Canonical Property</span></span>](pidtagfolderassociatedcontents-canonical-property.md)
  
[<span data-ttu-id="311d2-194">PidTagMessageAttachments 规范属性</span><span class="sxs-lookup"><span data-stu-id="311d2-194">PidTagMessageAttachments Canonical Property</span></span>](pidtagmessageattachments-canonical-property.md)
  
[<span data-ttu-id="311d2-195">PidTagMessageRecipients 规范属性</span><span class="sxs-lookup"><span data-stu-id="311d2-195">PidTagMessageRecipients Canonical Property</span></span>](pidtagmessagerecipients-canonical-property.md)
  
[<span data-ttu-id="311d2-196">SPropProblemArray</span><span class="sxs-lookup"><span data-stu-id="311d2-196">SPropProblemArray</span></span>](spropproblemarray.md)
  
[<span data-ttu-id="311d2-197">SPropTagArray</span><span class="sxs-lookup"><span data-stu-id="311d2-197">SPropTagArray</span></span>](sproptagarray.md)
  
[<span data-ttu-id="311d2-198">IMAPISupport : IUnknown</span><span class="sxs-lookup"><span data-stu-id="311d2-198">IMAPISupport : IUnknown</span></span>](imapisupportiunknown.md)

