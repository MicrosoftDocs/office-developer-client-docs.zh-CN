---
title: IMAPISupportGetLastError
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISupport.GetLastError
api_type:
- COM
ms.assetid: 5b4290d9-230f-416a-9644-188578565c7b
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 3e641842dd8264c0cd3556c498bd74c77bda32f7
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22577504"
---
# <a name="imapisupportgetlasterror"></a><span data-ttu-id="d9d25-103">IMAPISupport::GetLastError</span><span class="sxs-lookup"><span data-stu-id="d9d25-103">IMAPISupport::GetLastError</span></span>

  
  
<span data-ttu-id="d9d25-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="d9d25-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="d9d25-105">返回一个[MAPIERROR](mapierror.md)结构，其中包含有关前面的支持对象错误的信息。</span><span class="sxs-lookup"><span data-stu-id="d9d25-105">Returns a [MAPIERROR](mapierror.md) structure that contains information about the previous support object error.</span></span> 
  
```cpp
HRESULT GetLastError(
  HRESULT hResult,
  ULONG ulFlags,
  LPMAPIERROR FAR * lppMAPIError
);
```

## <a name="parameters"></a><span data-ttu-id="d9d25-106">参数</span><span class="sxs-lookup"><span data-stu-id="d9d25-106">Parameters</span></span>

 <span data-ttu-id="d9d25-107">_hResult_</span><span class="sxs-lookup"><span data-stu-id="d9d25-107">_hResult_</span></span>
  
> <span data-ttu-id="d9d25-108">[in]支持对象的上一个方法调用中生成的错误值句柄。</span><span class="sxs-lookup"><span data-stu-id="d9d25-108">[in] A handle to the error value generated in the previous method call for the support object.</span></span>
    
 <span data-ttu-id="d9d25-109">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="d9d25-109">_ulFlags_</span></span>
  
> <span data-ttu-id="d9d25-110">[in]返回控制的字符串类型的标志位掩码。</span><span class="sxs-lookup"><span data-stu-id="d9d25-110">[in] A bitmask of flags that controls the type of strings returned.</span></span> <span data-ttu-id="d9d25-111">可以设置以下标记：</span><span class="sxs-lookup"><span data-stu-id="d9d25-111">The following flag can be set:</span></span>
    
<span data-ttu-id="d9d25-112">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="d9d25-112">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="d9d25-113">返回_lppMAPIError_参数中的**MAPIERROR**结构中的字符串采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="d9d25-113">The strings in the **MAPIERROR** structure returned in the  _lppMAPIError_ parameter are in Unicode format.</span></span> <span data-ttu-id="d9d25-114">如果未设置 MAPI_UNICODE 标志的字符串是以 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="d9d25-114">If the MAPI_UNICODE flag is not set, the strings are in ANSI format.</span></span> 
    
 <span data-ttu-id="d9d25-115">_lppMAPIError_</span><span class="sxs-lookup"><span data-stu-id="d9d25-115">_lppMAPIError_</span></span>
  
> <span data-ttu-id="d9d25-116">[输出]指向包含错误的版本、 组件及上下文信息**MAPIERROR**结构的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="d9d25-116">[out] A pointer to a pointer to the **MAPIERROR** structure that contains version, component, and context information for the error.</span></span> <span data-ttu-id="d9d25-117">如果不能提供适当的错误信息**MAPIERROR**结构， _lppMAPIError_参数可以设置为 NULL。</span><span class="sxs-lookup"><span data-stu-id="d9d25-117">The  _lppMAPIError_ parameter can be set to NULL if a **MAPIERROR** structure with appropriate error information cannot be provided.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="d9d25-118">返回值</span><span class="sxs-lookup"><span data-stu-id="d9d25-118">Return value</span></span>

<span data-ttu-id="d9d25-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="d9d25-119">S_OK</span></span> 
  
> <span data-ttu-id="d9d25-120">呼叫成功，并返回预期的值。</span><span class="sxs-lookup"><span data-stu-id="d9d25-120">The call succeeded and returned the expected value or values.</span></span>
    
<span data-ttu-id="d9d25-121">MAPI_E_BAD_CHARWIDTH</span><span class="sxs-lookup"><span data-stu-id="d9d25-121">MAPI_E_BAD_CHARWIDTH</span></span> 
  
> <span data-ttu-id="d9d25-122">既设置了 MAPI_UNICODE 标志 MAPI 不支持 Unicode，或未设置 MAPI_UNICODE 和 MAPI 支持仅 Unicode。</span><span class="sxs-lookup"><span data-stu-id="d9d25-122">Either the MAPI_UNICODE flag was set and MAPI does not support Unicode, or MAPI_UNICODE was not set and MAPI supports only Unicode.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="d9d25-123">注解</span><span class="sxs-lookup"><span data-stu-id="d9d25-123">Remarks</span></span>

<span data-ttu-id="d9d25-124">对于所有支持对象实现**IMAPISupport::GetLastError**方法。</span><span class="sxs-lookup"><span data-stu-id="d9d25-124">The **IMAPISupport::GetLastError** method is implemented for all support objects.</span></span> <span data-ttu-id="d9d25-125">呼叫者可以向其用户提供有关错误的详细信息通过在对话框中包括的**MAPIERROR**结构中的数据。</span><span class="sxs-lookup"><span data-stu-id="d9d25-125">Callers can provide their users with detailed information about the error by including the data from the **MAPIERROR** structure in a dialog box.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="d9d25-126">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="d9d25-126">Notes to callers</span></span>

<span data-ttu-id="d9d25-127">可以使用该指针指向**MAPIERROR**结构中，如果 MAPI 提供一个_lppMAPIError_参数中才**时出错**，则返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="d9d25-127">You can use the pointer to the **MAPIERROR** structure, if MAPI supplies one, in the  _lppMAPIError_ parameter only if **GetLastError** returns S_OK.</span></span> <span data-ttu-id="d9d25-128">有时 MAPI 无法确定最后一个错误是什么，或者它具有更多有关错误报告的 nothing。</span><span class="sxs-lookup"><span data-stu-id="d9d25-128">Sometimes MAPI cannot determine what the last error was or it has nothing more to report about the error.</span></span> <span data-ttu-id="d9d25-129">在此情况下， _lppMAPIError_返回的指针为 NULL 相反。</span><span class="sxs-lookup"><span data-stu-id="d9d25-129">In this situation,  _lppMAPIError_ returns a pointer to NULL instead.</span></span> 
  
<span data-ttu-id="d9d25-130">有关**GetLastError**方法的详细信息，请参阅[MAPI 扩展错误](mapi-extended-errors.md)。</span><span class="sxs-lookup"><span data-stu-id="d9d25-130">For more information about the **GetLastError** method, see [MAPI Extended Errors](mapi-extended-errors.md).</span></span>
  
<span data-ttu-id="d9d25-131">释放所有 MAPI 所分配的内存，请返回**MAPIERROR**结构调用[MAPIFreeBuffer](mapifreebuffer.md)函数。</span><span class="sxs-lookup"><span data-stu-id="d9d25-131">To release all the memory allocated by MAPI, call the [MAPIFreeBuffer](mapifreebuffer.md) function for the returned **MAPIERROR** structure.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="d9d25-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d9d25-132">See also</span></span>



[<span data-ttu-id="d9d25-133">MAPIERROR</span><span class="sxs-lookup"><span data-stu-id="d9d25-133">MAPIERROR</span></span>](mapierror.md)
  
[<span data-ttu-id="d9d25-134">MAPIFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="d9d25-134">MAPIFreeBuffer</span></span>](mapifreebuffer.md)
  
[<span data-ttu-id="d9d25-135">IMAPISupport : IUnknown</span><span class="sxs-lookup"><span data-stu-id="d9d25-135">IMAPISupport : IUnknown</span></span>](imapisupportiunknown.md)


[<span data-ttu-id="d9d25-136">MAPI 扩展错误</span><span class="sxs-lookup"><span data-stu-id="d9d25-136">MAPI Extended Errors</span></span>](mapi-extended-errors.md)

