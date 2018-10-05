---
title: IMAPISupportDoCopyTo
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISupport.DoCopyTo
api_type:
- COM
ms.assetid: 84019475-5176-4fc5-a3ee-871095077498
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 6f6c802f1d5ead1750c05fafc54533487fe3732a
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25390630"
---
# <a name="imapisupportdocopyto"></a><span data-ttu-id="92775-103">IMAPISupport::DoCopyTo</span><span class="sxs-lookup"><span data-stu-id="92775-103">IMAPISupport::DoCopyTo</span></span>

  
  
<span data-ttu-id="92775-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="92775-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="92775-105">复制或移动到另一个对象的一个对象，特别是排除的属性，除外的所有属性。</span><span class="sxs-lookup"><span data-stu-id="92775-105">Copies or moves all properties of one object, except for specifically excluded properties, to another object.</span></span>
  
```cpp
HRESULT DoCopyTo(
  LPCIID lpSrcInterface,
  LPVOID lpSrcObj,
  ULONG ciidExclude,
  LPCIID rgiidExclude,
  LPSPropTagArray lpExcludeProps,
  ULONG_PTR ulUIParam,
  LPMAPIPROGRESS lpProgress,
  LPCIID lpDestInterface,
  LPVOID lpDestObj,
  ULONG ulFlags,
  LPSPropProblemArray FAR * lppProblems
);
```

## <a name="parameters"></a><span data-ttu-id="92775-106">参数</span><span class="sxs-lookup"><span data-stu-id="92775-106">Parameters</span></span>

 <span data-ttu-id="92775-107">_lpSrcInterface_</span><span class="sxs-lookup"><span data-stu-id="92775-107">_lpSrcInterface_</span></span>
  
> <span data-ttu-id="92775-108">[in]指向接口标识 (IID) 值，该值代表要用于访问具有要复制或移动的属性的对象的接口的指针。</span><span class="sxs-lookup"><span data-stu-id="92775-108">[in] A pointer to the interface identifier (IID) that represents the interface to be used to access the object that has the properties to be copied or moved.</span></span>
    
 <span data-ttu-id="92775-109">_lpSrcObj_</span><span class="sxs-lookup"><span data-stu-id="92775-109">_lpSrcObj_</span></span>
  
> <span data-ttu-id="92775-110">[in]指向具有要复制或移动的属性的对象的指针。</span><span class="sxs-lookup"><span data-stu-id="92775-110">[in] A pointer to the object that has the properties to be copied or moved.</span></span>
    
 <span data-ttu-id="92775-111">_ciidExclude_</span><span class="sxs-lookup"><span data-stu-id="92775-111">_ciidExclude_</span></span>
  
> <span data-ttu-id="92775-112">[in]复制或移动属性时要排除的接口的计数。</span><span class="sxs-lookup"><span data-stu-id="92775-112">[in] The count of interfaces to exclude when you copy or move properties.</span></span>
    
 <span data-ttu-id="92775-113">_rgiidExclude_</span><span class="sxs-lookup"><span data-stu-id="92775-113">_rgiidExclude_</span></span>
  
> <span data-ttu-id="92775-114">[in]指示当您复制或移动到的目标对象的附加信息不应使用的接口的接口标识符数组。</span><span class="sxs-lookup"><span data-stu-id="92775-114">[in] An array of interface identifiers that indicates interfaces that should not be used when you copy or move supplemental information to the destination object.</span></span>
    
 <span data-ttu-id="92775-115">_lpExcludeProps_</span><span class="sxs-lookup"><span data-stu-id="92775-115">_lpExcludeProps_</span></span>
  
> <span data-ttu-id="92775-116">[in]指向属性标记数组，标识属性标记的应排除从副本或移动操作的指针。</span><span class="sxs-lookup"><span data-stu-id="92775-116">[in] A pointer to a property tag array that identifies the property tags that should be excluded from the copy or move operation.</span></span> <span data-ttu-id="92775-117">_LpExcludeProps_参数中传递 NULL 指示所有对象的属性应该可以复制或移动。</span><span class="sxs-lookup"><span data-stu-id="92775-117">Passing NULL in the  _lpExcludeProps_ parameter indicates that all of the object's properties should be copied or moved.</span></span> <span data-ttu-id="92775-118">**DoCopyTo**返回 MAPI_E_INVALID_PARAMETER [SPropTagArray](sproptagarray.md)结构的**cValues**成员所指的_lpExcludeProps_时设置为 0。</span><span class="sxs-lookup"><span data-stu-id="92775-118">**DoCopyTo** returns MAPI_E_INVALID_PARAMETER when the **cValues** member of the [SPropTagArray](sproptagarray.md) structure pointed to by  _lpExcludeProps_ is set to 0.</span></span> 
    
 <span data-ttu-id="92775-119">_ulUIParam_</span><span class="sxs-lookup"><span data-stu-id="92775-119">_ulUIParam_</span></span>
  
> <span data-ttu-id="92775-120">[in]进度指示器的父窗口句柄。</span><span class="sxs-lookup"><span data-stu-id="92775-120">[in] A handle to the parent window of the progress indicator.</span></span> 
    
 <span data-ttu-id="92775-121">_lpProgress_</span><span class="sxs-lookup"><span data-stu-id="92775-121">_lpProgress_</span></span>
  
> <span data-ttu-id="92775-122">[in]指向进度指示器实现的指针。</span><span class="sxs-lookup"><span data-stu-id="92775-122">[in] A pointer to a progress indicator implementation.</span></span> <span data-ttu-id="92775-123">如果_lpProgress_参数中传递 NULL，则 MAPI 提供进度实现。</span><span class="sxs-lookup"><span data-stu-id="92775-123">If NULL is passed in the  _lpProgress_ parameter, MAPI provides the progress implementation.</span></span> <span data-ttu-id="92775-124">除非 MAPI_DIALOG 标志设置_ulFlags_参数中，将忽略该_lpProgress_参数。</span><span class="sxs-lookup"><span data-stu-id="92775-124">The  _lpProgress_ parameter is ignored unless the MAPI_DIALOG flag is set in the  _ulFlags_ parameter.</span></span> 
    
 <span data-ttu-id="92775-125">_lpDestInterface_</span><span class="sxs-lookup"><span data-stu-id="92775-125">_lpDestInterface_</span></span>
  
> <span data-ttu-id="92775-126">[in]指向接口标识符值，该值代表要用于访问对象，以接收复制或移动属性的接口的指针。</span><span class="sxs-lookup"><span data-stu-id="92775-126">[in] A pointer to the interface identifier that represents the interface to be used to access the object to receive the copied or moved properties.</span></span>
    
 <span data-ttu-id="92775-127">_lpDestObj_</span><span class="sxs-lookup"><span data-stu-id="92775-127">_lpDestObj_</span></span>
  
> <span data-ttu-id="92775-128">[in]指向要接收复制或移动属性的对象的指针。</span><span class="sxs-lookup"><span data-stu-id="92775-128">[in] A pointer to the object to receive the copied or moved properties.</span></span>
    
 <span data-ttu-id="92775-129">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="92775-129">_ulFlags_</span></span>
  
> <span data-ttu-id="92775-130">[in]位掩码的标志，用于控制复制或移动操作。</span><span class="sxs-lookup"><span data-stu-id="92775-130">[in] A bitmask of flags that controls the copy or move operation.</span></span> <span data-ttu-id="92775-131">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="92775-131">The following flags can be set:</span></span>
    
<span data-ttu-id="92775-132">MAPI_DIALOG</span><span class="sxs-lookup"><span data-stu-id="92775-132">MAPI_DIALOG</span></span> 
  
> <span data-ttu-id="92775-133">显示进度指示器。</span><span class="sxs-lookup"><span data-stu-id="92775-133">Displays a progress indicator.</span></span> 
    
<span data-ttu-id="92775-134">MAPI_MOVE</span><span class="sxs-lookup"><span data-stu-id="92775-134">MAPI_MOVE</span></span> 
  
> <span data-ttu-id="92775-135">**DoCopyTo**应执行移动操作而不是复制操作。</span><span class="sxs-lookup"><span data-stu-id="92775-135">**DoCopyTo** should perform a move operation instead of a copy operation.</span></span> <span data-ttu-id="92775-136">当未设置此标志时， **DoCopyTo**执行复制操作。</span><span class="sxs-lookup"><span data-stu-id="92775-136">When this flag is not set, **DoCopyTo** performs a copy operation.</span></span> 
    
<span data-ttu-id="92775-137">MAPI_NOREPLACE</span><span class="sxs-lookup"><span data-stu-id="92775-137">MAPI_NOREPLACE</span></span> 
  
> <span data-ttu-id="92775-138">不应覆盖目标对象中的现有属性。</span><span class="sxs-lookup"><span data-stu-id="92775-138">Existing properties in the destination object should not be overwritten.</span></span> <span data-ttu-id="92775-139">如果未设置此标志， **DoCopyTo**会覆盖现有属性。</span><span class="sxs-lookup"><span data-stu-id="92775-139">When this flag is not set, **DoCopyTo** overwrites existing properties.</span></span> 
    
 <span data-ttu-id="92775-140">_lppProblems_</span><span class="sxs-lookup"><span data-stu-id="92775-140">_lppProblems_</span></span>
  
> <span data-ttu-id="92775-141">[输出]在输入时，为[SPropProblemArray](spropproblemarray.md)结构; 指针的指针否则，为 NULL，表示不需要错误信息。</span><span class="sxs-lookup"><span data-stu-id="92775-141">[out] On input, a pointer to a pointer to an [SPropProblemArray](spropproblemarray.md) structure; otherwise, NULL, which indicates no need for error information.</span></span> <span data-ttu-id="92775-142">如果_lppProblems_上输入, 的有效指针**DoCopyTo**中复制一个或多个属性返回有关错误的详细的信息。</span><span class="sxs-lookup"><span data-stu-id="92775-142">If  _lppProblems_ is a valid pointer on input, **DoCopyTo** returns detailed information about errors in copying one or more properties.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="92775-143">返回值</span><span class="sxs-lookup"><span data-stu-id="92775-143">Return value</span></span>

<span data-ttu-id="92775-144">S_OK</span><span class="sxs-lookup"><span data-stu-id="92775-144">S_OK</span></span> 
  
> <span data-ttu-id="92775-145">属性已成功复制或移动。</span><span class="sxs-lookup"><span data-stu-id="92775-145">The properties have been successfully copied or moved.</span></span>
    
<span data-ttu-id="92775-146">MAPI_E_COLLISION</span><span class="sxs-lookup"><span data-stu-id="92775-146">MAPI_E_COLLISION</span></span> 
  
> <span data-ttu-id="92775-147">对目标对象中存在要复制或已移动的属性并且设置 MAPI_NOREPLACE 标志。</span><span class="sxs-lookup"><span data-stu-id="92775-147">A property to be copied or moved already exists in the destination object and the MAPI_NOREPLACE flag is set.</span></span> 
    
<span data-ttu-id="92775-148">MAPI_E_FOLDER_CYCLE</span><span class="sxs-lookup"><span data-stu-id="92775-148">MAPI_E_FOLDER_CYCLE</span></span> 
  
> <span data-ttu-id="92775-149">源对象直接或间接包含对目标对象。</span><span class="sxs-lookup"><span data-stu-id="92775-149">The source object directly or indirectly contains the destination object.</span></span> <span data-ttu-id="92775-150">重要工作可能已执行之前已发现这种情况，所以可能部分修改的源和目标对象。</span><span class="sxs-lookup"><span data-stu-id="92775-150">Significant work might have been performed before this condition was discovered, so the source and destination objects might be partially modified.</span></span> 
    
<span data-ttu-id="92775-151">MAPI_E_INTERFACE_NOT_SUPPORTED</span><span class="sxs-lookup"><span data-stu-id="92775-151">MAPI_E_INTERFACE_NOT_SUPPORTED</span></span> 
  
> <span data-ttu-id="92775-152">指向_lpSrcObj_，对象不支持_lpSrcInterface_参数标识的接口或指向_lpDestObj 对象不支持_lpDestInterface_参数标识的接口_.</span><span class="sxs-lookup"><span data-stu-id="92775-152">The interface identified by the  _lpSrcInterface_ parameter is not supported by the object pointed to by  _lpSrcObj_, or the interface identified by the  _lpDestInterface_ parameter is not supported by the object pointed to by  _lpDestObj_.</span></span> 
    
<span data-ttu-id="92775-153">MAPI_E_NO_ACCESS</span><span class="sxs-lookup"><span data-stu-id="92775-153">MAPI_E_NO_ACCESS</span></span> 
  
> <span data-ttu-id="92775-154">尝试访问其呼叫者没有足够的权限的对象。</span><span class="sxs-lookup"><span data-stu-id="92775-154">An attempt was made to access an object for which the caller has insufficient permissions.</span></span> <span data-ttu-id="92775-155">如果目标对象是对源对象相同，则返回此错误。</span><span class="sxs-lookup"><span data-stu-id="92775-155">This error is returned if the destination object is the same as the source object.</span></span>
    
<span data-ttu-id="92775-156">MAPI_E_INVALID_PARAMETER</span><span class="sxs-lookup"><span data-stu-id="92775-156">MAPI_E_INVALID_PARAMETER</span></span> 
  
> <span data-ttu-id="92775-157">_LpSrcInterface_参数为 NULL。</span><span class="sxs-lookup"><span data-stu-id="92775-157">The  _lpSrcInterface_ parameter is NULL.</span></span> 
    
<span data-ttu-id="92775-158">可以为**DoCopyTo**中返回在**SPropProblemArray**结构中，但不是返回值是以下值。</span><span class="sxs-lookup"><span data-stu-id="92775-158">The following values can be returned in the **SPropProblemArray** structure, but not as return values for **DoCopyTo**.</span></span> <span data-ttu-id="92775-159">这些错误应用于单个属性。</span><span class="sxs-lookup"><span data-stu-id="92775-159">These errors apply to a single property.</span></span>
  
<span data-ttu-id="92775-160">MAPI_E_BAD_CHARWIDTH</span><span class="sxs-lookup"><span data-stu-id="92775-160">MAPI_E_BAD_CHARWIDTH</span></span> 
  
> <span data-ttu-id="92775-161">可以设置该 MAPI_UNICODE 标记**DoCopyTo**不支持 Unicode，或未设置 MAPI_UNICODE 和**DoCopyTo**支持仅 Unicode。</span><span class="sxs-lookup"><span data-stu-id="92775-161">Either the MAPI_UNICODE flag was set and **DoCopyTo** does not support Unicode, or MAPI_UNICODE was not set and **DoCopyTo** supports only Unicode.</span></span> 
    
<span data-ttu-id="92775-162">MAPI_E_COMPUTED</span><span class="sxs-lookup"><span data-stu-id="92775-162">MAPI_E_COMPUTED</span></span> 
  
> <span data-ttu-id="92775-163">该属性不能修改呼叫者，因为它是只读属性，计算目标对象的所有者。</span><span class="sxs-lookup"><span data-stu-id="92775-163">The property cannot be modified by the caller because it is a read-only property, computed by the owner of the destination object.</span></span> <span data-ttu-id="92775-164">此错误不是严重性。呼叫者应允许复制操作继续。</span><span class="sxs-lookup"><span data-stu-id="92775-164">This error is not severe; the caller should allow the copy operation to continue.</span></span>
    
<span data-ttu-id="92775-165">MAPI_E_INVALID_TYPE</span><span class="sxs-lookup"><span data-stu-id="92775-165">MAPI_E_INVALID_TYPE</span></span> 
  
> <span data-ttu-id="92775-166">属性类型无效。</span><span class="sxs-lookup"><span data-stu-id="92775-166">The property type is invalid.</span></span>
    
<span data-ttu-id="92775-167">MAPI_E_UNEXPECTED_TYPE</span><span class="sxs-lookup"><span data-stu-id="92775-167">MAPI_E_UNEXPECTED_TYPE</span></span> 
  
> <span data-ttu-id="92775-168">属性类型不需要呼叫者的类型。</span><span class="sxs-lookup"><span data-stu-id="92775-168">The property type is not the type expected by the caller.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="92775-169">说明</span><span class="sxs-lookup"><span data-stu-id="92775-169">Remarks</span></span>

<span data-ttu-id="92775-170">消息存储提供程序支持对象的实现**IMAPISupport::DoCopyTo**方法。</span><span class="sxs-lookup"><span data-stu-id="92775-170">The **IMAPISupport::DoCopyTo** method is implemented for message store provider support objects.</span></span> <span data-ttu-id="92775-171">消息存储提供程序可以调用**DoCopyTo**实现其文件夹和邮件的[IMAPIProp::CopyTo](imapiprop-copyto.md)方法。</span><span class="sxs-lookup"><span data-stu-id="92775-171">Message store providers can call **DoCopyTo** to implement the [IMAPIProp::CopyTo](imapiprop-copyto.md) method for their folders and messages.</span></span> 
  
<span data-ttu-id="92775-172">默认情况下， **DoCopyTo**复制或移动到另一个对象的所有一个对象的属性。</span><span class="sxs-lookup"><span data-stu-id="92775-172">By default, **DoCopyTo** copies or moves all of the properties of one object to another object.</span></span> <span data-ttu-id="92775-173">源对象中的任何子对象自动包括在操作并复制或移动全部。</span><span class="sxs-lookup"><span data-stu-id="92775-173">Any subobjects in the source object are automatically included in the operation and copied or moved in their entirety.</span></span> 
  
<span data-ttu-id="92775-174">如果任一复制或移动属性已经存在于目标对象，除非 MAPI_NOREPLACE 标志设置_ulFlags_参数中通过新的属性，来覆盖现有属性。</span><span class="sxs-lookup"><span data-stu-id="92775-174">If any of the copied or moved properties already exist in the destination object, the existing properties are overwritten by the new properties, unless the MAPI_NOREPLACE flag is set in the  _ulFlags_ parameter.</span></span> <span data-ttu-id="92775-175">保持不变，不会被覆盖的目标对象中的现有信息。</span><span class="sxs-lookup"><span data-stu-id="92775-175">Existing information in the destination object that is not overwritten is left untouched.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="92775-176">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="92775-176">Notes to callers</span></span>

<span data-ttu-id="92775-177">若要从副本排除属性或移动操作，其属性标记中包含的_lpExcludeProps_参数。</span><span class="sxs-lookup"><span data-stu-id="92775-177">To exclude properties from the copy or move operation, include their property tags in the  _lpExcludeProps_ parameter.</span></span> <span data-ttu-id="92775-178">如果您通过使用[PROP_TAG](prop_tag.md)宏生成从一个特定的标识符，该属性标记数组中的属性标记的结果，与该标识符的所有属性都将被都排除。</span><span class="sxs-lookup"><span data-stu-id="92775-178">If you pass the results of using the [PROP_TAG](prop_tag.md) macro to build a property tag from a specific identifier in the property tag array, all properties with that identifier will be excluded.</span></span> <span data-ttu-id="92775-179">例如，属性标记数组中的以下条目 0x8002 排除，无论类型的标识符的原因是了所有属性：</span><span class="sxs-lookup"><span data-stu-id="92775-179">For example, the following entry in the property tag array causes all properties with an identifier of 0x8002 to be excluded, regardless of type:</span></span> 
  
 `PROP_TAG(PT_LONG, 0x8002)`
  
<span data-ttu-id="92775-180">若要避免复制邮件的传递时间时将邮件复制到另一个文件夹，指定属性标记排除数组中的**PR_MESSAGE_DELIVERY_TIME** ([PidTagMessageDeliveryTime](pidtagmessagedeliverytime-canonical-property.md))。</span><span class="sxs-lookup"><span data-stu-id="92775-180">To avoid copying a message's delivery time when you copy the message to a different folder, specify **PR_MESSAGE_DELIVERY_TIME** ([PidTagMessageDeliveryTime](pidtagmessagedeliverytime-canonical-property.md)) in the property tag exclude array.</span></span> <span data-ttu-id="92775-181">若要排除邮件的收件人列表，请向排除数组添加**PR_MESSAGE_RECIPIENTS** ([PidTagMessageRecipients](pidtagmessagerecipients-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="92775-181">To exclude a message's recipient list, add the **PR_MESSAGE_RECIPIENTS** ([PidTagMessageRecipients](pidtagmessagerecipients-canonical-property.md)) property to the exclude array.</span></span> <span data-ttu-id="92775-182">若要排除邮件的附件，添加到数组**PR_MESSAGE_ATTACHMENTS** ([PidTagMessageAttachments](pidtagmessageattachments-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="92775-182">To exclude a message's attachments, add the **PR_MESSAGE_ATTACHMENTS** ([PidTagMessageAttachments](pidtagmessageattachments-canonical-property.md)) property to the array.</span></span>
  
<span data-ttu-id="92775-183">同样，要阻止的复制或移动的文件夹或通讯簿容器层次结构或内容表，包括**PR_CONTAINER_HIERARCHY** ([PidTagContainerHierarchy](pidtagcontainerhierarchy-canonical-property.md)) 或**PR_CONTAINER_CONTENTS** ([PidTagContainerContents](pidtagcontainercontents-canonical-property.md)) 的属性中标记排除数组。</span><span class="sxs-lookup"><span data-stu-id="92775-183">Similarly, to prevent the copying or moving of a folder or address book container's hierarchy or contents table, include **PR_CONTAINER_HIERARCHY** ([PidTagContainerHierarchy](pidtagcontainerhierarchy-canonical-property.md)) or **PR_CONTAINER_CONTENTS** ([PidTagContainerContents](pidtagcontainercontents-canonical-property.md)) in the property tag exclude array.</span></span>
  
<span data-ttu-id="92775-184">忽略 MAPI_E_COMPUTED _lppProblems_参数中**SPropProblemArray**结构中返回的错误。</span><span class="sxs-lookup"><span data-stu-id="92775-184">Ignore MAPI_E_COMPUTED errors returned in the **SPropProblemArray** structure in the  _lppProblems_ parameter.</span></span> 
  
<span data-ttu-id="92775-185">_LpSrcInterface_指向通常是相同的界面标识符_lpDestInterface_指向接口标识符。</span><span class="sxs-lookup"><span data-stu-id="92775-185">The interface identifier that  _lpSrcInterface_ points to is usually the same as the interface identifier that  _lpDestInterface_ points to.</span></span> 
  
<span data-ttu-id="92775-186">如果传递_lpDestInterface_中的可接受的界面标识符而_lpDestObj_中无效的指针，结果将无法预料。</span><span class="sxs-lookup"><span data-stu-id="92775-186">If you pass an acceptable interface identifier in  _lpDestInterface_ but an invalid pointer in  _lpDestObj_, the results are unpredictable.</span></span> <span data-ttu-id="92775-187">很可能这将导致您的提供商失败。</span><span class="sxs-lookup"><span data-stu-id="92775-187">Most likely this will cause your provider to fail.</span></span> 
  
<span data-ttu-id="92775-188">相反，如果您所知的补充信息的不应复制或移动，添加排除_rgiidExclude_参数中传递的数组中的接口的界面标识符。</span><span class="sxs-lookup"><span data-stu-id="92775-188">Conversely, if you are aware of supplemental information that should not be copied or moved, add the interface identifiers for the interfaces to be excluded in the array passed in the  _rgiidExclude_ parameter.</span></span> <span data-ttu-id="92775-189">例如，如果要复制的邮件，但不是任何其邮件附件， _rgiidExclude_数组中传递 IID_IMessage。</span><span class="sxs-lookup"><span data-stu-id="92775-189">For example, if you are copying messages, but not any of their message attachments, pass IID_IMessage in the  _rgiidExclude_ array.</span></span> <span data-ttu-id="92775-190">**DoCopyTo**忽略它无法识别的_rgiidExclude_中列出的任何接口。</span><span class="sxs-lookup"><span data-stu-id="92775-190">**DoCopyTo** ignores any interfaces listed in  _rgiidExclude_ that it does not recognize.</span></span> 
  
<span data-ttu-id="92775-191">当_rgiidExclude_参数用于排除一个接口时，它还不包括所有接口派生自的接口。</span><span class="sxs-lookup"><span data-stu-id="92775-191">When you use the  _rgiidExclude_ parameter to exclude an interface, it also excludes all interfaces derived from that interface.</span></span> <span data-ttu-id="92775-192">例如，不包括[IMAPIContainer](imapicontainerimapiprop.md)界面使文件夹或通讯簿容器排除，具体取决于提供程序的类型。</span><span class="sxs-lookup"><span data-stu-id="92775-192">For example, excluding the [IMAPIContainer](imapicontainerimapiprop.md) interface causes folders or address book containers to be excluded, depending on the type of provider.</span></span> <span data-ttu-id="92775-193">因为太多接口从它们派生，不要排除[IMAPIProp](imapipropiunknown.md)或[IUnknown](https://msdn.microsoft.com/library/33f1d79a-33fc-4ce5-a372-e08bda378332%28Office.15%29.aspx) 。</span><span class="sxs-lookup"><span data-stu-id="92775-193">Do not exclude [IMAPIProp](imapipropiunknown.md) or [IUnknown](https://msdn.microsoft.com/library/33f1d79a-33fc-4ce5-a372-e08bda378332%28Office.15%29.aspx) because so many interfaces derive from them.</span></span> 
  
 <span data-ttu-id="92775-194">**DoCopyTo**报告应用于作为一个整体，该操作的全局错误和的各个属性应用于单个错误。</span><span class="sxs-lookup"><span data-stu-id="92775-194">**DoCopyTo** reports global errors that apply to the operation as a whole, and individual errors that apply to individual properties.</span></span> <span data-ttu-id="92775-195">这些单个错误保持**SPropProblemArray**结构中。</span><span class="sxs-lookup"><span data-stu-id="92775-195">These individual errors are put in an **SPropProblemArray** structure.</span></span> <span data-ttu-id="92775-196">您可以隐藏错误属性级别通过传递 NULL，而不是有效的指针，property 问题数组结构参数的报告。</span><span class="sxs-lookup"><span data-stu-id="92775-196">You can suppress error reporting at the property level by passing NULL, rather than a valid pointer, for the property problem array structure parameter.</span></span> 
  
<span data-ttu-id="92775-197">如果您想要接收有关错误的信息，请在_lppProblems_参数中传递一个有效的**SPropProblemArray**结构指针。</span><span class="sxs-lookup"><span data-stu-id="92775-197">If you want to receive information about errors, pass a valid **SPropProblemArray** structure pointer in the  _lppProblems_ parameter.</span></span> <span data-ttu-id="92775-198">时**DoCopyTo** ，则返回 S_OK，检查与结构中的各个属性的可能错误。</span><span class="sxs-lookup"><span data-stu-id="92775-198">When **DoCopyTo** returns S_OK, check for possible errors with individual properties in the structure.</span></span> <span data-ttu-id="92775-199">当**DoCopyTo**返回错误时， **SPropProblemArray**结构中不返回任何信息。</span><span class="sxs-lookup"><span data-stu-id="92775-199">When **DoCopyTo** returns an error, no information is returned in the **SPropProblemArray** structure.</span></span> <span data-ttu-id="92775-200">相反，调用[IMAPISupport::GetLastError](imapisupport-getlasterror.md)方法检索详细的错误信息。</span><span class="sxs-lookup"><span data-stu-id="92775-200">Instead, call the [IMAPISupport::GetLastError](imapisupport-getlasterror.md) method to retrieve detailed error information.</span></span> 
  
<span data-ttu-id="92775-201">如果**DoCopyTo** ，则返回 S_OK，通过调用[MAPIFreeBuffer](mapifreebuffer.md)函数释放返回的**SPropProblemArray**结构。</span><span class="sxs-lookup"><span data-stu-id="92775-201">If **DoCopyTo** returns S_OK, free the returned **SPropProblemArray** structure by calling the [MAPIFreeBuffer](mapifreebuffer.md) function.</span></span> 
  
<span data-ttu-id="92775-202">如果一个全局错误出现**DoCopyTo**呼叫，不要使用或释放**SPropProblemArray**结构。</span><span class="sxs-lookup"><span data-stu-id="92775-202">If a global error occurs on the **DoCopyTo** call, do not use or free the **SPropProblemArray** structure.</span></span> <span data-ttu-id="92775-203">提供程序应忽略返回**DoCopyTo** **SPropProblemArray**结构中的作为_ulIndex_成员。</span><span class="sxs-lookup"><span data-stu-id="92775-203">Providers should ignore the  _ulIndex_ member in **SPropProblemArray** structures returned by **DoCopyTo**.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="92775-204">另请参阅</span><span class="sxs-lookup"><span data-stu-id="92775-204">See also</span></span>



[<span data-ttu-id="92775-205">IMAPIProp::CopyTo</span><span class="sxs-lookup"><span data-stu-id="92775-205">IMAPIProp::CopyTo</span></span>](imapiprop-copyto.md)
  
[<span data-ttu-id="92775-206">IMAPISupport::CopyFolder</span><span class="sxs-lookup"><span data-stu-id="92775-206">IMAPISupport::CopyFolder</span></span>](imapisupport-copyfolder.md)
  
[<span data-ttu-id="92775-207">IMAPISupport::CopyMessages</span><span class="sxs-lookup"><span data-stu-id="92775-207">IMAPISupport::CopyMessages</span></span>](imapisupport-copymessages.md)
  
[<span data-ttu-id="92775-208">IMAPISupport::GetLastError</span><span class="sxs-lookup"><span data-stu-id="92775-208">IMAPISupport::GetLastError</span></span>](imapisupport-getlasterror.md)
  
[<span data-ttu-id="92775-209">PidTagContainerContents 规范属性</span><span class="sxs-lookup"><span data-stu-id="92775-209">PidTagContainerContents Canonical Property</span></span>](pidtagcontainercontents-canonical-property.md)
  
[<span data-ttu-id="92775-210">PidTagContainerHierarchy 规范属性</span><span class="sxs-lookup"><span data-stu-id="92775-210">PidTagContainerHierarchy Canonical Property</span></span>](pidtagcontainerhierarchy-canonical-property.md)
  
[<span data-ttu-id="92775-211">PidTagMessageAttachments 规范属性</span><span class="sxs-lookup"><span data-stu-id="92775-211">PidTagMessageAttachments Canonical Property</span></span>](pidtagmessageattachments-canonical-property.md)
  
[<span data-ttu-id="92775-212">PidTagMessageDeliveryTime 规范属性</span><span class="sxs-lookup"><span data-stu-id="92775-212">PidTagMessageDeliveryTime Canonical Property</span></span>](pidtagmessagedeliverytime-canonical-property.md)
  
[<span data-ttu-id="92775-213">PidTagMessageRecipients 规范属性</span><span class="sxs-lookup"><span data-stu-id="92775-213">PidTagMessageRecipients Canonical Property</span></span>](pidtagmessagerecipients-canonical-property.md)
  
[<span data-ttu-id="92775-214">SPropProblemArray</span><span class="sxs-lookup"><span data-stu-id="92775-214">SPropProblemArray</span></span>](spropproblemarray.md)
  
[<span data-ttu-id="92775-215">SPropTagArray</span><span class="sxs-lookup"><span data-stu-id="92775-215">SPropTagArray</span></span>](sproptagarray.md)
  
[<span data-ttu-id="92775-216">IMAPISupport : IUnknown</span><span class="sxs-lookup"><span data-stu-id="92775-216">IMAPISupport : IUnknown</span></span>](imapisupportiunknown.md)

