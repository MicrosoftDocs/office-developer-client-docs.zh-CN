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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: a30a323874c847d9a08b00512cfd30ff3cf5c5ff
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22591126"
---
# <a name="imapisupportdocopyprops"></a><span data-ttu-id="1c290-103">IMAPISupport::DoCopyProps</span><span class="sxs-lookup"><span data-stu-id="1c290-103">IMAPISupport::DoCopyProps</span></span>

  
  
<span data-ttu-id="1c290-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="1c290-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="1c290-105">复制或移动到另一个对象的一个或多个对象的属性。</span><span class="sxs-lookup"><span data-stu-id="1c290-105">Copies or moves one or more properties of an object to another object.</span></span>
  
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

## <a name="parameters"></a><span data-ttu-id="1c290-106">参数</span><span class="sxs-lookup"><span data-stu-id="1c290-106">Parameters</span></span>

 <span data-ttu-id="1c290-107">_lpSrcInterface_</span><span class="sxs-lookup"><span data-stu-id="1c290-107">_lpSrcInterface_</span></span>
  
> <span data-ttu-id="1c290-108">[in]指向接口标识 (IID) 值，该值代表要用于访问对象的属性复制或移动的接口的指针。</span><span class="sxs-lookup"><span data-stu-id="1c290-108">[in] A pointer to the interface identifier (IID) that represents the interface to be used to access the object with the properties to be copied or moved.</span></span>
    
 <span data-ttu-id="1c290-109">_lpSrcObj_</span><span class="sxs-lookup"><span data-stu-id="1c290-109">_lpSrcObj_</span></span>
  
> <span data-ttu-id="1c290-110">[in]指向包含属性复制或移动的对象的指针。</span><span class="sxs-lookup"><span data-stu-id="1c290-110">[in] A pointer to the object that contains the properties to be copied or moved.</span></span>
    
 <span data-ttu-id="1c290-111">_lpIncludeProps_</span><span class="sxs-lookup"><span data-stu-id="1c290-111">_lpIncludeProps_</span></span>
  
> <span data-ttu-id="1c290-112">[in]指向[SPropTagArray](sproptagarray.md)结构，其中包含指示要复制或移动的属性的属性标记的计数的阵列的指针。</span><span class="sxs-lookup"><span data-stu-id="1c290-112">[in] A pointer to an [SPropTagArray](sproptagarray.md) structure that contains a counted array of property tags that indicate the properties to copy or move.</span></span> <span data-ttu-id="1c290-113">_LpIncludeProps_参数不能为 NULL。</span><span class="sxs-lookup"><span data-stu-id="1c290-113">The  _lpIncludeProps_ parameter cannot be NULL.</span></span> 
    
 <span data-ttu-id="1c290-114">_ulUIParam_</span><span class="sxs-lookup"><span data-stu-id="1c290-114">_ulUIParam_</span></span>
  
> <span data-ttu-id="1c290-115">[in]进度指示器的父窗口句柄。</span><span class="sxs-lookup"><span data-stu-id="1c290-115">[in] A handle to the parent window of the progress indicator.</span></span>
    
 <span data-ttu-id="1c290-116">_lpProgress_</span><span class="sxs-lookup"><span data-stu-id="1c290-116">_lpProgress_</span></span>
  
> <span data-ttu-id="1c290-117">[in]一个指向进度指示器的实现。</span><span class="sxs-lookup"><span data-stu-id="1c290-117">[in] A pointer to an implementation of a progress indicator.</span></span> <span data-ttu-id="1c290-118">如果_lpProgress_参数中传递 NULL，则是通过使用 MAPI 实现显示进度指示器。</span><span class="sxs-lookup"><span data-stu-id="1c290-118">If NULL is passed in the  _lpProgress_ parameter, the progress indicator is displayed by using the MAPI implementation.</span></span> <span data-ttu-id="1c290-119">除非 MAPI_DIALOG 标志设置_ulFlags_参数中，将忽略该_lpProgress_参数。</span><span class="sxs-lookup"><span data-stu-id="1c290-119">The  _lpProgress_ parameter is ignored unless the MAPI_DIALOG flag is set in the  _ulFlags_ parameter.</span></span> 
    
 <span data-ttu-id="1c290-120">_lpDestInterface_</span><span class="sxs-lookup"><span data-stu-id="1c290-120">_lpDestInterface_</span></span>
  
> <span data-ttu-id="1c290-121">[in]指向接口标识符值，该值代表要用于访问对象，以接收属性的复制或移动的接口的指针。</span><span class="sxs-lookup"><span data-stu-id="1c290-121">[in] A pointer to the interface identifier that represents the interface to be used to access the object to receive the properties that are copied or moved.</span></span>
    
 <span data-ttu-id="1c290-122">_lpDestObj_</span><span class="sxs-lookup"><span data-stu-id="1c290-122">_lpDestObj_</span></span>
  
> <span data-ttu-id="1c290-123">[in]指向要接收复制或移动属性的对象的指针。</span><span class="sxs-lookup"><span data-stu-id="1c290-123">[in] A pointer to the object to receive the copied or moved properties.</span></span>
    
 <span data-ttu-id="1c290-124">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="1c290-124">_ulFlags_</span></span>
  
> <span data-ttu-id="1c290-125">[in]位掩码的标志，控制如何执行复制或移动操作。</span><span class="sxs-lookup"><span data-stu-id="1c290-125">[in] A bitmask of flags that controls how the copy or move operation is performed.</span></span> <span data-ttu-id="1c290-126">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="1c290-126">The following flags can be set:</span></span>
    
<span data-ttu-id="1c290-127">MAPI_DIALOG</span><span class="sxs-lookup"><span data-stu-id="1c290-127">MAPI_DIALOG</span></span> 
  
> <span data-ttu-id="1c290-128">显示进度指示器。</span><span class="sxs-lookup"><span data-stu-id="1c290-128">Displays a progress indicator.</span></span>
    
<span data-ttu-id="1c290-129">MAPI_MOVE</span><span class="sxs-lookup"><span data-stu-id="1c290-129">MAPI_MOVE</span></span> 
  
> <span data-ttu-id="1c290-130">**DoCopyProps**应执行移动操作而不是复制操作。</span><span class="sxs-lookup"><span data-stu-id="1c290-130">**DoCopyProps** should perform a move operation instead of a copy operation.</span></span> <span data-ttu-id="1c290-131">当未设置此标志时， **DoCopyProps**执行复制操作。</span><span class="sxs-lookup"><span data-stu-id="1c290-131">When this flag is not set, **DoCopyProps** performs a copy operation.</span></span> 
    
<span data-ttu-id="1c290-132">MAPI_NOREPLACE</span><span class="sxs-lookup"><span data-stu-id="1c290-132">MAPI_NOREPLACE</span></span> 
  
> <span data-ttu-id="1c290-133">不应覆盖目标对象中的现有属性。</span><span class="sxs-lookup"><span data-stu-id="1c290-133">Existing properties in the destination object should not be overwritten.</span></span> <span data-ttu-id="1c290-134">如果未设置此标志， **DoCopyProps**会覆盖现有属性。</span><span class="sxs-lookup"><span data-stu-id="1c290-134">When this flag is not set, **DoCopyProps** overwrites existing properties.</span></span> 
    
 <span data-ttu-id="1c290-135">_lppProblems_</span><span class="sxs-lookup"><span data-stu-id="1c290-135">_lppProblems_</span></span>
  
> <span data-ttu-id="1c290-136">[传入、 传出]在输入时，为[SPropProblemArray](spropproblemarray.md)结构; 指针的指针否则，为 NULL，表示不需要错误信息。</span><span class="sxs-lookup"><span data-stu-id="1c290-136">[in, out] On input, a pointer to a pointer to an [SPropProblemArray](spropproblemarray.md) structure; otherwise, NULL, which indicates no need for error information.</span></span> <span data-ttu-id="1c290-137">如果_lppProblems_上输入, 的有效指针**DoCopyProps**中复制一个或多个属性返回有关错误的详细的信息。</span><span class="sxs-lookup"><span data-stu-id="1c290-137">If  _lppProblems_ is a valid pointer on input, **DoCopyProps** returns detailed information about errors in copying one or more properties.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="1c290-138">返回值</span><span class="sxs-lookup"><span data-stu-id="1c290-138">Return value</span></span>

<span data-ttu-id="1c290-139">S_OK</span><span class="sxs-lookup"><span data-stu-id="1c290-139">S_OK</span></span> 
  
> <span data-ttu-id="1c290-140">属性已成功复制或移动。</span><span class="sxs-lookup"><span data-stu-id="1c290-140">Properties were successfully copied or moved.</span></span>
    
<span data-ttu-id="1c290-141">MAPI_E_COLLISION</span><span class="sxs-lookup"><span data-stu-id="1c290-141">MAPI_E_COLLISION</span></span> 
  
> <span data-ttu-id="1c290-142">对目标对象中存在要复制或已移动的属性并且设置 MAPI_NOREPLACE 标志。</span><span class="sxs-lookup"><span data-stu-id="1c290-142">A property to be copied or moved already exists in the destination object and the MAPI_NOREPLACE flag is set.</span></span> 
    
<span data-ttu-id="1c290-143">MAPI_E_FOLDER_CYCLE</span><span class="sxs-lookup"><span data-stu-id="1c290-143">MAPI_E_FOLDER_CYCLE</span></span> 
  
> <span data-ttu-id="1c290-144">源对象直接或间接包含对目标对象。</span><span class="sxs-lookup"><span data-stu-id="1c290-144">The source object directly or indirectly contains the destination object.</span></span> <span data-ttu-id="1c290-145">重要工作可能已执行之前已发现这种情况，所以可能部分修改的源和目标对象。</span><span class="sxs-lookup"><span data-stu-id="1c290-145">Significant work might have been performed before this condition was discovered, so the source and destination objects might be partially modified.</span></span> 
    
<span data-ttu-id="1c290-146">MAPI_E_INTERFACE_NOT_SUPPORTED</span><span class="sxs-lookup"><span data-stu-id="1c290-146">MAPI_E_INTERFACE_NOT_SUPPORTED</span></span> 
  
> <span data-ttu-id="1c290-147">_LpSrcInterface_参数标识的接口不支持的源对象，或对目标对象不支持_lpDestInterface_参数标识的接口。</span><span class="sxs-lookup"><span data-stu-id="1c290-147">The interface identified by the  _lpSrcInterface_ parameter is not supported by the source object, or the interface identified by the  _lpDestInterface_ parameter is not supported by the destination object.</span></span> 
    
<span data-ttu-id="1c290-148">MAPI_E_NO_ACCESS</span><span class="sxs-lookup"><span data-stu-id="1c290-148">MAPI_E_NO_ACCESS</span></span> 
  
> <span data-ttu-id="1c290-149">尝试访问其呼叫者没有足够的权限的对象。</span><span class="sxs-lookup"><span data-stu-id="1c290-149">An attempt was made to access an object for which the caller has insufficient permissions.</span></span> <span data-ttu-id="1c290-150">如果目标对象是对源对象相同，则返回此错误。</span><span class="sxs-lookup"><span data-stu-id="1c290-150">This error is returned if the destination object is the same as the source object.</span></span>
    
<span data-ttu-id="1c290-151">可以为**DoCopyProps**中返回在**SPropProblemArray**结构中，但不是返回值是以下值。</span><span class="sxs-lookup"><span data-stu-id="1c290-151">The following values can be returned in the **SPropProblemArray** structure, but not as return values for **DoCopyProps**.</span></span> <span data-ttu-id="1c290-152">这些错误应用于单个属性。</span><span class="sxs-lookup"><span data-stu-id="1c290-152">These errors apply to a single property.</span></span>
  
<span data-ttu-id="1c290-153">MAPI_E_BAD_CHARWIDTH</span><span class="sxs-lookup"><span data-stu-id="1c290-153">MAPI_E_BAD_CHARWIDTH</span></span> 
  
> <span data-ttu-id="1c290-154">可以设置该 MAPI_UNICODE 标记**DoCopyProps**不支持 Unicode，或未设置 MAPI_UNICODE 和**DoCopyProps**支持仅 Unicode。</span><span class="sxs-lookup"><span data-stu-id="1c290-154">Either the MAPI_UNICODE flag was set and **DoCopyProps** does not support Unicode, or MAPI_UNICODE was not set and **DoCopyProps** supports only Unicode.</span></span> 
    
<span data-ttu-id="1c290-155">MAPI_E_COMPUTED</span><span class="sxs-lookup"><span data-stu-id="1c290-155">MAPI_E_COMPUTED</span></span> 
  
> <span data-ttu-id="1c290-156">该属性不能修改呼叫者，因为它是只读属性，计算目标对象的所有者。</span><span class="sxs-lookup"><span data-stu-id="1c290-156">The property cannot be modified by the caller because it is a read-only property, computed by the owner of the destination object.</span></span> <span data-ttu-id="1c290-157">此错误不是严重性。呼叫者应允许复制操作继续。</span><span class="sxs-lookup"><span data-stu-id="1c290-157">This error is not severe; the caller should allow the copy operation to continue.</span></span>
    
<span data-ttu-id="1c290-158">MAPI_E_INVALID_TYPE</span><span class="sxs-lookup"><span data-stu-id="1c290-158">MAPI_E_INVALID_TYPE</span></span> 
  
> <span data-ttu-id="1c290-159">属性类型无效。</span><span class="sxs-lookup"><span data-stu-id="1c290-159">The property type is invalid.</span></span>
    
<span data-ttu-id="1c290-160">MAPI_E_UNEXPECTED_TYPE</span><span class="sxs-lookup"><span data-stu-id="1c290-160">MAPI_E_UNEXPECTED_TYPE</span></span> 
  
> <span data-ttu-id="1c290-161">属性类型不是呼叫者预期的类型。</span><span class="sxs-lookup"><span data-stu-id="1c290-161">The property type is not the type that the caller expects.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="1c290-162">注解</span><span class="sxs-lookup"><span data-stu-id="1c290-162">Remarks</span></span>

<span data-ttu-id="1c290-163">消息存储提供程序支持对象的实现**IMAPISupport::DoCopyProps**方法。</span><span class="sxs-lookup"><span data-stu-id="1c290-163">The **IMAPISupport::DoCopyProps** method is implemented for message store provider support objects.</span></span> <span data-ttu-id="1c290-164">消息存储提供程序可以调用**DoCopyProps**实现其文件夹和邮件的[IMAPIProp::CopyProps](imapiprop-copyprops.md)方法。</span><span class="sxs-lookup"><span data-stu-id="1c290-164">Message store providers can call **DoCopyProps** to implement the [IMAPIProp::CopyProps](imapiprop-copyprops.md) method for their folders and messages.</span></span> <span data-ttu-id="1c290-165">**DoCopyProps**复制或移动的属性所指的_lpIncludeProps_属性标记数组中的标识和指向_lpSrcObj_对象中当前存在。</span><span class="sxs-lookup"><span data-stu-id="1c290-165">**DoCopyProps** copies or moves the properties that are identified in the property tag array pointed to by  _lpIncludeProps_ and that are present in the object pointed to by  _lpSrcObj_.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="1c290-166">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="1c290-166">Notes to callers</span></span>

<span data-ttu-id="1c290-167">复制之间的相同的类型，两条消息，如对象的属性时的_lpSrcInterface_和_lpDestInterface_参数必须包含相同的界面标识符，以及_lpSrcObj_和_lpDestObj_参数必须指向同一类型的对象。</span><span class="sxs-lookup"><span data-stu-id="1c290-167">When you copy properties between objects of the same type, such as two messages, the  _lpSrcInterface_ and  _lpDestInterface_ parameters must contain the same interface identifier, and the  _lpSrcObj_ and  _lpDestObj_ parameters must point to objects of the same type.</span></span> <span data-ttu-id="1c290-168">如果_lpDestInterface_设置为 NULL，则**DoCopyProps**返回 MAPI_E_INVALID_PARAMETER。</span><span class="sxs-lookup"><span data-stu-id="1c290-168">If  _lpDestInterface_ is set to NULL, **DoCopyProps** returns MAPI_E_INVALID_PARAMETER.</span></span> <span data-ttu-id="1c290-169">如果您将_lpDestInterface_设置为可接受的界面标识符，但设置_lpDestObj_到了无效的指针，结果将无法预料。</span><span class="sxs-lookup"><span data-stu-id="1c290-169">If you set  _lpDestInterface_ to an acceptable interface identifier, but set  _lpDestObj_ to an invalid pointer, the results are unpredictable.</span></span> <span data-ttu-id="1c290-170">很可能将失败提供程序。</span><span class="sxs-lookup"><span data-stu-id="1c290-170">Most likely your provider will fail.</span></span> 
  
<span data-ttu-id="1c290-171">如果您不希望任何目的对象将覆盖的属性，请设置 MAPI_NOREPLACE 标志。</span><span class="sxs-lookup"><span data-stu-id="1c290-171">Set the MAPI_NOREPLACE flag if you do not want any of the properties in the destination object to be overwritten.</span></span> <span data-ttu-id="1c290-172">对目标对象中的源对象中存在的且不会被覆盖的属性不被删除或修改。</span><span class="sxs-lookup"><span data-stu-id="1c290-172">Properties in the destination object that exist in the source object and are not overwritten are not deleted or modified.</span></span>
  
<span data-ttu-id="1c290-173">要复制邮件的收件人列表，请_lpIncludeProps_参数指向该属性标记数组中包含的**PR_MESSAGE_RECIPIENTS** ([PidTagMessageRecipients](pidtagmessagerecipients-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="1c290-173">To copy a message's recipient list, include the **PR_MESSAGE_RECIPIENTS** ([PidTagMessageRecipients](pidtagmessagerecipients-canonical-property.md)) property in the property tag array pointed to by the  _lpIncludeProps_ parameter.</span></span> <span data-ttu-id="1c290-174">若要复制邮件的附件，包括**PR_MESSAGE_ATTACHMENTS** ([PidTagMessageAttachments](pidtagmessageattachments-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="1c290-174">To copy the message's attachments, include the **PR_MESSAGE_ATTACHMENTS** ([PidTagMessageAttachments](pidtagmessageattachments-canonical-property.md)) property.</span></span> 
  
<span data-ttu-id="1c290-175">若要复制的文件夹或通讯簿容器层次结构或内容表，包括属性标记数组中的**PR_CONTAINER_HIERARCHY** ([PidTagContainerHierarchy](pidtagcontainerhierarchy-canonical-property.md)) 或**PR_CONTAINER_CONTENTS** ([PidTagContainerContents](pidtagcontainercontents-canonical-property.md))。</span><span class="sxs-lookup"><span data-stu-id="1c290-175">To copy a folder or address book container's hierarchy or contents table, include **PR_CONTAINER_HIERARCHY** ([PidTagContainerHierarchy](pidtagcontainerhierarchy-canonical-property.md)) or **PR_CONTAINER_CONTENTS** ([PidTagContainerContents](pidtagcontainercontents-canonical-property.md)) in the property tag array.</span></span> <span data-ttu-id="1c290-176">若要包含的文件夹关联的内容表，该数组中包括**PR_FOLDER_ASSOCIATED_CONTENTS** ([PidTagFolderAssociatedContents](pidtagfolderassociatedcontents-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="1c290-176">To include a folder's associated contents table, include the **PR_FOLDER_ASSOCIATED_CONTENTS** ([PidTagFolderAssociatedContents](pidtagfolderassociatedcontents-canonical-property.md)) property in the array.</span></span>
  
<span data-ttu-id="1c290-177">如果复制或移动的子文件夹，及其内容复制或移动全部，无论使用了由**SPropTagArray**结构指示的属性。</span><span class="sxs-lookup"><span data-stu-id="1c290-177">If subfolders are copied or moved, their contents are copied or moved in their entirety, regardless of the use of properties indicated by the **SPropTagArray** structure.</span></span> 
  
 <span data-ttu-id="1c290-178">**DoCopyProps**报告全局作为一个整体，操作发生的错误和各个错误出现的一个或多个属性。</span><span class="sxs-lookup"><span data-stu-id="1c290-178">**DoCopyProps** reports global errors that occur with the operation as a whole, and individual errors that occur with one or more of the properties.</span></span> <span data-ttu-id="1c290-179">这些单个错误保持**SPropProblemArray**结构中。</span><span class="sxs-lookup"><span data-stu-id="1c290-179">These individual errors are put in an **SPropProblemArray** structure.</span></span> <span data-ttu-id="1c290-180">您可以隐藏错误属性级别通过传递 NULL，而不是有效的指针，property 问题数组结构参数的报告。</span><span class="sxs-lookup"><span data-stu-id="1c290-180">You can suppress error reporting at the property level by passing NULL, rather than a valid pointer, for the property problem array structure parameter.</span></span> 
  
<span data-ttu-id="1c290-181">如果您想要接收有关错误的信息，请在_lppProblems_参数中传递一个有效的**SPropProblemArray**结构指针。</span><span class="sxs-lookup"><span data-stu-id="1c290-181">If you want to receive information about errors, pass a valid **SPropProblemArray** structure pointer in the  _lppProblems_ parameter.</span></span> <span data-ttu-id="1c290-182">时**DoCopyProps** ，则返回 S_OK，检查与结构中的各个属性的可能错误。</span><span class="sxs-lookup"><span data-stu-id="1c290-182">When **DoCopyProps** returns S_OK, check for possible errors with individual properties in the structure.</span></span> <span data-ttu-id="1c290-183">当**DoCopyProps**返回错误时， **SPropProblemArray**结构中不返回任何信息。</span><span class="sxs-lookup"><span data-stu-id="1c290-183">When **DoCopyProps** returns an error, no information is returned in the **SPropProblemArray** structure.</span></span> <span data-ttu-id="1c290-184">相反，调用[IMAPISupport::GetLastError](imapisupport-getlasterror.md)方法检索详细的错误信息。</span><span class="sxs-lookup"><span data-stu-id="1c290-184">Instead, call the [IMAPISupport::GetLastError](imapisupport-getlasterror.md) method to retrieve detailed error information.</span></span> 
  
<span data-ttu-id="1c290-185">如果**DoCopyProps** ，则返回 S_OK，通过调用[MAPIFreeBuffer](mapifreebuffer.md)函数释放返回的**SPropProblemArray**结构。</span><span class="sxs-lookup"><span data-stu-id="1c290-185">If **DoCopyProps** returns S_OK, free the returned **SPropProblemArray** structure by calling the [MAPIFreeBuffer](mapifreebuffer.md) function.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="1c290-186">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1c290-186">See also</span></span>



[<span data-ttu-id="1c290-187">IMAPIProp::CopyProps</span><span class="sxs-lookup"><span data-stu-id="1c290-187">IMAPIProp::CopyProps</span></span>](imapiprop-copyprops.md)
  
[<span data-ttu-id="1c290-188">IMAPISupport::CopyMessages</span><span class="sxs-lookup"><span data-stu-id="1c290-188">IMAPISupport::CopyMessages</span></span>](imapisupport-copymessages.md)
  
[<span data-ttu-id="1c290-189">IMAPISupport::DoCopyTo</span><span class="sxs-lookup"><span data-stu-id="1c290-189">IMAPISupport::DoCopyTo</span></span>](imapisupport-docopyto.md)
  
[<span data-ttu-id="1c290-190">IMAPISupport::GetLastError</span><span class="sxs-lookup"><span data-stu-id="1c290-190">IMAPISupport::GetLastError</span></span>](imapisupport-getlasterror.md)
  
[<span data-ttu-id="1c290-191">PidTagContainerContents 规范属性</span><span class="sxs-lookup"><span data-stu-id="1c290-191">PidTagContainerContents Canonical Property</span></span>](pidtagcontainercontents-canonical-property.md)
  
[<span data-ttu-id="1c290-192">PidTagContainerHierarchy 规范属性</span><span class="sxs-lookup"><span data-stu-id="1c290-192">PidTagContainerHierarchy Canonical Property</span></span>](pidtagcontainerhierarchy-canonical-property.md)
  
[<span data-ttu-id="1c290-193">PidTagFolderAssociatedContents 规范属性</span><span class="sxs-lookup"><span data-stu-id="1c290-193">PidTagFolderAssociatedContents Canonical Property</span></span>](pidtagfolderassociatedcontents-canonical-property.md)
  
[<span data-ttu-id="1c290-194">PidTagMessageAttachments 规范属性</span><span class="sxs-lookup"><span data-stu-id="1c290-194">PidTagMessageAttachments Canonical Property</span></span>](pidtagmessageattachments-canonical-property.md)
  
[<span data-ttu-id="1c290-195">PidTagMessageRecipients 规范属性</span><span class="sxs-lookup"><span data-stu-id="1c290-195">PidTagMessageRecipients Canonical Property</span></span>](pidtagmessagerecipients-canonical-property.md)
  
[<span data-ttu-id="1c290-196">SPropProblemArray</span><span class="sxs-lookup"><span data-stu-id="1c290-196">SPropProblemArray</span></span>](spropproblemarray.md)
  
[<span data-ttu-id="1c290-197">SPropTagArray</span><span class="sxs-lookup"><span data-stu-id="1c290-197">SPropTagArray</span></span>](sproptagarray.md)
  
[<span data-ttu-id="1c290-198">IMAPISupport : IUnknown</span><span class="sxs-lookup"><span data-stu-id="1c290-198">IMAPISupport : IUnknown</span></span>](imapisupportiunknown.md)

