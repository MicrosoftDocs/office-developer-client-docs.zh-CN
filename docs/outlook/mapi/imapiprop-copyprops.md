---
title: IMAPIPropCopyProps
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIProp.CopyProps
api_type:
- COM
ms.assetid: f65da1c8-d49b-44e8-8c66-9c53d088d334
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: ff8f13a1dcf678e1d05b6e8e083597156422b83d
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775537"
---
# <a name="imapipropcopyprops"></a><span data-ttu-id="bb064-103">IMAPIProp::CopyProps</span><span class="sxs-lookup"><span data-stu-id="bb064-103">IMAPIProp::CopyProps</span></span>

  
  
<span data-ttu-id="bb064-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="bb064-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="bb064-105">复制或移动所选的属性。</span><span class="sxs-lookup"><span data-stu-id="bb064-105">Copies or moves selected properties.</span></span> 
  
```cpp
HRESULT CopyProps(
  LPSPropTagArray lpIncludeProps,
  ULONG_PTR ulUIParam,
  LPMAPIPROGRESS lpProgress,
  LPCIID lpInterface,
  LPVOID lpDestObj,
  ULONG ulFlags,
  LPSPropProblemArray FAR * lppProblems
);
```

## <a name="parameters"></a><span data-ttu-id="bb064-106">参数</span><span class="sxs-lookup"><span data-stu-id="bb064-106">Parameters</span></span>

 <span data-ttu-id="bb064-107">_lpIncludeProps_</span><span class="sxs-lookup"><span data-stu-id="bb064-107">_lpIncludeProps_</span></span>
  
> <span data-ttu-id="bb064-108">[in]一个指向属性标记数组，它指定要复制或移动的属性。</span><span class="sxs-lookup"><span data-stu-id="bb064-108">[in] A pointer to a property tag array that specifies the properties to copy or move.</span></span> <span data-ttu-id="bb064-109">**PR_NULL**不能包含数组 ([PidTagNull](pidtagnull-canonical-property.md))。</span><span class="sxs-lookup"><span data-stu-id="bb064-109">**PR_NULL** ([PidTagNull](pidtagnull-canonical-property.md)) cannot be included in the array.</span></span> <span data-ttu-id="bb064-110">_LpIncludeProps_参数不能为**null**。</span><span class="sxs-lookup"><span data-stu-id="bb064-110">The  _lpIncludeProps_ parameter cannot be **null**.</span></span>
    
 <span data-ttu-id="bb064-111">_ulUIParam_</span><span class="sxs-lookup"><span data-stu-id="bb064-111">_ulUIParam_</span></span>
  
> <span data-ttu-id="bb064-112">[in]进度指示器的父窗口句柄。</span><span class="sxs-lookup"><span data-stu-id="bb064-112">[in] A handle to the parent window of the progress indicator.</span></span> 
    
 <span data-ttu-id="bb064-113">_lpProgress_</span><span class="sxs-lookup"><span data-stu-id="bb064-113">_lpProgress_</span></span>
  
> <span data-ttu-id="bb064-114">[in]一个指向进度指示器的实现。</span><span class="sxs-lookup"><span data-stu-id="bb064-114">[in] A pointer to an implementation of a progress indicator.</span></span> <span data-ttu-id="bb064-115">如果_lpProgress_参数中传递**null** ，是通过使用 MAPI 实现显示进度指示器。</span><span class="sxs-lookup"><span data-stu-id="bb064-115">If **null** is passed in the  _lpProgress_ parameter, the progress indicator is displayed by using the MAPI implementation.</span></span> <span data-ttu-id="bb064-116">除非 MAPI_DIALOG 标志设置_ulFlags_参数中，将忽略该_lpProgress_参数。</span><span class="sxs-lookup"><span data-stu-id="bb064-116">The  _lpProgress_ parameter is ignored unless the MAPI_DIALOG flag is set in the  _ulFlags_ parameter.</span></span> 
    
 <span data-ttu-id="bb064-117">_lpInterface_</span><span class="sxs-lookup"><span data-stu-id="bb064-117">_lpInterface_</span></span>
  
> <span data-ttu-id="bb064-118">[in]指向接口标识 (IID) 表示必须用于访问_lpDestObj_参数指向的对象的接口的指针。</span><span class="sxs-lookup"><span data-stu-id="bb064-118">[in] A pointer to the interface identifier (IID) that represents the interface that must be used to access the object pointed to by the  _lpDestObj_ parameter.</span></span> <span data-ttu-id="bb064-119">_LpInterface_参数不为**null**。</span><span class="sxs-lookup"><span data-stu-id="bb064-119">The  _lpInterface_ parameter must not be **null**.</span></span>
    
 <span data-ttu-id="bb064-120">_lpDestObj_</span><span class="sxs-lookup"><span data-stu-id="bb064-120">_lpDestObj_</span></span>
  
> <span data-ttu-id="bb064-121">[in]指向要接收复制或移动属性的对象的指针。</span><span class="sxs-lookup"><span data-stu-id="bb064-121">[in] A pointer to the object to receive the copied or moved properties.</span></span>
    
 <span data-ttu-id="bb064-122">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="bb064-122">_ulFlags_</span></span>
  
> <span data-ttu-id="bb064-123">[in]位掩码的标志，用于控制复制或移动操作。</span><span class="sxs-lookup"><span data-stu-id="bb064-123">[in] A bitmask of flags that controls the copy or move operation.</span></span> <span data-ttu-id="bb064-124">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="bb064-124">The following flags can be set:</span></span>
    
<span data-ttu-id="bb064-125">MAPI_DECLINE_OK</span><span class="sxs-lookup"><span data-stu-id="bb064-125">MAPI_DECLINE_OK</span></span> 
  
> <span data-ttu-id="bb064-126">如果**CopyProps**调用[IMAPISupport::DoCopyProps](imapisupport-docopyprops.md)方法来处理复制或移动操作，则应改为错误值 MAPI_E_DECLINE_COPY 立即返回。</span><span class="sxs-lookup"><span data-stu-id="bb064-126">If **CopyProps** calls the [IMAPISupport::DoCopyProps](imapisupport-docopyprops.md) method to handle the copy or move operation, it should instead return immediately with the error value MAPI_E_DECLINE_COPY.</span></span> <span data-ttu-id="bb064-127">MAPI 设置 MAPI_DECLINE_OK 标志来限制递归。</span><span class="sxs-lookup"><span data-stu-id="bb064-127">The MAPI_DECLINE_OK flag is set by MAPI to limit recursion.</span></span> <span data-ttu-id="bb064-128">客户端未设置此标志。</span><span class="sxs-lookup"><span data-stu-id="bb064-128">Clients do not set this flag.</span></span> 
    
<span data-ttu-id="bb064-129">MAPI_DIALOG</span><span class="sxs-lookup"><span data-stu-id="bb064-129">MAPI_DIALOG</span></span> 
  
> <span data-ttu-id="bb064-130">显示进度指示器。</span><span class="sxs-lookup"><span data-stu-id="bb064-130">Displays a progress indicator.</span></span>
    
<span data-ttu-id="bb064-131">MAPI_MOVE</span><span class="sxs-lookup"><span data-stu-id="bb064-131">MAPI_MOVE</span></span> 
  
> <span data-ttu-id="bb064-132">**CopyProps**应执行移动操作而不是复制操作。</span><span class="sxs-lookup"><span data-stu-id="bb064-132">**CopyProps** should perform a move operation instead of a copy operation.</span></span> <span data-ttu-id="bb064-133">当未设置此标志时， **CopyProps**执行复制操作。</span><span class="sxs-lookup"><span data-stu-id="bb064-133">When this flag is not set, **CopyProps** performs a copy operation.</span></span> 
    
<span data-ttu-id="bb064-134">MAPI_NOREPLACE</span><span class="sxs-lookup"><span data-stu-id="bb064-134">MAPI_NOREPLACE</span></span> 
  
> <span data-ttu-id="bb064-135">不应覆盖目标对象中的现有属性。</span><span class="sxs-lookup"><span data-stu-id="bb064-135">Existing properties in the destination object should not be overwritten.</span></span> <span data-ttu-id="bb064-136">如果未设置此标志， **CopyProps**会覆盖现有属性。</span><span class="sxs-lookup"><span data-stu-id="bb064-136">When this flag is not set, **CopyProps** overwrites existing properties.</span></span> 
    
 <span data-ttu-id="bb064-137">_lppProblems_</span><span class="sxs-lookup"><span data-stu-id="bb064-137">_lppProblems_</span></span>
  
> <span data-ttu-id="bb064-138">[传入、 传出]在输入时，为[SPropProblemArray](spropproblemarray.md)结构; 指针的指针否则为**为 null**，指示存在错误信息不需要。</span><span class="sxs-lookup"><span data-stu-id="bb064-138">[in, out] On input, a pointer to a pointer to an [SPropProblemArray](spropproblemarray.md) structure; otherwise, **null**, indicating that there is no need for error information.</span></span> <span data-ttu-id="bb064-139">如果_lppProblems_上输入, 的有效指针**CopyProps**中复制一个或多个属性返回有关错误的详细的信息。</span><span class="sxs-lookup"><span data-stu-id="bb064-139">If  _lppProblems_ is a valid pointer on input, **CopyProps** returns detailed information about errors in copying one or more properties.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="bb064-140">返回值</span><span class="sxs-lookup"><span data-stu-id="bb064-140">Return value</span></span>

<span data-ttu-id="bb064-141">S_OK</span><span class="sxs-lookup"><span data-stu-id="bb064-141">S_OK</span></span> 
  
> <span data-ttu-id="bb064-142">属性已成功复制或移动。</span><span class="sxs-lookup"><span data-stu-id="bb064-142">Properties have been successfully copied or moved.</span></span>
    
<span data-ttu-id="bb064-143">MAPI_E_COLLISION</span><span class="sxs-lookup"><span data-stu-id="bb064-143">MAPI_E_COLLISION</span></span> 
  
> <span data-ttu-id="bb064-144">不能复制的子对象，因为目标对象中已存在具有相同的显示名称，由**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 属性中，定义的子对象。</span><span class="sxs-lookup"><span data-stu-id="bb064-144">A subobject cannot be copied because a subobject with the same display name, defined by the **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) property, already exists in the destination object.</span></span> 
    
<span data-ttu-id="bb064-145">MAPI_E_DECLINE_COPY</span><span class="sxs-lookup"><span data-stu-id="bb064-145">MAPI_E_DECLINE_COPY</span></span> 
  
> <span data-ttu-id="bb064-146">服务提供商不实现复制操作。</span><span class="sxs-lookup"><span data-stu-id="bb064-146">The service provider does not implement the copy operation.</span></span>
    
<span data-ttu-id="bb064-147">MAPI_E_FOLDER_CYCLE</span><span class="sxs-lookup"><span data-stu-id="bb064-147">MAPI_E_FOLDER_CYCLE</span></span> 
  
> <span data-ttu-id="bb064-148">直接或间接执行复制或移动操作的源对象包含的目标对象。</span><span class="sxs-lookup"><span data-stu-id="bb064-148">The source object performing the copy or move operation directly or indirectly contains the destination object.</span></span> <span data-ttu-id="bb064-149">重要工作可能已执行之前已发现这种情况，所以可能部分修改的源和目标对象。</span><span class="sxs-lookup"><span data-stu-id="bb064-149">Significant work might have been performed before this condition was discovered, so the source and destination objects might be partially modified.</span></span> 
    
<span data-ttu-id="bb064-150">MAPI_E_INTERFACE_NOT_SUPPORTED</span><span class="sxs-lookup"><span data-stu-id="bb064-150">MAPI_E_INTERFACE_NOT_SUPPORTED</span></span> 
  
> <span data-ttu-id="bb064-151">由目标对象不支持_lpInterface_参数标识的接口。</span><span class="sxs-lookup"><span data-stu-id="bb064-151">The interface identified by the  _lpInterface_ parameter is not supported by the destination object.</span></span> 
    
<span data-ttu-id="bb064-152">MAPI_E_NO_ACCESS</span><span class="sxs-lookup"><span data-stu-id="bb064-152">MAPI_E_NO_ACCESS</span></span> 
  
> <span data-ttu-id="bb064-153">尝试访问其呼叫者没有足够的权限的对象。</span><span class="sxs-lookup"><span data-stu-id="bb064-153">An attempt was made to access an object for which the caller has insufficient permissions.</span></span> <span data-ttu-id="bb064-154">如果目标对象是对源对象相同，则返回此错误。</span><span class="sxs-lookup"><span data-stu-id="bb064-154">This error is returned if the destination object is the same as the source object.</span></span>
    
<span data-ttu-id="bb064-155">可以为**CopyProps**中返回在**SPropProblemArray**结构中，但不是返回值是以下值。</span><span class="sxs-lookup"><span data-stu-id="bb064-155">The following values can be returned in the **SPropProblemArray** structure, but not as return values for **CopyProps**.</span></span> <span data-ttu-id="bb064-156">这些错误应用于单个属性。</span><span class="sxs-lookup"><span data-stu-id="bb064-156">These errors apply to a single property.</span></span>
  
<span data-ttu-id="bb064-157">MAPI_E_BAD_CHARWIDTH</span><span class="sxs-lookup"><span data-stu-id="bb064-157">MAPI_E_BAD_CHARWIDTH</span></span> 
  
> <span data-ttu-id="bb064-158">可以设置该 MAPI_UNICODE 标记**CopyProps**不支持 Unicode，或未设置 MAPI_UNICODE 和**CopyProps**支持仅 Unicode。</span><span class="sxs-lookup"><span data-stu-id="bb064-158">Either the MAPI_UNICODE flag was set and **CopyProps** does not support Unicode, or MAPI_UNICODE was not set and **CopyProps** supports only Unicode.</span></span> 
    
<span data-ttu-id="bb064-159">MAPI_E_COMPUTED</span><span class="sxs-lookup"><span data-stu-id="bb064-159">MAPI_E_COMPUTED</span></span> 
  
> <span data-ttu-id="bb064-160">该属性不能修改呼叫者，因为它是只读属性，计算目标对象的所有者。</span><span class="sxs-lookup"><span data-stu-id="bb064-160">The property cannot be modified by the caller because it is a read-only property, computed by the owner of the destination object.</span></span> <span data-ttu-id="bb064-161">此错误不是严重性。呼叫者应允许复制操作继续。</span><span class="sxs-lookup"><span data-stu-id="bb064-161">This error is not severe; the caller should allow the copy operation to continue.</span></span>
    
<span data-ttu-id="bb064-162">MAPI_E_INVALID_TYPE</span><span class="sxs-lookup"><span data-stu-id="bb064-162">MAPI_E_INVALID_TYPE</span></span> 
  
> <span data-ttu-id="bb064-163">属性类型无效。</span><span class="sxs-lookup"><span data-stu-id="bb064-163">The property type is invalid.</span></span>
    
<span data-ttu-id="bb064-164">MAPI_E_UNEXPECTED_TYPE</span><span class="sxs-lookup"><span data-stu-id="bb064-164">MAPI_E_UNEXPECTED_TYPE</span></span> 
  
> <span data-ttu-id="bb064-165">属性类型不需要呼叫者的类型。</span><span class="sxs-lookup"><span data-stu-id="bb064-165">The property type is not the type expected by the caller.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="bb064-166">说明</span><span class="sxs-lookup"><span data-stu-id="bb064-166">Remarks</span></span>

<span data-ttu-id="bb064-167">**IMAPIProp::CopyProps**方法复制，或将所选的属性从当前对象移动到目标对象。</span><span class="sxs-lookup"><span data-stu-id="bb064-167">The **IMAPIProp::CopyProps** method copies or moves selected properties from the current object to a destination object.</span></span> <span data-ttu-id="bb064-168">**CopyProps**主要用于答复或转发的邮件，其中只将某些从原始邮件属性的差旅与答复或转发副本。</span><span class="sxs-lookup"><span data-stu-id="bb064-168">**CopyProps** is used mainly for replying to and forwarding messages, where only some of the properties from the original message travel with the reply or forwarded copy.</span></span> 
  
<span data-ttu-id="bb064-169">源对象中的任何子对象自动包括在操作并复制或移动全部，无论使用了由[SPropTagArray](sproptagarray.md)结构指示的属性。</span><span class="sxs-lookup"><span data-stu-id="bb064-169">Any subobjects in the source object are automatically included in the operation and copied or moved in their entirety, regardless of the use of properties indicated by the [SPropTagArray](sproptagarray.md) structure.</span></span> <span data-ttu-id="bb064-170">默认情况下**CopyProps**覆盖目标对象的匹配从源对象的属性的任何属性。</span><span class="sxs-lookup"><span data-stu-id="bb064-170">By default, **CopyProps** overwrites any properties in the destination object that match properties from the source object.</span></span> <span data-ttu-id="bb064-171">如果任一复制或移动属性已经存在于目标对象，除非 MAPI_NOREPLACE 标志设置_ulFlags_参数中通过新的属性，来覆盖现有属性。</span><span class="sxs-lookup"><span data-stu-id="bb064-171">If any of the copied or moved properties already exist in the destination object, the existing properties are overwritten by the new properties, unless the MAPI_NOREPLACE flag is set in the  _ulFlags_ parameter.</span></span> <span data-ttu-id="bb064-172">保持不变，不会被覆盖的目标对象中的现有信息。</span><span class="sxs-lookup"><span data-stu-id="bb064-172">Existing information in the destination object that is not overwritten is left untouched.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="bb064-173">针对实施者的注释</span><span class="sxs-lookup"><span data-stu-id="bb064-173">Notes to implementers</span></span>

<span data-ttu-id="bb064-174">您可以提供**CopyProps**完全实现或依赖 MAPI 提供其支持对象中的实现。</span><span class="sxs-lookup"><span data-stu-id="bb064-174">You can provide a full implementation of **CopyProps** or rely on the implementation that MAPI provides in its support object.</span></span> <span data-ttu-id="bb064-175">如果您想要使用的 MAPI 实现，调用**IMAPISupport::DoCopyProps**方法。</span><span class="sxs-lookup"><span data-stu-id="bb064-175">If you want to use the MAPI implementation, call the **IMAPISupport::DoCopyProps** method.</span></span> <span data-ttu-id="bb064-176">但是，如果您执行委派到**DoCopyProps**处理和传递 MAPI_DECLINE_OK 标志，避免支持呼叫并改为返回 MAPI_E_DECLINE_COPY。</span><span class="sxs-lookup"><span data-stu-id="bb064-176">However, if you do delegate processing to **DoCopyProps** and you are passed the MAPI_DECLINE_OK flag, avoid the support call and return MAPI_E_DECLINE_COPY instead.</span></span> <span data-ttu-id="bb064-177">您将使用此标志由调用 MAPI 以避免可能递归复制文件夹时可能发生的。</span><span class="sxs-lookup"><span data-stu-id="bb064-177">You will be called with this flag by MAPI to avoid the possible recursion that can occur when you copy folders.</span></span> 
  
<span data-ttu-id="bb064-178">因为复制操作可能很长，您应显示进度指示器。</span><span class="sxs-lookup"><span data-stu-id="bb064-178">Because the copy operation can be lengthy, you should display a progress indicator.</span></span> <span data-ttu-id="bb064-179">如果存在，请使用_lpProgress_参数中传递的[IMAPIProgress](imapiprogressiunknown.md)实现。</span><span class="sxs-lookup"><span data-stu-id="bb064-179">Use the [IMAPIProgress](imapiprogressiunknown.md) implementation that is passed in the  _lpProgress_ parameter, if there is one.</span></span> <span data-ttu-id="bb064-180">如果_lpProgress_为**null**，调用[IMAPISupport::DoProgressDialog](imapisupport-doprogressdialog.md)方法使用 MAPI 实现。</span><span class="sxs-lookup"><span data-stu-id="bb064-180">If  _lpProgress_ is **null**, call the [IMAPISupport::DoProgressDialog](imapisupport-doprogressdialog.md) method to use the MAPI implementation.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="bb064-181">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="bb064-181">Notes to callers</span></span>

<span data-ttu-id="bb064-182">不设置 MAPI_DECLINE_OK 标志;它用于通过 MAPI 其呼叫消息存储提供程序**CopyProps**实现。</span><span class="sxs-lookup"><span data-stu-id="bb064-182">Do not set the MAPI_DECLINE_OK flag; it is used by MAPI in its calls to message store provider **CopyProps** implementations.</span></span> 
  
<span data-ttu-id="bb064-183">因为复制和移动操作可能需要花费时间，则最好通过设置 MAPI_DIALOG 标志请求的进度指示器显示。</span><span class="sxs-lookup"><span data-stu-id="bb064-183">Because copy and move operations can take time, it is wise to request the display of a progress indicator by setting the MAPI_DIALOG flag.</span></span> <span data-ttu-id="bb064-184">您可以将_lpProgress_参数设置的**IMAPIProgress**，如果您没有实现或**null**。</span><span class="sxs-lookup"><span data-stu-id="bb064-184">You can set the  _lpProgress_ parameter to your implementation of **IMAPIProgress**, if you have one, or to **null**.</span></span> <span data-ttu-id="bb064-185">如果_lpProgress_为**null**， **CopyProps**将使用 MAPI 提供默认进度指示器。</span><span class="sxs-lookup"><span data-stu-id="bb064-185">If  _lpProgress_ is **null**, **CopyProps** will use the default progress indicator provided by MAPI.</span></span> 
  
<span data-ttu-id="bb064-186">您可以通过不设置 MAPI_DIALOG 标志来禁止显示进度指示器。</span><span class="sxs-lookup"><span data-stu-id="bb064-186">You can suppress the display of a progress indicator by not setting the MAPI_DIALOG flag.</span></span> <span data-ttu-id="bb064-187">**CopyProps**将忽略的_ulUIParam_和_lpProgress_参数，并避免显示指示器。</span><span class="sxs-lookup"><span data-stu-id="bb064-187">**CopyProps** will ignore the  _ulUIParam_ and  _lpProgress_ parameters and avoid displaying the indicator.</span></span> 
  
 <span data-ttu-id="bb064-188">**CopyProps**可以报告全局和单个错误，或者与一个或多个属性发生的错误。</span><span class="sxs-lookup"><span data-stu-id="bb064-188">**CopyProps** can report global and individual errors, or errors that occur with one or more of the properties.</span></span> <span data-ttu-id="bb064-189">这些单个错误保持**SPropProblemArray**结构中。</span><span class="sxs-lookup"><span data-stu-id="bb064-189">These individual errors are put in an **SPropProblemArray** structure.</span></span> <span data-ttu-id="bb064-190">您可以隐藏错误属性级别通过传递**null**，而不是有效的指针，property 问题数组结构参数的报告。</span><span class="sxs-lookup"><span data-stu-id="bb064-190">You can suppress error reporting at the property level by passing **null**, instead of a valid pointer, for the property problem array structure parameter.</span></span> 
  
<span data-ttu-id="bb064-191">如果您想要接收有关错误的信息，请在_lppProblems_参数中传递一个有效的**SPropProblemArray**结构指针。</span><span class="sxs-lookup"><span data-stu-id="bb064-191">If you want to receive information about errors, pass a valid **SPropProblemArray** structure pointer in the  _lppProblems_ parameter.</span></span> <span data-ttu-id="bb064-192">时**CopyProps** ，则返回 S_OK，检查与结构中的各个属性的可能错误。</span><span class="sxs-lookup"><span data-stu-id="bb064-192">When **CopyProps** returns S_OK, check for possible errors with individual properties in the structure.</span></span> <span data-ttu-id="bb064-193">当**CopyProps**返回错误时， **SPropProblemArray**结构中不返回任何信息。</span><span class="sxs-lookup"><span data-stu-id="bb064-193">When **CopyProps** returns an error, no information is returned in the **SPropProblemArray** structure.</span></span> <span data-ttu-id="bb064-194">相反，调用[IMAPIProp::GetLastError](imapiprop-getlasterror.md)方法检索详细的错误信息。</span><span class="sxs-lookup"><span data-stu-id="bb064-194">Instead, call the [IMAPIProp::GetLastError](imapiprop-getlasterror.md) method to retrieve detailed error information.</span></span> 
  
<span data-ttu-id="bb064-195">如果**CopyProps** ，则返回 S_OK，通过调用[MAPIFreeBuffer](mapifreebuffer.md)函数释放返回的**SPropProblemArray**结构。</span><span class="sxs-lookup"><span data-stu-id="bb064-195">If **CopyProps** returns S_OK, free the returned **SPropProblemArray** structure by calling the [MAPIFreeBuffer](mapifreebuffer.md) function.</span></span> 
  
<span data-ttu-id="bb064-196">如果要复制对源对象类型是唯一的属性，您必须确保目标对象属于同一类型。</span><span class="sxs-lookup"><span data-stu-id="bb064-196">If you are copying properties that are unique to the source object type, you must make sure that the destination object is of the same type.</span></span> <span data-ttu-id="bb064-197">**CopyProps**不阻止您关联通常属于一种类型的对象与其他类型的对象的属性。</span><span class="sxs-lookup"><span data-stu-id="bb064-197">**CopyProps** does not prevent you from associating properties that typically belong to one type of object with another type of object.</span></span> <span data-ttu-id="bb064-198">由您要复制对目标对象有意义的属性。</span><span class="sxs-lookup"><span data-stu-id="bb064-198">It is up to you to copy properties that make sense for the destination object.</span></span> <span data-ttu-id="bb064-199">例如，不应将消息属性复制到通讯簿容器。</span><span class="sxs-lookup"><span data-stu-id="bb064-199">For example, you should not copy message properties to an address book container.</span></span> 
  
<span data-ttu-id="bb064-200">若要确保您要复制的相同类型的对象之间，检查源和目标对象相同的类型，通过比较对象指针或调用[IUnknown::QueryInterface](http://msdn.microsoft.com/library/54d5ff80-18db-43f2-b636-f93ac053146d%28Office.15%29.aspx)方法。</span><span class="sxs-lookup"><span data-stu-id="bb064-200">To ensure that you are copying between objects of the same type, check that the source and destination object are the same type, either by comparing object pointers or calling the [IUnknown::QueryInterface](http://msdn.microsoft.com/library/54d5ff80-18db-43f2-b636-f93ac053146d%28Office.15%29.aspx) method.</span></span> <span data-ttu-id="bb064-201">设置所指的源对象的标准接口_lpInterface_接口标识符。</span><span class="sxs-lookup"><span data-stu-id="bb064-201">Set the interface identifier pointed to by  _lpInterface_ to the standard interface for the source object.</span></span> <span data-ttu-id="bb064-202">此外，还要确保**PR_OBJECT_TYPE** ([PidTagObjectType](pidtagobjecttype-canonical-property.md)) 属性的对象类型是相同的两个对象。</span><span class="sxs-lookup"><span data-stu-id="bb064-202">Also, ensure that the object type or **PR_OBJECT_TYPE** ([PidTagObjectType](pidtagobjecttype-canonical-property.md)) property is the same for the two objects.</span></span> <span data-ttu-id="bb064-203">例如，如果您从一条消息中进行复制，则可设置为 IID_IMessage 和**PR_OBJECT_TYPE** MAPI_MESSAGE 这两个对象的_lpInterface_ 。</span><span class="sxs-lookup"><span data-stu-id="bb064-203">For example, if you are copying from a message, set  _lpInterface_ to IID_IMessage and the **PR_OBJECT_TYPE** for both objects to MAPI_MESSAGE.</span></span> 
  
<span data-ttu-id="bb064-204">如果_lpDestObj_参数中传递了无效的指针，则结果将无法预料。</span><span class="sxs-lookup"><span data-stu-id="bb064-204">If an invalid pointer is passed in the  _lpDestObj_ parameter, the results are unpredictable.</span></span> 
  
<span data-ttu-id="bb064-205">要复制邮件的收件人列表，请调用消息的**CopyProps**方法和属性标记数组中包含的**PR_MESSAGE_RECIPIENTS** ([PidTagMessageRecipients](pidtagmessagerecipients-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="bb064-205">To copy a message's recipient list, call the message's **CopyProps** method and include the **PR_MESSAGE_RECIPIENTS** ([PidTagMessageRecipients](pidtagmessagerecipients-canonical-property.md)) property in the property tag array.</span></span> <span data-ttu-id="bb064-206">若要复制邮件的附件，包括**PR_MESSAGE_ATTACHMENTS** ([PidTagMessageAttachments](pidtagmessageattachments-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="bb064-206">To copy the message's attachments, include the **PR_MESSAGE_ATTACHMENTS** ([PidTagMessageAttachments](pidtagmessageattachments-canonical-property.md)) property.</span></span> 
  
<span data-ttu-id="bb064-207">要复制的文件夹或通讯簿容器层次结构或内容表，包含**PR_CONTAINER_HIERARCHY** ([PidTagContainerHierarchy](pidtagcontainerhierarchy-canonical-property.md)) 或**PR_CONTAINER_CONTENTS** ([PidTagContainerContents](pidtagcontainercontents-canonical-property.md)) 中的属性属性标记数组。</span><span class="sxs-lookup"><span data-stu-id="bb064-207">To copy a folder or address book container's hierarchy or contents table, include the **PR_CONTAINER_HIERARCHY** ([PidTagContainerHierarchy](pidtagcontainerhierarchy-canonical-property.md)) or **PR_CONTAINER_CONTENTS** ([PidTagContainerContents](pidtagcontainercontents-canonical-property.md)) properties in the property tag array.</span></span> <span data-ttu-id="bb064-208">若要包含的文件夹关联的内容表，该数组中包括**PR_FOLDER_ASSOCIATED_CONTENTS** ([PidTagFolderAssociatedContents](pidtagfolderassociatedcontents-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="bb064-208">To include a folder's associated contents table, include the **PR_FOLDER_ASSOCIATED_CONTENTS** ([PidTagFolderAssociatedContents](pidtagfolderassociatedcontents-canonical-property.md)) property in the array.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="bb064-209">MFCMAPI 参考 （英文）</span><span class="sxs-lookup"><span data-stu-id="bb064-209">MFCMAPI reference</span></span>

<span data-ttu-id="bb064-210">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="bb064-210">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="bb064-211">**文件**</span><span class="sxs-lookup"><span data-stu-id="bb064-211">**File**</span></span>|<span data-ttu-id="bb064-212">**函数**</span><span class="sxs-lookup"><span data-stu-id="bb064-212">**Function**</span></span>|<span data-ttu-id="bb064-213">**Comment**</span><span class="sxs-lookup"><span data-stu-id="bb064-213">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="bb064-214">MAPIFunctions.cpp</span><span class="sxs-lookup"><span data-stu-id="bb064-214">MAPIFunctions.cpp</span></span>  <br/> |<span data-ttu-id="bb064-215">CopyNamedProps</span><span class="sxs-lookup"><span data-stu-id="bb064-215">CopyNamedProps</span></span>  <br/> |<span data-ttu-id="bb064-216">MFCMAPI 使用**IMAPIProp::CopyProps**方法将命名的属性复制到另一条消息。</span><span class="sxs-lookup"><span data-stu-id="bb064-216">MFCMAPI uses the **IMAPIProp::CopyProps** method to copy named properties from one message to another.</span></span>  <br/> |
|<span data-ttu-id="bb064-217">SingleMAPIPropListCtrl.cpp</span><span class="sxs-lookup"><span data-stu-id="bb064-217">SingleMAPIPropListCtrl.cpp</span></span>  <br/> |<span data-ttu-id="bb064-218">CSingleMAPIPropListCtrl::OnPasteProperty</span><span class="sxs-lookup"><span data-stu-id="bb064-218">CSingleMAPIPropListCtrl::OnPasteProperty</span></span>  <br/> |<span data-ttu-id="bb064-219">MFCMAPI 使用**IMAPIProp::CopyProps**方法粘贴已复制从另一个对象的属性。</span><span class="sxs-lookup"><span data-stu-id="bb064-219">MFCMAPI uses the **IMAPIProp::CopyProps** method to paste a property that has been copied from another object.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="bb064-220">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bb064-220">See also</span></span>



[<span data-ttu-id="bb064-221">IMAPIFolder::CopyMessages</span><span class="sxs-lookup"><span data-stu-id="bb064-221">IMAPIFolder::CopyMessages</span></span>](imapifolder-copymessages.md)
  
[<span data-ttu-id="bb064-222">IMAPIProgress : IUnknown</span><span class="sxs-lookup"><span data-stu-id="bb064-222">IMAPIProgress : IUnknown</span></span>](imapiprogressiunknown.md)
  
[<span data-ttu-id="bb064-223">IMAPIProp::CopyTo</span><span class="sxs-lookup"><span data-stu-id="bb064-223">IMAPIProp::CopyTo</span></span>](imapiprop-copyto.md)
  
[<span data-ttu-id="bb064-224">IMAPIProp::GetLastError</span><span class="sxs-lookup"><span data-stu-id="bb064-224">IMAPIProp::GetLastError</span></span>](imapiprop-getlasterror.md)
  
[<span data-ttu-id="bb064-225">IMAPISupport::DoCopyProps</span><span class="sxs-lookup"><span data-stu-id="bb064-225">IMAPISupport::DoCopyProps</span></span>](imapisupport-docopyprops.md)
  
[<span data-ttu-id="bb064-226">IMAPISupport::DoProgressDialog</span><span class="sxs-lookup"><span data-stu-id="bb064-226">IMAPISupport::DoProgressDialog</span></span>](imapisupport-doprogressdialog.md)
  
[<span data-ttu-id="bb064-227">MAPIFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="bb064-227">MAPIFreeBuffer</span></span>](mapifreebuffer.md)
  
[<span data-ttu-id="bb064-228">PidTagContainerContents 规范属性</span><span class="sxs-lookup"><span data-stu-id="bb064-228">PidTagContainerContents Canonical Property</span></span>](pidtagcontainercontents-canonical-property.md)
  
[<span data-ttu-id="bb064-229">PidTagContainerHierarchy 规范属性</span><span class="sxs-lookup"><span data-stu-id="bb064-229">PidTagContainerHierarchy Canonical Property</span></span>](pidtagcontainerhierarchy-canonical-property.md)
  
[<span data-ttu-id="bb064-230">PidTagDisplayName 规范属性</span><span class="sxs-lookup"><span data-stu-id="bb064-230">PidTagDisplayName Canonical Property</span></span>](pidtagdisplayname-canonical-property.md)
  
[<span data-ttu-id="bb064-231">PidTagFolderAssociatedContents 规范属性</span><span class="sxs-lookup"><span data-stu-id="bb064-231">PidTagFolderAssociatedContents Canonical Property</span></span>](pidtagfolderassociatedcontents-canonical-property.md)
  
[<span data-ttu-id="bb064-232">PidTagMessageAttachments 规范属性</span><span class="sxs-lookup"><span data-stu-id="bb064-232">PidTagMessageAttachments Canonical Property</span></span>](pidtagmessageattachments-canonical-property.md)
  
[<span data-ttu-id="bb064-233">PidTagMessageRecipients 规范属性</span><span class="sxs-lookup"><span data-stu-id="bb064-233">PidTagMessageRecipients Canonical Property</span></span>](pidtagmessagerecipients-canonical-property.md)
  
[<span data-ttu-id="bb064-234">PidTagObjectType 规范属性</span><span class="sxs-lookup"><span data-stu-id="bb064-234">PidTagObjectType Canonical Property</span></span>](pidtagobjecttype-canonical-property.md)
  
[<span data-ttu-id="bb064-235">SPropProblemArray</span><span class="sxs-lookup"><span data-stu-id="bb064-235">SPropProblemArray</span></span>](spropproblemarray.md)
  
[<span data-ttu-id="bb064-236">SPropTagArray</span><span class="sxs-lookup"><span data-stu-id="bb064-236">SPropTagArray</span></span>](sproptagarray.md)
  
[<span data-ttu-id="bb064-237">IMAPIProp : IUnknown</span><span class="sxs-lookup"><span data-stu-id="bb064-237">IMAPIProp : IUnknown</span></span>](imapipropiunknown.md)


[<span data-ttu-id="bb064-238">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="bb064-238">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

