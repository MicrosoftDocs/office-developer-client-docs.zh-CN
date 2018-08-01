---
title: IMAPIPropSetProps
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIProp.SetProps
api_type:
- COM
ms.assetid: 49f007c9-42e5-4391-8b83-988c9b0ebdba
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 304295e3ac77fb67ec5875620a7a269377b542c1
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775527"
---
# <a name="imapipropsetprops"></a><span data-ttu-id="25a62-103">IMAPIProp::SetProps</span><span class="sxs-lookup"><span data-stu-id="25a62-103">IMAPIProp::SetProps</span></span>

  
  
<span data-ttu-id="25a62-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="25a62-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="25a62-105">更新一个或多个属性。</span><span class="sxs-lookup"><span data-stu-id="25a62-105">Updates one or more properties.</span></span>
  
```cpp
HRESULT SetProps(
  ULONG cValues,
  LPSPropValue lpPropArray,
  LPSPropProblemArray FAR * lppProblems
);
```

## <a name="parameters"></a><span data-ttu-id="25a62-106">参数</span><span class="sxs-lookup"><span data-stu-id="25a62-106">Parameters</span></span>

 <span data-ttu-id="25a62-107">_cValues_</span><span class="sxs-lookup"><span data-stu-id="25a62-107">_cValues_</span></span>
  
> <span data-ttu-id="25a62-108">[in]_LpPropArray_参数指向的属性值的计数。</span><span class="sxs-lookup"><span data-stu-id="25a62-108">[in] The count of property values pointed to by the  _lpPropArray_ parameter.</span></span> <span data-ttu-id="25a62-109">_CValues_参数不能 0。</span><span class="sxs-lookup"><span data-stu-id="25a62-109">The  _cValues_ parameter must not be 0.</span></span> 
    
 <span data-ttu-id="25a62-110">_lpPropArray_</span><span class="sxs-lookup"><span data-stu-id="25a62-110">_lpPropArray_</span></span>
  
> <span data-ttu-id="25a62-111">[in]一个指向一个[SPropValue](spropvalue.md)结构包含要更新的属性值的数组。</span><span class="sxs-lookup"><span data-stu-id="25a62-111">[in] A pointer to an array of [SPropValue](spropvalue.md) structures that contain property values to be updated.</span></span> 
    
 <span data-ttu-id="25a62-112">_lppProblems_</span><span class="sxs-lookup"><span data-stu-id="25a62-112">_lppProblems_</span></span>
  
> <span data-ttu-id="25a62-113">[传入、 传出]在输入时，为[SPropProblemArray](spropproblemarray.md)结构; 指针的指针否则，为 NULL，表明错误信息不需要。</span><span class="sxs-lookup"><span data-stu-id="25a62-113">[in, out] On input, a pointer to a pointer to an [SPropProblemArray](spropproblemarray.md) structure; otherwise, NULL, indicating no need for error information.</span></span> <span data-ttu-id="25a62-114">如果_lppProblems_上输入, 的有效指针**SetProps**更新一个或多个属性的返回有关错误的详细的信息。</span><span class="sxs-lookup"><span data-stu-id="25a62-114">If  _lppProblems_ is a valid pointer on input, **SetProps** returns detailed information about errors in updating one or more properties.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="25a62-115">返回值</span><span class="sxs-lookup"><span data-stu-id="25a62-115">Return value</span></span>

<span data-ttu-id="25a62-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="25a62-116">S_OK</span></span> 
  
> <span data-ttu-id="25a62-117">属性已成功更新。</span><span class="sxs-lookup"><span data-stu-id="25a62-117">The properties were successfully updated.</span></span>
    
<span data-ttu-id="25a62-118">可以为**SetProps**中返回在**SPropProblemArray**结构中，但不是返回值是以下值：</span><span class="sxs-lookup"><span data-stu-id="25a62-118">The following values can be returned in the **SPropProblemArray** structure, but not as return values for **SetProps**:</span></span>
  
<span data-ttu-id="25a62-119">MAPI_E_BAD_CHARWIDTH</span><span class="sxs-lookup"><span data-stu-id="25a62-119">MAPI_E_BAD_CHARWIDTH</span></span> 
  
> <span data-ttu-id="25a62-120">既设置了 MAPI_UNICODE 标志实现不支持 Unicode，或未设置 MAPI_UNICODE 并实现支持仅 Unicode。</span><span class="sxs-lookup"><span data-stu-id="25a62-120">Either the MAPI_UNICODE flag was set and the implementation does not support Unicode, or MAPI_UNICODE was not set and the implementation supports only Unicode.</span></span>
    
<span data-ttu-id="25a62-121">MAPI_E_COMPUTED</span><span class="sxs-lookup"><span data-stu-id="25a62-121">MAPI_E_COMPUTED</span></span> 
  
> <span data-ttu-id="25a62-122">无法更新属性，因为它是只读的计算负责对象的服务提供商。</span><span class="sxs-lookup"><span data-stu-id="25a62-122">The property cannot be updated because it is read-only, computed by the service provider that is responsible for the object.</span></span>
    
<span data-ttu-id="25a62-123">MAPI_E_INVALID_TYPE</span><span class="sxs-lookup"><span data-stu-id="25a62-123">MAPI_E_INVALID_TYPE</span></span> 
  
> <span data-ttu-id="25a62-124">属性类型无效。</span><span class="sxs-lookup"><span data-stu-id="25a62-124">The property type is invalid.</span></span>
    
<span data-ttu-id="25a62-125">MAPI_E_NO_ACCESS</span><span class="sxs-lookup"><span data-stu-id="25a62-125">MAPI_E_NO_ACCESS</span></span> 
  
> <span data-ttu-id="25a62-126">尝试修改只读对象或访问其用户没有足够的权限的对象。</span><span class="sxs-lookup"><span data-stu-id="25a62-126">An attempt was made to modify a read-only object or to access an object for which the user has insufficient permissions.</span></span>
    
<span data-ttu-id="25a62-127">MAPI_E_NOT_ENOUGH_MEMORY</span><span class="sxs-lookup"><span data-stu-id="25a62-127">MAPI_E_NOT_ENOUGH_MEMORY</span></span> 
  
> <span data-ttu-id="25a62-128">无法更新属性，因为它是大于远程过程调用 (RPC) 缓冲区大小。</span><span class="sxs-lookup"><span data-stu-id="25a62-128">The property cannot be updated because it is larger than the remote procedure call (RPC) buffer size.</span></span>
    
<span data-ttu-id="25a62-129">MAPI_E_UNEXPECTED_TYPE</span><span class="sxs-lookup"><span data-stu-id="25a62-129">MAPI_E_UNEXPECTED_TYPE</span></span> 
  
> <span data-ttu-id="25a62-130">属性类型不需要调用实现的类型。</span><span class="sxs-lookup"><span data-stu-id="25a62-130">The property type is not the type expected by the calling implementation.</span></span>
    
## <a name="notes-to-implementers"></a><span data-ttu-id="25a62-131">针对实施者的注释</span><span class="sxs-lookup"><span data-stu-id="25a62-131">Notes to implementers</span></span>

<span data-ttu-id="25a62-132">忽略**PR_NULL** ([PidTagNull](pidtagnull-canonical-property.md)) 属性标记和**PT_ERROR**类型的所有属性。</span><span class="sxs-lookup"><span data-stu-id="25a62-132">Ignore the **PR_NULL** ([PidTagNull](pidtagnull-canonical-property.md)) property tag and all properties with a type of **PT_ERROR**.</span></span> <span data-ttu-id="25a62-133">不进行更改或报告问题**SPropProblemArray**结构中。</span><span class="sxs-lookup"><span data-stu-id="25a62-133">Do not make changes or report problems in the **SPropProblemArray** structure.</span></span> 
  
<span data-ttu-id="25a62-134">如果类型**PT_OBJECT**的属性包含属性值数组中，返回 MAPI_E_INVALID_PARAMETER。</span><span class="sxs-lookup"><span data-stu-id="25a62-134">Return MAPI_E_INVALID_PARAMETER if a property of type **PT_OBJECT** is included in the property value array.</span></span> <span data-ttu-id="25a62-135">也返回此错误，则多值属性包含数组和其**cValues**成员中设置为 0。</span><span class="sxs-lookup"><span data-stu-id="25a62-135">Also return this error if a multiple-value property is included in the array and its **cValues** member is set to 0.</span></span> 
  
<span data-ttu-id="25a62-136">如果调用成功总体，但有问题设置的一些属性，返回 S_OK 和问题的信息置于_lppProblems_参数指向的**SPropProblemArray**结构中的相应项。</span><span class="sxs-lookup"><span data-stu-id="25a62-136">If the call succeeds overall but there are problems with setting some of the properties, return S_OK and put information about the problems in the appropriate entry of the **SPropProblemArray** structure that the  _lppProblems_ parameter points to.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="25a62-137">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="25a62-137">Notes to callers</span></span>

<span data-ttu-id="25a62-138">根据服务提供程序，您可能还能够通过传递比以前使用的给定的属性标识符具有包含不同类型的属性标记更改的属性类型。</span><span class="sxs-lookup"><span data-stu-id="25a62-138">Depending on the service provider, you might also be able to change the property type by passing a property tag that contains a different type than was previously used with a given property identifier.</span></span>
  
<span data-ttu-id="25a62-139">如果包括属性标记为不支持的对象的属性和**SetProps**的实现允许创建的新属性，则将属性添加到对象。</span><span class="sxs-lookup"><span data-stu-id="25a62-139">If you include a property tag for a property that is unsupported by the object and the implementation of **SetProps** allows the creation of new properties, the property is added to the object.</span></span> <span data-ttu-id="25a62-140">存储用于新属性的属性标识符与以前的任何值将被丢弃。</span><span class="sxs-lookup"><span data-stu-id="25a62-140">Any previous value stored with the property identifier that was used for the new property is discarded.</span></span> 
  
<span data-ttu-id="25a62-141">请注意，不保证 S_OK 返回值的所有属性已成功更新。</span><span class="sxs-lookup"><span data-stu-id="25a62-141">Note that the S_OK return value does not guarantee that all of the properties were successfully updated.</span></span> <span data-ttu-id="25a62-142">某些提供程序直到其接收呼叫，需要提供程序干预，如[IMAPIProp::SaveChanges](imapiprop-savechanges.md)或[IMAPIProp::GetProps](imapiprop-getprops.md)缓存**SetProps**呼叫。</span><span class="sxs-lookup"><span data-stu-id="25a62-142">Some providers cache **SetProps** calls until they receive a call that requires provider intervention, such as [IMAPIProp::SaveChanges](imapiprop-savechanges.md) or [IMAPIProp::GetProps](imapiprop-getprops.md).</span></span> <span data-ttu-id="25a62-143">因此，很可能收到与更高版本的呼叫的**SetProps**呼叫相关的错误值。</span><span class="sxs-lookup"><span data-stu-id="25a62-143">Therefore, it is possible to receive error values that relate to the **SetProps** call with the later calls.</span></span> 
  
<span data-ttu-id="25a62-144">如果**SetProps** ，则返回 S_OK，检查所指的_lppProblems_更新各个属性的问题的**SPropProblemArray**结构。</span><span class="sxs-lookup"><span data-stu-id="25a62-144">If **SetProps** returns S_OK, check the **SPropProblemArray** structure pointed to by  _lppProblems_ for problems updating individual properties.</span></span> <span data-ttu-id="25a62-145">如果**SetProps**返回一个错误，则不会检查属性问题数组。</span><span class="sxs-lookup"><span data-stu-id="25a62-145">If **SetProps** returns an error, do not check the property problem array.</span></span> <span data-ttu-id="25a62-146">相反，呼叫对象的[IMAPIProp::GetLastError](imapiprop-getlasterror.md)方法。</span><span class="sxs-lookup"><span data-stu-id="25a62-146">Instead, call the object's [IMAPIProp::GetLastError](imapiprop-getlasterror.md) method.</span></span> 
  
<span data-ttu-id="25a62-147">更新时大型属性， **SetProps**可以失败并返回 MAPI_E_NOT_ENOUGH_MEMORY。</span><span class="sxs-lookup"><span data-stu-id="25a62-147">When updating large properties, **SetProps** can fail and return MAPI_E_NOT_ENOUGH_MEMORY.</span></span> <span data-ttu-id="25a62-148">没有属性，最大大小和不同的对象可以具有不同的限制。</span><span class="sxs-lookup"><span data-stu-id="25a62-148">There is no maximum size for properties, and different objects can have different limits.</span></span> <span data-ttu-id="25a62-149">如果您处理可能很大的属性，准备接口标识调用与 IID_IStream [IMAPIProp::OpenProperty](imapiprop-openproperty.md)方法，如果**SetProps**返回此错误值。</span><span class="sxs-lookup"><span data-stu-id="25a62-149">If you deal with potentially large properties, be prepared to call the [IMAPIProp::OpenProperty](imapiprop-openproperty.md) method with IID_IStream as the interface identifier if **SetProps** returns this error value.</span></span> 
  
<span data-ttu-id="25a62-150">调用[MAPIFreeBuffer](mapifreebuffer.md)函数以释放**SPropProblemArray**结构。</span><span class="sxs-lookup"><span data-stu-id="25a62-150">Call the [MAPIFreeBuffer](mapifreebuffer.md) function to free the **SPropProblemArray** structure.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="25a62-151">MFCMAPI 参考 （英文）</span><span class="sxs-lookup"><span data-stu-id="25a62-151">MFCMAPI reference</span></span>

<span data-ttu-id="25a62-152">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="25a62-152">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="25a62-153">**文件**</span><span class="sxs-lookup"><span data-stu-id="25a62-153">**File**</span></span>|<span data-ttu-id="25a62-154">**函数**</span><span class="sxs-lookup"><span data-stu-id="25a62-154">**Function**</span></span>|<span data-ttu-id="25a62-155">**Comment**</span><span class="sxs-lookup"><span data-stu-id="25a62-155">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="25a62-156">PropertyEditor.cpp</span><span class="sxs-lookup"><span data-stu-id="25a62-156">PropertyEditor.cpp</span></span>  <br/> |<span data-ttu-id="25a62-157">CPropertyEditor::WriteSPropValueToObject</span><span class="sxs-lookup"><span data-stu-id="25a62-157">CPropertyEditor::WriteSPropValueToObject</span></span>  <br/> |<span data-ttu-id="25a62-158">MFCMAPI 使用**IMAPIProp::SetProps**方法后，已编辑属性回写到对象的属性。</span><span class="sxs-lookup"><span data-stu-id="25a62-158">MFCMAPI uses the **IMAPIProp::SetProps** method to write a property back to an object after the property has been edited.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="25a62-159">另请参阅</span><span class="sxs-lookup"><span data-stu-id="25a62-159">See also</span></span>



[<span data-ttu-id="25a62-160">IMAPIProp::GetLastError</span><span class="sxs-lookup"><span data-stu-id="25a62-160">IMAPIProp::GetLastError</span></span>](imapiprop-getlasterror.md)
  
[<span data-ttu-id="25a62-161">IMAPIProp::GetProps</span><span class="sxs-lookup"><span data-stu-id="25a62-161">IMAPIProp::GetProps</span></span>](imapiprop-getprops.md)
  
[<span data-ttu-id="25a62-162">IMAPIProp::OpenProperty</span><span class="sxs-lookup"><span data-stu-id="25a62-162">IMAPIProp::OpenProperty</span></span>](imapiprop-openproperty.md)
  
[<span data-ttu-id="25a62-163">IMAPIProp::SaveChanges</span><span class="sxs-lookup"><span data-stu-id="25a62-163">IMAPIProp::SaveChanges</span></span>](imapiprop-savechanges.md)
  
[<span data-ttu-id="25a62-164">MAPIFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="25a62-164">MAPIFreeBuffer</span></span>](mapifreebuffer.md)
  
[<span data-ttu-id="25a62-165">SPropProblemArray</span><span class="sxs-lookup"><span data-stu-id="25a62-165">SPropProblemArray</span></span>](spropproblemarray.md)
  
[<span data-ttu-id="25a62-166">SPropValue</span><span class="sxs-lookup"><span data-stu-id="25a62-166">SPropValue</span></span>](spropvalue.md)
  
[<span data-ttu-id="25a62-167">IMAPIProp : IUnknown</span><span class="sxs-lookup"><span data-stu-id="25a62-167">IMAPIProp : IUnknown</span></span>](imapipropiunknown.md)

