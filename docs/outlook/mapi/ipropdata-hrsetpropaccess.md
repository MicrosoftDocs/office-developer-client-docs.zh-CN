---
title: IPropDataHrSetPropAccess
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IPropData.HrSetPropAccess
api_type:
- COM
ms.assetid: 02365050-5e8b-437c-925f-4eb0df646356
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: d0054e54d56fbe1cc6d6d783ffcd6330d8ab2e6b
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22564659"
---
# <a name="ipropdatahrsetpropaccess"></a><span data-ttu-id="8f581-103">IPropData::HrSetPropAccess</span><span class="sxs-lookup"><span data-stu-id="8f581-103">IPropData::HrSetPropAccess</span></span>

  
  
<span data-ttu-id="8f581-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="8f581-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="8f581-105">设置访问权限级别或一个或多个对象的属性的状态。</span><span class="sxs-lookup"><span data-stu-id="8f581-105">Sets the access level or status for one or more of the object's properties.</span></span>
  
```cpp
HRESULT HrSetPropAccess(
  LPSPropTagArray lpPropTagArray,
  ULONG FAR * rgulAccess
);
```

## <a name="parameters"></a><span data-ttu-id="8f581-106">参数</span><span class="sxs-lookup"><span data-stu-id="8f581-106">Parameters</span></span>

 <span data-ttu-id="8f581-107">_lpPropTagArray_</span><span class="sxs-lookup"><span data-stu-id="8f581-107">_lpPropTagArray_</span></span>
  
> <span data-ttu-id="8f581-108">[in]一个指向数组属性标记，指示要修改的属性。</span><span class="sxs-lookup"><span data-stu-id="8f581-108">[in] A pointer to an array of property tags that indicate the properties to be modified.</span></span> 
    
 <span data-ttu-id="8f581-109">_rgulAccess_</span><span class="sxs-lookup"><span data-stu-id="8f581-109">_rgulAccess_</span></span>
  
> <span data-ttu-id="8f581-110">[in]一个标志位掩码的数组。</span><span class="sxs-lookup"><span data-stu-id="8f581-110">[in] An array of flag bitmasks.</span></span> <span data-ttu-id="8f581-111">每位掩码指示的访问级别或状态，或同时为每个标识_lpPropTagArray_参数指向该数组中的属性。</span><span class="sxs-lookup"><span data-stu-id="8f581-111">Each bitmask indicates the access levels or status, or both, for each of the properties identified in the array that the  _lpPropTagArray_ parameter points to.</span></span> <span data-ttu-id="8f581-112">两个数组是位置_rgulAccess_中的第一个位掩码介绍的第一个属性的_lpPropTagArray_点到，依此类推。</span><span class="sxs-lookup"><span data-stu-id="8f581-112">The two arrays are positional in that the first bitmask in  _rgulAccess_ describes the first property that  _lpPropTagArray_ points to, and so on.</span></span> <span data-ttu-id="8f581-113">对于每个属性标记，可以设置一个访问级别标志和一个状态标志。</span><span class="sxs-lookup"><span data-stu-id="8f581-113">For each property tag, one access-level flag and one status flag can be set.</span></span> <span data-ttu-id="8f581-114">下表显示了可能的标志。</span><span class="sxs-lookup"><span data-stu-id="8f581-114">The following table shows the possible flags.</span></span> 
    
|<span data-ttu-id="8f581-115">**访问级别标志**</span><span class="sxs-lookup"><span data-stu-id="8f581-115">**Access-level flag**</span></span>|<span data-ttu-id="8f581-116">**状态标志**</span><span class="sxs-lookup"><span data-stu-id="8f581-116">**Status flag**</span></span>|
|:-----|:-----|
|<span data-ttu-id="8f581-117">IPROP_READONLY，指示无法修改属性</span><span class="sxs-lookup"><span data-stu-id="8f581-117">IPROP_READONLY, which indicates that the property cannot be modified</span></span>  <br/> |<span data-ttu-id="8f581-118">IPROP_CLEAN，这表明该属性不被修改。</span><span class="sxs-lookup"><span data-stu-id="8f581-118">IPROP_CLEAN, which indicates that the property has not been modified.</span></span>  <br/> |
|<span data-ttu-id="8f581-119">IPROP_READWRITE，指示可以修改的属性。</span><span class="sxs-lookup"><span data-stu-id="8f581-119">IPROP_READWRITE, which indicates that the property can be modified.</span></span>  <br/> |<span data-ttu-id="8f581-120">IPROP_DIRTY，这表明该属性已修改。</span><span class="sxs-lookup"><span data-stu-id="8f581-120">IPROP_DIRTY, which indicates that the property has been modified.</span></span>  <br/> |
   
## <a name="return-value"></a><span data-ttu-id="8f581-121">返回值</span><span class="sxs-lookup"><span data-stu-id="8f581-121">Return value</span></span>

<span data-ttu-id="8f581-122">S_OK</span><span class="sxs-lookup"><span data-stu-id="8f581-122">S_OK</span></span> 
  
> <span data-ttu-id="8f581-123">已成功设置访问级别和状态标志。</span><span class="sxs-lookup"><span data-stu-id="8f581-123">The access-level and status flags have been successfully set.</span></span>
    
<span data-ttu-id="8f581-124">MAPI_E_NO_ACCESS</span><span class="sxs-lookup"><span data-stu-id="8f581-124">MAPI_E_NO_ACCESS</span></span> 
  
> <span data-ttu-id="8f581-125">尝试对只读对象或对象对其呼叫者具有权限不足，无法设置属性。</span><span class="sxs-lookup"><span data-stu-id="8f581-125">An attempt was made to set a property on a read-only object or an object for which the caller has insufficient permissions.</span></span>
    
<span data-ttu-id="8f581-126">MAPI_E_INVALID_PARAMETER</span><span class="sxs-lookup"><span data-stu-id="8f581-126">MAPI_E_INVALID_PARAMETER</span></span> 
  
> <span data-ttu-id="8f581-127">_RgulAccess_参数包含无效的标志，如 IPROP_READONLY 和 IPROP_READWRITE 组合。</span><span class="sxs-lookup"><span data-stu-id="8f581-127">The  _rgulAccess_ parameter contains an invalid combination of flags, such as IPROP_READONLY and IPROP_READWRITE.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="8f581-128">注解</span><span class="sxs-lookup"><span data-stu-id="8f581-128">Remarks</span></span>

<span data-ttu-id="8f581-129">**IPropData::HrSetPropAccess**方法可更改访问级别和属性在_lpPropTagArray_参数指向的[SPropTagArray](sproptagarray.md)结构中的属性标记标识的状态。</span><span class="sxs-lookup"><span data-stu-id="8f581-129">The **IPropData::HrSetPropAccess** method changes the access level and status for the properties that are identified by the property tags in the [SPropTagArray](sproptagarray.md) structure pointed to by the  _lpPropTagArray_ parameter.</span></span> <span data-ttu-id="8f581-130">对于每个属性， _rgulAccess_数组中没有对应的项。</span><span class="sxs-lookup"><span data-stu-id="8f581-130">For each property, there is a corresponding entry in the  _rgulAccess_ array.</span></span> <span data-ttu-id="8f581-131">项可以设为一个标志，指示该属性的访问级别，另一个标志，指示其状态。</span><span class="sxs-lookup"><span data-stu-id="8f581-131">The entry can be set to one flag that indicates the property's access level and another flag that indicates its status.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="8f581-132">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="8f581-132">Notes to callers</span></span>

<span data-ttu-id="8f581-133">若要确定特定属性值更改时，并且可以更改一个或多个对象的属性的访问级别，请使用**HrSetPropAccess** 。</span><span class="sxs-lookup"><span data-stu-id="8f581-133">Use **HrSetPropAccess** to determine when a particular property value changes and to change the access level for one or more of an object's properties.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="8f581-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8f581-134">See also</span></span>



[<span data-ttu-id="8f581-135">SPropTagArray</span><span class="sxs-lookup"><span data-stu-id="8f581-135">SPropTagArray</span></span>](sproptagarray.md)
  
[<span data-ttu-id="8f581-136">IPropData : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="8f581-136">IPropData : IMAPIProp</span></span>](ipropdataimapiprop.md)

