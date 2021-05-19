---
title: IMAPIViewContextGetPrintSetup
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIViewContext.GetPrintSetup
api_type:
- COM
ms.assetid: eaf3bafb-975d-42c8-99ea-7f9ef9c934ba
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: a58e723113f70c10b5c8468f5bdd0d8d9014bd2c
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33425125"
---
# <a name="imapiviewcontextgetprintsetup"></a><span data-ttu-id="296f7-103">IMAPIViewContext::GetPrintSetup</span><span class="sxs-lookup"><span data-stu-id="296f7-103">IMAPIViewContext::GetPrintSetup</span></span>

  
  
<span data-ttu-id="296f7-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="296f7-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="296f7-105">检索当前打印信息。</span><span class="sxs-lookup"><span data-stu-id="296f7-105">Retrieves current printing information.</span></span>
  
```cpp
HRESULT GetPrintSetup(
ULONG ulFlags,
LPFORMPRINTSETUP FAR * lppFormPrintSetup
);
```

## <a name="parameters"></a><span data-ttu-id="296f7-106">参数</span><span class="sxs-lookup"><span data-stu-id="296f7-106">Parameters</span></span>

 <span data-ttu-id="296f7-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="296f7-107">_ulFlags_</span></span>
  
> <span data-ttu-id="296f7-108">[in]控制返回的字符串类型的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="296f7-108">[in] Bitmask of flags that controls the type of the returned strings.</span></span> <span data-ttu-id="296f7-109">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="296f7-109">The following flag can be set:</span></span>
    
<span data-ttu-id="296f7-110">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="296f7-110">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="296f7-111">返回的字符串采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="296f7-111">The returned strings are in Unicode format.</span></span> <span data-ttu-id="296f7-112">如果未MAPI_UNICODE，则字符串采用 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="296f7-112">If the MAPI_UNICODE flag is not set, the strings are in ANSI format.</span></span>
    
 <span data-ttu-id="296f7-113">_lppFormPrintSetup_</span><span class="sxs-lookup"><span data-stu-id="296f7-113">_lppFormPrintSetup_</span></span>
  
> <span data-ttu-id="296f7-114">[out]指向指向包含打印信息的结构的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="296f7-114">[out] Pointer to a pointer to a structure that holds the printing information.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="296f7-115">返回值</span><span class="sxs-lookup"><span data-stu-id="296f7-115">Return value</span></span>

<span data-ttu-id="296f7-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="296f7-116">S_OK</span></span> 
  
> <span data-ttu-id="296f7-117">已成功检索打印信息。</span><span class="sxs-lookup"><span data-stu-id="296f7-117">The printing information was successfully retrieved.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="296f7-118">备注</span><span class="sxs-lookup"><span data-stu-id="296f7-118">Remarks</span></span>

<span data-ttu-id="296f7-119">Form 对象调用 **IMAPIViewContext：：GetPrintSetup** 方法，以在尝试打印当前邮件之前检索有关打印机设置的信息。</span><span class="sxs-lookup"><span data-stu-id="296f7-119">Form objects call the **IMAPIViewContext::GetPrintSetup** method to retrieve information about the printer setup before attempting to print the current message.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="296f7-120">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="296f7-120">Notes to implementers</span></span>

<span data-ttu-id="296f7-121">使用 Win32 函数 **GlobalAlloc** 分配 [FORMPRINTSETUP](formprintsetup.md)结构的 **hDevMode** 和 **hDevName** 成员。</span><span class="sxs-lookup"><span data-stu-id="296f7-121">Allocate the **hDevMode** and **hDevName** members of the [FORMPRINTSETUP](formprintsetup.md) structure using the Win32 function **GlobalAlloc**.</span></span>
  
## <a name="notes-to-callers"></a><span data-ttu-id="296f7-122">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="296f7-122">Notes to callers</span></span>

<span data-ttu-id="296f7-123">如果您希望 _lppFormPrintSetup_ 参数指向的 **FORMPRINTSETUP** 结构的 **hDevMode** 和 **hDevName** 成员为 Unicode 字符串，则将 _ulFlags_ 设置为 MAPI_UNICODE。</span><span class="sxs-lookup"><span data-stu-id="296f7-123">If you expect the **hDevMode** and **hDevName** members of the **FORMPRINTSETUP** structure pointed to by the  _lppFormPrintSetup_ parameter to be Unicode strings, set  _ulFlags_ to MAPI_UNICODE.</span></span> <span data-ttu-id="296f7-124">否则 **，GetPrintSetup** 将返回 ANSI 格式的这些字符串。</span><span class="sxs-lookup"><span data-stu-id="296f7-124">Otherwise, **GetPrintSetup** will return these strings in ANSI format.</span></span> 
  
<span data-ttu-id="296f7-125">通过调用 Win32 函数 **GlobalFree** 释放 **FORMPRINTSETUP** 结构的 **hDevMode** 和 **hDevName** 成员。</span><span class="sxs-lookup"><span data-stu-id="296f7-125">Free the **hDevMode** and **hDevName** members of the **FORMPRINTSETUP** structure by calling the Win32 function **GlobalFree**.</span></span> <span data-ttu-id="296f7-126">通过调用 [MAPIFreeBuffer](mapifreebuffer.md)释放整个 **FORMPRINTSETUP** 结构。</span><span class="sxs-lookup"><span data-stu-id="296f7-126">Free the entire **FORMPRINTSETUP** structure by calling [MAPIFreeBuffer](mapifreebuffer.md).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="296f7-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="296f7-127">See also</span></span>



[<span data-ttu-id="296f7-128">FORMPRINTSETUP</span><span class="sxs-lookup"><span data-stu-id="296f7-128">FORMPRINTSETUP</span></span>](formprintsetup.md)
  
[<span data-ttu-id="296f7-129">IMAPIViewContext : IUnknown</span><span class="sxs-lookup"><span data-stu-id="296f7-129">IMAPIViewContext : IUnknown</span></span>](imapiviewcontextiunknown.md)

