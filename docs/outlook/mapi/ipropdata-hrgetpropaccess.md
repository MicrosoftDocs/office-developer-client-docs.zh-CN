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
ms.openlocfilehash: 5e36cf12b7a5b1643f5a0ec97223030718195a7d
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33433435"
---
# <a name="ipropdatahrgetpropaccess"></a><span data-ttu-id="0d3ba-103">IPropData::HrGetPropAccess</span><span class="sxs-lookup"><span data-stu-id="0d3ba-103">IPropData::HrGetPropAccess</span></span>

  
  
<span data-ttu-id="0d3ba-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="0d3ba-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="0d3ba-105">检索一个或多个对象属性的访问级别和状态。</span><span class="sxs-lookup"><span data-stu-id="0d3ba-105">Retrieves the access level and status for one or more of the object's properties.</span></span>
  
```cpp
HRESULT HrGetPropAccess(
  LPSPropTagArray FAR * lppPropTagArray,
  ULONG FAR * FAR * lprgulAccess
);
```

## <a name="parameters"></a><span data-ttu-id="0d3ba-106">参数</span><span class="sxs-lookup"><span data-stu-id="0d3ba-106">Parameters</span></span>

 <span data-ttu-id="0d3ba-107">_lppPropTagArray_</span><span class="sxs-lookup"><span data-stu-id="0d3ba-107">_lppPropTagArray_</span></span>
  
> <span data-ttu-id="0d3ba-108">[in, out]在输入时, 指明要检索其访问级别和状态的属性的一组属性标记。否则为指向 NULL 的指针, 指示**HrGetPropAccess**应检索所有属性的访问级别和状态。</span><span class="sxs-lookup"><span data-stu-id="0d3ba-108">[in, out] On input, an array of property tags that indicate the properties for which to retrieve access levels and status; otherwise, a pointer to NULL, which indicates that **HrGetPropAccess** should retrieve access levels and status for all properties.</span></span> <span data-ttu-id="0d3ba-109">在输出时, 为其检索访问和状态标志的一组属性标记。</span><span class="sxs-lookup"><span data-stu-id="0d3ba-109">On output, an array of property tags for which access and status flags were retrieved.</span></span> <span data-ttu-id="0d3ba-110">这些标志存储在由_lprgulAccess_参数指向的数组中。</span><span class="sxs-lookup"><span data-stu-id="0d3ba-110">The flags are stored in the array pointed to by the  _lprgulAccess_ parameter.</span></span> 
    
 <span data-ttu-id="0d3ba-111">_lprgulAccess_</span><span class="sxs-lookup"><span data-stu-id="0d3ba-111">_lprgulAccess_</span></span>
  
> <span data-ttu-id="0d3ba-112">排除指向标志位掩码数组的指针。</span><span class="sxs-lookup"><span data-stu-id="0d3ba-112">[out] A pointer to an array of flag bitmasks.</span></span> <span data-ttu-id="0d3ba-113">每个位掩码表示由_lpPropTagArray_参数所指向的数组中标识的每个属性的访问级别或状态。</span><span class="sxs-lookup"><span data-stu-id="0d3ba-113">Each bitmask indicates the access levels or status, or both, for each of the properties identified in the array pointed to by the  _lpPropTagArray_ parameter.</span></span> <span data-ttu-id="0d3ba-114">这两个数组的位置是_lprgulAccess_指向的第一个位掩码, 它描述_lpPropTagArray_指向的第一个属性, 依此类推。</span><span class="sxs-lookup"><span data-stu-id="0d3ba-114">The two arrays are positional in that the first bitmask that  _lprgulAccess_ points to describes the first property that  _lpPropTagArray_ points to, and so on.</span></span> <span data-ttu-id="0d3ba-115">对于每个属性标记, 可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="0d3ba-115">For each property tag, the following flags can be set:</span></span> 
    
|<span data-ttu-id="0d3ba-116">**访问级别标志**</span><span class="sxs-lookup"><span data-stu-id="0d3ba-116">**Access-level flag**</span></span>|<span data-ttu-id="0d3ba-117">**状态标志**</span><span class="sxs-lookup"><span data-stu-id="0d3ba-117">**Status flag**</span></span>|
|:-----|:-----|
|<span data-ttu-id="0d3ba-118">IPROP_READONLY, 指示属性不能修改。</span><span class="sxs-lookup"><span data-stu-id="0d3ba-118">IPROP_READONLY, which indicates that the property cannot be modified.</span></span>  <br/> |<span data-ttu-id="0d3ba-119">IPROP_CLEAN, 指示属性尚未修改。</span><span class="sxs-lookup"><span data-stu-id="0d3ba-119">IPROP_CLEAN, which indicates that the property has not been modified.</span></span>  <br/> |
|<span data-ttu-id="0d3ba-120">IPROP_READWRITE, 指示可以修改属性。</span><span class="sxs-lookup"><span data-stu-id="0d3ba-120">IPROP_READWRITE, which indicates that the property can be modified.</span></span>  <br/> |<span data-ttu-id="0d3ba-121">IPROP_DIRTY, 指示属性已被修改。</span><span class="sxs-lookup"><span data-stu-id="0d3ba-121">IPROP_DIRTY, which indicates that the property has been modified.</span></span>  <br/> |
   
## <a name="return-value"></a><span data-ttu-id="0d3ba-122">返回值</span><span class="sxs-lookup"><span data-stu-id="0d3ba-122">Return value</span></span>

<span data-ttu-id="0d3ba-123">S_OK</span><span class="sxs-lookup"><span data-stu-id="0d3ba-123">S_OK</span></span> 
  
> <span data-ttu-id="0d3ba-124">成功返回属性的访问级别和状态标志。</span><span class="sxs-lookup"><span data-stu-id="0d3ba-124">The access level and status flags for the properties were successfully returned.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="0d3ba-125">说明</span><span class="sxs-lookup"><span data-stu-id="0d3ba-125">Remarks</span></span>

<span data-ttu-id="0d3ba-126">**IPropData:: HrGetPropAccess**方法检索一组标志, 这些标志指示一个或多个属性的访问级别和状态。</span><span class="sxs-lookup"><span data-stu-id="0d3ba-126">The **IPropData::HrGetPropAccess** method retrieves a set of flags that indicates the access level and status for one or more properties.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="0d3ba-127">调用者注意：</span><span class="sxs-lookup"><span data-stu-id="0d3ba-127">Notes to callers:</span></span>

<span data-ttu-id="0d3ba-128">您可以使用**HrGetPropAccess**来实现以下目的:</span><span class="sxs-lookup"><span data-stu-id="0d3ba-128">You can use **HrGetPropAccess** for the following purposes:</span></span> 
  
- <span data-ttu-id="0d3ba-129">确定客户端是否更改或删除了可写属性。</span><span class="sxs-lookup"><span data-stu-id="0d3ba-129">To determine whether a client changed or deleted a writable property.</span></span>
    
- <span data-ttu-id="0d3ba-130">若要防止客户端使用[IMAPIProp](imapipropiunknown.md)方法来更改或删除属性。</span><span class="sxs-lookup"><span data-stu-id="0d3ba-130">To prevent a client from changing or deleting a property by using the [IMAPIProp](imapipropiunknown.md) methods.</span></span> 
    
<span data-ttu-id="0d3ba-131">如果_lppPropTagArray_所指向的属性标记数组中的某个属性已被删除, 则**HrGetPropAccess**会在输出中将数组项设置为0。</span><span class="sxs-lookup"><span data-stu-id="0d3ba-131">If one of the properties in the property tag array pointed to by  _lppPropTagArray_ has been deleted, **HrGetPropAccess** sets the array entry to 0 on output.</span></span> <span data-ttu-id="0d3ba-132">如果将_lppPropTagArray_设置为 NULL, 并且已删除某个对象的属性, 则会在数组中返回 deleted 属性。</span><span class="sxs-lookup"><span data-stu-id="0d3ba-132">If you set  _lppPropTagArray_ to NULL and one of the object's properties has been deleted, the deleted property is returned in the array.</span></span> 
  
<span data-ttu-id="0d3ba-133">如果已修改某个属性, 则会在_lprgulAccess_指向的数组中对应的条目中设置其 IPROP_DIRTY 标志。</span><span class="sxs-lookup"><span data-stu-id="0d3ba-133">If a property has been modified, its IPROP_DIRTY flag is set in the corresponding entry in the array that  _lprgulAccess_ points to.</span></span> <span data-ttu-id="0d3ba-134">不会设置 IPROP_READONLY, 也不会设置 IPROP_READWRITE。</span><span class="sxs-lookup"><span data-stu-id="0d3ba-134">Neither IPROP_READONLY nor IPROP_READWRITE will be set.</span></span> 
  
<span data-ttu-id="0d3ba-135">如果尚未修改或删除某个属性, 将仅设置 IPROP_READONLY 或 IPROP_READWRITE 标志。</span><span class="sxs-lookup"><span data-stu-id="0d3ba-135">If a property has not been modified or deleted, only the IPROP_READONLY or IPROP_READWRITE flag will be set.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="0d3ba-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0d3ba-136">See also</span></span>



[<span data-ttu-id="0d3ba-137">SPropTagArray</span><span class="sxs-lookup"><span data-stu-id="0d3ba-137">SPropTagArray</span></span>](sproptagarray.md)
  
[<span data-ttu-id="0d3ba-138">IPropData : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="0d3ba-138">IPropData : IMAPIProp</span></span>](ipropdataimapiprop.md)

