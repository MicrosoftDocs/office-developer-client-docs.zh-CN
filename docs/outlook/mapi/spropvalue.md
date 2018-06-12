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
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: f378bdd473410b846328cbe1f911eba9401f88cf
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778872"
---
# <a name="spropvalue"></a><span data-ttu-id="2f405-103">SPropValue</span><span class="sxs-lookup"><span data-stu-id="2f405-103">SPropValue</span></span>

  
  
<span data-ttu-id="2f405-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="2f405-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="2f405-105">描述的 MAPI 属性。</span><span class="sxs-lookup"><span data-stu-id="2f405-105">Describes a MAPI property.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="2f405-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="2f405-106">Header file:</span></span>  <br/> |<span data-ttu-id="2f405-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="2f405-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="2f405-108">相关的宏：</span><span class="sxs-lookup"><span data-stu-id="2f405-108">Related macros:</span></span>  <br/> |<span data-ttu-id="2f405-109">[CHANGE_PROP_TYPE](change_prop_type.md)、 [MVI_PROP](mvi_prop.md)、 [PROP_ID](prop_id.md)、 [PROP_TAG](prop_tag.md)、 [PROP_TYPE](prop_type.md)</span><span class="sxs-lookup"><span data-stu-id="2f405-109">[CHANGE_PROP_TYPE](change_prop_type.md), [MVI_PROP](mvi_prop.md), [PROP_ID](prop_id.md), [PROP_TAG](prop_tag.md), [PROP_TYPE](prop_type.md)</span></span> <br/> |
   
```cpp
typedef struct _SPropValue
{
  ULONG ulPropTag;
  ULONG dwAlignPad;
  union _PV Value;
} SPropValue, FAR *LPSPropValue;

```

## <a name="members"></a><span data-ttu-id="2f405-110">成员</span><span class="sxs-lookup"><span data-stu-id="2f405-110">Members</span></span>

 <span data-ttu-id="2f405-111">**ulPropTag**</span><span class="sxs-lookup"><span data-stu-id="2f405-111">**ulPropTag**</span></span>
  
> <span data-ttu-id="2f405-112">属性标记属性。</span><span class="sxs-lookup"><span data-stu-id="2f405-112">Property tag for the property.</span></span> <span data-ttu-id="2f405-113">属性标记是 32 位无符号的整数组成的属性中高阶 16 位的唯一标识符和低序位 16 位中的该属性的类型。</span><span class="sxs-lookup"><span data-stu-id="2f405-113">Property tags are 32-bit unsigned integers consisting of the property's unique identifier in the high-order 16 bits and the property's type in the low-order 16 bits.</span></span>
    
 <span data-ttu-id="2f405-114">**dwAlignPad**</span><span class="sxs-lookup"><span data-stu-id="2f405-114">**dwAlignPad**</span></span>
  
> <span data-ttu-id="2f405-115">供 MAPI;不要使用。</span><span class="sxs-lookup"><span data-stu-id="2f405-115">Reserved for MAPI; do not use.</span></span> 
    
 <span data-ttu-id="2f405-116">**值**</span><span class="sxs-lookup"><span data-stu-id="2f405-116">**Value**</span></span>
  
> <span data-ttu-id="2f405-117">联合的数据值，指明属性类型的特定值。</span><span class="sxs-lookup"><span data-stu-id="2f405-117">Union of data values, the specific value dictated by the property type.</span></span> <span data-ttu-id="2f405-118">下表列出了针对每个属性类型、 联合应使用的成员和其关联的数据类型。</span><span class="sxs-lookup"><span data-stu-id="2f405-118">The following table lists for each property type, the member of the union that should be used and its associated data type.</span></span>
    
|<span data-ttu-id="2f405-119">**属性类型**</span><span class="sxs-lookup"><span data-stu-id="2f405-119">**Property type**</span></span>|<span data-ttu-id="2f405-120">**值**</span><span class="sxs-lookup"><span data-stu-id="2f405-120">**Value**</span></span>|<span data-ttu-id="2f405-121">**值的数据类型**</span><span class="sxs-lookup"><span data-stu-id="2f405-121">**Data type of Value**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="2f405-122">PT_I2 或 PT_SHORT</span><span class="sxs-lookup"><span data-stu-id="2f405-122">PT_I2 or PT_SHORT</span></span>  <br/> |<span data-ttu-id="2f405-123">**我**</span><span class="sxs-lookup"><span data-stu-id="2f405-123">**i**</span></span> <br/> |<span data-ttu-id="2f405-124">短 int</span><span class="sxs-lookup"><span data-stu-id="2f405-124">short int</span></span>  <br/> |
|<span data-ttu-id="2f405-125">PT_I4 或 PT_LONG （签名）</span><span class="sxs-lookup"><span data-stu-id="2f405-125">PT_I4 or PT_LONG (signed)</span></span>  <br/> |<span data-ttu-id="2f405-126">**l**</span><span class="sxs-lookup"><span data-stu-id="2f405-126">**l**</span></span> <br/> |<span data-ttu-id="2f405-127">长</span><span class="sxs-lookup"><span data-stu-id="2f405-127">LONG</span></span>  <br/> |
|<span data-ttu-id="2f405-128">PT_I4 或 PT_LONG （无符号）</span><span class="sxs-lookup"><span data-stu-id="2f405-128">PT_I4 or PT_LONG (unsigned)</span></span>  <br/> |<span data-ttu-id="2f405-129">**ul**</span><span class="sxs-lookup"><span data-stu-id="2f405-129">**ul**</span></span> <br/> |<span data-ttu-id="2f405-130">ULONG</span><span class="sxs-lookup"><span data-stu-id="2f405-130">ULONG</span></span>  <br/> |
|<span data-ttu-id="2f405-131">PT_R4 或 PT_FLOAT</span><span class="sxs-lookup"><span data-stu-id="2f405-131">PT_R4 or PT_FLOAT</span></span>  <br/> |<span data-ttu-id="2f405-132">**flt**</span><span class="sxs-lookup"><span data-stu-id="2f405-132">**flt**</span></span> <br/> |<span data-ttu-id="2f405-133">float</span><span class="sxs-lookup"><span data-stu-id="2f405-133">float</span></span>  <br/> |
|<span data-ttu-id="2f405-134">PT_R8 或 PT_DOUBLE</span><span class="sxs-lookup"><span data-stu-id="2f405-134">PT_R8 or PT_DOUBLE</span></span>  <br/> |<span data-ttu-id="2f405-135">**双**</span><span class="sxs-lookup"><span data-stu-id="2f405-135">**dbl**</span></span> <br/> |<span data-ttu-id="2f405-136">double</span><span class="sxs-lookup"><span data-stu-id="2f405-136">double</span></span>  <br/> |
|<span data-ttu-id="2f405-137">PT_BOOLEAN</span><span class="sxs-lookup"><span data-stu-id="2f405-137">PT_BOOLEAN</span></span>  <br/> |<span data-ttu-id="2f405-138">**b**</span><span class="sxs-lookup"><span data-stu-id="2f405-138">**b**</span></span> <br/> |<span data-ttu-id="2f405-139">未签署的简短 int</span><span class="sxs-lookup"><span data-stu-id="2f405-139">unsigned short int</span></span>  <br/> |
|<span data-ttu-id="2f405-140">PT_CURRENCY</span><span class="sxs-lookup"><span data-stu-id="2f405-140">PT_CURRENCY</span></span>  <br/> |<span data-ttu-id="2f405-141">**当前**</span><span class="sxs-lookup"><span data-stu-id="2f405-141">**cur**</span></span> <br/> |[<span data-ttu-id="2f405-142">货币</span><span class="sxs-lookup"><span data-stu-id="2f405-142">CURRENCY</span></span>](currency.md) <br/> |
|<span data-ttu-id="2f405-143">PT_APPTIME</span><span class="sxs-lookup"><span data-stu-id="2f405-143">PT_APPTIME</span></span>  <br/> |<span data-ttu-id="2f405-144">**在**</span><span class="sxs-lookup"><span data-stu-id="2f405-144">**at**</span></span> <br/> |<span data-ttu-id="2f405-145">double</span><span class="sxs-lookup"><span data-stu-id="2f405-145">double</span></span>  <br/> |
|<span data-ttu-id="2f405-146">PT_SYSTIME</span><span class="sxs-lookup"><span data-stu-id="2f405-146">PT_SYSTIME</span></span>  <br/> |<span data-ttu-id="2f405-147">**ft**</span><span class="sxs-lookup"><span data-stu-id="2f405-147">**ft**</span></span> <br/> |[<span data-ttu-id="2f405-148">FILETIME</span><span class="sxs-lookup"><span data-stu-id="2f405-148">FILETIME</span></span>](filetime.md) <br/> |
|<span data-ttu-id="2f405-149">PT_STRING8</span><span class="sxs-lookup"><span data-stu-id="2f405-149">PT_STRING8</span></span>  <br/> |<span data-ttu-id="2f405-150">**lpszA**</span><span class="sxs-lookup"><span data-stu-id="2f405-150">**lpszA**</span></span> <br/> |<span data-ttu-id="2f405-151">LPSTR</span><span class="sxs-lookup"><span data-stu-id="2f405-151">LPSTR</span></span>  <br/> |
|<span data-ttu-id="2f405-152">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="2f405-152">PT_BINARY</span></span>  <br/> |<span data-ttu-id="2f405-153">**回收站**</span><span class="sxs-lookup"><span data-stu-id="2f405-153">**bin**</span></span> <br/> |<span data-ttu-id="2f405-154">字节 [数组]</span><span class="sxs-lookup"><span data-stu-id="2f405-154">BYTE [array]</span></span>  <br/> |
|<span data-ttu-id="2f405-155">PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="2f405-155">PT_UNICODE</span></span>  <br/> |<span data-ttu-id="2f405-156">**lpszW**</span><span class="sxs-lookup"><span data-stu-id="2f405-156">**lpszW**</span></span> <br/> |<span data-ttu-id="2f405-157">LPWSTR</span><span class="sxs-lookup"><span data-stu-id="2f405-157">LPWSTR</span></span>  <br/> |
|<span data-ttu-id="2f405-158">PT_CLSID</span><span class="sxs-lookup"><span data-stu-id="2f405-158">PT_CLSID</span></span>  <br/> |<span data-ttu-id="2f405-159">**lpguid**</span><span class="sxs-lookup"><span data-stu-id="2f405-159">**lpguid**</span></span> <br/> |<span data-ttu-id="2f405-160">LPGUID</span><span class="sxs-lookup"><span data-stu-id="2f405-160">LPGUID</span></span>  <br/> |
|<span data-ttu-id="2f405-161">PT_I8 或 PT_LONGLONG</span><span class="sxs-lookup"><span data-stu-id="2f405-161">PT_I8 or PT_LONGLONG</span></span>  <br/> |<span data-ttu-id="2f405-162">**li**</span><span class="sxs-lookup"><span data-stu-id="2f405-162">**li**</span></span> <br/> |<span data-ttu-id="2f405-163">**LARGE_INTEGER**</span><span class="sxs-lookup"><span data-stu-id="2f405-163">**LARGE_INTEGER**</span></span> <br/> |
|<span data-ttu-id="2f405-164">PT_MV_I2</span><span class="sxs-lookup"><span data-stu-id="2f405-164">PT_MV_I2</span></span>  <br/> |<span data-ttu-id="2f405-165">**MVi**</span><span class="sxs-lookup"><span data-stu-id="2f405-165">**MVi**</span></span> <br/> |[<span data-ttu-id="2f405-166">SShortArray</span><span class="sxs-lookup"><span data-stu-id="2f405-166">SShortArray</span></span>](sshortarray.md) <br/> |
|<span data-ttu-id="2f405-167">PT_MV_LONG</span><span class="sxs-lookup"><span data-stu-id="2f405-167">PT_MV_LONG</span></span>  <br/> |<span data-ttu-id="2f405-168">**MVI**</span><span class="sxs-lookup"><span data-stu-id="2f405-168">**MVI**</span></span> <br/> |[<span data-ttu-id="2f405-169">SLongArray</span><span class="sxs-lookup"><span data-stu-id="2f405-169">SLongArray</span></span>](slongarray.md) <br/> |
|<span data-ttu-id="2f405-170">PT_MV_R4</span><span class="sxs-lookup"><span data-stu-id="2f405-170">PT_MV_R4</span></span>  <br/> |<span data-ttu-id="2f405-171">**MVflt**</span><span class="sxs-lookup"><span data-stu-id="2f405-171">**MVflt**</span></span> <br/> |[<span data-ttu-id="2f405-172">SRealArray</span><span class="sxs-lookup"><span data-stu-id="2f405-172">SRealArray</span></span>](srealarray.md) <br/> |
|<span data-ttu-id="2f405-173">PT_MV_DOUBLE</span><span class="sxs-lookup"><span data-stu-id="2f405-173">PT_MV_DOUBLE</span></span>  <br/> |<span data-ttu-id="2f405-174">**MVdbl**</span><span class="sxs-lookup"><span data-stu-id="2f405-174">**MVdbl**</span></span> <br/> |[<span data-ttu-id="2f405-175">SDoubleArray</span><span class="sxs-lookup"><span data-stu-id="2f405-175">SDoubleArray</span></span>](sdoublearray.md) <br/> |
|<span data-ttu-id="2f405-176">PT_MV_CURRENCY</span><span class="sxs-lookup"><span data-stu-id="2f405-176">PT_MV_CURRENCY</span></span>  <br/> |<span data-ttu-id="2f405-177">**MVcur**</span><span class="sxs-lookup"><span data-stu-id="2f405-177">**MVcur**</span></span> <br/> |[<span data-ttu-id="2f405-178">SCurrencyArray</span><span class="sxs-lookup"><span data-stu-id="2f405-178">SCurrencyArray</span></span>](scurrencyarray.md) <br/> |
|<span data-ttu-id="2f405-179">PT_MV_APPTIME</span><span class="sxs-lookup"><span data-stu-id="2f405-179">PT_MV_APPTIME</span></span>  <br/> |<span data-ttu-id="2f405-180">**MVat**</span><span class="sxs-lookup"><span data-stu-id="2f405-180">**MVat**</span></span> <br/> |[<span data-ttu-id="2f405-181">SAppTimeArray</span><span class="sxs-lookup"><span data-stu-id="2f405-181">SAppTimeArray</span></span>](sapptimearray.md) <br/> |
|<span data-ttu-id="2f405-182">PT_MV_SYSTIME</span><span class="sxs-lookup"><span data-stu-id="2f405-182">PT_MV_SYSTIME</span></span>  <br/> |<span data-ttu-id="2f405-183">**MVft**</span><span class="sxs-lookup"><span data-stu-id="2f405-183">**MVft**</span></span> <br/> |[<span data-ttu-id="2f405-184">SDateTimeArray</span><span class="sxs-lookup"><span data-stu-id="2f405-184">SDateTimeArray</span></span>](sdatetimearray.md) <br/> |
|<span data-ttu-id="2f405-185">PT_MV_BINARY</span><span class="sxs-lookup"><span data-stu-id="2f405-185">PT_MV_BINARY</span></span>  <br/> |<span data-ttu-id="2f405-186">**MVbin**</span><span class="sxs-lookup"><span data-stu-id="2f405-186">**MVbin**</span></span> <br/> |[<span data-ttu-id="2f405-187">SBinaryArray</span><span class="sxs-lookup"><span data-stu-id="2f405-187">SBinaryArray</span></span>](sbinaryarray.md) <br/> |
|<span data-ttu-id="2f405-188">PT_MV_STRING8</span><span class="sxs-lookup"><span data-stu-id="2f405-188">PT_MV_STRING8</span></span>  <br/> |<span data-ttu-id="2f405-189">**MVszA**</span><span class="sxs-lookup"><span data-stu-id="2f405-189">**MVszA**</span></span> <br/> |[<span data-ttu-id="2f405-190">SLPSTRArray</span><span class="sxs-lookup"><span data-stu-id="2f405-190">SLPSTRArray</span></span>](slpstrarray.md) <br/> |
|<span data-ttu-id="2f405-191">PT_MV_UNICODE</span><span class="sxs-lookup"><span data-stu-id="2f405-191">PT_MV_UNICODE</span></span>  <br/> |<span data-ttu-id="2f405-192">**MVszW**</span><span class="sxs-lookup"><span data-stu-id="2f405-192">**MVszW**</span></span> <br/> |[<span data-ttu-id="2f405-193">SWStringArray</span><span class="sxs-lookup"><span data-stu-id="2f405-193">SWStringArray</span></span>](swstringarray.md) <br/> |
|<span data-ttu-id="2f405-194">PT_MV_CLSID</span><span class="sxs-lookup"><span data-stu-id="2f405-194">PT_MV_CLSID</span></span>  <br/> |<span data-ttu-id="2f405-195">**MVguid**</span><span class="sxs-lookup"><span data-stu-id="2f405-195">**MVguid**</span></span> <br/> |[<span data-ttu-id="2f405-196">SGuidArray</span><span class="sxs-lookup"><span data-stu-id="2f405-196">SGuidArray</span></span>](sguidarray.md) <br/> |
|<span data-ttu-id="2f405-197">PT_MV_I8</span><span class="sxs-lookup"><span data-stu-id="2f405-197">PT_MV_I8</span></span>  <br/> |<span data-ttu-id="2f405-198">**MVli**</span><span class="sxs-lookup"><span data-stu-id="2f405-198">**MVli**</span></span> <br/> |[<span data-ttu-id="2f405-199">SLargeIntegerArray</span><span class="sxs-lookup"><span data-stu-id="2f405-199">SLargeIntegerArray</span></span>](slargeintegerarray.md) <br/> |
|<span data-ttu-id="2f405-200">PT_ERROR</span><span class="sxs-lookup"><span data-stu-id="2f405-200">PT_ERROR</span></span>  <br/> |<span data-ttu-id="2f405-201">**err**</span><span class="sxs-lookup"><span data-stu-id="2f405-201">**err**</span></span> <br/> |[<span data-ttu-id="2f405-202">SCODE</span><span class="sxs-lookup"><span data-stu-id="2f405-202">SCODE</span></span>](scode.md) <br/> |
|<span data-ttu-id="2f405-203">PT_NULL 或 PT_OBJECT</span><span class="sxs-lookup"><span data-stu-id="2f405-203">PT_NULL or PT_OBJECT</span></span>  <br/> |<span data-ttu-id="2f405-204">**x**</span><span class="sxs-lookup"><span data-stu-id="2f405-204">**x**</span></span> <br/> |<span data-ttu-id="2f405-205">长</span><span class="sxs-lookup"><span data-stu-id="2f405-205">LONG</span></span>  <br/> |
|<span data-ttu-id="2f405-206">PT_PTR</span><span class="sxs-lookup"><span data-stu-id="2f405-206">PT_PTR</span></span>  <br/> |<span data-ttu-id="2f405-207">**lpv**</span><span class="sxs-lookup"><span data-stu-id="2f405-207">**lpv**</span></span> <br/> |<span data-ttu-id="2f405-208">VOID\*</span><span class="sxs-lookup"><span data-stu-id="2f405-208">VOID \*</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="2f405-209">备注</span><span class="sxs-lookup"><span data-stu-id="2f405-209">Remarks</span></span>

<span data-ttu-id="2f405-210">**UlPropTag**成员由两部分组成：</span><span class="sxs-lookup"><span data-stu-id="2f405-210">The **ulPropTag** member is made up of two parts:</span></span> 
  
- <span data-ttu-id="2f405-211">中高阶 16 位的标识符。</span><span class="sxs-lookup"><span data-stu-id="2f405-211">An identifier in the high-order 16 bits.</span></span>
    
- <span data-ttu-id="2f405-212">低序位 16 位中的类型。</span><span class="sxs-lookup"><span data-stu-id="2f405-212">A type in the low-order 16 bits.</span></span>
    
<span data-ttu-id="2f405-213">标识符是一个数值在特定范围内。</span><span class="sxs-lookup"><span data-stu-id="2f405-213">The identifier is a numeric value within a particular range.</span></span> <span data-ttu-id="2f405-214">MAPI 定义标识符来描述属性用于和谁负责维护它的区域。</span><span class="sxs-lookup"><span data-stu-id="2f405-214">MAPI defines ranges for identifiers to describe what the property is used for and who is responsible for maintaining it.</span></span> <span data-ttu-id="2f405-215">MAPI 属性标记它 Mapitags.h 头文件中所支持的每个定义的约束。</span><span class="sxs-lookup"><span data-stu-id="2f405-215">MAPI defines constraints for each of the property tags that it supports in the Mapitags.h header file.</span></span>
  
<span data-ttu-id="2f405-216">该类型指示该属性的值的格式。</span><span class="sxs-lookup"><span data-stu-id="2f405-216">The type indicates the format for the property's value.</span></span> <span data-ttu-id="2f405-217">MAPI 的属性类型，它支持 Mapidefs.h 头文件中的每个定义的常数。</span><span class="sxs-lookup"><span data-stu-id="2f405-217">MAPI defines constants for each of the property types that it supports in the Mapidefs.h header file.</span></span> 
  
<span data-ttu-id="2f405-218">标识符和属性类型的有效属性范围的完整列表，请参阅附录[属性标识符和类型](property-identifiers-and-types.md)。</span><span class="sxs-lookup"><span data-stu-id="2f405-218">For a complete list of the valid property ranges for identifiers and property types, see the [Property Identifiers and Types](property-identifiers-and-types.md) appendix.</span></span> 
  
<span data-ttu-id="2f405-219">**DwAlignPad**成员作为填充使用，以确保正确的对齐方式为 8 字节值需要 8 字节对齐的计算机上。</span><span class="sxs-lookup"><span data-stu-id="2f405-219">The **dwAlignPad** member is used as padding to make sure proper alignment on computers that require 8-byte alignment for 8-byte values.</span></span> <span data-ttu-id="2f405-220">开发人员编写代码在该计算机上应使用分配**SPropValue**数组 8 字节边界上的内存分配例程。</span><span class="sxs-lookup"><span data-stu-id="2f405-220">Developers who write code on such computers should use memory allocation routines that allocate the **SPropValue** arrays on 8-byte boundaries.</span></span> 
  
<span data-ttu-id="2f405-221">有关详细信息，请参阅[MAPI 属性类型概述](mapi-property-type-overview.md)和[更新 MAPI 属性](updating-mapi-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="2f405-221">For more information, see [MAPI Property Type Overview](mapi-property-type-overview.md) and [Updating MAPI Properties](updating-mapi-properties.md).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="2f405-222">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2f405-222">See also</span></span>



[<span data-ttu-id="2f405-223">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="2f405-223">MAPI Structures</span></span>](mapi-structures.md)

