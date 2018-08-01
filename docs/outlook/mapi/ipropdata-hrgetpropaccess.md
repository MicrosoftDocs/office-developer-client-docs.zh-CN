---
title: IPropDataHrGetPropAccess
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IPropData.HrGetPropAccess
api_type:
- COM
ms.assetid: 0101d291-00ca-4f66-b857-75d74b9f91a1
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 8441a4898659a5cd278265cb0199bb9097244aa3
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776009"
---
# <a name="ipropdatahrgetpropaccess"></a><span data-ttu-id="5599e-103">IPropData::HrGetPropAccess</span><span class="sxs-lookup"><span data-stu-id="5599e-103">IPropData::HrGetPropAccess</span></span>

  
  
<span data-ttu-id="5599e-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="5599e-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="5599e-105">检索的访问级别和一个或多个对象的属性的状态。</span><span class="sxs-lookup"><span data-stu-id="5599e-105">Retrieves the access level and status for one or more of the object's properties.</span></span>
  
```cpp
HRESULT HrGetPropAccess(
  LPSPropTagArray FAR * lppPropTagArray,
  ULONG FAR * FAR * lprgulAccess
);
```

## <a name="parameters"></a><span data-ttu-id="5599e-106">参数</span><span class="sxs-lookup"><span data-stu-id="5599e-106">Parameters</span></span>

 <span data-ttu-id="5599e-107">_lppPropTagArray_</span><span class="sxs-lookup"><span data-stu-id="5599e-107">_lppPropTagArray_</span></span>
  
> <span data-ttu-id="5599e-108">[传入、 传出]在输入数组属性标记，指示要为其检索访问级别和状态; 属性否则为为 NULL，表明**HrGetPropAccess**应检索访问级别和的所有属性的状态的指针。</span><span class="sxs-lookup"><span data-stu-id="5599e-108">[in, out] On input, an array of property tags that indicate the properties for which to retrieve access levels and status; otherwise, a pointer to NULL, which indicates that **HrGetPropAccess** should retrieve access levels and status for all properties.</span></span> <span data-ttu-id="5599e-109">输出，检索到数组属性标记为哪些访问和状态标志。</span><span class="sxs-lookup"><span data-stu-id="5599e-109">On output, an array of property tags for which access and status flags were retrieved.</span></span> <span data-ttu-id="5599e-110">Flags 存储在_lprgulAccess_参数指向的数组。</span><span class="sxs-lookup"><span data-stu-id="5599e-110">The flags are stored in the array pointed to by the  _lprgulAccess_ parameter.</span></span> 
    
 <span data-ttu-id="5599e-111">_lprgulAccess_</span><span class="sxs-lookup"><span data-stu-id="5599e-111">_lprgulAccess_</span></span>
  
> <span data-ttu-id="5599e-112">[输出]一个指向数组标志位掩码。</span><span class="sxs-lookup"><span data-stu-id="5599e-112">[out] A pointer to an array of flag bitmasks.</span></span> <span data-ttu-id="5599e-113">每位掩码指示的访问级别或状态，或同时为每个标识_lpPropTagArray_参数指向该数组中的属性。</span><span class="sxs-lookup"><span data-stu-id="5599e-113">Each bitmask indicates the access levels or status, or both, for each of the properties identified in the array pointed to by the  _lpPropTagArray_ parameter.</span></span> <span data-ttu-id="5599e-114">两个数组是位置_lprgulAccess_指向介绍的第一个属性的第一个位掩码的_lpPropTagArray_ points 为，依此类推。</span><span class="sxs-lookup"><span data-stu-id="5599e-114">The two arrays are positional in that the first bitmask that  _lprgulAccess_ points to describes the first property that  _lpPropTagArray_ points to, and so on.</span></span> <span data-ttu-id="5599e-115">对于每个属性标记，可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="5599e-115">For each property tag, the following flags can be set:</span></span> 
    
|<span data-ttu-id="5599e-116">**访问级别标志**</span><span class="sxs-lookup"><span data-stu-id="5599e-116">**Access-level flag**</span></span>|<span data-ttu-id="5599e-117">**状态标志**</span><span class="sxs-lookup"><span data-stu-id="5599e-117">**Status flag**</span></span>|
|:-----|:-----|
|<span data-ttu-id="5599e-118">IPROP_READONLY，指示无法修改的属性。</span><span class="sxs-lookup"><span data-stu-id="5599e-118">IPROP_READONLY, which indicates that the property cannot be modified.</span></span>  <br/> |<span data-ttu-id="5599e-119">IPROP_CLEAN，这表明该属性不被修改。</span><span class="sxs-lookup"><span data-stu-id="5599e-119">IPROP_CLEAN, which indicates that the property has not been modified.</span></span>  <br/> |
|<span data-ttu-id="5599e-120">IPROP_READWRITE，指示可以修改的属性。</span><span class="sxs-lookup"><span data-stu-id="5599e-120">IPROP_READWRITE, which indicates that the property can be modified.</span></span>  <br/> |<span data-ttu-id="5599e-121">IPROP_DIRTY，这表明该属性已修改。</span><span class="sxs-lookup"><span data-stu-id="5599e-121">IPROP_DIRTY, which indicates that the property has been modified.</span></span>  <br/> |
   
## <a name="return-value"></a><span data-ttu-id="5599e-122">返回值</span><span class="sxs-lookup"><span data-stu-id="5599e-122">Return value</span></span>

<span data-ttu-id="5599e-123">S_OK</span><span class="sxs-lookup"><span data-stu-id="5599e-123">S_OK</span></span> 
  
> <span data-ttu-id="5599e-124">已成功返回的属性的访问级别和状态标志。</span><span class="sxs-lookup"><span data-stu-id="5599e-124">The access level and status flags for the properties were successfully returned.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="5599e-125">说明</span><span class="sxs-lookup"><span data-stu-id="5599e-125">Remarks</span></span>

<span data-ttu-id="5599e-126">**IPropData::HrGetPropAccess**方法检索一组标志指示的访问级别和一个或多个属性的状态。</span><span class="sxs-lookup"><span data-stu-id="5599e-126">The **IPropData::HrGetPropAccess** method retrieves a set of flags that indicates the access level and status for one or more properties.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="5599e-127">调用方注释：</span><span class="sxs-lookup"><span data-stu-id="5599e-127">Notes to callers:</span></span>

<span data-ttu-id="5599e-128">您可以使用**HrGetPropAccess**出于以下目的：</span><span class="sxs-lookup"><span data-stu-id="5599e-128">You can use **HrGetPropAccess** for the following purposes:</span></span> 
  
- <span data-ttu-id="5599e-129">若要确定客户端是否更改或删除可写属性。</span><span class="sxs-lookup"><span data-stu-id="5599e-129">To determine whether a client changed or deleted a writable property.</span></span>
    
- <span data-ttu-id="5599e-130">若要防止更改或删除属性使用[IMAPIProp](imapipropiunknown.md)方法客户端。</span><span class="sxs-lookup"><span data-stu-id="5599e-130">To prevent a client from changing or deleting a property by using the [IMAPIProp](imapipropiunknown.md) methods.</span></span> 
    
<span data-ttu-id="5599e-131">如果一个指向_lppPropTagArray_属性标记数组中的属性已被删除， **HrGetPropAccess**设置为 0 具有输出的数组项。</span><span class="sxs-lookup"><span data-stu-id="5599e-131">If one of the properties in the property tag array pointed to by  _lppPropTagArray_ has been deleted, **HrGetPropAccess** sets the array entry to 0 on output.</span></span> <span data-ttu-id="5599e-132">如果_lppPropTagArray_设为 NULL，一个对象的属性已被删除时，则数组中返回的已删除的属性。</span><span class="sxs-lookup"><span data-stu-id="5599e-132">If you set  _lppPropTagArray_ to NULL and one of the object's properties has been deleted, the deleted property is returned in the array.</span></span> 
  
<span data-ttu-id="5599e-133">如果已修改的属性，其 IPROP_DIRTY 标志设置在数组中对应的项的_lprgulAccess_点为。</span><span class="sxs-lookup"><span data-stu-id="5599e-133">If a property has been modified, its IPROP_DIRTY flag is set in the corresponding entry in the array that  _lprgulAccess_ points to.</span></span> <span data-ttu-id="5599e-134">IPROP_READONLY 和 IPROP_READWRITE 都不会将设置。</span><span class="sxs-lookup"><span data-stu-id="5599e-134">Neither IPROP_READONLY nor IPROP_READWRITE will be set.</span></span> 
  
<span data-ttu-id="5599e-135">如果未修改或删除属性，将设置仅 IPROP_READONLY 或 IPROP_READWRITE 标志。</span><span class="sxs-lookup"><span data-stu-id="5599e-135">If a property has not been modified or deleted, only the IPROP_READONLY or IPROP_READWRITE flag will be set.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="5599e-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5599e-136">See also</span></span>



[<span data-ttu-id="5599e-137">SPropTagArray</span><span class="sxs-lookup"><span data-stu-id="5599e-137">SPropTagArray</span></span>](sproptagarray.md)
  
[<span data-ttu-id="5599e-138">IPropData : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="5599e-138">IPropData : IMAPIProp</span></span>](ipropdataimapiprop.md)

