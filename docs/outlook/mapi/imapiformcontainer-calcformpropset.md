---
title: IMAPIFormContainerCalcFormPropSet
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIFormContainer.CalcFormPropSet
api_type:
- COM
ms.assetid: 594e3aac-a00f-422e-8e7a-949e4c9a3f8d
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: b15dc4e467644c2a0c3856372b550c3b55469f1a
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775389"
---
# <a name="imapiformcontainercalcformpropset"></a><span data-ttu-id="bcab4-103">IMAPIFormContainer::CalcFormPropSet</span><span class="sxs-lookup"><span data-stu-id="bcab4-103">IMAPIFormContainer::CalcFormPropSet</span></span>

  
  
<span data-ttu-id="bcab4-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="bcab4-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="bcab4-105">返回一个数组由安装窗体容器中的所有窗体的属性。</span><span class="sxs-lookup"><span data-stu-id="bcab4-105">Returns an array of the properties used by all forms installed in a form container.</span></span>
  
```cpp
HRESULT CalcFormPropSet(
  ULONG ulFlags,
  LPMAPIFORMPROPARRAY FAR * ppResults
);
```

## <a name="parameters"></a><span data-ttu-id="bcab4-106">参数</span><span class="sxs-lookup"><span data-stu-id="bcab4-106">Parameters</span></span>

 <span data-ttu-id="bcab4-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="bcab4-107">_ulFlags_</span></span>
  
> <span data-ttu-id="bcab4-108">[in]位掩码的标志，控制如何返回_ppResults_参数中的属性数组。</span><span class="sxs-lookup"><span data-stu-id="bcab4-108">[in] A bitmask of flags that controls how the property array in the  _ppResults_ parameter is returned.</span></span> <span data-ttu-id="bcab4-109">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="bcab4-109">The following flags can be set:</span></span> 
    
<span data-ttu-id="bcab4-110">FORMPROPSET_INTERSECTION</span><span class="sxs-lookup"><span data-stu-id="bcab4-110">FORMPROPSET_INTERSECTION</span></span> 
  
> <span data-ttu-id="bcab4-111">返回的数组包含窗体的属性的交点。</span><span class="sxs-lookup"><span data-stu-id="bcab4-111">The returned array contains the intersection of the forms' properties.</span></span>
    
<span data-ttu-id="bcab4-112">FORMPROPSET_UNION</span><span class="sxs-lookup"><span data-stu-id="bcab4-112">FORMPROPSET_UNION</span></span> 
  
> <span data-ttu-id="bcab4-113">返回的数组包含窗体的属性的合并。</span><span class="sxs-lookup"><span data-stu-id="bcab4-113">The returned array contains the union of the forms' properties.</span></span>
    
<span data-ttu-id="bcab4-114">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="bcab4-114">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="bcab4-115">数组中返回的字符串是 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="bcab4-115">The strings returned in the array are in Unicode format.</span></span> <span data-ttu-id="bcab4-116">如果未设置 MAPI_UNICODE 标志的字符串是以 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="bcab4-116">If the MAPI_UNICODE flag is not set, the strings are in ANSI format.</span></span>
    
 <span data-ttu-id="bcab4-117">_ppResults_</span><span class="sxs-lookup"><span data-stu-id="bcab4-117">_ppResults_</span></span>
  
> <span data-ttu-id="bcab4-118">[输出]指向返回[SMAPIFormPropArray](smapiformproparray.md)结构的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="bcab4-118">[out] A pointer to a pointer to the returned [SMAPIFormPropArray](smapiformproparray.md) structure.</span></span> <span data-ttu-id="bcab4-119">此结构包含所有安装的表单所使用的属性。</span><span class="sxs-lookup"><span data-stu-id="bcab4-119">This structure contains all properties used by the installed forms.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="bcab4-120">返回值</span><span class="sxs-lookup"><span data-stu-id="bcab4-120">Return value</span></span>

<span data-ttu-id="bcab4-121">S_OK</span><span class="sxs-lookup"><span data-stu-id="bcab4-121">S_OK</span></span> 
  
> <span data-ttu-id="bcab4-122">呼叫成功或多个预期值返回。</span><span class="sxs-lookup"><span data-stu-id="bcab4-122">The call succeeded and has returned the expected value or values.</span></span>
    
<span data-ttu-id="bcab4-123">MAPI_E_BAD_CHARWIDTH</span><span class="sxs-lookup"><span data-stu-id="bcab4-123">MAPI_E_BAD_CHARWIDTH</span></span> 
  
> <span data-ttu-id="bcab4-124">既设置了 MAPI_UNICODE 标志实现不支持 Unicode，或未设置 MAPI_UNICODE 并实现支持仅 Unicode。</span><span class="sxs-lookup"><span data-stu-id="bcab4-124">Either the MAPI_UNICODE flag was set and the implementation does not support Unicode, or MAPI_UNICODE was not set and the implementation supports only Unicode.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="bcab4-125">说明</span><span class="sxs-lookup"><span data-stu-id="bcab4-125">Remarks</span></span>

<span data-ttu-id="bcab4-126">客户端应用程序调用**IMAPIFormContainer::CalcFormPropSet**方法以获取属性由安装窗体容器中的所有窗体的数组。</span><span class="sxs-lookup"><span data-stu-id="bcab4-126">Client applications call the **IMAPIFormContainer::CalcFormPropSet** method to obtain an array of properties used by all forms installed in a form container.</span></span> <span data-ttu-id="bcab4-127">**IMAPIFormContainer::CalcFormPropSet**工作[IMAPIFormMgr::CalcFormPropSet](imapiformmgr-calcformpropset.md)方法，如之处在于它运行在某个特定的容器中注册的每个窗体上。</span><span class="sxs-lookup"><span data-stu-id="bcab4-127">**IMAPIFormContainer::CalcFormPropSet** works like the [IMAPIFormMgr::CalcFormPropSet](imapiformmgr-calcformpropset.md) method, except that it operates on every form registered in a particular container.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="bcab4-128">针对实施者的注释</span><span class="sxs-lookup"><span data-stu-id="bcab4-128">Notes to implementers</span></span>

<span data-ttu-id="bcab4-129">如果传递 MAPI_UNICODE，窗体库提供程序不支持 Unicode 字符串应返回 MAPI_E_BAD_CHARWIDTH。</span><span class="sxs-lookup"><span data-stu-id="bcab4-129">Form library providers that do not support Unicode strings should return MAPI_E_BAD_CHARWIDTH if MAPI_UNICODE is passed.</span></span>
  
## <a name="notes-to-callers"></a><span data-ttu-id="bcab4-130">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="bcab4-130">Notes to callers</span></span>

 <span data-ttu-id="bcab4-131">**IMAPIFormContainer::CalcFormPropSet**采用交集或的窗体的属性集，具体取决于的标记设置_ulFlags_参数中的联合，并将返回包含**SMAPIFormPropArray**结构生成组的属性。</span><span class="sxs-lookup"><span data-stu-id="bcab4-131">**IMAPIFormContainer::CalcFormPropSet** takes either an intersection or a union of the forms' property sets, depending on the flag set in the  _ulFlags_ parameter, and it returns an **SMAPIFormPropArray** structure that contains the resulting group of properties.</span></span> 
  
<span data-ttu-id="bcab4-132">如果客户端传入_ulFlags_MAPI_UNICODE 标志，所有返回的字符串是在 Unicode。</span><span class="sxs-lookup"><span data-stu-id="bcab4-132">If a client passes the MAPI_UNICODE flag in  _ulFlags_, all returned strings are Unicode.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="bcab4-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bcab4-133">See also</span></span>



[<span data-ttu-id="bcab4-134">IMAPIFormMgr::CalcFormPropSet</span><span class="sxs-lookup"><span data-stu-id="bcab4-134">IMAPIFormMgr::CalcFormPropSet</span></span>](imapiformmgr-calcformpropset.md)
  
[<span data-ttu-id="bcab4-135">SMAPIFormPropArray</span><span class="sxs-lookup"><span data-stu-id="bcab4-135">SMAPIFormPropArray</span></span>](smapiformproparray.md)
  
[<span data-ttu-id="bcab4-136">IMAPIFormContainer : IUnknown</span><span class="sxs-lookup"><span data-stu-id="bcab4-136">IMAPIFormContainer : IUnknown</span></span>](imapiformcontaineriunknown.md)

