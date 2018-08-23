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
ms.openlocfilehash: bbc9dcf2218907b5d31ce1fc9f904e6ae1da47d9
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22594010"
---
# <a name="imapipropcopyto"></a><span data-ttu-id="2bf52-103">IMAPIProp::CopyTo</span><span class="sxs-lookup"><span data-stu-id="2bf52-103">IMAPIProp::CopyTo</span></span>

  
  
<span data-ttu-id="2bf52-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="2bf52-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="2bf52-105">复制或移动的所有属性，特别是排除属性除外。</span><span class="sxs-lookup"><span data-stu-id="2bf52-105">Copies or moves all properties, except for specifically excluded properties.</span></span>
  
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

## <a name="parameters"></a><span data-ttu-id="2bf52-106">参数</span><span class="sxs-lookup"><span data-stu-id="2bf52-106">Parameters</span></span>

 <span data-ttu-id="2bf52-107">_ciidExclude_</span><span class="sxs-lookup"><span data-stu-id="2bf52-107">_ciidExclude_</span></span>
  
> <span data-ttu-id="2bf52-108">[in]复制或移动属性时要排除的接口的计数。</span><span class="sxs-lookup"><span data-stu-id="2bf52-108">[in] The count of interfaces to exclude when properties are copied or moved.</span></span>
    
 <span data-ttu-id="2bf52-109">_rgiidExclude_</span><span class="sxs-lookup"><span data-stu-id="2bf52-109">_rgiidExclude_</span></span>
  
> <span data-ttu-id="2bf52-110">[in]指定接口的补充信息是复制或移动到目标对象时不应使用的接口标识符 (Iid) 的数组。</span><span class="sxs-lookup"><span data-stu-id="2bf52-110">[in] An array of interface identifiers (IIDs) that specify interfaces that should not be used when supplemental information is copied or moved to the destination object.</span></span>
    
 <span data-ttu-id="2bf52-111">_lpExcludeProps_</span><span class="sxs-lookup"><span data-stu-id="2bf52-111">_lpExcludeProps_</span></span>
  
> <span data-ttu-id="2bf52-112">[in]指向属性标记数组，标识属性标记的应排除从副本或移动操作的指针。</span><span class="sxs-lookup"><span data-stu-id="2bf52-112">[in] A pointer to a property tag array that identifies the property tags that should be excluded from the copy or move operation.</span></span> <span data-ttu-id="2bf52-113">_LpExcludeProps_参数中传递**null**指示所有对象的属性应该可以复制或移动。</span><span class="sxs-lookup"><span data-stu-id="2bf52-113">Passing **null** in the  _lpExcludeProps_ parameter indicates that all of the object's properties should be copied or moved.</span></span> <span data-ttu-id="2bf52-114">**CopyTo**返回 MAPI_E_INVALID_PARAMETER [SPropProblemArray](spropproblemarray.md)结构的**cValues**成员所指的_lpExcludeProps_时设置为 0。</span><span class="sxs-lookup"><span data-stu-id="2bf52-114">**CopyTo** returns MAPI_E_INVALID_PARAMETER when the **cValues** member of the [SPropProblemArray](spropproblemarray.md) structure pointed to by  _lpExcludeProps_ is set to 0.</span></span> 
    
 <span data-ttu-id="2bf52-115">_ulUIParam_</span><span class="sxs-lookup"><span data-stu-id="2bf52-115">_ulUIParam_</span></span>
  
> <span data-ttu-id="2bf52-116">[in]进度指示器的父窗口句柄。</span><span class="sxs-lookup"><span data-stu-id="2bf52-116">[in] A handle to the parent window of the progress indicator.</span></span> 
    
 <span data-ttu-id="2bf52-117">_lpProgress_</span><span class="sxs-lookup"><span data-stu-id="2bf52-117">_lpProgress_</span></span>
  
> <span data-ttu-id="2bf52-118">[in]指向进度指示器实现的指针。</span><span class="sxs-lookup"><span data-stu-id="2bf52-118">[in] A pointer to a progress indicator implementation.</span></span> <span data-ttu-id="2bf52-119">如果_lpProgress_参数中传递**null** ，MAPI 提供进度实现。</span><span class="sxs-lookup"><span data-stu-id="2bf52-119">If **null** is passed in the  _lpProgress_ parameter, MAPI provides the progress implementation.</span></span> <span data-ttu-id="2bf52-120">除非 MAPI_DIALOG 标志设置_ulFlags_参数中，将忽略该_lpProgress_参数。</span><span class="sxs-lookup"><span data-stu-id="2bf52-120">The  _lpProgress_ parameter is ignored unless the MAPI_DIALOG flag is set in the  _ulFlags_ parameter.</span></span> 
    
 <span data-ttu-id="2bf52-121">_lpInterface_</span><span class="sxs-lookup"><span data-stu-id="2bf52-121">_lpInterface_</span></span>
  
> <span data-ttu-id="2bf52-122">[in]指向接口标识 (IID) 值，该值代表要用于访问_lpDestObj_参数指向的对象的接口的指针。</span><span class="sxs-lookup"><span data-stu-id="2bf52-122">[in] A pointer to the interface identifier (IID) that represents the interface to be used to access the object pointed to by the  _lpDestObj_ parameter.</span></span> <span data-ttu-id="2bf52-123">_LpInterface_参数不为**null**。</span><span class="sxs-lookup"><span data-stu-id="2bf52-123">The  _lpInterface_ parameter must not be **null**.</span></span>
    
 <span data-ttu-id="2bf52-124">_lpDestObj_</span><span class="sxs-lookup"><span data-stu-id="2bf52-124">_lpDestObj_</span></span>
  
> <span data-ttu-id="2bf52-125">[in]指向要接收复制或移动属性的对象的指针。</span><span class="sxs-lookup"><span data-stu-id="2bf52-125">[in] A pointer to the object to receive the copied or moved properties.</span></span>
    
 <span data-ttu-id="2bf52-126">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="2bf52-126">_ulFlags_</span></span>
  
> <span data-ttu-id="2bf52-127">[in]位掩码的标志，用于控制复制或移动操作。</span><span class="sxs-lookup"><span data-stu-id="2bf52-127">[in] A bitmask of flags that controls the copy or move operation.</span></span> <span data-ttu-id="2bf52-128">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="2bf52-128">The following flags can be set:</span></span>
    
<span data-ttu-id="2bf52-129">MAPI_DECLINE_OK</span><span class="sxs-lookup"><span data-stu-id="2bf52-129">MAPI_DECLINE_OK</span></span> 
  
> <span data-ttu-id="2bf52-130">如果**CopyTo**调用[IMAPISupport::DoCopyTo](imapisupport-docopyto.md)方法来处理复制或移动操作，则应改为错误值 MAPI_E_DECLINE_COPY 立即返回。</span><span class="sxs-lookup"><span data-stu-id="2bf52-130">If **CopyTo** calls the [IMAPISupport::DoCopyTo](imapisupport-docopyto.md) method to handle the copy or move operation, it should instead return immediately with the error value MAPI_E_DECLINE_COPY.</span></span> <span data-ttu-id="2bf52-131">MAPI 设置 MAPI_DECLINE_OK 标志来限制递归。</span><span class="sxs-lookup"><span data-stu-id="2bf52-131">The MAPI_DECLINE_OK flag is set by MAPI to limit recursion.</span></span> <span data-ttu-id="2bf52-132">客户端未设置此标志。</span><span class="sxs-lookup"><span data-stu-id="2bf52-132">Clients do not set this flag.</span></span> 
    
<span data-ttu-id="2bf52-133">MAPI_DIALOG</span><span class="sxs-lookup"><span data-stu-id="2bf52-133">MAPI_DIALOG</span></span> 
  
> <span data-ttu-id="2bf52-134">显示进度指示器。</span><span class="sxs-lookup"><span data-stu-id="2bf52-134">Displays a progress indicator.</span></span>
    
<span data-ttu-id="2bf52-135">MAPI_MOVE</span><span class="sxs-lookup"><span data-stu-id="2bf52-135">MAPI_MOVE</span></span> 
  
> <span data-ttu-id="2bf52-136">**CopyTo**应执行移动操作而不是复制操作。</span><span class="sxs-lookup"><span data-stu-id="2bf52-136">**CopyTo** should perform a move operation instead of a copy operation.</span></span> <span data-ttu-id="2bf52-137">当未设置此标志时， **CopyTo**执行复制操作。</span><span class="sxs-lookup"><span data-stu-id="2bf52-137">When this flag is not set, **CopyTo** performs a copy operation.</span></span> 
    
<span data-ttu-id="2bf52-138">MAPI_NOREPLACE</span><span class="sxs-lookup"><span data-stu-id="2bf52-138">MAPI_NOREPLACE</span></span> 
  
> <span data-ttu-id="2bf52-139">不应覆盖目标对象中的现有属性。</span><span class="sxs-lookup"><span data-stu-id="2bf52-139">Existing properties in the destination object should not be overwritten.</span></span> <span data-ttu-id="2bf52-140">如果未设置此标志， **CopyTo**会覆盖现有属性。</span><span class="sxs-lookup"><span data-stu-id="2bf52-140">When this flag is not set, **CopyTo** overwrites existing properties.</span></span> 
    
 <span data-ttu-id="2bf52-141">_lppProblems_</span><span class="sxs-lookup"><span data-stu-id="2bf52-141">_lppProblems_</span></span>
  
> <span data-ttu-id="2bf52-142">[传入、 传出]在输入时，为**SPropProblemArray**结构; 指针的指针否则为**为 null**，指示不需要错误信息。</span><span class="sxs-lookup"><span data-stu-id="2bf52-142">[in, out] On input, a pointer to a pointer to an **SPropProblemArray** structure; otherwise, **null**, indicating no need for error information.</span></span> <span data-ttu-id="2bf52-143">如果_lppProblems_上输入的有效指针， **CopyTo**中复制一个或多个属性返回有关错误的详细的信息。</span><span class="sxs-lookup"><span data-stu-id="2bf52-143">If  _lppProblems_ is a valid pointer on input, **CopyTo** returns detailed information about errors in copying one or more properties.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="2bf52-144">返回值</span><span class="sxs-lookup"><span data-stu-id="2bf52-144">Return value</span></span>

<span data-ttu-id="2bf52-145">S_OK</span><span class="sxs-lookup"><span data-stu-id="2bf52-145">S_OK</span></span> 
  
> <span data-ttu-id="2bf52-146">属性已成功复制或移动。</span><span class="sxs-lookup"><span data-stu-id="2bf52-146">The properties have been successfully copied or moved.</span></span>
    
<span data-ttu-id="2bf52-147">MAPI_E_COLLISION</span><span class="sxs-lookup"><span data-stu-id="2bf52-147">MAPI_E_COLLISION</span></span> 
  
> <span data-ttu-id="2bf52-148">不能复制的子对象，因为具有相同的子对象的显示名称 — **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 属性指定 — 对目标对象中已存在。</span><span class="sxs-lookup"><span data-stu-id="2bf52-148">A subobject cannot be copied because a subobject with the same display name — specified by the **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) property — already exists in the destination object.</span></span> 
    
<span data-ttu-id="2bf52-149">MAPI_E_DECLINE_COPY</span><span class="sxs-lookup"><span data-stu-id="2bf52-149">MAPI_E_DECLINE_COPY</span></span> 
  
> <span data-ttu-id="2bf52-150">服务提供商不实现复制操作。</span><span class="sxs-lookup"><span data-stu-id="2bf52-150">The service provider does not implement the copy operation.</span></span>
    
<span data-ttu-id="2bf52-151">MAPI_E_FOLDER_CYCLE</span><span class="sxs-lookup"><span data-stu-id="2bf52-151">MAPI_E_FOLDER_CYCLE</span></span> 
  
> <span data-ttu-id="2bf52-152">直接或间接执行复制或移动操作的源对象包含的目标对象。</span><span class="sxs-lookup"><span data-stu-id="2bf52-152">The source object performing the copy or move operation directly or indirectly contains the destination object.</span></span> <span data-ttu-id="2bf52-153">重要工作可能已执行之前已发现这种情况，所以可能部分修改的源和目标对象。</span><span class="sxs-lookup"><span data-stu-id="2bf52-153">Significant work might have been performed before this condition was discovered, so the source and destination objects might be partially modified.</span></span> 
    
<span data-ttu-id="2bf52-154">MAPI_E_INTERFACE_NOT_SUPPORTED</span><span class="sxs-lookup"><span data-stu-id="2bf52-154">MAPI_E_INTERFACE_NOT_SUPPORTED</span></span> 
  
> <span data-ttu-id="2bf52-155">由目标对象不支持_lpInterface_参数标识的接口。</span><span class="sxs-lookup"><span data-stu-id="2bf52-155">The interface identified by the  _lpInterface_ parameter is not supported by the destination object.</span></span> 
    
<span data-ttu-id="2bf52-156">MAPI_E_NO_ACCESS</span><span class="sxs-lookup"><span data-stu-id="2bf52-156">MAPI_E_NO_ACCESS</span></span> 
  
> <span data-ttu-id="2bf52-157">尝试访问其呼叫者没有足够的权限的对象。</span><span class="sxs-lookup"><span data-stu-id="2bf52-157">An attempt was made to access an object for which the caller has insufficient permissions.</span></span> <span data-ttu-id="2bf52-158">如果目标对象是对源对象相同，则返回此错误。</span><span class="sxs-lookup"><span data-stu-id="2bf52-158">This error is returned if the destination object is the same as the source object.</span></span>
    
<span data-ttu-id="2bf52-159">可以为**CopyTo**中返回在**SPropProblemArray**结构中，但不是返回值是以下值。</span><span class="sxs-lookup"><span data-stu-id="2bf52-159">The following values can be returned in the **SPropProblemArray** structure, but not as return values for **CopyTo**.</span></span> <span data-ttu-id="2bf52-160">对单个属性应用以下错误：</span><span class="sxs-lookup"><span data-stu-id="2bf52-160">The following errors apply to a single property:</span></span>
  
<span data-ttu-id="2bf52-161">MAPI_E_BAD_CHARWIDTH</span><span class="sxs-lookup"><span data-stu-id="2bf52-161">MAPI_E_BAD_CHARWIDTH</span></span> 
  
> <span data-ttu-id="2bf52-162">可以设置该 MAPI_UNICODE 标记**CopyTo**不支持 Unicode，或未设置 MAPI_UNICODE 和**CopyTo**支持仅 Unicode。</span><span class="sxs-lookup"><span data-stu-id="2bf52-162">Either the MAPI_UNICODE flag was set and **CopyTo** does not support Unicode, or MAPI_UNICODE was not set and **CopyTo** supports only Unicode.</span></span> 
    
<span data-ttu-id="2bf52-163">MAPI_E_COMPUTED</span><span class="sxs-lookup"><span data-stu-id="2bf52-163">MAPI_E_COMPUTED</span></span> 
  
> <span data-ttu-id="2bf52-164">该属性不能修改呼叫者，因为它是只读属性，计算目标对象的所有者。</span><span class="sxs-lookup"><span data-stu-id="2bf52-164">The property cannot be modified by the caller because it is a read-only property, computed by the owner of the destination object.</span></span> <span data-ttu-id="2bf52-165">此错误不是严重性。呼叫者应允许复制操作继续。</span><span class="sxs-lookup"><span data-stu-id="2bf52-165">This error is not severe; the caller should allow the copy operation to continue.</span></span>
    
<span data-ttu-id="2bf52-166">MAPI_E_INVALID_TYPE</span><span class="sxs-lookup"><span data-stu-id="2bf52-166">MAPI_E_INVALID_TYPE</span></span> 
  
> <span data-ttu-id="2bf52-167">属性类型无效。</span><span class="sxs-lookup"><span data-stu-id="2bf52-167">The property type is invalid.</span></span>
    
<span data-ttu-id="2bf52-168">MAPI_E_UNEXPECTED_TYPE</span><span class="sxs-lookup"><span data-stu-id="2bf52-168">MAPI_E_UNEXPECTED_TYPE</span></span> 
  
> <span data-ttu-id="2bf52-169">属性类型不需要呼叫者的类型。</span><span class="sxs-lookup"><span data-stu-id="2bf52-169">The property type is not the type expected by the caller.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="2bf52-170">注解</span><span class="sxs-lookup"><span data-stu-id="2bf52-170">Remarks</span></span>

<span data-ttu-id="2bf52-171">默认情况下， **IMAPIProp::CopyTo**方法复制或移动的所有当前对象的属性对目标对象。</span><span class="sxs-lookup"><span data-stu-id="2bf52-171">By default, the **IMAPIProp::CopyTo** method copies or moves all of the current object's properties to a destination object.</span></span> <span data-ttu-id="2bf52-172">**CopyTo**应复制或移动完全，与所有或其属性保持不变的大多数对象时使用。</span><span class="sxs-lookup"><span data-stu-id="2bf52-172">**CopyTo** is used when an object should be copied or moved exactly, with all or most of its properties intact.</span></span> 
  
<span data-ttu-id="2bf52-173">自动包括在操作对源对象中的任何子对象复制或移动全部。</span><span class="sxs-lookup"><span data-stu-id="2bf52-173">Any subobjects in the source object are automatically included in the operation and are copied or moved in their entirety.</span></span> <span data-ttu-id="2bf52-174">默认情况下， **CopyTo**会覆盖目标对象的匹配从源对象的属性的任何属性。</span><span class="sxs-lookup"><span data-stu-id="2bf52-174">By default, **CopyTo** overwrites any properties in the destination object that match properties from the source object.</span></span> <span data-ttu-id="2bf52-175">如果任一复制或移动属性已经存在于目标对象，除非 MAPI_NOREPLACE 标志设置_ulFlags_参数中通过新的属性，来覆盖现有属性。</span><span class="sxs-lookup"><span data-stu-id="2bf52-175">If any of the copied or moved properties already exist in the destination object, the existing properties are overwritten by the new properties, unless the MAPI_NOREPLACE flag is set in the  _ulFlags_ parameter.</span></span> <span data-ttu-id="2bf52-176">保持不变，不会被覆盖的目标对象中的现有信息。</span><span class="sxs-lookup"><span data-stu-id="2bf52-176">Existing information in the destination object that is not overwritten is left untouched.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="2bf52-177">针对实施者的注释</span><span class="sxs-lookup"><span data-stu-id="2bf52-177">Notes to implementers</span></span>

<span data-ttu-id="2bf52-178">您可以提供**CopyTo**完全实现或依赖 MAPI 提供其支持对象中的实现。</span><span class="sxs-lookup"><span data-stu-id="2bf52-178">You can provide a full implementation of **CopyTo** or rely on the implementation that MAPI provides in its support object.</span></span> <span data-ttu-id="2bf52-179">如果您想要使用的 MAPI 实现，调用**IMAPISupport::DoCopyTo**。</span><span class="sxs-lookup"><span data-stu-id="2bf52-179">If you want to use the MAPI implementation, call **IMAPISupport::DoCopyTo**.</span></span> <span data-ttu-id="2bf52-180">但是，如果您执行委派到**DoCopyTo**处理和传递 MAPI_DECLINE_OK 标志，避免支持呼叫并改为返回 MAPI_E_DECLINE_COPY。</span><span class="sxs-lookup"><span data-stu-id="2bf52-180">However, if you do delegate processing to **DoCopyTo** and you are passed the MAPI_DECLINE_OK flag, avoid the support call and return MAPI_E_DECLINE_COPY instead.</span></span> <span data-ttu-id="2bf52-181">MAPI 将使用此标志以避免可能递归复制文件夹时可能发生调用。</span><span class="sxs-lookup"><span data-stu-id="2bf52-181">MAPI will call with this flag to avoid the possible recursion that can happen when folders are copied.</span></span> 
  
<span data-ttu-id="2bf52-182">因为复制操作可能很长，您应显示进度指示器。</span><span class="sxs-lookup"><span data-stu-id="2bf52-182">Because the copy operation can be lengthy, you should display a progress indicator.</span></span> <span data-ttu-id="2bf52-183">如果存在，请使用_lpProgress_参数中传递的[IMAPIProgress](imapiprogressiunknown.md)实现。</span><span class="sxs-lookup"><span data-stu-id="2bf52-183">Use the [IMAPIProgress](imapiprogressiunknown.md) implementation passed in the  _lpProgress_ parameter, if there is one.</span></span> <span data-ttu-id="2bf52-184">如果_lpProgress_为**null**，调用[IMAPISupport::DoProgressDialog](imapisupport-doprogressdialog.md)方法使用 MAPI 实现。</span><span class="sxs-lookup"><span data-stu-id="2bf52-184">If  _lpProgress_ is **null**, call the [IMAPISupport::DoProgressDialog](imapisupport-doprogressdialog.md) method to use the MAPI implementation.</span></span> 
  
<span data-ttu-id="2bf52-185">请务尝试对目标对象; 中设置任何已知的只读属性改为返回 MAPI_E_NO_ACCESS。</span><span class="sxs-lookup"><span data-stu-id="2bf52-185">Do not attempt to set any known read-only properties in the destination object; return MAPI_E_NO_ACCESS instead.</span></span>
  
<span data-ttu-id="2bf52-186">源和目标对象应使用相同的接口。</span><span class="sxs-lookup"><span data-stu-id="2bf52-186">The source and destination objects should use the same interfaces.</span></span> <span data-ttu-id="2bf52-187">如果未设置_lpInterface_ ，返回 MAPI_E_INVALID_PARAMETER。</span><span class="sxs-lookup"><span data-stu-id="2bf52-187">Return MAPI_E_INVALID_PARAMETER if  _lpInterface_ is not set.</span></span> 
  
<span data-ttu-id="2bf52-188">如果排除所有已知的接口，则返回 MAPI_E_INTERFACE_NOT_SUPPORTED。</span><span class="sxs-lookup"><span data-stu-id="2bf52-188">Return MAPI_E_INTERFACE_NOT_SUPPORTED if all known interfaces are excluded.</span></span>
  
## <a name="notes-to-callers"></a><span data-ttu-id="2bf52-189">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="2bf52-189">Notes to callers</span></span>

<span data-ttu-id="2bf52-190">不设置 MAPI_DECLINE_OK 标志;MAPI 使用它在其呼叫消息存储提供程序**CopyTo**实现。</span><span class="sxs-lookup"><span data-stu-id="2bf52-190">Do not set the MAPI_DECLINE_OK flag; MAPI uses it in its calls to message store provider **CopyTo** implementations.</span></span> 
  
<span data-ttu-id="2bf52-191">因为复制和移动操作可能需要花费时间，您应通过设置 MAPI_DIALOG 标志请求的进度指示器显示。</span><span class="sxs-lookup"><span data-stu-id="2bf52-191">Because copy and move operations can take time, you should request the display of a progress indicator by setting the MAPI_DIALOG flag.</span></span> <span data-ttu-id="2bf52-192">您可以将_lpProgress_参数设置的**IMAPIProgress**，如果您没有实现或**null**。</span><span class="sxs-lookup"><span data-stu-id="2bf52-192">You can set the  _lpProgress_ parameter to your implementation of **IMAPIProgress**, if you have one, or to **null**.</span></span> <span data-ttu-id="2bf52-193">如果_lpProgress_为**null**， **CopyTo**将使用 MAPI 提供默认进度指示器。</span><span class="sxs-lookup"><span data-stu-id="2bf52-193">If  _lpProgress_ is **null**, **CopyTo** will use the default progress indicator that MAPI provides.</span></span> 
  
<span data-ttu-id="2bf52-194">您可以通过不设置 MAPI_DIALOG 标志来禁止显示进度指示器。</span><span class="sxs-lookup"><span data-stu-id="2bf52-194">You can suppress the display of a progress indicator by not setting the MAPI_DIALOG flag.</span></span> <span data-ttu-id="2bf52-195">**CopyTo**将忽略的_ulUIParam_和_lpProgress_参数，将不会显示该标记。</span><span class="sxs-lookup"><span data-stu-id="2bf52-195">**CopyTo** will ignore the  _ulUIParam_ and  _lpProgress_ parameters and will not display the indicator.</span></span> 
  
 <span data-ttu-id="2bf52-196">**CopyTo**可以报告全局和单个错误，或者与一个或多个属性发生的错误。</span><span class="sxs-lookup"><span data-stu-id="2bf52-196">**CopyTo** can report global and individual errors, or errors that occur with one or more properties.</span></span> <span data-ttu-id="2bf52-197">这些单个错误被放在**SPropProblemArray**结构中。</span><span class="sxs-lookup"><span data-stu-id="2bf52-197">These individual errors are placed in an **SPropProblemArray** structure.</span></span> <span data-ttu-id="2bf52-198">您可以隐藏错误属性级别通过传递**null**，而不是有效的指针，property 问题数组结构参数的报告。</span><span class="sxs-lookup"><span data-stu-id="2bf52-198">You can suppress error reporting at the property level by passing **null**, instead of a valid pointer, for the property problem array structure parameter.</span></span> 
  
<span data-ttu-id="2bf52-199">如果您想要接收有关错误的信息，请在_lppProblems_参数中传递一个有效的**SPropProblemArray**结构指针。</span><span class="sxs-lookup"><span data-stu-id="2bf52-199">If you want to receive information about errors, pass a valid **SPropProblemArray** structure pointer in the  _lppProblems_ parameter.</span></span> <span data-ttu-id="2bf52-200">时**CopyTo** ，则返回 S_OK，检查与结构中的各个属性的可能错误。</span><span class="sxs-lookup"><span data-stu-id="2bf52-200">When **CopyTo** returns S_OK, check for possible errors with individual properties in the structure.</span></span> <span data-ttu-id="2bf52-201">当**CopyTo**返回错误时， **SPropProblemArray**结构中不返回任何信息。</span><span class="sxs-lookup"><span data-stu-id="2bf52-201">When **CopyTo** returns an error, no information is returned in the **SPropProblemArray** structure.</span></span> <span data-ttu-id="2bf52-202">相反，调用[IMAPIProp::GetLastError](imapiprop-getlasterror.md)检索详细的错误信息。</span><span class="sxs-lookup"><span data-stu-id="2bf52-202">Instead, call [IMAPIProp::GetLastError](imapiprop-getlasterror.md) to retrieve detailed error information.</span></span> 
  
<span data-ttu-id="2bf52-203">如果**CopyTo** ，则返回 S_OK，通过调用[MAPIFreeBuffer](mapifreebuffer.md)函数释放返回的**SPropProblemArray**结构。</span><span class="sxs-lookup"><span data-stu-id="2bf52-203">If **CopyTo** returns S_OK, free the returned **SPropProblemArray** structure by calling the [MAPIFreeBuffer](mapifreebuffer.md) function.</span></span> 
  
<span data-ttu-id="2bf52-204">如果您要复制对源对象类型是唯一的属性，您必须确保对目标对象类型相同。</span><span class="sxs-lookup"><span data-stu-id="2bf52-204">If you copy properties that are unique to the source object type, you must ensure that the destination object is of the same type.</span></span> <span data-ttu-id="2bf52-205">**CopyTo**不阻止您关联通常属于一种类型的对象与其他类型的对象的属性。</span><span class="sxs-lookup"><span data-stu-id="2bf52-205">**CopyTo** does not prevent you from associating properties that typically belong to one type of object with another type of object.</span></span> <span data-ttu-id="2bf52-206">由您要复制对目标对象有意义的属性。</span><span class="sxs-lookup"><span data-stu-id="2bf52-206">It is up to you to copy properties that make sense for the destination object.</span></span> <span data-ttu-id="2bf52-207">例如，不应将消息属性复制到通讯簿容器。</span><span class="sxs-lookup"><span data-stu-id="2bf52-207">For example, you should not copy message properties to an address book container.</span></span> 
  
<span data-ttu-id="2bf52-208">若要确保您复制之间的相同类型的对象，检查源和目标对象相同的类型，通过比较对象指针或调用[IUnknown::QueryInterface](http://msdn.microsoft.com/en-us/library/ms682521%28v=VS.85%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="2bf52-208">To ensure that you copy between objects of the same type, check that the source and destination object are the same type, either by comparing object pointers or calling [IUnknown::QueryInterface](http://msdn.microsoft.com/en-us/library/ms682521%28v=VS.85%29.aspx).</span></span> <span data-ttu-id="2bf52-209">设置所指的源对象的标准接口_lpInterface_接口标识符。</span><span class="sxs-lookup"><span data-stu-id="2bf52-209">Set the interface identifier pointed to by  _lpInterface_ to the standard interface for the source object.</span></span> <span data-ttu-id="2bf52-210">另外，确保**PR_OBJECT_TYPE** ([PidTagObjectType](pidtagobjecttype-canonical-property.md)) 属性的对象类型是相同的两个对象。</span><span class="sxs-lookup"><span data-stu-id="2bf52-210">Also, be sure that the object type or **PR_OBJECT_TYPE** ([PidTagObjectType](pidtagobjecttype-canonical-property.md)) property is the same for the two objects.</span></span> <span data-ttu-id="2bf52-211">例如，如果复制从一条消息，则可设置为 IID_IMessage 和**PR_OBJECT_TYPE** MAPI_MESSAGE 这两个对象的_lpInterface_ 。</span><span class="sxs-lookup"><span data-stu-id="2bf52-211">For example, if you copy from a message, set  _lpInterface_ to IID_IMessage and the **PR_OBJECT_TYPE** for both objects to MAPI_MESSAGE.</span></span> 
  
<span data-ttu-id="2bf52-212">如果_lpDestObj_参数中传递了无效的指针，则结果将无法预料。</span><span class="sxs-lookup"><span data-stu-id="2bf52-212">If an invalid pointer is passed in the  _lpDestObj_ parameter, the results are unpredictable.</span></span> 
  
<span data-ttu-id="2bf52-213">排除属性**CopyTo**呼叫会很有用。</span><span class="sxs-lookup"><span data-stu-id="2bf52-213">Excluding properties on a **CopyTo** call can be useful.</span></span> <span data-ttu-id="2bf52-214">例如，某些对象具有特定于该对象，如的日期和时间的邮件传递的单个实例的属性。</span><span class="sxs-lookup"><span data-stu-id="2bf52-214">For example, some objects have properties that are specific to a single instance of the object, such as the date and time of message delivery.</span></span> <span data-ttu-id="2bf52-215">若要避免复制邮件的传递时间时将邮件复制到另一个文件夹，指定属性标记排除数组中的**PR_MESSAGE_DELIVERY_TIME** ([PidTagMessageDeliveryTime](pidtagmessagedeliverytime-canonical-property.md))。</span><span class="sxs-lookup"><span data-stu-id="2bf52-215">To avoid copying a message's delivery time when you copy the message to a different folder, specify **PR_MESSAGE_DELIVERY_TIME** ([PidTagMessageDeliveryTime](pidtagmessagedeliverytime-canonical-property.md)) in the property tag exclude array.</span></span> <span data-ttu-id="2bf52-216">若要排除邮件的收件人列表，请向排除数组添加**PR_MESSAGE_RECIPIENTS** ([PidTagMessageRecipients](pidtagmessagerecipients-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="2bf52-216">To exclude a message's recipient list, add the **PR_MESSAGE_RECIPIENTS** ([PidTagMessageRecipients](pidtagmessagerecipients-canonical-property.md)) property to the exclude array.</span></span> <span data-ttu-id="2bf52-217">若要排除邮件的附件，添加到数组**PR_MESSAGE_ATTACHMENTS** ([PidTagMessageAttachments](pidtagmessageattachments-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="2bf52-217">To exclude a message's attachments, add the **PR_MESSAGE_ATTACHMENTS** ([PidTagMessageAttachments](pidtagmessageattachments-canonical-property.md)) property to the array.</span></span>
  
<span data-ttu-id="2bf52-218">同样，以阻止复制或移动的文件夹或通讯簿容器层次结构或内容表包括**PR_CONTAINER_HIERARCHY** ([PidTagContainerHierarchy](pidtagcontainerhierarchy-canonical-property.md)) 或**PR_CONTAINER_CONTENTS** ([PidTagContainerContents](pidtagcontainercontents-canonical-property.md)) 的属性中标记排除数组。</span><span class="sxs-lookup"><span data-stu-id="2bf52-218">Similarly, prevent the copying or moving of a folder or address book container's hierarchy or contents table by including **PR_CONTAINER_HIERARCHY** ([PidTagContainerHierarchy](pidtagcontainerhierarchy-canonical-property.md)) or **PR_CONTAINER_CONTENTS** ([PidTagContainerContents](pidtagcontainercontents-canonical-property.md)) in the property tag exclude array.</span></span>
  
<span data-ttu-id="2bf52-219">若要从副本排除属性或移动操作，其属性标记中包含的_lpExcludeProps_参数。</span><span class="sxs-lookup"><span data-stu-id="2bf52-219">To exclude properties from the copy or move operation, include their property tags in the  _lpExcludeProps_ parameter.</span></span> <span data-ttu-id="2bf52-220">如果传递**PROP_TAG**宏生成从一个特定的标识符，该属性标记数组中的属性标记的结果，与该标识符的所有属性都将被都排除。</span><span class="sxs-lookup"><span data-stu-id="2bf52-220">If you pass the results of the **PROP_TAG** macro to build a property tag from a specific identifier in the property tag array, all properties with that identifier will be excluded.</span></span> <span data-ttu-id="2bf52-221">例如，属性标记数组中的以下条目 0x8002 排除，无论类型的标识符的原因是了所有属性：</span><span class="sxs-lookup"><span data-stu-id="2bf52-221">For example, the following entry in the property tag array causes all properties with an identifier of 0x8002 to be excluded, regardless of type:</span></span> 
  
 `PROP_TAG(PT_LONG, 0x8002)`
  
<span data-ttu-id="2bf52-222">不能**PR_NULL** ([PidTagNull](pidtagnull-canonical-property.md)) 属性标记包含_lpExcludeProps_数组中。</span><span class="sxs-lookup"><span data-stu-id="2bf52-222">The **PR_NULL** ([PidTagNull](pidtagnull-canonical-property.md)) property tag cannot be included in the  _lpExcludeProps_ array.</span></span> 
  
<span data-ttu-id="2bf52-223">排除接口的**CopyTo**功能的用途是可能不明显，排除属性的有效性。</span><span class="sxs-lookup"><span data-stu-id="2bf52-223">The usefulness of the **CopyTo** feature for excluding interfaces is perhaps not as obvious as the usefulness of excluding properties.</span></span> <span data-ttu-id="2bf52-224">复制到不知道的一组属性对象时，您可以排除接口。</span><span class="sxs-lookup"><span data-stu-id="2bf52-224">You can exclude an interface when you copy to an object that has no knowledge of a group of properties.</span></span> <span data-ttu-id="2bf52-225">例如，如果将属性从文件夹复制到附件中时，附件可以使用的唯一属性将是具有任何[IMAPIProp](imapipropiunknown.md)实现的泛型属性。</span><span class="sxs-lookup"><span data-stu-id="2bf52-225">For example, if you copy properties from a folder to an attachment, the only properties that the attachment can work with are the generic properties available with any [IMAPIProp](imapipropiunknown.md) implementation.</span></span> <span data-ttu-id="2bf52-226">通过复制操作从排除[IMAPIFolder](imapifolderimapicontainer.md) ，附件不会收到任何更具体的文件夹属性。</span><span class="sxs-lookup"><span data-stu-id="2bf52-226">By excluding [IMAPIFolder](imapifolderimapicontainer.md) from the copy operation, the attachment will not receive any of the more specific folder properties.</span></span> 
  
<span data-ttu-id="2bf52-227">当_rgiidExclude_参数用于排除一个接口时，它还不包括所有接口派生自的接口。</span><span class="sxs-lookup"><span data-stu-id="2bf52-227">When you use the  _rgiidExclude_ parameter to exclude an interface, it also excludes all interfaces derived from that interface.</span></span> <span data-ttu-id="2bf52-228">例如，不包括[IMAPIContainer](imapicontainerimapiprop.md)使文件夹或通讯簿容器排除，具体取决于提供程序的类型。</span><span class="sxs-lookup"><span data-stu-id="2bf52-228">For example, excluding [IMAPIContainer](imapicontainerimapiprop.md) causes folders or address book containers to be excluded, depending on the type of provider.</span></span> <span data-ttu-id="2bf52-229">因为太多接口从它们派生，不要排除**IMAPIProp**或[IUnknown](http://msdn.microsoft.com/en-us/library/ms680509%28v=VS.85%29.aspx) 。</span><span class="sxs-lookup"><span data-stu-id="2bf52-229">Do not exclude **IMAPIProp** or [IUnknown](http://msdn.microsoft.com/en-us/library/ms680509%28v=VS.85%29.aspx) because so many interfaces derive from them.</span></span> 
  
<span data-ttu-id="2bf52-230">忽略 MAPI_E_COMPUTED _lppProblems_参数中**SPropProblemArray**结构中返回的错误。</span><span class="sxs-lookup"><span data-stu-id="2bf52-230">Ignore MAPI_E_COMPUTED errors returned in the **SPropProblemArray** structure in the  _lppProblems_ parameter.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="2bf52-231">MFCMAPI 参考 （英文）</span><span class="sxs-lookup"><span data-stu-id="2bf52-231">MFCMAPI reference</span></span>

<span data-ttu-id="2bf52-232">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="2bf52-232">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="2bf52-233">**文件**</span><span class="sxs-lookup"><span data-stu-id="2bf52-233">**File**</span></span>|<span data-ttu-id="2bf52-234">**函数**</span><span class="sxs-lookup"><span data-stu-id="2bf52-234">**Function**</span></span>|<span data-ttu-id="2bf52-235">**Comment**</span><span class="sxs-lookup"><span data-stu-id="2bf52-235">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="2bf52-236">File.cpp</span><span class="sxs-lookup"><span data-stu-id="2bf52-236">File.cpp</span></span>  <br/> |<span data-ttu-id="2bf52-237">LoadFromMSG</span><span class="sxs-lookup"><span data-stu-id="2bf52-237">LoadFromMSG</span></span>  <br/> |<span data-ttu-id="2bf52-238">MFCMAPI 使用**IMAPIProp::CopyTo**方法将属性从.msg 文件复制到[IMAPIMessageSite](imapimessagesiteiunknown.md)对象。</span><span class="sxs-lookup"><span data-stu-id="2bf52-238">MFCMAPI uses the **IMAPIProp::CopyTo** method to copy properties from a .msg file to an [IMAPIMessageSite](imapimessagesiteiunknown.md) object.</span></span>  <br/> |
|<span data-ttu-id="2bf52-239">FolderDlg.cpp</span><span class="sxs-lookup"><span data-stu-id="2bf52-239">FolderDlg.cpp</span></span>  <br/> |<span data-ttu-id="2bf52-240">CFolderDlg::HandlePaste</span><span class="sxs-lookup"><span data-stu-id="2bf52-240">CFolderDlg::HandlePaste</span></span>  <br/> |<span data-ttu-id="2bf52-241">MFCMAPI 使用**IMAPIProp::CopyTo**方法将属性复制源邮件到目标邮件在粘贴操作过程。</span><span class="sxs-lookup"><span data-stu-id="2bf52-241">MFCMAPI uses the **IMAPIProp::CopyTo** method to copy properties from a source message to a target message during a paste operation.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="2bf52-242">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2bf52-242">See also</span></span>



[<span data-ttu-id="2bf52-243">IMAPIFolder::CopyMessages</span><span class="sxs-lookup"><span data-stu-id="2bf52-243">IMAPIFolder::CopyMessages</span></span>](imapifolder-copymessages.md)
  
[<span data-ttu-id="2bf52-244">IMAPIProp::GetLastError</span><span class="sxs-lookup"><span data-stu-id="2bf52-244">IMAPIProp::GetLastError</span></span>](imapiprop-getlasterror.md)
  
[<span data-ttu-id="2bf52-245">IMAPIMessageSite : IUnknown</span><span class="sxs-lookup"><span data-stu-id="2bf52-245">IMAPIMessageSite : IUnknown</span></span>](imapimessagesiteiunknown.md)
  
[<span data-ttu-id="2bf52-246">IMAPIProgress : IUnknown</span><span class="sxs-lookup"><span data-stu-id="2bf52-246">IMAPIProgress : IUnknown</span></span>](imapiprogressiunknown.md)
  
[<span data-ttu-id="2bf52-247">IMAPISupport::DoProgressDialog</span><span class="sxs-lookup"><span data-stu-id="2bf52-247">IMAPISupport::DoProgressDialog</span></span>](imapisupport-doprogressdialog.md)
  
[<span data-ttu-id="2bf52-248">IMAPISupport::DoCopyTo</span><span class="sxs-lookup"><span data-stu-id="2bf52-248">IMAPISupport::DoCopyTo</span></span>](imapisupport-docopyto.md)
  
[<span data-ttu-id="2bf52-249">MAPIFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="2bf52-249">MAPIFreeBuffer</span></span>](mapifreebuffer.md)
  
[<span data-ttu-id="2bf52-250">PidTagContainerContents 规范属性</span><span class="sxs-lookup"><span data-stu-id="2bf52-250">PidTagContainerContents Canonical Property</span></span>](pidtagcontainercontents-canonical-property.md)
  
[<span data-ttu-id="2bf52-251">PidTagContainerHierarchy 规范属性</span><span class="sxs-lookup"><span data-stu-id="2bf52-251">PidTagContainerHierarchy Canonical Property</span></span>](pidtagcontainerhierarchy-canonical-property.md)
  
[<span data-ttu-id="2bf52-252">PidTagMessageAttachments 规范属性</span><span class="sxs-lookup"><span data-stu-id="2bf52-252">PidTagMessageAttachments Canonical Property</span></span>](pidtagmessageattachments-canonical-property.md)
  
[<span data-ttu-id="2bf52-253">PidTagMessageDeliveryTime 规范属性</span><span class="sxs-lookup"><span data-stu-id="2bf52-253">PidTagMessageDeliveryTime Canonical Property</span></span>](pidtagmessagedeliverytime-canonical-property.md)
  
[<span data-ttu-id="2bf52-254">PidTagMessageRecipients 规范属性</span><span class="sxs-lookup"><span data-stu-id="2bf52-254">PidTagMessageRecipients Canonical Property</span></span>](pidtagmessagerecipients-canonical-property.md)
  
[<span data-ttu-id="2bf52-255">PidTagObjectType 规范属性</span><span class="sxs-lookup"><span data-stu-id="2bf52-255">PidTagObjectType Canonical Property</span></span>](pidtagobjecttype-canonical-property.md)
  
[<span data-ttu-id="2bf52-256">SPropProblemArray</span><span class="sxs-lookup"><span data-stu-id="2bf52-256">SPropProblemArray</span></span>](spropproblemarray.md)
  
[<span data-ttu-id="2bf52-257">SPropTagArray</span><span class="sxs-lookup"><span data-stu-id="2bf52-257">SPropTagArray</span></span>](sproptagarray.md)
  
[<span data-ttu-id="2bf52-258">IMAPIProp : IUnknown</span><span class="sxs-lookup"><span data-stu-id="2bf52-258">IMAPIProp : IUnknown</span></span>](imapipropiunknown.md)


[<span data-ttu-id="2bf52-259">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="2bf52-259">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

