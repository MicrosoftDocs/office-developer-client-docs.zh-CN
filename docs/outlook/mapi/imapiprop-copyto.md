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
# <a name="imapipropcopyto"></a><span data-ttu-id="08b8b-103">IMAPIProp::CopyTo</span><span class="sxs-lookup"><span data-stu-id="08b8b-103">IMAPIProp::CopyTo</span></span>

  
  
<span data-ttu-id="08b8b-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="08b8b-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="08b8b-105">复制或移动所有属性, 但特殊排除的属性除外。</span><span class="sxs-lookup"><span data-stu-id="08b8b-105">Copies or moves all properties, except for specifically excluded properties.</span></span>
  
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

## <a name="parameters"></a><span data-ttu-id="08b8b-106">参数</span><span class="sxs-lookup"><span data-stu-id="08b8b-106">Parameters</span></span>

 <span data-ttu-id="08b8b-107">_ciidExclude_</span><span class="sxs-lookup"><span data-stu-id="08b8b-107">_ciidExclude_</span></span>
  
> <span data-ttu-id="08b8b-108">实时复制或移动属性时要排除的接口数。</span><span class="sxs-lookup"><span data-stu-id="08b8b-108">[in] The count of interfaces to exclude when properties are copied or moved.</span></span>
    
 <span data-ttu-id="08b8b-109">_rgiidExclude_</span><span class="sxs-lookup"><span data-stu-id="08b8b-109">_rgiidExclude_</span></span>
  
> <span data-ttu-id="08b8b-110">实时一个接口标识符 (IIDs) 的数组, 该数组指定在将补充信息复制或移动到目标对象时不应使用的接口。</span><span class="sxs-lookup"><span data-stu-id="08b8b-110">[in] An array of interface identifiers (IIDs) that specify interfaces that should not be used when supplemental information is copied or moved to the destination object.</span></span>
    
 <span data-ttu-id="08b8b-111">_lpExcludeProps_</span><span class="sxs-lookup"><span data-stu-id="08b8b-111">_lpExcludeProps_</span></span>
  
> <span data-ttu-id="08b8b-112">实时一个指向属性标记数组的指针, 该数组标识应从复制或移动操作中排除的属性标记。</span><span class="sxs-lookup"><span data-stu-id="08b8b-112">[in] A pointer to a property tag array that identifies the property tags that should be excluded from the copy or move operation.</span></span> <span data-ttu-id="08b8b-113">在_lpExcludeProps_参数中传递**null**表示应复制或移动对象的所有属性。</span><span class="sxs-lookup"><span data-stu-id="08b8b-113">Passing **null** in the  _lpExcludeProps_ parameter indicates that all of the object's properties should be copied or moved.</span></span> <span data-ttu-id="08b8b-114">当_lpExcludeProps_指向的[SPropProblemArray](spropproblemarray.md)结构的**cValues**成员设置为0时, **CopyTo**将返回 MAPI_E_INVALID_PARAMETER。</span><span class="sxs-lookup"><span data-stu-id="08b8b-114">**CopyTo** returns MAPI_E_INVALID_PARAMETER when the **cValues** member of the [SPropProblemArray](spropproblemarray.md) structure pointed to by  _lpExcludeProps_ is set to 0.</span></span> 
    
 <span data-ttu-id="08b8b-115">_ulUIParam_</span><span class="sxs-lookup"><span data-stu-id="08b8b-115">_ulUIParam_</span></span>
  
> <span data-ttu-id="08b8b-116">实时进度指示器的父窗口的句柄。</span><span class="sxs-lookup"><span data-stu-id="08b8b-116">[in] A handle to the parent window of the progress indicator.</span></span> 
    
 <span data-ttu-id="08b8b-117">_lpProgress_</span><span class="sxs-lookup"><span data-stu-id="08b8b-117">_lpProgress_</span></span>
  
> <span data-ttu-id="08b8b-118">实时指向进度指示器实现的指针。</span><span class="sxs-lookup"><span data-stu-id="08b8b-118">[in] A pointer to a progress indicator implementation.</span></span> <span data-ttu-id="08b8b-119">如果在_lpProgress_参数中传递**null** , MAPI 将提供进度实现。</span><span class="sxs-lookup"><span data-stu-id="08b8b-119">If **null** is passed in the  _lpProgress_ parameter, MAPI provides the progress implementation.</span></span> <span data-ttu-id="08b8b-120">除非在_ulFlags_参数中设置了 MAPI_DIALOG 标志, 否则将忽略_lpProgress_参数。</span><span class="sxs-lookup"><span data-stu-id="08b8b-120">The  _lpProgress_ parameter is ignored unless the MAPI_DIALOG flag is set in the  _ulFlags_ parameter.</span></span> 
    
 <span data-ttu-id="08b8b-121">_lpInterface_</span><span class="sxs-lookup"><span data-stu-id="08b8b-121">_lpInterface_</span></span>
  
> <span data-ttu-id="08b8b-122">实时指向接口标识符 (IID) 的指针, 该接口标识符表示用于访问_lpDestObj_参数所指向的对象的接口。</span><span class="sxs-lookup"><span data-stu-id="08b8b-122">[in] A pointer to the interface identifier (IID) that represents the interface to be used to access the object pointed to by the  _lpDestObj_ parameter.</span></span> <span data-ttu-id="08b8b-123">_lpInterface_参数不能为**null**。</span><span class="sxs-lookup"><span data-stu-id="08b8b-123">The  _lpInterface_ parameter must not be **null**.</span></span>
    
 <span data-ttu-id="08b8b-124">_lpDestObj_</span><span class="sxs-lookup"><span data-stu-id="08b8b-124">_lpDestObj_</span></span>
  
> <span data-ttu-id="08b8b-125">实时指向接收复制或移动的属性的对象的指针。</span><span class="sxs-lookup"><span data-stu-id="08b8b-125">[in] A pointer to the object to receive the copied or moved properties.</span></span>
    
 <span data-ttu-id="08b8b-126">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="08b8b-126">_ulFlags_</span></span>
  
> <span data-ttu-id="08b8b-127">实时用于控制复制或移动操作的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="08b8b-127">[in] A bitmask of flags that controls the copy or move operation.</span></span> <span data-ttu-id="08b8b-128">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="08b8b-128">The following flags can be set:</span></span>
    
<span data-ttu-id="08b8b-129">MAPI_DECLINE_OK</span><span class="sxs-lookup"><span data-stu-id="08b8b-129">MAPI_DECLINE_OK</span></span> 
  
> <span data-ttu-id="08b8b-130">如果**CopyTo**调用[IMAPISupport::D ocopyto](imapisupport-docopyto.md)方法来处理复制或移动操作, 则应立即返回错误值 MAPI_E_DECLINE_COPY。</span><span class="sxs-lookup"><span data-stu-id="08b8b-130">If **CopyTo** calls the [IMAPISupport::DoCopyTo](imapisupport-docopyto.md) method to handle the copy or move operation, it should instead return immediately with the error value MAPI_E_DECLINE_COPY.</span></span> <span data-ttu-id="08b8b-131">MAPI_DECLINE_OK 标志由 MAPI 设置以限制递归。</span><span class="sxs-lookup"><span data-stu-id="08b8b-131">The MAPI_DECLINE_OK flag is set by MAPI to limit recursion.</span></span> <span data-ttu-id="08b8b-132">客户端不设置此标志。</span><span class="sxs-lookup"><span data-stu-id="08b8b-132">Clients do not set this flag.</span></span> 
    
<span data-ttu-id="08b8b-133">MAPI_DIALOG</span><span class="sxs-lookup"><span data-stu-id="08b8b-133">MAPI_DIALOG</span></span> 
  
> <span data-ttu-id="08b8b-134">显示进度指示器。</span><span class="sxs-lookup"><span data-stu-id="08b8b-134">Displays a progress indicator.</span></span>
    
<span data-ttu-id="08b8b-135">MAPI_MOVE</span><span class="sxs-lookup"><span data-stu-id="08b8b-135">MAPI_MOVE</span></span> 
  
> <span data-ttu-id="08b8b-136">**CopyTo**应执行移动操作, 而不是复制操作。</span><span class="sxs-lookup"><span data-stu-id="08b8b-136">**CopyTo** should perform a move operation instead of a copy operation.</span></span> <span data-ttu-id="08b8b-137">如果未设置此标志, **CopyTo**将执行复制操作。</span><span class="sxs-lookup"><span data-stu-id="08b8b-137">When this flag is not set, **CopyTo** performs a copy operation.</span></span> 
    
<span data-ttu-id="08b8b-138">MAPI_NOREPLACE</span><span class="sxs-lookup"><span data-stu-id="08b8b-138">MAPI_NOREPLACE</span></span> 
  
> <span data-ttu-id="08b8b-139">不应覆盖目标对象中的现有属性。</span><span class="sxs-lookup"><span data-stu-id="08b8b-139">Existing properties in the destination object should not be overwritten.</span></span> <span data-ttu-id="08b8b-140">如果未设置此标志, **CopyTo**将覆盖现有属性。</span><span class="sxs-lookup"><span data-stu-id="08b8b-140">When this flag is not set, **CopyTo** overwrites existing properties.</span></span> 
    
 <span data-ttu-id="08b8b-141">_lppProblems_</span><span class="sxs-lookup"><span data-stu-id="08b8b-141">_lppProblems_</span></span>
  
> <span data-ttu-id="08b8b-142">[in, out]在输入时, 指向指向**SPropProblemArray**结构的指针的指针;否则**为 null**, 表示无需错误信息。</span><span class="sxs-lookup"><span data-stu-id="08b8b-142">[in, out] On input, a pointer to a pointer to an **SPropProblemArray** structure; otherwise, **null**, indicating no need for error information.</span></span> <span data-ttu-id="08b8b-143">如果_lppProblems_是有效的输入指针, **CopyTo**将返回有关复制一个或多个属性中的错误的详细信息。</span><span class="sxs-lookup"><span data-stu-id="08b8b-143">If  _lppProblems_ is a valid pointer on input, **CopyTo** returns detailed information about errors in copying one or more properties.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="08b8b-144">返回值</span><span class="sxs-lookup"><span data-stu-id="08b8b-144">Return value</span></span>

<span data-ttu-id="08b8b-145">S_OK</span><span class="sxs-lookup"><span data-stu-id="08b8b-145">S_OK</span></span> 
  
> <span data-ttu-id="08b8b-146">已成功复制或移动属性。</span><span class="sxs-lookup"><span data-stu-id="08b8b-146">The properties have been successfully copied or moved.</span></span>
    
<span data-ttu-id="08b8b-147">MAPI_E_COLLISION</span><span class="sxs-lookup"><span data-stu-id="08b8b-147">MAPI_E_COLLISION</span></span> 
  
> <span data-ttu-id="08b8b-148">无法复制子对象, 因为目标对象中已存在具有相同显示名称 (由**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 属性指定) 的子对象。</span><span class="sxs-lookup"><span data-stu-id="08b8b-148">A subobject cannot be copied because a subobject with the same display name — specified by the **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) property — already exists in the destination object.</span></span> 
    
<span data-ttu-id="08b8b-149">MAPI_E_DECLINE_COPY</span><span class="sxs-lookup"><span data-stu-id="08b8b-149">MAPI_E_DECLINE_COPY</span></span> 
  
> <span data-ttu-id="08b8b-150">服务提供程序不实施复制操作。</span><span class="sxs-lookup"><span data-stu-id="08b8b-150">The service provider does not implement the copy operation.</span></span>
    
<span data-ttu-id="08b8b-151">MAPI_E_FOLDER_CYCLE</span><span class="sxs-lookup"><span data-stu-id="08b8b-151">MAPI_E_FOLDER_CYCLE</span></span> 
  
> <span data-ttu-id="08b8b-152">执行复制或移动操作直接或间接包含目标对象的源对象。</span><span class="sxs-lookup"><span data-stu-id="08b8b-152">The source object performing the copy or move operation directly or indirectly contains the destination object.</span></span> <span data-ttu-id="08b8b-153">在发现此条件之前, 可能已经执行了大量的工作, 因此源和目标对象可能被部分修改。</span><span class="sxs-lookup"><span data-stu-id="08b8b-153">Significant work might have been performed before this condition was discovered, so the source and destination objects might be partially modified.</span></span> 
    
<span data-ttu-id="08b8b-154">MAPI_E_INTERFACE_NOT_SUPPORTED</span><span class="sxs-lookup"><span data-stu-id="08b8b-154">MAPI_E_INTERFACE_NOT_SUPPORTED</span></span> 
  
> <span data-ttu-id="08b8b-155">目标对象不支持由_lpInterface_参数标识的接口。</span><span class="sxs-lookup"><span data-stu-id="08b8b-155">The interface identified by the  _lpInterface_ parameter is not supported by the destination object.</span></span> 
    
<span data-ttu-id="08b8b-156">MAPI_E_NO_ACCESS</span><span class="sxs-lookup"><span data-stu-id="08b8b-156">MAPI_E_NO_ACCESS</span></span> 
  
> <span data-ttu-id="08b8b-157">试图访问呼叫者没有足够权限的对象。</span><span class="sxs-lookup"><span data-stu-id="08b8b-157">An attempt was made to access an object for which the caller has insufficient permissions.</span></span> <span data-ttu-id="08b8b-158">如果目标对象与源对象相同, 则返回此错误。</span><span class="sxs-lookup"><span data-stu-id="08b8b-158">This error is returned if the destination object is the same as the source object.</span></span>
    
<span data-ttu-id="08b8b-159">以下值可在**SPropProblemArray**结构中返回, 但不能在**CopyTo**的返回值中返回。</span><span class="sxs-lookup"><span data-stu-id="08b8b-159">The following values can be returned in the **SPropProblemArray** structure, but not as return values for **CopyTo**.</span></span> <span data-ttu-id="08b8b-160">以下错误适用于单个属性:</span><span class="sxs-lookup"><span data-stu-id="08b8b-160">The following errors apply to a single property:</span></span>
  
<span data-ttu-id="08b8b-161">MAPI_E_BAD_CHARWIDTH</span><span class="sxs-lookup"><span data-stu-id="08b8b-161">MAPI_E_BAD_CHARWIDTH</span></span> 
  
> <span data-ttu-id="08b8b-162">设置了 MAPI_UNICODE 标志, 并且**copyto**不支持 unicode, 或者未设置 MAPI_UNICODE, **CopyTo**仅支持 UNICODE。</span><span class="sxs-lookup"><span data-stu-id="08b8b-162">Either the MAPI_UNICODE flag was set and **CopyTo** does not support Unicode, or MAPI_UNICODE was not set and **CopyTo** supports only Unicode.</span></span> 
    
<span data-ttu-id="08b8b-163">MAPI_E_COMPUTED</span><span class="sxs-lookup"><span data-stu-id="08b8b-163">MAPI_E_COMPUTED</span></span> 
  
> <span data-ttu-id="08b8b-164">调用程序无法修改该属性, 因为它是由目标对象的所有者计算的只读属性。</span><span class="sxs-lookup"><span data-stu-id="08b8b-164">The property cannot be modified by the caller because it is a read-only property, computed by the owner of the destination object.</span></span> <span data-ttu-id="08b8b-165">此错误不严重;呼叫者应允许复制操作继续进行。</span><span class="sxs-lookup"><span data-stu-id="08b8b-165">This error is not severe; the caller should allow the copy operation to continue.</span></span>
    
<span data-ttu-id="08b8b-166">MAPI_E_INVALID_TYPE</span><span class="sxs-lookup"><span data-stu-id="08b8b-166">MAPI_E_INVALID_TYPE</span></span> 
  
> <span data-ttu-id="08b8b-167">属性类型无效。</span><span class="sxs-lookup"><span data-stu-id="08b8b-167">The property type is invalid.</span></span>
    
<span data-ttu-id="08b8b-168">MAPI_E_UNEXPECTED_TYPE</span><span class="sxs-lookup"><span data-stu-id="08b8b-168">MAPI_E_UNEXPECTED_TYPE</span></span> 
  
> <span data-ttu-id="08b8b-169">属性类型不是调用方预期的类型。</span><span class="sxs-lookup"><span data-stu-id="08b8b-169">The property type is not the type expected by the caller.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="08b8b-170">注解</span><span class="sxs-lookup"><span data-stu-id="08b8b-170">Remarks</span></span>

<span data-ttu-id="08b8b-171">默认情况下, **IMAPIProp:: CopyTo**方法将当前对象的所有属性复制或移动到目标对象。</span><span class="sxs-lookup"><span data-stu-id="08b8b-171">By default, the **IMAPIProp::CopyTo** method copies or moves all of the current object's properties to a destination object.</span></span> <span data-ttu-id="08b8b-172">当对象应完全复制或移动时, 使用其全部或大部分属性保持不变时使用的**CopyTo** 。</span><span class="sxs-lookup"><span data-stu-id="08b8b-172">**CopyTo** is used when an object should be copied or moved exactly, with all or most of its properties intact.</span></span> 
  
<span data-ttu-id="08b8b-173">源对象中的任何子对象将自动包含在操作中, 并将完全复制或移动。</span><span class="sxs-lookup"><span data-stu-id="08b8b-173">Any subobjects in the source object are automatically included in the operation and are copied or moved in their entirety.</span></span> <span data-ttu-id="08b8b-174">默认情况下, **CopyTo**会覆盖目标对象中与源对象的属性相匹配的任何属性。</span><span class="sxs-lookup"><span data-stu-id="08b8b-174">By default, **CopyTo** overwrites any properties in the destination object that match properties from the source object.</span></span> <span data-ttu-id="08b8b-175">如果目标对象中已存在任何复制或移动的属性, 则新属性将覆盖现有属性, 除非在_ulFlags_参数中设置 MAPI_NOREPLACE 标志。</span><span class="sxs-lookup"><span data-stu-id="08b8b-175">If any of the copied or moved properties already exist in the destination object, the existing properties are overwritten by the new properties, unless the MAPI_NOREPLACE flag is set in the  _ulFlags_ parameter.</span></span> <span data-ttu-id="08b8b-176">不会覆盖的目标对象中的现有信息将保持不变。</span><span class="sxs-lookup"><span data-stu-id="08b8b-176">Existing information in the destination object that is not overwritten is left untouched.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="08b8b-177">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="08b8b-177">Notes to implementers</span></span>

<span data-ttu-id="08b8b-178">您可以提供**CopyTo**的完全实现, 也可以依赖 MAPI 在其支持对象中提供的实现。</span><span class="sxs-lookup"><span data-stu-id="08b8b-178">You can provide a full implementation of **CopyTo** or rely on the implementation that MAPI provides in its support object.</span></span> <span data-ttu-id="08b8b-179">如果要使用 MAPI 实现, 请调用**IMAPISupport::D ocopyto**。</span><span class="sxs-lookup"><span data-stu-id="08b8b-179">If you want to use the MAPI implementation, call **IMAPISupport::DoCopyTo**.</span></span> <span data-ttu-id="08b8b-180">但是, 如果您将处理委派给**DoCopyTo** , 并且您已传递 MAPI_DECLINE_OK 标志, 请避免支持呼叫, 而改为返回 MAPI_E_DECLINE_COPY。</span><span class="sxs-lookup"><span data-stu-id="08b8b-180">However, if you do delegate processing to **DoCopyTo** and you are passed the MAPI_DECLINE_OK flag, avoid the support call and return MAPI_E_DECLINE_COPY instead.</span></span> <span data-ttu-id="08b8b-181">MAPI 将使用此标志进行呼叫, 以避免在复制文件夹时可能发生的递归。</span><span class="sxs-lookup"><span data-stu-id="08b8b-181">MAPI will call with this flag to avoid the possible recursion that can happen when folders are copied.</span></span> 
  
<span data-ttu-id="08b8b-182">由于复制操作可能很长, 因此应显示进度指示器。</span><span class="sxs-lookup"><span data-stu-id="08b8b-182">Because the copy operation can be lengthy, you should display a progress indicator.</span></span> <span data-ttu-id="08b8b-183">使用在_lpProgress_参数中传递的[IMAPIProgress](imapiprogressiunknown.md)实现 (如果有的话)。</span><span class="sxs-lookup"><span data-stu-id="08b8b-183">Use the [IMAPIProgress](imapiprogressiunknown.md) implementation passed in the  _lpProgress_ parameter, if there is one.</span></span> <span data-ttu-id="08b8b-184">如果_lpProgress_为**null**, 则调用[IMAPISupport::D oprogressdialog](imapisupport-doprogressdialog.md)方法以使用 MAPI 实现。</span><span class="sxs-lookup"><span data-stu-id="08b8b-184">If  _lpProgress_ is **null**, call the [IMAPISupport::DoProgressDialog](imapisupport-doprogressdialog.md) method to use the MAPI implementation.</span></span> 
  
<span data-ttu-id="08b8b-185">请勿尝试在目标对象中设置任何已知的只读属性;改为返回 MAPI_E_NO_ACCESS。</span><span class="sxs-lookup"><span data-stu-id="08b8b-185">Do not attempt to set any known read-only properties in the destination object; return MAPI_E_NO_ACCESS instead.</span></span>
  
<span data-ttu-id="08b8b-186">源和目标对象应使用相同的接口。</span><span class="sxs-lookup"><span data-stu-id="08b8b-186">The source and destination objects should use the same interfaces.</span></span> <span data-ttu-id="08b8b-187">如果未设置_lpInterface_ , 则返回 MAPI_E_INVALID_PARAMETER。</span><span class="sxs-lookup"><span data-stu-id="08b8b-187">Return MAPI_E_INVALID_PARAMETER if  _lpInterface_ is not set.</span></span> 
  
<span data-ttu-id="08b8b-188">如果排除了所有已知接口, 则返回 MAPI_E_INTERFACE_NOT_SUPPORTED。</span><span class="sxs-lookup"><span data-stu-id="08b8b-188">Return MAPI_E_INTERFACE_NOT_SUPPORTED if all known interfaces are excluded.</span></span>
  
## <a name="notes-to-callers"></a><span data-ttu-id="08b8b-189">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="08b8b-189">Notes to callers</span></span>

<span data-ttu-id="08b8b-190">请勿设置 MAPI_DECLINE_OK 标志;MAPI 在其对邮件存储提供程序的**CopyTo**实现中使用它。</span><span class="sxs-lookup"><span data-stu-id="08b8b-190">Do not set the MAPI_DECLINE_OK flag; MAPI uses it in its calls to message store provider **CopyTo** implementations.</span></span> 
  
<span data-ttu-id="08b8b-191">由于复制和移动操作可能需要一些时间, 因此您应通过设置 MAPI_DIALOG 标志来请求显示进度指示器。</span><span class="sxs-lookup"><span data-stu-id="08b8b-191">Because copy and move operations can take time, you should request the display of a progress indicator by setting the MAPI_DIALOG flag.</span></span> <span data-ttu-id="08b8b-192">您可以将_lpProgress_参数设置为**IMAPIProgress**的实现, 如果有, 则设置为**null**。</span><span class="sxs-lookup"><span data-stu-id="08b8b-192">You can set the  _lpProgress_ parameter to your implementation of **IMAPIProgress**, if you have one, or to **null**.</span></span> <span data-ttu-id="08b8b-193">如果_lpProgress_为**null**, 则**CopyTo**将使用 MAPI 提供的默认进度指示器。</span><span class="sxs-lookup"><span data-stu-id="08b8b-193">If  _lpProgress_ is **null**, **CopyTo** will use the default progress indicator that MAPI provides.</span></span> 
  
<span data-ttu-id="08b8b-194">您可以通过不设置 MAPI_DIALOG 标志来禁止显示进度指示器。</span><span class="sxs-lookup"><span data-stu-id="08b8b-194">You can suppress the display of a progress indicator by not setting the MAPI_DIALOG flag.</span></span> <span data-ttu-id="08b8b-195">**CopyTo**将忽略_ulUIParam_和_lpProgress_参数, 并且不会显示指示器。</span><span class="sxs-lookup"><span data-stu-id="08b8b-195">**CopyTo** will ignore the  _ulUIParam_ and  _lpProgress_ parameters and will not display the indicator.</span></span> 
  
 <span data-ttu-id="08b8b-196">**CopyTo**可以报告全局和单个错误, 或一个或多个属性发生的错误。</span><span class="sxs-lookup"><span data-stu-id="08b8b-196">**CopyTo** can report global and individual errors, or errors that occur with one or more properties.</span></span> <span data-ttu-id="08b8b-197">这些单独的错误放在**SPropProblemArray**结构中。</span><span class="sxs-lookup"><span data-stu-id="08b8b-197">These individual errors are placed in an **SPropProblemArray** structure.</span></span> <span data-ttu-id="08b8b-198">您可以通过为属性问题数组结构参数传递**null**(而不是有效的指针) 来抑制属性级别的错误报告。</span><span class="sxs-lookup"><span data-stu-id="08b8b-198">You can suppress error reporting at the property level by passing **null**, instead of a valid pointer, for the property problem array structure parameter.</span></span> 
  
<span data-ttu-id="08b8b-199">如果要接收有关错误的信息, 请在_lppProblems_参数中传递有效的**SPropProblemArray**结构指针。</span><span class="sxs-lookup"><span data-stu-id="08b8b-199">If you want to receive information about errors, pass a valid **SPropProblemArray** structure pointer in the  _lppProblems_ parameter.</span></span> <span data-ttu-id="08b8b-200">当**CopyTo**返回 S_OK 时, 检查结构中的各个属性可能存在的错误。</span><span class="sxs-lookup"><span data-stu-id="08b8b-200">When **CopyTo** returns S_OK, check for possible errors with individual properties in the structure.</span></span> <span data-ttu-id="08b8b-201">当**CopyTo**返回错误时, 不会在**SPropProblemArray**结构中返回任何信息。</span><span class="sxs-lookup"><span data-stu-id="08b8b-201">When **CopyTo** returns an error, no information is returned in the **SPropProblemArray** structure.</span></span> <span data-ttu-id="08b8b-202">而是调用[IMAPIProp:: GetLastError](imapiprop-getlasterror.md)检索详细的错误信息。</span><span class="sxs-lookup"><span data-stu-id="08b8b-202">Instead, call [IMAPIProp::GetLastError](imapiprop-getlasterror.md) to retrieve detailed error information.</span></span> 
  
<span data-ttu-id="08b8b-203">如果**CopyTo**返回 S_OK, 请通过调用[MAPIFreeBuffer](mapifreebuffer.md)函数释放返回的**SPropProblemArray**结构。</span><span class="sxs-lookup"><span data-stu-id="08b8b-203">If **CopyTo** returns S_OK, free the returned **SPropProblemArray** structure by calling the [MAPIFreeBuffer](mapifreebuffer.md) function.</span></span> 
  
<span data-ttu-id="08b8b-204">如果复制源对象类型所特有的属性, 则必须确保目标对象的类型相同。</span><span class="sxs-lookup"><span data-stu-id="08b8b-204">If you copy properties that are unique to the source object type, you must ensure that the destination object is of the same type.</span></span> <span data-ttu-id="08b8b-205">**CopyTo**不会阻止您将通常属于一种类型的对象的属性与另一种类型的对象相关联。</span><span class="sxs-lookup"><span data-stu-id="08b8b-205">**CopyTo** does not prevent you from associating properties that typically belong to one type of object with another type of object.</span></span> <span data-ttu-id="08b8b-206">您将由您来复制对目标对象有意义的属性。</span><span class="sxs-lookup"><span data-stu-id="08b8b-206">It is up to you to copy properties that make sense for the destination object.</span></span> <span data-ttu-id="08b8b-207">例如, 不应将邮件属性复制到通讯簿容器。</span><span class="sxs-lookup"><span data-stu-id="08b8b-207">For example, you should not copy message properties to an address book container.</span></span> 
  
<span data-ttu-id="08b8b-208">若要确保在相同类型的对象之间进行复制, 请通过比较对象指针或调用[IUnknown:: QueryInterface](https://msdn.microsoft.com/library/ms682521%28v=VS.85%29.aspx)来检查源对象和目标对象是否为相同的类型。</span><span class="sxs-lookup"><span data-stu-id="08b8b-208">To ensure that you copy between objects of the same type, check that the source and destination object are the same type, either by comparing object pointers or calling [IUnknown::QueryInterface](https://msdn.microsoft.com/library/ms682521%28v=VS.85%29.aspx).</span></span> <span data-ttu-id="08b8b-209">将_lpInterface_指向的接口标识符设置为源对象的标准接口。</span><span class="sxs-lookup"><span data-stu-id="08b8b-209">Set the interface identifier pointed to by  _lpInterface_ to the standard interface for the source object.</span></span> <span data-ttu-id="08b8b-210">此外, 请确保这两个对象的对象类型或**PR_OBJECT_TYPE** ([PidTagObjectType](pidtagobjecttype-canonical-property.md)) 属性相同。</span><span class="sxs-lookup"><span data-stu-id="08b8b-210">Also, be sure that the object type or **PR_OBJECT_TYPE** ([PidTagObjectType](pidtagobjecttype-canonical-property.md)) property is the same for the two objects.</span></span> <span data-ttu-id="08b8b-211">例如, 如果从邮件中复制, 请将这两个对象的_lpInterface_设置为 IID_IMessage, 并将这两个对象的**PR_OBJECT_TYPE**设置为 MAPI_MESSAGE。</span><span class="sxs-lookup"><span data-stu-id="08b8b-211">For example, if you copy from a message, set  _lpInterface_ to IID_IMessage and the **PR_OBJECT_TYPE** for both objects to MAPI_MESSAGE.</span></span> 
  
<span data-ttu-id="08b8b-212">如果在_lpDestObj_参数中传递无效的指针, 则结果是不可预知的。</span><span class="sxs-lookup"><span data-stu-id="08b8b-212">If an invalid pointer is passed in the  _lpDestObj_ parameter, the results are unpredictable.</span></span> 
  
<span data-ttu-id="08b8b-213">排除**CopyTo**调用中的属性可能有用。</span><span class="sxs-lookup"><span data-stu-id="08b8b-213">Excluding properties on a **CopyTo** call can be useful.</span></span> <span data-ttu-id="08b8b-214">例如, 某些对象具有特定于单个对象实例的属性, 例如邮件传递的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="08b8b-214">For example, some objects have properties that are specific to a single instance of the object, such as the date and time of message delivery.</span></span> <span data-ttu-id="08b8b-215">若要避免在将邮件复制到其他文件夹时复制邮件的传递时间, 请在属性标记 exclude 数组中指定**PR_MESSAGE_DELIVERY_TIME** ([PidTagMessageDeliveryTime](pidtagmessagedeliverytime-canonical-property.md))。</span><span class="sxs-lookup"><span data-stu-id="08b8b-215">To avoid copying a message's delivery time when you copy the message to a different folder, specify **PR_MESSAGE_DELIVERY_TIME** ([PidTagMessageDeliveryTime](pidtagmessagedeliverytime-canonical-property.md)) in the property tag exclude array.</span></span> <span data-ttu-id="08b8b-216">若要排除邮件的收件人列表, 请将**PR_MESSAGE_RECIPIENTS** ([PidTagMessageRecipients](pidtagmessagerecipients-canonical-property.md)) 属性添加到排除数组中。</span><span class="sxs-lookup"><span data-stu-id="08b8b-216">To exclude a message's recipient list, add the **PR_MESSAGE_RECIPIENTS** ([PidTagMessageRecipients](pidtagmessagerecipients-canonical-property.md)) property to the exclude array.</span></span> <span data-ttu-id="08b8b-217">若要排除邮件的附件, 请将**PR_MESSAGE_ATTACHMENTS** ([PidTagMessageAttachments](pidtagmessageattachments-canonical-property.md)) 属性添加到数组中。</span><span class="sxs-lookup"><span data-stu-id="08b8b-217">To exclude a message's attachments, add the **PR_MESSAGE_ATTACHMENTS** ([PidTagMessageAttachments](pidtagmessageattachments-canonical-property.md)) property to the array.</span></span>
  
<span data-ttu-id="08b8b-218">同样, 通过包括**PR_CONTAINER_HIERARCHY** ([PidTagContainerHierarchy](pidtagcontainerhierarchy-canonical-property.md)) 或**PR_CONTAINER_CONTENTS** , 阻止复制或移动文件夹或通讯簿容器的层次结构或内容表 ([PidTagContainerContents](pidtagcontainercontents-canonical-property.md)) 在属性标记排除数组中。</span><span class="sxs-lookup"><span data-stu-id="08b8b-218">Similarly, prevent the copying or moving of a folder or address book container's hierarchy or contents table by including **PR_CONTAINER_HIERARCHY** ([PidTagContainerHierarchy](pidtagcontainerhierarchy-canonical-property.md)) or **PR_CONTAINER_CONTENTS** ([PidTagContainerContents](pidtagcontainercontents-canonical-property.md)) in the property tag exclude array.</span></span>
  
<span data-ttu-id="08b8b-219">若要从复制或移动操作中排除属性, 请将其属性标记包含在_lpExcludeProps_参数中。</span><span class="sxs-lookup"><span data-stu-id="08b8b-219">To exclude properties from the copy or move operation, include their property tags in the  _lpExcludeProps_ parameter.</span></span> <span data-ttu-id="08b8b-220">如果将**PROP_TAG**宏的结果传递给属性标记数组中的特定标识符, 则将排除包含该标识符的所有属性。</span><span class="sxs-lookup"><span data-stu-id="08b8b-220">If you pass the results of the **PROP_TAG** macro to build a property tag from a specific identifier in the property tag array, all properties with that identifier will be excluded.</span></span> <span data-ttu-id="08b8b-221">例如, 属性标记数组中的以下条目将导致排除标识符为0x8002 的所有属性, 而不考虑类型:</span><span class="sxs-lookup"><span data-stu-id="08b8b-221">For example, the following entry in the property tag array causes all properties with an identifier of 0x8002 to be excluded, regardless of type:</span></span> 
  
 `PROP_TAG(PT_LONG, 0x8002)`
  
<span data-ttu-id="08b8b-222">**PR_NULL** ([PidTagNull](pidtagnull-canonical-property.md)) 属性标记不能包含在_lpExcludeProps_数组中。</span><span class="sxs-lookup"><span data-stu-id="08b8b-222">The **PR_NULL** ([PidTagNull](pidtagnull-canonical-property.md)) property tag cannot be included in the  _lpExcludeProps_ array.</span></span> 
  
<span data-ttu-id="08b8b-223">用于排除接口的**CopyTo**功能的有用性可能并不像排除属性的有用性那样明显。</span><span class="sxs-lookup"><span data-stu-id="08b8b-223">The usefulness of the **CopyTo** feature for excluding interfaces is perhaps not as obvious as the usefulness of excluding properties.</span></span> <span data-ttu-id="08b8b-224">当您复制到不知道一组属性的对象时, 可以排除接口。</span><span class="sxs-lookup"><span data-stu-id="08b8b-224">You can exclude an interface when you copy to an object that has no knowledge of a group of properties.</span></span> <span data-ttu-id="08b8b-225">例如, 如果将文件夹中的属性复制到附件中, 则附件可以使用的属性就是可用于任何[IMAPIProp](imapipropiunknown.md)实现的通用属性。</span><span class="sxs-lookup"><span data-stu-id="08b8b-225">For example, if you copy properties from a folder to an attachment, the only properties that the attachment can work with are the generic properties available with any [IMAPIProp](imapipropiunknown.md) implementation.</span></span> <span data-ttu-id="08b8b-226">通过从复制操作中排除[IMAPIFolder](imapifolderimapicontainer.md) , 附件将不会收到任何更具体的文件夹属性。</span><span class="sxs-lookup"><span data-stu-id="08b8b-226">By excluding [IMAPIFolder](imapifolderimapicontainer.md) from the copy operation, the attachment will not receive any of the more specific folder properties.</span></span> 
  
<span data-ttu-id="08b8b-227">当您使用_rgiidExclude_参数来排除某个接口时, 它还会排除从该接口派生的所有接口。</span><span class="sxs-lookup"><span data-stu-id="08b8b-227">When you use the  _rgiidExclude_ parameter to exclude an interface, it also excludes all interfaces derived from that interface.</span></span> <span data-ttu-id="08b8b-228">例如, 排除[IMAPIContainer](imapicontainerimapiprop.md)会导致文件夹或通讯簿容器被排除, 具体取决于提供程序的类型。</span><span class="sxs-lookup"><span data-stu-id="08b8b-228">For example, excluding [IMAPIContainer](imapicontainerimapiprop.md) causes folders or address book containers to be excluded, depending on the type of provider.</span></span> <span data-ttu-id="08b8b-229">请勿排除**IMAPIProp**或[IUnknown](https://msdn.microsoft.com/library/ms680509%28v=VS.85%29.aspx) , 因为如此多的接口派生自它们。</span><span class="sxs-lookup"><span data-stu-id="08b8b-229">Do not exclude **IMAPIProp** or [IUnknown](https://msdn.microsoft.com/library/ms680509%28v=VS.85%29.aspx) because so many interfaces derive from them.</span></span> 
  
<span data-ttu-id="08b8b-230">忽略在_lppProblems_参数的**SPropProblemArray**结构中返回的 MAPI_E_COMPUTED 错误。</span><span class="sxs-lookup"><span data-stu-id="08b8b-230">Ignore MAPI_E_COMPUTED errors returned in the **SPropProblemArray** structure in the  _lppProblems_ parameter.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="08b8b-231">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="08b8b-231">MFCMAPI reference</span></span>

<span data-ttu-id="08b8b-232">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="08b8b-232">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="08b8b-233">**文件**</span><span class="sxs-lookup"><span data-stu-id="08b8b-233">**File**</span></span>|<span data-ttu-id="08b8b-234">**函数**</span><span class="sxs-lookup"><span data-stu-id="08b8b-234">**Function**</span></span>|<span data-ttu-id="08b8b-235">**备注**</span><span class="sxs-lookup"><span data-stu-id="08b8b-235">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="08b8b-236">文件 .cpp</span><span class="sxs-lookup"><span data-stu-id="08b8b-236">File.cpp</span></span>  <br/> |<span data-ttu-id="08b8b-237">LoadFromMSG</span><span class="sxs-lookup"><span data-stu-id="08b8b-237">LoadFromMSG</span></span>  <br/> |<span data-ttu-id="08b8b-238">MFCMAPI 使用**IMAPIProp:: CopyTo**方法将属性从 .msg 文件复制到[IMAPIMessageSite](imapimessagesiteiunknown.md)对象。</span><span class="sxs-lookup"><span data-stu-id="08b8b-238">MFCMAPI uses the **IMAPIProp::CopyTo** method to copy properties from a .msg file to an [IMAPIMessageSite](imapimessagesiteiunknown.md) object.</span></span>  <br/> |
|<span data-ttu-id="08b8b-239">FolderDlg</span><span class="sxs-lookup"><span data-stu-id="08b8b-239">FolderDlg.cpp</span></span>  <br/> |<span data-ttu-id="08b8b-240">CFolderDlg:: HandlePaste</span><span class="sxs-lookup"><span data-stu-id="08b8b-240">CFolderDlg::HandlePaste</span></span>  <br/> |<span data-ttu-id="08b8b-241">在粘贴操作过程中, MFCMAPI 使用**IMAPIProp:: CopyTo**方法将属性从源邮件复制到目标邮件。</span><span class="sxs-lookup"><span data-stu-id="08b8b-241">MFCMAPI uses the **IMAPIProp::CopyTo** method to copy properties from a source message to a target message during a paste operation.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="08b8b-242">另请参阅</span><span class="sxs-lookup"><span data-stu-id="08b8b-242">See also</span></span>



[<span data-ttu-id="08b8b-243">IMAPIFolder::CopyMessages</span><span class="sxs-lookup"><span data-stu-id="08b8b-243">IMAPIFolder::CopyMessages</span></span>](imapifolder-copymessages.md)
  
[<span data-ttu-id="08b8b-244">IMAPIProp::GetLastError</span><span class="sxs-lookup"><span data-stu-id="08b8b-244">IMAPIProp::GetLastError</span></span>](imapiprop-getlasterror.md)
  
[<span data-ttu-id="08b8b-245">IMAPIMessageSite : IUnknown</span><span class="sxs-lookup"><span data-stu-id="08b8b-245">IMAPIMessageSite : IUnknown</span></span>](imapimessagesiteiunknown.md)
  
[<span data-ttu-id="08b8b-246">IMAPIProgress : IUnknown</span><span class="sxs-lookup"><span data-stu-id="08b8b-246">IMAPIProgress : IUnknown</span></span>](imapiprogressiunknown.md)
  
[<span data-ttu-id="08b8b-247">IMAPISupport::DoProgressDialog</span><span class="sxs-lookup"><span data-stu-id="08b8b-247">IMAPISupport::DoProgressDialog</span></span>](imapisupport-doprogressdialog.md)
  
[<span data-ttu-id="08b8b-248">IMAPISupport::DoCopyTo</span><span class="sxs-lookup"><span data-stu-id="08b8b-248">IMAPISupport::DoCopyTo</span></span>](imapisupport-docopyto.md)
  
[<span data-ttu-id="08b8b-249">MAPIFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="08b8b-249">MAPIFreeBuffer</span></span>](mapifreebuffer.md)
  
[<span data-ttu-id="08b8b-250">PidTagContainerContents 规范属性</span><span class="sxs-lookup"><span data-stu-id="08b8b-250">PidTagContainerContents Canonical Property</span></span>](pidtagcontainercontents-canonical-property.md)
  
[<span data-ttu-id="08b8b-251">PidTagContainerHierarchy 规范属性</span><span class="sxs-lookup"><span data-stu-id="08b8b-251">PidTagContainerHierarchy Canonical Property</span></span>](pidtagcontainerhierarchy-canonical-property.md)
  
[<span data-ttu-id="08b8b-252">PidTagMessageAttachments 规范属性</span><span class="sxs-lookup"><span data-stu-id="08b8b-252">PidTagMessageAttachments Canonical Property</span></span>](pidtagmessageattachments-canonical-property.md)
  
[<span data-ttu-id="08b8b-253">PidTagMessageDeliveryTime 规范属性</span><span class="sxs-lookup"><span data-stu-id="08b8b-253">PidTagMessageDeliveryTime Canonical Property</span></span>](pidtagmessagedeliverytime-canonical-property.md)
  
[<span data-ttu-id="08b8b-254">PidTagMessageRecipients 规范属性</span><span class="sxs-lookup"><span data-stu-id="08b8b-254">PidTagMessageRecipients Canonical Property</span></span>](pidtagmessagerecipients-canonical-property.md)
  
[<span data-ttu-id="08b8b-255">PidTagObjectType 规范属性</span><span class="sxs-lookup"><span data-stu-id="08b8b-255">PidTagObjectType Canonical Property</span></span>](pidtagobjecttype-canonical-property.md)
  
[<span data-ttu-id="08b8b-256">SPropProblemArray</span><span class="sxs-lookup"><span data-stu-id="08b8b-256">SPropProblemArray</span></span>](spropproblemarray.md)
  
[<span data-ttu-id="08b8b-257">SPropTagArray</span><span class="sxs-lookup"><span data-stu-id="08b8b-257">SPropTagArray</span></span>](sproptagarray.md)
  
[<span data-ttu-id="08b8b-258">IMAPIProp : IUnknown</span><span class="sxs-lookup"><span data-stu-id="08b8b-258">IMAPIProp : IUnknown</span></span>](imapipropiunknown.md)


[<span data-ttu-id="08b8b-259">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="08b8b-259">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

