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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: c34c175c43ada03e982f08a27f675448ea24a567
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32316589"
---
# <a name="imapisupportgetlasterror"></a><span data-ttu-id="0a6f8-103">IMAPISupport::GetLastError</span><span class="sxs-lookup"><span data-stu-id="0a6f8-103">IMAPISupport::GetLastError</span></span>

  
  
<span data-ttu-id="0a6f8-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="0a6f8-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="0a6f8-105">返回一个[MAPIERROR](mapierror.md)结构, 该结构包含上一个支持对象错误的相关信息。</span><span class="sxs-lookup"><span data-stu-id="0a6f8-105">Returns a [MAPIERROR](mapierror.md) structure that contains information about the previous support object error.</span></span> 
  
```cpp
HRESULT GetLastError(
  HRESULT hResult,
  ULONG ulFlags,
  LPMAPIERROR FAR * lppMAPIError
);
```

## <a name="parameters"></a><span data-ttu-id="0a6f8-106">参数</span><span class="sxs-lookup"><span data-stu-id="0a6f8-106">Parameters</span></span>

 <span data-ttu-id="0a6f8-107">_hResult_</span><span class="sxs-lookup"><span data-stu-id="0a6f8-107">_hResult_</span></span>
  
> <span data-ttu-id="0a6f8-108">实时对支持对象的上一个方法调用中生成的错误值的句柄。</span><span class="sxs-lookup"><span data-stu-id="0a6f8-108">[in] A handle to the error value generated in the previous method call for the support object.</span></span>
    
 <span data-ttu-id="0a6f8-109">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="0a6f8-109">_ulFlags_</span></span>
  
> <span data-ttu-id="0a6f8-110">实时用于控制返回的字符串类型的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="0a6f8-110">[in] A bitmask of flags that controls the type of strings returned.</span></span> <span data-ttu-id="0a6f8-111">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="0a6f8-111">The following flag can be set:</span></span>
    
<span data-ttu-id="0a6f8-112">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="0a6f8-112">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="0a6f8-113">在_lppMAPIError_参数中返回的**MAPIERROR**结构中的字符串采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="0a6f8-113">The strings in the **MAPIERROR** structure returned in the  _lppMAPIError_ parameter are in Unicode format.</span></span> <span data-ttu-id="0a6f8-114">如果未设置 MAPI_UNICODE 标志, 则字符串将采用 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="0a6f8-114">If the MAPI_UNICODE flag is not set, the strings are in ANSI format.</span></span> 
    
 <span data-ttu-id="0a6f8-115">_lppMAPIError_</span><span class="sxs-lookup"><span data-stu-id="0a6f8-115">_lppMAPIError_</span></span>
  
> <span data-ttu-id="0a6f8-116">排除指向包含错误的版本、组件和上下文信息的**MAPIERROR**结构的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="0a6f8-116">[out] A pointer to a pointer to the **MAPIERROR** structure that contains version, component, and context information for the error.</span></span> <span data-ttu-id="0a6f8-117">如果无法提供具有相应错误消息的**MAPIERROR**结构, 则可以将_lppMAPIError_参数设置为 NULL。</span><span class="sxs-lookup"><span data-stu-id="0a6f8-117">The  _lppMAPIError_ parameter can be set to NULL if a **MAPIERROR** structure with appropriate error information cannot be provided.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="0a6f8-118">返回值</span><span class="sxs-lookup"><span data-stu-id="0a6f8-118">Return value</span></span>

<span data-ttu-id="0a6f8-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="0a6f8-119">S_OK</span></span> 
  
> <span data-ttu-id="0a6f8-120">调用成功, 并返回了所需的一个或一些值。</span><span class="sxs-lookup"><span data-stu-id="0a6f8-120">The call succeeded and returned the expected value or values.</span></span>
    
<span data-ttu-id="0a6f8-121">MAPI_E_BAD_CHARWIDTH</span><span class="sxs-lookup"><span data-stu-id="0a6f8-121">MAPI_E_BAD_CHARWIDTH</span></span> 
  
> <span data-ttu-id="0a6f8-122">设置了 MAPI_UNICODE 标志且 mapi 不支持 unicode, 或者未设置 MAPI_UNICODE, 且 mapi 仅支持 UNICODE。</span><span class="sxs-lookup"><span data-stu-id="0a6f8-122">Either the MAPI_UNICODE flag was set and MAPI does not support Unicode, or MAPI_UNICODE was not set and MAPI supports only Unicode.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="0a6f8-123">注解</span><span class="sxs-lookup"><span data-stu-id="0a6f8-123">Remarks</span></span>

<span data-ttu-id="0a6f8-124">**IMAPISupport:: GetLastError**方法是为所有支持对象实现的。</span><span class="sxs-lookup"><span data-stu-id="0a6f8-124">The **IMAPISupport::GetLastError** method is implemented for all support objects.</span></span> <span data-ttu-id="0a6f8-125">通过在对话框中包含**MAPIERROR**结构中的数据, 呼叫者可以向其用户提供有关错误的详细信息。</span><span class="sxs-lookup"><span data-stu-id="0a6f8-125">Callers can provide their users with detailed information about the error by including the data from the **MAPIERROR** structure in a dialog box.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="0a6f8-126">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="0a6f8-126">Notes to callers</span></span>

<span data-ttu-id="0a6f8-127">只有当**GetLastError**返回 S_OK 时, 才能在_lppMAPIError_参数中使用指向**MAPIERROR**结构的指针 (如果 MAPI 提供一个)。</span><span class="sxs-lookup"><span data-stu-id="0a6f8-127">You can use the pointer to the **MAPIERROR** structure, if MAPI supplies one, in the  _lppMAPIError_ parameter only if **GetLastError** returns S_OK.</span></span> <span data-ttu-id="0a6f8-128">有时 MAPI 无法确定是什么是最后一个错误, 或者它对错误报告没有更多的报告。</span><span class="sxs-lookup"><span data-stu-id="0a6f8-128">Sometimes MAPI cannot determine what the last error was or it has nothing more to report about the error.</span></span> <span data-ttu-id="0a6f8-129">在这种情况下, _lppMAPIError_返回指向 NULL 的指针。</span><span class="sxs-lookup"><span data-stu-id="0a6f8-129">In this situation,  _lppMAPIError_ returns a pointer to NULL instead.</span></span> 
  
<span data-ttu-id="0a6f8-130">有关**GetLastError**方法的详细信息, 请参阅[MAPI 扩展错误](mapi-extended-errors.md)。</span><span class="sxs-lookup"><span data-stu-id="0a6f8-130">For more information about the **GetLastError** method, see [MAPI Extended Errors](mapi-extended-errors.md).</span></span>
  
<span data-ttu-id="0a6f8-131">若要释放 MAPI 分配的所有内存, 请调用返回的**MAPIERROR**结构的[MAPIFreeBuffer](mapifreebuffer.md)函数。</span><span class="sxs-lookup"><span data-stu-id="0a6f8-131">To release all the memory allocated by MAPI, call the [MAPIFreeBuffer](mapifreebuffer.md) function for the returned **MAPIERROR** structure.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="0a6f8-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0a6f8-132">See also</span></span>



[<span data-ttu-id="0a6f8-133">MAPIERROR</span><span class="sxs-lookup"><span data-stu-id="0a6f8-133">MAPIERROR</span></span>](mapierror.md)
  
[<span data-ttu-id="0a6f8-134">MAPIFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="0a6f8-134">MAPIFreeBuffer</span></span>](mapifreebuffer.md)
  
[<span data-ttu-id="0a6f8-135">IMAPISupport : IUnknown</span><span class="sxs-lookup"><span data-stu-id="0a6f8-135">IMAPISupport : IUnknown</span></span>](imapisupportiunknown.md)


[<span data-ttu-id="0a6f8-136">MAPI 扩展错误</span><span class="sxs-lookup"><span data-stu-id="0a6f8-136">MAPI Extended Errors</span></span>](mapi-extended-errors.md)

