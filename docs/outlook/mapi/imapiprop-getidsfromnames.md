---
title: IMAPIPropGetIDsFromNames
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIProp.GetIDsFromNames
api_type:
- COM
ms.assetid: e3f501a4-a8ee-43d7-bd83-c94e7980c398
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 7f7c243995c633389ab8fa80a26dddd152347276
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22565359"
---
# <a name="imapipropgetidsfromnames"></a><span data-ttu-id="7f4d3-103">IMAPIProp::GetIDsFromNames</span><span class="sxs-lookup"><span data-stu-id="7f4d3-103">IMAPIProp::GetIDsFromNames</span></span>

  
  
<span data-ttu-id="7f4d3-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="7f4d3-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="7f4d3-105">提供属性的标识符的对应于一个或多个属性的名称。</span><span class="sxs-lookup"><span data-stu-id="7f4d3-105">Provides the property identifiers that correspond to one or more property names.</span></span>
  
```cpp
HRESULT GetIDsFromNames(
  ULONG cPropNames,
  LPMAPINAMEID FAR * lppPropNames,
  ULONG ulFlags,
  LPSPropTagArray FAR * lppPropTags
);
```

## <a name="parameters"></a><span data-ttu-id="7f4d3-106">参数</span><span class="sxs-lookup"><span data-stu-id="7f4d3-106">Parameters</span></span>

 <span data-ttu-id="7f4d3-107">_cPropNames_</span><span class="sxs-lookup"><span data-stu-id="7f4d3-107">_cPropNames_</span></span>
  
> <span data-ttu-id="7f4d3-108">[in]_LppPropNames_参数指向的属性名称的计数。</span><span class="sxs-lookup"><span data-stu-id="7f4d3-108">[in] The count of property names pointed to by the  _lppPropNames_ parameter.</span></span> <span data-ttu-id="7f4d3-109">如果_lppPropNames_为 NULL，则_cPropNames_参数必须为 0。</span><span class="sxs-lookup"><span data-stu-id="7f4d3-109">If  _lppPropNames_ is NULL, the  _cPropNames_ parameter must be 0.</span></span> 
    
 <span data-ttu-id="7f4d3-110">_lppPropNames_</span><span class="sxs-lookup"><span data-stu-id="7f4d3-110">_lppPropNames_</span></span>
  
> <span data-ttu-id="7f4d3-111">[in]一个指向数组属性名称，则为 NULL。</span><span class="sxs-lookup"><span data-stu-id="7f4d3-111">[in] A pointer to an array of property names, or NULL.</span></span> <span data-ttu-id="7f4d3-112">传递空请求中所有的属性集有关哪些对象有信息的所有属性名属性标识符。</span><span class="sxs-lookup"><span data-stu-id="7f4d3-112">Passing NULL requests property identifiers for all property names in all property sets about which the object has information.</span></span> <span data-ttu-id="7f4d3-113">如果_ulFlags_参数中设置 MAPI_CREATE 标志， _lppPropNames_参数必须不为 NULL。</span><span class="sxs-lookup"><span data-stu-id="7f4d3-113">The  _lppPropNames_ parameter must not be NULL if the MAPI_CREATE flag is set in the  _ulFlags_ parameter.</span></span> 
    
 <span data-ttu-id="7f4d3-114">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="7f4d3-114">_ulFlags_</span></span>
  
> <span data-ttu-id="7f4d3-115">[in]位掩码的标志，指示应如何返回属性的标识符。</span><span class="sxs-lookup"><span data-stu-id="7f4d3-115">[in] A bitmask of flags that indicates how the property identifiers should be returned.</span></span> <span data-ttu-id="7f4d3-116">可以设置以下标记：</span><span class="sxs-lookup"><span data-stu-id="7f4d3-116">The following flag can be set:</span></span>
    
<span data-ttu-id="7f4d3-117">MAPI_CREATE</span><span class="sxs-lookup"><span data-stu-id="7f4d3-117">MAPI_CREATE</span></span> 
  
> <span data-ttu-id="7f4d3-118">指派属性标识符，如果一个具有尚未分配，到一个或多个所指的_lppPropNames_属性名称数组中包含的名称。</span><span class="sxs-lookup"><span data-stu-id="7f4d3-118">Assigns a property identifier, if one has not yet been assigned, to one or more of the names included in the property name array pointed to by  _lppPropNames_.</span></span> <span data-ttu-id="7f4d3-119">此标志内部注册名称为标识符映射表中的标识符。</span><span class="sxs-lookup"><span data-stu-id="7f4d3-119">This flag internally registers the identifier in the name-to-identifier mapping table.</span></span>
    
 <span data-ttu-id="7f4d3-120">_lppPropTags_</span><span class="sxs-lookup"><span data-stu-id="7f4d3-120">_lppPropTags_</span></span>
  
> <span data-ttu-id="7f4d3-121">[输出]指向为数组属性标记包含现有或新分配属性标识符的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="7f4d3-121">[out] A pointer to a pointer to an array of property tags that contains existing or newly assigned property identifiers.</span></span> <span data-ttu-id="7f4d3-122">在此数组中的属性标记的属性类型设置为**PT_UNSPECIFIED**。</span><span class="sxs-lookup"><span data-stu-id="7f4d3-122">The property types for the property tags in this array are set to **PT_UNSPECIFIED**.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="7f4d3-123">返回值</span><span class="sxs-lookup"><span data-stu-id="7f4d3-123">Return value</span></span>

<span data-ttu-id="7f4d3-124">S_OK</span><span class="sxs-lookup"><span data-stu-id="7f4d3-124">S_OK</span></span> 
  
> <span data-ttu-id="7f4d3-125">已成功返回的指定的属性名称的标识符。</span><span class="sxs-lookup"><span data-stu-id="7f4d3-125">The identifiers for the specified property names were successfully returned.</span></span>
    
<span data-ttu-id="7f4d3-126">MAPI_E_NO_SUPPORT</span><span class="sxs-lookup"><span data-stu-id="7f4d3-126">MAPI_E_NO_SUPPORT</span></span> 
  
> <span data-ttu-id="7f4d3-127">对象不支持命名的属性。</span><span class="sxs-lookup"><span data-stu-id="7f4d3-127">The object does not support named properties.</span></span>
    
<span data-ttu-id="7f4d3-128">MAPI_E_NOT_ENOUGH_MEMORY</span><span class="sxs-lookup"><span data-stu-id="7f4d3-128">MAPI_E_NOT_ENOUGH_MEMORY</span></span> 
  
> <span data-ttu-id="7f4d3-129">内存不足的可用以检索这些标识符。</span><span class="sxs-lookup"><span data-stu-id="7f4d3-129">Insufficient memory was available to retrieve the identifiers.</span></span>
    
<span data-ttu-id="7f4d3-130">MAPI_E_TOO_BIG</span><span class="sxs-lookup"><span data-stu-id="7f4d3-130">MAPI_E_TOO_BIG</span></span> 
  
> <span data-ttu-id="7f4d3-131">无法执行操作，因为它要求要返回的属性标记太多。</span><span class="sxs-lookup"><span data-stu-id="7f4d3-131">The operation cannot be performed because it requires too many property tags to be returned.</span></span>
    
<span data-ttu-id="7f4d3-132">MAPI_W_ERRORS_RETURNED</span><span class="sxs-lookup"><span data-stu-id="7f4d3-132">MAPI_W_ERRORS_RETURNED</span></span> 
  
> <span data-ttu-id="7f4d3-133">调用成功总体上讲，但不是会返回一个或多个属性标识符。</span><span class="sxs-lookup"><span data-stu-id="7f4d3-133">The call succeeded overall, but one or more property identifiers could not be returned.</span></span> <span data-ttu-id="7f4d3-134">不可用的每个属性的相应属性类型设置为**PT_ERROR**和其标识符为零。</span><span class="sxs-lookup"><span data-stu-id="7f4d3-134">The corresponding property type for each unavailable property is set to **PT_ERROR** and its identifier to zero.</span></span> <span data-ttu-id="7f4d3-135">返回此警告时，处理为成功的呼叫。</span><span class="sxs-lookup"><span data-stu-id="7f4d3-135">When this warning is returned, handle the call as successful.</span></span> <span data-ttu-id="7f4d3-136">若要测试此警告，请使用**HR_FAILED**宏。</span><span class="sxs-lookup"><span data-stu-id="7f4d3-136">To test for this warning, use the **HR_FAILED** macro.</span></span> <span data-ttu-id="7f4d3-137">请参阅[使用宏的错误处理](using-macros-for-error-handling.md)。</span><span class="sxs-lookup"><span data-stu-id="7f4d3-137">See [Using Macros for Error Handling](using-macros-for-error-handling.md).</span></span>
    
## <a name="remarks"></a><span data-ttu-id="7f4d3-138">注解</span><span class="sxs-lookup"><span data-stu-id="7f4d3-138">Remarks</span></span>

<span data-ttu-id="7f4d3-139">**IMAPIProp::GetIDsFromNames**方法检索保留一个或多个命名属性的属性标识符的属性标记的数组。</span><span class="sxs-lookup"><span data-stu-id="7f4d3-139">The **IMAPIProp::GetIDsFromNames** method retrieves an array of property tags that hold the property identifiers for one or more named properties.</span></span> <span data-ttu-id="7f4d3-140">**IMAPIProp::GetIDsFromNames**可调用它以执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="7f4d3-140">**IMAPIProp::GetIDsFromNames** can be called to do the following:</span></span> 
  
- <span data-ttu-id="7f4d3-141">创建新的名称标识符。</span><span class="sxs-lookup"><span data-stu-id="7f4d3-141">Create identifiers for new names.</span></span>
    
- <span data-ttu-id="7f4d3-142">检索特定的名称标识符。</span><span class="sxs-lookup"><span data-stu-id="7f4d3-142">Retrieve identifiers for specific names.</span></span>
    
- <span data-ttu-id="7f4d3-143">检索所有命名属性的对象映射中包含的标识符。</span><span class="sxs-lookup"><span data-stu-id="7f4d3-143">Retrieve identifiers for all named properties that are included in the object's mapping.</span></span>
    
<span data-ttu-id="7f4d3-144">命名的属性通常使用文件夹和消息的消息存储提供程序。</span><span class="sxs-lookup"><span data-stu-id="7f4d3-144">Named properties are typically used by message store providers for folders and messages.</span></span> <span data-ttu-id="7f4d3-145">其他对象，如消息用户和配置文件节，可能不支持的关联属性标识符的名称，并可能会返回 MAPI_E_NO_SUPPORT 来自**GetIDsFromNames**。</span><span class="sxs-lookup"><span data-stu-id="7f4d3-145">Other objects, such as messaging users and profile sections, might not support the association of names to property identifiers and might return MAPI_E_NO_SUPPORT from **GetIDsFromNames**.</span></span>
  
<span data-ttu-id="7f4d3-146">如果没有返回特定名称的标识符的错误， **GetIDsFromNames**返回 MAPI_W_ERRORS_RETURNED，并设置对应于**PT_ERROR**和标识符为零的名称属性标记数组项中的属性类型。</span><span class="sxs-lookup"><span data-stu-id="7f4d3-146">If there is an error that returns an identifier for a particular name, **GetIDsFromNames** returns MAPI_W_ERRORS_RETURNED and sets the property type in the property tag array entry that corresponds to the name to **PT_ERROR** and the identifier to zero.</span></span> 
  
<span data-ttu-id="7f4d3-147">由对象的**PR_MAPPING_SIGNATURE** ([PidTagMappingSignature](pidtagmappingsignature-canonical-property.md)) 属性表示名称-标识符映射。</span><span class="sxs-lookup"><span data-stu-id="7f4d3-147">Name-to-identifier mapping is represented by an object's **PR_MAPPING_SIGNATURE** ([PidTagMappingSignature](pidtagmappingsignature-canonical-property.md)) property.</span></span> <span data-ttu-id="7f4d3-148">**PR_MAPPING_SIGNATURE**包含指示服务提供程序负责对象[MAPIUID](mapiuid.md)结构。</span><span class="sxs-lookup"><span data-stu-id="7f4d3-148">**PR_MAPPING_SIGNATURE** contains a [MAPIUID](mapiuid.md) structure that indicates the service provider responsible for the object.</span></span> <span data-ttu-id="7f4d3-149">如果两个对象相同的**PR_MAPPING_SIGNATURE**属性，则假定这些对象使用相同的名称为标识符映射。</span><span class="sxs-lookup"><span data-stu-id="7f4d3-149">If the **PR_MAPPING_SIGNATURE** property is the same for two objects, assume that these objects use the same name-to-identifier mapping.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="7f4d3-150">针对实施者的注释</span><span class="sxs-lookup"><span data-stu-id="7f4d3-150">Notes to implementers</span></span>

<span data-ttu-id="7f4d3-151">返回_lppPropNames_参数指向该属性标记数组中传递的标识符必须 0x8000 到 0xFFFE 范围中。</span><span class="sxs-lookup"><span data-stu-id="7f4d3-151">The identifiers that you pass back in the property tag array pointed to by the  _lppPropNames_ parameter must be in the 0x8000 to 0xFFFE range.</span></span> <span data-ttu-id="7f4d3-152">该数组中的条目必须与属性名称数组中传递的名称相同的顺序指向通过_lppPropNames_。</span><span class="sxs-lookup"><span data-stu-id="7f4d3-152">The entries in this array must be in the same order as the names passed in the property name array pointed to by  _lppPropNames_.</span></span> 
  
<span data-ttu-id="7f4d3-153">如果您支持的容器上的命名的属性，用于您的容器中的所有对象的相同的名称为标识符映射 （也就是说，不要都使用不同映射的每个文件夹中保存邮件或文件夹中的每个邮件）。</span><span class="sxs-lookup"><span data-stu-id="7f4d3-153">If you support named properties on a container, use the same name-to-identifier mapping for all objects in your container (that is, do not use a different mapping for each folder in your message store or each message in your folder).</span></span>
  
## <a name="notes-to-callers"></a><span data-ttu-id="7f4d3-154">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="7f4d3-154">Notes to callers</span></span>

<span data-ttu-id="7f4d3-155">由于所指的_lppPropTags_属性标记数组中返回标识符的属性类型设置为**PT_UNSPECIFIED**，，必须调用[IMAPIProp::SetProps](imapiprop-setprops.md)方法来检索准确的类型。</span><span class="sxs-lookup"><span data-stu-id="7f4d3-155">Because the property types for the returned identifiers in the property tag array pointed to by  _lppPropTags_ are set to **PT_UNSPECIFIED**, you will have to call the [IMAPIProp::SetProps](imapiprop-setprops.md) method to retrieve the accurate types.</span></span> 
  
<span data-ttu-id="7f4d3-156">如果您移动或复制对象命名属性，和源和目标对象具有不同映射签名由其**PR_MAPPING_SIGNATURE**属性的值，您必须在这些操作保留名称。</span><span class="sxs-lookup"><span data-stu-id="7f4d3-156">If you move or copy objects with named properties, and the source and destination objects have different mapping signatures as indicated by the values of their **PR_MAPPING_SIGNATURE** properties, you must preserve the names during these operations.</span></span> <span data-ttu-id="7f4d3-157">若要保留属性名称，请调整相应属性的标识符匹配的目标对象的名称为标识符映射。</span><span class="sxs-lookup"><span data-stu-id="7f4d3-157">To preserve property names, adjust the corresponding property identifiers to match the name-to-identifier mapping of the destination object.</span></span> 
  
<span data-ttu-id="7f4d3-158">某些对象有他们可以命名属性标识符的数限制。</span><span class="sxs-lookup"><span data-stu-id="7f4d3-158">Some objects have a limit as to the number of property identifiers they can name.</span></span> <span data-ttu-id="7f4d3-159">如果调用**GetIDsFromNames**导致超过此限制，则该方法返回 MAPI_E_TOO_BIG。</span><span class="sxs-lookup"><span data-stu-id="7f4d3-159">If a call to **GetIDsFromNames** causes this limit to be exceeded, the method returns MAPI_E_TOO_BIG.</span></span> <span data-ttu-id="7f4d3-160">在这种情况下，查询的标识符。</span><span class="sxs-lookup"><span data-stu-id="7f4d3-160">In this case, query by identifier.</span></span> 
  
<span data-ttu-id="7f4d3-161">有关详细信息，请参阅[MAPI 命名属性](mapi-named-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="7f4d3-161">For more information, see [MAPI Named Properties](mapi-named-properties.md).</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="7f4d3-162">MFCMAPI 参考 （英文）</span><span class="sxs-lookup"><span data-stu-id="7f4d3-162">MFCMAPI reference</span></span>

<span data-ttu-id="7f4d3-163">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="7f4d3-163">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="7f4d3-164">**文件**</span><span class="sxs-lookup"><span data-stu-id="7f4d3-164">**File**</span></span>|<span data-ttu-id="7f4d3-165">**函数**</span><span class="sxs-lookup"><span data-stu-id="7f4d3-165">**Function**</span></span>|<span data-ttu-id="7f4d3-166">**Comment**</span><span class="sxs-lookup"><span data-stu-id="7f4d3-166">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="7f4d3-167">SingleMAPIPropListCtrl.cpp</span><span class="sxs-lookup"><span data-stu-id="7f4d3-167">SingleMAPIPropListCtrl.cpp</span></span>  <br/> |<span data-ttu-id="7f4d3-168">CSingleMAPIPropListCtrl::FindAllNamedPropsUsed</span><span class="sxs-lookup"><span data-stu-id="7f4d3-168">CSingleMAPIPropListCtrl::FindAllNamedPropsUsed</span></span>  <br/> |<span data-ttu-id="7f4d3-169">MFCMAPI 使用**IMAPIProp::GetIDsFromNames**方法获取属性标记为已被映射的所有命名属性。</span><span class="sxs-lookup"><span data-stu-id="7f4d3-169">MFCMAPI uses the **IMAPIProp::GetIDsFromNames** method to obtain property tags for all named properties that have been mapped.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="7f4d3-170">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7f4d3-170">See also</span></span>



[<span data-ttu-id="7f4d3-171">IMAPIProp::GetNamesFromIDs</span><span class="sxs-lookup"><span data-stu-id="7f4d3-171">IMAPIProp::GetNamesFromIDs</span></span>](imapiprop-getnamesfromids.md)
  
[<span data-ttu-id="7f4d3-172">IMAPIProp::SetProps</span><span class="sxs-lookup"><span data-stu-id="7f4d3-172">IMAPIProp::SetProps</span></span>](imapiprop-setprops.md)
  
[<span data-ttu-id="7f4d3-173">MAPINAMEID</span><span class="sxs-lookup"><span data-stu-id="7f4d3-173">MAPINAMEID</span></span>](mapinameid.md)
  
[<span data-ttu-id="7f4d3-174">MAPIUID</span><span class="sxs-lookup"><span data-stu-id="7f4d3-174">MAPIUID</span></span>](mapiuid.md)
  
[<span data-ttu-id="7f4d3-175">IMAPIProp : IUnknown</span><span class="sxs-lookup"><span data-stu-id="7f4d3-175">IMAPIProp : IUnknown</span></span>](imapipropiunknown.md)


[<span data-ttu-id="7f4d3-176">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="7f4d3-176">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)
  
[<span data-ttu-id="7f4d3-177">MAPI 命名属性</span><span class="sxs-lookup"><span data-stu-id="7f4d3-177">MAPI Named Properties</span></span>](mapi-named-properties.md)
  
[<span data-ttu-id="7f4d3-178">使用宏进行错误处理</span><span class="sxs-lookup"><span data-stu-id="7f4d3-178">Using Macros for Error Handling</span></span>](using-macros-for-error-handling.md)

