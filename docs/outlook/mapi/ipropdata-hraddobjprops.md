---
title: IPropDataHrAddObjProps
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IPropData.HrAddObjProps
api_type:
- COM
ms.assetid: 683cf476-3c02-4b3b-939f-6fff6611f9aa
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: df63f08d3d453575816c4f7ab043f802023e21d0
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33416382"
---
# <a name="ipropdatahraddobjprops"></a><span data-ttu-id="dcfd5-103">IPropData::HrAddObjProps</span><span class="sxs-lookup"><span data-stu-id="dcfd5-103">IPropData::HrAddObjProps</span></span>

  
  
<span data-ttu-id="dcfd5-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="dcfd5-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="dcfd5-105">向对象添加一个或多个PT_OBJECT类型的属性。</span><span class="sxs-lookup"><span data-stu-id="dcfd5-105">Adds one or more properties of type PT_OBJECT to the object.</span></span>
  
```cpp
HRESULT HrAddObjProps(
  LPSPropTagArray lpPropTagArray,
  LPSPropProblemArray FAR * lppProblems
);
```

## <a name="parameters"></a><span data-ttu-id="dcfd5-106">参数</span><span class="sxs-lookup"><span data-stu-id="dcfd5-106">Parameters</span></span>

 <span data-ttu-id="dcfd5-107">_lpPropTagArray_</span><span class="sxs-lookup"><span data-stu-id="dcfd5-107">_lpPropTagArray_</span></span>
  
> <span data-ttu-id="dcfd5-108">[in]指向指示要添加的属性的属性标记数组的指针。</span><span class="sxs-lookup"><span data-stu-id="dcfd5-108">[in] A pointer to an array of property tags that indicate the properties to add.</span></span>
    
 <span data-ttu-id="dcfd5-109">_lppProblems_</span><span class="sxs-lookup"><span data-stu-id="dcfd5-109">_lppProblems_</span></span>
  
> <span data-ttu-id="dcfd5-110">[in， out]在输入时，指向 [SPropProblemArray](spropproblemarray.md) 结构或 NULL 的有效指针。</span><span class="sxs-lookup"><span data-stu-id="dcfd5-110">[in, out] On input, a valid pointer to an [SPropProblemArray](spropproblemarray.md) structure, or NULL.</span></span> <span data-ttu-id="dcfd5-111">在输出时，指向包含有关无法添加的属性的信息的结构的指针的指针或 NULL。</span><span class="sxs-lookup"><span data-stu-id="dcfd5-111">On output, a pointer to a pointer to a structure that contains information about properties that could not be added, or NULL.</span></span> <span data-ttu-id="dcfd5-112">只有当传入了有效的指针时，才返回一个指向属性问题数组结构的指针。</span><span class="sxs-lookup"><span data-stu-id="dcfd5-112">A pointer to a property problem array structure is returned only if a valid pointer is passed in.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="dcfd5-113">返回值</span><span class="sxs-lookup"><span data-stu-id="dcfd5-113">Return value</span></span>

<span data-ttu-id="dcfd5-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="dcfd5-114">S_OK</span></span> 
  
> <span data-ttu-id="dcfd5-115">已成功添加属性。</span><span class="sxs-lookup"><span data-stu-id="dcfd5-115">The properties were successfully added.</span></span>
    
<span data-ttu-id="dcfd5-116">MAPI_E_INVALID_TYPE</span><span class="sxs-lookup"><span data-stu-id="dcfd5-116">MAPI_E_INVALID_TYPE</span></span> 
  
> <span data-ttu-id="dcfd5-117">在  _lpPropTagArray_ 参数PT_OBJECT的数组中传递了除 PT_OBJECT 属性类型的属性。</span><span class="sxs-lookup"><span data-stu-id="dcfd5-117">A property type other than PT_OBJECT was passed in the array that the  _lpPropTagArray_ parameter points to.</span></span> 
    
<span data-ttu-id="dcfd5-118">MAPI_E_NO_ACCESS</span><span class="sxs-lookup"><span data-stu-id="dcfd5-118">MAPI_E_NO_ACCESS</span></span> 
  
> <span data-ttu-id="dcfd5-119">对象已设置为不允许读/写权限。</span><span class="sxs-lookup"><span data-stu-id="dcfd5-119">The object has been set not to allow read/write permission.</span></span>
    
<span data-ttu-id="dcfd5-120">MAPI_W_PARTIAL_COMPLETION</span><span class="sxs-lookup"><span data-stu-id="dcfd5-120">MAPI_W_PARTIAL_COMPLETION</span></span> 
  
> <span data-ttu-id="dcfd5-121">已添加某些（而不是全部）属性。</span><span class="sxs-lookup"><span data-stu-id="dcfd5-121">Some, but not all, of the properties were added.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="dcfd5-122">备注</span><span class="sxs-lookup"><span data-stu-id="dcfd5-122">Remarks</span></span>

<span data-ttu-id="dcfd5-123">**IPropData：：HrAddObjProps** 方法向对象添加一个或多个类型PT_OBJECT属性。</span><span class="sxs-lookup"><span data-stu-id="dcfd5-123">The **IPropData::HrAddObjProps** method adds one or more properties of type PT_OBJECT to the object.</span></span> <span data-ttu-id="dcfd5-124">**HrAddObjProps** 为对象属性提供了 [IMAPIProp：：SetProps](imapiprop-setprops.md) 方法的替代方法，因为无法通过调用 **SetProps 创建对象属性**。</span><span class="sxs-lookup"><span data-stu-id="dcfd5-124">**HrAddObjProps** provides an alternative to the [IMAPIProp::SetProps](imapiprop-setprops.md) method for object properties, because object properties cannot be created by calling **SetProps**.</span></span> <span data-ttu-id="dcfd5-125">添加对象属性会导致属性标记包含在 [IMAPIProp：：GetPropList](imapiprop-getproplist.md) 方法返回的属性标记列表中。</span><span class="sxs-lookup"><span data-stu-id="dcfd5-125">Adding an object property results in the property tag being included in the list of property tags that the [IMAPIProp::GetPropList](imapiprop-getproplist.md) method returns.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="dcfd5-126">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="dcfd5-126">Notes to callers</span></span>

<span data-ttu-id="dcfd5-127">如果 **HrAddObjProps** 返回 MAPI_W_PARTIAL_COMPLETION并且你已将  _lppProblems_ 设置为一个有效的指针，请检查返回的 [SPropProblemArray](spropproblemarray.md) 结构以找出未添加的属性。</span><span class="sxs-lookup"><span data-stu-id="dcfd5-127">If **HrAddObjProps** returns MAPI_W_PARTIAL_COMPLETION and you have set  _lppProblems_ to a valid pointer, check the returned [SPropProblemArray](spropproblemarray.md) structure to find out which properties were not added.</span></span> <span data-ttu-id="dcfd5-128">通常，唯一发生的问题是缺少内存。</span><span class="sxs-lookup"><span data-stu-id="dcfd5-128">Typically, the only problem that occurs is lack of memory.</span></span> <span data-ttu-id="dcfd5-129">完成 **SPropProblemArray** 结构后，通过调用 [MAPIFreeBuffer](mapifreebuffer.md) 函数释放它。</span><span class="sxs-lookup"><span data-stu-id="dcfd5-129">Free the **SPropProblemArray** structure by calling the [MAPIFreeBuffer](mapifreebuffer.md) function when you are finished with it.</span></span> 
  
<span data-ttu-id="dcfd5-130">若要添加属性，目标对象必须具有读/写权限。</span><span class="sxs-lookup"><span data-stu-id="dcfd5-130">To add a property, the target object must have read/write permission.</span></span> <span data-ttu-id="dcfd5-131">如果 **HrAddObjProps** MAPI_E_NO_ACCESS，则不能向对象添加属性，因为它不允许修改。</span><span class="sxs-lookup"><span data-stu-id="dcfd5-131">If **HrAddObjProps** returns MAPI_E_NO_ACCESS, you cannot add properties to the object because it does not permit modification.</span></span> <span data-ttu-id="dcfd5-132">若要在调用 **HrAddObjProps** 之前获取对象的读/写权限，请调用 [IPropData：：HrSetObjAccess，](ipropdata-hrsetobjaccess.md) 将  _ulAccess_ 参数设置为 IPROP_READWRITE。</span><span class="sxs-lookup"><span data-stu-id="dcfd5-132">To obtain read/write permission to an object prior to calling **HrAddObjProps**, call [IPropData::HrSetObjAccess](ipropdata-hrsetobjaccess.md) and set the  _ulAccess_ parameter to IPROP_READWRITE.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="dcfd5-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dcfd5-133">See also</span></span>



[<span data-ttu-id="dcfd5-134">MAPIFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="dcfd5-134">MAPIFreeBuffer</span></span>](mapifreebuffer.md)
  
[<span data-ttu-id="dcfd5-135">SPropProblemArray</span><span class="sxs-lookup"><span data-stu-id="dcfd5-135">SPropProblemArray</span></span>](spropproblemarray.md)
  
[<span data-ttu-id="dcfd5-136">SPropTagArray</span><span class="sxs-lookup"><span data-stu-id="dcfd5-136">SPropTagArray</span></span>](sproptagarray.md)
  
[<span data-ttu-id="dcfd5-137">IPropData : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="dcfd5-137">IPropData : IMAPIProp</span></span>](ipropdataimapiprop.md)

