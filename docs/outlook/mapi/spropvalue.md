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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32326584"
---
# <a name="spropvalue"></a><span data-ttu-id="4b4f0-103">SPropValue</span><span class="sxs-lookup"><span data-stu-id="4b4f0-103">SPropValue</span></span>

  
  
<span data-ttu-id="4b4f0-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="4b4f0-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="4b4f0-105">描述 MAPI 属性。</span><span class="sxs-lookup"><span data-stu-id="4b4f0-105">Describes a MAPI property.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="4b4f0-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="4b4f0-106">Header file:</span></span>  <br/> |<span data-ttu-id="4b4f0-107">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="4b4f0-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="4b4f0-108">相关宏:</span><span class="sxs-lookup"><span data-stu-id="4b4f0-108">Related macros:</span></span>  <br/> |<span data-ttu-id="4b4f0-109">[CHANGE_PROP_TYPE](change_prop_type.md)、 [MVI_PROP](mvi_prop.md)、 [PROP_ID](prop_id.md)、 [PROP_TAG](prop_tag.md)、 [PROP_TYPE](prop_type.md)</span><span class="sxs-lookup"><span data-stu-id="4b4f0-109">[CHANGE_PROP_TYPE](change_prop_type.md), [MVI_PROP](mvi_prop.md), [PROP_ID](prop_id.md), [PROP_TAG](prop_tag.md), [PROP_TYPE](prop_type.md)</span></span> <br/> |
   
```cpp
typedef struct _SPropValue
{
  ULONG ulPropTag;
  ULONG dwAlignPad;
  union _PV Value;
} SPropValue, FAR *LPSPropValue;

```

## <a name="members"></a><span data-ttu-id="4b4f0-110">Members</span><span class="sxs-lookup"><span data-stu-id="4b4f0-110">Members</span></span>

 <span data-ttu-id="4b4f0-111">**ulPropTag**</span><span class="sxs-lookup"><span data-stu-id="4b4f0-111">**ulPropTag**</span></span>
  
> <span data-ttu-id="4b4f0-112">属性的属性标记。</span><span class="sxs-lookup"><span data-stu-id="4b4f0-112">Property tag for the property.</span></span> <span data-ttu-id="4b4f0-113">属性标记是32位无符号整数, 由高序位16位中的属性唯一标识符和低序位16位中的属性类型组成。</span><span class="sxs-lookup"><span data-stu-id="4b4f0-113">Property tags are 32-bit unsigned integers consisting of the property's unique identifier in the high-order 16 bits and the property's type in the low-order 16 bits.</span></span>
    
 <span data-ttu-id="4b4f0-114">**dwAlignPad**</span><span class="sxs-lookup"><span data-stu-id="4b4f0-114">**dwAlignPad**</span></span>
  
> <span data-ttu-id="4b4f0-115">为 MAPI 保留;请勿使用。</span><span class="sxs-lookup"><span data-stu-id="4b4f0-115">Reserved for MAPI; do not use.</span></span> 
    
 <span data-ttu-id="4b4f0-116">**值**</span><span class="sxs-lookup"><span data-stu-id="4b4f0-116">**Value**</span></span>
  
> <span data-ttu-id="4b4f0-117">数据值的联合, 由属性类型指定的特定值。</span><span class="sxs-lookup"><span data-stu-id="4b4f0-117">Union of data values, the specific value dictated by the property type.</span></span> <span data-ttu-id="4b4f0-118">下表列出了每个属性类型、应使用的联合的成员及其关联的数据类型。</span><span class="sxs-lookup"><span data-stu-id="4b4f0-118">The following table lists for each property type, the member of the union that should be used and its associated data type.</span></span>
    
|<span data-ttu-id="4b4f0-119">**属性类型**</span><span class="sxs-lookup"><span data-stu-id="4b4f0-119">**Property type**</span></span>|<span data-ttu-id="4b4f0-120">**值**</span><span class="sxs-lookup"><span data-stu-id="4b4f0-120">**Value**</span></span>|<span data-ttu-id="4b4f0-121">**值的数据类型**</span><span class="sxs-lookup"><span data-stu-id="4b4f0-121">**Data type of Value**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="4b4f0-122">PT_I2 或 PT_SHORT</span><span class="sxs-lookup"><span data-stu-id="4b4f0-122">PT_I2 or PT_SHORT</span></span>  <br/> |<span data-ttu-id="4b4f0-123">**得到**</span><span class="sxs-lookup"><span data-stu-id="4b4f0-123">**i**</span></span> <br/> |<span data-ttu-id="4b4f0-124">短整型</span><span class="sxs-lookup"><span data-stu-id="4b4f0-124">short int</span></span>  <br/> |
|<span data-ttu-id="4b4f0-125">PT_I4 或 PT_LONG (已签名)</span><span class="sxs-lookup"><span data-stu-id="4b4f0-125">PT_I4 or PT_LONG (signed)</span></span>  <br/> |<span data-ttu-id="4b4f0-126">**l**</span><span class="sxs-lookup"><span data-stu-id="4b4f0-126">**l**</span></span> <br/> |<span data-ttu-id="4b4f0-127">大量</span><span class="sxs-lookup"><span data-stu-id="4b4f0-127">LONG</span></span>  <br/> |
|<span data-ttu-id="4b4f0-128">PT_I4 或 PT_LONG (无符号)</span><span class="sxs-lookup"><span data-stu-id="4b4f0-128">PT_I4 or PT_LONG (unsigned)</span></span>  <br/> |<span data-ttu-id="4b4f0-129">**列名**</span><span class="sxs-lookup"><span data-stu-id="4b4f0-129">**ul**</span></span> <br/> |<span data-ttu-id="4b4f0-130">ULONG</span><span class="sxs-lookup"><span data-stu-id="4b4f0-130">ULONG</span></span>  <br/> |
|<span data-ttu-id="4b4f0-131">PT_R4 或 PT_FLOAT</span><span class="sxs-lookup"><span data-stu-id="4b4f0-131">PT_R4 or PT_FLOAT</span></span>  <br/> |<span data-ttu-id="4b4f0-132">**flt**</span><span class="sxs-lookup"><span data-stu-id="4b4f0-132">**flt**</span></span> <br/> |<span data-ttu-id="4b4f0-133">float</span><span class="sxs-lookup"><span data-stu-id="4b4f0-133">float</span></span>  <br/> |
|<span data-ttu-id="4b4f0-134">PT_R8 或 PT_DOUBLE</span><span class="sxs-lookup"><span data-stu-id="4b4f0-134">PT_R8 or PT_DOUBLE</span></span>  <br/> |<span data-ttu-id="4b4f0-135">**双**</span><span class="sxs-lookup"><span data-stu-id="4b4f0-135">**dbl**</span></span> <br/> |<span data-ttu-id="4b4f0-136">double</span><span class="sxs-lookup"><span data-stu-id="4b4f0-136">double</span></span>  <br/> |
|<span data-ttu-id="4b4f0-137">PT_BOOLEAN</span><span class="sxs-lookup"><span data-stu-id="4b4f0-137">PT_BOOLEAN</span></span>  <br/> |<span data-ttu-id="4b4f0-138">**黑白**</span><span class="sxs-lookup"><span data-stu-id="4b4f0-138">**b**</span></span> <br/> |<span data-ttu-id="4b4f0-139">无符号短整型</span><span class="sxs-lookup"><span data-stu-id="4b4f0-139">unsigned short int</span></span>  <br/> |
|<span data-ttu-id="4b4f0-140">PT_CURRENCY</span><span class="sxs-lookup"><span data-stu-id="4b4f0-140">PT_CURRENCY</span></span>  <br/> |<span data-ttu-id="4b4f0-141">**选用**</span><span class="sxs-lookup"><span data-stu-id="4b4f0-141">**cur**</span></span> <br/> |[<span data-ttu-id="4b4f0-142">CURRENCY</span><span class="sxs-lookup"><span data-stu-id="4b4f0-142">CURRENCY</span></span>](currency.md) <br/> |
|<span data-ttu-id="4b4f0-143">PT_APPTIME</span><span class="sxs-lookup"><span data-stu-id="4b4f0-143">PT_APPTIME</span></span>  <br/> |<span data-ttu-id="4b4f0-144">**个**</span><span class="sxs-lookup"><span data-stu-id="4b4f0-144">**at**</span></span> <br/> |<span data-ttu-id="4b4f0-145">double</span><span class="sxs-lookup"><span data-stu-id="4b4f0-145">double</span></span>  <br/> |
|<span data-ttu-id="4b4f0-146">PT_SYSTIME</span><span class="sxs-lookup"><span data-stu-id="4b4f0-146">PT_SYSTIME</span></span>  <br/> |<span data-ttu-id="4b4f0-147">**ft**</span><span class="sxs-lookup"><span data-stu-id="4b4f0-147">**ft**</span></span> <br/> |[<span data-ttu-id="4b4f0-148">FILETIME</span><span class="sxs-lookup"><span data-stu-id="4b4f0-148">FILETIME</span></span>](filetime.md) <br/> |
|<span data-ttu-id="4b4f0-149">PT_STRING8</span><span class="sxs-lookup"><span data-stu-id="4b4f0-149">PT_STRING8</span></span>  <br/> |<span data-ttu-id="4b4f0-150">**lpszA**</span><span class="sxs-lookup"><span data-stu-id="4b4f0-150">**lpszA**</span></span> <br/> |<span data-ttu-id="4b4f0-151">LPSTR</span><span class="sxs-lookup"><span data-stu-id="4b4f0-151">LPSTR</span></span>  <br/> |
|<span data-ttu-id="4b4f0-152">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="4b4f0-152">PT_BINARY</span></span>  <br/> |<span data-ttu-id="4b4f0-153">**区间**</span><span class="sxs-lookup"><span data-stu-id="4b4f0-153">**bin**</span></span> <br/> |<span data-ttu-id="4b4f0-154">BYTE [array]</span><span class="sxs-lookup"><span data-stu-id="4b4f0-154">BYTE [array]</span></span>  <br/> |
|<span data-ttu-id="4b4f0-155">PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="4b4f0-155">PT_UNICODE</span></span>  <br/> |<span data-ttu-id="4b4f0-156">**lpszW**</span><span class="sxs-lookup"><span data-stu-id="4b4f0-156">**lpszW**</span></span> <br/> |<span data-ttu-id="4b4f0-157">LPWSTR</span><span class="sxs-lookup"><span data-stu-id="4b4f0-157">LPWSTR</span></span>  <br/> |
|<span data-ttu-id="4b4f0-158">PT_CLSID</span><span class="sxs-lookup"><span data-stu-id="4b4f0-158">PT_CLSID</span></span>  <br/> |<span data-ttu-id="4b4f0-159">**lpguid**</span><span class="sxs-lookup"><span data-stu-id="4b4f0-159">**lpguid**</span></span> <br/> |<span data-ttu-id="4b4f0-160">LPGUID</span><span class="sxs-lookup"><span data-stu-id="4b4f0-160">LPGUID</span></span>  <br/> |
|<span data-ttu-id="4b4f0-161">PT_I8 或 PT_LONGLONG</span><span class="sxs-lookup"><span data-stu-id="4b4f0-161">PT_I8 or PT_LONGLONG</span></span>  <br/> |<span data-ttu-id="4b4f0-162">**i**</span><span class="sxs-lookup"><span data-stu-id="4b4f0-162">**li**</span></span> <br/> |<span data-ttu-id="4b4f0-163">**LARGE_INTEGER**</span><span class="sxs-lookup"><span data-stu-id="4b4f0-163">**LARGE_INTEGER**</span></span> <br/> |
|<span data-ttu-id="4b4f0-164">PT_MV_I2</span><span class="sxs-lookup"><span data-stu-id="4b4f0-164">PT_MV_I2</span></span>  <br/> |<span data-ttu-id="4b4f0-165">**MVi**</span><span class="sxs-lookup"><span data-stu-id="4b4f0-165">**MVi**</span></span> <br/> |[<span data-ttu-id="4b4f0-166">SShortArray</span><span class="sxs-lookup"><span data-stu-id="4b4f0-166">SShortArray</span></span>](sshortarray.md) <br/> |
|<span data-ttu-id="4b4f0-167">PT_MV_LONG</span><span class="sxs-lookup"><span data-stu-id="4b4f0-167">PT_MV_LONG</span></span>  <br/> |<span data-ttu-id="4b4f0-168">**MVI**</span><span class="sxs-lookup"><span data-stu-id="4b4f0-168">**MVI**</span></span> <br/> |[<span data-ttu-id="4b4f0-169">SLongArray</span><span class="sxs-lookup"><span data-stu-id="4b4f0-169">SLongArray</span></span>](slongarray.md) <br/> |
|<span data-ttu-id="4b4f0-170">PT_MV_R4</span><span class="sxs-lookup"><span data-stu-id="4b4f0-170">PT_MV_R4</span></span>  <br/> |<span data-ttu-id="4b4f0-171">**MVflt**</span><span class="sxs-lookup"><span data-stu-id="4b4f0-171">**MVflt**</span></span> <br/> |[<span data-ttu-id="4b4f0-172">SRealArray</span><span class="sxs-lookup"><span data-stu-id="4b4f0-172">SRealArray</span></span>](srealarray.md) <br/> |
|<span data-ttu-id="4b4f0-173">PT_MV_DOUBLE</span><span class="sxs-lookup"><span data-stu-id="4b4f0-173">PT_MV_DOUBLE</span></span>  <br/> |<span data-ttu-id="4b4f0-174">**MVdbl**</span><span class="sxs-lookup"><span data-stu-id="4b4f0-174">**MVdbl**</span></span> <br/> |[<span data-ttu-id="4b4f0-175">SDoubleArray</span><span class="sxs-lookup"><span data-stu-id="4b4f0-175">SDoubleArray</span></span>](sdoublearray.md) <br/> |
|<span data-ttu-id="4b4f0-176">PT_MV_CURRENCY</span><span class="sxs-lookup"><span data-stu-id="4b4f0-176">PT_MV_CURRENCY</span></span>  <br/> |<span data-ttu-id="4b4f0-177">**MVcur**</span><span class="sxs-lookup"><span data-stu-id="4b4f0-177">**MVcur**</span></span> <br/> |[<span data-ttu-id="4b4f0-178">SCurrencyArray</span><span class="sxs-lookup"><span data-stu-id="4b4f0-178">SCurrencyArray</span></span>](scurrencyarray.md) <br/> |
|<span data-ttu-id="4b4f0-179">PT_MV_APPTIME</span><span class="sxs-lookup"><span data-stu-id="4b4f0-179">PT_MV_APPTIME</span></span>  <br/> |<span data-ttu-id="4b4f0-180">**MVat**</span><span class="sxs-lookup"><span data-stu-id="4b4f0-180">**MVat**</span></span> <br/> |[<span data-ttu-id="4b4f0-181">SAppTimeArray</span><span class="sxs-lookup"><span data-stu-id="4b4f0-181">SAppTimeArray</span></span>](sapptimearray.md) <br/> |
|<span data-ttu-id="4b4f0-182">PT_MV_SYSTIME</span><span class="sxs-lookup"><span data-stu-id="4b4f0-182">PT_MV_SYSTIME</span></span>  <br/> |<span data-ttu-id="4b4f0-183">**MVft**</span><span class="sxs-lookup"><span data-stu-id="4b4f0-183">**MVft**</span></span> <br/> |[<span data-ttu-id="4b4f0-184">SDateTimeArray</span><span class="sxs-lookup"><span data-stu-id="4b4f0-184">SDateTimeArray</span></span>](sdatetimearray.md) <br/> |
|<span data-ttu-id="4b4f0-185">PT_MV_BINARY</span><span class="sxs-lookup"><span data-stu-id="4b4f0-185">PT_MV_BINARY</span></span>  <br/> |<span data-ttu-id="4b4f0-186">**MVbin**</span><span class="sxs-lookup"><span data-stu-id="4b4f0-186">**MVbin**</span></span> <br/> |[<span data-ttu-id="4b4f0-187">SBinaryArray</span><span class="sxs-lookup"><span data-stu-id="4b4f0-187">SBinaryArray</span></span>](sbinaryarray.md) <br/> |
|<span data-ttu-id="4b4f0-188">PT_MV_STRING8</span><span class="sxs-lookup"><span data-stu-id="4b4f0-188">PT_MV_STRING8</span></span>  <br/> |<span data-ttu-id="4b4f0-189">**MVszA**</span><span class="sxs-lookup"><span data-stu-id="4b4f0-189">**MVszA**</span></span> <br/> |[<span data-ttu-id="4b4f0-190">SLPSTRArray</span><span class="sxs-lookup"><span data-stu-id="4b4f0-190">SLPSTRArray</span></span>](slpstrarray.md) <br/> |
|<span data-ttu-id="4b4f0-191">PT_MV_UNICODE</span><span class="sxs-lookup"><span data-stu-id="4b4f0-191">PT_MV_UNICODE</span></span>  <br/> |<span data-ttu-id="4b4f0-192">**MVszW**</span><span class="sxs-lookup"><span data-stu-id="4b4f0-192">**MVszW**</span></span> <br/> |[<span data-ttu-id="4b4f0-193">SWStringArray</span><span class="sxs-lookup"><span data-stu-id="4b4f0-193">SWStringArray</span></span>](swstringarray.md) <br/> |
|<span data-ttu-id="4b4f0-194">PT_MV_CLSID</span><span class="sxs-lookup"><span data-stu-id="4b4f0-194">PT_MV_CLSID</span></span>  <br/> |<span data-ttu-id="4b4f0-195">**MVguid**</span><span class="sxs-lookup"><span data-stu-id="4b4f0-195">**MVguid**</span></span> <br/> |[<span data-ttu-id="4b4f0-196">SGuidArray</span><span class="sxs-lookup"><span data-stu-id="4b4f0-196">SGuidArray</span></span>](sguidarray.md) <br/> |
|<span data-ttu-id="4b4f0-197">PT_MV_I8</span><span class="sxs-lookup"><span data-stu-id="4b4f0-197">PT_MV_I8</span></span>  <br/> |<span data-ttu-id="4b4f0-198">**MVli**</span><span class="sxs-lookup"><span data-stu-id="4b4f0-198">**MVli**</span></span> <br/> |[<span data-ttu-id="4b4f0-199">SLargeIntegerArray</span><span class="sxs-lookup"><span data-stu-id="4b4f0-199">SLargeIntegerArray</span></span>](slargeintegerarray.md) <br/> |
|<span data-ttu-id="4b4f0-200">PT_ERROR</span><span class="sxs-lookup"><span data-stu-id="4b4f0-200">PT_ERROR</span></span>  <br/> |<span data-ttu-id="4b4f0-201">**err**</span><span class="sxs-lookup"><span data-stu-id="4b4f0-201">**err**</span></span> <br/> |[<span data-ttu-id="4b4f0-202">SCODE</span><span class="sxs-lookup"><span data-stu-id="4b4f0-202">SCODE</span></span>](scode.md) <br/> |
|<span data-ttu-id="4b4f0-203">PT_NULL 或 PT_OBJECT</span><span class="sxs-lookup"><span data-stu-id="4b4f0-203">PT_NULL or PT_OBJECT</span></span>  <br/> |<span data-ttu-id="4b4f0-204">**x**</span><span class="sxs-lookup"><span data-stu-id="4b4f0-204">**x**</span></span> <br/> |<span data-ttu-id="4b4f0-205">大量</span><span class="sxs-lookup"><span data-stu-id="4b4f0-205">LONG</span></span>  <br/> |
|<span data-ttu-id="4b4f0-206">PT_PTR</span><span class="sxs-lookup"><span data-stu-id="4b4f0-206">PT_PTR</span></span>  <br/> |<span data-ttu-id="4b4f0-207">**lpv**</span><span class="sxs-lookup"><span data-stu-id="4b4f0-207">**lpv**</span></span> <br/> |<span data-ttu-id="4b4f0-208">作废\*</span><span class="sxs-lookup"><span data-stu-id="4b4f0-208">VOID \*</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="4b4f0-209">注解</span><span class="sxs-lookup"><span data-stu-id="4b4f0-209">Remarks</span></span>

<span data-ttu-id="4b4f0-210">**ulPropTag**成员由两部分组成:</span><span class="sxs-lookup"><span data-stu-id="4b4f0-210">The **ulPropTag** member is made up of two parts:</span></span> 
  
- <span data-ttu-id="4b4f0-211">高顺序16位中的标识符。</span><span class="sxs-lookup"><span data-stu-id="4b4f0-211">An identifier in the high-order 16 bits.</span></span>
    
- <span data-ttu-id="4b4f0-212">一个低序位16位的类型。</span><span class="sxs-lookup"><span data-stu-id="4b4f0-212">A type in the low-order 16 bits.</span></span>
    
<span data-ttu-id="4b4f0-213">标识符是在特定范围内的一个数字值。</span><span class="sxs-lookup"><span data-stu-id="4b4f0-213">The identifier is a numeric value within a particular range.</span></span> <span data-ttu-id="4b4f0-214">MAPI 为标识符定义范围, 以描述该属性的用途, 以及负责维护该属性的参与者。</span><span class="sxs-lookup"><span data-stu-id="4b4f0-214">MAPI defines ranges for identifiers to describe what the property is used for and who is responsible for maintaining it.</span></span> <span data-ttu-id="4b4f0-215">MAPI 为在 Mapitags 头文件中支持的每个属性标记定义约束。</span><span class="sxs-lookup"><span data-stu-id="4b4f0-215">MAPI defines constraints for each of the property tags that it supports in the Mapitags.h header file.</span></span>
  
<span data-ttu-id="4b4f0-216">类型指示属性值的格式。</span><span class="sxs-lookup"><span data-stu-id="4b4f0-216">The type indicates the format for the property's value.</span></span> <span data-ttu-id="4b4f0-217">MAPI 为它在 mapidefs.h 头文件中支持的每个属性类型定义常量。</span><span class="sxs-lookup"><span data-stu-id="4b4f0-217">MAPI defines constants for each of the property types that it supports in the Mapidefs.h header file.</span></span> 
  
<span data-ttu-id="4b4f0-218">有关标识符和属性类型的有效属性范围的完整列表, 请参阅[属性标识符和类型](property-identifiers-and-types.md)附录。</span><span class="sxs-lookup"><span data-stu-id="4b4f0-218">For a complete list of the valid property ranges for identifiers and property types, see the [Property Identifiers and Types](property-identifiers-and-types.md) appendix.</span></span> 
  
<span data-ttu-id="4b4f0-219">**dwAlignPad**成员用作填充, 以确保在需要8字节对齐方式的计算机上进行正确的对齐8字节值。</span><span class="sxs-lookup"><span data-stu-id="4b4f0-219">The **dwAlignPad** member is used as padding to make sure proper alignment on computers that require 8-byte alignment for 8-byte values.</span></span> <span data-ttu-id="4b4f0-220">在此类计算机上编写代码的开发人员应使用在8字节边界上分配**SPropValue**数组的内存分配例程。</span><span class="sxs-lookup"><span data-stu-id="4b4f0-220">Developers who write code on such computers should use memory allocation routines that allocate the **SPropValue** arrays on 8-byte boundaries.</span></span> 
  
<span data-ttu-id="4b4f0-221">有关详细信息, 请参阅[mapi 属性类型概述](mapi-property-type-overview.md)和[更新 mapi 属性](updating-mapi-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="4b4f0-221">For more information, see [MAPI Property Type Overview](mapi-property-type-overview.md) and [Updating MAPI Properties](updating-mapi-properties.md).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="4b4f0-222">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4b4f0-222">See also</span></span>



[<span data-ttu-id="4b4f0-223">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="4b4f0-223">MAPI Structures</span></span>](mapi-structures.md)

