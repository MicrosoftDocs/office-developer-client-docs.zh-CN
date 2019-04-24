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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32315531"
---
# <a name="ipropdatahraddobjprops"></a><span data-ttu-id="f8245-103">IPropData::HrAddObjProps</span><span class="sxs-lookup"><span data-stu-id="f8245-103">IPropData::HrAddObjProps</span></span>

  
  
<span data-ttu-id="f8245-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="f8245-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="f8245-105">将 PT_OBJECT 类型的一个或多个属性添加到对象中。</span><span class="sxs-lookup"><span data-stu-id="f8245-105">Adds one or more properties of type PT_OBJECT to the object.</span></span>
  
```cpp
HRESULT HrAddObjProps(
  LPSPropTagArray lpPropTagArray,
  LPSPropProblemArray FAR * lppProblems
);
```

## <a name="parameters"></a><span data-ttu-id="f8245-106">参数</span><span class="sxs-lookup"><span data-stu-id="f8245-106">Parameters</span></span>

 <span data-ttu-id="f8245-107">_lpPropTagArray_</span><span class="sxs-lookup"><span data-stu-id="f8245-107">_lpPropTagArray_</span></span>
  
> <span data-ttu-id="f8245-108">实时指向指示要添加的属性的属性标记数组的指针。</span><span class="sxs-lookup"><span data-stu-id="f8245-108">[in] A pointer to an array of property tags that indicate the properties to add.</span></span>
    
 <span data-ttu-id="f8245-109">_lppProblems_</span><span class="sxs-lookup"><span data-stu-id="f8245-109">_lppProblems_</span></span>
  
> <span data-ttu-id="f8245-110">[in, out]在输入时, 指向[SPropProblemArray](spropproblemarray.md)结构的有效指针或 NULL。</span><span class="sxs-lookup"><span data-stu-id="f8245-110">[in, out] On input, a valid pointer to an [SPropProblemArray](spropproblemarray.md) structure, or NULL.</span></span> <span data-ttu-id="f8245-111">在输出时, 指向指向结构的指针的指针, 该结构包含有关无法添加的属性的信息, 或为 NULL。</span><span class="sxs-lookup"><span data-stu-id="f8245-111">On output, a pointer to a pointer to a structure that contains information about properties that could not be added, or NULL.</span></span> <span data-ttu-id="f8245-112">仅当传入有效指针时, 才会返回指向属性问题数组结构的指针。</span><span class="sxs-lookup"><span data-stu-id="f8245-112">A pointer to a property problem array structure is returned only if a valid pointer is passed in.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="f8245-113">返回值</span><span class="sxs-lookup"><span data-stu-id="f8245-113">Return value</span></span>

<span data-ttu-id="f8245-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="f8245-114">S_OK</span></span> 
  
> <span data-ttu-id="f8245-115">成功添加了属性。</span><span class="sxs-lookup"><span data-stu-id="f8245-115">The properties were successfully added.</span></span>
    
<span data-ttu-id="f8245-116">MAPI_E_INVALID_TYPE</span><span class="sxs-lookup"><span data-stu-id="f8245-116">MAPI_E_INVALID_TYPE</span></span> 
  
> <span data-ttu-id="f8245-117">在_lpPropTagArray_参数指向的数组中传递了除 PT_OBJECT 之外的属性类型。</span><span class="sxs-lookup"><span data-stu-id="f8245-117">A property type other than PT_OBJECT was passed in the array that the  _lpPropTagArray_ parameter points to.</span></span> 
    
<span data-ttu-id="f8245-118">MAPI_E_NO_ACCESS</span><span class="sxs-lookup"><span data-stu-id="f8245-118">MAPI_E_NO_ACCESS</span></span> 
  
> <span data-ttu-id="f8245-119">对象已设置为不允许读/写权限。</span><span class="sxs-lookup"><span data-stu-id="f8245-119">The object has been set not to allow read/write permission.</span></span>
    
<span data-ttu-id="f8245-120">MAPI_W_PARTIAL_COMPLETION</span><span class="sxs-lookup"><span data-stu-id="f8245-120">MAPI_W_PARTIAL_COMPLETION</span></span> 
  
> <span data-ttu-id="f8245-121">添加了一些属性, 但并非全部。</span><span class="sxs-lookup"><span data-stu-id="f8245-121">Some, but not all, of the properties were added.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="f8245-122">注解</span><span class="sxs-lookup"><span data-stu-id="f8245-122">Remarks</span></span>

<span data-ttu-id="f8245-123">**IPropData:: HrAddObjProps**方法将类型为 PT_OBJECT 的一个或多个属性添加到对象中。</span><span class="sxs-lookup"><span data-stu-id="f8245-123">The **IPropData::HrAddObjProps** method adds one or more properties of type PT_OBJECT to the object.</span></span> <span data-ttu-id="f8245-124">**HrAddObjProps**为 object 属性提供了[IMAPIProp:: SetProps](imapiprop-setprops.md)方法的替代方法, 因为不能通过调用**SetProps**来创建对象属性。</span><span class="sxs-lookup"><span data-stu-id="f8245-124">**HrAddObjProps** provides an alternative to the [IMAPIProp::SetProps](imapiprop-setprops.md) method for object properties, because object properties cannot be created by calling **SetProps**.</span></span> <span data-ttu-id="f8245-125">添加对象属性将导致属性标记包含在[IMAPIProp:: GetPropList](imapiprop-getproplist.md)方法返回的属性标记列表中。</span><span class="sxs-lookup"><span data-stu-id="f8245-125">Adding an object property results in the property tag being included in the list of property tags that the [IMAPIProp::GetPropList](imapiprop-getproplist.md) method returns.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="f8245-126">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="f8245-126">Notes to callers</span></span>

<span data-ttu-id="f8245-127">如果**HrAddObjProps**返回 MAPI_W_PARTIAL_COMPLETION, 并且您已将_lppProblems_设置为有效指针, 请检查返回的[SPropProblemArray](spropproblemarray.md)结构以找出未添加的属性。</span><span class="sxs-lookup"><span data-stu-id="f8245-127">If **HrAddObjProps** returns MAPI_W_PARTIAL_COMPLETION and you have set  _lppProblems_ to a valid pointer, check the returned [SPropProblemArray](spropproblemarray.md) structure to find out which properties were not added.</span></span> <span data-ttu-id="f8245-128">通常情况下, 仅存在内存不足的问题。</span><span class="sxs-lookup"><span data-stu-id="f8245-128">Typically, the only problem that occurs is lack of memory.</span></span> <span data-ttu-id="f8245-129">完成**SPropProblemArray**结构后, 通过调用[MAPIFreeBuffer](mapifreebuffer.md)函数来释放该结构。</span><span class="sxs-lookup"><span data-stu-id="f8245-129">Free the **SPropProblemArray** structure by calling the [MAPIFreeBuffer](mapifreebuffer.md) function when you are finished with it.</span></span> 
  
<span data-ttu-id="f8245-130">若要添加属性, 目标对象必须具有读/写权限。</span><span class="sxs-lookup"><span data-stu-id="f8245-130">To add a property, the target object must have read/write permission.</span></span> <span data-ttu-id="f8245-131">如果**HrAddObjProps**返回 MAPI_E_NO_ACCESS, 则不能向该对象添加属性, 因为它不允许进行修改。</span><span class="sxs-lookup"><span data-stu-id="f8245-131">If **HrAddObjProps** returns MAPI_E_NO_ACCESS, you cannot add properties to the object because it does not permit modification.</span></span> <span data-ttu-id="f8245-132">若要在调用**HrAddObjProps**之前获取对象的读/写权限, 请调用[IPropData:: HrSetObjAccess](ipropdata-hrsetobjaccess.md)并将_ulAccess_参数设置为 IPROP_READWRITE。</span><span class="sxs-lookup"><span data-stu-id="f8245-132">To obtain read/write permission to an object prior to calling **HrAddObjProps**, call [IPropData::HrSetObjAccess](ipropdata-hrsetobjaccess.md) and set the  _ulAccess_ parameter to IPROP_READWRITE.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="f8245-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f8245-133">See also</span></span>



[<span data-ttu-id="f8245-134">MAPIFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="f8245-134">MAPIFreeBuffer</span></span>](mapifreebuffer.md)
  
[<span data-ttu-id="f8245-135">SPropProblemArray</span><span class="sxs-lookup"><span data-stu-id="f8245-135">SPropProblemArray</span></span>](spropproblemarray.md)
  
[<span data-ttu-id="f8245-136">SPropTagArray</span><span class="sxs-lookup"><span data-stu-id="f8245-136">SPropTagArray</span></span>](sproptagarray.md)
  
[<span data-ttu-id="f8245-137">IPropData : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="f8245-137">IPropData : IMAPIProp</span></span>](ipropdataimapiprop.md)

