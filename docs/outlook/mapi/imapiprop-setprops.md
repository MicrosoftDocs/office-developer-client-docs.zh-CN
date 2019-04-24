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
ms.openlocfilehash: 87709f8a77471637d7652982669bcba93ca2e1dd
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32341011"
---
# <a name="imapipropsetprops"></a><span data-ttu-id="4664c-103">IMAPIProp::SetProps</span><span class="sxs-lookup"><span data-stu-id="4664c-103">IMAPIProp::SetProps</span></span>

  
  
<span data-ttu-id="4664c-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="4664c-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="4664c-105">更新一个或多个属性。</span><span class="sxs-lookup"><span data-stu-id="4664c-105">Updates one or more properties.</span></span>
  
```cpp
HRESULT SetProps(
  ULONG cValues,
  LPSPropValue lpPropArray,
  LPSPropProblemArray FAR * lppProblems
);
```

## <a name="parameters"></a><span data-ttu-id="4664c-106">参数</span><span class="sxs-lookup"><span data-stu-id="4664c-106">Parameters</span></span>

 <span data-ttu-id="4664c-107">_cValues_</span><span class="sxs-lookup"><span data-stu-id="4664c-107">_cValues_</span></span>
  
> <span data-ttu-id="4664c-108">实时由_lpPropArray_参数指向的属性值的计数。</span><span class="sxs-lookup"><span data-stu-id="4664c-108">[in] The count of property values pointed to by the  _lpPropArray_ parameter.</span></span> <span data-ttu-id="4664c-109">_cValues_参数不得为0。</span><span class="sxs-lookup"><span data-stu-id="4664c-109">The  _cValues_ parameter must not be 0.</span></span> 
    
 <span data-ttu-id="4664c-110">_lpPropArray_</span><span class="sxs-lookup"><span data-stu-id="4664c-110">_lpPropArray_</span></span>
  
> <span data-ttu-id="4664c-111">实时指向[SPropValue](spropvalue.md)结构数组的指针, 该数组包含要更新的属性值。</span><span class="sxs-lookup"><span data-stu-id="4664c-111">[in] A pointer to an array of [SPropValue](spropvalue.md) structures that contain property values to be updated.</span></span> 
    
 <span data-ttu-id="4664c-112">_lppProblems_</span><span class="sxs-lookup"><span data-stu-id="4664c-112">_lppProblems_</span></span>
  
> <span data-ttu-id="4664c-113">[in, out]在输入时, 指向指向[SPropProblemArray](spropproblemarray.md)结构的指针的指针;否则为 NULL, 表示无需错误信息。</span><span class="sxs-lookup"><span data-stu-id="4664c-113">[in, out] On input, a pointer to a pointer to an [SPropProblemArray](spropproblemarray.md) structure; otherwise, NULL, indicating no need for error information.</span></span> <span data-ttu-id="4664c-114">如果_lppProblems_是有效的输入指针, **SetProps**将返回有关更新一个或多个属性中的错误的详细信息。</span><span class="sxs-lookup"><span data-stu-id="4664c-114">If  _lppProblems_ is a valid pointer on input, **SetProps** returns detailed information about errors in updating one or more properties.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="4664c-115">返回值</span><span class="sxs-lookup"><span data-stu-id="4664c-115">Return value</span></span>

<span data-ttu-id="4664c-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="4664c-116">S_OK</span></span> 
  
> <span data-ttu-id="4664c-117">属性已成功更新。</span><span class="sxs-lookup"><span data-stu-id="4664c-117">The properties were successfully updated.</span></span>
    
<span data-ttu-id="4664c-118">以下值可在**SPropProblemArray**结构中返回, 但不能在**SetProps**的返回值中返回:</span><span class="sxs-lookup"><span data-stu-id="4664c-118">The following values can be returned in the **SPropProblemArray** structure, but not as return values for **SetProps**:</span></span>
  
<span data-ttu-id="4664c-119">MAPI_E_BAD_CHARWIDTH</span><span class="sxs-lookup"><span data-stu-id="4664c-119">MAPI_E_BAD_CHARWIDTH</span></span> 
  
> <span data-ttu-id="4664c-120">设置了 MAPI_UNICODE 标志, 且实现不支持 unicode, 或者未设置 MAPI_UNICODE, 且实现仅支持 UNICODE。</span><span class="sxs-lookup"><span data-stu-id="4664c-120">Either the MAPI_UNICODE flag was set and the implementation does not support Unicode, or MAPI_UNICODE was not set and the implementation supports only Unicode.</span></span>
    
<span data-ttu-id="4664c-121">MAPI_E_COMPUTED</span><span class="sxs-lookup"><span data-stu-id="4664c-121">MAPI_E_COMPUTED</span></span> 
  
> <span data-ttu-id="4664c-122">属性不能更新, 因为它是只读的, 由负责该对象的服务提供程序进行计算。</span><span class="sxs-lookup"><span data-stu-id="4664c-122">The property cannot be updated because it is read-only, computed by the service provider that is responsible for the object.</span></span>
    
<span data-ttu-id="4664c-123">MAPI_E_INVALID_TYPE</span><span class="sxs-lookup"><span data-stu-id="4664c-123">MAPI_E_INVALID_TYPE</span></span> 
  
> <span data-ttu-id="4664c-124">属性类型无效。</span><span class="sxs-lookup"><span data-stu-id="4664c-124">The property type is invalid.</span></span>
    
<span data-ttu-id="4664c-125">MAPI_E_NO_ACCESS</span><span class="sxs-lookup"><span data-stu-id="4664c-125">MAPI_E_NO_ACCESS</span></span> 
  
> <span data-ttu-id="4664c-126">试图修改只读对象或访问用户拥有的对象权限不足的对象。</span><span class="sxs-lookup"><span data-stu-id="4664c-126">An attempt was made to modify a read-only object or to access an object for which the user has insufficient permissions.</span></span>
    
<span data-ttu-id="4664c-127">MAPI_E_NOT_ENOUGH_MEMORY</span><span class="sxs-lookup"><span data-stu-id="4664c-127">MAPI_E_NOT_ENOUGH_MEMORY</span></span> 
  
> <span data-ttu-id="4664c-128">属性不能更新, 因为它大于远程过程调用 (RPC) 缓冲区大小。</span><span class="sxs-lookup"><span data-stu-id="4664c-128">The property cannot be updated because it is larger than the remote procedure call (RPC) buffer size.</span></span>
    
<span data-ttu-id="4664c-129">MAPI_E_UNEXPECTED_TYPE</span><span class="sxs-lookup"><span data-stu-id="4664c-129">MAPI_E_UNEXPECTED_TYPE</span></span> 
  
> <span data-ttu-id="4664c-130">属性类型不是调用实现所需的类型。</span><span class="sxs-lookup"><span data-stu-id="4664c-130">The property type is not the type expected by the calling implementation.</span></span>
    
## <a name="notes-to-implementers"></a><span data-ttu-id="4664c-131">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="4664c-131">Notes to implementers</span></span>

<span data-ttu-id="4664c-132">忽略类型为**PT_ERROR**的**PR_NULL** ([PidTagNull](pidtagnull-canonical-property.md)) 属性标记和所有属性。</span><span class="sxs-lookup"><span data-stu-id="4664c-132">Ignore the **PR_NULL** ([PidTagNull](pidtagnull-canonical-property.md)) property tag and all properties with a type of **PT_ERROR**.</span></span> <span data-ttu-id="4664c-133">请勿在**SPropProblemArray**结构中进行更改或报告问题。</span><span class="sxs-lookup"><span data-stu-id="4664c-133">Do not make changes or report problems in the **SPropProblemArray** structure.</span></span> 
  
<span data-ttu-id="4664c-134">如果属性值数组中包含**PT_OBJECT**类型的属性, 则返回 MAPI_E_INVALID_PARAMETER。</span><span class="sxs-lookup"><span data-stu-id="4664c-134">Return MAPI_E_INVALID_PARAMETER if a property of type **PT_OBJECT** is included in the property value array.</span></span> <span data-ttu-id="4664c-135">如果数组中包含多值属性, 并将其**cValues**成员设置为 0, 则也会返回此错误。</span><span class="sxs-lookup"><span data-stu-id="4664c-135">Also return this error if a multiple-value property is included in the array and its **cValues** member is set to 0.</span></span> 
  
<span data-ttu-id="4664c-136">如果调用成功, 但在设置某些属性时出现问题, 则返回 S_OK, 并将有关问题的信息放在_lppProblems_参数指向的**SPropProblemArray**结构的相应条目中。</span><span class="sxs-lookup"><span data-stu-id="4664c-136">If the call succeeds overall but there are problems with setting some of the properties, return S_OK and put information about the problems in the appropriate entry of the **SPropProblemArray** structure that the  _lppProblems_ parameter points to.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="4664c-137">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="4664c-137">Notes to callers</span></span>

<span data-ttu-id="4664c-138">根据服务提供程序的不同, 您还可以通过传递包含与先前用于给定属性标识符的类型不同的属性标记来更改属性类型。</span><span class="sxs-lookup"><span data-stu-id="4664c-138">Depending on the service provider, you might also be able to change the property type by passing a property tag that contains a different type than was previously used with a given property identifier.</span></span>
  
<span data-ttu-id="4664c-139">如果包含对象不支持的属性的属性标记, 且**SetProps**的实现允许创建新的属性, 则会将该属性添加到对象中。</span><span class="sxs-lookup"><span data-stu-id="4664c-139">If you include a property tag for a property that is unsupported by the object and the implementation of **SetProps** allows the creation of new properties, the property is added to the object.</span></span> <span data-ttu-id="4664c-140">以前与用于新属性的属性标识符一起存储的任何值都将被丢弃。</span><span class="sxs-lookup"><span data-stu-id="4664c-140">Any previous value stored with the property identifier that was used for the new property is discarded.</span></span> 
  
<span data-ttu-id="4664c-141">请注意, S_OK 返回值并不保证已成功更新所有属性。</span><span class="sxs-lookup"><span data-stu-id="4664c-141">Note that the S_OK return value does not guarantee that all of the properties were successfully updated.</span></span> <span data-ttu-id="4664c-142">某些提供程序在收到需要提供程序干预的调用 (如[IMAPIProp:: SaveChanges](imapiprop-savechanges.md)或[IMAPIProp:: GetProps](imapiprop-getprops.md)) 之前缓存**SetProps**调用。</span><span class="sxs-lookup"><span data-stu-id="4664c-142">Some providers cache **SetProps** calls until they receive a call that requires provider intervention, such as [IMAPIProp::SaveChanges](imapiprop-savechanges.md) or [IMAPIProp::GetProps](imapiprop-getprops.md).</span></span> <span data-ttu-id="4664c-143">因此, 可以接收与后续调用相关的**SetProps**调用的错误值。</span><span class="sxs-lookup"><span data-stu-id="4664c-143">Therefore, it is possible to receive error values that relate to the **SetProps** call with the later calls.</span></span> 
  
<span data-ttu-id="4664c-144">如果**SetProps**返回 S_OK, 请检查_lppProblems_针对更新各个属性的问题所指向的**SPropProblemArray**结构。</span><span class="sxs-lookup"><span data-stu-id="4664c-144">If **SetProps** returns S_OK, check the **SPropProblemArray** structure pointed to by  _lppProblems_ for problems updating individual properties.</span></span> <span data-ttu-id="4664c-145">如果**SetProps**返回错误, 请勿检查属性问题数组。</span><span class="sxs-lookup"><span data-stu-id="4664c-145">If **SetProps** returns an error, do not check the property problem array.</span></span> <span data-ttu-id="4664c-146">而是调用对象的[IMAPIProp:: GetLastError](imapiprop-getlasterror.md)方法。</span><span class="sxs-lookup"><span data-stu-id="4664c-146">Instead, call the object's [IMAPIProp::GetLastError](imapiprop-getlasterror.md) method.</span></span> 
  
<span data-ttu-id="4664c-147">更新大型属性时, **SetProps**可能会失败并返回 MAPI_E_NOT_ENOUGH_MEMORY。</span><span class="sxs-lookup"><span data-stu-id="4664c-147">When updating large properties, **SetProps** can fail and return MAPI_E_NOT_ENOUGH_MEMORY.</span></span> <span data-ttu-id="4664c-148">属性没有最大大小, 不同的对象可以有不同的限制。</span><span class="sxs-lookup"><span data-stu-id="4664c-148">There is no maximum size for properties, and different objects can have different limits.</span></span> <span data-ttu-id="4664c-149">如果您处理可能的大型属性, 请准备好在**SetProps**返回此错误值时将[IMAPIProp:: OpenProperty](imapiprop-openproperty.md)方法用作接口标识符, 以将 IID_IStream 作为接口标识符进行调用。</span><span class="sxs-lookup"><span data-stu-id="4664c-149">If you deal with potentially large properties, be prepared to call the [IMAPIProp::OpenProperty](imapiprop-openproperty.md) method with IID_IStream as the interface identifier if **SetProps** returns this error value.</span></span> 
  
<span data-ttu-id="4664c-150">调用[MAPIFreeBuffer](mapifreebuffer.md)函数以释放**SPropProblemArray**结构。</span><span class="sxs-lookup"><span data-stu-id="4664c-150">Call the [MAPIFreeBuffer](mapifreebuffer.md) function to free the **SPropProblemArray** structure.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="4664c-151">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="4664c-151">MFCMAPI reference</span></span>

<span data-ttu-id="4664c-152">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="4664c-152">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="4664c-153">**文件**</span><span class="sxs-lookup"><span data-stu-id="4664c-153">**File**</span></span>|<span data-ttu-id="4664c-154">**函数**</span><span class="sxs-lookup"><span data-stu-id="4664c-154">**Function**</span></span>|<span data-ttu-id="4664c-155">**备注**</span><span class="sxs-lookup"><span data-stu-id="4664c-155">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="4664c-156">PropertyEditor</span><span class="sxs-lookup"><span data-stu-id="4664c-156">PropertyEditor.cpp</span></span>  <br/> |<span data-ttu-id="4664c-157">CPropertyEditor:: WriteSPropValueToObject</span><span class="sxs-lookup"><span data-stu-id="4664c-157">CPropertyEditor::WriteSPropValueToObject</span></span>  <br/> |<span data-ttu-id="4664c-158">MFCMAPI 使用**IMAPIProp:: SetProps**方法在编辑属性后将属性写入对象。</span><span class="sxs-lookup"><span data-stu-id="4664c-158">MFCMAPI uses the **IMAPIProp::SetProps** method to write a property back to an object after the property has been edited.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="4664c-159">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4664c-159">See also</span></span>



[<span data-ttu-id="4664c-160">IMAPIProp::GetLastError</span><span class="sxs-lookup"><span data-stu-id="4664c-160">IMAPIProp::GetLastError</span></span>](imapiprop-getlasterror.md)
  
[<span data-ttu-id="4664c-161">IMAPIProp::GetProps</span><span class="sxs-lookup"><span data-stu-id="4664c-161">IMAPIProp::GetProps</span></span>](imapiprop-getprops.md)
  
[<span data-ttu-id="4664c-162">IMAPIProp::OpenProperty</span><span class="sxs-lookup"><span data-stu-id="4664c-162">IMAPIProp::OpenProperty</span></span>](imapiprop-openproperty.md)
  
[<span data-ttu-id="4664c-163">IMAPIProp::SaveChanges</span><span class="sxs-lookup"><span data-stu-id="4664c-163">IMAPIProp::SaveChanges</span></span>](imapiprop-savechanges.md)
  
[<span data-ttu-id="4664c-164">MAPIFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="4664c-164">MAPIFreeBuffer</span></span>](mapifreebuffer.md)
  
[<span data-ttu-id="4664c-165">SPropProblemArray</span><span class="sxs-lookup"><span data-stu-id="4664c-165">SPropProblemArray</span></span>](spropproblemarray.md)
  
[<span data-ttu-id="4664c-166">SPropValue</span><span class="sxs-lookup"><span data-stu-id="4664c-166">SPropValue</span></span>](spropvalue.md)
  
[<span data-ttu-id="4664c-167">IMAPIProp : IUnknown</span><span class="sxs-lookup"><span data-stu-id="4664c-167">IMAPIProp : IUnknown</span></span>](imapipropiunknown.md)

