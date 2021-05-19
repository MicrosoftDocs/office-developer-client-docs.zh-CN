---
title: HrGetOneProp
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- HrGetOneProp
api_type:
- HeaderDef
ms.assetid: 8d0a381a-e714-4663-9a57-b0e1cdbd6ba7
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: e5adc7d0c317d8b803645d78227777998d7d241f
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33416053"
---
# <a name="hrgetoneprop"></a><span data-ttu-id="7f129-103">HrGetOneProp</span><span class="sxs-lookup"><span data-stu-id="7f129-103">HrGetOneProp</span></span>

  
  
<span data-ttu-id="7f129-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="7f129-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="7f129-105">从属性接口（即派生自 [IMAPIProp](imapipropiunknown.md)的接口）检索单个属性的值。</span><span class="sxs-lookup"><span data-stu-id="7f129-105">Retrieves the value of a single property from a property interface, that is, an interface derived from [IMAPIProp](imapipropiunknown.md).</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="7f129-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="7f129-106">Header file:</span></span>  <br/> |<span data-ttu-id="7f129-107">Mapiutil.h</span><span class="sxs-lookup"><span data-stu-id="7f129-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="7f129-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="7f129-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="7f129-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="7f129-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="7f129-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="7f129-110">Called by:</span></span>  <br/> |<span data-ttu-id="7f129-111">客户端应用程序和服务提供商</span><span class="sxs-lookup"><span data-stu-id="7f129-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
HrGetOneProp(
  LPMAPIPROP pmp,
  ULONG ulPropTag,
  LPSPropValue FAR * ppprop
);
```

## <a name="parameters"></a><span data-ttu-id="7f129-112">参数</span><span class="sxs-lookup"><span data-stu-id="7f129-112">Parameters</span></span>

 <span data-ttu-id="7f129-113">_pmp_</span><span class="sxs-lookup"><span data-stu-id="7f129-113">_pmp_</span></span>
  
> <span data-ttu-id="7f129-114">[in]指向要检索属性值的 [IMAPIProp](imapipropiunknown.md) 接口的指针。</span><span class="sxs-lookup"><span data-stu-id="7f129-114">[in] Pointer to the [IMAPIProp](imapipropiunknown.md) interface from which the property value is to be retrieved.</span></span> 
    
 <span data-ttu-id="7f129-115">_ulPropTag_</span><span class="sxs-lookup"><span data-stu-id="7f129-115">_ulPropTag_</span></span>
  
> <span data-ttu-id="7f129-116">[in]要检索的属性的属性标记。</span><span class="sxs-lookup"><span data-stu-id="7f129-116">[in] Property tag of the property to be retrieved.</span></span> 
    
 <span data-ttu-id="7f129-117">_ppprop_</span><span class="sxs-lookup"><span data-stu-id="7f129-117">_ppprop_</span></span>
  
> <span data-ttu-id="7f129-118">[out]指向定义检索到的属性值的 [返回 SPropValue](spropvalue.md) 结构的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="7f129-118">[out] Pointer to a pointer to the returned [SPropValue](spropvalue.md) structure defining the retrieved property value.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="7f129-119">返回值</span><span class="sxs-lookup"><span data-stu-id="7f129-119">Return value</span></span>

<span data-ttu-id="7f129-120">MAPI_E_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="7f129-120">MAPI_E_NOT_FOUND</span></span> 
  
> <span data-ttu-id="7f129-121">请求的属性在指定的接口中不可用。</span><span class="sxs-lookup"><span data-stu-id="7f129-121">The requested property is not available from the specified interface.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="7f129-122">备注</span><span class="sxs-lookup"><span data-stu-id="7f129-122">Remarks</span></span>

<span data-ttu-id="7f129-123">与 [IMAPIProp：：GetProps](imapiprop-getprops.md) 方法不同 **，HrGetOneProp** 函数从不返回任何警告。</span><span class="sxs-lookup"><span data-stu-id="7f129-123">Unlike the [IMAPIProp::GetProps](imapiprop-getprops.md) method, the **HrGetOneProp** function never returns any warning.</span></span> <span data-ttu-id="7f129-124">因为它只检索一个属性，所以它要么成功要么失败。</span><span class="sxs-lookup"><span data-stu-id="7f129-124">Because it retrieves only one property, it simply either succeeds or fails.</span></span> <span data-ttu-id="7f129-125">对于检索多个属性 **，GetProps** 速度更快。</span><span class="sxs-lookup"><span data-stu-id="7f129-125">For retrieving multiple properties, **GetProps** is faster.</span></span> 
  
<span data-ttu-id="7f129-126">可以使用 [HrSetOneProp](hrsetoneprop.md) 函数设置或更改单个属性。</span><span class="sxs-lookup"><span data-stu-id="7f129-126">You can set or change a single property with the [HrSetOneProp](hrsetoneprop.md) function.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="7f129-127">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="7f129-127">MFCMAPI reference</span></span>

<span data-ttu-id="7f129-128">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="7f129-128">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="7f129-129">**文件**</span><span class="sxs-lookup"><span data-stu-id="7f129-129">**File**</span></span>|<span data-ttu-id="7f129-130">**函数**</span><span class="sxs-lookup"><span data-stu-id="7f129-130">**Function**</span></span>|<span data-ttu-id="7f129-131">**备注**</span><span class="sxs-lookup"><span data-stu-id="7f129-131">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="7f129-132">MAPIFunctions.cpp</span><span class="sxs-lookup"><span data-stu-id="7f129-132">MAPIFunctions.cpp</span></span>  <br/> |<span data-ttu-id="7f129-133">GetMAPIObjectType</span><span class="sxs-lookup"><span data-stu-id="7f129-133">GetMAPIObjectType</span></span>  <br/> |<span data-ttu-id="7f129-134">MFCMAPI 使用 **HrGetOneProp** 方法检索对象的类型。</span><span class="sxs-lookup"><span data-stu-id="7f129-134">MFCMAPI uses the **HrGetOneProp** method to retrieve the type of an object.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="7f129-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7f129-135">See also</span></span>



[<span data-ttu-id="7f129-136">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="7f129-136">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

