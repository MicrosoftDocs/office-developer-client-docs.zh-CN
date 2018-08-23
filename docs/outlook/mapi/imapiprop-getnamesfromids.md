---
title: IMAPIPropGetNamesFromIDs
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIProp.GetNamesFromIDs
api_type:
- COM
ms.assetid: 3efa4731-cf32-4a6c-9ba8-d059e58b0d98
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 186afd6a80d0ae3ae0a767456e60b2ebaaa579b9
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22574382"
---
# <a name="imapipropgetnamesfromids"></a><span data-ttu-id="1d28f-103">IMAPIProp::GetNamesFromIDs</span><span class="sxs-lookup"><span data-stu-id="1d28f-103">IMAPIProp::GetNamesFromIDs</span></span>

  
  
<span data-ttu-id="1d28f-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="1d28f-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="1d28f-105">提供对应于一个或多个属性标识符的属性名称。</span><span class="sxs-lookup"><span data-stu-id="1d28f-105">Provides the property names that correspond to one or more property identifiers.</span></span>
  
```cpp
HRESULT GetNamesFromIDs(
  LPSPropTagArray FAR * lppPropTags,
  LPGUID lpPropSetGuid,
  ULONG ulFlags,
  ULONG FAR * lpcPropNames,
  LPMAPINAMEID FAR * FAR * lpppPropNames
);
```

## <a name="parameters"></a><span data-ttu-id="1d28f-106">参数</span><span class="sxs-lookup"><span data-stu-id="1d28f-106">Parameters</span></span>

 <span data-ttu-id="1d28f-107">_lppPropTags_</span><span class="sxs-lookup"><span data-stu-id="1d28f-107">_lppPropTags_</span></span>
  
> <span data-ttu-id="1d28f-108">[传入、 传出]在输入指向包含属性的数组[SPropTagArray](sproptagarray.md)结构的标签;否则，为 NULL，指示应返回所有名称。</span><span class="sxs-lookup"><span data-stu-id="1d28f-108">[in, out] On input, a pointer to an [SPropTagArray](sproptagarray.md) structure that contains an array of property tags; otherwise, NULL, indicating that all names should be returned.</span></span> <span data-ttu-id="1d28f-109">属性标记数组的**cValues**成员不能为 0。</span><span class="sxs-lookup"><span data-stu-id="1d28f-109">The **cValues** member for the property tag array cannot be 0.</span></span> <span data-ttu-id="1d28f-110">如果_lppPropTags_上输入, 的有效指针**GetNamesFromIDs**返回包含数组中每个属性标识符的名称。</span><span class="sxs-lookup"><span data-stu-id="1d28f-110">If  _lppPropTags_ is a valid pointer on input, **GetNamesFromIDs** returns names for each property identifier included in the array.</span></span> 
    
 <span data-ttu-id="1d28f-111">_lpPropSetGuid_</span><span class="sxs-lookup"><span data-stu-id="1d28f-111">_lpPropSetGuid_</span></span>
  
> <span data-ttu-id="1d28f-112">[in]指向的 GUID 或[GUID](guid.md)的结构，标识属性集。</span><span class="sxs-lookup"><span data-stu-id="1d28f-112">[in] A pointer to a GUID, or [GUID](guid.md) structure, that identifies a property set.</span></span> <span data-ttu-id="1d28f-113">_LpPropSetGuid_参数可以指向有效的属性集，也可以是 NULL。</span><span class="sxs-lookup"><span data-stu-id="1d28f-113">The  _lpPropSetGuid_ parameter can point to a valid property set or can be NULL.</span></span> 
    
 <span data-ttu-id="1d28f-114">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="1d28f-114">_ulFlags_</span></span>
  
> <span data-ttu-id="1d28f-115">[in]位掩码的标志，指示要返回的名称的类型。</span><span class="sxs-lookup"><span data-stu-id="1d28f-115">[in] A bitmask of flags that indicates the type of names to be returned.</span></span> <span data-ttu-id="1d28f-116">可使用以下标志 （如果设置两个标志，没有将返回名称）：</span><span class="sxs-lookup"><span data-stu-id="1d28f-116">The following flags can be used (if both flags are set, no names will be returned):</span></span>
    
<span data-ttu-id="1d28f-117">MAPI_NO_IDS</span><span class="sxs-lookup"><span data-stu-id="1d28f-117">MAPI_NO_IDS</span></span> 
  
> <span data-ttu-id="1d28f-118">返回仅存储为 Unicode 字符串的名称的请求。</span><span class="sxs-lookup"><span data-stu-id="1d28f-118">Requests that only names stored as Unicode strings be returned.</span></span> 
    
<span data-ttu-id="1d28f-119">MAPI_NO_STRINGS</span><span class="sxs-lookup"><span data-stu-id="1d28f-119">MAPI_NO_STRINGS</span></span> 
  
> <span data-ttu-id="1d28f-120">返回仅存储为数字标识符的名称的请求。</span><span class="sxs-lookup"><span data-stu-id="1d28f-120">Requests that only names stored as numeric identifiers be returned.</span></span> 
    
 <span data-ttu-id="1d28f-121">_lpcPropNames_</span><span class="sxs-lookup"><span data-stu-id="1d28f-121">_lpcPropNames_</span></span>
  
> <span data-ttu-id="1d28f-122">[输出]指向数目_lppPropNames_参数指向该数组中的属性名称指针的指针。</span><span class="sxs-lookup"><span data-stu-id="1d28f-122">[out] A pointer to a count of the property name pointers in the array pointed to by the  _lppPropNames_ parameter.</span></span> 
    
 <span data-ttu-id="1d28f-123">_lpppPropNames_</span><span class="sxs-lookup"><span data-stu-id="1d28f-123">_lpppPropNames_</span></span>
  
> <span data-ttu-id="1d28f-124">[输出]指向包含属性名称数组指向[MAPINAMEID](mapinameid.md)结构的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="1d28f-124">[out] A pointer to an array of pointers to [MAPINAMEID](mapinameid.md) structures that contains property names.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="1d28f-125">返回值</span><span class="sxs-lookup"><span data-stu-id="1d28f-125">Return value</span></span>

<span data-ttu-id="1d28f-126">S_OK</span><span class="sxs-lookup"><span data-stu-id="1d28f-126">S_OK</span></span> 
  
> <span data-ttu-id="1d28f-127">已成功返回的属性名称。</span><span class="sxs-lookup"><span data-stu-id="1d28f-127">The property names were successfully returned.</span></span> 
    
<span data-ttu-id="1d28f-128">MAPI_E_NO_SUPPORT</span><span class="sxs-lookup"><span data-stu-id="1d28f-128">MAPI_E_NO_SUPPORT</span></span> 
  
> <span data-ttu-id="1d28f-129">对象不支持命名的属性。</span><span class="sxs-lookup"><span data-stu-id="1d28f-129">The object does not support named properties.</span></span> 
    
<span data-ttu-id="1d28f-130">MAPI_W_ERRORS_RETURNED</span><span class="sxs-lookup"><span data-stu-id="1d28f-130">MAPI_W_ERRORS_RETURNED</span></span> 
  
> <span data-ttu-id="1d28f-131">调用成功总体上讲，但不是会返回一个或多个属性的名称。</span><span class="sxs-lookup"><span data-stu-id="1d28f-131">The call succeeded overall, but names for one or more properties could not be returned.</span></span> <span data-ttu-id="1d28f-132">属性标记为失败属性有**PT_ERROR**属性类型。</span><span class="sxs-lookup"><span data-stu-id="1d28f-132">The property tags for the failing properties have a property type of **PT_ERROR**.</span></span> <span data-ttu-id="1d28f-133">返回此警告时，应处理呼叫为成功。</span><span class="sxs-lookup"><span data-stu-id="1d28f-133">When this warning is returned, the call should be handled as successful.</span></span> <span data-ttu-id="1d28f-134">若要测试此警告，请使用**HR_FAILED**宏。</span><span class="sxs-lookup"><span data-stu-id="1d28f-134">To test for this warning, use the **HR_FAILED** macro.</span></span> <span data-ttu-id="1d28f-135">有关详细信息，请参阅[使用宏的错误处理](using-macros-for-error-handling.md)。</span><span class="sxs-lookup"><span data-stu-id="1d28f-135">For more information, see [Using Macros for Error Handling](using-macros-for-error-handling.md).</span></span> 
    
<span data-ttu-id="1d28f-136">MAPI_E_INVALID_PARAMETER</span><span class="sxs-lookup"><span data-stu-id="1d28f-136">MAPI_E_INVALID_PARAMETER</span></span> 
  
> <span data-ttu-id="1d28f-137">一个或多个所指的_lppPropTags_属性标记数组中的条目的**cValues**成员设置为 0。</span><span class="sxs-lookup"><span data-stu-id="1d28f-137">The **cValues** member of one or more of the entries in the property tag array pointed to by  _lppPropTags_ is set to 0.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="1d28f-138">注解</span><span class="sxs-lookup"><span data-stu-id="1d28f-138">Remarks</span></span>

<span data-ttu-id="1d28f-139">按属性标识符对大多数属性的访问时，可以通过名称访问某些属性。</span><span class="sxs-lookup"><span data-stu-id="1d28f-139">While access to most properties is by property identifier, some properties can be accessed by name.</span></span> <span data-ttu-id="1d28f-140">**IMAPIProp::GetNamesFromIDs**方法可调用它以执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="1d28f-140">The **IMAPIProp::GetNamesFromIDs** method can be called to do the following:</span></span> 
  
- <span data-ttu-id="1d28f-141">检索特定的属性集内的特定属性标识符的名称。</span><span class="sxs-lookup"><span data-stu-id="1d28f-141">Retrieve names for specific property identifiers in a specific property set.</span></span>
    
- <span data-ttu-id="1d28f-142">检索设置的任何属性中的特定属性标识符的名称。</span><span class="sxs-lookup"><span data-stu-id="1d28f-142">Retrieve names for specific property identifiers in any property set.</span></span>
    
- <span data-ttu-id="1d28f-143">检索的对象映射中包含的所有命名属性的名称。</span><span class="sxs-lookup"><span data-stu-id="1d28f-143">Retrieve names for all named properties that are included in the object's mapping.</span></span>
    
<span data-ttu-id="1d28f-144">如果具有一个或多个属性标识符的有效属性标记数组的_lppPropTags_指向和_lpPropSetGuid_指向有效属性设置， **GetNamesFromIDs**忽略属性集和属性类型，并返回的所有名称映射到指定的标识符。</span><span class="sxs-lookup"><span data-stu-id="1d28f-144">If  _lppPropTags_ points to a valid property tag array with one or more property identifiers, and  _lpPropSetGuid_ points to a valid property set, **GetNamesFromIDs** ignores the property set and the property types and returns all of the names that map to the specified identifiers.</span></span> 
  
<span data-ttu-id="1d28f-145">如果_lppPropTags_指向与一个或多个属性标识符和_lpPropSetGuid_有效属性标记数组为 NULL， **GetNamesFromIDs**返回所有将映射到指定标识符的名称。</span><span class="sxs-lookup"><span data-stu-id="1d28f-145">If  _lppPropTags_ points to a valid property tag array with one or more property identifiers and  _lpPropSetGuid_ is NULL, **GetNamesFromIDs** returns all of the names that map to the specified identifiers.</span></span> 
  
<span data-ttu-id="1d28f-146">如果指定的标识符不具有一个名称， **GetNamesFromIDs** _lpppPropNames_中返回的结构中的该标识符就地返回 NULL，并返回 MAPI_W_ERRORS_RETURNED。</span><span class="sxs-lookup"><span data-stu-id="1d28f-146">If a specified identifier does not have a name, **GetNamesFromIDs** returns NULL in that identifier's place in the structure returned in  _lpppPropNames_ and also returns MAPI_W_ERRORS_RETURNED.</span></span> 
  
<span data-ttu-id="1d28f-147">如果_lpPropSetGuid_和_lppPropTags_均为空， **GetNamesFromIDs**分配新的属性标记数组，并返回所有的所有对象的命名属性的名称。</span><span class="sxs-lookup"><span data-stu-id="1d28f-147">If both  _lpPropSetGuid_ and  _lppPropTags_ are NULL, **GetNamesFromIDs** allocates a new property tag array and returns all of the names for all of the named properties for the object.</span></span> 
  
<span data-ttu-id="1d28f-148">当没有要返回的名称时，可能是因为请求的属性集合中没有任何属性或由标志，排除类型的所有属性都**GetNamesFromIDs**执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="1d28f-148">When there are no names to be returned, perhaps because there are no properties in the requested property set or all of the properties are of a type excluded by the flags, **GetNamesFromIDs** does the following:</span></span> 
  
- <span data-ttu-id="1d28f-149">返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="1d28f-149">Returns S_OK.</span></span>
    
- <span data-ttu-id="1d28f-150">分配新的**SPropTagArray**结构，并将**cValues**成员设置为 0。</span><span class="sxs-lookup"><span data-stu-id="1d28f-150">Allocates a new **SPropTagArray** structure, setting the **cValues** member to 0.</span></span> 
    
- <span data-ttu-id="1d28f-151">将_lpcPropNames_的内容设置为 0。</span><span class="sxs-lookup"><span data-stu-id="1d28f-151">Sets the contents of  _lpcPropNames_ to 0.</span></span> 
    
- <span data-ttu-id="1d28f-152">将_lpppPropNames_的内容设置为 NULL。</span><span class="sxs-lookup"><span data-stu-id="1d28f-152">Sets the contents of  _lpppPropNames_ to NULL.</span></span> 
    
## <a name="notes-to-implementers"></a><span data-ttu-id="1d28f-153">针对实施者的注释</span><span class="sxs-lookup"><span data-stu-id="1d28f-153">Notes to implementers</span></span>

<span data-ttu-id="1d28f-154">如果_lpPropSetGuid_指向有效的属性集和_lppPropTags_为 NULL，则结果是未定义。</span><span class="sxs-lookup"><span data-stu-id="1d28f-154">If  _lpPropSetGuid_ points to a valid property set and  _lppPropTags_ is NULL, the result is undefined.</span></span> <span data-ttu-id="1d28f-155">您可以使用以下策略之一：</span><span class="sxs-lookup"><span data-stu-id="1d28f-155">You can use one of the following strategies:</span></span> 
  
- <span data-ttu-id="1d28f-156">忽略属性集，该属性标记数组中返回标识符的名称。</span><span class="sxs-lookup"><span data-stu-id="1d28f-156">Ignore the property set and return the names for the identifiers in the property tag array.</span></span>
    
- <span data-ttu-id="1d28f-157">属于指定的属性集属性标记数组中返回仅的标识符的名称。</span><span class="sxs-lookup"><span data-stu-id="1d28f-157">Return the names for only the identifiers in the property tag array that belong to the specified property set.</span></span>
    
- <span data-ttu-id="1d28f-158">呼叫，返回 MAPI_E_INVALID_PARAMETER 将失败。</span><span class="sxs-lookup"><span data-stu-id="1d28f-158">Fail the call, returning MAPI_E_INVALID_PARAMETER.</span></span> 
    
## <a name="notes-to-callers"></a><span data-ttu-id="1d28f-159">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="1d28f-159">Notes to callers</span></span>

<span data-ttu-id="1d28f-160">若要检索所有对象的命名属性，必须首先调用该对象的[IMAPIProp::GetPropList](imapiprop-getproplist.md)方法，然后传递到**GetNamesFromIDs**0x8000 范围之上的返回的标识符。</span><span class="sxs-lookup"><span data-stu-id="1d28f-160">To retrieve all of the named properties for an object, you must first call the object's [IMAPIProp::GetPropList](imapiprop-getproplist.md) method and then pass the returned identifiers that are above the 0x8000 range to **GetNamesFromIDs**.</span></span>
  
<span data-ttu-id="1d28f-161">如果传递有效的属性集，而不是有效属性标记数组，准备无法预料的结果。</span><span class="sxs-lookup"><span data-stu-id="1d28f-161">If you pass a valid property set but not a valid property tag array, be prepared for unpredictable results.</span></span> <span data-ttu-id="1d28f-162">**GetNamesFromIDs**某些实现忽略属性集，该属性标记数组中返回标识符的名称。</span><span class="sxs-lookup"><span data-stu-id="1d28f-162">Some implementations of **GetNamesFromIDs** ignore the property set and return the names for the identifiers in the property tag array.</span></span> <span data-ttu-id="1d28f-163">某些实现返回 MAPI_E_INVALID_PARAMETER。</span><span class="sxs-lookup"><span data-stu-id="1d28f-163">Some implementations return MAPI_E_INVALID_PARAMETER.</span></span> <span data-ttu-id="1d28f-164">仍其他实现设置的属性中返回的所有属性的标识符的名称。</span><span class="sxs-lookup"><span data-stu-id="1d28f-164">Still other implementations return names for identifiers of all properties in the property set.</span></span> <span data-ttu-id="1d28f-165">如果属性集，PS_PUBLIC_STRINGS **GetNamesFromIDs**可以返回已创建的所有名称。</span><span class="sxs-lookup"><span data-stu-id="1d28f-165">If the property set is PS_PUBLIC_STRINGS, **GetNamesFromIDs** can return all names that were ever created.</span></span> <span data-ttu-id="1d28f-166">服务提供商是否存储在与公共字符串关联的标识符的属性并不重要。</span><span class="sxs-lookup"><span data-stu-id="1d28f-166">Whether the service provider stores a property under the identifiers associated with the public strings is immaterial.</span></span> 
  
<span data-ttu-id="1d28f-167">完后，属性名称，则检查_lpcPropNames_参数，以确定是否返回任何名称的内容。</span><span class="sxs-lookup"><span data-stu-id="1d28f-167">When you are finished with the property names, check the contents of the  _lpcPropNames_ parameter to determine whether any names were returned.</span></span> <span data-ttu-id="1d28f-168">如果是这样，呼叫[MAPIFreeBuffer](mapifreebuffer.md)函数以释放内存指向_lppPropTags_和_lpppPropNames_时返回一个成功的结果。</span><span class="sxs-lookup"><span data-stu-id="1d28f-168">If so, call the [MAPIFreeBuffer](mapifreebuffer.md) function to free the memory pointed to by  _lppPropTags_ and  _lpppPropNames_ when a successful result is returned.</span></span> <span data-ttu-id="1d28f-169">一次调用**MAPIFreeBuffer**就足以为每个参数;您不必遍历的指针数组和单独释放每个**MAPINAMEID**结构。</span><span class="sxs-lookup"><span data-stu-id="1d28f-169">One call to **MAPIFreeBuffer** is sufficient for each parameter; you do not have to traverse the array of pointers and free each **MAPINAMEID** structure individually.</span></span> 
  
<span data-ttu-id="1d28f-170">有关命名属性的详细信息，请参阅[MAPI 命名属性](mapi-named-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="1d28f-170">For more information about named properties, see [MAPI Named Properties](mapi-named-properties.md).</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="1d28f-171">MFCMAPI 参考 （英文）</span><span class="sxs-lookup"><span data-stu-id="1d28f-171">MFCMAPI reference</span></span>

<span data-ttu-id="1d28f-172">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="1d28f-172">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="1d28f-173">**文件**</span><span class="sxs-lookup"><span data-stu-id="1d28f-173">**File**</span></span>|<span data-ttu-id="1d28f-174">**函数**</span><span class="sxs-lookup"><span data-stu-id="1d28f-174">**Function**</span></span>|<span data-ttu-id="1d28f-175">**Comment**</span><span class="sxs-lookup"><span data-stu-id="1d28f-175">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="1d28f-176">SingleMAPIPropListCtrl.cpp</span><span class="sxs-lookup"><span data-stu-id="1d28f-176">SingleMAPIPropListCtrl.cpp</span></span>  <br/> |<span data-ttu-id="1d28f-177">CSingleMAPIPropListCtrl::FindAllNamedProps</span><span class="sxs-lookup"><span data-stu-id="1d28f-177">CSingleMAPIPropListCtrl::FindAllNamedProps</span></span>  <br/> |<span data-ttu-id="1d28f-178">MFCMAPI 使用**IMAPIProp::GetNamesFromIDs**方法查找以前未映射的命名属性。</span><span class="sxs-lookup"><span data-stu-id="1d28f-178">MFCMAPI uses the **IMAPIProp::GetNamesFromIDs** method to look up named properties that have previously been mapped.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="1d28f-179">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1d28f-179">See also</span></span>



[<span data-ttu-id="1d28f-180">GUID</span><span class="sxs-lookup"><span data-stu-id="1d28f-180">GUID</span></span>](guid.md)
  
[<span data-ttu-id="1d28f-181">IMAPIProp::GetIDsFromNames</span><span class="sxs-lookup"><span data-stu-id="1d28f-181">IMAPIProp::GetIDsFromNames</span></span>](imapiprop-getidsfromnames.md)
  
[<span data-ttu-id="1d28f-182">IMAPIProp::GetPropList</span><span class="sxs-lookup"><span data-stu-id="1d28f-182">IMAPIProp::GetPropList</span></span>](imapiprop-getproplist.md)
  
[<span data-ttu-id="1d28f-183">MAPIFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="1d28f-183">MAPIFreeBuffer</span></span>](mapifreebuffer.md)
  
[<span data-ttu-id="1d28f-184">MAPINAMEID</span><span class="sxs-lookup"><span data-stu-id="1d28f-184">MAPINAMEID</span></span>](mapinameid.md)
  
[<span data-ttu-id="1d28f-185">SPropTagArray</span><span class="sxs-lookup"><span data-stu-id="1d28f-185">SPropTagArray</span></span>](sproptagarray.md)
  
[<span data-ttu-id="1d28f-186">IMAPIProp : IUnknown</span><span class="sxs-lookup"><span data-stu-id="1d28f-186">IMAPIProp : IUnknown</span></span>](imapipropiunknown.md)


[<span data-ttu-id="1d28f-187">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="1d28f-187">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)
  
[<span data-ttu-id="1d28f-188">MAPI 命名属性</span><span class="sxs-lookup"><span data-stu-id="1d28f-188">MAPI Named Properties</span></span>](mapi-named-properties.md)
  
[<span data-ttu-id="1d28f-189">使用宏进行错误处理</span><span class="sxs-lookup"><span data-stu-id="1d28f-189">Using Macros for Error Handling</span></span>](using-macros-for-error-handling.md)

