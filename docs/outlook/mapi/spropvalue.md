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
# <a name="spropvalue"></a><span data-ttu-id="d4c97-103">SPropValue</span><span class="sxs-lookup"><span data-stu-id="d4c97-103">SPropValue</span></span>

  
  
<span data-ttu-id="d4c97-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="d4c97-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="d4c97-105">描述 MAPI 属性。</span><span class="sxs-lookup"><span data-stu-id="d4c97-105">Describes a MAPI property.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="d4c97-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="d4c97-106">Header file:</span></span>  <br/> |<span data-ttu-id="d4c97-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="d4c97-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="d4c97-108">相关宏：</span><span class="sxs-lookup"><span data-stu-id="d4c97-108">Related macros:</span></span>  <br/> |<span data-ttu-id="d4c97-109">[](change_prop_type.md)CHANGE_PROP_TYPE、MVI_PROP、PROP_ID、PROP_TAG、PROP_TYPE [](prop_id.md) [](mvi_prop.md) [](prop_tag.md) [](prop_type.md)</span><span class="sxs-lookup"><span data-stu-id="d4c97-109">[CHANGE_PROP_TYPE](change_prop_type.md), [MVI_PROP](mvi_prop.md), [PROP_ID](prop_id.md), [PROP_TAG](prop_tag.md), [PROP_TYPE](prop_type.md)</span></span> <br/> |
   
```cpp
typedef struct _SPropValue
{
  ULONG ulPropTag;
  ULONG dwAlignPad;
  union _PV Value;
} SPropValue, FAR *LPSPropValue;

```

## <a name="members"></a><span data-ttu-id="d4c97-110">Members</span><span class="sxs-lookup"><span data-stu-id="d4c97-110">Members</span></span>

 <span data-ttu-id="d4c97-111">**ulPropTag**</span><span class="sxs-lookup"><span data-stu-id="d4c97-111">**ulPropTag**</span></span>
  
> <span data-ttu-id="d4c97-112">属性的属性标记。</span><span class="sxs-lookup"><span data-stu-id="d4c97-112">Property tag for the property.</span></span> <span data-ttu-id="d4c97-113">属性标记是 32 位无符号整数，由该属性在高顺序 16 位中的唯一标识符和低顺序 16 位中的属性类型组成。</span><span class="sxs-lookup"><span data-stu-id="d4c97-113">Property tags are 32-bit unsigned integers consisting of the property's unique identifier in the high-order 16 bits and the property's type in the low-order 16 bits.</span></span>
    
 <span data-ttu-id="d4c97-114">**dwAlignPad**</span><span class="sxs-lookup"><span data-stu-id="d4c97-114">**dwAlignPad**</span></span>
  
> <span data-ttu-id="d4c97-115">保留用于 MAPI;请勿使用。</span><span class="sxs-lookup"><span data-stu-id="d4c97-115">Reserved for MAPI; do not use.</span></span> 
    
 <span data-ttu-id="d4c97-116">**值**</span><span class="sxs-lookup"><span data-stu-id="d4c97-116">**Value**</span></span>
  
> <span data-ttu-id="d4c97-117">数据值联合，由属性类型指示的特定值。</span><span class="sxs-lookup"><span data-stu-id="d4c97-117">Union of data values, the specific value dictated by the property type.</span></span> <span data-ttu-id="d4c97-118">下表列出了每种属性类型、应该使用的联合成员及其关联的数据类型。</span><span class="sxs-lookup"><span data-stu-id="d4c97-118">The following table lists for each property type, the member of the union that should be used and its associated data type.</span></span>
    
|<span data-ttu-id="d4c97-119">**属性类型**</span><span class="sxs-lookup"><span data-stu-id="d4c97-119">**Property type**</span></span>|<span data-ttu-id="d4c97-120">**值**</span><span class="sxs-lookup"><span data-stu-id="d4c97-120">**Value**</span></span>|<span data-ttu-id="d4c97-121">**Value 的数据类型**</span><span class="sxs-lookup"><span data-stu-id="d4c97-121">**Data type of Value**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d4c97-122">PT_I2 或 PT_SHORT</span><span class="sxs-lookup"><span data-stu-id="d4c97-122">PT_I2 or PT_SHORT</span></span>  <br/> |<span data-ttu-id="d4c97-123">**i**</span><span class="sxs-lookup"><span data-stu-id="d4c97-123">**i**</span></span> <br/> |<span data-ttu-id="d4c97-124">short int</span><span class="sxs-lookup"><span data-stu-id="d4c97-124">short int</span></span>  <br/> |
|<span data-ttu-id="d4c97-125">PT_I4或PT_LONG (签名) </span><span class="sxs-lookup"><span data-stu-id="d4c97-125">PT_I4 or PT_LONG (signed)</span></span>  <br/> |<span data-ttu-id="d4c97-126">**l**</span><span class="sxs-lookup"><span data-stu-id="d4c97-126">**l**</span></span> <br/> |<span data-ttu-id="d4c97-127">LONG</span><span class="sxs-lookup"><span data-stu-id="d4c97-127">LONG</span></span>  <br/> |
|<span data-ttu-id="d4c97-128">PT_I4或PT_LONG (未签名) </span><span class="sxs-lookup"><span data-stu-id="d4c97-128">PT_I4 or PT_LONG (unsigned)</span></span>  <br/> |<span data-ttu-id="d4c97-129">**ul**</span><span class="sxs-lookup"><span data-stu-id="d4c97-129">**ul**</span></span> <br/> |<span data-ttu-id="d4c97-130">ULONG</span><span class="sxs-lookup"><span data-stu-id="d4c97-130">ULONG</span></span>  <br/> |
|<span data-ttu-id="d4c97-131">PT_R4 或 PT_FLOAT</span><span class="sxs-lookup"><span data-stu-id="d4c97-131">PT_R4 or PT_FLOAT</span></span>  <br/> |<span data-ttu-id="d4c97-132">**flt**</span><span class="sxs-lookup"><span data-stu-id="d4c97-132">**flt**</span></span> <br/> |<span data-ttu-id="d4c97-133">float</span><span class="sxs-lookup"><span data-stu-id="d4c97-133">float</span></span>  <br/> |
|<span data-ttu-id="d4c97-134">PT_R8 或 PT_DOUBLE</span><span class="sxs-lookup"><span data-stu-id="d4c97-134">PT_R8 or PT_DOUBLE</span></span>  <br/> |<span data-ttu-id="d4c97-135">**dbl**</span><span class="sxs-lookup"><span data-stu-id="d4c97-135">**dbl**</span></span> <br/> |<span data-ttu-id="d4c97-136">double</span><span class="sxs-lookup"><span data-stu-id="d4c97-136">double</span></span>  <br/> |
|<span data-ttu-id="d4c97-137">PT_BOOLEAN</span><span class="sxs-lookup"><span data-stu-id="d4c97-137">PT_BOOLEAN</span></span>  <br/> |<span data-ttu-id="d4c97-138">**b**</span><span class="sxs-lookup"><span data-stu-id="d4c97-138">**b**</span></span> <br/> |<span data-ttu-id="d4c97-139">unsigned short int</span><span class="sxs-lookup"><span data-stu-id="d4c97-139">unsigned short int</span></span>  <br/> |
|<span data-ttu-id="d4c97-140">PT_CURRENCY</span><span class="sxs-lookup"><span data-stu-id="d4c97-140">PT_CURRENCY</span></span>  <br/> |<span data-ttu-id="d4c97-141">**cur**</span><span class="sxs-lookup"><span data-stu-id="d4c97-141">**cur**</span></span> <br/> |[<span data-ttu-id="d4c97-142">CURRENCY</span><span class="sxs-lookup"><span data-stu-id="d4c97-142">CURRENCY</span></span>](currency.md) <br/> |
|<span data-ttu-id="d4c97-143">PT_APPTIME</span><span class="sxs-lookup"><span data-stu-id="d4c97-143">PT_APPTIME</span></span>  <br/> |<span data-ttu-id="d4c97-144">**at**</span><span class="sxs-lookup"><span data-stu-id="d4c97-144">**at**</span></span> <br/> |<span data-ttu-id="d4c97-145">double</span><span class="sxs-lookup"><span data-stu-id="d4c97-145">double</span></span>  <br/> |
|<span data-ttu-id="d4c97-146">PT_SYSTIME</span><span class="sxs-lookup"><span data-stu-id="d4c97-146">PT_SYSTIME</span></span>  <br/> |<span data-ttu-id="d4c97-147">**ft**</span><span class="sxs-lookup"><span data-stu-id="d4c97-147">**ft**</span></span> <br/> |[<span data-ttu-id="d4c97-148">FILETIME</span><span class="sxs-lookup"><span data-stu-id="d4c97-148">FILETIME</span></span>](filetime.md) <br/> |
|<span data-ttu-id="d4c97-149">PT_STRING8</span><span class="sxs-lookup"><span data-stu-id="d4c97-149">PT_STRING8</span></span>  <br/> |<span data-ttu-id="d4c97-150">**lpszA**</span><span class="sxs-lookup"><span data-stu-id="d4c97-150">**lpszA**</span></span> <br/> |<span data-ttu-id="d4c97-151">LPSTR</span><span class="sxs-lookup"><span data-stu-id="d4c97-151">LPSTR</span></span>  <br/> |
|<span data-ttu-id="d4c97-152">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="d4c97-152">PT_BINARY</span></span>  <br/> |<span data-ttu-id="d4c97-153">**bin**</span><span class="sxs-lookup"><span data-stu-id="d4c97-153">**bin**</span></span> <br/> |<span data-ttu-id="d4c97-154">BYTE [array]</span><span class="sxs-lookup"><span data-stu-id="d4c97-154">BYTE [array]</span></span>  <br/> |
|<span data-ttu-id="d4c97-155">PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="d4c97-155">PT_UNICODE</span></span>  <br/> |<span data-ttu-id="d4c97-156">**lpszW**</span><span class="sxs-lookup"><span data-stu-id="d4c97-156">**lpszW**</span></span> <br/> |<span data-ttu-id="d4c97-157">LPWSTR</span><span class="sxs-lookup"><span data-stu-id="d4c97-157">LPWSTR</span></span>  <br/> |
|<span data-ttu-id="d4c97-158">PT_CLSID</span><span class="sxs-lookup"><span data-stu-id="d4c97-158">PT_CLSID</span></span>  <br/> |<span data-ttu-id="d4c97-159">**lpguid**</span><span class="sxs-lookup"><span data-stu-id="d4c97-159">**lpguid**</span></span> <br/> |<span data-ttu-id="d4c97-160">LPGUID</span><span class="sxs-lookup"><span data-stu-id="d4c97-160">LPGUID</span></span>  <br/> |
|<span data-ttu-id="d4c97-161">PT_I8 或 PT_LONGLONG</span><span class="sxs-lookup"><span data-stu-id="d4c97-161">PT_I8 or PT_LONGLONG</span></span>  <br/> |<span data-ttu-id="d4c97-162">**li**</span><span class="sxs-lookup"><span data-stu-id="d4c97-162">**li**</span></span> <br/> |<span data-ttu-id="d4c97-163">**LARGE_INTEGER**</span><span class="sxs-lookup"><span data-stu-id="d4c97-163">**LARGE_INTEGER**</span></span> <br/> |
|<span data-ttu-id="d4c97-164">PT_MV_I2</span><span class="sxs-lookup"><span data-stu-id="d4c97-164">PT_MV_I2</span></span>  <br/> |<span data-ttu-id="d4c97-165">**MVi**</span><span class="sxs-lookup"><span data-stu-id="d4c97-165">**MVi**</span></span> <br/> |[<span data-ttu-id="d4c97-166">SShortArray</span><span class="sxs-lookup"><span data-stu-id="d4c97-166">SShortArray</span></span>](sshortarray.md) <br/> |
|<span data-ttu-id="d4c97-167">PT_MV_LONG</span><span class="sxs-lookup"><span data-stu-id="d4c97-167">PT_MV_LONG</span></span>  <br/> |<span data-ttu-id="d4c97-168">**MVI**</span><span class="sxs-lookup"><span data-stu-id="d4c97-168">**MVI**</span></span> <br/> |[<span data-ttu-id="d4c97-169">SLongArray</span><span class="sxs-lookup"><span data-stu-id="d4c97-169">SLongArray</span></span>](slongarray.md) <br/> |
|<span data-ttu-id="d4c97-170">PT_MV_R4</span><span class="sxs-lookup"><span data-stu-id="d4c97-170">PT_MV_R4</span></span>  <br/> |<span data-ttu-id="d4c97-171">**MLt**</span><span class="sxs-lookup"><span data-stu-id="d4c97-171">**MVflt**</span></span> <br/> |[<span data-ttu-id="d4c97-172">SRealArray</span><span class="sxs-lookup"><span data-stu-id="d4c97-172">SRealArray</span></span>](srealarray.md) <br/> |
|<span data-ttu-id="d4c97-173">PT_MV_DOUBLE</span><span class="sxs-lookup"><span data-stu-id="d4c97-173">PT_MV_DOUBLE</span></span>  <br/> |<span data-ttu-id="d4c97-174">**MVdbl**</span><span class="sxs-lookup"><span data-stu-id="d4c97-174">**MVdbl**</span></span> <br/> |[<span data-ttu-id="d4c97-175">SDoubleArray</span><span class="sxs-lookup"><span data-stu-id="d4c97-175">SDoubleArray</span></span>](sdoublearray.md) <br/> |
|<span data-ttu-id="d4c97-176">PT_MV_CURRENCY</span><span class="sxs-lookup"><span data-stu-id="d4c97-176">PT_MV_CURRENCY</span></span>  <br/> |<span data-ttu-id="d4c97-177">**MVcur**</span><span class="sxs-lookup"><span data-stu-id="d4c97-177">**MVcur**</span></span> <br/> |[<span data-ttu-id="d4c97-178">SCurrencyArray</span><span class="sxs-lookup"><span data-stu-id="d4c97-178">SCurrencyArray</span></span>](scurrencyarray.md) <br/> |
|<span data-ttu-id="d4c97-179">PT_MV_APPTIME</span><span class="sxs-lookup"><span data-stu-id="d4c97-179">PT_MV_APPTIME</span></span>  <br/> |<span data-ttu-id="d4c97-180">**MVat**</span><span class="sxs-lookup"><span data-stu-id="d4c97-180">**MVat**</span></span> <br/> |[<span data-ttu-id="d4c97-181">SAppTimeArray</span><span class="sxs-lookup"><span data-stu-id="d4c97-181">SAppTimeArray</span></span>](sapptimearray.md) <br/> |
|<span data-ttu-id="d4c97-182">PT_MV_SYSTIME</span><span class="sxs-lookup"><span data-stu-id="d4c97-182">PT_MV_SYSTIME</span></span>  <br/> |<span data-ttu-id="d4c97-183">**MVft**</span><span class="sxs-lookup"><span data-stu-id="d4c97-183">**MVft**</span></span> <br/> |[<span data-ttu-id="d4c97-184">SDateTimeArray</span><span class="sxs-lookup"><span data-stu-id="d4c97-184">SDateTimeArray</span></span>](sdatetimearray.md) <br/> |
|<span data-ttu-id="d4c97-185">PT_MV_BINARY</span><span class="sxs-lookup"><span data-stu-id="d4c97-185">PT_MV_BINARY</span></span>  <br/> |<span data-ttu-id="d4c97-186">**MVbin**</span><span class="sxs-lookup"><span data-stu-id="d4c97-186">**MVbin**</span></span> <br/> |[<span data-ttu-id="d4c97-187">SBinaryArray</span><span class="sxs-lookup"><span data-stu-id="d4c97-187">SBinaryArray</span></span>](sbinaryarray.md) <br/> |
|<span data-ttu-id="d4c97-188">PT_MV_STRING8</span><span class="sxs-lookup"><span data-stu-id="d4c97-188">PT_MV_STRING8</span></span>  <br/> |<span data-ttu-id="d4c97-189">**MVszA**</span><span class="sxs-lookup"><span data-stu-id="d4c97-189">**MVszA**</span></span> <br/> |[<span data-ttu-id="d4c97-190">SLPSTRArray</span><span class="sxs-lookup"><span data-stu-id="d4c97-190">SLPSTRArray</span></span>](slpstrarray.md) <br/> |
|<span data-ttu-id="d4c97-191">PT_MV_UNICODE</span><span class="sxs-lookup"><span data-stu-id="d4c97-191">PT_MV_UNICODE</span></span>  <br/> |<span data-ttu-id="d4c97-192">**MVszW**</span><span class="sxs-lookup"><span data-stu-id="d4c97-192">**MVszW**</span></span> <br/> |[<span data-ttu-id="d4c97-193">SWStringArray</span><span class="sxs-lookup"><span data-stu-id="d4c97-193">SWStringArray</span></span>](swstringarray.md) <br/> |
|<span data-ttu-id="d4c97-194">PT_MV_CLSID</span><span class="sxs-lookup"><span data-stu-id="d4c97-194">PT_MV_CLSID</span></span>  <br/> |<span data-ttu-id="d4c97-195">**MVguid**</span><span class="sxs-lookup"><span data-stu-id="d4c97-195">**MVguid**</span></span> <br/> |[<span data-ttu-id="d4c97-196">SGuidArray</span><span class="sxs-lookup"><span data-stu-id="d4c97-196">SGuidArray</span></span>](sguidarray.md) <br/> |
|<span data-ttu-id="d4c97-197">PT_MV_I8</span><span class="sxs-lookup"><span data-stu-id="d4c97-197">PT_MV_I8</span></span>  <br/> |<span data-ttu-id="d4c97-198">**MVli**</span><span class="sxs-lookup"><span data-stu-id="d4c97-198">**MVli**</span></span> <br/> |[<span data-ttu-id="d4c97-199">SLargeIntegerArray</span><span class="sxs-lookup"><span data-stu-id="d4c97-199">SLargeIntegerArray</span></span>](slargeintegerarray.md) <br/> |
|<span data-ttu-id="d4c97-200">PT_ERROR</span><span class="sxs-lookup"><span data-stu-id="d4c97-200">PT_ERROR</span></span>  <br/> |<span data-ttu-id="d4c97-201">**err**</span><span class="sxs-lookup"><span data-stu-id="d4c97-201">**err**</span></span> <br/> |[<span data-ttu-id="d4c97-202">SCODE</span><span class="sxs-lookup"><span data-stu-id="d4c97-202">SCODE</span></span>](scode.md) <br/> |
|<span data-ttu-id="d4c97-203">PT_NULL 或 PT_OBJECT</span><span class="sxs-lookup"><span data-stu-id="d4c97-203">PT_NULL or PT_OBJECT</span></span>  <br/> |<span data-ttu-id="d4c97-204">**x**</span><span class="sxs-lookup"><span data-stu-id="d4c97-204">**x**</span></span> <br/> |<span data-ttu-id="d4c97-205">LONG</span><span class="sxs-lookup"><span data-stu-id="d4c97-205">LONG</span></span>  <br/> |
|<span data-ttu-id="d4c97-206">PT_PTR</span><span class="sxs-lookup"><span data-stu-id="d4c97-206">PT_PTR</span></span>  <br/> |<span data-ttu-id="d4c97-207">**lpv**</span><span class="sxs-lookup"><span data-stu-id="d4c97-207">**lpv**</span></span> <br/> |<span data-ttu-id="d4c97-208">VOID \*</span><span class="sxs-lookup"><span data-stu-id="d4c97-208">VOID \*</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="d4c97-209">备注</span><span class="sxs-lookup"><span data-stu-id="d4c97-209">Remarks</span></span>

<span data-ttu-id="d4c97-210">**ulPropTag** 成员由两部分组成：</span><span class="sxs-lookup"><span data-stu-id="d4c97-210">The **ulPropTag** member is made up of two parts:</span></span> 
  
- <span data-ttu-id="d4c97-211">高顺序 16 位中的标识符。</span><span class="sxs-lookup"><span data-stu-id="d4c97-211">An identifier in the high-order 16 bits.</span></span>
    
- <span data-ttu-id="d4c97-212">低顺序 16 位中的类型。</span><span class="sxs-lookup"><span data-stu-id="d4c97-212">A type in the low-order 16 bits.</span></span>
    
<span data-ttu-id="d4c97-213">标识符是特定范围内的数值。</span><span class="sxs-lookup"><span data-stu-id="d4c97-213">The identifier is a numeric value within a particular range.</span></span> <span data-ttu-id="d4c97-214">MAPI 为标识符定义范围，以描述属性用于什么以及谁负责维护它。</span><span class="sxs-lookup"><span data-stu-id="d4c97-214">MAPI defines ranges for identifiers to describe what the property is used for and who is responsible for maintaining it.</span></span> <span data-ttu-id="d4c97-215">MAPI 为 Mapitags.h 头文件中支持的每个属性标记定义约束。</span><span class="sxs-lookup"><span data-stu-id="d4c97-215">MAPI defines constraints for each of the property tags that it supports in the Mapitags.h header file.</span></span>
  
<span data-ttu-id="d4c97-216">类型指示属性值的格式。</span><span class="sxs-lookup"><span data-stu-id="d4c97-216">The type indicates the format for the property's value.</span></span> <span data-ttu-id="d4c97-217">MAPI 为 Mapidefs.h 头文件中支持的每个属性类型定义常量。</span><span class="sxs-lookup"><span data-stu-id="d4c97-217">MAPI defines constants for each of the property types that it supports in the Mapidefs.h header file.</span></span> 
  
<span data-ttu-id="d4c97-218">有关标识符和属性类型的有效属性范围的完整列表，请参阅属性 [标识符和类型](property-identifiers-and-types.md) 附录。</span><span class="sxs-lookup"><span data-stu-id="d4c97-218">For a complete list of the valid property ranges for identifiers and property types, see the [Property Identifiers and Types](property-identifiers-and-types.md) appendix.</span></span> 
  
<span data-ttu-id="d4c97-219">**dwAlignPad** 成员用作填充，以确保在需要 8 字节对齐的 8 字节值的计算机上正确对齐。</span><span class="sxs-lookup"><span data-stu-id="d4c97-219">The **dwAlignPad** member is used as padding to make sure proper alignment on computers that require 8-byte alignment for 8-byte values.</span></span> <span data-ttu-id="d4c97-220">在此类计算机上编写代码的开发人员应该使用在 8 字节边界上分配 **SPropValue** 数组的内存分配例程。</span><span class="sxs-lookup"><span data-stu-id="d4c97-220">Developers who write code on such computers should use memory allocation routines that allocate the **SPropValue** arrays on 8-byte boundaries.</span></span> 
  
<span data-ttu-id="d4c97-221">有关详细信息，请参阅[MAPI 属性类型概述](mapi-property-type-overview.md)[和更新 MAPI 属性](updating-mapi-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="d4c97-221">For more information, see [MAPI Property Type Overview](mapi-property-type-overview.md) and [Updating MAPI Properties](updating-mapi-properties.md).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="d4c97-222">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d4c97-222">See also</span></span>



[<span data-ttu-id="d4c97-223">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="d4c97-223">MAPI Structures</span></span>](mapi-structures.md)

