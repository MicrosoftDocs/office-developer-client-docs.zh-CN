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
ms.openlocfilehash: 33351235db2a9a3f9d9b67f59e8356a0fa8abfa8
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775525"
---
# <a name="imapipropgetprops"></a><span data-ttu-id="e0bac-103">IMAPIProp::GetProps</span><span class="sxs-lookup"><span data-stu-id="e0bac-103">IMAPIProp::GetProps</span></span>

  
  
<span data-ttu-id="e0bac-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="e0bac-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="e0bac-105">检索一个或多个对象的属性的属性值。</span><span class="sxs-lookup"><span data-stu-id="e0bac-105">Retrieves the property value of one or more properties of an object.</span></span>
  
```cpp
HRESULT GetProps(
  LPSPropTagArray lpPropTagArray,
  ULONG ulFlags,
  ULONG FAR * lpcValues,
  LPSPropValue FAR * lppPropArray
);
```

## <a name="parameters"></a><span data-ttu-id="e0bac-106">参数</span><span class="sxs-lookup"><span data-stu-id="e0bac-106">Parameters</span></span>

 <span data-ttu-id="e0bac-107">_lpPropTagArray_</span><span class="sxs-lookup"><span data-stu-id="e0bac-107">_lpPropTagArray_</span></span>
  
> <span data-ttu-id="e0bac-108">[in]一个指向数组属性标记来标识要检索其值的属性。</span><span class="sxs-lookup"><span data-stu-id="e0bac-108">[in] A pointer to an array of property tags that identify the properties whose values are to be retrieved.</span></span> <span data-ttu-id="e0bac-109">_LpPropTagArray_参数必须为或者是 NULL，表明对象的所有属性的值应返回，或指向[SPropTagArray](sproptagarray.md)结构，其中包含一个或多个属性标记。</span><span class="sxs-lookup"><span data-stu-id="e0bac-109">The  _lpPropTagArray_ parameter must be either NULL, indicating that values for all properties of the object should be returned, or point to an [SPropTagArray](sproptagarray.md) structure that contains one or more property tags.</span></span> 
    
 <span data-ttu-id="e0bac-110">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="e0bac-110">_ulFlags_</span></span>
  
> <span data-ttu-id="e0bac-111">[in]位掩码的标志，指示具有 PT_UNSPECIFIED 类型的属性的格式。</span><span class="sxs-lookup"><span data-stu-id="e0bac-111">[in] A bitmask of flags that indicates the format for properties that have the type PT_UNSPECIFIED.</span></span> <span data-ttu-id="e0bac-112">可以设置以下标记：</span><span class="sxs-lookup"><span data-stu-id="e0bac-112">The following flag can be set:</span></span>
    
<span data-ttu-id="e0bac-113">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="e0bac-113">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="e0bac-114">这些属性的字符串值应为 Unicode 格式返回。</span><span class="sxs-lookup"><span data-stu-id="e0bac-114">The string values for these properties should be returned in the Unicode format.</span></span> <span data-ttu-id="e0bac-115">如果未设置 MAPI_UNICODE 标志，应以 ANSI 格式返回的字符串值。</span><span class="sxs-lookup"><span data-stu-id="e0bac-115">If the MAPI_UNICODE flag is not set, the string values should be returned in the ANSI format.</span></span>
    
 <span data-ttu-id="e0bac-116">_lpcValues_</span><span class="sxs-lookup"><span data-stu-id="e0bac-116">_lpcValues_</span></span>
  
> <span data-ttu-id="e0bac-117">[输出]一个指向_lppPropArray_参数指向的属性值的计数。</span><span class="sxs-lookup"><span data-stu-id="e0bac-117">[out] A pointer to a count of property values pointed to by the  _lppPropArray_ parameter.</span></span> <span data-ttu-id="e0bac-118">如果_lppPropArray_为 NULL，则_lpcValues_参数的内容为零。</span><span class="sxs-lookup"><span data-stu-id="e0bac-118">If  _lppPropArray_ is NULL, the content of the  _lpcValues_ parameter is zero.</span></span> 
    
 <span data-ttu-id="e0bac-119">_lppPropArray_</span><span class="sxs-lookup"><span data-stu-id="e0bac-119">_lppPropArray_</span></span>
  
> <span data-ttu-id="e0bac-120">[输出]指向检索的属性值的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="e0bac-120">[out] A pointer to a pointer to the retrieved property values.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="e0bac-121">返回值</span><span class="sxs-lookup"><span data-stu-id="e0bac-121">Return value</span></span>

<span data-ttu-id="e0bac-122">S_OK</span><span class="sxs-lookup"><span data-stu-id="e0bac-122">S_OK</span></span> 
  
> <span data-ttu-id="e0bac-123">已成功检索属性值。</span><span class="sxs-lookup"><span data-stu-id="e0bac-123">The property values were successfully retrieved.</span></span>
    
<span data-ttu-id="e0bac-124">MAPI_W_ERRORS_RETURNED</span><span class="sxs-lookup"><span data-stu-id="e0bac-124">MAPI_W_ERRORS_RETURNED</span></span> 
  
> <span data-ttu-id="e0bac-125">调用成功总体上讲，但无法访问一个或多个属性。</span><span class="sxs-lookup"><span data-stu-id="e0bac-125">The call succeeded overall, but one or more properties could not be accessed.</span></span> <span data-ttu-id="e0bac-126">不可用的每个属性的属性值的**aulPropTag**成员具有 PT_ERROR 和零的标识符的属性类型。</span><span class="sxs-lookup"><span data-stu-id="e0bac-126">The **aulPropTag** member of the property value for each unavailable property has a property type of PT_ERROR and an identifier of zero.</span></span> <span data-ttu-id="e0bac-127">返回此警告时，应处理呼叫为成功。</span><span class="sxs-lookup"><span data-stu-id="e0bac-127">When this warning is returned, the call should be handled as successful.</span></span> <span data-ttu-id="e0bac-128">若要测试此警告，请使用**HR_FAILED**宏。</span><span class="sxs-lookup"><span data-stu-id="e0bac-128">To test for this warning, use the **HR_FAILED** macro.</span></span> <span data-ttu-id="e0bac-129">有关详细信息，请参阅[使用宏的错误处理](using-macros-for-error-handling.md)。</span><span class="sxs-lookup"><span data-stu-id="e0bac-129">For more information, see [Using Macros for Error Handling](using-macros-for-error-handling.md).</span></span>
    
<span data-ttu-id="e0bac-130">MAPI_E_INVALID_PARAMETER</span><span class="sxs-lookup"><span data-stu-id="e0bac-130">MAPI_E_INVALID_PARAMETER</span></span> 
  
> <span data-ttu-id="e0bac-131">在所指的_lpPropTagArray_ **SPropTagArray**结构的**cValues**成员传递零。</span><span class="sxs-lookup"><span data-stu-id="e0bac-131">Zero was passed in the **cValues** member of the **SPropTagArray** structure pointed to by  _lpPropTagArray_.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="e0bac-132">说明</span><span class="sxs-lookup"><span data-stu-id="e0bac-132">Remarks</span></span>

<span data-ttu-id="e0bac-133">**IMAPIProp::GetProps**方法获取对象的一个或多个属性的属性值。</span><span class="sxs-lookup"><span data-stu-id="e0bac-133">The **IMAPIProp::GetProps** method obtains the property values of one or more properties of an object.</span></span> 
  
<span data-ttu-id="e0bac-134">他们已请求将返回相同的顺序的属性值 （即，该属性标记数组中的属性的顺序所指的_lpPropTagArray_匹配项的属性值结构所指的_lppPropArray 数组中的顺序_).</span><span class="sxs-lookup"><span data-stu-id="e0bac-134">The property values are returned in the same order as they were requested (that is, the order of properties in the property tag array pointed to by  _lpPropTagArray_ matches the order in the array of property value structures pointed to by  _lppPropArray_).</span></span> 
  
<span data-ttu-id="e0bac-135">属性标记数组的**aulPropTag**成员中指定的属性类型指示应在每个属性值结构的**值**成员中返回的值的类型。</span><span class="sxs-lookup"><span data-stu-id="e0bac-135">The property types specified in the **aulPropTag** members of the property tag array indicate the type of value that should be returned in the **Value** member of each property value structure.</span></span> <span data-ttu-id="e0bac-136">但是，如果呼叫者不知道属性的类型，在**aulPropTag**成员类型可以改为设置到 PT_UNSPECIFIED。</span><span class="sxs-lookup"><span data-stu-id="e0bac-136">However, if the caller does not know the type of a property, the type in the **aulPropTag** member can be set instead to PT_UNSPECIFIED.</span></span> <span data-ttu-id="e0bac-137">在检索值， **GetProps**属性的属性值结构的**aulPropTag**成员中设置正确的类型。</span><span class="sxs-lookup"><span data-stu-id="e0bac-137">In retrieving the value, **GetProps** sets the correct type in the **aulPropTag** member of the property value structure for the property.</span></span> 
  
<span data-ttu-id="e0bac-138">如果**SPropTagArray**中_lpPropTagArray_中指定属性类型中**SPropValue** _lppPropArray_中返回, 的属性值将具有完全匹配的请求的类型的类型，除非返回错误值而是。</span><span class="sxs-lookup"><span data-stu-id="e0bac-138">If property types are specified in the **SPropTagArray** in  _lpPropTagArray_, the property values in the **SPropValue** returned in  _lppPropArray_ have types that exactly match the requested types, unless an error value is returned instead.</span></span> 
  
<span data-ttu-id="e0bac-139">字符串属性可以有两种属性类型之一： PT_UNICODE 表示 Unicode 格式和 PT_STRING8 来代表 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="e0bac-139">String properties can have one of two property types: PT_UNICODE to represent the Unicode format and PT_STRING8 to represent the ANSI format.</span></span> <span data-ttu-id="e0bac-140">如果 MAPI_UNICODE 标记中设置_ulFlags_参数，只要**GetProps**无法确定适当的格式为字符串属性，则它将返回其值为 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="e0bac-140">If the MAPI_UNICODE flag is set in the  _ulFlags_ parameter, whenever **GetProps** cannot determine the appropriate format for a string property, it returns its value in the Unicode format.</span></span> <span data-ttu-id="e0bac-141">**GetProps**无法确定在下列情况下的准确字符串属性类型：</span><span class="sxs-lookup"><span data-stu-id="e0bac-141">**GetProps** cannot determine an exact string property type in the following situations:</span></span> 
  
- <span data-ttu-id="e0bac-142">_LpPropTagArray_参数设置为 NULL，请求的所有属性。</span><span class="sxs-lookup"><span data-stu-id="e0bac-142">The  _lpPropTagArray_ parameter is set to NULL to request all properties.</span></span> 
    
- <span data-ttu-id="e0bac-143">**AulPropTag**成员作为其属性类型属性标记数组中包含的值 PT_UNSPECIFIED。</span><span class="sxs-lookup"><span data-stu-id="e0bac-143">The **aulPropTag** member includes the value PT_UNSPECIFIED as its property type in the property tag array.</span></span> 
    
<span data-ttu-id="e0bac-144">如果_lpPropTagArray_参数设置为 NULL，若要检索所有对象的属性，并且不存在任何属性， **GetProps**执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="e0bac-144">If the  _lpPropTagArray_ parameter is set to NULL to retrieve all of the properties of the object and no properties exist, **GetProps** does the following:</span></span> 
  
- <span data-ttu-id="e0bac-145">返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="e0bac-145">Returns S_OK.</span></span>
    
- <span data-ttu-id="e0bac-146">将数值设置为 0 的属性值结构的**cValues**成员中。</span><span class="sxs-lookup"><span data-stu-id="e0bac-146">Sets the count value in the **cValues** member of the property value structure to 0.</span></span> 
    
- <span data-ttu-id="e0bac-147">将_lpcValues_的内容设置为 0。</span><span class="sxs-lookup"><span data-stu-id="e0bac-147">Sets the contents of  _lpcValues_ to 0.</span></span> 
    
- <span data-ttu-id="e0bac-148">将_lppPropArray_设置为 NULL。</span><span class="sxs-lookup"><span data-stu-id="e0bac-148">Sets  _lppPropArray_ to NULL.</span></span> 
    
 <span data-ttu-id="e0bac-149">不能**GetProps**返回**cValues**多值属性设置为 0。</span><span class="sxs-lookup"><span data-stu-id="e0bac-149">**GetProps** must not return multiple-value properties with **cValues** set to 0.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="e0bac-150">针对实施者的注释</span><span class="sxs-lookup"><span data-stu-id="e0bac-150">Notes to implementers</span></span>

<span data-ttu-id="e0bac-151">调用[MAPIAllocateBuffer](mapiallocatebuffer.md)函数所指的_lpPropTagArray_; [SPropValue](spropvalue.md)结构最初分配内存调用[MAPIAllocateMore](mapiallocatemore.md)分配所需的结构的成员的任何其他内存。</span><span class="sxs-lookup"><span data-stu-id="e0bac-151">Call the [MAPIAllocateBuffer](mapiallocatebuffer.md) function to allocate memory initially for the [SPropValue](spropvalue.md) structure pointed to by  _lpPropTagArray_; call [MAPIAllocateMore](mapiallocatemore.md) to allocate any additional memory needed for the structure's members.</span></span> 
  
<span data-ttu-id="e0bac-152">如果您无法检索一个或多个请求属性的值，则返回 MAPI_W_ERRORS_RETURNED。</span><span class="sxs-lookup"><span data-stu-id="e0bac-152">Return MAPI_W_ERRORS_RETURNED if you cannot retrieve the value for one or more of the requested properties.</span></span> <span data-ttu-id="e0bac-153">在属性值结构中，设置为 PT_ERROR **aulPropTag**成员和描述错误状态代码**值**成员中的类型。</span><span class="sxs-lookup"><span data-stu-id="e0bac-153">In the property value structure, set the type in the **aulPropTag** member to PT_ERROR and the **Value** member to a status code that describes the error.</span></span> <span data-ttu-id="e0bac-154">例如，如果已将字符串转换为 Unicode，并且不支持 Unicode，则可设置为 MAPI_E_BAD_CHARWIDTH**值**成员。</span><span class="sxs-lookup"><span data-stu-id="e0bac-154">For example, if you have to convert a string to Unicode and do not support Unicode, set the **Value** member to MAPI_E_BAD_CHARWIDTH.</span></span> <span data-ttu-id="e0bac-155">如果该属性是太大，则将其设置为 MAPI_E_NOT_ENOUGH_MEMORY。</span><span class="sxs-lookup"><span data-stu-id="e0bac-155">If the property is too large, set it to MAPI_E_NOT_ENOUGH_MEMORY.</span></span> <span data-ttu-id="e0bac-156">如果对象不支持属性，则将其设置为 MAPI_E_NOT_FOUND。</span><span class="sxs-lookup"><span data-stu-id="e0bac-156">If the object does not support the property, set it to MAPI_E_NOT_FOUND.</span></span> 
  
<span data-ttu-id="e0bac-157">远程传输提供程序的方法的实现， **GetProps**必须返回请求的呼叫者的属性的文件夹的属性值。</span><span class="sxs-lookup"><span data-stu-id="e0bac-157">A remote transport provider's implementation of the **GetProps** method must return the folder's property values for properties requested by the caller.</span></span> <span data-ttu-id="e0bac-158">实现必须执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="e0bac-158">Your implementation must do the following:</span></span> 
  
- <span data-ttu-id="e0bac-159">分配属性值数组返回到呼叫者，并将其地址存储在属性值指针参数中传递为实现此目的。</span><span class="sxs-lookup"><span data-stu-id="e0bac-159">Allocate a property value array to return to the caller and store its address in the property value pointer parameter passed in for that purpose.</span></span>
    
- <span data-ttu-id="e0bac-160">将从该文件夹的属性的属性标记复制到数组传递给**GetProps**属性标记根据属性值数组中的属性标记中。</span><span class="sxs-lookup"><span data-stu-id="e0bac-160">Copy the property tags from the folder's properties into the property tags in the property value array according to the array of property tags passed to **GetProps**.</span></span>
    
- <span data-ttu-id="e0bac-161">确保属性类型为传递给**GetProps**的所有属性标记。</span><span class="sxs-lookup"><span data-stu-id="e0bac-161">Ensure that the property type is set for all property tags passed to **GetProps**.</span></span> <span data-ttu-id="e0bac-162">呼叫者可以传递的 PT_UNSPECIFIED，案例**GetProps**必须设置该属性标记的正确的属性类型的属性类型。</span><span class="sxs-lookup"><span data-stu-id="e0bac-162">The caller can pass in a property type of PT_UNSPECIFIED, in which case **GetProps** must set the correct property type for that property tag.</span></span> 
    
- <span data-ttu-id="e0bac-163">设置属性值数组根据其标记中的每个属性的值。</span><span class="sxs-lookup"><span data-stu-id="e0bac-163">Set the value of each property in the property value array according to its tag.</span></span> <span data-ttu-id="e0bac-164">例如，如果呼叫者请求的属性标记为**PR_OBJECT_TYPE** ([PidTagObjectType](pidtagobjecttype-canonical-property.md))， **GetProps**可以将值设置为 MAPI_FOLDER。</span><span class="sxs-lookup"><span data-stu-id="e0bac-164">For example, if the property tag requested by the caller is **PR_OBJECT_TYPE** ([PidTagObjectType](pidtagobjecttype-canonical-property.md)), **GetProps** can set the value to MAPI_FOLDER.</span></span> 
    
- <span data-ttu-id="e0bac-165">如果呼叫者通过在您的实现并不处理任何属性标记中，可以设置该属性标记为 PT_ERROR 这些属性，并将该属性值设置为 MAPI_E_NOT_FOUND。</span><span class="sxs-lookup"><span data-stu-id="e0bac-165">If the caller passes in any property tags that your implementation does not handle, you can set the property tag to PT_ERROR for those properties, and set the property value to MAPI_E_NOT_FOUND.</span></span>
    
- <span data-ttu-id="e0bac-166">如果出现错误，则返回 S_OK 如果不出现任何错误或 MAPI_W_ERRORS_RETURNED。</span><span class="sxs-lookup"><span data-stu-id="e0bac-166">Return S_OK if no errors occurred or MAPI_W_ERRORS_RETURNED if there were errors.</span></span>
    
<span data-ttu-id="e0bac-167">远程传输提供程序的方法的实现， **GetProps**必须支持最少的以下属性：</span><span class="sxs-lookup"><span data-stu-id="e0bac-167">A remote transport provider's implementation of the **GetProps** method must support the following properties at a minimum:</span></span> 
  
- <span data-ttu-id="e0bac-168">**PR_ACCESS**([PidTagAccess](pidtagaccess-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="e0bac-168">**PR_ACCESS** ([PidTagAccess](pidtagaccess-canonical-property.md))</span></span>
    
- <span data-ttu-id="e0bac-169">**PR_ACCESS_LEVEL**([PidTagAccessLevel](pidtagaccesslevel-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="e0bac-169">**PR_ACCESS_LEVEL** ([PidTagAccessLevel](pidtagaccesslevel-canonical-property.md))</span></span>
    
- <span data-ttu-id="e0bac-170">**PR_ASSOC_CONTENT_COUNT**([PidTagAssociatedContentCount](pidtagassociatedcontentcount-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="e0bac-170">**PR_ASSOC_CONTENT_COUNT** ([PidTagAssociatedContentCount](pidtagassociatedcontentcount-canonical-property.md))</span></span>
    
- <span data-ttu-id="e0bac-171">**PR_CONTENT_COUNT**([PidTagContentCount](pidtagcontentcount-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="e0bac-171">**PR_CONTENT_COUNT** ([PidTagContentCount](pidtagcontentcount-canonical-property.md))</span></span>
    
- <span data-ttu-id="e0bac-172">**PR_CREATION_TIME**([PidTagCreationTime](pidtagcreationtime-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="e0bac-172">**PR_CREATION_TIME** ([PidTagCreationTime](pidtagcreationtime-canonical-property.md))</span></span>
    
- <span data-ttu-id="e0bac-173">**PR_DISPLAY_NAME**([PidTagDisplayName](pidtagdisplayname-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="e0bac-173">**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md))</span></span>
    
- <span data-ttu-id="e0bac-174">**PR_DISPLAY_TYPE**([PidTagDisplayType](pidtagdisplaytype-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="e0bac-174">**PR_DISPLAY_TYPE** ([PidTagDisplayType](pidtagdisplaytype-canonical-property.md))</span></span>
    
- <span data-ttu-id="e0bac-175">**PR_FOLDER_TYPE**([PidTagFolderType](pidtagfoldertype-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="e0bac-175">**PR_FOLDER_TYPE** ([PidTagFolderType](pidtagfoldertype-canonical-property.md))</span></span>
    
- <span data-ttu-id="e0bac-176">**PR_OBJECT_TYPE**</span><span class="sxs-lookup"><span data-stu-id="e0bac-176">**PR_OBJECT_TYPE**</span></span>
    
- <span data-ttu-id="e0bac-177">**PR_SUBFOLDERS**([PidTagSubfolders](pidtagsubfolders-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="e0bac-177">**PR_SUBFOLDERS** ([PidTagSubfolders](pidtagsubfolders-canonical-property.md))</span></span>
    
## <a name="notes-to-callers"></a><span data-ttu-id="e0bac-178">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="e0bac-178">Notes to callers</span></span>

<span data-ttu-id="e0bac-179">对于类型 PT_OBJECT 的属性，则调用而不是**GetProps** [IMAPIProp::OpenProperty](imapiprop-openproperty.md)方法。</span><span class="sxs-lookup"><span data-stu-id="e0bac-179">For properties of type PT_OBJECT, call the [IMAPIProp::OpenProperty](imapiprop-openproperty.md) method instead of **GetProps**.</span></span> 
  
<span data-ttu-id="e0bac-180">对于安全属性，不希望检索其调用**GetProps**不带_lppPropTagArray_参数设置为 NULL。</span><span class="sxs-lookup"><span data-stu-id="e0bac-180">For secure properties, do not expect to retrieve them by calling **GetProps** with the  _lppPropTagArray_ parameter set to NULL.</span></span> <span data-ttu-id="e0bac-181">调用**GetProps**时，您必须显式设置其属性标记数组的**aulPropTag**成员中安全属性的标识符。</span><span class="sxs-lookup"><span data-stu-id="e0bac-181">You must explicitly set a secure property's identifier in the **aulPropTag** member of its property tag array when you call **GetProps**.</span></span> <span data-ttu-id="e0bac-182">何时以及如何安全属性是可由服务提供商。</span><span class="sxs-lookup"><span data-stu-id="e0bac-182">When and how a secure property is available is up to the service provider.</span></span> 
  
<span data-ttu-id="e0bac-183">通过**GetProps**返回 S_OK 或 MAPI_W_ERRORS_RETURNED 时，才调用[MAPIFreeBuffer](mapifreebuffer.md)函数释放返回的**SPropValue**结构。</span><span class="sxs-lookup"><span data-stu-id="e0bac-183">Free the returned **SPropValue** structure by calling the [MAPIFreeBuffer](mapifreebuffer.md) function only if **GetProps** returns S_OK or MAPI_W_ERRORS_RETURNED.</span></span> 
  
<span data-ttu-id="e0bac-184">如果**GetProps**返回 MAPI_W_ERRORS_RETURNED，因为它无法访问一个或多个属性，则检查属性标记返回的属性。</span><span class="sxs-lookup"><span data-stu-id="e0bac-184">If **GetProps** returns MAPI_W_ERRORS_RETURNED because it could not access one or more properties, check the property tags of the returned properties.</span></span> <span data-ttu-id="e0bac-185">失败的属性将具有设置其属性值结构中的以下值：</span><span class="sxs-lookup"><span data-stu-id="e0bac-185">The failed properties will have the following values set in their property value structure:</span></span> 
  
- <span data-ttu-id="e0bac-186">在设置为 PT_ERROR **aulPropTag**成员属性类型。</span><span class="sxs-lookup"><span data-stu-id="e0bac-186">The property type in the **aulPropTag** member set to PT_ERROR.</span></span> 
    
- <span data-ttu-id="e0bac-187">**值**成员中的属性值设置为错误，例如 MAPI_E_NOT_FOUND 状态代码。</span><span class="sxs-lookup"><span data-stu-id="e0bac-187">The property value in the **Value** member set to a status code for the error, such as MAPI_E_NOT_FOUND.</span></span> 
    
<span data-ttu-id="e0bac-188">失败，因为它们是太大，以方便地返回属性值结构中的属性已设置为 MAPI_E_NOT_ENOUGH_MEMORY 其**值**成员。</span><span class="sxs-lookup"><span data-stu-id="e0bac-188">Properties that fail because they are too large to conveniently be returned in the property value structure have their **Value** member set to MAPI_E_NOT_ENOUGH_MEMORY.</span></span> <span data-ttu-id="e0bac-189">通常，这时发生类型的字符串或二进制属性与 PT_STRING8、 PT_UNICODE 或 PT_BINARY 属性的值为 4 KB 或更大。</span><span class="sxs-lookup"><span data-stu-id="e0bac-189">Typically, this occurs with string or binary properties of type PT_STRING8, PT_UNICODE, or PT_BINARY when the value of the property is 4 KB or larger.</span></span> <span data-ttu-id="e0bac-190">调用**IMAPIProp::OpenProperty**检索大型属性。</span><span class="sxs-lookup"><span data-stu-id="e0bac-190">Call **IMAPIProp::OpenProperty** to retrieve large properties.</span></span> 
  
<span data-ttu-id="e0bac-191">并非所有的**GetProps**实现支持的字符的字符串的 Unicode 和 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="e0bac-191">Not all implementations of **GetProps** support both the Unicode and ANSI formats for character strings.</span></span> <span data-ttu-id="e0bac-192">当特定属性需要字符串格式转换和**GetProps**无法支持它时，属性**值**成员设置为 MAPI_E_BAD_CHARWIDTH。</span><span class="sxs-lookup"><span data-stu-id="e0bac-192">When a particular property requires string format conversion and **GetProps** cannot support it, the **Value** member for the property is set to MAPI_E_BAD_CHARWIDTH.</span></span> 
  
<span data-ttu-id="e0bac-193">若要检查 PST 是否 SharePoint PST，装入 PST 使用[IMAPISession::OpenMsgStore](imapisession-openmsgstore.md)，然后调用**GetProps**上请求此属性的消息存储对象。</span><span class="sxs-lookup"><span data-stu-id="e0bac-193">To check if a PST is a SharePoint PST, mount the PST using [IMAPISession::OpenMsgStore](imapisession-openmsgstore.md), then call **GetProps** on the message store object requesting this property.</span></span> <span data-ttu-id="e0bac-194">如果存在，您可以假定 PST 已配置的 SharePoint;如果没有，作为 SharePoint PST 尚未配置太平洋标准时间。</span><span class="sxs-lookup"><span data-stu-id="e0bac-194">If it exists, you can assume the PST has been configured for SharePoint; if not, the PST has not been configured as a SharePoint PST.</span></span> 
  
<span data-ttu-id="e0bac-195">有关如何使用**GetProps**访问属性的详细信息，请参阅[检索 MAPI 属性](retrieving-mapi-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="e0bac-195">For more information about how to use **GetProps** to access properties, see [Retrieving MAPI Properties](retrieving-mapi-properties.md).</span></span>
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="e0bac-196">MFCMAPI 参考 （英文）</span><span class="sxs-lookup"><span data-stu-id="e0bac-196">MFCMAPI reference</span></span>

<span data-ttu-id="e0bac-197">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="e0bac-197">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="e0bac-198">**文件**</span><span class="sxs-lookup"><span data-stu-id="e0bac-198">**File**</span></span>|<span data-ttu-id="e0bac-199">**函数**</span><span class="sxs-lookup"><span data-stu-id="e0bac-199">**Function**</span></span>|<span data-ttu-id="e0bac-200">**Comment**</span><span class="sxs-lookup"><span data-stu-id="e0bac-200">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e0bac-201">MAPIFunctions.cpp</span><span class="sxs-lookup"><span data-stu-id="e0bac-201">MAPIFunctions.cpp</span></span>  <br/> |<span data-ttu-id="e0bac-202">GetPropsNULL</span><span class="sxs-lookup"><span data-stu-id="e0bac-202">GetPropsNULL</span></span>  <br/> |<span data-ttu-id="e0bac-203">MFCMAPI 使用**IMAPIProp::GetProps**方法通过传递 NULL 或_lpPropTagArray_参数中的[IMAPIProp::GetPropList](imapiprop-getproplist.md)方法返回的数组获取对象的所有属性。</span><span class="sxs-lookup"><span data-stu-id="e0bac-203">MFCMAPI uses the **IMAPIProp::GetProps** method to obtain all properties for an object by passing either NULL or the array returned by the [IMAPIProp::GetPropList](imapiprop-getproplist.md) method in the  _lpPropTagArray_ parameter.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="e0bac-204">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e0bac-204">See also</span></span>



[<span data-ttu-id="e0bac-205">IMAPIProp::GetPropList</span><span class="sxs-lookup"><span data-stu-id="e0bac-205">IMAPIProp::GetPropList</span></span>](imapiprop-getproplist.md)
  
[<span data-ttu-id="e0bac-206">IMAPIProp::OpenProperty</span><span class="sxs-lookup"><span data-stu-id="e0bac-206">IMAPIProp::OpenProperty</span></span>](imapiprop-openproperty.md)
  
[<span data-ttu-id="e0bac-207">MAPIAllocateBuffer</span><span class="sxs-lookup"><span data-stu-id="e0bac-207">MAPIAllocateBuffer</span></span>](mapiallocatebuffer.md)
  
[<span data-ttu-id="e0bac-208">MAPIAllocateMore</span><span class="sxs-lookup"><span data-stu-id="e0bac-208">MAPIAllocateMore</span></span>](mapiallocatemore.md)
  
[<span data-ttu-id="e0bac-209">MAPIFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="e0bac-209">MAPIFreeBuffer</span></span>](mapifreebuffer.md)
  
[<span data-ttu-id="e0bac-210">SPropTagArray</span><span class="sxs-lookup"><span data-stu-id="e0bac-210">SPropTagArray</span></span>](sproptagarray.md)
  
[<span data-ttu-id="e0bac-211">SPropValue</span><span class="sxs-lookup"><span data-stu-id="e0bac-211">SPropValue</span></span>](spropvalue.md)
  
[<span data-ttu-id="e0bac-212">IMAPIProp : IUnknown</span><span class="sxs-lookup"><span data-stu-id="e0bac-212">IMAPIProp : IUnknown</span></span>](imapipropiunknown.md)


[<span data-ttu-id="e0bac-213">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="e0bac-213">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)
  
[<span data-ttu-id="e0bac-214">检索 MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="e0bac-214">Retrieving MAPI Properties</span></span>](retrieving-mapi-properties.md)
  
[<span data-ttu-id="e0bac-215">使用宏进行错误处理</span><span class="sxs-lookup"><span data-stu-id="e0bac-215">Using Macros for Error Handling</span></span>](using-macros-for-error-handling.md)

