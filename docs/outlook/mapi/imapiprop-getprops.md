---
title: IMAPIPropGetProps
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIProp.GetProps
api_type:
- COM
ms.assetid: 1c7a9cd2-d765-4218-9aee-52df1a2aae6c
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 9b03775d495f7d1f51142eb0ed06fc9ecdf6d1a3
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32316609"
---
# <a name="imapipropgetprops"></a><span data-ttu-id="cef14-103">IMAPIProp::GetProps</span><span class="sxs-lookup"><span data-stu-id="cef14-103">IMAPIProp::GetProps</span></span>

  
  
<span data-ttu-id="cef14-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="cef14-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="cef14-105">检索对象的一个或多个属性的属性值。</span><span class="sxs-lookup"><span data-stu-id="cef14-105">Retrieves the property value of one or more properties of an object.</span></span>
  
```cpp
HRESULT GetProps(
  LPSPropTagArray lpPropTagArray,
  ULONG ulFlags,
  ULONG FAR * lpcValues,
  LPSPropValue FAR * lppPropArray
);
```

## <a name="parameters"></a><span data-ttu-id="cef14-106">参数</span><span class="sxs-lookup"><span data-stu-id="cef14-106">Parameters</span></span>

 <span data-ttu-id="cef14-107">_lpPropTagArray_</span><span class="sxs-lookup"><span data-stu-id="cef14-107">_lpPropTagArray_</span></span>
  
> <span data-ttu-id="cef14-108">实时指向标识要检索其值的属性的属性标记数组的指针。</span><span class="sxs-lookup"><span data-stu-id="cef14-108">[in] A pointer to an array of property tags that identify the properties whose values are to be retrieved.</span></span> <span data-ttu-id="cef14-109">_lpPropTagArray_参数必须是 NULL, 指示应返回对象的所有属性的值, 或指向包含一个或多个属性标记的[SPropTagArray](sproptagarray.md)结构。</span><span class="sxs-lookup"><span data-stu-id="cef14-109">The  _lpPropTagArray_ parameter must be either NULL, indicating that values for all properties of the object should be returned, or point to an [SPropTagArray](sproptagarray.md) structure that contains one or more property tags.</span></span> 
    
 <span data-ttu-id="cef14-110">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="cef14-110">_ulFlags_</span></span>
  
> <span data-ttu-id="cef14-111">实时标志的位掩码, 指示属性类型为 PT_UNSPECIFIED 的格式。</span><span class="sxs-lookup"><span data-stu-id="cef14-111">[in] A bitmask of flags that indicates the format for properties that have the type PT_UNSPECIFIED.</span></span> <span data-ttu-id="cef14-112">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="cef14-112">The following flag can be set:</span></span>
    
<span data-ttu-id="cef14-113">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="cef14-113">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="cef14-114">这些属性的字符串值应以 Unicode 格式返回。</span><span class="sxs-lookup"><span data-stu-id="cef14-114">The string values for these properties should be returned in the Unicode format.</span></span> <span data-ttu-id="cef14-115">如果未设置 MAPI_UNICODE 标志, 则字符串值应以 ANSI 格式返回。</span><span class="sxs-lookup"><span data-stu-id="cef14-115">If the MAPI_UNICODE flag is not set, the string values should be returned in the ANSI format.</span></span>
    
 <span data-ttu-id="cef14-116">_lpcValues_</span><span class="sxs-lookup"><span data-stu-id="cef14-116">_lpcValues_</span></span>
  
> <span data-ttu-id="cef14-117">排除一个指针, 指向_lppPropArray_参数指向的属性值的计数。</span><span class="sxs-lookup"><span data-stu-id="cef14-117">[out] A pointer to a count of property values pointed to by the  _lppPropArray_ parameter.</span></span> <span data-ttu-id="cef14-118">如果_lppPropArray_为 NULL, 则_lpcValues_参数的内容为零。</span><span class="sxs-lookup"><span data-stu-id="cef14-118">If  _lppPropArray_ is NULL, the content of the  _lpcValues_ parameter is zero.</span></span> 
    
 <span data-ttu-id="cef14-119">_lppPropArray_</span><span class="sxs-lookup"><span data-stu-id="cef14-119">_lppPropArray_</span></span>
  
> <span data-ttu-id="cef14-120">排除指向已检索的属性值的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="cef14-120">[out] A pointer to a pointer to the retrieved property values.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="cef14-121">返回值</span><span class="sxs-lookup"><span data-stu-id="cef14-121">Return value</span></span>

<span data-ttu-id="cef14-122">S_OK</span><span class="sxs-lookup"><span data-stu-id="cef14-122">S_OK</span></span> 
  
> <span data-ttu-id="cef14-123">已成功检索属性值。</span><span class="sxs-lookup"><span data-stu-id="cef14-123">The property values were successfully retrieved.</span></span>
    
<span data-ttu-id="cef14-124">MAPI_W_ERRORS_RETURNED</span><span class="sxs-lookup"><span data-stu-id="cef14-124">MAPI_W_ERRORS_RETURNED</span></span> 
  
> <span data-ttu-id="cef14-125">呼叫全部成功, 但无法访问一个或多个属性。</span><span class="sxs-lookup"><span data-stu-id="cef14-125">The call succeeded overall, but one or more properties could not be accessed.</span></span> <span data-ttu-id="cef14-126">每个不可用属性的属性值的**aulPropTag**成员的属性类型为 PT_ERROR, 标识符为零。</span><span class="sxs-lookup"><span data-stu-id="cef14-126">The **aulPropTag** member of the property value for each unavailable property has a property type of PT_ERROR and an identifier of zero.</span></span> <span data-ttu-id="cef14-127">返回此警告时, 应以成功的方式处理该调用。</span><span class="sxs-lookup"><span data-stu-id="cef14-127">When this warning is returned, the call should be handled as successful.</span></span> <span data-ttu-id="cef14-128">若要测试此警告, 请使用**HR_FAILED**宏。</span><span class="sxs-lookup"><span data-stu-id="cef14-128">To test for this warning, use the **HR_FAILED** macro.</span></span> <span data-ttu-id="cef14-129">有关详细信息, 请参阅[使用宏进行错误处理](using-macros-for-error-handling.md)。</span><span class="sxs-lookup"><span data-stu-id="cef14-129">For more information, see [Using Macros for Error Handling](using-macros-for-error-handling.md).</span></span>
    
<span data-ttu-id="cef14-130">MAPI_E_INVALID_PARAMETER</span><span class="sxs-lookup"><span data-stu-id="cef14-130">MAPI_E_INVALID_PARAMETER</span></span> 
  
> <span data-ttu-id="cef14-131">在_lpPropTagArray_指向的**SPropTagArray**结构的**cValues**成员中传递了零。</span><span class="sxs-lookup"><span data-stu-id="cef14-131">Zero was passed in the **cValues** member of the **SPropTagArray** structure pointed to by  _lpPropTagArray_.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="cef14-132">注解</span><span class="sxs-lookup"><span data-stu-id="cef14-132">Remarks</span></span>

<span data-ttu-id="cef14-133">**IMAPIProp:: GetProps**方法获取对象的一个或多个属性的属性值。</span><span class="sxs-lookup"><span data-stu-id="cef14-133">The **IMAPIProp::GetProps** method obtains the property values of one or more properties of an object.</span></span> 
  
<span data-ttu-id="cef14-134">属性值按其请求的顺序返回 (即, 由_lpPropTagArray_指向的属性标记数组中属性的顺序与 lppPropArray 指向的属性值结构数组中的顺序匹配)。 __).</span><span class="sxs-lookup"><span data-stu-id="cef14-134">The property values are returned in the same order as they were requested (that is, the order of properties in the property tag array pointed to by  _lpPropTagArray_ matches the order in the array of property value structures pointed to by  _lppPropArray_).</span></span> 
  
<span data-ttu-id="cef14-135">在属性标记数组的**aulPropTag**成员中指定的属性类型指示应在每个属性值结构的**value**成员中返回的值的类型。</span><span class="sxs-lookup"><span data-stu-id="cef14-135">The property types specified in the **aulPropTag** members of the property tag array indicate the type of value that should be returned in the **Value** member of each property value structure.</span></span> <span data-ttu-id="cef14-136">但是, 如果调用方不知道属性的类型, 则可以改为将**aulPropTag**成员中的类型设置为 PT_UNSPECIFIED。</span><span class="sxs-lookup"><span data-stu-id="cef14-136">However, if the caller does not know the type of a property, the type in the **aulPropTag** member can be set instead to PT_UNSPECIFIED.</span></span> <span data-ttu-id="cef14-137">在检索值时, **GetProps**会在属性的属性值结构的**aulPropTag**成员中设置正确的类型。</span><span class="sxs-lookup"><span data-stu-id="cef14-137">In retrieving the value, **GetProps** sets the correct type in the **aulPropTag** member of the property value structure for the property.</span></span> 
  
<span data-ttu-id="cef14-138">如果在_lpPropTagArray_中的**SPropTagArray**中指定了属性类型, 则在_lppPropArray_中返回的**SPropValue**中的属性值的类型与请求的类型完全匹配, 除非返回错误值应当.</span><span class="sxs-lookup"><span data-stu-id="cef14-138">If property types are specified in the **SPropTagArray** in  _lpPropTagArray_, the property values in the **SPropValue** returned in  _lppPropArray_ have types that exactly match the requested types, unless an error value is returned instead.</span></span> 
  
<span data-ttu-id="cef14-139">字符串属性可以具有以下两种属性类型之一: PT_UNICODE 表示 UNICODE 格式和 PT_STRING8 来表示 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="cef14-139">String properties can have one of two property types: PT_UNICODE to represent the Unicode format and PT_STRING8 to represent the ANSI format.</span></span> <span data-ttu-id="cef14-140">如果在_ulFlags_参数中设置了 MAPI_UNICODE 标志, 则只要**GetProps**无法确定字符串属性的相应格式, 它将以 UNICODE 格式返回其值。</span><span class="sxs-lookup"><span data-stu-id="cef14-140">If the MAPI_UNICODE flag is set in the  _ulFlags_ parameter, whenever **GetProps** cannot determine the appropriate format for a string property, it returns its value in the Unicode format.</span></span> <span data-ttu-id="cef14-141">在以下情况下, **GetProps**无法确定确切的字符串属性类型:</span><span class="sxs-lookup"><span data-stu-id="cef14-141">**GetProps** cannot determine an exact string property type in the following situations:</span></span> 
  
- <span data-ttu-id="cef14-142">将_lpPropTagArray_参数设置为 NULL 以请求所有属性。</span><span class="sxs-lookup"><span data-stu-id="cef14-142">The  _lpPropTagArray_ parameter is set to NULL to request all properties.</span></span> 
    
- <span data-ttu-id="cef14-143">**aulPropTag**成员将值 PT_UNSPECIFIED 作为其属性类型包含在属性标记数组中。</span><span class="sxs-lookup"><span data-stu-id="cef14-143">The **aulPropTag** member includes the value PT_UNSPECIFIED as its property type in the property tag array.</span></span> 
    
<span data-ttu-id="cef14-144">如果将_lpPropTagArray_参数设置为 NULL 以检索对象的所有属性, 并且不存在任何属性, 则**GetProps**将执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="cef14-144">If the  _lpPropTagArray_ parameter is set to NULL to retrieve all of the properties of the object and no properties exist, **GetProps** does the following:</span></span> 
  
- <span data-ttu-id="cef14-145">返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="cef14-145">Returns S_OK.</span></span>
    
- <span data-ttu-id="cef14-146">将属性值结构的**cValues**成员中的 count 值设置为0。</span><span class="sxs-lookup"><span data-stu-id="cef14-146">Sets the count value in the **cValues** member of the property value structure to 0.</span></span> 
    
- <span data-ttu-id="cef14-147">将_lpcValues_的内容设置为0。</span><span class="sxs-lookup"><span data-stu-id="cef14-147">Sets the contents of  _lpcValues_ to 0.</span></span> 
    
- <span data-ttu-id="cef14-148">将_lppPropArray_设置为 NULL。</span><span class="sxs-lookup"><span data-stu-id="cef14-148">Sets  _lppPropArray_ to NULL.</span></span> 
    
 <span data-ttu-id="cef14-149">**GetProps**不能返回将**cValues**设置为0的多值属性。</span><span class="sxs-lookup"><span data-stu-id="cef14-149">**GetProps** must not return multiple-value properties with **cValues** set to 0.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="cef14-150">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="cef14-150">Notes to implementers</span></span>

<span data-ttu-id="cef14-151">调用[MAPIAllocateBuffer](mapiallocatebuffer.md)函数, 以在_lpPropTagArray_指向的[SPropValue](spropvalue.md)结构中最初分配内存;调用[MAPIAllocateMore](mapiallocatemore.md)以分配结构成员所需的任何额外内存。</span><span class="sxs-lookup"><span data-stu-id="cef14-151">Call the [MAPIAllocateBuffer](mapiallocatebuffer.md) function to allocate memory initially for the [SPropValue](spropvalue.md) structure pointed to by  _lpPropTagArray_; call [MAPIAllocateMore](mapiallocatemore.md) to allocate any additional memory needed for the structure's members.</span></span> 
  
<span data-ttu-id="cef14-152">如果无法检索一个或多个请求的属性的值, 则返回 MAPI_W_ERRORS_RETURNED。</span><span class="sxs-lookup"><span data-stu-id="cef14-152">Return MAPI_W_ERRORS_RETURNED if you cannot retrieve the value for one or more of the requested properties.</span></span> <span data-ttu-id="cef14-153">在属性值结构中, 将**aulPropTag**成员中的 "类型" 设置为 "PT_ERROR", 并将 "**值**" 成员设置为描述错误的状态代码。</span><span class="sxs-lookup"><span data-stu-id="cef14-153">In the property value structure, set the type in the **aulPropTag** member to PT_ERROR and the **Value** member to a status code that describes the error.</span></span> <span data-ttu-id="cef14-154">例如, 如果您必须将字符串转换为 unicode 且不支持 unicode, 请将**Value**成员设置为 MAPI_E_BAD_CHARWIDTH。</span><span class="sxs-lookup"><span data-stu-id="cef14-154">For example, if you have to convert a string to Unicode and do not support Unicode, set the **Value** member to MAPI_E_BAD_CHARWIDTH.</span></span> <span data-ttu-id="cef14-155">如果属性太大, 请将其设置为 MAPI_E_NOT_ENOUGH_MEMORY。</span><span class="sxs-lookup"><span data-stu-id="cef14-155">If the property is too large, set it to MAPI_E_NOT_ENOUGH_MEMORY.</span></span> <span data-ttu-id="cef14-156">如果该对象不支持该属性, 请将其设置为 MAPI_E_NOT_FOUND。</span><span class="sxs-lookup"><span data-stu-id="cef14-156">If the object does not support the property, set it to MAPI_E_NOT_FOUND.</span></span> 
  
<span data-ttu-id="cef14-157">远程传输提供程序的**GetProps**方法的实现必须为调用方请求的属性返回文件夹的属性值。</span><span class="sxs-lookup"><span data-stu-id="cef14-157">A remote transport provider's implementation of the **GetProps** method must return the folder's property values for properties requested by the caller.</span></span> <span data-ttu-id="cef14-158">您的实现必须执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="cef14-158">Your implementation must do the following:</span></span> 
  
- <span data-ttu-id="cef14-159">分配一个属性值数组以返回到调用方, 并将其地址存储在为该目的而传入的属性值指针参数中。</span><span class="sxs-lookup"><span data-stu-id="cef14-159">Allocate a property value array to return to the caller and store its address in the property value pointer parameter passed in for that purpose.</span></span>
    
- <span data-ttu-id="cef14-160">根据传递给**GetProps**的属性标记数组, 将文件夹属性中的属性标记复制到属性值数组中的属性标记中。</span><span class="sxs-lookup"><span data-stu-id="cef14-160">Copy the property tags from the folder's properties into the property tags in the property value array according to the array of property tags passed to **GetProps**.</span></span>
    
- <span data-ttu-id="cef14-161">确保为传递到**GetProps**的所有属性标记设置了属性类型。</span><span class="sxs-lookup"><span data-stu-id="cef14-161">Ensure that the property type is set for all property tags passed to **GetProps**.</span></span> <span data-ttu-id="cef14-162">调用方可以传入 PT_UNSPECIFIED 的属性类型, 在这种情况下, **GetProps**必须为该属性标记设置正确的属性类型。</span><span class="sxs-lookup"><span data-stu-id="cef14-162">The caller can pass in a property type of PT_UNSPECIFIED, in which case **GetProps** must set the correct property type for that property tag.</span></span> 
    
- <span data-ttu-id="cef14-163">根据其标记设置属性值数组中每个属性的值。</span><span class="sxs-lookup"><span data-stu-id="cef14-163">Set the value of each property in the property value array according to its tag.</span></span> <span data-ttu-id="cef14-164">例如, 如果调用方请求的属性标记是**PR_OBJECT_TYPE** ([PidTagObjectType](pidtagobjecttype-canonical-property.md)), 则**GetProps**可以将该值设置为 MAPI_FOLDER。</span><span class="sxs-lookup"><span data-stu-id="cef14-164">For example, if the property tag requested by the caller is **PR_OBJECT_TYPE** ([PidTagObjectType](pidtagobjecttype-canonical-property.md)), **GetProps** can set the value to MAPI_FOLDER.</span></span> 
    
- <span data-ttu-id="cef14-165">如果调用方传递到您的实现未处理的任何属性标记中, 则可以为这些属性将属性标记设置为 PT_ERROR, 并将属性值设置为 MAPI_E_NOT_FOUND。</span><span class="sxs-lookup"><span data-stu-id="cef14-165">If the caller passes in any property tags that your implementation does not handle, you can set the property tag to PT_ERROR for those properties, and set the property value to MAPI_E_NOT_FOUND.</span></span>
    
- <span data-ttu-id="cef14-166">如果没有错误发生, 则返回 S_OK; 如果有错误, 则返回 MAPI_W_ERRORS_RETURNED。</span><span class="sxs-lookup"><span data-stu-id="cef14-166">Return S_OK if no errors occurred or MAPI_W_ERRORS_RETURNED if there were errors.</span></span>
    
<span data-ttu-id="cef14-167">远程传输提供程序的**GetProps**方法实现必须至少支持以下属性:</span><span class="sxs-lookup"><span data-stu-id="cef14-167">A remote transport provider's implementation of the **GetProps** method must support the following properties at a minimum:</span></span> 
  
- <span data-ttu-id="cef14-168">**PR_ACCESS**([PidTagAccess](pidtagaccess-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="cef14-168">**PR_ACCESS** ([PidTagAccess](pidtagaccess-canonical-property.md))</span></span>
    
- <span data-ttu-id="cef14-169">**PR_ACCESS_LEVEL**([PidTagAccessLevel](pidtagaccesslevel-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="cef14-169">**PR_ACCESS_LEVEL** ([PidTagAccessLevel](pidtagaccesslevel-canonical-property.md))</span></span>
    
- <span data-ttu-id="cef14-170">**PR_ASSOC_CONTENT_COUNT**([PidTagAssociatedContentCount](pidtagassociatedcontentcount-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="cef14-170">**PR_ASSOC_CONTENT_COUNT** ([PidTagAssociatedContentCount](pidtagassociatedcontentcount-canonical-property.md))</span></span>
    
- <span data-ttu-id="cef14-171">**PR_CONTENT_COUNT**([PidTagContentCount](pidtagcontentcount-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="cef14-171">**PR_CONTENT_COUNT** ([PidTagContentCount](pidtagcontentcount-canonical-property.md))</span></span>
    
- <span data-ttu-id="cef14-172">**PR_CREATION_TIME**([PidTagCreationTime](pidtagcreationtime-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="cef14-172">**PR_CREATION_TIME** ([PidTagCreationTime](pidtagcreationtime-canonical-property.md))</span></span>
    
- <span data-ttu-id="cef14-173">**PR_DISPLAY_NAME**([PidTagDisplayName](pidtagdisplayname-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="cef14-173">**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md))</span></span>
    
- <span data-ttu-id="cef14-174">**PR_DISPLAY_TYPE**([PidTagDisplayType](pidtagdisplaytype-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="cef14-174">**PR_DISPLAY_TYPE** ([PidTagDisplayType](pidtagdisplaytype-canonical-property.md))</span></span>
    
- <span data-ttu-id="cef14-175">**PR_FOLDER_TYPE**([PidTagFolderType](pidtagfoldertype-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="cef14-175">**PR_FOLDER_TYPE** ([PidTagFolderType](pidtagfoldertype-canonical-property.md))</span></span>
    
- <span data-ttu-id="cef14-176">**PR_OBJECT_TYPE**</span><span class="sxs-lookup"><span data-stu-id="cef14-176">**PR_OBJECT_TYPE**</span></span>
    
- <span data-ttu-id="cef14-177">**PR_SUBFOLDERS**([PidTagSubfolders](pidtagsubfolders-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="cef14-177">**PR_SUBFOLDERS** ([PidTagSubfolders](pidtagsubfolders-canonical-property.md))</span></span>
    
## <a name="notes-to-callers"></a><span data-ttu-id="cef14-178">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="cef14-178">Notes to callers</span></span>

<span data-ttu-id="cef14-179">对于类型为 PT_OBJECT 的属性, 请调用[IMAPIProp:: OpenProperty](imapiprop-openproperty.md)方法, 而不是**GetProps**。</span><span class="sxs-lookup"><span data-stu-id="cef14-179">For properties of type PT_OBJECT, call the [IMAPIProp::OpenProperty](imapiprop-openproperty.md) method instead of **GetProps**.</span></span> 
  
<span data-ttu-id="cef14-180">对于安全属性, 不希望通过调用**GetProps**并将_lppPropTagArray_参数设置为 NULL 来检索这些属性。</span><span class="sxs-lookup"><span data-stu-id="cef14-180">For secure properties, do not expect to retrieve them by calling **GetProps** with the  _lppPropTagArray_ parameter set to NULL.</span></span> <span data-ttu-id="cef14-181">调用**GetProps**时, 您必须在其属性标记数组的**aulPropTag**成员中显式设置安全属性的标识符。</span><span class="sxs-lookup"><span data-stu-id="cef14-181">You must explicitly set a secure property's identifier in the **aulPropTag** member of its property tag array when you call **GetProps**.</span></span> <span data-ttu-id="cef14-182">安全属性可用的时间和方式由服务提供商负责。</span><span class="sxs-lookup"><span data-stu-id="cef14-182">When and how a secure property is available is up to the service provider.</span></span> 
  
<span data-ttu-id="cef14-183">仅在**GetProps**返回 S_OK 或 MAPI_W_ERRORS_RETURNED 时调用[MAPIFreeBuffer](mapifreebuffer.md)函数, 从而释放返回的**SPropValue**结构。</span><span class="sxs-lookup"><span data-stu-id="cef14-183">Free the returned **SPropValue** structure by calling the [MAPIFreeBuffer](mapifreebuffer.md) function only if **GetProps** returns S_OK or MAPI_W_ERRORS_RETURNED.</span></span> 
  
<span data-ttu-id="cef14-184">如果**GetProps**返回 MAPI_W_ERRORS_RETURNED, 因为它无法访问一个或多个属性, 请检查返回的属性的属性标记。</span><span class="sxs-lookup"><span data-stu-id="cef14-184">If **GetProps** returns MAPI_W_ERRORS_RETURNED because it could not access one or more properties, check the property tags of the returned properties.</span></span> <span data-ttu-id="cef14-185">失败的属性将在其属性值结构中设置以下值:</span><span class="sxs-lookup"><span data-stu-id="cef14-185">The failed properties will have the following values set in their property value structure:</span></span> 
  
- <span data-ttu-id="cef14-186">**aulPropTag**成员集中的属性类型设置为 PT_ERROR。</span><span class="sxs-lookup"><span data-stu-id="cef14-186">The property type in the **aulPropTag** member set to PT_ERROR.</span></span> 
    
- <span data-ttu-id="cef14-187">**value**成员中的属性值设置为错误的状态代码, 如 MAPI_E_NOT_FOUND。</span><span class="sxs-lookup"><span data-stu-id="cef14-187">The property value in the **Value** member set to a status code for the error, such as MAPI_E_NOT_FOUND.</span></span> 
    
<span data-ttu-id="cef14-188">由于在属性值结构中太大而无法轻松地返回的属性的**value**成员设置为 MAPI_E_NOT_ENOUGH_MEMORY, 因此这些属性会失败。</span><span class="sxs-lookup"><span data-stu-id="cef14-188">Properties that fail because they are too large to conveniently be returned in the property value structure have their **Value** member set to MAPI_E_NOT_ENOUGH_MEMORY.</span></span> <span data-ttu-id="cef14-189">通常情况下, 当属性的值为 4 KB 或更大时, PT_STRING8、PT_UNICODE 或 PT_BINARY 类型的字符串或二进制属性会发生此情况。</span><span class="sxs-lookup"><span data-stu-id="cef14-189">Typically, this occurs with string or binary properties of type PT_STRING8, PT_UNICODE, or PT_BINARY when the value of the property is 4 KB or larger.</span></span> <span data-ttu-id="cef14-190">调用**IMAPIProp:: OpenProperty**以检索大型属性。</span><span class="sxs-lookup"><span data-stu-id="cef14-190">Call **IMAPIProp::OpenProperty** to retrieve large properties.</span></span> 
  
<span data-ttu-id="cef14-191">并非**GetProps**的所有实现都支持字符串的 Unicode 和 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="cef14-191">Not all implementations of **GetProps** support both the Unicode and ANSI formats for character strings.</span></span> <span data-ttu-id="cef14-192">当某个特定属性需要字符串格式转换且**GetProps**无法支持该属性时, 该属性的**值**成员将设置为 MAPI_E_BAD_CHARWIDTH。</span><span class="sxs-lookup"><span data-stu-id="cef14-192">When a particular property requires string format conversion and **GetProps** cannot support it, the **Value** member for the property is set to MAPI_E_BAD_CHARWIDTH.</span></span> 
  
<span data-ttu-id="cef14-193">若要检查 pst 是否为 SharePoint pst, 请使用[IMAPISession:: OpenMsgStore](imapisession-openmsgstore.md)装入 pst, 然后对请求该属性的邮件存储对象调用**GetProps** 。</span><span class="sxs-lookup"><span data-stu-id="cef14-193">To check if a PST is a SharePoint PST, mount the PST using [IMAPISession::OpenMsgStore](imapisession-openmsgstore.md), then call **GetProps** on the message store object requesting this property.</span></span> <span data-ttu-id="cef14-194">如果存在, 则可以假定已为 SharePoint 配置了 PST;如果不是, 则 PST 尚未配置为 SharePoint pst。</span><span class="sxs-lookup"><span data-stu-id="cef14-194">If it exists, you can assume the PST has been configured for SharePoint; if not, the PST has not been configured as a SharePoint PST.</span></span> 
  
<span data-ttu-id="cef14-195">有关如何使用**GetProps**访问属性的详细信息, 请参阅[检索 MAPI 属性](retrieving-mapi-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="cef14-195">For more information about how to use **GetProps** to access properties, see [Retrieving MAPI Properties](retrieving-mapi-properties.md).</span></span>
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="cef14-196">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="cef14-196">MFCMAPI reference</span></span>

<span data-ttu-id="cef14-197">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="cef14-197">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="cef14-198">**文件**</span><span class="sxs-lookup"><span data-stu-id="cef14-198">**File**</span></span>|<span data-ttu-id="cef14-199">**函数**</span><span class="sxs-lookup"><span data-stu-id="cef14-199">**Function**</span></span>|<span data-ttu-id="cef14-200">**备注**</span><span class="sxs-lookup"><span data-stu-id="cef14-200">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="cef14-201">MAPIFunctions</span><span class="sxs-lookup"><span data-stu-id="cef14-201">MAPIFunctions.cpp</span></span>  <br/> |<span data-ttu-id="cef14-202">GetPropsNULL</span><span class="sxs-lookup"><span data-stu-id="cef14-202">GetPropsNULL</span></span>  <br/> |<span data-ttu-id="cef14-203">MFCMAPI 使用**IMAPIProp:: GetProps**方法获取对象的所有属性, 方法是在_GetPropList_参数中传递的[IMAPIProp:: lpPropTagArray](imapiprop-getproplist.md)方法返回的 NULL 或数组。</span><span class="sxs-lookup"><span data-stu-id="cef14-203">MFCMAPI uses the **IMAPIProp::GetProps** method to obtain all properties for an object by passing either NULL or the array returned by the [IMAPIProp::GetPropList](imapiprop-getproplist.md) method in the  _lpPropTagArray_ parameter.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="cef14-204">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cef14-204">See also</span></span>



[<span data-ttu-id="cef14-205">IMAPIProp::GetPropList</span><span class="sxs-lookup"><span data-stu-id="cef14-205">IMAPIProp::GetPropList</span></span>](imapiprop-getproplist.md)
  
[<span data-ttu-id="cef14-206">IMAPIProp::OpenProperty</span><span class="sxs-lookup"><span data-stu-id="cef14-206">IMAPIProp::OpenProperty</span></span>](imapiprop-openproperty.md)
  
[<span data-ttu-id="cef14-207">MAPIAllocateBuffer</span><span class="sxs-lookup"><span data-stu-id="cef14-207">MAPIAllocateBuffer</span></span>](mapiallocatebuffer.md)
  
[<span data-ttu-id="cef14-208">MAPIAllocateMore</span><span class="sxs-lookup"><span data-stu-id="cef14-208">MAPIAllocateMore</span></span>](mapiallocatemore.md)
  
[<span data-ttu-id="cef14-209">MAPIFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="cef14-209">MAPIFreeBuffer</span></span>](mapifreebuffer.md)
  
[<span data-ttu-id="cef14-210">SPropTagArray</span><span class="sxs-lookup"><span data-stu-id="cef14-210">SPropTagArray</span></span>](sproptagarray.md)
  
[<span data-ttu-id="cef14-211">SPropValue</span><span class="sxs-lookup"><span data-stu-id="cef14-211">SPropValue</span></span>](spropvalue.md)
  
[<span data-ttu-id="cef14-212">IMAPIProp : IUnknown</span><span class="sxs-lookup"><span data-stu-id="cef14-212">IMAPIProp : IUnknown</span></span>](imapipropiunknown.md)


[<span data-ttu-id="cef14-213">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="cef14-213">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)
  
[<span data-ttu-id="cef14-214">检索 MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="cef14-214">Retrieving MAPI Properties</span></span>](retrieving-mapi-properties.md)
  
[<span data-ttu-id="cef14-215">使用宏进行错误处理</span><span class="sxs-lookup"><span data-stu-id="cef14-215">Using Macros for Error Handling</span></span>](using-macros-for-error-handling.md)

