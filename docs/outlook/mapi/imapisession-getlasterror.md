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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 7477213ee854be1ae71b47a0c1b339c4c13b6f04
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33435577"
---
# <a name="imapisessiongetlasterror"></a><span data-ttu-id="34152-103">IMAPISession::GetLastError</span><span class="sxs-lookup"><span data-stu-id="34152-103">IMAPISession::GetLastError</span></span>

  
  
<span data-ttu-id="34152-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="34152-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="34152-105">返回一 [个 MAPIERROR](mapierror.md) 结构，其中包含有关上一个会话错误的信息。</span><span class="sxs-lookup"><span data-stu-id="34152-105">Returns a [MAPIERROR](mapierror.md) structure that contains information about the previous session error.</span></span> 
  
```cpp
HRESULT GetLastError(
  HRESULT hResult,
  ULONG ulFlags,
  LPMAPIERROR FAR * lppMAPIError
);
```

## <a name="parameters"></a><span data-ttu-id="34152-106">参数</span><span class="sxs-lookup"><span data-stu-id="34152-106">Parameters</span></span>

 <span data-ttu-id="34152-107">_hResult_</span><span class="sxs-lookup"><span data-stu-id="34152-107">_hResult_</span></span>
  
> <span data-ttu-id="34152-108">[in]上一个方法调用中生成的错误值的句柄。</span><span class="sxs-lookup"><span data-stu-id="34152-108">[in] A handle to the error value generated in the previous method call.</span></span>
    
 <span data-ttu-id="34152-109">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="34152-109">_ulFlags_</span></span>
  
> <span data-ttu-id="34152-110">[in]控制返回的字符串类型的标志位掩码。</span><span class="sxs-lookup"><span data-stu-id="34152-110">[in] A bitmask of flags that controls the type of strings returned.</span></span> <span data-ttu-id="34152-111">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="34152-111">The following flag can be set:</span></span>
    
<span data-ttu-id="34152-112">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="34152-112">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="34152-113">_lppMAPIError_ 参数中返回的 **MAPIERROR** 结构中的字符串采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="34152-113">The strings in the **MAPIERROR** structure returned in the  _lppMAPIError_ parameter are in Unicode format.</span></span> <span data-ttu-id="34152-114">如果未MAPI_UNICODE，则字符串采用 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="34152-114">If the MAPI_UNICODE flag is not set, the strings are in ANSI format.</span></span> 
    
 <span data-ttu-id="34152-115">_lppMAPIError_</span><span class="sxs-lookup"><span data-stu-id="34152-115">_lppMAPIError_</span></span>
  
> <span data-ttu-id="34152-116">[out]指向 **MAPIERROR** 结构的指针的指针，其中包含错误的版本、组件和上下文信息。</span><span class="sxs-lookup"><span data-stu-id="34152-116">[out] A pointer to a pointer to a **MAPIERROR** structure that contains version, component, and context information for the error.</span></span> <span data-ttu-id="34152-117">如果 MAPI 无法为 **MAPIERROR** 结构提供适当的信息，可以将 _lppMAPIError_ 参数设置为 NULL。</span><span class="sxs-lookup"><span data-stu-id="34152-117">The  _lppMAPIError_ parameter can be set to NULL if MAPI cannot supply appropriate information for a **MAPIERROR** structure.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="34152-118">返回值</span><span class="sxs-lookup"><span data-stu-id="34152-118">Return value</span></span>

<span data-ttu-id="34152-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="34152-119">S_OK</span></span> 
  
> <span data-ttu-id="34152-120">调用成功并返回了预期值。</span><span class="sxs-lookup"><span data-stu-id="34152-120">The call succeeded and has returned the expected value or values.</span></span>
    
<span data-ttu-id="34152-121">MAPI_E_BAD_CHARWIDTH</span><span class="sxs-lookup"><span data-stu-id="34152-121">MAPI_E_BAD_CHARWIDTH</span></span> 
  
> <span data-ttu-id="34152-122">已MAPI_UNICODE该标记，并且会话不支持 Unicode。</span><span class="sxs-lookup"><span data-stu-id="34152-122">The MAPI_UNICODE flag was set and the session does not support Unicode.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="34152-123">备注</span><span class="sxs-lookup"><span data-stu-id="34152-123">Remarks</span></span>

<span data-ttu-id="34152-124">**IMAPISession：：GetLastError** 方法检索 **有关 IMAPISession** 方法调用返回的最后一个错误的信息。</span><span class="sxs-lookup"><span data-stu-id="34152-124">The **IMAPISession::GetLastError** method retrieves information about the last error that was returned by an **IMAPISession** method call.</span></span> <span data-ttu-id="34152-125">客户端可以通过在对话框中包含此信息来为用户提供有关错误的详细信息。</span><span class="sxs-lookup"><span data-stu-id="34152-125">Clients can provide their users with detailed information about the error by including this information in a dialog box.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="34152-126">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="34152-126">Notes to callers</span></span>

<span data-ttu-id="34152-127">如果 MAPI 提供由 _lppMAPIError_ 参数指向的 **MAPIERROR** 结构，则仅在 **GetLastError** 返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="34152-127">You can use the **MAPIERROR** structure, if MAPI supplies one, pointed to by the  _lppMAPIError_ parameter only if **GetLastError** returns S_OK.</span></span> <span data-ttu-id="34152-128">有时 MAPI 无法确定上一个错误是什么，或者它仅能报告有关该错误的信息。</span><span class="sxs-lookup"><span data-stu-id="34152-128">Sometimes MAPI cannot determine what the last error was, or it has nothing more to report about the error.</span></span> <span data-ttu-id="34152-129">在这种情况下 **，GetLastError** 会改为在  _lppMAPIError_ 中返回指向 NULL 的指针。</span><span class="sxs-lookup"><span data-stu-id="34152-129">In this situation, **GetLastError** returns a pointer to NULL in  _lppMAPIError_ instead.</span></span> 
  
<span data-ttu-id="34152-130">有关 **GetLastError** 方法的详细信息，请参阅 [MAPI 扩展错误](mapi-extended-errors.md)。</span><span class="sxs-lookup"><span data-stu-id="34152-130">For more information about the **GetLastError** method, see [MAPI Extended Errors](mapi-extended-errors.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="34152-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="34152-131">See also</span></span>



[<span data-ttu-id="34152-132">MAPIERROR</span><span class="sxs-lookup"><span data-stu-id="34152-132">MAPIERROR</span></span>](mapierror.md)
  
[<span data-ttu-id="34152-133">MAPIFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="34152-133">MAPIFreeBuffer</span></span>](mapifreebuffer.md)
  
[<span data-ttu-id="34152-134">IMAPISession : IUnknown</span><span class="sxs-lookup"><span data-stu-id="34152-134">IMAPISession : IUnknown</span></span>](imapisessioniunknown.md)


[<span data-ttu-id="34152-135">MAPI 扩展错误</span><span class="sxs-lookup"><span data-stu-id="34152-135">MAPI Extended Errors</span></span>](mapi-extended-errors.md)

