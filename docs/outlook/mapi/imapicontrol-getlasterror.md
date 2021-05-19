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
# <a name="imapicontrolgetlasterror"></a><span data-ttu-id="b35cb-103">IMAPIControl::GetLastError</span><span class="sxs-lookup"><span data-stu-id="b35cb-103">IMAPIControl::GetLastError</span></span>

  
  
<span data-ttu-id="b35cb-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="b35cb-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="b35cb-105">返回一 [个 MAPIERROR](mapierror.md) 结构，其中包含有关上一个按钮控件错误的信息。</span><span class="sxs-lookup"><span data-stu-id="b35cb-105">Returns a [MAPIERROR](mapierror.md) structure that contains information about the previous button control error.</span></span> 
  
```cpp
HRESULT GetLastError(
  HRESULT hResult,
  ULONG ulFlags,
  LPMAPIERROR FAR * lppMAPIError
);
```

## <a name="parameters"></a><span data-ttu-id="b35cb-106">参数</span><span class="sxs-lookup"><span data-stu-id="b35cb-106">Parameters</span></span>

 <span data-ttu-id="b35cb-107">_hResult_</span><span class="sxs-lookup"><span data-stu-id="b35cb-107">_hResult_</span></span>
  
> <span data-ttu-id="b35cb-108">[in]上一个方法调用中生成的错误值的句柄。</span><span class="sxs-lookup"><span data-stu-id="b35cb-108">[in] A handle to the error value generated in the previous method call.</span></span>
    
 <span data-ttu-id="b35cb-109">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="b35cb-109">_ulFlags_</span></span>
  
> <span data-ttu-id="b35cb-110">[in]控制返回的字符串类型的标志位掩码。</span><span class="sxs-lookup"><span data-stu-id="b35cb-110">[in] A bitmask of flags that controls the type of the strings returned.</span></span> <span data-ttu-id="b35cb-111">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="b35cb-111">The following flag can be set:</span></span>
    
<span data-ttu-id="b35cb-112">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="b35cb-112">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="b35cb-113">_lppMAPIError_ 参数中返回的 **MAPIERROR** 结构中的字符串采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="b35cb-113">The strings in the **MAPIERROR** structure returned in the  _lppMAPIError_ parameter are in Unicode format.</span></span> <span data-ttu-id="b35cb-114">如果未MAPI_UNICODE，则字符串采用 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="b35cb-114">If the MAPI_UNICODE flag is not set, the strings are in ANSI format.</span></span> 
    
 <span data-ttu-id="b35cb-115">_lppMAPIError_</span><span class="sxs-lookup"><span data-stu-id="b35cb-115">_lppMAPIError_</span></span>
  
> <span data-ttu-id="b35cb-116">[out]指向 **MAPIERROR** 结构的指针的指针，其中包含错误的版本、组件和上下文信息。</span><span class="sxs-lookup"><span data-stu-id="b35cb-116">[out] A pointer to a pointer to a **MAPIERROR** structure that contains version, component, and context information for the error.</span></span> <span data-ttu-id="b35cb-117">如果提供程序无法向 **MAPIERROR** 结构提供适当的信息，则 _lppMAPIError_ 参数可以设置为 NULL。</span><span class="sxs-lookup"><span data-stu-id="b35cb-117">The  _lppMAPIError_ parameter can be set to NULL if the provider cannot supply a **MAPIERROR** structure with appropriate information.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="b35cb-118">返回值</span><span class="sxs-lookup"><span data-stu-id="b35cb-118">Return value</span></span>

<span data-ttu-id="b35cb-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="b35cb-119">S_OK</span></span> 
  
> <span data-ttu-id="b35cb-120">调用成功并返回了预期值。</span><span class="sxs-lookup"><span data-stu-id="b35cb-120">The call succeeded and has returned the expected value or values.</span></span>
    
<span data-ttu-id="b35cb-121">MAPI_E_BAD_CHARWIDTH</span><span class="sxs-lookup"><span data-stu-id="b35cb-121">MAPI_E_BAD_CHARWIDTH</span></span> 
  
> <span data-ttu-id="b35cb-122">设置 MAPI_UNICODE 标志，而实现不支持 Unicode，或者MAPI_UNICODE未设置，并且实现仅支持 Unicode。</span><span class="sxs-lookup"><span data-stu-id="b35cb-122">Either the MAPI_UNICODE flag was set and the implementation does not support Unicode, or MAPI_UNICODE was not set and the implementation supports only Unicode.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="b35cb-123">备注</span><span class="sxs-lookup"><span data-stu-id="b35cb-123">Remarks</span></span>

<span data-ttu-id="b35cb-124">服务提供商实现 **IMAPIControl：：GetLastError** 方法，以提供有关失败的之前方法调用的信息。</span><span class="sxs-lookup"><span data-stu-id="b35cb-124">Service providers implement the **IMAPIControl::GetLastError** method to supply information about a prior method call that failed.</span></span> <span data-ttu-id="b35cb-125">MAPI 可以通过在消息或对话框中显示 **MAPIERROR** 结构的数据来为用户提供有关错误的详细信息。</span><span class="sxs-lookup"><span data-stu-id="b35cb-125">MAPI can give users detailed information about the error by displaying the data from the **MAPIERROR** structure in a message or dialog box.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="b35cb-126">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="b35cb-126">Notes to implementers</span></span>

<span data-ttu-id="b35cb-127">无需包含针对每个错误的 **MAPIERROR** 结构的信息。</span><span class="sxs-lookup"><span data-stu-id="b35cb-127">You do not need to have information to include in the **MAPIERROR** structure for every error.</span></span> <span data-ttu-id="b35cb-128">可能无法确定上一错误是什么。</span><span class="sxs-lookup"><span data-stu-id="b35cb-128">It may not be possible to determine what the previous error was.</span></span> <span data-ttu-id="b35cb-129">如果你有信息，请S_OK **MAPIERROR** 结构中的数据和相应的数据。</span><span class="sxs-lookup"><span data-stu-id="b35cb-129">If you have information, return S_OK and the appropriate data in the **MAPIERROR** structure.</span></span> <span data-ttu-id="b35cb-130">如果没有可用信息，则返回 S_OK，并返回  _lppMAPIError_ 参数的 NULL 指针。</span><span class="sxs-lookup"><span data-stu-id="b35cb-130">If no information is available, return S_OK and a pointer to NULL for the  _lppMAPIError_ parameter.</span></span> 
  
<span data-ttu-id="b35cb-131">有关 **GetLastError** 方法的详细信息，请参阅 [MAPI 扩展错误](mapi-extended-errors.md)。</span><span class="sxs-lookup"><span data-stu-id="b35cb-131">For more information about the **GetLastError** method, see [MAPI Extended Errors](mapi-extended-errors.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="b35cb-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b35cb-132">See also</span></span>



[<span data-ttu-id="b35cb-133">MAPIERROR</span><span class="sxs-lookup"><span data-stu-id="b35cb-133">MAPIERROR</span></span>](mapierror.md)
  
[<span data-ttu-id="b35cb-134">MAPIFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="b35cb-134">MAPIFreeBuffer</span></span>](mapifreebuffer.md)
  
[<span data-ttu-id="b35cb-135">IMAPIControl : IUnknown</span><span class="sxs-lookup"><span data-stu-id="b35cb-135">IMAPIControl : IUnknown</span></span>](imapicontroliunknown.md)

