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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: bf072aba27c90b7cea80c464e17fafb47524b695
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33436424"
---
# <a name="imapiformmgrcalcformpropset"></a><span data-ttu-id="f27e0-103">IMAPIFormMgr::CalcFormPropSet</span><span class="sxs-lookup"><span data-stu-id="f27e0-103">IMAPIFormMgr::CalcFormPropSet</span></span>

  
  
<span data-ttu-id="f27e0-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="f27e0-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="f27e0-105">返回一组窗体使用的属性的数组。</span><span class="sxs-lookup"><span data-stu-id="f27e0-105">Returns an array of the properties that a group of forms uses.</span></span>
  
```cpp
HRESULT CalcFormPropSet(
  LPSMAPIFORMINFOARRAY pfrminfoarray,
  ULONG ulFlags,
  LPMAPIFORMPROPARRAY FAR * ppResults
);
```

## <a name="parameters"></a><span data-ttu-id="f27e0-106">参数</span><span class="sxs-lookup"><span data-stu-id="f27e0-106">Parameters</span></span>

 <span data-ttu-id="f27e0-107">_pfrminfoarray_</span><span class="sxs-lookup"><span data-stu-id="f27e0-107">_pfrminfoarray_</span></span>
  
> <span data-ttu-id="f27e0-108">实时指向表单信息对象数组的指针, 这些对象标识要为其返回属性的窗体。</span><span class="sxs-lookup"><span data-stu-id="f27e0-108">[in] A pointer to an array of form information objects that identify the forms for which to return properties.</span></span>
    
 <span data-ttu-id="f27e0-109">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="f27e0-109">_ulFlags_</span></span>
  
> <span data-ttu-id="f27e0-110">实时标志的位掩码, 用于控制如何返回_ppResults_参数中的属性数组。</span><span class="sxs-lookup"><span data-stu-id="f27e0-110">[in] A bitmask of flags that controls how the property array in the  _ppResults_ parameter is returned.</span></span> <span data-ttu-id="f27e0-111">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="f27e0-111">The following flags can be set:</span></span> 
    
<span data-ttu-id="f27e0-112">FORMPROPSET_INTERSECTION</span><span class="sxs-lookup"><span data-stu-id="f27e0-112">FORMPROPSET_INTERSECTION</span></span> 
  
> <span data-ttu-id="f27e0-113">返回的数组包含窗体属性的交集。</span><span class="sxs-lookup"><span data-stu-id="f27e0-113">The returned array contains the intersection of the form's properties.</span></span>
    
<span data-ttu-id="f27e0-114">FORMPROPSET_UNION</span><span class="sxs-lookup"><span data-stu-id="f27e0-114">FORMPROPSET_UNION</span></span> 
  
> <span data-ttu-id="f27e0-115">返回的数组包含表单属性的联合。</span><span class="sxs-lookup"><span data-stu-id="f27e0-115">The returned array contains the union of the form's properties.</span></span>
    
<span data-ttu-id="f27e0-116">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="f27e0-116">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="f27e0-117">数组中返回的字符串采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="f27e0-117">The strings returned in the array are in Unicode format.</span></span> <span data-ttu-id="f27e0-118">如果未设置 MAPI_UNICODE 标志, 则字符串将采用 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="f27e0-118">If the MAPI_UNICODE flag is not set, the strings are in ANSI format.</span></span>
    
 <span data-ttu-id="f27e0-119">_ppResults_</span><span class="sxs-lookup"><span data-stu-id="f27e0-119">_ppResults_</span></span>
  
> <span data-ttu-id="f27e0-120">排除指向返回的[SMAPIFormPropArray](smapiformproparray.md)结构的指针的指针, 该指针包含表单使用的属性。</span><span class="sxs-lookup"><span data-stu-id="f27e0-120">[out] A pointer to a pointer to the returned [SMAPIFormPropArray](smapiformproparray.md) structure, which contains the properties that the forms use.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="f27e0-121">返回值</span><span class="sxs-lookup"><span data-stu-id="f27e0-121">Return value</span></span>

<span data-ttu-id="f27e0-122">S_OK</span><span class="sxs-lookup"><span data-stu-id="f27e0-122">S_OK</span></span> 
  
> <span data-ttu-id="f27e0-123">调用成功, 并返回了所需的一个或一些值。</span><span class="sxs-lookup"><span data-stu-id="f27e0-123">The call succeeded and returned the expected value or values.</span></span>
    
<span data-ttu-id="f27e0-124">MAPI_E_BAD_CHARWIDTH</span><span class="sxs-lookup"><span data-stu-id="f27e0-124">MAPI_E_BAD_CHARWIDTH</span></span> 
  
> <span data-ttu-id="f27e0-125">设置了 MAPI_UNICODE 标志, 且实现不支持 unicode, 或者未设置 MAPI_UNICODE, 且实现仅支持 UNICODE。</span><span class="sxs-lookup"><span data-stu-id="f27e0-125">Either the MAPI_UNICODE flag was set and the implementation does not support Unicode, or MAPI_UNICODE was not set and the implementation supports only Unicode.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="f27e0-126">说明</span><span class="sxs-lookup"><span data-stu-id="f27e0-126">Remarks</span></span>

<span data-ttu-id="f27e0-127">表单查看者调用**IMAPIFormMgr:: CalcFormPropSet**方法以获取一组表单使用的属性的数组。</span><span class="sxs-lookup"><span data-stu-id="f27e0-127">Form viewers call the **IMAPIFormMgr::CalcFormPropSet** method to obtain an array of the properties that a group of forms uses.</span></span> <span data-ttu-id="f27e0-128">**CalcFormPropSet**采用相交或联合这些 forms 的属性集, 具体取决于在_ulFlags_参数中设置的标志, 并且它将返回一个**SMAPIFormPropArray**结构, 其中包含生成的一组属性.</span><span class="sxs-lookup"><span data-stu-id="f27e0-128">**CalcFormPropSet** takes either an intersection or a union of these forms' property sets, depending on the flag set in the  _ulFlags_ parameter, and it returns an **SMAPIFormPropArray** structure that contains the resulting group of properties.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="f27e0-129">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="f27e0-129">Notes to implementers</span></span>

<span data-ttu-id="f27e0-130">如果表单查看器在_ulFlags_参数中传递 MAPI_UNICODE 标志, 则所有字符串都应以 UNICODE 字符串的形式返回。</span><span class="sxs-lookup"><span data-stu-id="f27e0-130">If a form viewer passes the MAPI_UNICODE flag in the  _ulFlags_ parameter, all strings should be returned as Unicode strings.</span></span> <span data-ttu-id="f27e0-131">如果 MAPI_UNICODE 已传递, 则不支持 Unicode 字符串的表单库提供程序应返回 MAPI_E_BAD_CHARWIDTH。</span><span class="sxs-lookup"><span data-stu-id="f27e0-131">Form library providers that do not support Unicode strings should return MAPI_E_BAD_CHARWIDTH if MAPI_UNICODE is passed.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="f27e0-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f27e0-132">See also</span></span>



[<span data-ttu-id="f27e0-133">SMAPIFormPropArray</span><span class="sxs-lookup"><span data-stu-id="f27e0-133">SMAPIFormPropArray</span></span>](smapiformproparray.md)
  
[<span data-ttu-id="f27e0-134">IMAPIFormMgr : IUnknown</span><span class="sxs-lookup"><span data-stu-id="f27e0-134">IMAPIFormMgr : IUnknown</span></span>](imapiformmgriunknown.md)

