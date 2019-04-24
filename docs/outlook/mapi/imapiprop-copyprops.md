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
ms.openlocfilehash: 7319f1abb4a74ee17b0a4a1220215c29434d256b
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32345505"
---
# <a name="imapipropcopyprops"></a><span data-ttu-id="91a1f-103">IMAPIProp::CopyProps</span><span class="sxs-lookup"><span data-stu-id="91a1f-103">IMAPIProp::CopyProps</span></span>

  
  
<span data-ttu-id="91a1f-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="91a1f-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="91a1f-105">复制或移动选定的属性。</span><span class="sxs-lookup"><span data-stu-id="91a1f-105">Copies or moves selected properties.</span></span> 
  
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

## <a name="parameters"></a><span data-ttu-id="91a1f-106">参数</span><span class="sxs-lookup"><span data-stu-id="91a1f-106">Parameters</span></span>

 <span data-ttu-id="91a1f-107">_lpIncludeProps_</span><span class="sxs-lookup"><span data-stu-id="91a1f-107">_lpIncludeProps_</span></span>
  
> <span data-ttu-id="91a1f-108">实时指向指定要复制或移动的属性的属性标记数组的指针。</span><span class="sxs-lookup"><span data-stu-id="91a1f-108">[in] A pointer to a property tag array that specifies the properties to copy or move.</span></span> <span data-ttu-id="91a1f-109">**PR_NULL**([PidTagNull](pidtagnull-canonical-property.md)) 不能包含在数组中。</span><span class="sxs-lookup"><span data-stu-id="91a1f-109">**PR_NULL** ([PidTagNull](pidtagnull-canonical-property.md)) cannot be included in the array.</span></span> <span data-ttu-id="91a1f-110">_lpIncludeProps_参数不能为**null**。</span><span class="sxs-lookup"><span data-stu-id="91a1f-110">The  _lpIncludeProps_ parameter cannot be **null**.</span></span>
    
 <span data-ttu-id="91a1f-111">_ulUIParam_</span><span class="sxs-lookup"><span data-stu-id="91a1f-111">_ulUIParam_</span></span>
  
> <span data-ttu-id="91a1f-112">实时进度指示器的父窗口的句柄。</span><span class="sxs-lookup"><span data-stu-id="91a1f-112">[in] A handle to the parent window of the progress indicator.</span></span> 
    
 <span data-ttu-id="91a1f-113">_lpProgress_</span><span class="sxs-lookup"><span data-stu-id="91a1f-113">_lpProgress_</span></span>
  
> <span data-ttu-id="91a1f-114">实时指向进度指示器的实现的指针。</span><span class="sxs-lookup"><span data-stu-id="91a1f-114">[in] A pointer to an implementation of a progress indicator.</span></span> <span data-ttu-id="91a1f-115">如果在_lpProgress_参数中传递**null** , 则将使用 MAPI 实现显示进度指示器。</span><span class="sxs-lookup"><span data-stu-id="91a1f-115">If **null** is passed in the  _lpProgress_ parameter, the progress indicator is displayed by using the MAPI implementation.</span></span> <span data-ttu-id="91a1f-116">除非在_ulFlags_参数中设置了 MAPI_DIALOG 标志, 否则将忽略_lpProgress_参数。</span><span class="sxs-lookup"><span data-stu-id="91a1f-116">The  _lpProgress_ parameter is ignored unless the MAPI_DIALOG flag is set in the  _ulFlags_ parameter.</span></span> 
    
 <span data-ttu-id="91a1f-117">_lpInterface_</span><span class="sxs-lookup"><span data-stu-id="91a1f-117">_lpInterface_</span></span>
  
> <span data-ttu-id="91a1f-118">实时指向接口标识符 (IID) 的指针, 该接口标识符表示必须用于访问_lpDestObj_参数所指向的对象的接口。</span><span class="sxs-lookup"><span data-stu-id="91a1f-118">[in] A pointer to the interface identifier (IID) that represents the interface that must be used to access the object pointed to by the  _lpDestObj_ parameter.</span></span> <span data-ttu-id="91a1f-119">_lpInterface_参数不能为**null**。</span><span class="sxs-lookup"><span data-stu-id="91a1f-119">The  _lpInterface_ parameter must not be **null**.</span></span>
    
 <span data-ttu-id="91a1f-120">_lpDestObj_</span><span class="sxs-lookup"><span data-stu-id="91a1f-120">_lpDestObj_</span></span>
  
> <span data-ttu-id="91a1f-121">实时指向接收复制或移动的属性的对象的指针。</span><span class="sxs-lookup"><span data-stu-id="91a1f-121">[in] A pointer to the object to receive the copied or moved properties.</span></span>
    
 <span data-ttu-id="91a1f-122">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="91a1f-122">_ulFlags_</span></span>
  
> <span data-ttu-id="91a1f-123">实时用于控制复制或移动操作的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="91a1f-123">[in] A bitmask of flags that controls the copy or move operation.</span></span> <span data-ttu-id="91a1f-124">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="91a1f-124">The following flags can be set:</span></span>
    
<span data-ttu-id="91a1f-125">MAPI_DECLINE_OK</span><span class="sxs-lookup"><span data-stu-id="91a1f-125">MAPI_DECLINE_OK</span></span> 
  
> <span data-ttu-id="91a1f-126">如果**CopyProps**调用[IMAPISupport::D ocopyprops](imapisupport-docopyprops.md)方法来处理复制或移动操作, 则应立即返回错误值 MAPI_E_DECLINE_COPY。</span><span class="sxs-lookup"><span data-stu-id="91a1f-126">If **CopyProps** calls the [IMAPISupport::DoCopyProps](imapisupport-docopyprops.md) method to handle the copy or move operation, it should instead return immediately with the error value MAPI_E_DECLINE_COPY.</span></span> <span data-ttu-id="91a1f-127">MAPI_DECLINE_OK 标志由 MAPI 设置以限制递归。</span><span class="sxs-lookup"><span data-stu-id="91a1f-127">The MAPI_DECLINE_OK flag is set by MAPI to limit recursion.</span></span> <span data-ttu-id="91a1f-128">客户端不设置此标志。</span><span class="sxs-lookup"><span data-stu-id="91a1f-128">Clients do not set this flag.</span></span> 
    
<span data-ttu-id="91a1f-129">MAPI_DIALOG</span><span class="sxs-lookup"><span data-stu-id="91a1f-129">MAPI_DIALOG</span></span> 
  
> <span data-ttu-id="91a1f-130">显示进度指示器。</span><span class="sxs-lookup"><span data-stu-id="91a1f-130">Displays a progress indicator.</span></span>
    
<span data-ttu-id="91a1f-131">MAPI_MOVE</span><span class="sxs-lookup"><span data-stu-id="91a1f-131">MAPI_MOVE</span></span> 
  
> <span data-ttu-id="91a1f-132">**CopyProps**应执行移动操作, 而不是复制操作。</span><span class="sxs-lookup"><span data-stu-id="91a1f-132">**CopyProps** should perform a move operation instead of a copy operation.</span></span> <span data-ttu-id="91a1f-133">如果未设置此标志, **CopyProps**将执行复制操作。</span><span class="sxs-lookup"><span data-stu-id="91a1f-133">When this flag is not set, **CopyProps** performs a copy operation.</span></span> 
    
<span data-ttu-id="91a1f-134">MAPI_NOREPLACE</span><span class="sxs-lookup"><span data-stu-id="91a1f-134">MAPI_NOREPLACE</span></span> 
  
> <span data-ttu-id="91a1f-135">不应覆盖目标对象中的现有属性。</span><span class="sxs-lookup"><span data-stu-id="91a1f-135">Existing properties in the destination object should not be overwritten.</span></span> <span data-ttu-id="91a1f-136">如果未设置此标志, **CopyProps**将覆盖现有属性。</span><span class="sxs-lookup"><span data-stu-id="91a1f-136">When this flag is not set, **CopyProps** overwrites existing properties.</span></span> 
    
 <span data-ttu-id="91a1f-137">_lppProblems_</span><span class="sxs-lookup"><span data-stu-id="91a1f-137">_lppProblems_</span></span>
  
> <span data-ttu-id="91a1f-138">[in, out]在输入时, 指向指向[SPropProblemArray](spropproblemarray.md)结构的指针的指针;否则**为 null**, 表示无需提供错误信息。</span><span class="sxs-lookup"><span data-stu-id="91a1f-138">[in, out] On input, a pointer to a pointer to an [SPropProblemArray](spropproblemarray.md) structure; otherwise, **null**, indicating that there is no need for error information.</span></span> <span data-ttu-id="91a1f-139">如果_lppProblems_是有效的输入指针, **CopyProps**将返回有关复制一个或多个属性中的错误的详细信息。</span><span class="sxs-lookup"><span data-stu-id="91a1f-139">If  _lppProblems_ is a valid pointer on input, **CopyProps** returns detailed information about errors in copying one or more properties.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="91a1f-140">返回值</span><span class="sxs-lookup"><span data-stu-id="91a1f-140">Return value</span></span>

<span data-ttu-id="91a1f-141">S_OK</span><span class="sxs-lookup"><span data-stu-id="91a1f-141">S_OK</span></span> 
  
> <span data-ttu-id="91a1f-142">已成功复制或移动属性。</span><span class="sxs-lookup"><span data-stu-id="91a1f-142">Properties have been successfully copied or moved.</span></span>
    
<span data-ttu-id="91a1f-143">MAPI_E_COLLISION</span><span class="sxs-lookup"><span data-stu-id="91a1f-143">MAPI_E_COLLISION</span></span> 
  
> <span data-ttu-id="91a1f-144">无法复制子对象, 因为**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 属性所定义的具有相同显示名称的子对象已经存在于目标对象中。</span><span class="sxs-lookup"><span data-stu-id="91a1f-144">A subobject cannot be copied because a subobject with the same display name, defined by the **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) property, already exists in the destination object.</span></span> 
    
<span data-ttu-id="91a1f-145">MAPI_E_DECLINE_COPY</span><span class="sxs-lookup"><span data-stu-id="91a1f-145">MAPI_E_DECLINE_COPY</span></span> 
  
> <span data-ttu-id="91a1f-146">服务提供程序不实施复制操作。</span><span class="sxs-lookup"><span data-stu-id="91a1f-146">The service provider does not implement the copy operation.</span></span>
    
<span data-ttu-id="91a1f-147">MAPI_E_FOLDER_CYCLE</span><span class="sxs-lookup"><span data-stu-id="91a1f-147">MAPI_E_FOLDER_CYCLE</span></span> 
  
> <span data-ttu-id="91a1f-148">执行复制或移动操作直接或间接包含目标对象的源对象。</span><span class="sxs-lookup"><span data-stu-id="91a1f-148">The source object performing the copy or move operation directly or indirectly contains the destination object.</span></span> <span data-ttu-id="91a1f-149">在发现此条件之前, 可能已经执行了大量的工作, 因此源和目标对象可能被部分修改。</span><span class="sxs-lookup"><span data-stu-id="91a1f-149">Significant work might have been performed before this condition was discovered, so the source and destination objects might be partially modified.</span></span> 
    
<span data-ttu-id="91a1f-150">MAPI_E_INTERFACE_NOT_SUPPORTED</span><span class="sxs-lookup"><span data-stu-id="91a1f-150">MAPI_E_INTERFACE_NOT_SUPPORTED</span></span> 
  
> <span data-ttu-id="91a1f-151">目标对象不支持由_lpInterface_参数标识的接口。</span><span class="sxs-lookup"><span data-stu-id="91a1f-151">The interface identified by the  _lpInterface_ parameter is not supported by the destination object.</span></span> 
    
<span data-ttu-id="91a1f-152">MAPI_E_NO_ACCESS</span><span class="sxs-lookup"><span data-stu-id="91a1f-152">MAPI_E_NO_ACCESS</span></span> 
  
> <span data-ttu-id="91a1f-153">试图访问呼叫者没有足够权限的对象。</span><span class="sxs-lookup"><span data-stu-id="91a1f-153">An attempt was made to access an object for which the caller has insufficient permissions.</span></span> <span data-ttu-id="91a1f-154">如果目标对象与源对象相同, 则返回此错误。</span><span class="sxs-lookup"><span data-stu-id="91a1f-154">This error is returned if the destination object is the same as the source object.</span></span>
    
<span data-ttu-id="91a1f-155">以下值可在**SPropProblemArray**结构中返回, 但不能在**CopyProps**的返回值中返回。</span><span class="sxs-lookup"><span data-stu-id="91a1f-155">The following values can be returned in the **SPropProblemArray** structure, but not as return values for **CopyProps**.</span></span> <span data-ttu-id="91a1f-156">这些错误适用于单个属性。</span><span class="sxs-lookup"><span data-stu-id="91a1f-156">These errors apply to a single property.</span></span>
  
<span data-ttu-id="91a1f-157">MAPI_E_BAD_CHARWIDTH</span><span class="sxs-lookup"><span data-stu-id="91a1f-157">MAPI_E_BAD_CHARWIDTH</span></span> 
  
> <span data-ttu-id="91a1f-158">设置了 MAPI_UNICODE 标志, 并且**CopyProps**不支持 unicode, 或者未设置 MAPI_UNICODE, 且**CopyProps**仅支持 UNICODE。</span><span class="sxs-lookup"><span data-stu-id="91a1f-158">Either the MAPI_UNICODE flag was set and **CopyProps** does not support Unicode, or MAPI_UNICODE was not set and **CopyProps** supports only Unicode.</span></span> 
    
<span data-ttu-id="91a1f-159">MAPI_E_COMPUTED</span><span class="sxs-lookup"><span data-stu-id="91a1f-159">MAPI_E_COMPUTED</span></span> 
  
> <span data-ttu-id="91a1f-160">调用程序无法修改该属性, 因为它是由目标对象的所有者计算的只读属性。</span><span class="sxs-lookup"><span data-stu-id="91a1f-160">The property cannot be modified by the caller because it is a read-only property, computed by the owner of the destination object.</span></span> <span data-ttu-id="91a1f-161">此错误不严重;呼叫者应允许复制操作继续进行。</span><span class="sxs-lookup"><span data-stu-id="91a1f-161">This error is not severe; the caller should allow the copy operation to continue.</span></span>
    
<span data-ttu-id="91a1f-162">MAPI_E_INVALID_TYPE</span><span class="sxs-lookup"><span data-stu-id="91a1f-162">MAPI_E_INVALID_TYPE</span></span> 
  
> <span data-ttu-id="91a1f-163">属性类型无效。</span><span class="sxs-lookup"><span data-stu-id="91a1f-163">The property type is invalid.</span></span>
    
<span data-ttu-id="91a1f-164">MAPI_E_UNEXPECTED_TYPE</span><span class="sxs-lookup"><span data-stu-id="91a1f-164">MAPI_E_UNEXPECTED_TYPE</span></span> 
  
> <span data-ttu-id="91a1f-165">属性类型不是调用方预期的类型。</span><span class="sxs-lookup"><span data-stu-id="91a1f-165">The property type is not the type expected by the caller.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="91a1f-166">注解</span><span class="sxs-lookup"><span data-stu-id="91a1f-166">Remarks</span></span>

<span data-ttu-id="91a1f-167">**IMAPIProp:: CopyProps**方法将当前对象的选定属性复制或移动到目标对象。</span><span class="sxs-lookup"><span data-stu-id="91a1f-167">The **IMAPIProp::CopyProps** method copies or moves selected properties from the current object to a destination object.</span></span> <span data-ttu-id="91a1f-168">**CopyProps**主要用于答复和转发邮件, 其中只有一些来自原始邮件的属性携带在答复或转发副本中。</span><span class="sxs-lookup"><span data-stu-id="91a1f-168">**CopyProps** is used mainly for replying to and forwarding messages, where only some of the properties from the original message travel with the reply or forwarded copy.</span></span> 
  
<span data-ttu-id="91a1f-169">无论使用由[SPropTagArray](sproptagarray.md)结构指示的属性, 源对象中的任何子对象都会自动包含在操作中并复制或移动到整个中。</span><span class="sxs-lookup"><span data-stu-id="91a1f-169">Any subobjects in the source object are automatically included in the operation and copied or moved in their entirety, regardless of the use of properties indicated by the [SPropTagArray](sproptagarray.md) structure.</span></span> <span data-ttu-id="91a1f-170">默认情况下, **CopyProps**会覆盖目标对象中与源对象的属性匹配的任何属性。</span><span class="sxs-lookup"><span data-stu-id="91a1f-170">By default, **CopyProps** overwrites any properties in the destination object that match properties from the source object.</span></span> <span data-ttu-id="91a1f-171">如果目标对象中已存在任何复制或移动的属性, 则新属性将覆盖现有属性, 除非在_ulFlags_参数中设置 MAPI_NOREPLACE 标志。</span><span class="sxs-lookup"><span data-stu-id="91a1f-171">If any of the copied or moved properties already exist in the destination object, the existing properties are overwritten by the new properties, unless the MAPI_NOREPLACE flag is set in the  _ulFlags_ parameter.</span></span> <span data-ttu-id="91a1f-172">不会覆盖的目标对象中的现有信息将保持不变。</span><span class="sxs-lookup"><span data-stu-id="91a1f-172">Existing information in the destination object that is not overwritten is left untouched.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="91a1f-173">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="91a1f-173">Notes to implementers</span></span>

<span data-ttu-id="91a1f-174">您可以提供**CopyProps**的完全实现, 也可以依赖 MAPI 在其支持对象中提供的实现。</span><span class="sxs-lookup"><span data-stu-id="91a1f-174">You can provide a full implementation of **CopyProps** or rely on the implementation that MAPI provides in its support object.</span></span> <span data-ttu-id="91a1f-175">如果要使用 MAPI 实现, 请调用**IMAPISupport::D ocopyprops**方法。</span><span class="sxs-lookup"><span data-stu-id="91a1f-175">If you want to use the MAPI implementation, call the **IMAPISupport::DoCopyProps** method.</span></span> <span data-ttu-id="91a1f-176">但是, 如果您将处理委派给**DoCopyProps** , 并且您已传递 MAPI_DECLINE_OK 标志, 请避免支持呼叫, 而改为返回 MAPI_E_DECLINE_COPY。</span><span class="sxs-lookup"><span data-stu-id="91a1f-176">However, if you do delegate processing to **DoCopyProps** and you are passed the MAPI_DECLINE_OK flag, avoid the support call and return MAPI_E_DECLINE_COPY instead.</span></span> <span data-ttu-id="91a1f-177">你将通过 MAPI 使用此标志调用, 以避免在复制文件夹时可能发生的递归。</span><span class="sxs-lookup"><span data-stu-id="91a1f-177">You will be called with this flag by MAPI to avoid the possible recursion that can occur when you copy folders.</span></span> 
  
<span data-ttu-id="91a1f-178">由于复制操作可能很长, 因此应显示进度指示器。</span><span class="sxs-lookup"><span data-stu-id="91a1f-178">Because the copy operation can be lengthy, you should display a progress indicator.</span></span> <span data-ttu-id="91a1f-179">使用在_lpProgress_参数中传递的[IMAPIProgress](imapiprogressiunknown.md)实现 (如果有的话)。</span><span class="sxs-lookup"><span data-stu-id="91a1f-179">Use the [IMAPIProgress](imapiprogressiunknown.md) implementation that is passed in the  _lpProgress_ parameter, if there is one.</span></span> <span data-ttu-id="91a1f-180">如果_lpProgress_为**null**, 则调用[IMAPISupport::D oprogressdialog](imapisupport-doprogressdialog.md)方法以使用 MAPI 实现。</span><span class="sxs-lookup"><span data-stu-id="91a1f-180">If  _lpProgress_ is **null**, call the [IMAPISupport::DoProgressDialog](imapisupport-doprogressdialog.md) method to use the MAPI implementation.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="91a1f-181">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="91a1f-181">Notes to callers</span></span>

<span data-ttu-id="91a1f-182">请勿设置 MAPI_DECLINE_OK 标志;它由 MAPI 在其对邮件存储提供程序**CopyProps**实现的调用中使用。</span><span class="sxs-lookup"><span data-stu-id="91a1f-182">Do not set the MAPI_DECLINE_OK flag; it is used by MAPI in its calls to message store provider **CopyProps** implementations.</span></span> 
  
<span data-ttu-id="91a1f-183">由于复制和移动操作可能需要一些时间, 因此最好通过设置 MAPI_DIALOG 标志来请求显示进度指示器。</span><span class="sxs-lookup"><span data-stu-id="91a1f-183">Because copy and move operations can take time, it is wise to request the display of a progress indicator by setting the MAPI_DIALOG flag.</span></span> <span data-ttu-id="91a1f-184">您可以将_lpProgress_参数设置为**IMAPIProgress**的实现, 如果有, 则设置为**null**。</span><span class="sxs-lookup"><span data-stu-id="91a1f-184">You can set the  _lpProgress_ parameter to your implementation of **IMAPIProgress**, if you have one, or to **null**.</span></span> <span data-ttu-id="91a1f-185">如果_lpProgress_为**null**, 则**CopyProps**将使用 MAPI 提供的默认进度指示器。</span><span class="sxs-lookup"><span data-stu-id="91a1f-185">If  _lpProgress_ is **null**, **CopyProps** will use the default progress indicator provided by MAPI.</span></span> 
  
<span data-ttu-id="91a1f-186">您可以通过不设置 MAPI_DIALOG 标志来禁止显示进度指示器。</span><span class="sxs-lookup"><span data-stu-id="91a1f-186">You can suppress the display of a progress indicator by not setting the MAPI_DIALOG flag.</span></span> <span data-ttu-id="91a1f-187">**CopyProps**将忽略_ulUIParam_和_lpProgress_参数, 并避免显示指示器。</span><span class="sxs-lookup"><span data-stu-id="91a1f-187">**CopyProps** will ignore the  _ulUIParam_ and  _lpProgress_ parameters and avoid displaying the indicator.</span></span> 
  
 <span data-ttu-id="91a1f-188">**CopyProps**可以报告一个或多个属性出现的全局和各个错误。</span><span class="sxs-lookup"><span data-stu-id="91a1f-188">**CopyProps** can report global and individual errors, or errors that occur with one or more of the properties.</span></span> <span data-ttu-id="91a1f-189">这些单独的错误放在**SPropProblemArray**结构中。</span><span class="sxs-lookup"><span data-stu-id="91a1f-189">These individual errors are put in an **SPropProblemArray** structure.</span></span> <span data-ttu-id="91a1f-190">您可以通过为属性问题数组结构参数传递**null**(而不是有效的指针) 来抑制属性级别的错误报告。</span><span class="sxs-lookup"><span data-stu-id="91a1f-190">You can suppress error reporting at the property level by passing **null**, instead of a valid pointer, for the property problem array structure parameter.</span></span> 
  
<span data-ttu-id="91a1f-191">如果要接收有关错误的信息, 请在_lppProblems_参数中传递有效的**SPropProblemArray**结构指针。</span><span class="sxs-lookup"><span data-stu-id="91a1f-191">If you want to receive information about errors, pass a valid **SPropProblemArray** structure pointer in the  _lppProblems_ parameter.</span></span> <span data-ttu-id="91a1f-192">当**CopyProps**返回 S_OK 时, 检查结构中的各个属性可能存在的错误。</span><span class="sxs-lookup"><span data-stu-id="91a1f-192">When **CopyProps** returns S_OK, check for possible errors with individual properties in the structure.</span></span> <span data-ttu-id="91a1f-193">当**CopyProps**返回错误时, **SPropProblemArray**结构中不返回任何信息。</span><span class="sxs-lookup"><span data-stu-id="91a1f-193">When **CopyProps** returns an error, no information is returned in the **SPropProblemArray** structure.</span></span> <span data-ttu-id="91a1f-194">相反, 请调用[IMAPIProp:: GetLastError](imapiprop-getlasterror.md)方法以检索详细的错误消息。</span><span class="sxs-lookup"><span data-stu-id="91a1f-194">Instead, call the [IMAPIProp::GetLastError](imapiprop-getlasterror.md) method to retrieve detailed error information.</span></span> 
  
<span data-ttu-id="91a1f-195">如果**CopyProps**返回 S_OK, 请通过调用[MAPIFreeBuffer](mapifreebuffer.md)函数释放返回的**SPropProblemArray**结构。</span><span class="sxs-lookup"><span data-stu-id="91a1f-195">If **CopyProps** returns S_OK, free the returned **SPropProblemArray** structure by calling the [MAPIFreeBuffer](mapifreebuffer.md) function.</span></span> 
  
<span data-ttu-id="91a1f-196">如果要复制源对象类型所特有的属性, 则必须确保目标对象的类型相同。</span><span class="sxs-lookup"><span data-stu-id="91a1f-196">If you are copying properties that are unique to the source object type, you must make sure that the destination object is of the same type.</span></span> <span data-ttu-id="91a1f-197">**CopyProps**不会阻止您将通常属于一种类型的对象的属性与另一种类型的对象相关联。</span><span class="sxs-lookup"><span data-stu-id="91a1f-197">**CopyProps** does not prevent you from associating properties that typically belong to one type of object with another type of object.</span></span> <span data-ttu-id="91a1f-198">您将由您来复制对目标对象有意义的属性。</span><span class="sxs-lookup"><span data-stu-id="91a1f-198">It is up to you to copy properties that make sense for the destination object.</span></span> <span data-ttu-id="91a1f-199">例如, 不应将邮件属性复制到通讯簿容器。</span><span class="sxs-lookup"><span data-stu-id="91a1f-199">For example, you should not copy message properties to an address book container.</span></span> 
  
<span data-ttu-id="91a1f-200">若要确保在同一类型的对象之间进行复制, 请通过比较对象指针或调用[IUnknown:: QueryInterface](https://msdn.microsoft.com/library/54d5ff80-18db-43f2-b636-f93ac053146d%28Office.15%29.aspx)方法来检查源和目标对象的类型是否相同。</span><span class="sxs-lookup"><span data-stu-id="91a1f-200">To ensure that you are copying between objects of the same type, check that the source and destination object are the same type, either by comparing object pointers or calling the [IUnknown::QueryInterface](https://msdn.microsoft.com/library/54d5ff80-18db-43f2-b636-f93ac053146d%28Office.15%29.aspx) method.</span></span> <span data-ttu-id="91a1f-201">将_lpInterface_指向的接口标识符设置为源对象的标准接口。</span><span class="sxs-lookup"><span data-stu-id="91a1f-201">Set the interface identifier pointed to by  _lpInterface_ to the standard interface for the source object.</span></span> <span data-ttu-id="91a1f-202">此外, 请确保这两个对象的对象类型或**PR_OBJECT_TYPE** ([PidTagObjectType](pidtagobjecttype-canonical-property.md)) 属性相同。</span><span class="sxs-lookup"><span data-stu-id="91a1f-202">Also, ensure that the object type or **PR_OBJECT_TYPE** ([PidTagObjectType](pidtagobjecttype-canonical-property.md)) property is the same for the two objects.</span></span> <span data-ttu-id="91a1f-203">例如, 如果要从邮件中进行复制, 请将这两个对象的_lpInterface_设置为 IID_IMessage, 并将这两个对象的**PR_OBJECT_TYPE**设置为 MAPI_MESSAGE。</span><span class="sxs-lookup"><span data-stu-id="91a1f-203">For example, if you are copying from a message, set  _lpInterface_ to IID_IMessage and the **PR_OBJECT_TYPE** for both objects to MAPI_MESSAGE.</span></span> 
  
<span data-ttu-id="91a1f-204">如果在_lpDestObj_参数中传递无效的指针, 则结果是不可预知的。</span><span class="sxs-lookup"><span data-stu-id="91a1f-204">If an invalid pointer is passed in the  _lpDestObj_ parameter, the results are unpredictable.</span></span> 
  
<span data-ttu-id="91a1f-205">若要复制邮件的收件人列表, 请调用邮件的**CopyProps**方法, 并在属性标记数组中包含**PR_MESSAGE_RECIPIENTS** ([PidTagMessageRecipients](pidtagmessagerecipients-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="91a1f-205">To copy a message's recipient list, call the message's **CopyProps** method and include the **PR_MESSAGE_RECIPIENTS** ([PidTagMessageRecipients](pidtagmessagerecipients-canonical-property.md)) property in the property tag array.</span></span> <span data-ttu-id="91a1f-206">若要复制邮件的附件, 请包含**PR_MESSAGE_ATTACHMENTS** ([PidTagMessageAttachments](pidtagmessageattachments-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="91a1f-206">To copy the message's attachments, include the **PR_MESSAGE_ATTACHMENTS** ([PidTagMessageAttachments](pidtagmessageattachments-canonical-property.md)) property.</span></span> 
  
<span data-ttu-id="91a1f-207">若要复制文件夹或通讯簿容器的层次结构或内容表, 请在**PR_CONTAINER_HIERARCHY** ([PidTagContainerHierarchy](pidtagcontainerhierarchy-canonical-property.md)) 或**PR_CONTAINER_CONTENTS** ([PidTagContainerContents](pidtagcontainercontents-canonical-property.md)) 属性中添加属性标记数组。</span><span class="sxs-lookup"><span data-stu-id="91a1f-207">To copy a folder or address book container's hierarchy or contents table, include the **PR_CONTAINER_HIERARCHY** ([PidTagContainerHierarchy](pidtagcontainerhierarchy-canonical-property.md)) or **PR_CONTAINER_CONTENTS** ([PidTagContainerContents](pidtagcontainercontents-canonical-property.md)) properties in the property tag array.</span></span> <span data-ttu-id="91a1f-208">若要包含文件夹的关联内容表, 请在数组中包含**PR_FOLDER_ASSOCIATED_CONTENTS** ([PidTagFolderAssociatedContents](pidtagfolderassociatedcontents-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="91a1f-208">To include a folder's associated contents table, include the **PR_FOLDER_ASSOCIATED_CONTENTS** ([PidTagFolderAssociatedContents](pidtagfolderassociatedcontents-canonical-property.md)) property in the array.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="91a1f-209">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="91a1f-209">MFCMAPI reference</span></span>

<span data-ttu-id="91a1f-210">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="91a1f-210">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="91a1f-211">**文件**</span><span class="sxs-lookup"><span data-stu-id="91a1f-211">**File**</span></span>|<span data-ttu-id="91a1f-212">**函数**</span><span class="sxs-lookup"><span data-stu-id="91a1f-212">**Function**</span></span>|<span data-ttu-id="91a1f-213">**备注**</span><span class="sxs-lookup"><span data-stu-id="91a1f-213">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="91a1f-214">MAPIFunctions</span><span class="sxs-lookup"><span data-stu-id="91a1f-214">MAPIFunctions.cpp</span></span>  <br/> |<span data-ttu-id="91a1f-215">CopyNamedProps</span><span class="sxs-lookup"><span data-stu-id="91a1f-215">CopyNamedProps</span></span>  <br/> |<span data-ttu-id="91a1f-216">MFCMAPI 使用**IMAPIProp:: CopyProps**方法将命名属性从一个邮件复制到另一个邮件。</span><span class="sxs-lookup"><span data-stu-id="91a1f-216">MFCMAPI uses the **IMAPIProp::CopyProps** method to copy named properties from one message to another.</span></span>  <br/> |
|<span data-ttu-id="91a1f-217">SingleMAPIPropListCtrl</span><span class="sxs-lookup"><span data-stu-id="91a1f-217">SingleMAPIPropListCtrl.cpp</span></span>  <br/> |<span data-ttu-id="91a1f-218">CSingleMAPIPropListCtrl:: OnPasteProperty</span><span class="sxs-lookup"><span data-stu-id="91a1f-218">CSingleMAPIPropListCtrl::OnPasteProperty</span></span>  <br/> |<span data-ttu-id="91a1f-219">MFCMAPI 使用**IMAPIProp:: CopyProps**方法粘贴已从另一个对象复制的属性。</span><span class="sxs-lookup"><span data-stu-id="91a1f-219">MFCMAPI uses the **IMAPIProp::CopyProps** method to paste a property that has been copied from another object.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="91a1f-220">另请参阅</span><span class="sxs-lookup"><span data-stu-id="91a1f-220">See also</span></span>



[<span data-ttu-id="91a1f-221">IMAPIFolder::CopyMessages</span><span class="sxs-lookup"><span data-stu-id="91a1f-221">IMAPIFolder::CopyMessages</span></span>](imapifolder-copymessages.md)
  
[<span data-ttu-id="91a1f-222">IMAPIProgress : IUnknown</span><span class="sxs-lookup"><span data-stu-id="91a1f-222">IMAPIProgress : IUnknown</span></span>](imapiprogressiunknown.md)
  
[<span data-ttu-id="91a1f-223">IMAPIProp::CopyTo</span><span class="sxs-lookup"><span data-stu-id="91a1f-223">IMAPIProp::CopyTo</span></span>](imapiprop-copyto.md)
  
[<span data-ttu-id="91a1f-224">IMAPIProp::GetLastError</span><span class="sxs-lookup"><span data-stu-id="91a1f-224">IMAPIProp::GetLastError</span></span>](imapiprop-getlasterror.md)
  
[<span data-ttu-id="91a1f-225">IMAPISupport::DoCopyProps</span><span class="sxs-lookup"><span data-stu-id="91a1f-225">IMAPISupport::DoCopyProps</span></span>](imapisupport-docopyprops.md)
  
[<span data-ttu-id="91a1f-226">IMAPISupport::DoProgressDialog</span><span class="sxs-lookup"><span data-stu-id="91a1f-226">IMAPISupport::DoProgressDialog</span></span>](imapisupport-doprogressdialog.md)
  
[<span data-ttu-id="91a1f-227">MAPIFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="91a1f-227">MAPIFreeBuffer</span></span>](mapifreebuffer.md)
  
[<span data-ttu-id="91a1f-228">PidTagContainerContents 规范属性</span><span class="sxs-lookup"><span data-stu-id="91a1f-228">PidTagContainerContents Canonical Property</span></span>](pidtagcontainercontents-canonical-property.md)
  
[<span data-ttu-id="91a1f-229">PidTagContainerHierarchy 规范属性</span><span class="sxs-lookup"><span data-stu-id="91a1f-229">PidTagContainerHierarchy Canonical Property</span></span>](pidtagcontainerhierarchy-canonical-property.md)
  
[<span data-ttu-id="91a1f-230">PidTagDisplayName 规范属性</span><span class="sxs-lookup"><span data-stu-id="91a1f-230">PidTagDisplayName Canonical Property</span></span>](pidtagdisplayname-canonical-property.md)
  
[<span data-ttu-id="91a1f-231">PidTagFolderAssociatedContents 规范属性</span><span class="sxs-lookup"><span data-stu-id="91a1f-231">PidTagFolderAssociatedContents Canonical Property</span></span>](pidtagfolderassociatedcontents-canonical-property.md)
  
[<span data-ttu-id="91a1f-232">PidTagMessageAttachments 规范属性</span><span class="sxs-lookup"><span data-stu-id="91a1f-232">PidTagMessageAttachments Canonical Property</span></span>](pidtagmessageattachments-canonical-property.md)
  
[<span data-ttu-id="91a1f-233">PidTagMessageRecipients 规范属性</span><span class="sxs-lookup"><span data-stu-id="91a1f-233">PidTagMessageRecipients Canonical Property</span></span>](pidtagmessagerecipients-canonical-property.md)
  
[<span data-ttu-id="91a1f-234">PidTagObjectType 规范属性</span><span class="sxs-lookup"><span data-stu-id="91a1f-234">PidTagObjectType Canonical Property</span></span>](pidtagobjecttype-canonical-property.md)
  
[<span data-ttu-id="91a1f-235">SPropProblemArray</span><span class="sxs-lookup"><span data-stu-id="91a1f-235">SPropProblemArray</span></span>](spropproblemarray.md)
  
[<span data-ttu-id="91a1f-236">SPropTagArray</span><span class="sxs-lookup"><span data-stu-id="91a1f-236">SPropTagArray</span></span>](sproptagarray.md)
  
[<span data-ttu-id="91a1f-237">IMAPIProp : IUnknown</span><span class="sxs-lookup"><span data-stu-id="91a1f-237">IMAPIProp : IUnknown</span></span>](imapipropiunknown.md)


[<span data-ttu-id="91a1f-238">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="91a1f-238">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

