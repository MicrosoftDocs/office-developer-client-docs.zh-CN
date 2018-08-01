---
title: IMAPITableGetLastError
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPITable.GetLastError
api_type:
- COM
ms.assetid: 832e2c18-ddba-4d18-a391-710d21fe23e6
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: b8ee83ad550106ae82f3308b9ef5692f66f5f5b6
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775706"
---
# <a name="imapitablegetlasterror"></a><span data-ttu-id="03d7a-103">IMAPITable::GetLastError</span><span class="sxs-lookup"><span data-stu-id="03d7a-103">IMAPITable::GetLastError</span></span>

  
  
<span data-ttu-id="03d7a-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="03d7a-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="03d7a-105">返回[MAPIERROR](mapierror.md)结构包含有关在表格的上一个错误。</span><span class="sxs-lookup"><span data-stu-id="03d7a-105">Returns a [MAPIERROR](mapierror.md) structure containing information about the previous error on the table.</span></span> 
  
```cpp
HRESULT GetLastError(
HRESULT hResult,
ULONG ulFlags,
LPMAPIERROR FAR * lppMAPIError
);
```

## <a name="parameters"></a><span data-ttu-id="03d7a-106">参数</span><span class="sxs-lookup"><span data-stu-id="03d7a-106">Parameters</span></span>

 <span data-ttu-id="03d7a-107">_hResult_</span><span class="sxs-lookup"><span data-stu-id="03d7a-107">_hResult_</span></span>
  
> <span data-ttu-id="03d7a-108">[in]HRESULT 包含在前面的方法调用中生成错误。</span><span class="sxs-lookup"><span data-stu-id="03d7a-108">[in] HRESULT containing the error generated in the previous method call.</span></span>
    
 <span data-ttu-id="03d7a-109">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="03d7a-109">_ulFlags_</span></span>
  
> <span data-ttu-id="03d7a-110">[in]位掩码的标志，控制返回的字符串的类型。</span><span class="sxs-lookup"><span data-stu-id="03d7a-110">[in] Bitmask of flags that controls the type of the returned strings.</span></span> <span data-ttu-id="03d7a-111">可以设置以下标记：</span><span class="sxs-lookup"><span data-stu-id="03d7a-111">The following flag can be set:</span></span>
    
<span data-ttu-id="03d7a-112">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="03d7a-112">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="03d7a-113">返回_lppMAPIError_参数中的**MAPIERROR**结构中的字符串采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="03d7a-113">The strings in the **MAPIERROR** structure returned in the  _lppMAPIError_ parameter are in Unicode format.</span></span> <span data-ttu-id="03d7a-114">如果未设置 MAPI_UNICODE 标志的字符串是以 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="03d7a-114">If the MAPI_UNICODE flag is not set, the strings are in ANSI format.</span></span> 
    
 <span data-ttu-id="03d7a-115">_lppMAPIError_</span><span class="sxs-lookup"><span data-stu-id="03d7a-115">_lppMAPIError_</span></span>
  
> <span data-ttu-id="03d7a-116">[输出]为包含用于错误的版本、 组件及上下文信息的返回**MAPIERROR**结构指针的指针。</span><span class="sxs-lookup"><span data-stu-id="03d7a-116">[out] Pointer to a pointer to the returned **MAPIERROR** structure containing version, component, and context information for the error.</span></span> <span data-ttu-id="03d7a-117">_LppMAPIError_参数可以设置为 NULL，如果不能提供一个**MAPIERROR**相应的信息。</span><span class="sxs-lookup"><span data-stu-id="03d7a-117">The  _lppMAPIError_ parameter can be set to NULL if a **MAPIERROR** structure with appropriate information cannot be provided.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="03d7a-118">返回值</span><span class="sxs-lookup"><span data-stu-id="03d7a-118">Return value</span></span>

<span data-ttu-id="03d7a-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="03d7a-119">S_OK</span></span> 
  
> <span data-ttu-id="03d7a-120">呼叫成功或多个预期值返回。</span><span class="sxs-lookup"><span data-stu-id="03d7a-120">The call succeeded and has returned the expected value or values.</span></span>
    
<span data-ttu-id="03d7a-121">MAPI_E_BAD_CHARWIDTH</span><span class="sxs-lookup"><span data-stu-id="03d7a-121">MAPI_E_BAD_CHARWIDTH</span></span> 
  
> <span data-ttu-id="03d7a-122">既设置了 MAPI_UNICODE 标志实现不支持 Unicode，或未设置 MAPI_UNICODE 并实现仅支持 Unicode。</span><span class="sxs-lookup"><span data-stu-id="03d7a-122">Either the MAPI_UNICODE flag was set and the implementation does not support Unicode, or MAPI_UNICODE was not set and the implementation only supports Unicode.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="03d7a-123">说明</span><span class="sxs-lookup"><span data-stu-id="03d7a-123">Remarks</span></span>

<span data-ttu-id="03d7a-124">**IMAPITable::GetLastError**方法返回的详细的信息，如果可用，有关失败的前一个方法调用。</span><span class="sxs-lookup"><span data-stu-id="03d7a-124">The **IMAPITable::GetLastError** method returns detailed information, if available, about a prior method call that failed.</span></span> <span data-ttu-id="03d7a-125">可以在一条消息或对话框中显示此信息。</span><span class="sxs-lookup"><span data-stu-id="03d7a-125">This information can be displayed in a message or a dialog box.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="03d7a-126">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="03d7a-126">Notes to callers</span></span>

<span data-ttu-id="03d7a-127">无论何时需要向用户显示错误的信息，请调用**时出错**。</span><span class="sxs-lookup"><span data-stu-id="03d7a-127">Call **GetLastError** whenever you need to display information about an error to the user.</span></span> 
  
<span data-ttu-id="03d7a-128">您可以利用[MAPIERROR](mapierror.md)结构_lppMAPIError_参数指向如果 table 对象提供一个仅当**时出错**，则返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="03d7a-128">You can make use of the [MAPIERROR](mapierror.md) structure pointed to by the  _lppMAPIError_ parameter if the table object supplies one only if **GetLastError** returns S_OK.</span></span> <span data-ttu-id="03d7a-129">有时表实现无法确定最后一个错误已或某种更多有关错误报告。</span><span class="sxs-lookup"><span data-stu-id="03d7a-129">Sometimes the table implementation cannot determine what the last error was or has nothing more to report about the error.</span></span> <span data-ttu-id="03d7a-130">在此情况下，在_lppMAPIError_指针设置为 NULL。</span><span class="sxs-lookup"><span data-stu-id="03d7a-130">In this situation, the pointer at  _lppMAPIError_ is set to NULL.</span></span> 
  
<span data-ttu-id="03d7a-131">若要解除所有**MAPIERROR**结构分配的内存，调用[MAPIFreeBuffer](mapifreebuffer.md)函数。</span><span class="sxs-lookup"><span data-stu-id="03d7a-131">To release all the memory allocated for the **MAPIERROR** structure, call the [MAPIFreeBuffer](mapifreebuffer.md) function.</span></span> 
  
<span data-ttu-id="03d7a-132">有关**GetLastError**方法的详细信息，请参阅[MAPI 扩展错误](mapi-extended-errors.md)。</span><span class="sxs-lookup"><span data-stu-id="03d7a-132">For more information about the **GetLastError** method, see [MAPI Extended Errors](mapi-extended-errors.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="03d7a-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="03d7a-133">See also</span></span>



[<span data-ttu-id="03d7a-134">MAPIERROR</span><span class="sxs-lookup"><span data-stu-id="03d7a-134">MAPIERROR</span></span>](mapierror.md)
  
[<span data-ttu-id="03d7a-135">MAPIFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="03d7a-135">MAPIFreeBuffer</span></span>](mapifreebuffer.md)
  
[<span data-ttu-id="03d7a-136">IMAPITable : IUnknown</span><span class="sxs-lookup"><span data-stu-id="03d7a-136">IMAPITable : IUnknown</span></span>](imapitableiunknown.md)

