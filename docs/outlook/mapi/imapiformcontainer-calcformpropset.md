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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33414912"
---
# <a name="imapiformcontainercalcformpropset"></a><span data-ttu-id="aeffd-103">IMAPIFormContainer::CalcFormPropSet</span><span class="sxs-lookup"><span data-stu-id="aeffd-103">IMAPIFormContainer::CalcFormPropSet</span></span>

  
  
<span data-ttu-id="aeffd-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="aeffd-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="aeffd-105">返回由安装在表单容器中的所有表单使用的属性数组。</span><span class="sxs-lookup"><span data-stu-id="aeffd-105">Returns an array of the properties used by all forms installed in a form container.</span></span>
  
```cpp
HRESULT CalcFormPropSet(
  ULONG ulFlags,
  LPMAPIFORMPROPARRAY FAR * ppResults
);
```

## <a name="parameters"></a><span data-ttu-id="aeffd-106">参数</span><span class="sxs-lookup"><span data-stu-id="aeffd-106">Parameters</span></span>

 <span data-ttu-id="aeffd-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="aeffd-107">_ulFlags_</span></span>
  
> <span data-ttu-id="aeffd-108">[in]控制  _ppResults_ 参数中属性数组的返回方式的标志位掩码。</span><span class="sxs-lookup"><span data-stu-id="aeffd-108">[in] A bitmask of flags that controls how the property array in the  _ppResults_ parameter is returned.</span></span> <span data-ttu-id="aeffd-109">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="aeffd-109">The following flags can be set:</span></span> 
    
<span data-ttu-id="aeffd-110">FORMPROPSET_INTERSECTION</span><span class="sxs-lookup"><span data-stu-id="aeffd-110">FORMPROPSET_INTERSECTION</span></span> 
  
> <span data-ttu-id="aeffd-111">返回的数组包含窗体属性的交集。</span><span class="sxs-lookup"><span data-stu-id="aeffd-111">The returned array contains the intersection of the forms' properties.</span></span>
    
<span data-ttu-id="aeffd-112">FORMPROPSET_UNION</span><span class="sxs-lookup"><span data-stu-id="aeffd-112">FORMPROPSET_UNION</span></span> 
  
> <span data-ttu-id="aeffd-113">返回的数组包含窗体属性的并集。</span><span class="sxs-lookup"><span data-stu-id="aeffd-113">The returned array contains the union of the forms' properties.</span></span>
    
<span data-ttu-id="aeffd-114">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="aeffd-114">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="aeffd-115">数组中返回的字符串采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="aeffd-115">The strings returned in the array are in Unicode format.</span></span> <span data-ttu-id="aeffd-116">如果未MAPI_UNICODE，则字符串采用 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="aeffd-116">If the MAPI_UNICODE flag is not set, the strings are in ANSI format.</span></span>
    
 <span data-ttu-id="aeffd-117">_ppResults_</span><span class="sxs-lookup"><span data-stu-id="aeffd-117">_ppResults_</span></span>
  
> <span data-ttu-id="aeffd-118">[out]指向返回的 [SMAPIFormPropArray 结构的指针的](smapiformproparray.md) 指针。</span><span class="sxs-lookup"><span data-stu-id="aeffd-118">[out] A pointer to a pointer to the returned [SMAPIFormPropArray](smapiformproparray.md) structure.</span></span> <span data-ttu-id="aeffd-119">此结构包含已安装的表单使用的所有属性。</span><span class="sxs-lookup"><span data-stu-id="aeffd-119">This structure contains all properties used by the installed forms.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="aeffd-120">返回值</span><span class="sxs-lookup"><span data-stu-id="aeffd-120">Return value</span></span>

<span data-ttu-id="aeffd-121">S_OK</span><span class="sxs-lookup"><span data-stu-id="aeffd-121">S_OK</span></span> 
  
> <span data-ttu-id="aeffd-122">调用成功并返回了预期值。</span><span class="sxs-lookup"><span data-stu-id="aeffd-122">The call succeeded and has returned the expected value or values.</span></span>
    
<span data-ttu-id="aeffd-123">MAPI_E_BAD_CHARWIDTH</span><span class="sxs-lookup"><span data-stu-id="aeffd-123">MAPI_E_BAD_CHARWIDTH</span></span> 
  
> <span data-ttu-id="aeffd-124">设置 MAPI_UNICODE 标志，而实现不支持 Unicode，或者MAPI_UNICODE未设置，并且实现仅支持 Unicode。</span><span class="sxs-lookup"><span data-stu-id="aeffd-124">Either the MAPI_UNICODE flag was set and the implementation does not support Unicode, or MAPI_UNICODE was not set and the implementation supports only Unicode.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="aeffd-125">备注</span><span class="sxs-lookup"><span data-stu-id="aeffd-125">Remarks</span></span>

<span data-ttu-id="aeffd-126">客户端应用程序调用 **IMAPIFormContainer：：CalcFormPropSet** 方法以获取表单容器中安装的所有表单所使用的属性数组。</span><span class="sxs-lookup"><span data-stu-id="aeffd-126">Client applications call the **IMAPIFormContainer::CalcFormPropSet** method to obtain an array of properties used by all forms installed in a form container.</span></span> <span data-ttu-id="aeffd-127">**IMAPIFormContainer：：CalcFormPropSet** 的工作方式与 [IMAPIFormMgr：：CalcFormPropSet](imapiformmgr-calcformpropset.md) 方法类似，只不过它在特定容器中注册的所有表单上运行。</span><span class="sxs-lookup"><span data-stu-id="aeffd-127">**IMAPIFormContainer::CalcFormPropSet** works like the [IMAPIFormMgr::CalcFormPropSet](imapiformmgr-calcformpropset.md) method, except that it operates on every form registered in a particular container.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="aeffd-128">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="aeffd-128">Notes to implementers</span></span>

<span data-ttu-id="aeffd-129">如果传递了 Unicode 字符串，则不支持 Unicode MAPI_E_BAD_CHARWIDTH返回MAPI_UNICODE提供程序。</span><span class="sxs-lookup"><span data-stu-id="aeffd-129">Form library providers that do not support Unicode strings should return MAPI_E_BAD_CHARWIDTH if MAPI_UNICODE is passed.</span></span>
  
## <a name="notes-to-callers"></a><span data-ttu-id="aeffd-130">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="aeffd-130">Notes to callers</span></span>

 <span data-ttu-id="aeffd-131">**IMAPIFormContainer：：CalcFormPropSet** 采用表单属性集的交集或联合，具体取决于  _ulFlags_ 参数中设置的标志，并返回一个 **SMAPIFormPropArray** 结构，其中包含生成的属性组。</span><span class="sxs-lookup"><span data-stu-id="aeffd-131">**IMAPIFormContainer::CalcFormPropSet** takes either an intersection or a union of the forms' property sets, depending on the flag set in the  _ulFlags_ parameter, and it returns an **SMAPIFormPropArray** structure that contains the resulting group of properties.</span></span> 
  
<span data-ttu-id="aeffd-132">如果客户端在  _ulFlags_ 中传递 MAPI_UNICODE 标志，则返回的所有字符串都是 Unicode。</span><span class="sxs-lookup"><span data-stu-id="aeffd-132">If a client passes the MAPI_UNICODE flag in  _ulFlags_, all returned strings are Unicode.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="aeffd-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="aeffd-133">See also</span></span>



[<span data-ttu-id="aeffd-134">IMAPIFormMgr::CalcFormPropSet</span><span class="sxs-lookup"><span data-stu-id="aeffd-134">IMAPIFormMgr::CalcFormPropSet</span></span>](imapiformmgr-calcformpropset.md)
  
[<span data-ttu-id="aeffd-135">SMAPIFormPropArray</span><span class="sxs-lookup"><span data-stu-id="aeffd-135">SMAPIFormPropArray</span></span>](smapiformproparray.md)
  
[<span data-ttu-id="aeffd-136">IMAPIFormContainer : IUnknown</span><span class="sxs-lookup"><span data-stu-id="aeffd-136">IMAPIFormContainer : IUnknown</span></span>](imapiformcontaineriunknown.md)

