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
ms.openlocfilehash: 4dcdce72781669988a0cb15eb9b3a7cd73494bfb
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775184"
---
# <a name="hrgetoneprop"></a><span data-ttu-id="134c8-103">HrGetOneProp</span><span class="sxs-lookup"><span data-stu-id="134c8-103">HrGetOneProp</span></span>

  
  
<span data-ttu-id="134c8-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="134c8-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="134c8-105">从属性界面，即接口派生自[IMAPIProp](imapipropiunknown.md)检索单个属性的值。</span><span class="sxs-lookup"><span data-stu-id="134c8-105">Retrieves the value of a single property from a property interface, that is, an interface derived from [IMAPIProp](imapipropiunknown.md).</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="134c8-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="134c8-106">Header file:</span></span>  <br/> |<span data-ttu-id="134c8-107">Mapiutil.h</span><span class="sxs-lookup"><span data-stu-id="134c8-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="134c8-108">通过实现：</span><span class="sxs-lookup"><span data-stu-id="134c8-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="134c8-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="134c8-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="134c8-110">调用：</span><span class="sxs-lookup"><span data-stu-id="134c8-110">Called by:</span></span>  <br/> |<span data-ttu-id="134c8-111">客户端应用程序和服务提供商</span><span class="sxs-lookup"><span data-stu-id="134c8-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
HrGetOneProp(
  LPMAPIPROP pmp,
  ULONG ulPropTag,
  LPSPropValue FAR * ppprop
);
```

## <a name="parameters"></a><span data-ttu-id="134c8-112">参数</span><span class="sxs-lookup"><span data-stu-id="134c8-112">Parameters</span></span>

 <span data-ttu-id="134c8-113">_pmp_</span><span class="sxs-lookup"><span data-stu-id="134c8-113">_pmp_</span></span>
  
> <span data-ttu-id="134c8-114">[in]是要检索属性值的[IMAPIProp](imapipropiunknown.md)接口的指针。</span><span class="sxs-lookup"><span data-stu-id="134c8-114">[in] Pointer to the [IMAPIProp](imapipropiunknown.md) interface from which the property value is to be retrieved.</span></span> 
    
 <span data-ttu-id="134c8-115">_ulPropTag_</span><span class="sxs-lookup"><span data-stu-id="134c8-115">_ulPropTag_</span></span>
  
> <span data-ttu-id="134c8-116">[in]要检索的属性的属性标记。</span><span class="sxs-lookup"><span data-stu-id="134c8-116">[in] Property tag of the property to be retrieved.</span></span> 
    
 <span data-ttu-id="134c8-117">_ppprop_</span><span class="sxs-lookup"><span data-stu-id="134c8-117">_ppprop_</span></span>
  
> <span data-ttu-id="134c8-118">[输出]返回[SPropValue](spropvalue.md)结构定义检索的属性值为指针的指针。</span><span class="sxs-lookup"><span data-stu-id="134c8-118">[out] Pointer to a pointer to the returned [SPropValue](spropvalue.md) structure defining the retrieved property value.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="134c8-119">返回值</span><span class="sxs-lookup"><span data-stu-id="134c8-119">Return value</span></span>

<span data-ttu-id="134c8-120">MAPI_E_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="134c8-120">MAPI_E_NOT_FOUND</span></span> 
  
> <span data-ttu-id="134c8-121">从指定的接口请求的属性不可用。</span><span class="sxs-lookup"><span data-stu-id="134c8-121">The requested property is not available from the specified interface.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="134c8-122">说明</span><span class="sxs-lookup"><span data-stu-id="134c8-122">Remarks</span></span>

<span data-ttu-id="134c8-123">不同的[IMAPIProp::GetProps](imapiprop-getprops.md)方法， **HrGetOneProp**函数永远不会返回任何警告。</span><span class="sxs-lookup"><span data-stu-id="134c8-123">Unlike the [IMAPIProp::GetProps](imapiprop-getprops.md) method, the **HrGetOneProp** function never returns any warning.</span></span> <span data-ttu-id="134c8-124">检索只有一个属性，因为它只是成功或失败。</span><span class="sxs-lookup"><span data-stu-id="134c8-124">Because it retrieves only one property, it simply either succeeds or fails.</span></span> <span data-ttu-id="134c8-125">用于检索多个属性， **GetProps**是更快。</span><span class="sxs-lookup"><span data-stu-id="134c8-125">For retrieving multiple properties, **GetProps** is faster.</span></span> 
  
<span data-ttu-id="134c8-126">您可以设置或更改单个属性与[HrSetOneProp](hrsetoneprop.md)函数。</span><span class="sxs-lookup"><span data-stu-id="134c8-126">You can set or change a single property with the [HrSetOneProp](hrsetoneprop.md) function.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="134c8-127">MFCMAPI 参考 （英文）</span><span class="sxs-lookup"><span data-stu-id="134c8-127">MFCMAPI reference</span></span>

<span data-ttu-id="134c8-128">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="134c8-128">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="134c8-129">**文件**</span><span class="sxs-lookup"><span data-stu-id="134c8-129">**File**</span></span>|<span data-ttu-id="134c8-130">**函数**</span><span class="sxs-lookup"><span data-stu-id="134c8-130">**Function**</span></span>|<span data-ttu-id="134c8-131">**Comment**</span><span class="sxs-lookup"><span data-stu-id="134c8-131">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="134c8-132">MAPIFunctions.cpp</span><span class="sxs-lookup"><span data-stu-id="134c8-132">MAPIFunctions.cpp</span></span>  <br/> |<span data-ttu-id="134c8-133">GetMAPIObjectType</span><span class="sxs-lookup"><span data-stu-id="134c8-133">GetMAPIObjectType</span></span>  <br/> |<span data-ttu-id="134c8-134">MFCMAPI 使用**HrGetOneProp**方法检索的对象的类型。</span><span class="sxs-lookup"><span data-stu-id="134c8-134">MFCMAPI uses the **HrGetOneProp** method to retrieve the type of an object.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="134c8-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="134c8-135">See also</span></span>



[<span data-ttu-id="134c8-136">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="134c8-136">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

