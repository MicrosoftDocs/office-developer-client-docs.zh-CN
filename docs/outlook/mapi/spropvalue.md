---
title: SPropValue
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.SPropValue
api_type:
- COM
ms.assetid: faf795a2-84db-432d-a05f-082f25a5cab5
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: c7f4e8835831af6277cef134bf3961e9928cba33
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33433526"
---
# <a name="spropvalue"></a><span data-ttu-id="806d4-103">SPropValue</span><span class="sxs-lookup"><span data-stu-id="806d4-103">SPropValue</span></span>

  
  
<span data-ttu-id="806d4-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="806d4-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="806d4-105">描述 MAPI 属性。</span><span class="sxs-lookup"><span data-stu-id="806d4-105">Describes a MAPI property.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="806d4-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="806d4-106">Header file:</span></span>  <br/> |<span data-ttu-id="806d4-107">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="806d4-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="806d4-108">相关宏:</span><span class="sxs-lookup"><span data-stu-id="806d4-108">Related macros:</span></span>  <br/> |<span data-ttu-id="806d4-109">[CHANGE_PROP_TYPE](change_prop_type.md)、 [MVI_PROP](mvi_prop.md)、 [PROP_ID](prop_id.md)、 [PROP_TAG](prop_tag.md)、 [PROP_TYPE](prop_type.md)</span><span class="sxs-lookup"><span data-stu-id="806d4-109">[CHANGE_PROP_TYPE](change_prop_type.md), [MVI_PROP](mvi_prop.md), [PROP_ID](prop_id.md), [PROP_TAG](prop_tag.md), [PROP_TYPE](prop_type.md)</span></span> <br/> |
   
```cpp
typedef struct _SPropValue
{
  ULONG ulPropTag;
  ULONG dwAlignPad;
  union _PV Value;
} SPropValue, FAR *LPSPropValue;

```

## <a name="members"></a><span data-ttu-id="806d4-110">Members</span><span class="sxs-lookup"><span data-stu-id="806d4-110">Members</span></span>

 <span data-ttu-id="806d4-111">**ulPropTag**</span><span class="sxs-lookup"><span data-stu-id="806d4-111">**ulPropTag**</span></span>
  
> <span data-ttu-id="806d4-112">属性的属性标记。</span><span class="sxs-lookup"><span data-stu-id="806d4-112">Property tag for the property.</span></span> <span data-ttu-id="806d4-113">属性标记是32位无符号整数, 由高序位16位中的属性唯一标识符和低序位16位中的属性类型组成。</span><span class="sxs-lookup"><span data-stu-id="806d4-113">Property tags are 32-bit unsigned integers consisting of the property's unique identifier in the high-order 16 bits and the property's type in the low-order 16 bits.</span></span>
    
 <span data-ttu-id="806d4-114">**dwAlignPad**</span><span class="sxs-lookup"><span data-stu-id="806d4-114">**dwAlignPad**</span></span>
  
> <span data-ttu-id="806d4-115">为 MAPI 保留;请勿使用。</span><span class="sxs-lookup"><span data-stu-id="806d4-115">Reserved for MAPI; do not use.</span></span> 
    
 <span data-ttu-id="806d4-116">**值**</span><span class="sxs-lookup"><span data-stu-id="806d4-116">**Value**</span></span>
  
> <span data-ttu-id="806d4-117">数据值的联合, 由属性类型指定的特定值。</span><span class="sxs-lookup"><span data-stu-id="806d4-117">Union of data values, the specific value dictated by the property type.</span></span> <span data-ttu-id="806d4-118">下表列出了每个属性类型、应使用的联合的成员及其关联的数据类型。</span><span class="sxs-lookup"><span data-stu-id="806d4-118">The following table lists for each property type, the member of the union that should be used and its associated data type.</span></span>
    
|<span data-ttu-id="806d4-119">**属性类型**</span><span class="sxs-lookup"><span data-stu-id="806d4-119">**Property type**</span></span>|<span data-ttu-id="806d4-120">**值**</span><span class="sxs-lookup"><span data-stu-id="806d4-120">**Value**</span></span>|<span data-ttu-id="806d4-121">**值的数据类型**</span><span class="sxs-lookup"><span data-stu-id="806d4-121">**Data type of Value**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="806d4-122">PT_I2 或 PT_SHORT</span><span class="sxs-lookup"><span data-stu-id="806d4-122">PT_I2 or PT_SHORT</span></span>  <br/> |<span data-ttu-id="806d4-123">**i**</span><span class="sxs-lookup"><span data-stu-id="806d4-123">**i**</span></span> <br/> |<span data-ttu-id="806d4-124">短整型</span><span class="sxs-lookup"><span data-stu-id="806d4-124">short int</span></span>  <br/> |
|<span data-ttu-id="806d4-125">PT_I4 或 PT_LONG (已签名)</span><span class="sxs-lookup"><span data-stu-id="806d4-125">PT_I4 or PT_LONG (signed)</span></span>  <br/> |<span data-ttu-id="806d4-126">**l**</span><span class="sxs-lookup"><span data-stu-id="806d4-126">**l**</span></span> <br/> |<span data-ttu-id="806d4-127">LONG</span><span class="sxs-lookup"><span data-stu-id="806d4-127">LONG</span></span>  <br/> |
|<span data-ttu-id="806d4-128">PT_I4 或 PT_LONG (无符号)</span><span class="sxs-lookup"><span data-stu-id="806d4-128">PT_I4 or PT_LONG (unsigned)</span></span>  <br/> |<span data-ttu-id="806d4-129">**列名**</span><span class="sxs-lookup"><span data-stu-id="806d4-129">**ul**</span></span> <br/> |<span data-ttu-id="806d4-130">ULONG</span><span class="sxs-lookup"><span data-stu-id="806d4-130">ULONG</span></span>  <br/> |
|<span data-ttu-id="806d4-131">PT_R4 或 PT_FLOAT</span><span class="sxs-lookup"><span data-stu-id="806d4-131">PT_R4 or PT_FLOAT</span></span>  <br/> |<span data-ttu-id="806d4-132">**flt**</span><span class="sxs-lookup"><span data-stu-id="806d4-132">**flt**</span></span> <br/> |<span data-ttu-id="806d4-133">点数</span><span class="sxs-lookup"><span data-stu-id="806d4-133">float</span></span>  <br/> |
|<span data-ttu-id="806d4-134">PT_R8 或 PT_DOUBLE</span><span class="sxs-lookup"><span data-stu-id="806d4-134">PT_R8 or PT_DOUBLE</span></span>  <br/> |<span data-ttu-id="806d4-135">**双**</span><span class="sxs-lookup"><span data-stu-id="806d4-135">**dbl**</span></span> <br/> |<span data-ttu-id="806d4-136">double</span><span class="sxs-lookup"><span data-stu-id="806d4-136">double</span></span>  <br/> |
|<span data-ttu-id="806d4-137">PT_BOOLEAN</span><span class="sxs-lookup"><span data-stu-id="806d4-137">PT_BOOLEAN</span></span>  <br/> |<span data-ttu-id="806d4-138">**b**</span><span class="sxs-lookup"><span data-stu-id="806d4-138">**b**</span></span> <br/> |<span data-ttu-id="806d4-139">无符号短整型</span><span class="sxs-lookup"><span data-stu-id="806d4-139">unsigned short int</span></span>  <br/> |
|<span data-ttu-id="806d4-140">PT_CURRENCY</span><span class="sxs-lookup"><span data-stu-id="806d4-140">PT_CURRENCY</span></span>  <br/> |<span data-ttu-id="806d4-141">**选用**</span><span class="sxs-lookup"><span data-stu-id="806d4-141">**cur**</span></span> <br/> |[<span data-ttu-id="806d4-142">CURRENCY</span><span class="sxs-lookup"><span data-stu-id="806d4-142">CURRENCY</span></span>](currency.md) <br/> |
|<span data-ttu-id="806d4-143">PT_APPTIME</span><span class="sxs-lookup"><span data-stu-id="806d4-143">PT_APPTIME</span></span>  <br/> |<span data-ttu-id="806d4-144">**个**</span><span class="sxs-lookup"><span data-stu-id="806d4-144">**at**</span></span> <br/> |<span data-ttu-id="806d4-145">double</span><span class="sxs-lookup"><span data-stu-id="806d4-145">double</span></span>  <br/> |
|<span data-ttu-id="806d4-146">PT_SYSTIME</span><span class="sxs-lookup"><span data-stu-id="806d4-146">PT_SYSTIME</span></span>  <br/> |<span data-ttu-id="806d4-147">**ft**</span><span class="sxs-lookup"><span data-stu-id="806d4-147">**ft**</span></span> <br/> |[<span data-ttu-id="806d4-148">FILETIME</span><span class="sxs-lookup"><span data-stu-id="806d4-148">FILETIME</span></span>](filetime.md) <br/> |
|<span data-ttu-id="806d4-149">PT_STRING8</span><span class="sxs-lookup"><span data-stu-id="806d4-149">PT_STRING8</span></span>  <br/> |<span data-ttu-id="806d4-150">**lpszA**</span><span class="sxs-lookup"><span data-stu-id="806d4-150">**lpszA**</span></span> <br/> |<span data-ttu-id="806d4-151">LPSTR</span><span class="sxs-lookup"><span data-stu-id="806d4-151">LPSTR</span></span>  <br/> |
|<span data-ttu-id="806d4-152">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="806d4-152">PT_BINARY</span></span>  <br/> |<span data-ttu-id="806d4-153">**区间**</span><span class="sxs-lookup"><span data-stu-id="806d4-153">**bin**</span></span> <br/> |<span data-ttu-id="806d4-154">BYTE [array]</span><span class="sxs-lookup"><span data-stu-id="806d4-154">BYTE [array]</span></span>  <br/> |
|<span data-ttu-id="806d4-155">PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="806d4-155">PT_UNICODE</span></span>  <br/> |<span data-ttu-id="806d4-156">**lpszW**</span><span class="sxs-lookup"><span data-stu-id="806d4-156">**lpszW**</span></span> <br/> |<span data-ttu-id="806d4-157">LPWSTR</span><span class="sxs-lookup"><span data-stu-id="806d4-157">LPWSTR</span></span>  <br/> |
|<span data-ttu-id="806d4-158">PT_CLSID</span><span class="sxs-lookup"><span data-stu-id="806d4-158">PT_CLSID</span></span>  <br/> |<span data-ttu-id="806d4-159">**lpguid**</span><span class="sxs-lookup"><span data-stu-id="806d4-159">**lpguid**</span></span> <br/> |<span data-ttu-id="806d4-160">LPGUID</span><span class="sxs-lookup"><span data-stu-id="806d4-160">LPGUID</span></span>  <br/> |
|<span data-ttu-id="806d4-161">PT_I8 或 PT_LONGLONG</span><span class="sxs-lookup"><span data-stu-id="806d4-161">PT_I8 or PT_LONGLONG</span></span>  <br/> |<span data-ttu-id="806d4-162">**i**</span><span class="sxs-lookup"><span data-stu-id="806d4-162">**li**</span></span> <br/> |<span data-ttu-id="806d4-163">**LARGE_INTEGER**</span><span class="sxs-lookup"><span data-stu-id="806d4-163">**LARGE_INTEGER**</span></span> <br/> |
|<span data-ttu-id="806d4-164">PT_MV_I2</span><span class="sxs-lookup"><span data-stu-id="806d4-164">PT_MV_I2</span></span>  <br/> |<span data-ttu-id="806d4-165">**MVi**</span><span class="sxs-lookup"><span data-stu-id="806d4-165">**MVi**</span></span> <br/> |[<span data-ttu-id="806d4-166">SShortArray</span><span class="sxs-lookup"><span data-stu-id="806d4-166">SShortArray</span></span>](sshortarray.md) <br/> |
|<span data-ttu-id="806d4-167">PT_MV_LONG</span><span class="sxs-lookup"><span data-stu-id="806d4-167">PT_MV_LONG</span></span>  <br/> |<span data-ttu-id="806d4-168">**MVI**</span><span class="sxs-lookup"><span data-stu-id="806d4-168">**MVI**</span></span> <br/> |[<span data-ttu-id="806d4-169">SLongArray</span><span class="sxs-lookup"><span data-stu-id="806d4-169">SLongArray</span></span>](slongarray.md) <br/> |
|<span data-ttu-id="806d4-170">PT_MV_R4</span><span class="sxs-lookup"><span data-stu-id="806d4-170">PT_MV_R4</span></span>  <br/> |<span data-ttu-id="806d4-171">**MVflt**</span><span class="sxs-lookup"><span data-stu-id="806d4-171">**MVflt**</span></span> <br/> |[<span data-ttu-id="806d4-172">SRealArray</span><span class="sxs-lookup"><span data-stu-id="806d4-172">SRealArray</span></span>](srealarray.md) <br/> |
|<span data-ttu-id="806d4-173">PT_MV_DOUBLE</span><span class="sxs-lookup"><span data-stu-id="806d4-173">PT_MV_DOUBLE</span></span>  <br/> |<span data-ttu-id="806d4-174">**MVdbl**</span><span class="sxs-lookup"><span data-stu-id="806d4-174">**MVdbl**</span></span> <br/> |[<span data-ttu-id="806d4-175">SDoubleArray</span><span class="sxs-lookup"><span data-stu-id="806d4-175">SDoubleArray</span></span>](sdoublearray.md) <br/> |
|<span data-ttu-id="806d4-176">PT_MV_CURRENCY</span><span class="sxs-lookup"><span data-stu-id="806d4-176">PT_MV_CURRENCY</span></span>  <br/> |<span data-ttu-id="806d4-177">**MVcur**</span><span class="sxs-lookup"><span data-stu-id="806d4-177">**MVcur**</span></span> <br/> |[<span data-ttu-id="806d4-178">SCurrencyArray</span><span class="sxs-lookup"><span data-stu-id="806d4-178">SCurrencyArray</span></span>](scurrencyarray.md) <br/> |
|<span data-ttu-id="806d4-179">PT_MV_APPTIME</span><span class="sxs-lookup"><span data-stu-id="806d4-179">PT_MV_APPTIME</span></span>  <br/> |<span data-ttu-id="806d4-180">**MVat**</span><span class="sxs-lookup"><span data-stu-id="806d4-180">**MVat**</span></span> <br/> |[<span data-ttu-id="806d4-181">SAppTimeArray</span><span class="sxs-lookup"><span data-stu-id="806d4-181">SAppTimeArray</span></span>](sapptimearray.md) <br/> |
|<span data-ttu-id="806d4-182">PT_MV_SYSTIME</span><span class="sxs-lookup"><span data-stu-id="806d4-182">PT_MV_SYSTIME</span></span>  <br/> |<span data-ttu-id="806d4-183">**MVft**</span><span class="sxs-lookup"><span data-stu-id="806d4-183">**MVft**</span></span> <br/> |[<span data-ttu-id="806d4-184">SDateTimeArray</span><span class="sxs-lookup"><span data-stu-id="806d4-184">SDateTimeArray</span></span>](sdatetimearray.md) <br/> |
|<span data-ttu-id="806d4-185">PT_MV_BINARY</span><span class="sxs-lookup"><span data-stu-id="806d4-185">PT_MV_BINARY</span></span>  <br/> |<span data-ttu-id="806d4-186">**MVbin**</span><span class="sxs-lookup"><span data-stu-id="806d4-186">**MVbin**</span></span> <br/> |[<span data-ttu-id="806d4-187">SBinaryArray</span><span class="sxs-lookup"><span data-stu-id="806d4-187">SBinaryArray</span></span>](sbinaryarray.md) <br/> |
|<span data-ttu-id="806d4-188">PT_MV_STRING8</span><span class="sxs-lookup"><span data-stu-id="806d4-188">PT_MV_STRING8</span></span>  <br/> |<span data-ttu-id="806d4-189">**MVszA**</span><span class="sxs-lookup"><span data-stu-id="806d4-189">**MVszA**</span></span> <br/> |[<span data-ttu-id="806d4-190">SLPSTRArray</span><span class="sxs-lookup"><span data-stu-id="806d4-190">SLPSTRArray</span></span>](slpstrarray.md) <br/> |
|<span data-ttu-id="806d4-191">PT_MV_UNICODE</span><span class="sxs-lookup"><span data-stu-id="806d4-191">PT_MV_UNICODE</span></span>  <br/> |<span data-ttu-id="806d4-192">**MVszW**</span><span class="sxs-lookup"><span data-stu-id="806d4-192">**MVszW**</span></span> <br/> |[<span data-ttu-id="806d4-193">SWStringArray</span><span class="sxs-lookup"><span data-stu-id="806d4-193">SWStringArray</span></span>](swstringarray.md) <br/> |
|<span data-ttu-id="806d4-194">PT_MV_CLSID</span><span class="sxs-lookup"><span data-stu-id="806d4-194">PT_MV_CLSID</span></span>  <br/> |<span data-ttu-id="806d4-195">**MVguid**</span><span class="sxs-lookup"><span data-stu-id="806d4-195">**MVguid**</span></span> <br/> |[<span data-ttu-id="806d4-196">SGuidArray</span><span class="sxs-lookup"><span data-stu-id="806d4-196">SGuidArray</span></span>](sguidarray.md) <br/> |
|<span data-ttu-id="806d4-197">PT_MV_I8</span><span class="sxs-lookup"><span data-stu-id="806d4-197">PT_MV_I8</span></span>  <br/> |<span data-ttu-id="806d4-198">**MVli**</span><span class="sxs-lookup"><span data-stu-id="806d4-198">**MVli**</span></span> <br/> |[<span data-ttu-id="806d4-199">SLargeIntegerArray</span><span class="sxs-lookup"><span data-stu-id="806d4-199">SLargeIntegerArray</span></span>](slargeintegerarray.md) <br/> |
|<span data-ttu-id="806d4-200">PT_ERROR</span><span class="sxs-lookup"><span data-stu-id="806d4-200">PT_ERROR</span></span>  <br/> |<span data-ttu-id="806d4-201">**err**</span><span class="sxs-lookup"><span data-stu-id="806d4-201">**err**</span></span> <br/> |[<span data-ttu-id="806d4-202">SCODE</span><span class="sxs-lookup"><span data-stu-id="806d4-202">SCODE</span></span>](scode.md) <br/> |
|<span data-ttu-id="806d4-203">PT_NULL 或 PT_OBJECT</span><span class="sxs-lookup"><span data-stu-id="806d4-203">PT_NULL or PT_OBJECT</span></span>  <br/> |<span data-ttu-id="806d4-204">**x**</span><span class="sxs-lookup"><span data-stu-id="806d4-204">**x**</span></span> <br/> |<span data-ttu-id="806d4-205">LONG</span><span class="sxs-lookup"><span data-stu-id="806d4-205">LONG</span></span>  <br/> |
|<span data-ttu-id="806d4-206">PT_PTR</span><span class="sxs-lookup"><span data-stu-id="806d4-206">PT_PTR</span></span>  <br/> |<span data-ttu-id="806d4-207">**lpv**</span><span class="sxs-lookup"><span data-stu-id="806d4-207">**lpv**</span></span> <br/> |<span data-ttu-id="806d4-208">作废\*</span><span class="sxs-lookup"><span data-stu-id="806d4-208">VOID \*</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="806d4-209">说明</span><span class="sxs-lookup"><span data-stu-id="806d4-209">Remarks</span></span>

<span data-ttu-id="806d4-210">**ulPropTag**成员由两部分组成:</span><span class="sxs-lookup"><span data-stu-id="806d4-210">The **ulPropTag** member is made up of two parts:</span></span> 
  
- <span data-ttu-id="806d4-211">高顺序16位中的标识符。</span><span class="sxs-lookup"><span data-stu-id="806d4-211">An identifier in the high-order 16 bits.</span></span>
    
- <span data-ttu-id="806d4-212">一个低序位16位的类型。</span><span class="sxs-lookup"><span data-stu-id="806d4-212">A type in the low-order 16 bits.</span></span>
    
<span data-ttu-id="806d4-213">标识符是在特定范围内的一个数字值。</span><span class="sxs-lookup"><span data-stu-id="806d4-213">The identifier is a numeric value within a particular range.</span></span> <span data-ttu-id="806d4-214">MAPI 为标识符定义范围, 以描述该属性的用途, 以及负责维护该属性的参与者。</span><span class="sxs-lookup"><span data-stu-id="806d4-214">MAPI defines ranges for identifiers to describe what the property is used for and who is responsible for maintaining it.</span></span> <span data-ttu-id="806d4-215">MAPI 为在 Mapitags 头文件中支持的每个属性标记定义约束。</span><span class="sxs-lookup"><span data-stu-id="806d4-215">MAPI defines constraints for each of the property tags that it supports in the Mapitags.h header file.</span></span>
  
<span data-ttu-id="806d4-216">类型指示属性值的格式。</span><span class="sxs-lookup"><span data-stu-id="806d4-216">The type indicates the format for the property's value.</span></span> <span data-ttu-id="806d4-217">MAPI 为它在 mapidefs.h 头文件中支持的每个属性类型定义常量。</span><span class="sxs-lookup"><span data-stu-id="806d4-217">MAPI defines constants for each of the property types that it supports in the Mapidefs.h header file.</span></span> 
  
<span data-ttu-id="806d4-218">有关标识符和属性类型的有效属性范围的完整列表, 请参阅[属性标识符和类型](property-identifiers-and-types.md)附录。</span><span class="sxs-lookup"><span data-stu-id="806d4-218">For a complete list of the valid property ranges for identifiers and property types, see the [Property Identifiers and Types](property-identifiers-and-types.md) appendix.</span></span> 
  
<span data-ttu-id="806d4-219">**dwAlignPad**成员用作填充, 以确保在需要8字节对齐方式的计算机上进行正确的对齐8字节值。</span><span class="sxs-lookup"><span data-stu-id="806d4-219">The **dwAlignPad** member is used as padding to make sure proper alignment on computers that require 8-byte alignment for 8-byte values.</span></span> <span data-ttu-id="806d4-220">在此类计算机上编写代码的开发人员应使用在8字节边界上分配**SPropValue**数组的内存分配例程。</span><span class="sxs-lookup"><span data-stu-id="806d4-220">Developers who write code on such computers should use memory allocation routines that allocate the **SPropValue** arrays on 8-byte boundaries.</span></span> 
  
<span data-ttu-id="806d4-221">有关详细信息, 请参阅[mapi 属性类型概述](mapi-property-type-overview.md)和[更新 mapi 属性](updating-mapi-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="806d4-221">For more information, see [MAPI Property Type Overview](mapi-property-type-overview.md) and [Updating MAPI Properties](updating-mapi-properties.md).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="806d4-222">另请参阅</span><span class="sxs-lookup"><span data-stu-id="806d4-222">See also</span></span>



[<span data-ttu-id="806d4-223">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="806d4-223">MAPI Structures</span></span>](mapi-structures.md)

