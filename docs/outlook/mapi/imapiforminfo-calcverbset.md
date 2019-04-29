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
# <a name="imapiforminfocalcverbset"></a><span data-ttu-id="a90d5-103">IMAPIFormInfo::CalcVerbSet</span><span class="sxs-lookup"><span data-stu-id="a90d5-103">IMAPIFormInfo::CalcVerbSet</span></span>

  
  
<span data-ttu-id="a90d5-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="a90d5-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="a90d5-105">返回一个指针, 指向表单使用的完整的一组谓词。</span><span class="sxs-lookup"><span data-stu-id="a90d5-105">Returns a pointer to the complete set of verbs that a form uses.</span></span>
  
```cpp
HRESULT CalcVerbSet(
  ULONG ulFlags,
  LPMAPIVERBARRAY FAR * ppMAPIVerbArray
);
```

## <a name="parameters"></a><span data-ttu-id="a90d5-106">参数</span><span class="sxs-lookup"><span data-stu-id="a90d5-106">Parameters</span></span>

 <span data-ttu-id="a90d5-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="a90d5-107">_ulFlags_</span></span>
  
> <span data-ttu-id="a90d5-108">实时用于控制返回的字符串类型的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="a90d5-108">[in] A bitmask of flags that controls the type of strings returned.</span></span> <span data-ttu-id="a90d5-109">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="a90d5-109">The following flag can be set:</span></span>
    
<span data-ttu-id="a90d5-110">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="a90d5-110">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="a90d5-111">返回的字符串采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="a90d5-111">The returned strings are in Unicode format.</span></span> <span data-ttu-id="a90d5-112">如果未设置 MAPI_UNICODE 标志, 则字符串将采用 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="a90d5-112">If the MAPI_UNICODE flag is not set, the strings are in ANSI format.</span></span>
    
 <span data-ttu-id="a90d5-113">_ppMAPIVerbArray_</span><span class="sxs-lookup"><span data-stu-id="a90d5-113">_ppMAPIVerbArray_</span></span>
  
> <span data-ttu-id="a90d5-114">排除指向指向包含表单的谓词的返回[SMAPIVerbArray](smapiverbarray.md)结构的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="a90d5-114">[out] A pointer to a pointer to the returned [SMAPIVerbArray](smapiverbarray.md) structure that contains the form's verbs.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="a90d5-115">返回值</span><span class="sxs-lookup"><span data-stu-id="a90d5-115">Return value</span></span>

<span data-ttu-id="a90d5-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="a90d5-116">S_OK</span></span> 
  
> <span data-ttu-id="a90d5-117">调用成功, 并返回了所需的值或值。</span><span class="sxs-lookup"><span data-stu-id="a90d5-117">The call succeeded and has returned the expected value or values.</span></span>
    
<span data-ttu-id="a90d5-118">MAPI_E_BAD_CHARWIDTH</span><span class="sxs-lookup"><span data-stu-id="a90d5-118">MAPI_E_BAD_CHARWIDTH</span></span> 
  
> <span data-ttu-id="a90d5-119">设置了 MAPI_UNICODE 标志, 且实现不支持 unicode, 或者未设置 MAPI_UNICODE, 且实现仅支持 UNICODE。</span><span class="sxs-lookup"><span data-stu-id="a90d5-119">Either the MAPI_UNICODE flag was set and the implementation does not support Unicode, or MAPI_UNICODE was not set and the implementation supports only Unicode.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="a90d5-120">说明</span><span class="sxs-lookup"><span data-stu-id="a90d5-120">Remarks</span></span>

<span data-ttu-id="a90d5-121">客户端应用程序调用**IMAPIFormInfo:: CalcVerbSet**方法以获取指向表单使用的一组谓词的指针。</span><span class="sxs-lookup"><span data-stu-id="a90d5-121">Client applications call the **IMAPIFormInfo::CalcVerbSet** method to obtain a pointer to the set of verbs used by a form.</span></span> <span data-ttu-id="a90d5-122">在_ppMAPIVerbArray_参数中返回的**SMAPIVerbArray**结构中, 按照索引号的顺序返回谓词;在其**lVerb**成员中找到每个动词的索引。</span><span class="sxs-lookup"><span data-stu-id="a90d5-122">In the **SMAPIVerbArray** structure returned in the  _ppMAPIVerbArray_ parameter, the verbs are returned in order of index number; each verb's index is found in its **lVerb** member.</span></span> <span data-ttu-id="a90d5-123">客户端应用程序可以使用谓词数组来动态构建菜单、隐藏或显示按钮, 等等。</span><span class="sxs-lookup"><span data-stu-id="a90d5-123">Client applications can use the verb array to dynamically build menus, hide or show buttons, and so on.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="a90d5-124">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="a90d5-124">MFCMAPI reference</span></span>

<span data-ttu-id="a90d5-125">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="a90d5-125">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="a90d5-126">**文件**</span><span class="sxs-lookup"><span data-stu-id="a90d5-126">**File**</span></span>|<span data-ttu-id="a90d5-127">**函数**</span><span class="sxs-lookup"><span data-stu-id="a90d5-127">**Function**</span></span>|<span data-ttu-id="a90d5-128">**备注**</span><span class="sxs-lookup"><span data-stu-id="a90d5-128">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a90d5-129">MFCOutput</span><span class="sxs-lookup"><span data-stu-id="a90d5-129">MFCOutput.cpp</span></span>  <br/> |<span data-ttu-id="a90d5-130">_OutputFormInfo</span><span class="sxs-lookup"><span data-stu-id="a90d5-130">_OutputFormInfo</span></span>  <br/> |<span data-ttu-id="a90d5-131">MFCMAPI 在为表单信息对象编写调试输出时使用**IMAPIFormInfo:: CalcVerbSet**方法。</span><span class="sxs-lookup"><span data-stu-id="a90d5-131">MFCMAPI uses the **IMAPIFormInfo::CalcVerbSet** method while writing debug output for form information objects.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="a90d5-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a90d5-132">See also</span></span>



[<span data-ttu-id="a90d5-133">SMAPIVerbArray</span><span class="sxs-lookup"><span data-stu-id="a90d5-133">SMAPIVerbArray</span></span>](smapiverbarray.md)
  
[<span data-ttu-id="a90d5-134">IMAPIFormInfo : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="a90d5-134">IMAPIFormInfo : IMAPIProp</span></span>](imapiforminfoimapiprop.md)


[<span data-ttu-id="a90d5-135">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="a90d5-135">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

