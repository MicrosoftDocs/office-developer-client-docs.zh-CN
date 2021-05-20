---
title: IMAPIPropGetLastError
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIProp.GetLastError
api_type:
- COM
ms.assetid: f64a765d-c653-4eef-a0fc-24a54968757c
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 8c31cbf0472d3d64c7327fcfc80480ef27a1638e
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33435829"
---
# <a name="imapipropgetlasterror"></a><span data-ttu-id="d97fc-103">IMAPIProp::GetLastError</span><span class="sxs-lookup"><span data-stu-id="d97fc-103">IMAPIProp::GetLastError</span></span>

  
  
<span data-ttu-id="d97fc-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="d97fc-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="d97fc-105">返回一 [个 MAPIERROR](mapierror.md) 结构，其中包含有关上一个错误的信息。</span><span class="sxs-lookup"><span data-stu-id="d97fc-105">Returns a [MAPIERROR](mapierror.md) structure that contains information about the previous error.</span></span> 
  
```cpp
HRESULT GetLastError(
  HRESULT hResult,
  ULONG ulFlags,
  LPMAPIERROR FAR * lppMAPIError
);
```

## <a name="parameters"></a><span data-ttu-id="d97fc-106">参数</span><span class="sxs-lookup"><span data-stu-id="d97fc-106">Parameters</span></span>

 <span data-ttu-id="d97fc-107">_hResult_</span><span class="sxs-lookup"><span data-stu-id="d97fc-107">_hResult_</span></span>
  
> <span data-ttu-id="d97fc-108">[in]上一个方法调用中生成的错误代码的句柄。</span><span class="sxs-lookup"><span data-stu-id="d97fc-108">[in] A handle to the error code generated in the previous method call.</span></span>
    
 <span data-ttu-id="d97fc-109">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="d97fc-109">_ulFlags_</span></span>
  
> <span data-ttu-id="d97fc-110">[in]指示由 _lppMAPIError_ 指向 **的 MAPIERROR** 结构中返回的文本的格式的标志位掩码。</span><span class="sxs-lookup"><span data-stu-id="d97fc-110">[in] A bitmask of flags that indicates the format for the text returned in the **MAPIERROR** structure pointed to by  _lppMAPIError_.</span></span> <span data-ttu-id="d97fc-111">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="d97fc-111">The following flag can be set:</span></span>
    
<span data-ttu-id="d97fc-112">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="d97fc-112">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="d97fc-113">字符串应为 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="d97fc-113">The strings should be in Unicode format.</span></span> <span data-ttu-id="d97fc-114">如果未MAPI_UNICODE，则字符串应为 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="d97fc-114">If the MAPI_UNICODE flag is not set, the strings should be in ANSI format.</span></span>
    
 <span data-ttu-id="d97fc-115">_lppMAPIError_</span><span class="sxs-lookup"><span data-stu-id="d97fc-115">_lppMAPIError_</span></span>
  
> <span data-ttu-id="d97fc-116">[out]指向指向 **MAPIERROR** 结构的指针的指针，该结构包含错误的版本、组件和上下文信息。</span><span class="sxs-lookup"><span data-stu-id="d97fc-116">[out] A pointer to a pointer to the **MAPIERROR** structure that contains version, component, and context information for the error.</span></span> <span data-ttu-id="d97fc-117">如果没有  _要返回的错误信息，可以将 lppMAPIError_ 参数设置为 NULL。</span><span class="sxs-lookup"><span data-stu-id="d97fc-117">The  _lppMAPIError_ parameter can be set to NULL if there is no error information to return.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="d97fc-118">返回值</span><span class="sxs-lookup"><span data-stu-id="d97fc-118">Return value</span></span>

<span data-ttu-id="d97fc-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="d97fc-119">S_OK</span></span> 
  
> <span data-ttu-id="d97fc-120">返回了错误信息。</span><span class="sxs-lookup"><span data-stu-id="d97fc-120">The error information was returned.</span></span>
    
<span data-ttu-id="d97fc-121">MAPI_E_BAD_CHARWIDTH</span><span class="sxs-lookup"><span data-stu-id="d97fc-121">MAPI_E_BAD_CHARWIDTH</span></span> 
  
> <span data-ttu-id="d97fc-122">设置 MAPI_UNICODE 标志，而实现不支持 Unicode，或者MAPI_UNICODE未设置，并且实现仅支持 Unicode。</span><span class="sxs-lookup"><span data-stu-id="d97fc-122">Either the MAPI_UNICODE flag was set and the implementation does not support Unicode, or MAPI_UNICODE was not set and the implementation supports only Unicode.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="d97fc-123">备注</span><span class="sxs-lookup"><span data-stu-id="d97fc-123">Remarks</span></span>

<span data-ttu-id="d97fc-124">**IMAPIProp：：GetLastError** 方法提供有关失败之前的方法调用的信息。</span><span class="sxs-lookup"><span data-stu-id="d97fc-124">The **IMAPIProp::GetLastError** method supplies information about a prior method call that failed.</span></span> <span data-ttu-id="d97fc-125">客户端可以通过在对话框中包含 **MAPIERROR** 结构的数据，为用户提供有关错误的详细信息。</span><span class="sxs-lookup"><span data-stu-id="d97fc-125">Clients can provide their users with detailed information about the error by including the data from the **MAPIERROR** structure in a dialog box.</span></span> 
  
<span data-ttu-id="d97fc-126">MAPI 提供的所有 **GetLastError** 实现都是 ANSI 实现 [，IAddrBook](iaddrbookimapiprop.md) 实现除外。</span><span class="sxs-lookup"><span data-stu-id="d97fc-126">All of the implementations of **GetLastError** provided by MAPI are ANSI implementations, except for the [IAddrBook](iaddrbookimapiprop.md) implementation.</span></span> <span data-ttu-id="d97fc-127">**IAddrBook** 中包含的 **GetLastError** 方法支持 Unicode。</span><span class="sxs-lookup"><span data-stu-id="d97fc-127">The **GetLastError** method included with **IAddrBook** supports Unicode.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="d97fc-128">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="d97fc-128">Notes to implementers</span></span>

<span data-ttu-id="d97fc-129">远程传输提供程序实现此方法的详细信息以及此方法返回的邮件由传输提供程序决定，因为导致各种 HRESULT 值的特定错误条件对于不同的传输提供程序是不同的。</span><span class="sxs-lookup"><span data-stu-id="d97fc-129">The details of a remote transport provider's implementation of this method and what messages this method returns are up to the transport provider, because the particular error conditions that lead to various HRESULT values will be different for different transport providers.</span></span>
  
## <a name="notes-to-callers"></a><span data-ttu-id="d97fc-130">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="d97fc-130">Notes to callers</span></span>

<span data-ttu-id="d97fc-131">您可以使用 _lppMAPIError_ 参数指向的 **MAPIERROR** 结构，如果 **GetLastError** 提供了一个，则仅在返回值为 S_OK。</span><span class="sxs-lookup"><span data-stu-id="d97fc-131">You can use the **MAPIERROR** structure pointed to by the  _lppMAPIError_ parameter, if **GetLastError** supplies one, only if the return value is S_OK.</span></span> <span data-ttu-id="d97fc-132">有时 **，GetLastError** 无法确定上一个错误是什么，或者没有更多关于错误的报告。</span><span class="sxs-lookup"><span data-stu-id="d97fc-132">Sometimes **GetLastError** cannot determine what the last error was or has nothing more to report about the error.</span></span> <span data-ttu-id="d97fc-133">在这种情况下，将改为在  _lppMAPIError_ 中返回指向 NULL 的指针。</span><span class="sxs-lookup"><span data-stu-id="d97fc-133">In this situation, a pointer to NULL is returned in  _lppMAPIError_ instead.</span></span> 
  
<span data-ttu-id="d97fc-134">若要释放 **MAPIERROR** 结构的内存，请调用 [MAPIFreeBuffer](mapifreebuffer.md) 函数。</span><span class="sxs-lookup"><span data-stu-id="d97fc-134">To release the memory for the **MAPIERROR** structure, call the [MAPIFreeBuffer](mapifreebuffer.md) function.</span></span> 
  
<span data-ttu-id="d97fc-135">有关 **GetLastError** 方法的详细信息，请参阅 [MAPI 扩展错误](mapi-extended-errors.md)。</span><span class="sxs-lookup"><span data-stu-id="d97fc-135">For more information about the **GetLastError** method, see [MAPI Extended Errors](mapi-extended-errors.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d97fc-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d97fc-136">See also</span></span>



[<span data-ttu-id="d97fc-137">IAddrBook : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="d97fc-137">IAddrBook : IMAPIProp</span></span>](iaddrbookimapiprop.md)
  
[<span data-ttu-id="d97fc-138">MAPIERROR</span><span class="sxs-lookup"><span data-stu-id="d97fc-138">MAPIERROR</span></span>](mapierror.md)
  
[<span data-ttu-id="d97fc-139">MAPIFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="d97fc-139">MAPIFreeBuffer</span></span>](mapifreebuffer.md)
  
[<span data-ttu-id="d97fc-140">IMAPIProp : IUnknown</span><span class="sxs-lookup"><span data-stu-id="d97fc-140">IMAPIProp : IUnknown</span></span>](imapipropiunknown.md)


[<span data-ttu-id="d97fc-141">MAPI 扩展错误</span><span class="sxs-lookup"><span data-stu-id="d97fc-141">MAPI Extended Errors</span></span>](mapi-extended-errors.md)

