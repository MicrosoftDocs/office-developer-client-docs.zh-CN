---
title: IMAPIFormMgrCalcFormPropSet
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIFormMgr.CalcFormPropSet
api_type:
- COM
ms.assetid: ab302bfd-5cff-49b4-b0d2-308ae5af478d
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 5380b6541e609c17a9005c3390c6d5db06155306
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22567242"
---
# <a name="imapiformmgrcalcformpropset"></a><span data-ttu-id="a7920-103">IMAPIFormMgr::CalcFormPropSet</span><span class="sxs-lookup"><span data-stu-id="a7920-103">IMAPIFormMgr::CalcFormPropSet</span></span>

  
  
<span data-ttu-id="a7920-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="a7920-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="a7920-105">返回一个数组的一组表单使用的属性。</span><span class="sxs-lookup"><span data-stu-id="a7920-105">Returns an array of the properties that a group of forms uses.</span></span>
  
```cpp
HRESULT CalcFormPropSet(
  LPSMAPIFORMINFOARRAY pfrminfoarray,
  ULONG ulFlags,
  LPMAPIFORMPROPARRAY FAR * ppResults
);
```

## <a name="parameters"></a><span data-ttu-id="a7920-106">参数</span><span class="sxs-lookup"><span data-stu-id="a7920-106">Parameters</span></span>

 <span data-ttu-id="a7920-107">_pfrminfoarray_</span><span class="sxs-lookup"><span data-stu-id="a7920-107">_pfrminfoarray_</span></span>
  
> <span data-ttu-id="a7920-108">[in]一个指向确定要为其返回属性的窗体的窗体信息对象的数组。</span><span class="sxs-lookup"><span data-stu-id="a7920-108">[in] A pointer to an array of form information objects that identify the forms for which to return properties.</span></span>
    
 <span data-ttu-id="a7920-109">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="a7920-109">_ulFlags_</span></span>
  
> <span data-ttu-id="a7920-110">[in]位掩码的标志，控制如何返回_ppResults_参数中的属性数组。</span><span class="sxs-lookup"><span data-stu-id="a7920-110">[in] A bitmask of flags that controls how the property array in the  _ppResults_ parameter is returned.</span></span> <span data-ttu-id="a7920-111">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="a7920-111">The following flags can be set:</span></span> 
    
<span data-ttu-id="a7920-112">FORMPROPSET_INTERSECTION</span><span class="sxs-lookup"><span data-stu-id="a7920-112">FORMPROPSET_INTERSECTION</span></span> 
  
> <span data-ttu-id="a7920-113">返回的数组包含窗体的属性的交点。</span><span class="sxs-lookup"><span data-stu-id="a7920-113">The returned array contains the intersection of the form's properties.</span></span>
    
<span data-ttu-id="a7920-114">FORMPROPSET_UNION</span><span class="sxs-lookup"><span data-stu-id="a7920-114">FORMPROPSET_UNION</span></span> 
  
> <span data-ttu-id="a7920-115">返回的数组包含窗体的属性的合并。</span><span class="sxs-lookup"><span data-stu-id="a7920-115">The returned array contains the union of the form's properties.</span></span>
    
<span data-ttu-id="a7920-116">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="a7920-116">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="a7920-117">数组中返回的字符串是 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="a7920-117">The strings returned in the array are in Unicode format.</span></span> <span data-ttu-id="a7920-118">如果未设置 MAPI_UNICODE 标志的字符串是以 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="a7920-118">If the MAPI_UNICODE flag is not set, the strings are in ANSI format.</span></span>
    
 <span data-ttu-id="a7920-119">_ppResults_</span><span class="sxs-lookup"><span data-stu-id="a7920-119">_ppResults_</span></span>
  
> <span data-ttu-id="a7920-120">[输出]指向返回[SMAPIFormPropArray](smapiformproparray.md)结构，其中包含表单使用的属性的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="a7920-120">[out] A pointer to a pointer to the returned [SMAPIFormPropArray](smapiformproparray.md) structure, which contains the properties that the forms use.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="a7920-121">返回值</span><span class="sxs-lookup"><span data-stu-id="a7920-121">Return value</span></span>

<span data-ttu-id="a7920-122">S_OK</span><span class="sxs-lookup"><span data-stu-id="a7920-122">S_OK</span></span> 
  
> <span data-ttu-id="a7920-123">呼叫成功，并返回预期的值。</span><span class="sxs-lookup"><span data-stu-id="a7920-123">The call succeeded and returned the expected value or values.</span></span>
    
<span data-ttu-id="a7920-124">MAPI_E_BAD_CHARWIDTH</span><span class="sxs-lookup"><span data-stu-id="a7920-124">MAPI_E_BAD_CHARWIDTH</span></span> 
  
> <span data-ttu-id="a7920-125">既设置了 MAPI_UNICODE 标志实现不支持 Unicode，或未设置 MAPI_UNICODE 并实现支持仅 Unicode。</span><span class="sxs-lookup"><span data-stu-id="a7920-125">Either the MAPI_UNICODE flag was set and the implementation does not support Unicode, or MAPI_UNICODE was not set and the implementation supports only Unicode.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="a7920-126">注解</span><span class="sxs-lookup"><span data-stu-id="a7920-126">Remarks</span></span>

<span data-ttu-id="a7920-127">表单查看器调用**IMAPIFormMgr::CalcFormPropSet**方法以获取的属性的一组窗体使用数组。</span><span class="sxs-lookup"><span data-stu-id="a7920-127">Form viewers call the **IMAPIFormMgr::CalcFormPropSet** method to obtain an array of the properties that a group of forms uses.</span></span> <span data-ttu-id="a7920-128">**CalcFormPropSet**采用任一交集或联合这些窗体的属性的设置，具体取决于的标记设置中_ulFlags_参数，并将返回**SMAPIFormPropArray**结构，其中包含的生成组属性。</span><span class="sxs-lookup"><span data-stu-id="a7920-128">**CalcFormPropSet** takes either an intersection or a union of these forms' property sets, depending on the flag set in the  _ulFlags_ parameter, and it returns an **SMAPIFormPropArray** structure that contains the resulting group of properties.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="a7920-129">针对实施者的注释</span><span class="sxs-lookup"><span data-stu-id="a7920-129">Notes to implementers</span></span>

<span data-ttu-id="a7920-130">如果表单查看器_ulFlags_参数中传递 MAPI_UNICODE 标志，应以 Unicode 字符串形式返回所有字符串。</span><span class="sxs-lookup"><span data-stu-id="a7920-130">If a form viewer passes the MAPI_UNICODE flag in the  _ulFlags_ parameter, all strings should be returned as Unicode strings.</span></span> <span data-ttu-id="a7920-131">如果传递 MAPI_UNICODE，窗体库提供程序不支持 Unicode 字符串应返回 MAPI_E_BAD_CHARWIDTH。</span><span class="sxs-lookup"><span data-stu-id="a7920-131">Form library providers that do not support Unicode strings should return MAPI_E_BAD_CHARWIDTH if MAPI_UNICODE is passed.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="a7920-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a7920-132">See also</span></span>



[<span data-ttu-id="a7920-133">SMAPIFormPropArray</span><span class="sxs-lookup"><span data-stu-id="a7920-133">SMAPIFormPropArray</span></span>](smapiformproparray.md)
  
[<span data-ttu-id="a7920-134">IMAPIFormMgr : IUnknown</span><span class="sxs-lookup"><span data-stu-id="a7920-134">IMAPIFormMgr : IUnknown</span></span>](imapiformmgriunknown.md)

