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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: ef5fee7a2e84133f88a00703f7602831d26e3d3d
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22594724"
---
# <a name="imapicontrolgetlasterror"></a><span data-ttu-id="f7d9f-103">IMAPIControl::GetLastError</span><span class="sxs-lookup"><span data-stu-id="f7d9f-103">IMAPIControl::GetLastError</span></span>

  
  
<span data-ttu-id="f7d9f-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="f7d9f-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="f7d9f-105">返回一个[MAPIERROR](mapierror.md)结构，其中包含有关前一个按钮控件错误的信息。</span><span class="sxs-lookup"><span data-stu-id="f7d9f-105">Returns a [MAPIERROR](mapierror.md) structure that contains information about the previous button control error.</span></span> 
  
```cpp
HRESULT GetLastError(
  HRESULT hResult,
  ULONG ulFlags,
  LPMAPIERROR FAR * lppMAPIError
);
```

## <a name="parameters"></a><span data-ttu-id="f7d9f-106">参数</span><span class="sxs-lookup"><span data-stu-id="f7d9f-106">Parameters</span></span>

 <span data-ttu-id="f7d9f-107">_hResult_</span><span class="sxs-lookup"><span data-stu-id="f7d9f-107">_hResult_</span></span>
  
> <span data-ttu-id="f7d9f-108">[in]在以前的方法调用中生成的错误值句柄。</span><span class="sxs-lookup"><span data-stu-id="f7d9f-108">[in] A handle to the error value generated in the previous method call.</span></span>
    
 <span data-ttu-id="f7d9f-109">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="f7d9f-109">_ulFlags_</span></span>
  
> <span data-ttu-id="f7d9f-110">[in]返回控制的字符串类型的标志位掩码。</span><span class="sxs-lookup"><span data-stu-id="f7d9f-110">[in] A bitmask of flags that controls the type of the strings returned.</span></span> <span data-ttu-id="f7d9f-111">可以设置以下标记：</span><span class="sxs-lookup"><span data-stu-id="f7d9f-111">The following flag can be set:</span></span>
    
<span data-ttu-id="f7d9f-112">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="f7d9f-112">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="f7d9f-113">返回_lppMAPIError_参数中的**MAPIERROR**结构中的字符串采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="f7d9f-113">The strings in the **MAPIERROR** structure returned in the  _lppMAPIError_ parameter are in Unicode format.</span></span> <span data-ttu-id="f7d9f-114">如果未设置 MAPI_UNICODE 标志的字符串是以 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="f7d9f-114">If the MAPI_UNICODE flag is not set, the strings are in ANSI format.</span></span> 
    
 <span data-ttu-id="f7d9f-115">_lppMAPIError_</span><span class="sxs-lookup"><span data-stu-id="f7d9f-115">_lppMAPIError_</span></span>
  
> <span data-ttu-id="f7d9f-116">[输出]指向包含错误的版本、 组件及上下文信息**MAPIERROR**结构的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="f7d9f-116">[out] A pointer to a pointer to a **MAPIERROR** structure that contains version, component, and context information for the error.</span></span> <span data-ttu-id="f7d9f-117">_LppMAPIError_参数可以设置为 NULL，如果提供程序不能提供一个**MAPIERROR**相应的信息。</span><span class="sxs-lookup"><span data-stu-id="f7d9f-117">The  _lppMAPIError_ parameter can be set to NULL if the provider cannot supply a **MAPIERROR** structure with appropriate information.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="f7d9f-118">返回值</span><span class="sxs-lookup"><span data-stu-id="f7d9f-118">Return value</span></span>

<span data-ttu-id="f7d9f-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="f7d9f-119">S_OK</span></span> 
  
> <span data-ttu-id="f7d9f-120">呼叫成功或多个预期值返回。</span><span class="sxs-lookup"><span data-stu-id="f7d9f-120">The call succeeded and has returned the expected value or values.</span></span>
    
<span data-ttu-id="f7d9f-121">MAPI_E_BAD_CHARWIDTH</span><span class="sxs-lookup"><span data-stu-id="f7d9f-121">MAPI_E_BAD_CHARWIDTH</span></span> 
  
> <span data-ttu-id="f7d9f-122">既设置了 MAPI_UNICODE 标志实现不支持 Unicode，或未设置 MAPI_UNICODE 并实现支持仅 Unicode。</span><span class="sxs-lookup"><span data-stu-id="f7d9f-122">Either the MAPI_UNICODE flag was set and the implementation does not support Unicode, or MAPI_UNICODE was not set and the implementation supports only Unicode.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="f7d9f-123">注解</span><span class="sxs-lookup"><span data-stu-id="f7d9f-123">Remarks</span></span>

<span data-ttu-id="f7d9f-124">服务提供商实现**IMAPIControl::GetLastError**方法以提供有关失败的前一个方法调用的信息。</span><span class="sxs-lookup"><span data-stu-id="f7d9f-124">Service providers implement the **IMAPIControl::GetLastError** method to supply information about a prior method call that failed.</span></span> <span data-ttu-id="f7d9f-125">MAPI 可以通过在消息或对话框中显示的数据从**MAPIERROR**结构授予用户有关错误的详细的信息。</span><span class="sxs-lookup"><span data-stu-id="f7d9f-125">MAPI can give users detailed information about the error by displaying the data from the **MAPIERROR** structure in a message or dialog box.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="f7d9f-126">针对实施者的注释</span><span class="sxs-lookup"><span data-stu-id="f7d9f-126">Notes to implementers</span></span>

<span data-ttu-id="f7d9f-127">不需要在每个错误的**MAPIERROR**结构中包含的信息。</span><span class="sxs-lookup"><span data-stu-id="f7d9f-127">You do not need to have information to include in the **MAPIERROR** structure for every error.</span></span> <span data-ttu-id="f7d9f-128">它可能不确定前面的错误是什么。</span><span class="sxs-lookup"><span data-stu-id="f7d9f-128">It may not be possible to determine what the previous error was.</span></span> <span data-ttu-id="f7d9f-129">如果您有信息，则返回 S_OK 和适当的数据**MAPIERROR**结构中。</span><span class="sxs-lookup"><span data-stu-id="f7d9f-129">If you have information, return S_OK and the appropriate data in the **MAPIERROR** structure.</span></span> <span data-ttu-id="f7d9f-130">如果没有信息，则返回 S_OK 和指针为 NULL _lppMAPIError_参数。</span><span class="sxs-lookup"><span data-stu-id="f7d9f-130">If no information is available, return S_OK and a pointer to NULL for the  _lppMAPIError_ parameter.</span></span> 
  
<span data-ttu-id="f7d9f-131">有关**GetLastError**方法的详细信息，请参阅[MAPI 扩展错误](mapi-extended-errors.md)。</span><span class="sxs-lookup"><span data-stu-id="f7d9f-131">For more information about the **GetLastError** method, see [MAPI Extended Errors](mapi-extended-errors.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="f7d9f-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f7d9f-132">See also</span></span>



[<span data-ttu-id="f7d9f-133">MAPIERROR</span><span class="sxs-lookup"><span data-stu-id="f7d9f-133">MAPIERROR</span></span>](mapierror.md)
  
[<span data-ttu-id="f7d9f-134">MAPIFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="f7d9f-134">MAPIFreeBuffer</span></span>](mapifreebuffer.md)
  
[<span data-ttu-id="f7d9f-135">IMAPIControl : IUnknown</span><span class="sxs-lookup"><span data-stu-id="f7d9f-135">IMAPIControl : IUnknown</span></span>](imapicontroliunknown.md)

