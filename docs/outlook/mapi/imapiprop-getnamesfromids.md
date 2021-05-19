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
ms.openlocfilehash: f6688afde9b36a7722eaaf768f091481c15b7308
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33423571"
---
# <a name="imapipropgetnamesfromids"></a><span data-ttu-id="aa554-103">IMAPIProp::GetNamesFromIDs</span><span class="sxs-lookup"><span data-stu-id="aa554-103">IMAPIProp::GetNamesFromIDs</span></span>

  
  
<span data-ttu-id="aa554-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="aa554-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="aa554-105">提供对应于一个或多个属性标识符的属性名称。</span><span class="sxs-lookup"><span data-stu-id="aa554-105">Provides the property names that correspond to one or more property identifiers.</span></span>
  
```cpp
HRESULT GetNamesFromIDs(
  LPSPropTagArray FAR * lppPropTags,
  LPGUID lpPropSetGuid,
  ULONG ulFlags,
  ULONG FAR * lpcPropNames,
  LPMAPINAMEID FAR * FAR * lpppPropNames
);
```

## <a name="parameters"></a><span data-ttu-id="aa554-106">参数</span><span class="sxs-lookup"><span data-stu-id="aa554-106">Parameters</span></span>

 <span data-ttu-id="aa554-107">_lppPropTags_</span><span class="sxs-lookup"><span data-stu-id="aa554-107">_lppPropTags_</span></span>
  
> <span data-ttu-id="aa554-108">[in， out]在输入时，指向包含属性标记数组 [的 SPropTagArray](sproptagarray.md) 结构的指针;否则为 NULL，指示应返回所有名称。</span><span class="sxs-lookup"><span data-stu-id="aa554-108">[in, out] On input, a pointer to an [SPropTagArray](sproptagarray.md) structure that contains an array of property tags; otherwise, NULL, indicating that all names should be returned.</span></span> <span data-ttu-id="aa554-109">属性标记数组的 **cValues** 成员不能为 0。</span><span class="sxs-lookup"><span data-stu-id="aa554-109">The **cValues** member for the property tag array cannot be 0.</span></span> <span data-ttu-id="aa554-110">如果  _lppPropTags_ 是输入上的有效指针 **，GetNamesFromIDs** 将返回数组中包含的每个属性标识符的名称。</span><span class="sxs-lookup"><span data-stu-id="aa554-110">If  _lppPropTags_ is a valid pointer on input, **GetNamesFromIDs** returns names for each property identifier included in the array.</span></span> 
    
 <span data-ttu-id="aa554-111">_lpPropSetGuid_</span><span class="sxs-lookup"><span data-stu-id="aa554-111">_lpPropSetGuid_</span></span>
  
> <span data-ttu-id="aa554-112">[in]指向标识属性集的 GUID 或 [GUID](guid.md) 结构的指针。</span><span class="sxs-lookup"><span data-stu-id="aa554-112">[in] A pointer to a GUID, or [GUID](guid.md) structure, that identifies a property set.</span></span> <span data-ttu-id="aa554-113">_lpPropSetGuid_ 参数可以指向有效的属性集，也可以为 NULL。</span><span class="sxs-lookup"><span data-stu-id="aa554-113">The  _lpPropSetGuid_ parameter can point to a valid property set or can be NULL.</span></span> 
    
 <span data-ttu-id="aa554-114">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="aa554-114">_ulFlags_</span></span>
  
> <span data-ttu-id="aa554-115">[in]指示要返回的名称类型的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="aa554-115">[in] A bitmask of flags that indicates the type of names to be returned.</span></span> <span data-ttu-id="aa554-116">如果设置了这两个标志 (，则系统不会返回任何名称，) ：</span><span class="sxs-lookup"><span data-stu-id="aa554-116">The following flags can be used (if both flags are set, no names will be returned):</span></span>
    
<span data-ttu-id="aa554-117">MAPI_NO_IDS</span><span class="sxs-lookup"><span data-stu-id="aa554-117">MAPI_NO_IDS</span></span> 
  
> <span data-ttu-id="aa554-118">仅返回存储为 Unicode 字符串的名称的请求。</span><span class="sxs-lookup"><span data-stu-id="aa554-118">Requests that only names stored as Unicode strings be returned.</span></span> 
    
<span data-ttu-id="aa554-119">MAPI_NO_STRINGS</span><span class="sxs-lookup"><span data-stu-id="aa554-119">MAPI_NO_STRINGS</span></span> 
  
> <span data-ttu-id="aa554-120">仅返回存储为数字标识符的名称的请求。</span><span class="sxs-lookup"><span data-stu-id="aa554-120">Requests that only names stored as numeric identifiers be returned.</span></span> 
    
 <span data-ttu-id="aa554-121">_lpcPropNames_</span><span class="sxs-lookup"><span data-stu-id="aa554-121">_lpcPropNames_</span></span>
  
> <span data-ttu-id="aa554-122">[out]指向  _lppPropNames_ 参数指向的数组中的属性名称指针计数的指针。</span><span class="sxs-lookup"><span data-stu-id="aa554-122">[out] A pointer to a count of the property name pointers in the array pointed to by the  _lppPropNames_ parameter.</span></span> 
    
 <span data-ttu-id="aa554-123">_lpppPropNames_</span><span class="sxs-lookup"><span data-stu-id="aa554-123">_lpppPropNames_</span></span>
  
> <span data-ttu-id="aa554-124">[out]指向指向包含属性名称 [的 MAPINAMEID](mapinameid.md) 结构的指针数组的指针。</span><span class="sxs-lookup"><span data-stu-id="aa554-124">[out] A pointer to an array of pointers to [MAPINAMEID](mapinameid.md) structures that contains property names.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="aa554-125">返回值</span><span class="sxs-lookup"><span data-stu-id="aa554-125">Return value</span></span>

<span data-ttu-id="aa554-126">S_OK</span><span class="sxs-lookup"><span data-stu-id="aa554-126">S_OK</span></span> 
  
> <span data-ttu-id="aa554-127">属性名称已成功返回。</span><span class="sxs-lookup"><span data-stu-id="aa554-127">The property names were successfully returned.</span></span> 
    
<span data-ttu-id="aa554-128">MAPI_E_NO_SUPPORT</span><span class="sxs-lookup"><span data-stu-id="aa554-128">MAPI_E_NO_SUPPORT</span></span> 
  
> <span data-ttu-id="aa554-129">对象不支持命名属性。</span><span class="sxs-lookup"><span data-stu-id="aa554-129">The object does not support named properties.</span></span> 
    
<span data-ttu-id="aa554-130">MAPI_W_ERRORS_RETURNED</span><span class="sxs-lookup"><span data-stu-id="aa554-130">MAPI_W_ERRORS_RETURNED</span></span> 
  
> <span data-ttu-id="aa554-131">调用整体成功，但无法返回一个或多个属性的名称。</span><span class="sxs-lookup"><span data-stu-id="aa554-131">The call succeeded overall, but names for one or more properties could not be returned.</span></span> <span data-ttu-id="aa554-132">失败属性的属性标记的属性类型为 **PT_ERROR**。</span><span class="sxs-lookup"><span data-stu-id="aa554-132">The property tags for the failing properties have a property type of **PT_ERROR**.</span></span> <span data-ttu-id="aa554-133">返回此警告时，应成功处理呼叫。</span><span class="sxs-lookup"><span data-stu-id="aa554-133">When this warning is returned, the call should be handled as successful.</span></span> <span data-ttu-id="aa554-134">若要测试此警告，请使用 **HR_FAILED** 宏。</span><span class="sxs-lookup"><span data-stu-id="aa554-134">To test for this warning, use the **HR_FAILED** macro.</span></span> <span data-ttu-id="aa554-135">有关详细信息，请参阅使用 [宏处理错误](using-macros-for-error-handling.md)。</span><span class="sxs-lookup"><span data-stu-id="aa554-135">For more information, see [Using Macros for Error Handling](using-macros-for-error-handling.md).</span></span> 
    
<span data-ttu-id="aa554-136">MAPI_E_INVALID_PARAMETER</span><span class="sxs-lookup"><span data-stu-id="aa554-136">MAPI_E_INVALID_PARAMETER</span></span> 
  
> <span data-ttu-id="aa554-137">_lppPropTags_ 指向的属性标记数组中一个或多个条目的 **cValues** 成员设置为 0。</span><span class="sxs-lookup"><span data-stu-id="aa554-137">The **cValues** member of one or more of the entries in the property tag array pointed to by  _lppPropTags_ is set to 0.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="aa554-138">备注</span><span class="sxs-lookup"><span data-stu-id="aa554-138">Remarks</span></span>

<span data-ttu-id="aa554-139">虽然通过属性标识符访问大多数属性，但某些属性可以通过名称访问。</span><span class="sxs-lookup"><span data-stu-id="aa554-139">While access to most properties is by property identifier, some properties can be accessed by name.</span></span> <span data-ttu-id="aa554-140">可以 **调用 IMAPIProp：：GetNamesFromIDs** 方法来执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="aa554-140">The **IMAPIProp::GetNamesFromIDs** method can be called to do the following:</span></span> 
  
- <span data-ttu-id="aa554-141">检索特定属性集内特定属性标识符的名称。</span><span class="sxs-lookup"><span data-stu-id="aa554-141">Retrieve names for specific property identifiers in a specific property set.</span></span>
    
- <span data-ttu-id="aa554-142">检索任何属性集内特定属性标识符的名称。</span><span class="sxs-lookup"><span data-stu-id="aa554-142">Retrieve names for specific property identifiers in any property set.</span></span>
    
- <span data-ttu-id="aa554-143">检索对象映射中包含的所有命名属性的名称。</span><span class="sxs-lookup"><span data-stu-id="aa554-143">Retrieve names for all named properties that are included in the object's mapping.</span></span>
    
<span data-ttu-id="aa554-144">如果  _lppPropTags_ 指向具有一个或多个属性标识符的有效属性标记数组，  _并且 lpPropSetGuid_ 指向有效的属性集，则 **GetNamesFromIDs** 将忽略属性集和属性类型，并返回映射到指定标识符的所有名称。</span><span class="sxs-lookup"><span data-stu-id="aa554-144">If  _lppPropTags_ points to a valid property tag array with one or more property identifiers, and  _lpPropSetGuid_ points to a valid property set, **GetNamesFromIDs** ignores the property set and the property types and returns all of the names that map to the specified identifiers.</span></span> 
  
<span data-ttu-id="aa554-145">如果  _lppPropTags_ 指向具有一个或多个属性标识符的有效属性标记数组，并且  _lpPropSetGuid_ 为 NULL， **则 GetNamesFromIDs** 将返回映射到指定标识符的所有名称。</span><span class="sxs-lookup"><span data-stu-id="aa554-145">If  _lppPropTags_ points to a valid property tag array with one or more property identifiers and  _lpPropSetGuid_ is NULL, **GetNamesFromIDs** returns all of the names that map to the specified identifiers.</span></span> 
  
<span data-ttu-id="aa554-146">如果指定的标识符没有名称 **，GetNamesFromIDs** 将返回 NULL，该标识符的位置在  _lpppPropNames_ 中返回的结构中，并返回MAPI_W_ERRORS_RETURNED。</span><span class="sxs-lookup"><span data-stu-id="aa554-146">If a specified identifier does not have a name, **GetNamesFromIDs** returns NULL in that identifier's place in the structure returned in  _lpppPropNames_ and also returns MAPI_W_ERRORS_RETURNED.</span></span> 
  
<span data-ttu-id="aa554-147">如果  _lpPropSetGuid_ 和  _lppPropTags_ 都为 NULL， **则 GetNamesFromIDs** 将分配一个新的属性标记数组，并返回对象的所有命名属性的所有名称。</span><span class="sxs-lookup"><span data-stu-id="aa554-147">If both  _lpPropSetGuid_ and  _lppPropTags_ are NULL, **GetNamesFromIDs** allocates a new property tag array and returns all of the names for all of the named properties for the object.</span></span> 
  
<span data-ttu-id="aa554-148">如果没有要返回的名称，可能是因为请求的属性集没有属性，或者所有属性的类型都由标志排除 **，GetNamesFromIDs** 将执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="aa554-148">When there are no names to be returned, perhaps because there are no properties in the requested property set or all of the properties are of a type excluded by the flags, **GetNamesFromIDs** does the following:</span></span> 
  
- <span data-ttu-id="aa554-149">返回S_OK。</span><span class="sxs-lookup"><span data-stu-id="aa554-149">Returns S_OK.</span></span>
    
- <span data-ttu-id="aa554-150">分配新的 **SPropTagArray** 结构，将 **cValues** 成员设置为 0。</span><span class="sxs-lookup"><span data-stu-id="aa554-150">Allocates a new **SPropTagArray** structure, setting the **cValues** member to 0.</span></span> 
    
- <span data-ttu-id="aa554-151">将  _lpcPropNames 的内容设置_ 为 0。</span><span class="sxs-lookup"><span data-stu-id="aa554-151">Sets the contents of  _lpcPropNames_ to 0.</span></span> 
    
- <span data-ttu-id="aa554-152">将  _lpppPropNames 的内容设置_ 为 NULL。</span><span class="sxs-lookup"><span data-stu-id="aa554-152">Sets the contents of  _lpppPropNames_ to NULL.</span></span> 
    
## <a name="notes-to-implementers"></a><span data-ttu-id="aa554-153">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="aa554-153">Notes to implementers</span></span>

<span data-ttu-id="aa554-154">如果  _lpPropSetGuid_ 指向有效的属性集，  _而 lppPropTags_ 为 NULL，则结果为 undefined。</span><span class="sxs-lookup"><span data-stu-id="aa554-154">If  _lpPropSetGuid_ points to a valid property set and  _lppPropTags_ is NULL, the result is undefined.</span></span> <span data-ttu-id="aa554-155">可以使用以下策略之一：</span><span class="sxs-lookup"><span data-stu-id="aa554-155">You can use one of the following strategies:</span></span> 
  
- <span data-ttu-id="aa554-156">忽略属性集并返回属性标记数组中标识符的名称。</span><span class="sxs-lookup"><span data-stu-id="aa554-156">Ignore the property set and return the names for the identifiers in the property tag array.</span></span>
    
- <span data-ttu-id="aa554-157">仅返回属于指定属性集的属性标记数组中的标识符的名称。</span><span class="sxs-lookup"><span data-stu-id="aa554-157">Return the names for only the identifiers in the property tag array that belong to the specified property set.</span></span>
    
- <span data-ttu-id="aa554-158">呼叫失败，返回MAPI_E_INVALID_PARAMETER。</span><span class="sxs-lookup"><span data-stu-id="aa554-158">Fail the call, returning MAPI_E_INVALID_PARAMETER.</span></span> 
    
## <a name="notes-to-callers"></a><span data-ttu-id="aa554-159">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="aa554-159">Notes to callers</span></span>

<span data-ttu-id="aa554-160">若要检索对象的所有命名属性，必须先调用对象的 [IMAPIProp：：GetPropList](imapiprop-getproplist.md) 方法，然后将 0x8000 范围之上的返回标识符传递到 **GetNamesFromIDs**。</span><span class="sxs-lookup"><span data-stu-id="aa554-160">To retrieve all of the named properties for an object, you must first call the object's [IMAPIProp::GetPropList](imapiprop-getproplist.md) method and then pass the returned identifiers that are above the 0x8000 range to **GetNamesFromIDs**.</span></span>
  
<span data-ttu-id="aa554-161">如果传递的有效属性集不是有效的属性标记数组，请为不可预知的结果做好准备。</span><span class="sxs-lookup"><span data-stu-id="aa554-161">If you pass a valid property set but not a valid property tag array, be prepared for unpredictable results.</span></span> <span data-ttu-id="aa554-162">**GetNamesFromIDs** 的一些实现将忽略属性集，并返回属性标记数组中标识符的名称。</span><span class="sxs-lookup"><span data-stu-id="aa554-162">Some implementations of **GetNamesFromIDs** ignore the property set and return the names for the identifiers in the property tag array.</span></span> <span data-ttu-id="aa554-163">某些实现返回MAPI_E_INVALID_PARAMETER。</span><span class="sxs-lookup"><span data-stu-id="aa554-163">Some implementations return MAPI_E_INVALID_PARAMETER.</span></span> <span data-ttu-id="aa554-164">其他实现返回属性集内所有属性的标识符的名称。</span><span class="sxs-lookup"><span data-stu-id="aa554-164">Still other implementations return names for identifiers of all properties in the property set.</span></span> <span data-ttu-id="aa554-165">如果属性集已 **PS_PUBLIC_STRINGS，GetNamesFromIDs** 可以返回以前创建过的所有名称。</span><span class="sxs-lookup"><span data-stu-id="aa554-165">If the property set is PS_PUBLIC_STRINGS, **GetNamesFromIDs** can return all names that were ever created.</span></span> <span data-ttu-id="aa554-166">服务提供程序是否将属性存储在与公共字符串关联的标识符下并不重要。</span><span class="sxs-lookup"><span data-stu-id="aa554-166">Whether the service provider stores a property under the identifiers associated with the public strings is immaterial.</span></span> 
  
<span data-ttu-id="aa554-167">使用完属性名称后，请检查  _lpcPropNames_ 参数的内容以确定是否返回了任何名称。</span><span class="sxs-lookup"><span data-stu-id="aa554-167">When you are finished with the property names, check the contents of the  _lpcPropNames_ parameter to determine whether any names were returned.</span></span> <span data-ttu-id="aa554-168">如果是这样，请调用 [MAPIFreeBuffer](mapifreebuffer.md) 函数以在返回成功结果时释放  _lppPropTags_ 和  _lpppPropNames_ 指向的内存。</span><span class="sxs-lookup"><span data-stu-id="aa554-168">If so, call the [MAPIFreeBuffer](mapifreebuffer.md) function to free the memory pointed to by  _lppPropTags_ and  _lpppPropNames_ when a successful result is returned.</span></span> <span data-ttu-id="aa554-169">一次 **对 MAPIFreeBuffer** 的调用足以满足每个参数;你不需要遍历指针数组并单独释放每个 **MAPINAMEID** 结构。</span><span class="sxs-lookup"><span data-stu-id="aa554-169">One call to **MAPIFreeBuffer** is sufficient for each parameter; you do not have to traverse the array of pointers and free each **MAPINAMEID** structure individually.</span></span> 
  
<span data-ttu-id="aa554-170">有关命名属性的信息，请参阅 [MAPI Named Properties](mapi-named-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="aa554-170">For more information about named properties, see [MAPI Named Properties](mapi-named-properties.md).</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="aa554-171">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="aa554-171">MFCMAPI reference</span></span>

<span data-ttu-id="aa554-172">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="aa554-172">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="aa554-173">**文件**</span><span class="sxs-lookup"><span data-stu-id="aa554-173">**File**</span></span>|<span data-ttu-id="aa554-174">**函数**</span><span class="sxs-lookup"><span data-stu-id="aa554-174">**Function**</span></span>|<span data-ttu-id="aa554-175">**备注**</span><span class="sxs-lookup"><span data-stu-id="aa554-175">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="aa554-176">SingleMAPIPropListCtrl.cpp</span><span class="sxs-lookup"><span data-stu-id="aa554-176">SingleMAPIPropListCtrl.cpp</span></span>  <br/> |<span data-ttu-id="aa554-177">CSingleMAPIPropListCtrl：：FindAllNamedProps</span><span class="sxs-lookup"><span data-stu-id="aa554-177">CSingleMAPIPropListCtrl::FindAllNamedProps</span></span>  <br/> |<span data-ttu-id="aa554-178">MFCMAPI 使用 **IMAPIProp：：GetNamesFromIDs** 方法来查找之前已映射的命名属性。</span><span class="sxs-lookup"><span data-stu-id="aa554-178">MFCMAPI uses the **IMAPIProp::GetNamesFromIDs** method to look up named properties that have previously been mapped.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="aa554-179">另请参阅</span><span class="sxs-lookup"><span data-stu-id="aa554-179">See also</span></span>



[<span data-ttu-id="aa554-180">GUID</span><span class="sxs-lookup"><span data-stu-id="aa554-180">GUID</span></span>](guid.md)
  
[<span data-ttu-id="aa554-181">IMAPIProp::GetIDsFromNames</span><span class="sxs-lookup"><span data-stu-id="aa554-181">IMAPIProp::GetIDsFromNames</span></span>](imapiprop-getidsfromnames.md)
  
[<span data-ttu-id="aa554-182">IMAPIProp::GetPropList</span><span class="sxs-lookup"><span data-stu-id="aa554-182">IMAPIProp::GetPropList</span></span>](imapiprop-getproplist.md)
  
[<span data-ttu-id="aa554-183">MAPIFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="aa554-183">MAPIFreeBuffer</span></span>](mapifreebuffer.md)
  
[<span data-ttu-id="aa554-184">MAPINAMEID</span><span class="sxs-lookup"><span data-stu-id="aa554-184">MAPINAMEID</span></span>](mapinameid.md)
  
[<span data-ttu-id="aa554-185">SPropTagArray</span><span class="sxs-lookup"><span data-stu-id="aa554-185">SPropTagArray</span></span>](sproptagarray.md)
  
[<span data-ttu-id="aa554-186">IMAPIProp : IUnknown</span><span class="sxs-lookup"><span data-stu-id="aa554-186">IMAPIProp : IUnknown</span></span>](imapipropiunknown.md)


[<span data-ttu-id="aa554-187">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="aa554-187">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)
  
[<span data-ttu-id="aa554-188">MAPI 命名属性</span><span class="sxs-lookup"><span data-stu-id="aa554-188">MAPI Named Properties</span></span>](mapi-named-properties.md)
  
[<span data-ttu-id="aa554-189">使用宏处理错误</span><span class="sxs-lookup"><span data-stu-id="aa554-189">Using Macros for Error Handling</span></span>](using-macros-for-error-handling.md)

