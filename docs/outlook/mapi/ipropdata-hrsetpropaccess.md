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
ms.openlocfilehash: 9e443302e49bad4a586b657a6de298dafbeefab4
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32348676"
---
# <a name="ipropdatahrsetpropaccess"></a><span data-ttu-id="67717-103">IPropData::HrSetPropAccess</span><span class="sxs-lookup"><span data-stu-id="67717-103">IPropData::HrSetPropAccess</span></span>

  
  
<span data-ttu-id="67717-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="67717-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="67717-105">设置一个或多个对象属性的访问级别或状态。</span><span class="sxs-lookup"><span data-stu-id="67717-105">Sets the access level or status for one or more of the object's properties.</span></span>
  
```cpp
HRESULT HrSetPropAccess(
  LPSPropTagArray lpPropTagArray,
  ULONG FAR * rgulAccess
);
```

## <a name="parameters"></a><span data-ttu-id="67717-106">参数</span><span class="sxs-lookup"><span data-stu-id="67717-106">Parameters</span></span>

 <span data-ttu-id="67717-107">_lpPropTagArray_</span><span class="sxs-lookup"><span data-stu-id="67717-107">_lpPropTagArray_</span></span>
  
> <span data-ttu-id="67717-108">实时指向指示要修改的属性的属性标记数组的指针。</span><span class="sxs-lookup"><span data-stu-id="67717-108">[in] A pointer to an array of property tags that indicate the properties to be modified.</span></span> 
    
 <span data-ttu-id="67717-109">_rgulAccess_</span><span class="sxs-lookup"><span data-stu-id="67717-109">_rgulAccess_</span></span>
  
> <span data-ttu-id="67717-110">实时标记位掩码的数组。</span><span class="sxs-lookup"><span data-stu-id="67717-110">[in] An array of flag bitmasks.</span></span> <span data-ttu-id="67717-111">每个位掩码表示_lpPropTagArray_参数所指向的数组中标识的每个属性的访问级别或状态。</span><span class="sxs-lookup"><span data-stu-id="67717-111">Each bitmask indicates the access levels or status, or both, for each of the properties identified in the array that the  _lpPropTagArray_ parameter points to.</span></span> <span data-ttu-id="67717-112">这两个数组的位置如下所示: _rgulAccess_中的第一个位掩码描述_lpPropTagArray_指向的第一个属性, 等等。</span><span class="sxs-lookup"><span data-stu-id="67717-112">The two arrays are positional in that the first bitmask in  _rgulAccess_ describes the first property that  _lpPropTagArray_ points to, and so on.</span></span> <span data-ttu-id="67717-113">对于每个属性标记, 可以设置一个访问级别标志和一个状态标志。</span><span class="sxs-lookup"><span data-stu-id="67717-113">For each property tag, one access-level flag and one status flag can be set.</span></span> <span data-ttu-id="67717-114">下表显示了可能的标志。</span><span class="sxs-lookup"><span data-stu-id="67717-114">The following table shows the possible flags.</span></span> 
    
|<span data-ttu-id="67717-115">**访问级别标志**</span><span class="sxs-lookup"><span data-stu-id="67717-115">**Access-level flag**</span></span>|<span data-ttu-id="67717-116">**状态标志**</span><span class="sxs-lookup"><span data-stu-id="67717-116">**Status flag**</span></span>|
|:-----|:-----|
|<span data-ttu-id="67717-117">IPROP_READONLY, 表示无法修改属性</span><span class="sxs-lookup"><span data-stu-id="67717-117">IPROP_READONLY, which indicates that the property cannot be modified</span></span>  <br/> |<span data-ttu-id="67717-118">IPROP_CLEAN, 指示属性尚未修改。</span><span class="sxs-lookup"><span data-stu-id="67717-118">IPROP_CLEAN, which indicates that the property has not been modified.</span></span>  <br/> |
|<span data-ttu-id="67717-119">IPROP_READWRITE, 指示可以修改属性。</span><span class="sxs-lookup"><span data-stu-id="67717-119">IPROP_READWRITE, which indicates that the property can be modified.</span></span>  <br/> |<span data-ttu-id="67717-120">IPROP_DIRTY, 指示属性已被修改。</span><span class="sxs-lookup"><span data-stu-id="67717-120">IPROP_DIRTY, which indicates that the property has been modified.</span></span>  <br/> |
   
## <a name="return-value"></a><span data-ttu-id="67717-121">返回值</span><span class="sxs-lookup"><span data-stu-id="67717-121">Return value</span></span>

<span data-ttu-id="67717-122">S_OK</span><span class="sxs-lookup"><span data-stu-id="67717-122">S_OK</span></span> 
  
> <span data-ttu-id="67717-123">已成功设置了访问级别和状态标志。</span><span class="sxs-lookup"><span data-stu-id="67717-123">The access-level and status flags have been successfully set.</span></span>
    
<span data-ttu-id="67717-124">MAPI_E_NO_ACCESS</span><span class="sxs-lookup"><span data-stu-id="67717-124">MAPI_E_NO_ACCESS</span></span> 
  
> <span data-ttu-id="67717-125">试图设置只读对象或对象的属性, 该对象的调用方没有足够的权限。</span><span class="sxs-lookup"><span data-stu-id="67717-125">An attempt was made to set a property on a read-only object or an object for which the caller has insufficient permissions.</span></span>
    
<span data-ttu-id="67717-126">MAPI_E_INVALID_PARAMETER</span><span class="sxs-lookup"><span data-stu-id="67717-126">MAPI_E_INVALID_PARAMETER</span></span> 
  
> <span data-ttu-id="67717-127">_rgulAccess_参数包含无效的标志组合, 如 IPROP_READONLY 和 IPROP_READWRITE。</span><span class="sxs-lookup"><span data-stu-id="67717-127">The  _rgulAccess_ parameter contains an invalid combination of flags, such as IPROP_READONLY and IPROP_READWRITE.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="67717-128">注解</span><span class="sxs-lookup"><span data-stu-id="67717-128">Remarks</span></span>

<span data-ttu-id="67717-129">**IPropData:: HrSetPropAccess**方法更改由_lpPropTagArray_参数指向的[SPropTagArray](sproptagarray.md)结构中的属性标记所标识的属性的访问级别和状态。</span><span class="sxs-lookup"><span data-stu-id="67717-129">The **IPropData::HrSetPropAccess** method changes the access level and status for the properties that are identified by the property tags in the [SPropTagArray](sproptagarray.md) structure pointed to by the  _lpPropTagArray_ parameter.</span></span> <span data-ttu-id="67717-130">对于每个属性, _rgulAccess_数组中都有对应的条目。</span><span class="sxs-lookup"><span data-stu-id="67717-130">For each property, there is a corresponding entry in the  _rgulAccess_ array.</span></span> <span data-ttu-id="67717-131">该条目可设置为一个指示属性的访问级别和另一个指示其状态的标志的标志。</span><span class="sxs-lookup"><span data-stu-id="67717-131">The entry can be set to one flag that indicates the property's access level and another flag that indicates its status.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="67717-132">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="67717-132">Notes to callers</span></span>

<span data-ttu-id="67717-133">使用**HrSetPropAccess**来确定特定属性值何时更改, 并更改一个或多个对象的属性的访问级别。</span><span class="sxs-lookup"><span data-stu-id="67717-133">Use **HrSetPropAccess** to determine when a particular property value changes and to change the access level for one or more of an object's properties.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="67717-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="67717-134">See also</span></span>



[<span data-ttu-id="67717-135">SPropTagArray</span><span class="sxs-lookup"><span data-stu-id="67717-135">SPropTagArray</span></span>](sproptagarray.md)
  
[<span data-ttu-id="67717-136">IPropData : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="67717-136">IPropData : IMAPIProp</span></span>](ipropdataimapiprop.md)

