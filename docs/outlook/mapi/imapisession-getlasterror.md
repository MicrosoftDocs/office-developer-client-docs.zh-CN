---
title: IMAPISessionGetLastError
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISession.GetLastError
api_type:
- COM
ms.assetid: 38cb3692-a5f8-403a-9615-9bd5868af23c
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 59b534a076aee6498be9146eabb69c62fca313ed
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775550"
---
# <a name="imapisessiongetlasterror"></a><span data-ttu-id="f4e3c-103">IMAPISession::GetLastError</span><span class="sxs-lookup"><span data-stu-id="f4e3c-103">IMAPISession::GetLastError</span></span>

  
  
<span data-ttu-id="f4e3c-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="f4e3c-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="f4e3c-105">返回一个[MAPIERROR](mapierror.md)结构，其中包含有关以前会话错误的信息。</span><span class="sxs-lookup"><span data-stu-id="f4e3c-105">Returns a [MAPIERROR](mapierror.md) structure that contains information about the previous session error.</span></span> 
  
```cpp
HRESULT GetLastError(
  HRESULT hResult,
  ULONG ulFlags,
  LPMAPIERROR FAR * lppMAPIError
);
```

## <a name="parameters"></a><span data-ttu-id="f4e3c-106">参数</span><span class="sxs-lookup"><span data-stu-id="f4e3c-106">Parameters</span></span>

 <span data-ttu-id="f4e3c-107">_hResult_</span><span class="sxs-lookup"><span data-stu-id="f4e3c-107">_hResult_</span></span>
  
> <span data-ttu-id="f4e3c-108">[in]在以前的方法调用中生成的错误值句柄。</span><span class="sxs-lookup"><span data-stu-id="f4e3c-108">[in] A handle to the error value generated in the previous method call.</span></span>
    
 <span data-ttu-id="f4e3c-109">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="f4e3c-109">_ulFlags_</span></span>
  
> <span data-ttu-id="f4e3c-110">[in]返回控制的字符串类型的标志位掩码。</span><span class="sxs-lookup"><span data-stu-id="f4e3c-110">[in] A bitmask of flags that controls the type of strings returned.</span></span> <span data-ttu-id="f4e3c-111">可以设置以下标记：</span><span class="sxs-lookup"><span data-stu-id="f4e3c-111">The following flag can be set:</span></span>
    
<span data-ttu-id="f4e3c-112">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="f4e3c-112">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="f4e3c-113">返回_lppMAPIError_参数中的**MAPIERROR**结构中的字符串采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="f4e3c-113">The strings in the **MAPIERROR** structure returned in the  _lppMAPIError_ parameter are in Unicode format.</span></span> <span data-ttu-id="f4e3c-114">如果未设置 MAPI_UNICODE 标志的字符串是以 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="f4e3c-114">If the MAPI_UNICODE flag is not set, the strings are in ANSI format.</span></span> 
    
 <span data-ttu-id="f4e3c-115">_lppMAPIError_</span><span class="sxs-lookup"><span data-stu-id="f4e3c-115">_lppMAPIError_</span></span>
  
> <span data-ttu-id="f4e3c-116">[输出]指向包含错误的版本、 组件及上下文信息**MAPIERROR**结构的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="f4e3c-116">[out] A pointer to a pointer to a **MAPIERROR** structure that contains version, component, and context information for the error.</span></span> <span data-ttu-id="f4e3c-117">_LppMAPIError_参数可以设置为 NULL，如果 MAPI 不能提供相应**MAPIERROR**结构的信息。</span><span class="sxs-lookup"><span data-stu-id="f4e3c-117">The  _lppMAPIError_ parameter can be set to NULL if MAPI cannot supply appropriate information for a **MAPIERROR** structure.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="f4e3c-118">返回值</span><span class="sxs-lookup"><span data-stu-id="f4e3c-118">Return value</span></span>

<span data-ttu-id="f4e3c-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="f4e3c-119">S_OK</span></span> 
  
> <span data-ttu-id="f4e3c-120">呼叫成功或多个预期值返回。</span><span class="sxs-lookup"><span data-stu-id="f4e3c-120">The call succeeded and has returned the expected value or values.</span></span>
    
<span data-ttu-id="f4e3c-121">MAPI_E_BAD_CHARWIDTH</span><span class="sxs-lookup"><span data-stu-id="f4e3c-121">MAPI_E_BAD_CHARWIDTH</span></span> 
  
> <span data-ttu-id="f4e3c-122">设置该 MAPI_UNICODE 标记和会话不支持 Unicode。</span><span class="sxs-lookup"><span data-stu-id="f4e3c-122">The MAPI_UNICODE flag was set and the session does not support Unicode.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="f4e3c-123">说明</span><span class="sxs-lookup"><span data-stu-id="f4e3c-123">Remarks</span></span>

<span data-ttu-id="f4e3c-124">**IMAPISession::GetLastError**方法检索信息**IMAPISession**方法的调用返回的最后一个错误。</span><span class="sxs-lookup"><span data-stu-id="f4e3c-124">The **IMAPISession::GetLastError** method retrieves information about the last error that was returned by an **IMAPISession** method call.</span></span> <span data-ttu-id="f4e3c-125">客户端可以向其用户提供有关错误的详细信息通过在对话框中包括此信息。</span><span class="sxs-lookup"><span data-stu-id="f4e3c-125">Clients can provide their users with detailed information about the error by including this information in a dialog box.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="f4e3c-126">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="f4e3c-126">Notes to callers</span></span>

<span data-ttu-id="f4e3c-127">您可以使用**MAPIERROR**结构中，如果 MAPI 提供一个，由指向_lppMAPIError_参数才**GetLastError**返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="f4e3c-127">You can use the **MAPIERROR** structure, if MAPI supplies one, pointed to by the  _lppMAPIError_ parameter only if **GetLastError** returns S_OK.</span></span> <span data-ttu-id="f4e3c-128">有时 MAPI 无法确定最后一个错误是什么，或者它具有更多有关错误报告 nothing。</span><span class="sxs-lookup"><span data-stu-id="f4e3c-128">Sometimes MAPI cannot determine what the last error was, or it has nothing more to report about the error.</span></span> <span data-ttu-id="f4e3c-129">在此情况下， **GetLastError**返回一个指针为 NULL 中_lppMAPIError_相反。</span><span class="sxs-lookup"><span data-stu-id="f4e3c-129">In this situation, **GetLastError** returns a pointer to NULL in  _lppMAPIError_ instead.</span></span> 
  
<span data-ttu-id="f4e3c-130">有关**GetLastError**方法的详细信息，请参阅[MAPI 扩展错误](mapi-extended-errors.md)。</span><span class="sxs-lookup"><span data-stu-id="f4e3c-130">For more information about the **GetLastError** method, see [MAPI Extended Errors](mapi-extended-errors.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="f4e3c-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f4e3c-131">See also</span></span>



[<span data-ttu-id="f4e3c-132">MAPIERROR</span><span class="sxs-lookup"><span data-stu-id="f4e3c-132">MAPIERROR</span></span>](mapierror.md)
  
[<span data-ttu-id="f4e3c-133">MAPIFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="f4e3c-133">MAPIFreeBuffer</span></span>](mapifreebuffer.md)
  
[<span data-ttu-id="f4e3c-134">IMAPISession : IUnknown</span><span class="sxs-lookup"><span data-stu-id="f4e3c-134">IMAPISession : IUnknown</span></span>](imapisessioniunknown.md)


[<span data-ttu-id="f4e3c-135">MAPI 扩展错误</span><span class="sxs-lookup"><span data-stu-id="f4e3c-135">MAPI Extended Errors</span></span>](mapi-extended-errors.md)

