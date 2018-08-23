---
title: IMAPIFormInfoCalcFormPropSet
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIFormInfo.CalcFormPropSet
api_type:
- COM
ms.assetid: cc3ffb8d-9cc4-47d3-9aa9-02c3a5b7775c
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 7d0c044caf430c944d8912d050e4dbaba659c8b5
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22582495"
---
# <a name="imapiforminfocalcformpropset"></a><span data-ttu-id="9abd6-103">IMAPIFormInfo::CalcFormPropSet</span><span class="sxs-lookup"><span data-stu-id="9abd6-103">IMAPIFormInfo::CalcFormPropSet</span></span>

  
  
<span data-ttu-id="9abd6-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="9abd6-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="9abd6-105">向窗体使用的属性的完整集合中返回的指针。</span><span class="sxs-lookup"><span data-stu-id="9abd6-105">Returns a pointer to the complete set of properties that a form uses.</span></span>
  
```cpp
HRESULT CalcFormPropSet(
  ULONG ulFlags,
  LPMAPIFORMPROPARRAY FAR * ppFormPropArray
);
```

## <a name="parameters"></a><span data-ttu-id="9abd6-106">参数</span><span class="sxs-lookup"><span data-stu-id="9abd6-106">Parameters</span></span>

 <span data-ttu-id="9abd6-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="9abd6-107">_ulFlags_</span></span>
  
> <span data-ttu-id="9abd6-108">[in]返回控制的字符串类型的标志位掩码。</span><span class="sxs-lookup"><span data-stu-id="9abd6-108">[in] A bitmask of flags that controls the type of strings returned.</span></span> <span data-ttu-id="9abd6-109">可以设置以下标记：</span><span class="sxs-lookup"><span data-stu-id="9abd6-109">The following flag can be set:</span></span>
    
<span data-ttu-id="9abd6-110">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="9abd6-110">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="9abd6-111">返回的字符串采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="9abd6-111">The returned strings are in Unicode format.</span></span> <span data-ttu-id="9abd6-112">如果未设置 MAPI_UNICODE 标志的字符串是以 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="9abd6-112">If the MAPI_UNICODE flag is not set, the strings are in ANSI format.</span></span>
    
 <span data-ttu-id="9abd6-113">_ppFormPropArray_</span><span class="sxs-lookup"><span data-stu-id="9abd6-113">_ppFormPropArray_</span></span>
  
> <span data-ttu-id="9abd6-114">[输出]指向返回[SMAPIFormPropArray](smapiformproparray.md)结构的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="9abd6-114">[out] A pointer to a pointer to the returned [SMAPIFormPropArray](smapiformproparray.md) structure.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="9abd6-115">返回值</span><span class="sxs-lookup"><span data-stu-id="9abd6-115">Return value</span></span>

<span data-ttu-id="9abd6-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="9abd6-116">S_OK</span></span> 
  
> <span data-ttu-id="9abd6-117">呼叫成功或多个预期值返回。</span><span class="sxs-lookup"><span data-stu-id="9abd6-117">The call succeeded and has returned the expected value or values.</span></span>
    
<span data-ttu-id="9abd6-118">MAPI_E_BAD_CHARWIDTH</span><span class="sxs-lookup"><span data-stu-id="9abd6-118">MAPI_E_BAD_CHARWIDTH</span></span> 
  
> <span data-ttu-id="9abd6-119">既设置了 MAPI_UNICODE 标志实现不支持 Unicode，或未设置 MAPI_UNICODE 并实现支持仅 Unicode。</span><span class="sxs-lookup"><span data-stu-id="9abd6-119">Either the MAPI_UNICODE flag was set and the implementation does not support Unicode, or MAPI_UNICODE was not set and the implementation supports only Unicode.</span></span>
    
## <a name="mfcmapi-reference"></a><span data-ttu-id="9abd6-120">MFCMAPI 参考 （英文）</span><span class="sxs-lookup"><span data-stu-id="9abd6-120">MFCMAPI reference</span></span>

<span data-ttu-id="9abd6-121">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="9abd6-121">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="9abd6-122">**文件**</span><span class="sxs-lookup"><span data-stu-id="9abd6-122">**File**</span></span>|<span data-ttu-id="9abd6-123">**函数**</span><span class="sxs-lookup"><span data-stu-id="9abd6-123">**Function**</span></span>|<span data-ttu-id="9abd6-124">**Comment**</span><span class="sxs-lookup"><span data-stu-id="9abd6-124">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="9abd6-125">MFCOutput.cpp</span><span class="sxs-lookup"><span data-stu-id="9abd6-125">MFCOutput.cpp</span></span>  <br/> |<span data-ttu-id="9abd6-126">_OutputFormInfo</span><span class="sxs-lookup"><span data-stu-id="9abd6-126">_OutputFormInfo</span></span>  <br/> |<span data-ttu-id="9abd6-127">MFCMAPI 使用**IMAPIFormInfo::CalcFormPropSet**方法时编写窗体信息对象的调试输出。</span><span class="sxs-lookup"><span data-stu-id="9abd6-127">MFCMAPI uses the **IMAPIFormInfo::CalcFormPropSet** method when writing debug output for form information objects.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="9abd6-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9abd6-128">See also</span></span>



[<span data-ttu-id="9abd6-129">SMAPIFormPropArray</span><span class="sxs-lookup"><span data-stu-id="9abd6-129">SMAPIFormPropArray</span></span>](smapiformproparray.md)
  
[<span data-ttu-id="9abd6-130">IMAPIFormInfo : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="9abd6-130">IMAPIFormInfo : IMAPIProp</span></span>](imapiforminfoimapiprop.md)


[<span data-ttu-id="9abd6-131">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="9abd6-131">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

