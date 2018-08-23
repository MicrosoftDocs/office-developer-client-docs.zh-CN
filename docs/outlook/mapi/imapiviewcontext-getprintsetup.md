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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 63e3eca4e91e560a28d57f05250264d7e0592142
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22587255"
---
# <a name="imapiviewcontextgetprintsetup"></a><span data-ttu-id="0055a-103">IMAPIViewContext::GetPrintSetup</span><span class="sxs-lookup"><span data-stu-id="0055a-103">IMAPIViewContext::GetPrintSetup</span></span>

  
  
<span data-ttu-id="0055a-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="0055a-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="0055a-105">检索当前打印的信息。</span><span class="sxs-lookup"><span data-stu-id="0055a-105">Retrieves current printing information.</span></span>
  
```cpp
HRESULT GetPrintSetup(
ULONG ulFlags,
LPFORMPRINTSETUP FAR * lppFormPrintSetup
);
```

## <a name="parameters"></a><span data-ttu-id="0055a-106">参数</span><span class="sxs-lookup"><span data-stu-id="0055a-106">Parameters</span></span>

 <span data-ttu-id="0055a-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="0055a-107">_ulFlags_</span></span>
  
> <span data-ttu-id="0055a-108">[in]位掩码的标志，控制返回的字符串的类型。</span><span class="sxs-lookup"><span data-stu-id="0055a-108">[in] Bitmask of flags that controls the type of the returned strings.</span></span> <span data-ttu-id="0055a-109">可以设置以下标记：</span><span class="sxs-lookup"><span data-stu-id="0055a-109">The following flag can be set:</span></span>
    
<span data-ttu-id="0055a-110">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="0055a-110">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="0055a-111">返回的字符串采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="0055a-111">The returned strings are in Unicode format.</span></span> <span data-ttu-id="0055a-112">如果未设置 MAPI_UNICODE 标志的字符串是以 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="0055a-112">If the MAPI_UNICODE flag is not set, the strings are in ANSI format.</span></span>
    
 <span data-ttu-id="0055a-113">_lppFormPrintSetup_</span><span class="sxs-lookup"><span data-stu-id="0055a-113">_lppFormPrintSetup_</span></span>
  
> <span data-ttu-id="0055a-114">[输出]一个包含打印信息结构为指针的指针。</span><span class="sxs-lookup"><span data-stu-id="0055a-114">[out] Pointer to a pointer to a structure that holds the printing information.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="0055a-115">返回值</span><span class="sxs-lookup"><span data-stu-id="0055a-115">Return value</span></span>

<span data-ttu-id="0055a-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="0055a-116">S_OK</span></span> 
  
> <span data-ttu-id="0055a-117">已成功检索打印的信息。</span><span class="sxs-lookup"><span data-stu-id="0055a-117">The printing information was successfully retrieved.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="0055a-118">注解</span><span class="sxs-lookup"><span data-stu-id="0055a-118">Remarks</span></span>

<span data-ttu-id="0055a-119">表单对象调用**IMAPIViewContext::GetPrintSetup**方法检索有关的打印机设置打印当前消息在尝试之前的信息。</span><span class="sxs-lookup"><span data-stu-id="0055a-119">Form objects call the **IMAPIViewContext::GetPrintSetup** method to retrieve information about the printer setup before attempting to print the current message.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="0055a-120">针对实施者的注释</span><span class="sxs-lookup"><span data-stu-id="0055a-120">Notes to implementers</span></span>

<span data-ttu-id="0055a-121">分配**hDevMode**和**hDevName**使用 Win32 函数**GlobalAlloc** [FORMPRINTSETUP](formprintsetup.md)结构的成员。</span><span class="sxs-lookup"><span data-stu-id="0055a-121">Allocate the **hDevMode** and **hDevName** members of the [FORMPRINTSETUP](formprintsetup.md) structure using the Win32 function **GlobalAlloc**.</span></span>
  
## <a name="notes-to-callers"></a><span data-ttu-id="0055a-122">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="0055a-122">Notes to callers</span></span>

<span data-ttu-id="0055a-123">如果您希望**hDevMode** **FORMPRINTSETUP**结构的**hDevName**成员所指的_lppFormPrintSetup_参数设置为 Unicode 字符串，设置为 MAPI_UNICODE _ulFlags_ 。</span><span class="sxs-lookup"><span data-stu-id="0055a-123">If you expect the **hDevMode** and **hDevName** members of the **FORMPRINTSETUP** structure pointed to by the  _lppFormPrintSetup_ parameter to be Unicode strings, set  _ulFlags_ to MAPI_UNICODE.</span></span> <span data-ttu-id="0055a-124">否则， **GetPrintSetup**将以 ANSI 格式返回这些字符串。</span><span class="sxs-lookup"><span data-stu-id="0055a-124">Otherwise, **GetPrintSetup** will return these strings in ANSI format.</span></span> 
  
<span data-ttu-id="0055a-125">通过调用 Win32 函数**GlobalFree**释放**hDevMode**和**hDevName** **FORMPRINTSETUP**结构的成员。</span><span class="sxs-lookup"><span data-stu-id="0055a-125">Free the **hDevMode** and **hDevName** members of the **FORMPRINTSETUP** structure by calling the Win32 function **GlobalFree**.</span></span> <span data-ttu-id="0055a-126">通过调用[MAPIFreeBuffer](mapifreebuffer.md)释放整个**FORMPRINTSETUP**结构。</span><span class="sxs-lookup"><span data-stu-id="0055a-126">Free the entire **FORMPRINTSETUP** structure by calling [MAPIFreeBuffer](mapifreebuffer.md).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="0055a-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0055a-127">See also</span></span>



[<span data-ttu-id="0055a-128">FORMPRINTSETUP</span><span class="sxs-lookup"><span data-stu-id="0055a-128">FORMPRINTSETUP</span></span>](formprintsetup.md)
  
[<span data-ttu-id="0055a-129">IMAPIViewContext : IUnknown</span><span class="sxs-lookup"><span data-stu-id="0055a-129">IMAPIViewContext : IUnknown</span></span>](imapiviewcontextiunknown.md)

