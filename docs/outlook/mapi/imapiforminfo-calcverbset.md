---
title: IMAPIFormInfoCalcVerbSet
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIFormInfo.CalcVerbSet
api_type:
- COM
ms.assetid: 0170dc9d-dc72-48e2-a522-374f199b18ea
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: babff746af16d51ca154d049943f6be7e9fab589
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33428779"
---
# <a name="imapiforminfocalcverbset"></a><span data-ttu-id="cbf75-103">IMAPIFormInfo::CalcVerbSet</span><span class="sxs-lookup"><span data-stu-id="cbf75-103">IMAPIFormInfo::CalcVerbSet</span></span>

  
  
<span data-ttu-id="cbf75-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="cbf75-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="cbf75-105">返回一个指针，该指针指向窗体使用的完整动作集。</span><span class="sxs-lookup"><span data-stu-id="cbf75-105">Returns a pointer to the complete set of verbs that a form uses.</span></span>
  
```cpp
HRESULT CalcVerbSet(
  ULONG ulFlags,
  LPMAPIVERBARRAY FAR * ppMAPIVerbArray
);
```

## <a name="parameters"></a><span data-ttu-id="cbf75-106">参数</span><span class="sxs-lookup"><span data-stu-id="cbf75-106">Parameters</span></span>

 <span data-ttu-id="cbf75-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="cbf75-107">_ulFlags_</span></span>
  
> <span data-ttu-id="cbf75-108">[in]控制返回的字符串类型的标志位掩码。</span><span class="sxs-lookup"><span data-stu-id="cbf75-108">[in] A bitmask of flags that controls the type of strings returned.</span></span> <span data-ttu-id="cbf75-109">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="cbf75-109">The following flag can be set:</span></span>
    
<span data-ttu-id="cbf75-110">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="cbf75-110">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="cbf75-111">返回的字符串采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="cbf75-111">The returned strings are in Unicode format.</span></span> <span data-ttu-id="cbf75-112">如果未MAPI_UNICODE，则字符串采用 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="cbf75-112">If the MAPI_UNICODE flag is not set, the strings are in ANSI format.</span></span>
    
 <span data-ttu-id="cbf75-113">_ppMAPIVerbArray_</span><span class="sxs-lookup"><span data-stu-id="cbf75-113">_ppMAPIVerbArray_</span></span>
  
> <span data-ttu-id="cbf75-114">[out]指向返回的 [SMAPIVerbArray](smapiverbarray.md) 结构的指针的指针，该结构包含表单的谓词。</span><span class="sxs-lookup"><span data-stu-id="cbf75-114">[out] A pointer to a pointer to the returned [SMAPIVerbArray](smapiverbarray.md) structure that contains the form's verbs.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="cbf75-115">返回值</span><span class="sxs-lookup"><span data-stu-id="cbf75-115">Return value</span></span>

<span data-ttu-id="cbf75-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="cbf75-116">S_OK</span></span> 
  
> <span data-ttu-id="cbf75-117">调用成功并返回了预期值。</span><span class="sxs-lookup"><span data-stu-id="cbf75-117">The call succeeded and has returned the expected value or values.</span></span>
    
<span data-ttu-id="cbf75-118">MAPI_E_BAD_CHARWIDTH</span><span class="sxs-lookup"><span data-stu-id="cbf75-118">MAPI_E_BAD_CHARWIDTH</span></span> 
  
> <span data-ttu-id="cbf75-119">设置 MAPI_UNICODE 标志，而实现不支持 Unicode，或者MAPI_UNICODE未设置，并且实现仅支持 Unicode。</span><span class="sxs-lookup"><span data-stu-id="cbf75-119">Either the MAPI_UNICODE flag was set and the implementation does not support Unicode, or MAPI_UNICODE was not set and the implementation supports only Unicode.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="cbf75-120">备注</span><span class="sxs-lookup"><span data-stu-id="cbf75-120">Remarks</span></span>

<span data-ttu-id="cbf75-121">客户端应用程序调用 **IMAPIFormInfo：：CalcVerbSet** 方法以获取指向表单使用的一组动词的指针。</span><span class="sxs-lookup"><span data-stu-id="cbf75-121">Client applications call the **IMAPIFormInfo::CalcVerbSet** method to obtain a pointer to the set of verbs used by a form.</span></span> <span data-ttu-id="cbf75-122">在 _ppMAPIVerbArray_ 参数返回的 **SMAPIVerbArray** 结构中，动词按索引号顺序返回;每个动词的索引位于其 **lVerb** 成员中。</span><span class="sxs-lookup"><span data-stu-id="cbf75-122">In the **SMAPIVerbArray** structure returned in the  _ppMAPIVerbArray_ parameter, the verbs are returned in order of index number; each verb's index is found in its **lVerb** member.</span></span> <span data-ttu-id="cbf75-123">客户端应用程序可以使用动词数组动态生成菜单、隐藏或显示按钮等。</span><span class="sxs-lookup"><span data-stu-id="cbf75-123">Client applications can use the verb array to dynamically build menus, hide or show buttons, and so on.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="cbf75-124">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="cbf75-124">MFCMAPI reference</span></span>

<span data-ttu-id="cbf75-125">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="cbf75-125">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="cbf75-126">**文件**</span><span class="sxs-lookup"><span data-stu-id="cbf75-126">**File**</span></span>|<span data-ttu-id="cbf75-127">**函数**</span><span class="sxs-lookup"><span data-stu-id="cbf75-127">**Function**</span></span>|<span data-ttu-id="cbf75-128">**备注**</span><span class="sxs-lookup"><span data-stu-id="cbf75-128">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="cbf75-129">MFCOutput.cpp</span><span class="sxs-lookup"><span data-stu-id="cbf75-129">MFCOutput.cpp</span></span>  <br/> |<span data-ttu-id="cbf75-130">_OutputFormInfo</span><span class="sxs-lookup"><span data-stu-id="cbf75-130">_OutputFormInfo</span></span>  <br/> |<span data-ttu-id="cbf75-131">MFCMAPI 在编写表单信息对象的调试输出时，使用 **IMAPIFormInfo：：CalcVerbSet** 方法。</span><span class="sxs-lookup"><span data-stu-id="cbf75-131">MFCMAPI uses the **IMAPIFormInfo::CalcVerbSet** method while writing debug output for form information objects.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="cbf75-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cbf75-132">See also</span></span>



[<span data-ttu-id="cbf75-133">SMAPIVerbArray</span><span class="sxs-lookup"><span data-stu-id="cbf75-133">SMAPIVerbArray</span></span>](smapiverbarray.md)
  
[<span data-ttu-id="cbf75-134">IMAPIFormInfo : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="cbf75-134">IMAPIFormInfo : IMAPIProp</span></span>](imapiforminfoimapiprop.md)


[<span data-ttu-id="cbf75-135">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="cbf75-135">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

