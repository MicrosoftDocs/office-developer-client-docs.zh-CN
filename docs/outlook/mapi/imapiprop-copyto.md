---
title: IMAPIPropCopyTo
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIProp.CopyTo
api_type:
- COM
ms.assetid: e56042e9-5bb7-4a99-b6de-1546d4ca07f0
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: f76b0a5482647fe3e181a36d7dcd8cb60ffc8985
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32356390"
---
# <a name="imapipropcopyto"></a><span data-ttu-id="241a1-103">IMAPIProp::CopyTo</span><span class="sxs-lookup"><span data-stu-id="241a1-103">IMAPIProp::CopyTo</span></span>

  
  
<span data-ttu-id="241a1-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="241a1-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="241a1-105">复制或移动所有属性，但专门排除的属性除外。</span><span class="sxs-lookup"><span data-stu-id="241a1-105">Copies or moves all properties, except for specifically excluded properties.</span></span>
  
```cpp
HRESULT CopyTo(
 ULONG ciidExclude,
 LPCIID rgiidExclude,
 LPSPropTagArray lpExcludeProps,
 ULONG_PTR ulUIParam,
 LPMAPIPROGRESS lpProgress,
 LPCIID lpInterface,
 LPVOID lpDestObj,
 ULONG ulFlags,
 LPSPropProblemArray FAR * lppProblems
);
```

## <a name="parameters"></a><span data-ttu-id="241a1-106">参数</span><span class="sxs-lookup"><span data-stu-id="241a1-106">Parameters</span></span>

 <span data-ttu-id="241a1-107">_ciidExclude_</span><span class="sxs-lookup"><span data-stu-id="241a1-107">_ciidExclude_</span></span>
  
> <span data-ttu-id="241a1-108">[in]复制或移动属性时要排除的接口计数。</span><span class="sxs-lookup"><span data-stu-id="241a1-108">[in] The count of interfaces to exclude when properties are copied or moved.</span></span>
    
 <span data-ttu-id="241a1-109">_rgiidExclude_</span><span class="sxs-lookup"><span data-stu-id="241a1-109">_rgiidExclude_</span></span>
  
> <span data-ttu-id="241a1-110">[in]一组接口标识符 (IID) ，用于指定在将补充信息复制或移动到目标对象时不应使用的接口。</span><span class="sxs-lookup"><span data-stu-id="241a1-110">[in] An array of interface identifiers (IIDs) that specify interfaces that should not be used when supplemental information is copied or moved to the destination object.</span></span>
    
 <span data-ttu-id="241a1-111">_lpExcludeProps_</span><span class="sxs-lookup"><span data-stu-id="241a1-111">_lpExcludeProps_</span></span>
  
> <span data-ttu-id="241a1-112">[in]指向属性标记数组的指针，该数组标识应从复制或移动操作中排除的属性标记。</span><span class="sxs-lookup"><span data-stu-id="241a1-112">[in] A pointer to a property tag array that identifies the property tags that should be excluded from the copy or move operation.</span></span> <span data-ttu-id="241a1-113">在 _lpExcludeProps_ 参数中传递 **null** 指示应复制或移动对象的所有属性。</span><span class="sxs-lookup"><span data-stu-id="241a1-113">Passing **null** in the  _lpExcludeProps_ parameter indicates that all of the object's properties should be copied or moved.</span></span> <span data-ttu-id="241a1-114">**CopyTo** MAPI_E_INVALID_PARAMETER _lpExcludeProps_ 指向 [的 SPropProblemArray](spropproblemarray.md)结构的 **cValues** 成员设置为 0 时返回值。</span><span class="sxs-lookup"><span data-stu-id="241a1-114">**CopyTo** returns MAPI_E_INVALID_PARAMETER when the **cValues** member of the [SPropProblemArray](spropproblemarray.md) structure pointed to by  _lpExcludeProps_ is set to 0.</span></span> 
    
 <span data-ttu-id="241a1-115">_ulUIParam_</span><span class="sxs-lookup"><span data-stu-id="241a1-115">_ulUIParam_</span></span>
  
> <span data-ttu-id="241a1-116">[in]进度指示器的父窗口的句柄。</span><span class="sxs-lookup"><span data-stu-id="241a1-116">[in] A handle to the parent window of the progress indicator.</span></span> 
    
 <span data-ttu-id="241a1-117">_lpProgress_</span><span class="sxs-lookup"><span data-stu-id="241a1-117">_lpProgress_</span></span>
  
> <span data-ttu-id="241a1-118">[in]指向进度指示器实现的指针。</span><span class="sxs-lookup"><span data-stu-id="241a1-118">[in] A pointer to a progress indicator implementation.</span></span> <span data-ttu-id="241a1-119">如果在 _lpProgress_ 参数中传递 null，MAPI 将提供进度实现。</span><span class="sxs-lookup"><span data-stu-id="241a1-119">If **null** is passed in the  _lpProgress_ parameter, MAPI provides the progress implementation.</span></span> <span data-ttu-id="241a1-120">除非在 _ulFlags_ 参数中设置了 MAPI_DIALOG 标志，否则将忽略 _lpProgress_ 参数。</span><span class="sxs-lookup"><span data-stu-id="241a1-120">The  _lpProgress_ parameter is ignored unless the MAPI_DIALOG flag is set in the  _ulFlags_ parameter.</span></span> 
    
 <span data-ttu-id="241a1-121">_lpInterface_</span><span class="sxs-lookup"><span data-stu-id="241a1-121">_lpInterface_</span></span>
  
> <span data-ttu-id="241a1-122">[in]指向接口标识符 (IID) 表示用于访问  _lpDestObj_ 参数指向的对象的接口的指针。</span><span class="sxs-lookup"><span data-stu-id="241a1-122">[in] A pointer to the interface identifier (IID) that represents the interface to be used to access the object pointed to by the  _lpDestObj_ parameter.</span></span> <span data-ttu-id="241a1-123">_lpInterface_ 参数不能为 **null**。</span><span class="sxs-lookup"><span data-stu-id="241a1-123">The  _lpInterface_ parameter must not be **null**.</span></span>
    
 <span data-ttu-id="241a1-124">_lpDestObj_</span><span class="sxs-lookup"><span data-stu-id="241a1-124">_lpDestObj_</span></span>
  
> <span data-ttu-id="241a1-125">[in]指向接收复制或移动的属性的对象的指针。</span><span class="sxs-lookup"><span data-stu-id="241a1-125">[in] A pointer to the object to receive the copied or moved properties.</span></span>
    
 <span data-ttu-id="241a1-126">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="241a1-126">_ulFlags_</span></span>
  
> <span data-ttu-id="241a1-127">[in]控制复制或移动操作的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="241a1-127">[in] A bitmask of flags that controls the copy or move operation.</span></span> <span data-ttu-id="241a1-128">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="241a1-128">The following flags can be set:</span></span>
    
<span data-ttu-id="241a1-129">MAPI_DECLINE_OK</span><span class="sxs-lookup"><span data-stu-id="241a1-129">MAPI_DECLINE_OK</span></span> 
  
> <span data-ttu-id="241a1-130">如果 **CopyTo** 调用 [IMAPISupport：:D oCopyTo](imapisupport-docopyto.md) 方法来处理复制或移动操作，它应改为立即返回错误值 MAPI_E_DECLINE_COPY。</span><span class="sxs-lookup"><span data-stu-id="241a1-130">If **CopyTo** calls the [IMAPISupport::DoCopyTo](imapisupport-docopyto.md) method to handle the copy or move operation, it should instead return immediately with the error value MAPI_E_DECLINE_COPY.</span></span> <span data-ttu-id="241a1-131">MAPI MAPI_DECLINE_OK设置值以限制递归。</span><span class="sxs-lookup"><span data-stu-id="241a1-131">The MAPI_DECLINE_OK flag is set by MAPI to limit recursion.</span></span> <span data-ttu-id="241a1-132">客户端不设置此标志。</span><span class="sxs-lookup"><span data-stu-id="241a1-132">Clients do not set this flag.</span></span> 
    
<span data-ttu-id="241a1-133">MAPI_DIALOG</span><span class="sxs-lookup"><span data-stu-id="241a1-133">MAPI_DIALOG</span></span> 
  
> <span data-ttu-id="241a1-134">显示进度指示器。</span><span class="sxs-lookup"><span data-stu-id="241a1-134">Displays a progress indicator.</span></span>
    
<span data-ttu-id="241a1-135">MAPI_MOVE</span><span class="sxs-lookup"><span data-stu-id="241a1-135">MAPI_MOVE</span></span> 
  
> <span data-ttu-id="241a1-136">**CopyTo** 应执行移动操作，而不是复制操作。</span><span class="sxs-lookup"><span data-stu-id="241a1-136">**CopyTo** should perform a move operation instead of a copy operation.</span></span> <span data-ttu-id="241a1-137">未设置此标志时 **，CopyTo** 将执行复制操作。</span><span class="sxs-lookup"><span data-stu-id="241a1-137">When this flag is not set, **CopyTo** performs a copy operation.</span></span> 
    
<span data-ttu-id="241a1-138">MAPI_NOREPLACE</span><span class="sxs-lookup"><span data-stu-id="241a1-138">MAPI_NOREPLACE</span></span> 
  
> <span data-ttu-id="241a1-139">不应覆盖目标对象中的现有属性。</span><span class="sxs-lookup"><span data-stu-id="241a1-139">Existing properties in the destination object should not be overwritten.</span></span> <span data-ttu-id="241a1-140">未设置此标志时 **，CopyTo** 将覆盖现有属性。</span><span class="sxs-lookup"><span data-stu-id="241a1-140">When this flag is not set, **CopyTo** overwrites existing properties.</span></span> 
    
 <span data-ttu-id="241a1-141">_lppProblems_</span><span class="sxs-lookup"><span data-stu-id="241a1-141">_lppProblems_</span></span>
  
> <span data-ttu-id="241a1-142">[in， out]在输入时，指向指向 **SPropProblemArray 结构的指针的** 指针;否则为 **null**，表示不需要错误信息。</span><span class="sxs-lookup"><span data-stu-id="241a1-142">[in, out] On input, a pointer to a pointer to an **SPropProblemArray** structure; otherwise, **null**, indicating no need for error information.</span></span> <span data-ttu-id="241a1-143">如果  _lppProblems_ 是输入的有效指针 **，CopyTo** 将返回有关复制一个或多个属性时错误的详细信息。</span><span class="sxs-lookup"><span data-stu-id="241a1-143">If  _lppProblems_ is a valid pointer on input, **CopyTo** returns detailed information about errors in copying one or more properties.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="241a1-144">返回值</span><span class="sxs-lookup"><span data-stu-id="241a1-144">Return value</span></span>

<span data-ttu-id="241a1-145">S_OK</span><span class="sxs-lookup"><span data-stu-id="241a1-145">S_OK</span></span> 
  
> <span data-ttu-id="241a1-146">已成功复制或移动属性。</span><span class="sxs-lookup"><span data-stu-id="241a1-146">The properties have been successfully copied or moved.</span></span>
    
<span data-ttu-id="241a1-147">MAPI_E_COLLISION</span><span class="sxs-lookup"><span data-stu-id="241a1-147">MAPI_E_COLLISION</span></span> 
  
> <span data-ttu-id="241a1-148">无法复制子对象，因为目标对象中已存在具有同一 显示名称 的子对象（由 **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 属性指定）。</span><span class="sxs-lookup"><span data-stu-id="241a1-148">A subobject cannot be copied because a subobject with the same display name — specified by the **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) property — already exists in the destination object.</span></span> 
    
<span data-ttu-id="241a1-149">MAPI_E_DECLINE_COPY</span><span class="sxs-lookup"><span data-stu-id="241a1-149">MAPI_E_DECLINE_COPY</span></span> 
  
> <span data-ttu-id="241a1-150">服务提供商不实现复制操作。</span><span class="sxs-lookup"><span data-stu-id="241a1-150">The service provider does not implement the copy operation.</span></span>
    
<span data-ttu-id="241a1-151">MAPI_E_FOLDER_CYCLE</span><span class="sxs-lookup"><span data-stu-id="241a1-151">MAPI_E_FOLDER_CYCLE</span></span> 
  
> <span data-ttu-id="241a1-152">执行复制或移动操作的来源对象直接或间接包含目标对象。</span><span class="sxs-lookup"><span data-stu-id="241a1-152">The source object performing the copy or move operation directly or indirectly contains the destination object.</span></span> <span data-ttu-id="241a1-153">在发现此条件之前，可能执行了大量工作，因此可能会部分修改源对象和目标对象。</span><span class="sxs-lookup"><span data-stu-id="241a1-153">Significant work might have been performed before this condition was discovered, so the source and destination objects might be partially modified.</span></span> 
    
<span data-ttu-id="241a1-154">MAPI_E_INTERFACE_NOT_SUPPORTED</span><span class="sxs-lookup"><span data-stu-id="241a1-154">MAPI_E_INTERFACE_NOT_SUPPORTED</span></span> 
  
> <span data-ttu-id="241a1-155">目标对象不支持由  _lpInterface_ 参数标识的接口。</span><span class="sxs-lookup"><span data-stu-id="241a1-155">The interface identified by the  _lpInterface_ parameter is not supported by the destination object.</span></span> 
    
<span data-ttu-id="241a1-156">MAPI_E_NO_ACCESS</span><span class="sxs-lookup"><span data-stu-id="241a1-156">MAPI_E_NO_ACCESS</span></span> 
  
> <span data-ttu-id="241a1-157">试图访问调用方权限不足的对象。</span><span class="sxs-lookup"><span data-stu-id="241a1-157">An attempt was made to access an object for which the caller has insufficient permissions.</span></span> <span data-ttu-id="241a1-158">如果目标对象与源对象相同，则返回此错误。</span><span class="sxs-lookup"><span data-stu-id="241a1-158">This error is returned if the destination object is the same as the source object.</span></span>
    
<span data-ttu-id="241a1-159">以下值可以在 **SPropProblemArray** 结构中返回，但不能作为 **CopyTo 的返回值**。</span><span class="sxs-lookup"><span data-stu-id="241a1-159">The following values can be returned in the **SPropProblemArray** structure, but not as return values for **CopyTo**.</span></span> <span data-ttu-id="241a1-160">以下错误适用于单个属性：</span><span class="sxs-lookup"><span data-stu-id="241a1-160">The following errors apply to a single property:</span></span>
  
<span data-ttu-id="241a1-161">MAPI_E_BAD_CHARWIDTH</span><span class="sxs-lookup"><span data-stu-id="241a1-161">MAPI_E_BAD_CHARWIDTH</span></span> 
  
> <span data-ttu-id="241a1-162">设置MAPI_UNICODE **CopyTo** 不支持 Unicode，或者未MAPI_UNICODE **CopyTo** 仅支持 Unicode。</span><span class="sxs-lookup"><span data-stu-id="241a1-162">Either the MAPI_UNICODE flag was set and **CopyTo** does not support Unicode, or MAPI_UNICODE was not set and **CopyTo** supports only Unicode.</span></span> 
    
<span data-ttu-id="241a1-163">MAPI_E_COMPUTED</span><span class="sxs-lookup"><span data-stu-id="241a1-163">MAPI_E_COMPUTED</span></span> 
  
> <span data-ttu-id="241a1-164">调用方无法修改该属性，因为它是一个只读属性，由目标对象的所有者计算。</span><span class="sxs-lookup"><span data-stu-id="241a1-164">The property cannot be modified by the caller because it is a read-only property, computed by the owner of the destination object.</span></span> <span data-ttu-id="241a1-165">此错误并不严重;调用方应允许复制操作继续。</span><span class="sxs-lookup"><span data-stu-id="241a1-165">This error is not severe; the caller should allow the copy operation to continue.</span></span>
    
<span data-ttu-id="241a1-166">MAPI_E_INVALID_TYPE</span><span class="sxs-lookup"><span data-stu-id="241a1-166">MAPI_E_INVALID_TYPE</span></span> 
  
> <span data-ttu-id="241a1-167">属性类型无效。</span><span class="sxs-lookup"><span data-stu-id="241a1-167">The property type is invalid.</span></span>
    
<span data-ttu-id="241a1-168">MAPI_E_UNEXPECTED_TYPE</span><span class="sxs-lookup"><span data-stu-id="241a1-168">MAPI_E_UNEXPECTED_TYPE</span></span> 
  
> <span data-ttu-id="241a1-169">属性类型不是调用方预期的类型。</span><span class="sxs-lookup"><span data-stu-id="241a1-169">The property type is not the type expected by the caller.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="241a1-170">备注</span><span class="sxs-lookup"><span data-stu-id="241a1-170">Remarks</span></span>

<span data-ttu-id="241a1-171">默认情况下 **，IMAPIProp：：CopyTo** 方法将当前对象的所有属性复制或移动到目标对象。</span><span class="sxs-lookup"><span data-stu-id="241a1-171">By default, the **IMAPIProp::CopyTo** method copies or moves all of the current object's properties to a destination object.</span></span> <span data-ttu-id="241a1-172">**CopyTo** 用于完全复制或移动对象，其所有或大部分属性保持不变。</span><span class="sxs-lookup"><span data-stu-id="241a1-172">**CopyTo** is used when an object should be copied or moved exactly, with all or most of its properties intact.</span></span> 
  
<span data-ttu-id="241a1-173">源对象中任何子对象都将自动包含在操作中，并全部复制或移动。</span><span class="sxs-lookup"><span data-stu-id="241a1-173">Any subobjects in the source object are automatically included in the operation and are copied or moved in their entirety.</span></span> <span data-ttu-id="241a1-174">默认情况下 **，CopyTo** 覆盖目标对象中与源对象中的属性匹配的任何属性。</span><span class="sxs-lookup"><span data-stu-id="241a1-174">By default, **CopyTo** overwrites any properties in the destination object that match properties from the source object.</span></span> <span data-ttu-id="241a1-175">如果目标对象中已存在任何复制或移动的属性，则现有属性将被新属性覆盖，除非在  _ulFlags_ 参数中设置了 MAPI_NOREPLACE 标志。</span><span class="sxs-lookup"><span data-stu-id="241a1-175">If any of the copied or moved properties already exist in the destination object, the existing properties are overwritten by the new properties, unless the MAPI_NOREPLACE flag is set in the  _ulFlags_ parameter.</span></span> <span data-ttu-id="241a1-176">目标对象中未覆盖的现有信息保持不变。</span><span class="sxs-lookup"><span data-stu-id="241a1-176">Existing information in the destination object that is not overwritten is left untouched.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="241a1-177">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="241a1-177">Notes to implementers</span></span>

<span data-ttu-id="241a1-178">你可以提供 **CopyTo** 的完整实现或依赖于 MAPI 在其支持对象中提供的实现。</span><span class="sxs-lookup"><span data-stu-id="241a1-178">You can provide a full implementation of **CopyTo** or rely on the implementation that MAPI provides in its support object.</span></span> <span data-ttu-id="241a1-179">如果要使用 MAPI 实现，请调用 **IMAPISupport：:D oCopyTo**。</span><span class="sxs-lookup"><span data-stu-id="241a1-179">If you want to use the MAPI implementation, call **IMAPISupport::DoCopyTo**.</span></span> <span data-ttu-id="241a1-180">但是，如果您将处理委派给 **DoCopyTo，** 并且您被传递到 MAPI_DECLINE_OK 标志，请避免致电支持人员，并MAPI_E_DECLINE_COPY消息。</span><span class="sxs-lookup"><span data-stu-id="241a1-180">However, if you do delegate processing to **DoCopyTo** and you are passed the MAPI_DECLINE_OK flag, avoid the support call and return MAPI_E_DECLINE_COPY instead.</span></span> <span data-ttu-id="241a1-181">MAPI 将调用此标志以避免复制文件夹时可能发生的递归。</span><span class="sxs-lookup"><span data-stu-id="241a1-181">MAPI will call with this flag to avoid the possible recursion that can happen when folders are copied.</span></span> 
  
<span data-ttu-id="241a1-182">由于复制操作可能很长，因此应显示进度指示器。</span><span class="sxs-lookup"><span data-stu-id="241a1-182">Because the copy operation can be lengthy, you should display a progress indicator.</span></span> <span data-ttu-id="241a1-183">使用 [在 lpProgress](imapiprogressiunknown.md) 参数中传递的  _IMAPIProgress_ 实现（如果有）。</span><span class="sxs-lookup"><span data-stu-id="241a1-183">Use the [IMAPIProgress](imapiprogressiunknown.md) implementation passed in the  _lpProgress_ parameter, if there is one.</span></span> <span data-ttu-id="241a1-184">如果  _lpProgress_ 为 **null，** 则调用 [IMAPISupport：:D oProgressDialog](imapisupport-doprogressdialog.md) 方法以使用 MAPI 实现。</span><span class="sxs-lookup"><span data-stu-id="241a1-184">If  _lpProgress_ is **null**, call the [IMAPISupport::DoProgressDialog](imapisupport-doprogressdialog.md) method to use the MAPI implementation.</span></span> 
  
<span data-ttu-id="241a1-185">不要尝试在目标对象中设置任何已知的只读属性;返回MAPI_E_NO_ACCESS。</span><span class="sxs-lookup"><span data-stu-id="241a1-185">Do not attempt to set any known read-only properties in the destination object; return MAPI_E_NO_ACCESS instead.</span></span>
  
<span data-ttu-id="241a1-186">源对象和目标对象应使用相同的接口。</span><span class="sxs-lookup"><span data-stu-id="241a1-186">The source and destination objects should use the same interfaces.</span></span> <span data-ttu-id="241a1-187">如果未MAPI_E_INVALID_PARAMETER  _lpInterface，_ 则返回值。</span><span class="sxs-lookup"><span data-stu-id="241a1-187">Return MAPI_E_INVALID_PARAMETER if  _lpInterface_ is not set.</span></span> 
  
<span data-ttu-id="241a1-188">如果MAPI_E_INTERFACE_NOT_SUPPORTED所有已知接口，则返回返回值。</span><span class="sxs-lookup"><span data-stu-id="241a1-188">Return MAPI_E_INTERFACE_NOT_SUPPORTED if all known interfaces are excluded.</span></span>
  
## <a name="notes-to-callers"></a><span data-ttu-id="241a1-189">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="241a1-189">Notes to callers</span></span>

<span data-ttu-id="241a1-190">不要设置MAPI_DECLINE_OK标志;MAPI 在消息存储提供程序 CopyTo 实现调用 **中使用它** 。</span><span class="sxs-lookup"><span data-stu-id="241a1-190">Do not set the MAPI_DECLINE_OK flag; MAPI uses it in its calls to message store provider **CopyTo** implementations.</span></span> 
  
<span data-ttu-id="241a1-191">由于复制和移动操作可能需要一些时间，因此应该通过设置进度指示器标记来MAPI_DIALOG显示。</span><span class="sxs-lookup"><span data-stu-id="241a1-191">Because copy and move operations can take time, you should request the display of a progress indicator by setting the MAPI_DIALOG flag.</span></span> <span data-ttu-id="241a1-192">可以将  _lpProgress_ 参数设置为 **IMAPIProgress** 的实现（如果有）或 **设置为 null**。</span><span class="sxs-lookup"><span data-stu-id="241a1-192">You can set the  _lpProgress_ parameter to your implementation of **IMAPIProgress**, if you have one, or to **null**.</span></span> <span data-ttu-id="241a1-193">如果 _lpProgress_ **为 null，\*\*\*\*则 CopyTo** 将使用 MAPI 提供的默认进度指示器。</span><span class="sxs-lookup"><span data-stu-id="241a1-193">If  _lpProgress_ is **null**, **CopyTo** will use the default progress indicator that MAPI provides.</span></span> 
  
<span data-ttu-id="241a1-194">可以通过不设置进度指示器标记来禁止显示MAPI_DIALOG标记。</span><span class="sxs-lookup"><span data-stu-id="241a1-194">You can suppress the display of a progress indicator by not setting the MAPI_DIALOG flag.</span></span> <span data-ttu-id="241a1-195">**CopyTo** 将忽略  _ulUIParam_ 和  _lpProgress_ 参数，并且不显示指示器。</span><span class="sxs-lookup"><span data-stu-id="241a1-195">**CopyTo** will ignore the  _ulUIParam_ and  _lpProgress_ parameters and will not display the indicator.</span></span> 
  
 <span data-ttu-id="241a1-196">**CopyTo** 可以报告全局和单个错误，或者一个或多个属性发生的错误。</span><span class="sxs-lookup"><span data-stu-id="241a1-196">**CopyTo** can report global and individual errors, or errors that occur with one or more properties.</span></span> <span data-ttu-id="241a1-197">这些单个错误放置在 **SPropProblemArray** 结构中。</span><span class="sxs-lookup"><span data-stu-id="241a1-197">These individual errors are placed in an **SPropProblemArray** structure.</span></span> <span data-ttu-id="241a1-198">可以通过为属性问题数组结构参数传递 **null（** 而不是有效指针）来禁止在属性级别报告错误。</span><span class="sxs-lookup"><span data-stu-id="241a1-198">You can suppress error reporting at the property level by passing **null**, instead of a valid pointer, for the property problem array structure parameter.</span></span> 
  
<span data-ttu-id="241a1-199">如果要接收有关错误的信息，请传递 _lppProblems_ 参数中的有效 **SPropProblemArray** 结构指针。</span><span class="sxs-lookup"><span data-stu-id="241a1-199">If you want to receive information about errors, pass a valid **SPropProblemArray** structure pointer in the  _lppProblems_ parameter.</span></span> <span data-ttu-id="241a1-200">当 **CopyTo** 返回S_OK时，请检查结构中各个属性的可能错误。</span><span class="sxs-lookup"><span data-stu-id="241a1-200">When **CopyTo** returns S_OK, check for possible errors with individual properties in the structure.</span></span> <span data-ttu-id="241a1-201">当 **CopyTo** 返回错误时 **，SPropProblemArray** 结构中不会返回任何信息。</span><span class="sxs-lookup"><span data-stu-id="241a1-201">When **CopyTo** returns an error, no information is returned in the **SPropProblemArray** structure.</span></span> <span data-ttu-id="241a1-202">相反，调用 [IMAPIProp：：GetLastError](imapiprop-getlasterror.md) 以检索详细的错误信息。</span><span class="sxs-lookup"><span data-stu-id="241a1-202">Instead, call [IMAPIProp::GetLastError](imapiprop-getlasterror.md) to retrieve detailed error information.</span></span> 
  
<span data-ttu-id="241a1-203">如果 **CopyTo** S_OK，请通过调用 [MAPIFreeBuffer](mapifreebuffer.md)函数释放返回的 **SPropProblemArray** 结构。</span><span class="sxs-lookup"><span data-stu-id="241a1-203">If **CopyTo** returns S_OK, free the returned **SPropProblemArray** structure by calling the [MAPIFreeBuffer](mapifreebuffer.md) function.</span></span> 
  
<span data-ttu-id="241a1-204">如果复制源对象特有的属性对象类型，必须确保目标对象的类型相同。</span><span class="sxs-lookup"><span data-stu-id="241a1-204">If you copy properties that are unique to the source object type, you must ensure that the destination object is of the same type.</span></span> <span data-ttu-id="241a1-205">**CopyTo** 不会阻止您将通常属于一种对象类型的属性与另一种类型的对象关联。</span><span class="sxs-lookup"><span data-stu-id="241a1-205">**CopyTo** does not prevent you from associating properties that typically belong to one type of object with another type of object.</span></span> <span data-ttu-id="241a1-206">由你复制对目标对象有意义的属性。</span><span class="sxs-lookup"><span data-stu-id="241a1-206">It is up to you to copy properties that make sense for the destination object.</span></span> <span data-ttu-id="241a1-207">例如，不应将邮件属性复制到通讯簿容器。</span><span class="sxs-lookup"><span data-stu-id="241a1-207">For example, you should not copy message properties to an address book container.</span></span> 
  
<span data-ttu-id="241a1-208">若要确保在相同类型的对象之间复制，请检查源对象和目标对象是否相同，方法为比较对象指针或调用[IUnknown：：QueryInterface。](https://msdn.microsoft.com/library/ms682521%28v=VS.85%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="241a1-208">To ensure that you copy between objects of the same type, check that the source and destination object are the same type, either by comparing object pointers or calling [IUnknown::QueryInterface](https://msdn.microsoft.com/library/ms682521%28v=VS.85%29.aspx).</span></span> <span data-ttu-id="241a1-209">将  _lpInterface_ 指向的接口标识符设置为源对象的标准接口。</span><span class="sxs-lookup"><span data-stu-id="241a1-209">Set the interface identifier pointed to by  _lpInterface_ to the standard interface for the source object.</span></span> <span data-ttu-id="241a1-210">此外，请确保 PidTagObjectType对象类型 或 PR_OBJECT_TYPE ([PidTagObjectType](pidtagobjecttype-canonical-property.md)) 属性是相同的。</span><span class="sxs-lookup"><span data-stu-id="241a1-210">Also, be sure that the object type or **PR_OBJECT_TYPE** ([PidTagObjectType](pidtagobjecttype-canonical-property.md)) property is the same for the two objects.</span></span> <span data-ttu-id="241a1-211">例如，如果从邮件中复制，将 _lpInterface_ 设置为 IID_IMessage，PR_OBJECT_TYPE两个对象的 MAPI_MESSAGE。</span><span class="sxs-lookup"><span data-stu-id="241a1-211">For example, if you copy from a message, set  _lpInterface_ to IID_IMessage and the **PR_OBJECT_TYPE** for both objects to MAPI_MESSAGE.</span></span> 
  
<span data-ttu-id="241a1-212">如果在  _lpDestObj_ 参数中传递无效指针，则结果不可预测。</span><span class="sxs-lookup"><span data-stu-id="241a1-212">If an invalid pointer is passed in the  _lpDestObj_ parameter, the results are unpredictable.</span></span> 
  
<span data-ttu-id="241a1-213">在 **CopyTo 调用中排除** 属性可能很有用。</span><span class="sxs-lookup"><span data-stu-id="241a1-213">Excluding properties on a **CopyTo** call can be useful.</span></span> <span data-ttu-id="241a1-214">例如，某些对象具有特定于对象的单个实例的属性，如邮件传递的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="241a1-214">For example, some objects have properties that are specific to a single instance of the object, such as the date and time of message delivery.</span></span> <span data-ttu-id="241a1-215">为避免在将邮件复制到其他文件夹时复制邮件的传递时间，请指定 **PR_MESSAGE_DELIVERY_TIME** ([PidTagMessageDeliveryTime](pidtagmessagedeliverytime-canonical-property.md)) 属性标记排除数组。</span><span class="sxs-lookup"><span data-stu-id="241a1-215">To avoid copying a message's delivery time when you copy the message to a different folder, specify **PR_MESSAGE_DELIVERY_TIME** ([PidTagMessageDeliveryTime](pidtagmessagedeliverytime-canonical-property.md)) in the property tag exclude array.</span></span> <span data-ttu-id="241a1-216">若要排除邮件的收件人列表，PR_MESSAGE_RECIPIENTS ([PidTagMessageRecipients) PidTagMessageRecipients](pidtagmessagerecipients-canonical-property.md)属性添加到排除数组。 </span><span class="sxs-lookup"><span data-stu-id="241a1-216">To exclude a message's recipient list, add the **PR_MESSAGE_RECIPIENTS** ([PidTagMessageRecipients](pidtagmessagerecipients-canonical-property.md)) property to the exclude array.</span></span> <span data-ttu-id="241a1-217">若要排除邮件的附件，PR_MESSAGE_ATTACHMENTS ([PidTagMessageAttachments](pidtagmessageattachments-canonical-property.md)) 添加到数组。 </span><span class="sxs-lookup"><span data-stu-id="241a1-217">To exclude a message's attachments, add the **PR_MESSAGE_ATTACHMENTS** ([PidTagMessageAttachments](pidtagmessageattachments-canonical-property.md)) property to the array.</span></span>
  
<span data-ttu-id="241a1-218">同样，在属性标记排除数组中包括 **PR_CONTAINER_HIERARCHY** ([PidTagContainerHierarchy](pidtagcontainerhierarchy-canonical-property.md)) 或 **PR_CONTAINER_CONTENTS** ([PidTagContainerContents](pidtagcontainercontents-canonical-property.md)) ，防止复制或移动文件夹或通讯簿容器的层次结构或内容表。</span><span class="sxs-lookup"><span data-stu-id="241a1-218">Similarly, prevent the copying or moving of a folder or address book container's hierarchy or contents table by including **PR_CONTAINER_HIERARCHY** ([PidTagContainerHierarchy](pidtagcontainerhierarchy-canonical-property.md)) or **PR_CONTAINER_CONTENTS** ([PidTagContainerContents](pidtagcontainercontents-canonical-property.md)) in the property tag exclude array.</span></span>
  
<span data-ttu-id="241a1-219">若要从复制或移动操作中排除属性，请将其属性标记包括在  _lpExcludeProps_ 参数中。</span><span class="sxs-lookup"><span data-stu-id="241a1-219">To exclude properties from the copy or move operation, include their property tags in the  _lpExcludeProps_ parameter.</span></span> <span data-ttu-id="241a1-220">如果传递 PROP_TAG 宏的结果，以从属性标记数组中的特定标识符构建属性标记，那么将排除具有该标识符的所有属性。</span><span class="sxs-lookup"><span data-stu-id="241a1-220">If you pass the results of the **PROP_TAG** macro to build a property tag from a specific identifier in the property tag array, all properties with that identifier will be excluded.</span></span> <span data-ttu-id="241a1-221">例如，属性标记数组中的以下条目会导致排除标识符为 0x8002的所有属性，无论类型如何：</span><span class="sxs-lookup"><span data-stu-id="241a1-221">For example, the following entry in the property tag array causes all properties with an identifier of 0x8002 to be excluded, regardless of type:</span></span> 
  
 `PROP_TAG(PT_LONG, 0x8002)`
  
<span data-ttu-id="241a1-222">_lpExcludeProps_ PR_NULL ([PidTagNull](pidtagnull-canonical-property.md)) 属性标记中。 </span><span class="sxs-lookup"><span data-stu-id="241a1-222">The **PR_NULL** ([PidTagNull](pidtagnull-canonical-property.md)) property tag cannot be included in the  _lpExcludeProps_ array.</span></span> 
  
<span data-ttu-id="241a1-223">**CopyTo** 功能用于排除接口的实用性可能没有排除属性的有用性那么明显。</span><span class="sxs-lookup"><span data-stu-id="241a1-223">The usefulness of the **CopyTo** feature for excluding interfaces is perhaps not as obvious as the usefulness of excluding properties.</span></span> <span data-ttu-id="241a1-224">当复制到一个不了解一组属性的对象时，可以排除接口。</span><span class="sxs-lookup"><span data-stu-id="241a1-224">You can exclude an interface when you copy to an object that has no knowledge of a group of properties.</span></span> <span data-ttu-id="241a1-225">例如，如果将属性从文件夹复制到附件，则附件可以使用的唯一属性是可用于 [任何 IMAPIProp](imapipropiunknown.md) 实现的通用属性。</span><span class="sxs-lookup"><span data-stu-id="241a1-225">For example, if you copy properties from a folder to an attachment, the only properties that the attachment can work with are the generic properties available with any [IMAPIProp](imapipropiunknown.md) implementation.</span></span> <span data-ttu-id="241a1-226">通过从 [复制操作中排除 IMAPIFolder，](imapifolderimapicontainer.md) 附件将不会收到任何更具体的文件夹属性。</span><span class="sxs-lookup"><span data-stu-id="241a1-226">By excluding [IMAPIFolder](imapifolderimapicontainer.md) from the copy operation, the attachment will not receive any of the more specific folder properties.</span></span> 
  
<span data-ttu-id="241a1-227">使用  _rgiidExclude_ 参数排除接口时，它还排除从该接口派生的所有接口。</span><span class="sxs-lookup"><span data-stu-id="241a1-227">When you use the  _rgiidExclude_ parameter to exclude an interface, it also excludes all interfaces derived from that interface.</span></span> <span data-ttu-id="241a1-228">例如，排除 [IMAPIContainer](imapicontainerimapiprop.md) 会导致排除文件夹或通讯簿容器，具体取决于提供程序的类型。</span><span class="sxs-lookup"><span data-stu-id="241a1-228">For example, excluding [IMAPIContainer](imapicontainerimapiprop.md) causes folders or address book containers to be excluded, depending on the type of provider.</span></span> <span data-ttu-id="241a1-229">不要排除 **IMAPIProp** 或 [IUnknown，](https://msdn.microsoft.com/library/ms680509%28v=VS.85%29.aspx) 因为有很多接口派生自它们。</span><span class="sxs-lookup"><span data-stu-id="241a1-229">Do not exclude **IMAPIProp** or [IUnknown](https://msdn.microsoft.com/library/ms680509%28v=VS.85%29.aspx) because so many interfaces derive from them.</span></span> 
  
<span data-ttu-id="241a1-230">忽略MAPI_E_COMPUTED _lppProblems_ 参数 **的 SPropProblemArray** 结构中返回的错误。</span><span class="sxs-lookup"><span data-stu-id="241a1-230">Ignore MAPI_E_COMPUTED errors returned in the **SPropProblemArray** structure in the  _lppProblems_ parameter.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="241a1-231">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="241a1-231">MFCMAPI reference</span></span>

<span data-ttu-id="241a1-232">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="241a1-232">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="241a1-233">**文件**</span><span class="sxs-lookup"><span data-stu-id="241a1-233">**File**</span></span>|<span data-ttu-id="241a1-234">**函数**</span><span class="sxs-lookup"><span data-stu-id="241a1-234">**Function**</span></span>|<span data-ttu-id="241a1-235">**备注**</span><span class="sxs-lookup"><span data-stu-id="241a1-235">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="241a1-236">File.cpp</span><span class="sxs-lookup"><span data-stu-id="241a1-236">File.cpp</span></span>  <br/> |<span data-ttu-id="241a1-237">LoadFromMSG</span><span class="sxs-lookup"><span data-stu-id="241a1-237">LoadFromMSG</span></span>  <br/> |<span data-ttu-id="241a1-238">MFCMAPI 使用 **IMAPIProp：：CopyTo** 方法将属性从 .msg 文件复制到 [IMAPIMessageSite](imapimessagesiteiunknown.md) 对象。</span><span class="sxs-lookup"><span data-stu-id="241a1-238">MFCMAPI uses the **IMAPIProp::CopyTo** method to copy properties from a .msg file to an [IMAPIMessageSite](imapimessagesiteiunknown.md) object.</span></span>  <br/> |
|<span data-ttu-id="241a1-239">FolderDlg.cpp</span><span class="sxs-lookup"><span data-stu-id="241a1-239">FolderDlg.cpp</span></span>  <br/> |<span data-ttu-id="241a1-240">CFolderDlg：：HandlePaste</span><span class="sxs-lookup"><span data-stu-id="241a1-240">CFolderDlg::HandlePaste</span></span>  <br/> |<span data-ttu-id="241a1-241">在粘贴操作期间，MFCMAPI 使用 **IMAPIProp：：CopyTo** 方法将属性从源邮件复制到目标邮件。</span><span class="sxs-lookup"><span data-stu-id="241a1-241">MFCMAPI uses the **IMAPIProp::CopyTo** method to copy properties from a source message to a target message during a paste operation.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="241a1-242">另请参阅</span><span class="sxs-lookup"><span data-stu-id="241a1-242">See also</span></span>



[<span data-ttu-id="241a1-243">IMAPIFolder::CopyMessages</span><span class="sxs-lookup"><span data-stu-id="241a1-243">IMAPIFolder::CopyMessages</span></span>](imapifolder-copymessages.md)
  
[<span data-ttu-id="241a1-244">IMAPIProp::GetLastError</span><span class="sxs-lookup"><span data-stu-id="241a1-244">IMAPIProp::GetLastError</span></span>](imapiprop-getlasterror.md)
  
[<span data-ttu-id="241a1-245">IMAPIMessageSite : IUnknown</span><span class="sxs-lookup"><span data-stu-id="241a1-245">IMAPIMessageSite : IUnknown</span></span>](imapimessagesiteiunknown.md)
  
[<span data-ttu-id="241a1-246">IMAPIProgress : IUnknown</span><span class="sxs-lookup"><span data-stu-id="241a1-246">IMAPIProgress : IUnknown</span></span>](imapiprogressiunknown.md)
  
[<span data-ttu-id="241a1-247">IMAPISupport::DoProgressDialog</span><span class="sxs-lookup"><span data-stu-id="241a1-247">IMAPISupport::DoProgressDialog</span></span>](imapisupport-doprogressdialog.md)
  
[<span data-ttu-id="241a1-248">IMAPISupport::DoCopyTo</span><span class="sxs-lookup"><span data-stu-id="241a1-248">IMAPISupport::DoCopyTo</span></span>](imapisupport-docopyto.md)
  
[<span data-ttu-id="241a1-249">MAPIFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="241a1-249">MAPIFreeBuffer</span></span>](mapifreebuffer.md)
  
[<span data-ttu-id="241a1-250">PidTagContainerContents 规范属性</span><span class="sxs-lookup"><span data-stu-id="241a1-250">PidTagContainerContents Canonical Property</span></span>](pidtagcontainercontents-canonical-property.md)
  
[<span data-ttu-id="241a1-251">PidTagContainerHierarchy 规范属性</span><span class="sxs-lookup"><span data-stu-id="241a1-251">PidTagContainerHierarchy Canonical Property</span></span>](pidtagcontainerhierarchy-canonical-property.md)
  
[<span data-ttu-id="241a1-252">PidTagMessageAttachments 规范属性</span><span class="sxs-lookup"><span data-stu-id="241a1-252">PidTagMessageAttachments Canonical Property</span></span>](pidtagmessageattachments-canonical-property.md)
  
[<span data-ttu-id="241a1-253">PidTagMessageDeliveryTime 规范属性</span><span class="sxs-lookup"><span data-stu-id="241a1-253">PidTagMessageDeliveryTime Canonical Property</span></span>](pidtagmessagedeliverytime-canonical-property.md)
  
[<span data-ttu-id="241a1-254">PidTagMessageRecipients 规范属性</span><span class="sxs-lookup"><span data-stu-id="241a1-254">PidTagMessageRecipients Canonical Property</span></span>](pidtagmessagerecipients-canonical-property.md)
  
[<span data-ttu-id="241a1-255">PidTagObjectType 规范属性</span><span class="sxs-lookup"><span data-stu-id="241a1-255">PidTagObjectType Canonical Property</span></span>](pidtagobjecttype-canonical-property.md)
  
[<span data-ttu-id="241a1-256">SPropProblemArray</span><span class="sxs-lookup"><span data-stu-id="241a1-256">SPropProblemArray</span></span>](spropproblemarray.md)
  
[<span data-ttu-id="241a1-257">SPropTagArray</span><span class="sxs-lookup"><span data-stu-id="241a1-257">SPropTagArray</span></span>](sproptagarray.md)
  
[<span data-ttu-id="241a1-258">IMAPIProp : IUnknown</span><span class="sxs-lookup"><span data-stu-id="241a1-258">IMAPIProp : IUnknown</span></span>](imapipropiunknown.md)


[<span data-ttu-id="241a1-259">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="241a1-259">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

