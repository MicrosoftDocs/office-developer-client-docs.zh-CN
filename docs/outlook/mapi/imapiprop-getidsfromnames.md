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
ms.openlocfilehash: 28880b818bc80e31cae0c695d4aac92eb9555cac
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32314838"
---
# <a name="imapipropgetidsfromnames"></a><span data-ttu-id="ce9d2-103">IMAPIProp::GetIDsFromNames</span><span class="sxs-lookup"><span data-stu-id="ce9d2-103">IMAPIProp::GetIDsFromNames</span></span>

  
  
<span data-ttu-id="ce9d2-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="ce9d2-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="ce9d2-105">提供与一个或多个属性名称对应的属性标识符。</span><span class="sxs-lookup"><span data-stu-id="ce9d2-105">Provides the property identifiers that correspond to one or more property names.</span></span>
  
```cpp
HRESULT GetIDsFromNames(
  ULONG cPropNames,
  LPMAPINAMEID FAR * lppPropNames,
  ULONG ulFlags,
  LPSPropTagArray FAR * lppPropTags
);
```

## <a name="parameters"></a><span data-ttu-id="ce9d2-106">参数</span><span class="sxs-lookup"><span data-stu-id="ce9d2-106">Parameters</span></span>

 <span data-ttu-id="ce9d2-107">_cPropNames_</span><span class="sxs-lookup"><span data-stu-id="ce9d2-107">_cPropNames_</span></span>
  
> <span data-ttu-id="ce9d2-108">实时由_lppPropNames_参数指向的属性名称的计数。</span><span class="sxs-lookup"><span data-stu-id="ce9d2-108">[in] The count of property names pointed to by the  _lppPropNames_ parameter.</span></span> <span data-ttu-id="ce9d2-109">如果_lppPropNames_为 NULL, 则_cPropNames_参数必须为0。</span><span class="sxs-lookup"><span data-stu-id="ce9d2-109">If  _lppPropNames_ is NULL, the  _cPropNames_ parameter must be 0.</span></span> 
    
 <span data-ttu-id="ce9d2-110">_lppPropNames_</span><span class="sxs-lookup"><span data-stu-id="ce9d2-110">_lppPropNames_</span></span>
  
> <span data-ttu-id="ce9d2-111">实时指向属性名称数组的指针或 NULL。</span><span class="sxs-lookup"><span data-stu-id="ce9d2-111">[in] A pointer to an array of property names, or NULL.</span></span> <span data-ttu-id="ce9d2-112">向所有属性集中的所有属性名称传递 NULL 请求属性标识符, 该对象包含的所有属性集的信息。</span><span class="sxs-lookup"><span data-stu-id="ce9d2-112">Passing NULL requests property identifiers for all property names in all property sets about which the object has information.</span></span> <span data-ttu-id="ce9d2-113">如果在_ulFlags_参数中设置了 MAPI_CREATE 标志, 则_lppPropNames_参数不得为 NULL。</span><span class="sxs-lookup"><span data-stu-id="ce9d2-113">The  _lppPropNames_ parameter must not be NULL if the MAPI_CREATE flag is set in the  _ulFlags_ parameter.</span></span> 
    
 <span data-ttu-id="ce9d2-114">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="ce9d2-114">_ulFlags_</span></span>
  
> <span data-ttu-id="ce9d2-115">实时指示应如何返回属性标识符的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="ce9d2-115">[in] A bitmask of flags that indicates how the property identifiers should be returned.</span></span> <span data-ttu-id="ce9d2-116">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="ce9d2-116">The following flag can be set:</span></span>
    
<span data-ttu-id="ce9d2-117">MAPI_CREATE</span><span class="sxs-lookup"><span data-stu-id="ce9d2-117">MAPI_CREATE</span></span> 
  
> <span data-ttu-id="ce9d2-118">如果尚未将属性标识符分配给由_lppPropNames_指向的属性名称数组中包含的一个或多个名称, 则将该标识符分配给它。</span><span class="sxs-lookup"><span data-stu-id="ce9d2-118">Assigns a property identifier, if one has not yet been assigned, to one or more of the names included in the property name array pointed to by  _lppPropNames_.</span></span> <span data-ttu-id="ce9d2-119">此标志在内部注册名称到标识符的映射表中的标识符。</span><span class="sxs-lookup"><span data-stu-id="ce9d2-119">This flag internally registers the identifier in the name-to-identifier mapping table.</span></span>
    
 <span data-ttu-id="ce9d2-120">_lppPropTags_</span><span class="sxs-lookup"><span data-stu-id="ce9d2-120">_lppPropTags_</span></span>
  
> <span data-ttu-id="ce9d2-121">排除指向包含现有或新分配的属性标识符的属性标记数组的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="ce9d2-121">[out] A pointer to a pointer to an array of property tags that contains existing or newly assigned property identifiers.</span></span> <span data-ttu-id="ce9d2-122">此数组中的属性标记的属性类型设置为**PT_UNSPECIFIED**。</span><span class="sxs-lookup"><span data-stu-id="ce9d2-122">The property types for the property tags in this array are set to **PT_UNSPECIFIED**.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="ce9d2-123">返回值</span><span class="sxs-lookup"><span data-stu-id="ce9d2-123">Return value</span></span>

<span data-ttu-id="ce9d2-124">S_OK</span><span class="sxs-lookup"><span data-stu-id="ce9d2-124">S_OK</span></span> 
  
> <span data-ttu-id="ce9d2-125">已成功返回指定属性名称的标识符。</span><span class="sxs-lookup"><span data-stu-id="ce9d2-125">The identifiers for the specified property names were successfully returned.</span></span>
    
<span data-ttu-id="ce9d2-126">MAPI_E_NO_SUPPORT</span><span class="sxs-lookup"><span data-stu-id="ce9d2-126">MAPI_E_NO_SUPPORT</span></span> 
  
> <span data-ttu-id="ce9d2-127">对象不支持命名属性。</span><span class="sxs-lookup"><span data-stu-id="ce9d2-127">The object does not support named properties.</span></span>
    
<span data-ttu-id="ce9d2-128">MAPI_E_NOT_ENOUGH_MEMORY</span><span class="sxs-lookup"><span data-stu-id="ce9d2-128">MAPI_E_NOT_ENOUGH_MEMORY</span></span> 
  
> <span data-ttu-id="ce9d2-129">内存不足, 无法检索标识符。</span><span class="sxs-lookup"><span data-stu-id="ce9d2-129">Insufficient memory was available to retrieve the identifiers.</span></span>
    
<span data-ttu-id="ce9d2-130">MAPI_E_TOO_BIG</span><span class="sxs-lookup"><span data-stu-id="ce9d2-130">MAPI_E_TOO_BIG</span></span> 
  
> <span data-ttu-id="ce9d2-131">无法执行操作, 因为它需要返回过多的属性标记。</span><span class="sxs-lookup"><span data-stu-id="ce9d2-131">The operation cannot be performed because it requires too many property tags to be returned.</span></span>
    
<span data-ttu-id="ce9d2-132">MAPI_W_ERRORS_RETURNED</span><span class="sxs-lookup"><span data-stu-id="ce9d2-132">MAPI_W_ERRORS_RETURNED</span></span> 
  
> <span data-ttu-id="ce9d2-133">调用全部成功, 但无法返回一个或多个属性标识符。</span><span class="sxs-lookup"><span data-stu-id="ce9d2-133">The call succeeded overall, but one or more property identifiers could not be returned.</span></span> <span data-ttu-id="ce9d2-134">每个不可用属性的相应属性类型都设置为**PT_ERROR** , 其标识符设置为零。</span><span class="sxs-lookup"><span data-stu-id="ce9d2-134">The corresponding property type for each unavailable property is set to **PT_ERROR** and its identifier to zero.</span></span> <span data-ttu-id="ce9d2-135">返回此警告时, 请将呼叫处理为成功。</span><span class="sxs-lookup"><span data-stu-id="ce9d2-135">When this warning is returned, handle the call as successful.</span></span> <span data-ttu-id="ce9d2-136">若要测试此警告, 请使用**HR_FAILED**宏。</span><span class="sxs-lookup"><span data-stu-id="ce9d2-136">To test for this warning, use the **HR_FAILED** macro.</span></span> <span data-ttu-id="ce9d2-137">请参阅[使用宏进行错误处理](using-macros-for-error-handling.md)。</span><span class="sxs-lookup"><span data-stu-id="ce9d2-137">See [Using Macros for Error Handling](using-macros-for-error-handling.md).</span></span>
    
## <a name="remarks"></a><span data-ttu-id="ce9d2-138">注解</span><span class="sxs-lookup"><span data-stu-id="ce9d2-138">Remarks</span></span>

<span data-ttu-id="ce9d2-139">**IMAPIProp:: GetIDsFromNames**方法检索包含一个或多个命名属性的属性标识符的属性标记的数组。</span><span class="sxs-lookup"><span data-stu-id="ce9d2-139">The **IMAPIProp::GetIDsFromNames** method retrieves an array of property tags that hold the property identifiers for one or more named properties.</span></span> <span data-ttu-id="ce9d2-140">可以调用**IMAPIProp:: GetIDsFromNames**以执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="ce9d2-140">**IMAPIProp::GetIDsFromNames** can be called to do the following:</span></span> 
  
- <span data-ttu-id="ce9d2-141">为新名称创建标识符。</span><span class="sxs-lookup"><span data-stu-id="ce9d2-141">Create identifiers for new names.</span></span>
    
- <span data-ttu-id="ce9d2-142">检索特定名称的标识符。</span><span class="sxs-lookup"><span data-stu-id="ce9d2-142">Retrieve identifiers for specific names.</span></span>
    
- <span data-ttu-id="ce9d2-143">检索对象映射中包含的所有命名属性的标识符。</span><span class="sxs-lookup"><span data-stu-id="ce9d2-143">Retrieve identifiers for all named properties that are included in the object's mapping.</span></span>
    
<span data-ttu-id="ce9d2-144">命名属性通常由邮件存储提供程序用于文件夹和邮件。</span><span class="sxs-lookup"><span data-stu-id="ce9d2-144">Named properties are typically used by message store providers for folders and messages.</span></span> <span data-ttu-id="ce9d2-145">其他对象 (如邮件用户和配置文件节) 可能不支持将名称与属性标识符关联, 并且可能会从**GetIDsFromNames**返回 MAPI_E_NO_SUPPORT。</span><span class="sxs-lookup"><span data-stu-id="ce9d2-145">Other objects, such as messaging users and profile sections, might not support the association of names to property identifiers and might return MAPI_E_NO_SUPPORT from **GetIDsFromNames**.</span></span>
  
<span data-ttu-id="ce9d2-146">如果有错误返回特定名称的标识符, **GetIDsFromNames**将返回 MAPI_W_ERRORS_RETURNED, 并将属性标记数组项中对应于名称的属性类型设置为**PT_ERROR** , 并将标识符设置为零。</span><span class="sxs-lookup"><span data-stu-id="ce9d2-146">If there is an error that returns an identifier for a particular name, **GetIDsFromNames** returns MAPI_W_ERRORS_RETURNED and sets the property type in the property tag array entry that corresponds to the name to **PT_ERROR** and the identifier to zero.</span></span> 
  
<span data-ttu-id="ce9d2-147">名称到标识符的映射由对象的**PR_MAPPING_SIGNATURE** ([PidTagMappingSignature](pidtagmappingsignature-canonical-property.md)) 属性表示。</span><span class="sxs-lookup"><span data-stu-id="ce9d2-147">Name-to-identifier mapping is represented by an object's **PR_MAPPING_SIGNATURE** ([PidTagMappingSignature](pidtagmappingsignature-canonical-property.md)) property.</span></span> <span data-ttu-id="ce9d2-148">**PR_MAPPING_SIGNATURE**包含一个[MAPIUID](mapiuid.md)结构, 该结构指示负责对象的服务提供程序。</span><span class="sxs-lookup"><span data-stu-id="ce9d2-148">**PR_MAPPING_SIGNATURE** contains a [MAPIUID](mapiuid.md) structure that indicates the service provider responsible for the object.</span></span> <span data-ttu-id="ce9d2-149">如果两个对象的**PR_MAPPING_SIGNATURE**属性相同, 则假定这些对象使用相同的名称与标识符的映射。</span><span class="sxs-lookup"><span data-stu-id="ce9d2-149">If the **PR_MAPPING_SIGNATURE** property is the same for two objects, assume that these objects use the same name-to-identifier mapping.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="ce9d2-150">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="ce9d2-150">Notes to implementers</span></span>

<span data-ttu-id="ce9d2-151">您传递回由_lppPropNames_参数指向的属性标记数组中的标识符必须位于0x8000 到0xFFFE 范围中。</span><span class="sxs-lookup"><span data-stu-id="ce9d2-151">The identifiers that you pass back in the property tag array pointed to by the  _lppPropNames_ parameter must be in the 0x8000 to 0xFFFE range.</span></span> <span data-ttu-id="ce9d2-152">此数组中的条目必须与通过_lppPropNames_指向的属性名称数组中传递的名称的顺序相同。</span><span class="sxs-lookup"><span data-stu-id="ce9d2-152">The entries in this array must be in the same order as the names passed in the property name array pointed to by  _lppPropNames_.</span></span> 
  
<span data-ttu-id="ce9d2-153">如果支持容器上的命名属性, 请对容器中的所有对象使用相同的名称与标识符映射 (即, 不要对邮件存储区中的每个文件夹或文件夹中的每封邮件使用不同的映射)。</span><span class="sxs-lookup"><span data-stu-id="ce9d2-153">If you support named properties on a container, use the same name-to-identifier mapping for all objects in your container (that is, do not use a different mapping for each folder in your message store or each message in your folder).</span></span>
  
## <a name="notes-to-callers"></a><span data-ttu-id="ce9d2-154">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="ce9d2-154">Notes to callers</span></span>

<span data-ttu-id="ce9d2-155">由于_lppPropTags_指向的属性标记数组中返回的标识符的属性类型设置为**PT_UNSPECIFIED**, 因此您必须调用[IMAPIProp:: SetProps](imapiprop-setprops.md)方法以检索准确的类型。</span><span class="sxs-lookup"><span data-stu-id="ce9d2-155">Because the property types for the returned identifiers in the property tag array pointed to by  _lppPropTags_ are set to **PT_UNSPECIFIED**, you will have to call the [IMAPIProp::SetProps](imapiprop-setprops.md) method to retrieve the accurate types.</span></span> 
  
<span data-ttu-id="ce9d2-156">如果使用命名属性移动或复制对象, 并且源对象和目标对象的映射签名与它们的**PR_MAPPING_SIGNATURE**属性的值所表示的映射签名不同, 则必须在这些操作过程中保留这些名称。</span><span class="sxs-lookup"><span data-stu-id="ce9d2-156">If you move or copy objects with named properties, and the source and destination objects have different mapping signatures as indicated by the values of their **PR_MAPPING_SIGNATURE** properties, you must preserve the names during these operations.</span></span> <span data-ttu-id="ce9d2-157">若要保留属性名称, 请调整相应的属性标识符, 使其与目标对象的名称与标识符的映射相匹配。</span><span class="sxs-lookup"><span data-stu-id="ce9d2-157">To preserve property names, adjust the corresponding property identifiers to match the name-to-identifier mapping of the destination object.</span></span> 
  
<span data-ttu-id="ce9d2-158">某些对象的属性标识符的数目与它们可以命名的数目有一定的限制。</span><span class="sxs-lookup"><span data-stu-id="ce9d2-158">Some objects have a limit as to the number of property identifiers they can name.</span></span> <span data-ttu-id="ce9d2-159">如果对**GetIDsFromNames**的调用导致超出此限制, 则此方法将返回 MAPI_E_TOO_BIG。</span><span class="sxs-lookup"><span data-stu-id="ce9d2-159">If a call to **GetIDsFromNames** causes this limit to be exceeded, the method returns MAPI_E_TOO_BIG.</span></span> <span data-ttu-id="ce9d2-160">在这种情况下, 按标识符进行查询。</span><span class="sxs-lookup"><span data-stu-id="ce9d2-160">In this case, query by identifier.</span></span> 
  
<span data-ttu-id="ce9d2-161">有关详细信息, 请参阅[MAPI 命名属性](mapi-named-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="ce9d2-161">For more information, see [MAPI Named Properties](mapi-named-properties.md).</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="ce9d2-162">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="ce9d2-162">MFCMAPI reference</span></span>

<span data-ttu-id="ce9d2-163">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="ce9d2-163">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="ce9d2-164">**文件**</span><span class="sxs-lookup"><span data-stu-id="ce9d2-164">**File**</span></span>|<span data-ttu-id="ce9d2-165">**函数**</span><span class="sxs-lookup"><span data-stu-id="ce9d2-165">**Function**</span></span>|<span data-ttu-id="ce9d2-166">**备注**</span><span class="sxs-lookup"><span data-stu-id="ce9d2-166">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ce9d2-167">SingleMAPIPropListCtrl</span><span class="sxs-lookup"><span data-stu-id="ce9d2-167">SingleMAPIPropListCtrl.cpp</span></span>  <br/> |<span data-ttu-id="ce9d2-168">CSingleMAPIPropListCtrl:: FindAllNamedPropsUsed</span><span class="sxs-lookup"><span data-stu-id="ce9d2-168">CSingleMAPIPropListCtrl::FindAllNamedPropsUsed</span></span>  <br/> |<span data-ttu-id="ce9d2-169">MFCMAPI 使用**IMAPIProp:: GetIDsFromNames**方法获取已映射的所有命名属性的属性标记。</span><span class="sxs-lookup"><span data-stu-id="ce9d2-169">MFCMAPI uses the **IMAPIProp::GetIDsFromNames** method to obtain property tags for all named properties that have been mapped.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="ce9d2-170">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ce9d2-170">See also</span></span>



[<span data-ttu-id="ce9d2-171">IMAPIProp::GetNamesFromIDs</span><span class="sxs-lookup"><span data-stu-id="ce9d2-171">IMAPIProp::GetNamesFromIDs</span></span>](imapiprop-getnamesfromids.md)
  
[<span data-ttu-id="ce9d2-172">IMAPIProp::SetProps</span><span class="sxs-lookup"><span data-stu-id="ce9d2-172">IMAPIProp::SetProps</span></span>](imapiprop-setprops.md)
  
[<span data-ttu-id="ce9d2-173">MAPINAMEID</span><span class="sxs-lookup"><span data-stu-id="ce9d2-173">MAPINAMEID</span></span>](mapinameid.md)
  
[<span data-ttu-id="ce9d2-174">MAPIUID</span><span class="sxs-lookup"><span data-stu-id="ce9d2-174">MAPIUID</span></span>](mapiuid.md)
  
[<span data-ttu-id="ce9d2-175">IMAPIProp : IUnknown</span><span class="sxs-lookup"><span data-stu-id="ce9d2-175">IMAPIProp : IUnknown</span></span>](imapipropiunknown.md)


[<span data-ttu-id="ce9d2-176">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="ce9d2-176">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)
  
[<span data-ttu-id="ce9d2-177">MAPI 命名属性</span><span class="sxs-lookup"><span data-stu-id="ce9d2-177">MAPI Named Properties</span></span>](mapi-named-properties.md)
  
[<span data-ttu-id="ce9d2-178">使用宏进行错误处理</span><span class="sxs-lookup"><span data-stu-id="ce9d2-178">Using Macros for Error Handling</span></span>](using-macros-for-error-handling.md)

