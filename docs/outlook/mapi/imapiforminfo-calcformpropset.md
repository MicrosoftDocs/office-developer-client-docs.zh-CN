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
ms.openlocfilehash: 0b62c21348da71c1ee863f70d6e6a549a5d10003
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33438069"
---
# <a name="imapiforminfocalcformpropset"></a><span data-ttu-id="fb52a-103">IMAPIFormInfo::CalcFormPropSet</span><span class="sxs-lookup"><span data-stu-id="fb52a-103">IMAPIFormInfo::CalcFormPropSet</span></span>

  
  
<span data-ttu-id="fb52a-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="fb52a-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="fb52a-105">返回一个指针, 该指针指向表单使用的完整属性集。</span><span class="sxs-lookup"><span data-stu-id="fb52a-105">Returns a pointer to the complete set of properties that a form uses.</span></span>
  
```cpp
HRESULT CalcFormPropSet(
  ULONG ulFlags,
  LPMAPIFORMPROPARRAY FAR * ppFormPropArray
);
```

## <a name="parameters"></a><span data-ttu-id="fb52a-106">参数</span><span class="sxs-lookup"><span data-stu-id="fb52a-106">Parameters</span></span>

 <span data-ttu-id="fb52a-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="fb52a-107">_ulFlags_</span></span>
  
> <span data-ttu-id="fb52a-108">实时用于控制返回的字符串类型的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="fb52a-108">[in] A bitmask of flags that controls the type of strings returned.</span></span> <span data-ttu-id="fb52a-109">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="fb52a-109">The following flag can be set:</span></span>
    
<span data-ttu-id="fb52a-110">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="fb52a-110">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="fb52a-111">返回的字符串采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="fb52a-111">The returned strings are in Unicode format.</span></span> <span data-ttu-id="fb52a-112">如果未设置 MAPI_UNICODE 标志, 则字符串将采用 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="fb52a-112">If the MAPI_UNICODE flag is not set, the strings are in ANSI format.</span></span>
    
 <span data-ttu-id="fb52a-113">_ppFormPropArray_</span><span class="sxs-lookup"><span data-stu-id="fb52a-113">_ppFormPropArray_</span></span>
  
> <span data-ttu-id="fb52a-114">排除指向返回的[SMAPIFormPropArray](smapiformproparray.md)结构的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="fb52a-114">[out] A pointer to a pointer to the returned [SMAPIFormPropArray](smapiformproparray.md) structure.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="fb52a-115">返回值</span><span class="sxs-lookup"><span data-stu-id="fb52a-115">Return value</span></span>

<span data-ttu-id="fb52a-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="fb52a-116">S_OK</span></span> 
  
> <span data-ttu-id="fb52a-117">调用成功, 并返回了所需的值或值。</span><span class="sxs-lookup"><span data-stu-id="fb52a-117">The call succeeded and has returned the expected value or values.</span></span>
    
<span data-ttu-id="fb52a-118">MAPI_E_BAD_CHARWIDTH</span><span class="sxs-lookup"><span data-stu-id="fb52a-118">MAPI_E_BAD_CHARWIDTH</span></span> 
  
> <span data-ttu-id="fb52a-119">设置了 MAPI_UNICODE 标志, 且实现不支持 unicode, 或者未设置 MAPI_UNICODE, 且实现仅支持 UNICODE。</span><span class="sxs-lookup"><span data-stu-id="fb52a-119">Either the MAPI_UNICODE flag was set and the implementation does not support Unicode, or MAPI_UNICODE was not set and the implementation supports only Unicode.</span></span>
    
## <a name="mfcmapi-reference"></a><span data-ttu-id="fb52a-120">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="fb52a-120">MFCMAPI reference</span></span>

<span data-ttu-id="fb52a-121">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="fb52a-121">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="fb52a-122">**文件**</span><span class="sxs-lookup"><span data-stu-id="fb52a-122">**File**</span></span>|<span data-ttu-id="fb52a-123">**函数**</span><span class="sxs-lookup"><span data-stu-id="fb52a-123">**Function**</span></span>|<span data-ttu-id="fb52a-124">**备注**</span><span class="sxs-lookup"><span data-stu-id="fb52a-124">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="fb52a-125">MFCOutput</span><span class="sxs-lookup"><span data-stu-id="fb52a-125">MFCOutput.cpp</span></span>  <br/> |<span data-ttu-id="fb52a-126">_OutputFormInfo</span><span class="sxs-lookup"><span data-stu-id="fb52a-126">_OutputFormInfo</span></span>  <br/> |<span data-ttu-id="fb52a-127">在为表单信息对象编写调试输出时, MFCMAPI 使用**IMAPIFormInfo:: CalcFormPropSet**方法。</span><span class="sxs-lookup"><span data-stu-id="fb52a-127">MFCMAPI uses the **IMAPIFormInfo::CalcFormPropSet** method when writing debug output for form information objects.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="fb52a-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fb52a-128">See also</span></span>



[<span data-ttu-id="fb52a-129">SMAPIFormPropArray</span><span class="sxs-lookup"><span data-stu-id="fb52a-129">SMAPIFormPropArray</span></span>](smapiformproparray.md)
  
[<span data-ttu-id="fb52a-130">IMAPIFormInfo : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="fb52a-130">IMAPIFormInfo : IMAPIProp</span></span>](imapiforminfoimapiprop.md)


[<span data-ttu-id="fb52a-131">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="fb52a-131">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

