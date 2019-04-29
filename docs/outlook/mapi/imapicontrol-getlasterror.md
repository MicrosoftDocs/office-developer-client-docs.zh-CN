---
title: IMAPIControlGetLastError
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIControl.GetLastError
api_type:
- COM
ms.assetid: 83290b8e-fffc-41c8-a01e-578d130b65c5
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 10ac4e33b3f734ec2ce3205aa1897e0418cb563d
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33421149"
---
# <a name="imapicontrolgetlasterror"></a><span data-ttu-id="514f2-103">IMAPIControl::GetLastError</span><span class="sxs-lookup"><span data-stu-id="514f2-103">IMAPIControl::GetLastError</span></span>

  
  
<span data-ttu-id="514f2-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="514f2-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="514f2-105">返回一个[MAPIERROR](mapierror.md)结构, 该结构包含上一个按钮控件错误的相关信息。</span><span class="sxs-lookup"><span data-stu-id="514f2-105">Returns a [MAPIERROR](mapierror.md) structure that contains information about the previous button control error.</span></span> 
  
```cpp
HRESULT GetLastError(
  HRESULT hResult,
  ULONG ulFlags,
  LPMAPIERROR FAR * lppMAPIError
);
```

## <a name="parameters"></a><span data-ttu-id="514f2-106">参数</span><span class="sxs-lookup"><span data-stu-id="514f2-106">Parameters</span></span>

 <span data-ttu-id="514f2-107">_hResult_</span><span class="sxs-lookup"><span data-stu-id="514f2-107">_hResult_</span></span>
  
> <span data-ttu-id="514f2-108">实时在上一方法调用中生成的错误值的句柄。</span><span class="sxs-lookup"><span data-stu-id="514f2-108">[in] A handle to the error value generated in the previous method call.</span></span>
    
 <span data-ttu-id="514f2-109">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="514f2-109">_ulFlags_</span></span>
  
> <span data-ttu-id="514f2-110">实时标志的位掩码, 用于控制返回的字符串的类型。</span><span class="sxs-lookup"><span data-stu-id="514f2-110">[in] A bitmask of flags that controls the type of the strings returned.</span></span> <span data-ttu-id="514f2-111">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="514f2-111">The following flag can be set:</span></span>
    
<span data-ttu-id="514f2-112">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="514f2-112">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="514f2-113">在_lppMAPIError_参数中返回的**MAPIERROR**结构中的字符串采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="514f2-113">The strings in the **MAPIERROR** structure returned in the  _lppMAPIError_ parameter are in Unicode format.</span></span> <span data-ttu-id="514f2-114">如果未设置 MAPI_UNICODE 标志, 则字符串将采用 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="514f2-114">If the MAPI_UNICODE flag is not set, the strings are in ANSI format.</span></span> 
    
 <span data-ttu-id="514f2-115">_lppMAPIError_</span><span class="sxs-lookup"><span data-stu-id="514f2-115">_lppMAPIError_</span></span>
  
> <span data-ttu-id="514f2-116">排除指向包含错误的版本、组件和上下文信息的**MAPIERROR**结构的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="514f2-116">[out] A pointer to a pointer to a **MAPIERROR** structure that contains version, component, and context information for the error.</span></span> <span data-ttu-id="514f2-117">如果提供程序无法提供具有相应信息的**MAPIERROR**结构, 则可以将_lppMAPIError_参数设置为 NULL。</span><span class="sxs-lookup"><span data-stu-id="514f2-117">The  _lppMAPIError_ parameter can be set to NULL if the provider cannot supply a **MAPIERROR** structure with appropriate information.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="514f2-118">返回值</span><span class="sxs-lookup"><span data-stu-id="514f2-118">Return value</span></span>

<span data-ttu-id="514f2-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="514f2-119">S_OK</span></span> 
  
> <span data-ttu-id="514f2-120">调用成功, 并返回了所需的值或值。</span><span class="sxs-lookup"><span data-stu-id="514f2-120">The call succeeded and has returned the expected value or values.</span></span>
    
<span data-ttu-id="514f2-121">MAPI_E_BAD_CHARWIDTH</span><span class="sxs-lookup"><span data-stu-id="514f2-121">MAPI_E_BAD_CHARWIDTH</span></span> 
  
> <span data-ttu-id="514f2-122">设置了 MAPI_UNICODE 标志, 且实现不支持 unicode, 或者未设置 MAPI_UNICODE, 且实现仅支持 UNICODE。</span><span class="sxs-lookup"><span data-stu-id="514f2-122">Either the MAPI_UNICODE flag was set and the implementation does not support Unicode, or MAPI_UNICODE was not set and the implementation supports only Unicode.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="514f2-123">说明</span><span class="sxs-lookup"><span data-stu-id="514f2-123">Remarks</span></span>

<span data-ttu-id="514f2-124">服务提供程序实现**IMAPIControl:: GetLastError**方法, 以提供有关失败的上一个方法调用的信息。</span><span class="sxs-lookup"><span data-stu-id="514f2-124">Service providers implement the **IMAPIControl::GetLastError** method to supply information about a prior method call that failed.</span></span> <span data-ttu-id="514f2-125">MAPI 可以通过在消息或对话框中显示**MAPIERROR**结构中的数据, 为用户提供有关错误的详细信息。</span><span class="sxs-lookup"><span data-stu-id="514f2-125">MAPI can give users detailed information about the error by displaying the data from the **MAPIERROR** structure in a message or dialog box.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="514f2-126">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="514f2-126">Notes to implementers</span></span>

<span data-ttu-id="514f2-127">对于每个错误, 您无需将信息包含在**MAPIERROR**结构中。</span><span class="sxs-lookup"><span data-stu-id="514f2-127">You do not need to have information to include in the **MAPIERROR** structure for every error.</span></span> <span data-ttu-id="514f2-128">可能无法确定上一个错误是什么。</span><span class="sxs-lookup"><span data-stu-id="514f2-128">It may not be possible to determine what the previous error was.</span></span> <span data-ttu-id="514f2-129">如果您有信息, 请在**MAPIERROR**结构中返回 S_OK 和适当的数据。</span><span class="sxs-lookup"><span data-stu-id="514f2-129">If you have information, return S_OK and the appropriate data in the **MAPIERROR** structure.</span></span> <span data-ttu-id="514f2-130">如果没有可用的信息, 则返回 S_OK, 并将_lppMAPIError_参数的指针返回到 NULL。</span><span class="sxs-lookup"><span data-stu-id="514f2-130">If no information is available, return S_OK and a pointer to NULL for the  _lppMAPIError_ parameter.</span></span> 
  
<span data-ttu-id="514f2-131">有关**GetLastError**方法的详细信息, 请参阅[MAPI 扩展错误](mapi-extended-errors.md)。</span><span class="sxs-lookup"><span data-stu-id="514f2-131">For more information about the **GetLastError** method, see [MAPI Extended Errors](mapi-extended-errors.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="514f2-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="514f2-132">See also</span></span>



[<span data-ttu-id="514f2-133">MAPIERROR</span><span class="sxs-lookup"><span data-stu-id="514f2-133">MAPIERROR</span></span>](mapierror.md)
  
[<span data-ttu-id="514f2-134">MAPIFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="514f2-134">MAPIFreeBuffer</span></span>](mapifreebuffer.md)
  
[<span data-ttu-id="514f2-135">IMAPIControl : IUnknown</span><span class="sxs-lookup"><span data-stu-id="514f2-135">IMAPIControl : IUnknown</span></span>](imapicontroliunknown.md)

