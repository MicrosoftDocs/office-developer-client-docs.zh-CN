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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: ec1933f80f211c7c381f9de6b15d414932b9a78e
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32286585"
---
# <a name="imapiformcontainercalcformpropset"></a><span data-ttu-id="5a1c8-103">IMAPIFormContainer::CalcFormPropSet</span><span class="sxs-lookup"><span data-stu-id="5a1c8-103">IMAPIFormContainer::CalcFormPropSet</span></span>

  
  
<span data-ttu-id="5a1c8-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="5a1c8-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="5a1c8-105">返回安装在表单容器中的所有表单所使用的属性的数组。</span><span class="sxs-lookup"><span data-stu-id="5a1c8-105">Returns an array of the properties used by all forms installed in a form container.</span></span>
  
```cpp
HRESULT CalcFormPropSet(
  ULONG ulFlags,
  LPMAPIFORMPROPARRAY FAR * ppResults
);
```

## <a name="parameters"></a><span data-ttu-id="5a1c8-106">参数</span><span class="sxs-lookup"><span data-stu-id="5a1c8-106">Parameters</span></span>

 <span data-ttu-id="5a1c8-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="5a1c8-107">_ulFlags_</span></span>
  
> <span data-ttu-id="5a1c8-108">实时标志的位掩码, 用于控制如何返回_ppResults_参数中的属性数组。</span><span class="sxs-lookup"><span data-stu-id="5a1c8-108">[in] A bitmask of flags that controls how the property array in the  _ppResults_ parameter is returned.</span></span> <span data-ttu-id="5a1c8-109">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="5a1c8-109">The following flags can be set:</span></span> 
    
<span data-ttu-id="5a1c8-110">FORMPROPSET_INTERSECTION</span><span class="sxs-lookup"><span data-stu-id="5a1c8-110">FORMPROPSET_INTERSECTION</span></span> 
  
> <span data-ttu-id="5a1c8-111">返回的数组包含窗体属性的交集。</span><span class="sxs-lookup"><span data-stu-id="5a1c8-111">The returned array contains the intersection of the forms' properties.</span></span>
    
<span data-ttu-id="5a1c8-112">FORMPROPSET_UNION</span><span class="sxs-lookup"><span data-stu-id="5a1c8-112">FORMPROPSET_UNION</span></span> 
  
> <span data-ttu-id="5a1c8-113">返回的数组包含表单属性的联合。</span><span class="sxs-lookup"><span data-stu-id="5a1c8-113">The returned array contains the union of the forms' properties.</span></span>
    
<span data-ttu-id="5a1c8-114">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="5a1c8-114">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="5a1c8-115">数组中返回的字符串采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="5a1c8-115">The strings returned in the array are in Unicode format.</span></span> <span data-ttu-id="5a1c8-116">如果未设置 MAPI_UNICODE 标志, 则字符串将采用 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="5a1c8-116">If the MAPI_UNICODE flag is not set, the strings are in ANSI format.</span></span>
    
 <span data-ttu-id="5a1c8-117">_ppResults_</span><span class="sxs-lookup"><span data-stu-id="5a1c8-117">_ppResults_</span></span>
  
> <span data-ttu-id="5a1c8-118">排除指向返回的[SMAPIFormPropArray](smapiformproparray.md)结构的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="5a1c8-118">[out] A pointer to a pointer to the returned [SMAPIFormPropArray](smapiformproparray.md) structure.</span></span> <span data-ttu-id="5a1c8-119">此结构包含已安装的表单所使用的所有属性。</span><span class="sxs-lookup"><span data-stu-id="5a1c8-119">This structure contains all properties used by the installed forms.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="5a1c8-120">返回值</span><span class="sxs-lookup"><span data-stu-id="5a1c8-120">Return value</span></span>

<span data-ttu-id="5a1c8-121">S_OK</span><span class="sxs-lookup"><span data-stu-id="5a1c8-121">S_OK</span></span> 
  
> <span data-ttu-id="5a1c8-122">调用成功, 并返回了所需的值或值。</span><span class="sxs-lookup"><span data-stu-id="5a1c8-122">The call succeeded and has returned the expected value or values.</span></span>
    
<span data-ttu-id="5a1c8-123">MAPI_E_BAD_CHARWIDTH</span><span class="sxs-lookup"><span data-stu-id="5a1c8-123">MAPI_E_BAD_CHARWIDTH</span></span> 
  
> <span data-ttu-id="5a1c8-124">设置了 MAPI_UNICODE 标志, 且实现不支持 unicode, 或者未设置 MAPI_UNICODE, 且实现仅支持 UNICODE。</span><span class="sxs-lookup"><span data-stu-id="5a1c8-124">Either the MAPI_UNICODE flag was set and the implementation does not support Unicode, or MAPI_UNICODE was not set and the implementation supports only Unicode.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="5a1c8-125">注解</span><span class="sxs-lookup"><span data-stu-id="5a1c8-125">Remarks</span></span>

<span data-ttu-id="5a1c8-126">客户端应用程序调用**IMAPIFormContainer:: CalcFormPropSet**方法以获取在表单容器中安装的所有表单使用的属性数组。</span><span class="sxs-lookup"><span data-stu-id="5a1c8-126">Client applications call the **IMAPIFormContainer::CalcFormPropSet** method to obtain an array of properties used by all forms installed in a form container.</span></span> <span data-ttu-id="5a1c8-127">**IMAPIFormContainer:: CalcFormPropSet**的工作方式与[IMAPIFormMgr:: CalcFormPropSet](imapiformmgr-calcformpropset.md)方法相同, 不同之处在于它在特定容器中注册的每个窗体上运行。</span><span class="sxs-lookup"><span data-stu-id="5a1c8-127">**IMAPIFormContainer::CalcFormPropSet** works like the [IMAPIFormMgr::CalcFormPropSet](imapiformmgr-calcformpropset.md) method, except that it operates on every form registered in a particular container.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="5a1c8-128">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="5a1c8-128">Notes to implementers</span></span>

<span data-ttu-id="5a1c8-129">如果 MAPI_UNICODE 已传递, 则不支持 Unicode 字符串的表单库提供程序应返回 MAPI_E_BAD_CHARWIDTH。</span><span class="sxs-lookup"><span data-stu-id="5a1c8-129">Form library providers that do not support Unicode strings should return MAPI_E_BAD_CHARWIDTH if MAPI_UNICODE is passed.</span></span>
  
## <a name="notes-to-callers"></a><span data-ttu-id="5a1c8-130">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="5a1c8-130">Notes to callers</span></span>

 <span data-ttu-id="5a1c8-131">**IMAPIFormContainer:: CalcFormPropSet**采用交集或 union of forms 属性集, 具体取决于_ulFlags_参数中设置的标志, 并且它将返回一个**SMAPIFormPropArray**结构, 其中包含生成的属性组。</span><span class="sxs-lookup"><span data-stu-id="5a1c8-131">**IMAPIFormContainer::CalcFormPropSet** takes either an intersection or a union of the forms' property sets, depending on the flag set in the  _ulFlags_ parameter, and it returns an **SMAPIFormPropArray** structure that contains the resulting group of properties.</span></span> 
  
<span data-ttu-id="5a1c8-132">如果客户端在_ulFlags_中传递了 MAPI_UNICODE 标志, 则所有返回的字符串都是 UNICODE。</span><span class="sxs-lookup"><span data-stu-id="5a1c8-132">If a client passes the MAPI_UNICODE flag in  _ulFlags_, all returned strings are Unicode.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="5a1c8-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5a1c8-133">See also</span></span>



[<span data-ttu-id="5a1c8-134">IMAPIFormMgr::CalcFormPropSet</span><span class="sxs-lookup"><span data-stu-id="5a1c8-134">IMAPIFormMgr::CalcFormPropSet</span></span>](imapiformmgr-calcformpropset.md)
  
[<span data-ttu-id="5a1c8-135">SMAPIFormPropArray</span><span class="sxs-lookup"><span data-stu-id="5a1c8-135">SMAPIFormPropArray</span></span>](smapiformproparray.md)
  
[<span data-ttu-id="5a1c8-136">IMAPIFormContainer : IUnknown</span><span class="sxs-lookup"><span data-stu-id="5a1c8-136">IMAPIFormContainer : IUnknown</span></span>](imapiformcontaineriunknown.md)

