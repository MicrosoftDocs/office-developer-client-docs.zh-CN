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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 985b763ade9670c064c6c338953debf7beaa2783
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776017"
---
# <a name="ipropdatahraddobjprops"></a><span data-ttu-id="43baf-103">IPropData::HrAddObjProps</span><span class="sxs-lookup"><span data-stu-id="43baf-103">IPropData::HrAddObjProps</span></span>

  
  
<span data-ttu-id="43baf-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="43baf-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="43baf-105">添加到对象类型 PT_OBJECT 的一个或多个属性。</span><span class="sxs-lookup"><span data-stu-id="43baf-105">Adds one or more properties of type PT_OBJECT to the object.</span></span>
  
```cpp
HRESULT HrAddObjProps(
  LPSPropTagArray lpPropTagArray,
  LPSPropProblemArray FAR * lppProblems
);
```

## <a name="parameters"></a><span data-ttu-id="43baf-106">参数</span><span class="sxs-lookup"><span data-stu-id="43baf-106">Parameters</span></span>

 <span data-ttu-id="43baf-107">_lpPropTagArray_</span><span class="sxs-lookup"><span data-stu-id="43baf-107">_lpPropTagArray_</span></span>
  
> <span data-ttu-id="43baf-108">[in]一个指向数组属性标记，指示要添加的属性。</span><span class="sxs-lookup"><span data-stu-id="43baf-108">[in] A pointer to an array of property tags that indicate the properties to add.</span></span>
    
 <span data-ttu-id="43baf-109">_lppProblems_</span><span class="sxs-lookup"><span data-stu-id="43baf-109">_lppProblems_</span></span>
  
> <span data-ttu-id="43baf-110">[传入、 传出]在输入，有效的指针，指向[SPropProblemArray](spropproblemarray.md)结构，则为 NULL。</span><span class="sxs-lookup"><span data-stu-id="43baf-110">[in, out] On input, a valid pointer to an [SPropProblemArray](spropproblemarray.md) structure, or NULL.</span></span> <span data-ttu-id="43baf-111">输出，为包含有关无法添加的属性的信息的结构指针的指针或 NULL。</span><span class="sxs-lookup"><span data-stu-id="43baf-111">On output, a pointer to a pointer to a structure that contains information about properties that could not be added, or NULL.</span></span> <span data-ttu-id="43baf-112">仅当有效指针传递中，则返回指向属性问题数组结构的指针。</span><span class="sxs-lookup"><span data-stu-id="43baf-112">A pointer to a property problem array structure is returned only if a valid pointer is passed in.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="43baf-113">返回值</span><span class="sxs-lookup"><span data-stu-id="43baf-113">Return value</span></span>

<span data-ttu-id="43baf-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="43baf-114">S_OK</span></span> 
  
> <span data-ttu-id="43baf-115">已成功添加属性。</span><span class="sxs-lookup"><span data-stu-id="43baf-115">The properties were successfully added.</span></span>
    
<span data-ttu-id="43baf-116">MAPI_E_INVALID_TYPE</span><span class="sxs-lookup"><span data-stu-id="43baf-116">MAPI_E_INVALID_TYPE</span></span> 
  
> <span data-ttu-id="43baf-117">属性类型以外 PT_OBJECT 传递_lpPropTagArray_参数指向该数组中。</span><span class="sxs-lookup"><span data-stu-id="43baf-117">A property type other than PT_OBJECT was passed in the array that the  _lpPropTagArray_ parameter points to.</span></span> 
    
<span data-ttu-id="43baf-118">MAPI_E_NO_ACCESS</span><span class="sxs-lookup"><span data-stu-id="43baf-118">MAPI_E_NO_ACCESS</span></span> 
  
> <span data-ttu-id="43baf-119">已设置的对象不是以允许读/写权限。</span><span class="sxs-lookup"><span data-stu-id="43baf-119">The object has been set not to allow read/write permission.</span></span>
    
<span data-ttu-id="43baf-120">MAPI_W_PARTIAL_COMPLETION</span><span class="sxs-lookup"><span data-stu-id="43baf-120">MAPI_W_PARTIAL_COMPLETION</span></span> 
  
> <span data-ttu-id="43baf-121">某些，而不是全部已添加的属性。</span><span class="sxs-lookup"><span data-stu-id="43baf-121">Some, but not all, of the properties were added.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="43baf-122">说明</span><span class="sxs-lookup"><span data-stu-id="43baf-122">Remarks</span></span>

<span data-ttu-id="43baf-123">**IPropData::HrAddObjProps**方法添加到对象类型 PT_OBJECT 的一个或多个属性。</span><span class="sxs-lookup"><span data-stu-id="43baf-123">The **IPropData::HrAddObjProps** method adds one or more properties of type PT_OBJECT to the object.</span></span> <span data-ttu-id="43baf-124">**HrAddObjProps**提供对象属性的[IMAPIProp::SetProps](imapiprop-setprops.md)方法的替代项，因为无法通过调用**SetProps**创建对象属性。</span><span class="sxs-lookup"><span data-stu-id="43baf-124">**HrAddObjProps** provides an alternative to the [IMAPIProp::SetProps](imapiprop-setprops.md) method for object properties, because object properties cannot be created by calling **SetProps**.</span></span> <span data-ttu-id="43baf-125">被包含在列表中的[IMAPIProp::GetPropList](imapiprop-getproplist.md)方法返回的属性标记属性标记中添加对象属性结果。</span><span class="sxs-lookup"><span data-stu-id="43baf-125">Adding an object property results in the property tag being included in the list of property tags that the [IMAPIProp::GetPropList](imapiprop-getproplist.md) method returns.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="43baf-126">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="43baf-126">Notes to callers</span></span>

<span data-ttu-id="43baf-127">如果**HrAddObjProps**返回 MAPI_W_PARTIAL_COMPLETION，并将_lppProblems_设置为有效的指针，检查返回的[SPropProblemArray](spropproblemarray.md)结构，以找出未添加哪些属性。</span><span class="sxs-lookup"><span data-stu-id="43baf-127">If **HrAddObjProps** returns MAPI_W_PARTIAL_COMPLETION and you have set  _lppProblems_ to a valid pointer, check the returned [SPropProblemArray](spropproblemarray.md) structure to find out which properties were not added.</span></span> <span data-ttu-id="43baf-128">通常，唯一发生的问题是内存不足。</span><span class="sxs-lookup"><span data-stu-id="43baf-128">Typically, the only problem that occurs is lack of memory.</span></span> <span data-ttu-id="43baf-129">通过在与之完成时调用[MAPIFreeBuffer](mapifreebuffer.md)函数释放**SPropProblemArray**结构。</span><span class="sxs-lookup"><span data-stu-id="43baf-129">Free the **SPropProblemArray** structure by calling the [MAPIFreeBuffer](mapifreebuffer.md) function when you are finished with it.</span></span> 
  
<span data-ttu-id="43baf-130">若要添加的属性，目标对象必须具有读/写权限。</span><span class="sxs-lookup"><span data-stu-id="43baf-130">To add a property, the target object must have read/write permission.</span></span> <span data-ttu-id="43baf-131">如果**HrAddObjProps**返回 MAPI_E_NO_ACCESS，不能对对象添加属性，因为它不允许修改。</span><span class="sxs-lookup"><span data-stu-id="43baf-131">If **HrAddObjProps** returns MAPI_E_NO_ACCESS, you cannot add properties to the object because it does not permit modification.</span></span> <span data-ttu-id="43baf-132">若要获取对之前调用**HrAddObjProps**对象的读/写权限，请调用[IPropData::HrSetObjAccess](ipropdata-hrsetobjaccess.md) ，并将_ulAccess_参数设置为 IPROP_READWRITE。</span><span class="sxs-lookup"><span data-stu-id="43baf-132">To obtain read/write permission to an object prior to calling **HrAddObjProps**, call [IPropData::HrSetObjAccess](ipropdata-hrsetobjaccess.md) and set the  _ulAccess_ parameter to IPROP_READWRITE.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="43baf-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="43baf-133">See also</span></span>



[<span data-ttu-id="43baf-134">MAPIFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="43baf-134">MAPIFreeBuffer</span></span>](mapifreebuffer.md)
  
[<span data-ttu-id="43baf-135">SPropProblemArray</span><span class="sxs-lookup"><span data-stu-id="43baf-135">SPropProblemArray</span></span>](spropproblemarray.md)
  
[<span data-ttu-id="43baf-136">SPropTagArray</span><span class="sxs-lookup"><span data-stu-id="43baf-136">SPropTagArray</span></span>](sproptagarray.md)
  
[<span data-ttu-id="43baf-137">IPropData : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="43baf-137">IPropData : IMAPIProp</span></span>](ipropdataimapiprop.md)

