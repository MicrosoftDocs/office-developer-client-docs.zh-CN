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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 6f6c802f1d5ead1750c05fafc54533487fe3732a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32331806"
---
# <a name="imapisupportdocopyto"></a><span data-ttu-id="9b8a7-103">IMAPISupport::DoCopyTo</span><span class="sxs-lookup"><span data-stu-id="9b8a7-103">IMAPISupport::DoCopyTo</span></span>

  
  
<span data-ttu-id="9b8a7-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="9b8a7-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="9b8a7-105">将一个对象的所有属性（专门排除的属性除外）复制或移动到另一个对象。</span><span class="sxs-lookup"><span data-stu-id="9b8a7-105">Copies or moves all properties of one object, except for specifically excluded properties, to another object.</span></span>
  
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

## <a name="parameters"></a><span data-ttu-id="9b8a7-106">参数</span><span class="sxs-lookup"><span data-stu-id="9b8a7-106">Parameters</span></span>

 <span data-ttu-id="9b8a7-107">_lpSrcInterface_</span><span class="sxs-lookup"><span data-stu-id="9b8a7-107">_lpSrcInterface_</span></span>
  
> <span data-ttu-id="9b8a7-108">[in]指向接口标识符的指针 (IID) 表示用于访问具有要复制或移动的属性的对象的接口。</span><span class="sxs-lookup"><span data-stu-id="9b8a7-108">[in] A pointer to the interface identifier (IID) that represents the interface to be used to access the object that has the properties to be copied or moved.</span></span>
    
 <span data-ttu-id="9b8a7-109">_lpSrcObj_</span><span class="sxs-lookup"><span data-stu-id="9b8a7-109">_lpSrcObj_</span></span>
  
> <span data-ttu-id="9b8a7-110">[in]指向具有要复制或移动的属性的对象的指针。</span><span class="sxs-lookup"><span data-stu-id="9b8a7-110">[in] A pointer to the object that has the properties to be copied or moved.</span></span>
    
 <span data-ttu-id="9b8a7-111">_ciidExclude_</span><span class="sxs-lookup"><span data-stu-id="9b8a7-111">_ciidExclude_</span></span>
  
> <span data-ttu-id="9b8a7-112">[in]复制或移动属性时要排除的接口计数。</span><span class="sxs-lookup"><span data-stu-id="9b8a7-112">[in] The count of interfaces to exclude when you copy or move properties.</span></span>
    
 <span data-ttu-id="9b8a7-113">_rgiidExclude_</span><span class="sxs-lookup"><span data-stu-id="9b8a7-113">_rgiidExclude_</span></span>
  
> <span data-ttu-id="9b8a7-114">[in]接口标识符的数组，指示在将补充信息复制或移动到目标对象时不应使用的接口。</span><span class="sxs-lookup"><span data-stu-id="9b8a7-114">[in] An array of interface identifiers that indicates interfaces that should not be used when you copy or move supplemental information to the destination object.</span></span>
    
 <span data-ttu-id="9b8a7-115">_lpExcludeProps_</span><span class="sxs-lookup"><span data-stu-id="9b8a7-115">_lpExcludeProps_</span></span>
  
> <span data-ttu-id="9b8a7-116">[in]指向属性标记数组的指针，该数组标识应从复制或移动操作中排除的属性标记。</span><span class="sxs-lookup"><span data-stu-id="9b8a7-116">[in] A pointer to a property tag array that identifies the property tags that should be excluded from the copy or move operation.</span></span> <span data-ttu-id="9b8a7-117">在  _lpExcludeProps_ 参数中传递 NULL 指示应复制或移动对象的所有属性。</span><span class="sxs-lookup"><span data-stu-id="9b8a7-117">Passing NULL in the  _lpExcludeProps_ parameter indicates that all of the object's properties should be copied or moved.</span></span> <span data-ttu-id="9b8a7-118">**DoCopyTo** MAPI_E_INVALID_PARAMETER _lpExcludeProps_ 指向 [的 SPropTagArray](sproptagarray.md)结构的 **cValues** 成员设置为 0 时返回值。</span><span class="sxs-lookup"><span data-stu-id="9b8a7-118">**DoCopyTo** returns MAPI_E_INVALID_PARAMETER when the **cValues** member of the [SPropTagArray](sproptagarray.md) structure pointed to by  _lpExcludeProps_ is set to 0.</span></span> 
    
 <span data-ttu-id="9b8a7-119">_ulUIParam_</span><span class="sxs-lookup"><span data-stu-id="9b8a7-119">_ulUIParam_</span></span>
  
> <span data-ttu-id="9b8a7-120">[in]进度指示器的父窗口的句柄。</span><span class="sxs-lookup"><span data-stu-id="9b8a7-120">[in] A handle to the parent window of the progress indicator.</span></span> 
    
 <span data-ttu-id="9b8a7-121">_lpProgress_</span><span class="sxs-lookup"><span data-stu-id="9b8a7-121">_lpProgress_</span></span>
  
> <span data-ttu-id="9b8a7-122">[in]指向进度指示器实现的指针。</span><span class="sxs-lookup"><span data-stu-id="9b8a7-122">[in] A pointer to a progress indicator implementation.</span></span> <span data-ttu-id="9b8a7-123">如果在  _lpProgress_ 参数中传递 NULL，MAPI 将提供进度实现。</span><span class="sxs-lookup"><span data-stu-id="9b8a7-123">If NULL is passed in the  _lpProgress_ parameter, MAPI provides the progress implementation.</span></span> <span data-ttu-id="9b8a7-124">除非在 _ulFlags_ 参数中设置了 MAPI_DIALOG 标志，否则将忽略 _lpProgress_ 参数。</span><span class="sxs-lookup"><span data-stu-id="9b8a7-124">The  _lpProgress_ parameter is ignored unless the MAPI_DIALOG flag is set in the  _ulFlags_ parameter.</span></span> 
    
 <span data-ttu-id="9b8a7-125">_lpDestInterface_</span><span class="sxs-lookup"><span data-stu-id="9b8a7-125">_lpDestInterface_</span></span>
  
> <span data-ttu-id="9b8a7-126">[in]指向接口标识符的指针，该标识符表示用于访问对象以接收复制或移动的属性的接口。</span><span class="sxs-lookup"><span data-stu-id="9b8a7-126">[in] A pointer to the interface identifier that represents the interface to be used to access the object to receive the copied or moved properties.</span></span>
    
 <span data-ttu-id="9b8a7-127">_lpDestObj_</span><span class="sxs-lookup"><span data-stu-id="9b8a7-127">_lpDestObj_</span></span>
  
> <span data-ttu-id="9b8a7-128">[in]指向接收复制或移动的属性的对象的指针。</span><span class="sxs-lookup"><span data-stu-id="9b8a7-128">[in] A pointer to the object to receive the copied or moved properties.</span></span>
    
 <span data-ttu-id="9b8a7-129">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="9b8a7-129">_ulFlags_</span></span>
  
> <span data-ttu-id="9b8a7-130">[in]控制复制或移动操作的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="9b8a7-130">[in] A bitmask of flags that controls the copy or move operation.</span></span> <span data-ttu-id="9b8a7-131">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="9b8a7-131">The following flags can be set:</span></span>
    
<span data-ttu-id="9b8a7-132">MAPI_DIALOG</span><span class="sxs-lookup"><span data-stu-id="9b8a7-132">MAPI_DIALOG</span></span> 
  
> <span data-ttu-id="9b8a7-133">显示进度指示器。</span><span class="sxs-lookup"><span data-stu-id="9b8a7-133">Displays a progress indicator.</span></span> 
    
<span data-ttu-id="9b8a7-134">MAPI_MOVE</span><span class="sxs-lookup"><span data-stu-id="9b8a7-134">MAPI_MOVE</span></span> 
  
> <span data-ttu-id="9b8a7-135">**DoCopyTo** 应执行移动操作，而不是复制操作。</span><span class="sxs-lookup"><span data-stu-id="9b8a7-135">**DoCopyTo** should perform a move operation instead of a copy operation.</span></span> <span data-ttu-id="9b8a7-136">未设置此标志时 **，DoCopyTo** 将执行复制操作。</span><span class="sxs-lookup"><span data-stu-id="9b8a7-136">When this flag is not set, **DoCopyTo** performs a copy operation.</span></span> 
    
<span data-ttu-id="9b8a7-137">MAPI_NOREPLACE</span><span class="sxs-lookup"><span data-stu-id="9b8a7-137">MAPI_NOREPLACE</span></span> 
  
> <span data-ttu-id="9b8a7-138">不应覆盖目标对象中的现有属性。</span><span class="sxs-lookup"><span data-stu-id="9b8a7-138">Existing properties in the destination object should not be overwritten.</span></span> <span data-ttu-id="9b8a7-139">未设置此标志时 **，DoCopyTo** 将覆盖现有属性。</span><span class="sxs-lookup"><span data-stu-id="9b8a7-139">When this flag is not set, **DoCopyTo** overwrites existing properties.</span></span> 
    
 <span data-ttu-id="9b8a7-140">_lppProblems_</span><span class="sxs-lookup"><span data-stu-id="9b8a7-140">_lppProblems_</span></span>
  
> <span data-ttu-id="9b8a7-141">[out]在输入时，指向指向 [SPropProblemArray 结构的指针的](spropproblemarray.md) 指针;否则为 NULL，表示不需要错误信息。</span><span class="sxs-lookup"><span data-stu-id="9b8a7-141">[out] On input, a pointer to a pointer to an [SPropProblemArray](spropproblemarray.md) structure; otherwise, NULL, which indicates no need for error information.</span></span> <span data-ttu-id="9b8a7-142">如果  _lppProblems_ 是输入的有效指针， **则 DoCopyTo** 返回有关复制一个或多个属性时错误的详细信息。</span><span class="sxs-lookup"><span data-stu-id="9b8a7-142">If  _lppProblems_ is a valid pointer on input, **DoCopyTo** returns detailed information about errors in copying one or more properties.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="9b8a7-143">返回值</span><span class="sxs-lookup"><span data-stu-id="9b8a7-143">Return value</span></span>

<span data-ttu-id="9b8a7-144">S_OK</span><span class="sxs-lookup"><span data-stu-id="9b8a7-144">S_OK</span></span> 
  
> <span data-ttu-id="9b8a7-145">已成功复制或移动属性。</span><span class="sxs-lookup"><span data-stu-id="9b8a7-145">The properties have been successfully copied or moved.</span></span>
    
<span data-ttu-id="9b8a7-146">MAPI_E_COLLISION</span><span class="sxs-lookup"><span data-stu-id="9b8a7-146">MAPI_E_COLLISION</span></span> 
  
> <span data-ttu-id="9b8a7-147">要复制或移动的属性在目标对象中已存在，MAPI_NOREPLACE标记。</span><span class="sxs-lookup"><span data-stu-id="9b8a7-147">A property to be copied or moved already exists in the destination object and the MAPI_NOREPLACE flag is set.</span></span> 
    
<span data-ttu-id="9b8a7-148">MAPI_E_FOLDER_CYCLE</span><span class="sxs-lookup"><span data-stu-id="9b8a7-148">MAPI_E_FOLDER_CYCLE</span></span> 
  
> <span data-ttu-id="9b8a7-149">源对象直接或间接包含目标对象。</span><span class="sxs-lookup"><span data-stu-id="9b8a7-149">The source object directly or indirectly contains the destination object.</span></span> <span data-ttu-id="9b8a7-150">在发现此条件之前，可能执行了大量工作，因此可能会部分修改源对象和目标对象。</span><span class="sxs-lookup"><span data-stu-id="9b8a7-150">Significant work might have been performed before this condition was discovered, so the source and destination objects might be partially modified.</span></span> 
    
<span data-ttu-id="9b8a7-151">MAPI_E_INTERFACE_NOT_SUPPORTED</span><span class="sxs-lookup"><span data-stu-id="9b8a7-151">MAPI_E_INTERFACE_NOT_SUPPORTED</span></span> 
  
> <span data-ttu-id="9b8a7-152">_lpSrcInterface_ 参数标识的接口不受 _lpSrcObj_ 指向的对象支持，或者 _lpDestObj_ 指向的对象不支持 _由 lpDestInterface_ 参数标识的接口。</span><span class="sxs-lookup"><span data-stu-id="9b8a7-152">The interface identified by the  _lpSrcInterface_ parameter is not supported by the object pointed to by  _lpSrcObj_, or the interface identified by the  _lpDestInterface_ parameter is not supported by the object pointed to by  _lpDestObj_.</span></span> 
    
<span data-ttu-id="9b8a7-153">MAPI_E_NO_ACCESS</span><span class="sxs-lookup"><span data-stu-id="9b8a7-153">MAPI_E_NO_ACCESS</span></span> 
  
> <span data-ttu-id="9b8a7-154">试图访问调用方权限不足的对象。</span><span class="sxs-lookup"><span data-stu-id="9b8a7-154">An attempt was made to access an object for which the caller has insufficient permissions.</span></span> <span data-ttu-id="9b8a7-155">如果目标对象与源对象相同，则返回此错误。</span><span class="sxs-lookup"><span data-stu-id="9b8a7-155">This error is returned if the destination object is the same as the source object.</span></span>
    
<span data-ttu-id="9b8a7-156">MAPI_E_INVALID_PARAMETER</span><span class="sxs-lookup"><span data-stu-id="9b8a7-156">MAPI_E_INVALID_PARAMETER</span></span> 
  
> <span data-ttu-id="9b8a7-157">_lpSrcInterface_ 参数为 NULL。</span><span class="sxs-lookup"><span data-stu-id="9b8a7-157">The  _lpSrcInterface_ parameter is NULL.</span></span> 
    
<span data-ttu-id="9b8a7-158">以下值可以在 **SPropProblemArray** 结构中返回，但不能作为 **DoCopyTo** 的返回值。</span><span class="sxs-lookup"><span data-stu-id="9b8a7-158">The following values can be returned in the **SPropProblemArray** structure, but not as return values for **DoCopyTo**.</span></span> <span data-ttu-id="9b8a7-159">这些错误适用于单个属性。</span><span class="sxs-lookup"><span data-stu-id="9b8a7-159">These errors apply to a single property.</span></span>
  
<span data-ttu-id="9b8a7-160">MAPI_E_BAD_CHARWIDTH</span><span class="sxs-lookup"><span data-stu-id="9b8a7-160">MAPI_E_BAD_CHARWIDTH</span></span> 
  
> <span data-ttu-id="9b8a7-161">设置MAPI_UNICODE **DoCopyTo** 不支持 Unicode，或者未MAPI_UNICODE **DoCopyTo** 仅支持 Unicode。</span><span class="sxs-lookup"><span data-stu-id="9b8a7-161">Either the MAPI_UNICODE flag was set and **DoCopyTo** does not support Unicode, or MAPI_UNICODE was not set and **DoCopyTo** supports only Unicode.</span></span> 
    
<span data-ttu-id="9b8a7-162">MAPI_E_COMPUTED</span><span class="sxs-lookup"><span data-stu-id="9b8a7-162">MAPI_E_COMPUTED</span></span> 
  
> <span data-ttu-id="9b8a7-163">调用方无法修改该属性，因为它是一个只读属性，由目标对象的所有者计算。</span><span class="sxs-lookup"><span data-stu-id="9b8a7-163">The property cannot be modified by the caller because it is a read-only property, computed by the owner of the destination object.</span></span> <span data-ttu-id="9b8a7-164">此错误并不严重;调用方应允许复制操作继续。</span><span class="sxs-lookup"><span data-stu-id="9b8a7-164">This error is not severe; the caller should allow the copy operation to continue.</span></span>
    
<span data-ttu-id="9b8a7-165">MAPI_E_INVALID_TYPE</span><span class="sxs-lookup"><span data-stu-id="9b8a7-165">MAPI_E_INVALID_TYPE</span></span> 
  
> <span data-ttu-id="9b8a7-166">属性类型无效。</span><span class="sxs-lookup"><span data-stu-id="9b8a7-166">The property type is invalid.</span></span>
    
<span data-ttu-id="9b8a7-167">MAPI_E_UNEXPECTED_TYPE</span><span class="sxs-lookup"><span data-stu-id="9b8a7-167">MAPI_E_UNEXPECTED_TYPE</span></span> 
  
> <span data-ttu-id="9b8a7-168">属性类型不是调用方预期的类型。</span><span class="sxs-lookup"><span data-stu-id="9b8a7-168">The property type is not the type expected by the caller.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="9b8a7-169">备注</span><span class="sxs-lookup"><span data-stu-id="9b8a7-169">Remarks</span></span>

<span data-ttu-id="9b8a7-170">**IMAPISupport：:D oCopyTo** 方法为邮件存储提供程序支持对象实现。</span><span class="sxs-lookup"><span data-stu-id="9b8a7-170">The **IMAPISupport::DoCopyTo** method is implemented for message store provider support objects.</span></span> <span data-ttu-id="9b8a7-171">邮件存储提供程序可以调用 **DoCopyTo** 来实现其文件夹和消息的 [IMAPIProp：：CopyTo](imapiprop-copyto.md) 方法。</span><span class="sxs-lookup"><span data-stu-id="9b8a7-171">Message store providers can call **DoCopyTo** to implement the [IMAPIProp::CopyTo](imapiprop-copyto.md) method for their folders and messages.</span></span> 
  
<span data-ttu-id="9b8a7-172">默认情况下 **，DoCopyTo** 将一个对象的所有属性复制或移动到另一个对象。</span><span class="sxs-lookup"><span data-stu-id="9b8a7-172">By default, **DoCopyTo** copies or moves all of the properties of one object to another object.</span></span> <span data-ttu-id="9b8a7-173">源对象中任何子对象都将自动包含在操作中，并完整复制或移动。</span><span class="sxs-lookup"><span data-stu-id="9b8a7-173">Any subobjects in the source object are automatically included in the operation and copied or moved in their entirety.</span></span> 
  
<span data-ttu-id="9b8a7-174">如果目标对象中已存在任何复制或移动的属性，则现有属性将被新属性覆盖，除非在  _ulFlags_ 参数中设置了 MAPI_NOREPLACE 标志。</span><span class="sxs-lookup"><span data-stu-id="9b8a7-174">If any of the copied or moved properties already exist in the destination object, the existing properties are overwritten by the new properties, unless the MAPI_NOREPLACE flag is set in the  _ulFlags_ parameter.</span></span> <span data-ttu-id="9b8a7-175">目标对象中未覆盖的现有信息保持不变。</span><span class="sxs-lookup"><span data-stu-id="9b8a7-175">Existing information in the destination object that is not overwritten is left untouched.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="9b8a7-176">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="9b8a7-176">Notes to callers</span></span>

<span data-ttu-id="9b8a7-177">若要从复制或移动操作中排除属性，请将其属性标记包括在  _lpExcludeProps_ 参数中。</span><span class="sxs-lookup"><span data-stu-id="9b8a7-177">To exclude properties from the copy or move operation, include their property tags in the  _lpExcludeProps_ parameter.</span></span> <span data-ttu-id="9b8a7-178">如果传递使用 PROP_TAG 宏从[](prop_tag.md)属性标记数组中的特定标识符构建属性标记的结果，将排除具有该标识符的所有属性。</span><span class="sxs-lookup"><span data-stu-id="9b8a7-178">If you pass the results of using the [PROP_TAG](prop_tag.md) macro to build a property tag from a specific identifier in the property tag array, all properties with that identifier will be excluded.</span></span> <span data-ttu-id="9b8a7-179">例如，属性标记数组中的以下条目会导致排除标识符为 0x8002的所有属性，无论类型如何：</span><span class="sxs-lookup"><span data-stu-id="9b8a7-179">For example, the following entry in the property tag array causes all properties with an identifier of 0x8002 to be excluded, regardless of type:</span></span> 
  
 `PROP_TAG(PT_LONG, 0x8002)`
  
<span data-ttu-id="9b8a7-180">为避免在将邮件复制到其他文件夹时复制邮件的传递时间，请指定 **PR_MESSAGE_DELIVERY_TIME** ([PidTagMessageDeliveryTime](pidtagmessagedeliverytime-canonical-property.md)) 属性标记排除数组。</span><span class="sxs-lookup"><span data-stu-id="9b8a7-180">To avoid copying a message's delivery time when you copy the message to a different folder, specify **PR_MESSAGE_DELIVERY_TIME** ([PidTagMessageDeliveryTime](pidtagmessagedeliverytime-canonical-property.md)) in the property tag exclude array.</span></span> <span data-ttu-id="9b8a7-181">若要排除邮件的收件人列表，PR_MESSAGE_RECIPIENTS ([PidTagMessageRecipients) PidTagMessageRecipients](pidtagmessagerecipients-canonical-property.md)属性添加到排除数组。 </span><span class="sxs-lookup"><span data-stu-id="9b8a7-181">To exclude a message's recipient list, add the **PR_MESSAGE_RECIPIENTS** ([PidTagMessageRecipients](pidtagmessagerecipients-canonical-property.md)) property to the exclude array.</span></span> <span data-ttu-id="9b8a7-182">若要排除邮件的附件，PR_MESSAGE_ATTACHMENTS ([PidTagMessageAttachments](pidtagmessageattachments-canonical-property.md)) 添加到数组。 </span><span class="sxs-lookup"><span data-stu-id="9b8a7-182">To exclude a message's attachments, add the **PR_MESSAGE_ATTACHMENTS** ([PidTagMessageAttachments](pidtagmessageattachments-canonical-property.md)) property to the array.</span></span>
  
<span data-ttu-id="9b8a7-183">同样，若要防止复制或移动文件夹或通讯簿容器的层次结构或内容表，在属性标记排除数组中包括 **PR_CONTAINER_HIERARCHY** ([PidTagContainerHierarchy](pidtagcontainerhierarchy-canonical-property.md)) 或 **PR_CONTAINER_CONTENTS** ([PidTagContainerContents](pidtagcontainercontents-canonical-property.md)) 。</span><span class="sxs-lookup"><span data-stu-id="9b8a7-183">Similarly, to prevent the copying or moving of a folder or address book container's hierarchy or contents table, include **PR_CONTAINER_HIERARCHY** ([PidTagContainerHierarchy](pidtagcontainerhierarchy-canonical-property.md)) or **PR_CONTAINER_CONTENTS** ([PidTagContainerContents](pidtagcontainercontents-canonical-property.md)) in the property tag exclude array.</span></span>
  
<span data-ttu-id="9b8a7-184">忽略MAPI_E_COMPUTED _lppProblems_ 参数 **的 SPropProblemArray** 结构中返回的错误。</span><span class="sxs-lookup"><span data-stu-id="9b8a7-184">Ignore MAPI_E_COMPUTED errors returned in the **SPropProblemArray** structure in the  _lppProblems_ parameter.</span></span> 
  
<span data-ttu-id="9b8a7-185">_lpSrcInterface_ 指向的接口标识符通常与 _lpDestInterface_ 指向的接口标识符相同。</span><span class="sxs-lookup"><span data-stu-id="9b8a7-185">The interface identifier that  _lpSrcInterface_ points to is usually the same as the interface identifier that  _lpDestInterface_ points to.</span></span> 
  
<span data-ttu-id="9b8a7-186">如果在  _lpDestInterface 中_ 传递可接受的接口标识符，但  _lpDestObj_ 中的指针无效，则结果不可预测。</span><span class="sxs-lookup"><span data-stu-id="9b8a7-186">If you pass an acceptable interface identifier in  _lpDestInterface_ but an invalid pointer in  _lpDestObj_, the results are unpredictable.</span></span> <span data-ttu-id="9b8a7-187">这很可能会导致提供程序失败。</span><span class="sxs-lookup"><span data-stu-id="9b8a7-187">Most likely this will cause your provider to fail.</span></span> 
  
<span data-ttu-id="9b8a7-188">相反，如果您知道不应复制或移动的补充信息，请添加接口标识符，以在  _rgiidExclude_ 参数传递的数组中排除这些接口。</span><span class="sxs-lookup"><span data-stu-id="9b8a7-188">Conversely, if you are aware of supplemental information that should not be copied or moved, add the interface identifiers for the interfaces to be excluded in the array passed in the  _rgiidExclude_ parameter.</span></span> <span data-ttu-id="9b8a7-189">例如，如果要复制邮件，但不复制其任何邮件附件，IID_IMessage  _rgiidExclude 数组中传递_ 邮件。</span><span class="sxs-lookup"><span data-stu-id="9b8a7-189">For example, if you are copying messages, but not any of their message attachments, pass IID_IMessage in the  _rgiidExclude_ array.</span></span> <span data-ttu-id="9b8a7-190">**DoCopyTo** 忽略  _rgiidExclude_ 中未识别的任何接口。</span><span class="sxs-lookup"><span data-stu-id="9b8a7-190">**DoCopyTo** ignores any interfaces listed in  _rgiidExclude_ that it does not recognize.</span></span> 
  
<span data-ttu-id="9b8a7-191">使用  _rgiidExclude_ 参数排除接口时，它还排除从该接口派生的所有接口。</span><span class="sxs-lookup"><span data-stu-id="9b8a7-191">When you use the  _rgiidExclude_ parameter to exclude an interface, it also excludes all interfaces derived from that interface.</span></span> <span data-ttu-id="9b8a7-192">例如，排除 [IMAPIContainer](imapicontainerimapiprop.md) 接口会导致排除文件夹或通讯簿容器，具体取决于提供程序的类型。</span><span class="sxs-lookup"><span data-stu-id="9b8a7-192">For example, excluding the [IMAPIContainer](imapicontainerimapiprop.md) interface causes folders or address book containers to be excluded, depending on the type of provider.</span></span> <span data-ttu-id="9b8a7-193">不要排除 [IMAPIProp](imapipropiunknown.md) 或 [IUnknown，](https://msdn.microsoft.com/library/33f1d79a-33fc-4ce5-a372-e08bda378332%28Office.15%29.aspx) 因为有很多接口派生自它们。</span><span class="sxs-lookup"><span data-stu-id="9b8a7-193">Do not exclude [IMAPIProp](imapipropiunknown.md) or [IUnknown](https://msdn.microsoft.com/library/33f1d79a-33fc-4ce5-a372-e08bda378332%28Office.15%29.aspx) because so many interfaces derive from them.</span></span> 
  
 <span data-ttu-id="9b8a7-194">**DoCopyTo** 报告应用于整个运算的全局错误，以及适用于单个属性的单个错误。</span><span class="sxs-lookup"><span data-stu-id="9b8a7-194">**DoCopyTo** reports global errors that apply to the operation as a whole, and individual errors that apply to individual properties.</span></span> <span data-ttu-id="9b8a7-195">这些单个错误将放入 **SPropProblemArray** 结构中。</span><span class="sxs-lookup"><span data-stu-id="9b8a7-195">These individual errors are put in an **SPropProblemArray** structure.</span></span> <span data-ttu-id="9b8a7-196">可以通过为属性问题数组结构参数传递 NULL（而不是有效指针）来禁止在属性级别报告错误。</span><span class="sxs-lookup"><span data-stu-id="9b8a7-196">You can suppress error reporting at the property level by passing NULL, rather than a valid pointer, for the property problem array structure parameter.</span></span> 
  
<span data-ttu-id="9b8a7-197">如果要接收有关错误的信息，请传递 _lppProblems_ 参数中的有效 **SPropProblemArray** 结构指针。</span><span class="sxs-lookup"><span data-stu-id="9b8a7-197">If you want to receive information about errors, pass a valid **SPropProblemArray** structure pointer in the  _lppProblems_ parameter.</span></span> <span data-ttu-id="9b8a7-198">当 **DoCopyTo** S_OK时，请检查结构中各个属性的可能错误。</span><span class="sxs-lookup"><span data-stu-id="9b8a7-198">When **DoCopyTo** returns S_OK, check for possible errors with individual properties in the structure.</span></span> <span data-ttu-id="9b8a7-199">当 **DoCopyTo** 返回错误时 **，SPropProblemArray** 结构中不会返回任何信息。</span><span class="sxs-lookup"><span data-stu-id="9b8a7-199">When **DoCopyTo** returns an error, no information is returned in the **SPropProblemArray** structure.</span></span> <span data-ttu-id="9b8a7-200">相反，请调用 [IMAPISupport：：GetLastError](imapisupport-getlasterror.md) 方法来检索详细的错误信息。</span><span class="sxs-lookup"><span data-stu-id="9b8a7-200">Instead, call the [IMAPISupport::GetLastError](imapisupport-getlasterror.md) method to retrieve detailed error information.</span></span> 
  
<span data-ttu-id="9b8a7-201">如果 **DoCopyTo** S_OK，请通过调用 [MAPIFreeBuffer](mapifreebuffer.md)函数释放返回的 **SPropProblemArray** 结构。</span><span class="sxs-lookup"><span data-stu-id="9b8a7-201">If **DoCopyTo** returns S_OK, free the returned **SPropProblemArray** structure by calling the [MAPIFreeBuffer](mapifreebuffer.md) function.</span></span> 
  
<span data-ttu-id="9b8a7-202">如果在 **DoCopyTo** 调用上发生全局错误，请不要使用或释放 **SPropProblemArray** 结构。</span><span class="sxs-lookup"><span data-stu-id="9b8a7-202">If a global error occurs on the **DoCopyTo** call, do not use or free the **SPropProblemArray** structure.</span></span> <span data-ttu-id="9b8a7-203">提供程序应忽略 **DoCopyTo** 返回 **的 SPropProblemArray** 结构中的 _ulIndex_ 成员。</span><span class="sxs-lookup"><span data-stu-id="9b8a7-203">Providers should ignore the  _ulIndex_ member in **SPropProblemArray** structures returned by **DoCopyTo**.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="9b8a7-204">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9b8a7-204">See also</span></span>



[<span data-ttu-id="9b8a7-205">IMAPIProp::CopyTo</span><span class="sxs-lookup"><span data-stu-id="9b8a7-205">IMAPIProp::CopyTo</span></span>](imapiprop-copyto.md)
  
[<span data-ttu-id="9b8a7-206">IMAPISupport::CopyFolder</span><span class="sxs-lookup"><span data-stu-id="9b8a7-206">IMAPISupport::CopyFolder</span></span>](imapisupport-copyfolder.md)
  
[<span data-ttu-id="9b8a7-207">IMAPISupport::CopyMessages</span><span class="sxs-lookup"><span data-stu-id="9b8a7-207">IMAPISupport::CopyMessages</span></span>](imapisupport-copymessages.md)
  
[<span data-ttu-id="9b8a7-208">IMAPISupport::GetLastError</span><span class="sxs-lookup"><span data-stu-id="9b8a7-208">IMAPISupport::GetLastError</span></span>](imapisupport-getlasterror.md)
  
[<span data-ttu-id="9b8a7-209">PidTagContainerContents 规范属性</span><span class="sxs-lookup"><span data-stu-id="9b8a7-209">PidTagContainerContents Canonical Property</span></span>](pidtagcontainercontents-canonical-property.md)
  
[<span data-ttu-id="9b8a7-210">PidTagContainerHierarchy 规范属性</span><span class="sxs-lookup"><span data-stu-id="9b8a7-210">PidTagContainerHierarchy Canonical Property</span></span>](pidtagcontainerhierarchy-canonical-property.md)
  
[<span data-ttu-id="9b8a7-211">PidTagMessageAttachments 规范属性</span><span class="sxs-lookup"><span data-stu-id="9b8a7-211">PidTagMessageAttachments Canonical Property</span></span>](pidtagmessageattachments-canonical-property.md)
  
[<span data-ttu-id="9b8a7-212">PidTagMessageDeliveryTime 规范属性</span><span class="sxs-lookup"><span data-stu-id="9b8a7-212">PidTagMessageDeliveryTime Canonical Property</span></span>](pidtagmessagedeliverytime-canonical-property.md)
  
[<span data-ttu-id="9b8a7-213">PidTagMessageRecipients 规范属性</span><span class="sxs-lookup"><span data-stu-id="9b8a7-213">PidTagMessageRecipients Canonical Property</span></span>](pidtagmessagerecipients-canonical-property.md)
  
[<span data-ttu-id="9b8a7-214">SPropProblemArray</span><span class="sxs-lookup"><span data-stu-id="9b8a7-214">SPropProblemArray</span></span>](spropproblemarray.md)
  
[<span data-ttu-id="9b8a7-215">SPropTagArray</span><span class="sxs-lookup"><span data-stu-id="9b8a7-215">SPropTagArray</span></span>](sproptagarray.md)
  
[<span data-ttu-id="9b8a7-216">IMAPISupport : IUnknown</span><span class="sxs-lookup"><span data-stu-id="9b8a7-216">IMAPISupport : IUnknown</span></span>](imapisupportiunknown.md)

