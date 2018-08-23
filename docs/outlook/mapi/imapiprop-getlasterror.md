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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: f67dbb4d883f2f66099f2e2b9bc06b6c35b98236
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22575831"
---
# <a name="imapipropgetlasterror"></a><span data-ttu-id="aef89-103">IMAPIProp::GetLastError</span><span class="sxs-lookup"><span data-stu-id="aef89-103">IMAPIProp::GetLastError</span></span>

  
  
<span data-ttu-id="aef89-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="aef89-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="aef89-105">返回一个[MAPIERROR](mapierror.md)结构，其中包含有关前面的错误的信息。</span><span class="sxs-lookup"><span data-stu-id="aef89-105">Returns a [MAPIERROR](mapierror.md) structure that contains information about the previous error.</span></span> 
  
```cpp
HRESULT GetLastError(
  HRESULT hResult,
  ULONG ulFlags,
  LPMAPIERROR FAR * lppMAPIError
);
```

## <a name="parameters"></a><span data-ttu-id="aef89-106">参数</span><span class="sxs-lookup"><span data-stu-id="aef89-106">Parameters</span></span>

 <span data-ttu-id="aef89-107">_hResult_</span><span class="sxs-lookup"><span data-stu-id="aef89-107">_hResult_</span></span>
  
> <span data-ttu-id="aef89-108">[in]在以前的方法调用中生成的错误代码句柄。</span><span class="sxs-lookup"><span data-stu-id="aef89-108">[in] A handle to the error code generated in the previous method call.</span></span>
    
 <span data-ttu-id="aef89-109">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="aef89-109">_ulFlags_</span></span>
  
> <span data-ttu-id="aef89-110">[in]位掩码的标志，指示返回所指的_lppMAPIError_ **MAPIERROR**结构中的文本的格式。</span><span class="sxs-lookup"><span data-stu-id="aef89-110">[in] A bitmask of flags that indicates the format for the text returned in the **MAPIERROR** structure pointed to by  _lppMAPIError_.</span></span> <span data-ttu-id="aef89-111">可以设置以下标记：</span><span class="sxs-lookup"><span data-stu-id="aef89-111">The following flag can be set:</span></span>
    
<span data-ttu-id="aef89-112">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="aef89-112">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="aef89-113">字符串应为 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="aef89-113">The strings should be in Unicode format.</span></span> <span data-ttu-id="aef89-114">如果未设置 MAPI_UNICODE 标志，则字符串应以 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="aef89-114">If the MAPI_UNICODE flag is not set, the strings should be in ANSI format.</span></span>
    
 <span data-ttu-id="aef89-115">_lppMAPIError_</span><span class="sxs-lookup"><span data-stu-id="aef89-115">_lppMAPIError_</span></span>
  
> <span data-ttu-id="aef89-116">[输出]指向包含错误的版本、 组件及上下文信息**MAPIERROR**结构的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="aef89-116">[out] A pointer to a pointer to the **MAPIERROR** structure that contains version, component, and context information for the error.</span></span> <span data-ttu-id="aef89-117">要返回的错误信息时， _lppMAPIError_参数可以设置为 NULL。</span><span class="sxs-lookup"><span data-stu-id="aef89-117">The  _lppMAPIError_ parameter can be set to NULL if there is no error information to return.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="aef89-118">返回值</span><span class="sxs-lookup"><span data-stu-id="aef89-118">Return value</span></span>

<span data-ttu-id="aef89-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="aef89-119">S_OK</span></span> 
  
> <span data-ttu-id="aef89-120">返回的错误的信息。</span><span class="sxs-lookup"><span data-stu-id="aef89-120">The error information was returned.</span></span>
    
<span data-ttu-id="aef89-121">MAPI_E_BAD_CHARWIDTH</span><span class="sxs-lookup"><span data-stu-id="aef89-121">MAPI_E_BAD_CHARWIDTH</span></span> 
  
> <span data-ttu-id="aef89-122">既设置了 MAPI_UNICODE 标志实现不支持 Unicode，或未设置 MAPI_UNICODE 并实现支持仅 Unicode。</span><span class="sxs-lookup"><span data-stu-id="aef89-122">Either the MAPI_UNICODE flag was set and the implementation does not support Unicode, or MAPI_UNICODE was not set and the implementation supports only Unicode.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="aef89-123">注解</span><span class="sxs-lookup"><span data-stu-id="aef89-123">Remarks</span></span>

<span data-ttu-id="aef89-124">**IMAPIProp::GetLastError**方法提供有关失败的前一个方法调用的信息。</span><span class="sxs-lookup"><span data-stu-id="aef89-124">The **IMAPIProp::GetLastError** method supplies information about a prior method call that failed.</span></span> <span data-ttu-id="aef89-125">客户端可以其通过用户提供有关错误的详细信息对话框中包括的**MAPIERROR**结构中的数据。</span><span class="sxs-lookup"><span data-stu-id="aef89-125">Clients can provide their users with detailed information about the error by including the data from the **MAPIERROR** structure in a dialog box.</span></span> 
  
<span data-ttu-id="aef89-126">所有**GetLastError**供稿 MAPI 的实现都是 ANSI 实现，除[IAddrBook](iaddrbookimapiprop.md)实现。</span><span class="sxs-lookup"><span data-stu-id="aef89-126">All of the implementations of **GetLastError** provided by MAPI are ANSI implementations, except for the [IAddrBook](iaddrbookimapiprop.md) implementation.</span></span> <span data-ttu-id="aef89-127">附带**IAddrBook** **GetLastError**方法支持 Unicode。</span><span class="sxs-lookup"><span data-stu-id="aef89-127">The **GetLastError** method included with **IAddrBook** supports Unicode.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="aef89-128">针对实施者的注释</span><span class="sxs-lookup"><span data-stu-id="aef89-128">Notes to implementers</span></span>

<span data-ttu-id="aef89-129">远程的详细信息传输提供程序的此方法的实现和什么此方法返回的消息是最多为传输提供程序，因为指向不同的 HRESULT 值的特定错误条件将不同的不同的传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="aef89-129">The details of a remote transport provider's implementation of this method and what messages this method returns are up to the transport provider, because the particular error conditions that lead to various HRESULT values will be different for different transport providers.</span></span>
  
## <a name="notes-to-callers"></a><span data-ttu-id="aef89-130">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="aef89-130">Notes to callers</span></span>

<span data-ttu-id="aef89-131">您可以使用如果**GetLastError**提供，仅当返回值是 S_OK _lppMAPIError_参数中，指向**MAPIERROR**结构。</span><span class="sxs-lookup"><span data-stu-id="aef89-131">You can use the **MAPIERROR** structure pointed to by the  _lppMAPIError_ parameter, if **GetLastError** supplies one, only if the return value is S_OK.</span></span> <span data-ttu-id="aef89-132">有时**GetLastError**无法确定最后一个错误已或某种更多有关错误报告。</span><span class="sxs-lookup"><span data-stu-id="aef89-132">Sometimes **GetLastError** cannot determine what the last error was or has nothing more to report about the error.</span></span> <span data-ttu-id="aef89-133">在这种情况下，为 NULL 的指针被返回在_lppMAPIError_中。</span><span class="sxs-lookup"><span data-stu-id="aef89-133">In this situation, a pointer to NULL is returned in  _lppMAPIError_ instead.</span></span> 
  
<span data-ttu-id="aef89-134">释放**MAPIERROR**结构的内存，调用[MAPIFreeBuffer](mapifreebuffer.md)函数。</span><span class="sxs-lookup"><span data-stu-id="aef89-134">To release the memory for the **MAPIERROR** structure, call the [MAPIFreeBuffer](mapifreebuffer.md) function.</span></span> 
  
<span data-ttu-id="aef89-135">有关**GetLastError**方法的详细信息，请参阅[MAPI 扩展错误](mapi-extended-errors.md)。</span><span class="sxs-lookup"><span data-stu-id="aef89-135">For more information about the **GetLastError** method, see [MAPI Extended Errors](mapi-extended-errors.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="aef89-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="aef89-136">See also</span></span>



[<span data-ttu-id="aef89-137">IAddrBook : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="aef89-137">IAddrBook : IMAPIProp</span></span>](iaddrbookimapiprop.md)
  
[<span data-ttu-id="aef89-138">MAPIERROR</span><span class="sxs-lookup"><span data-stu-id="aef89-138">MAPIERROR</span></span>](mapierror.md)
  
[<span data-ttu-id="aef89-139">MAPIFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="aef89-139">MAPIFreeBuffer</span></span>](mapifreebuffer.md)
  
[<span data-ttu-id="aef89-140">IMAPIProp : IUnknown</span><span class="sxs-lookup"><span data-stu-id="aef89-140">IMAPIProp : IUnknown</span></span>](imapipropiunknown.md)


[<span data-ttu-id="aef89-141">MAPI 扩展错误</span><span class="sxs-lookup"><span data-stu-id="aef89-141">MAPI Extended Errors</span></span>](mapi-extended-errors.md)

