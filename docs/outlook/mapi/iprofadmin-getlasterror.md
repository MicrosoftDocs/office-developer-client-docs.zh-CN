---
title: IProfAdminGetLastError
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IProfAdmin.GetLastError
api_type:
- COM
ms.assetid: bb161d7b-ae5b-4f8e-a506-8346ac5e583d
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 65bf7debcae1367ccad9e109242fd4a72839a94e
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22584924"
---
# <a name="iprofadmingetlasterror"></a><span data-ttu-id="087ca-103">IProfAdmin::GetLastError</span><span class="sxs-lookup"><span data-stu-id="087ca-103">IProfAdmin::GetLastError</span></span>

  
  
<span data-ttu-id="087ca-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="087ca-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="087ca-105">返回一个[MAPIERROR](mapierror.md)结构，其中包含有关前面的配置文件管理对象发生的错误的信息。</span><span class="sxs-lookup"><span data-stu-id="087ca-105">Returns a [MAPIERROR](mapierror.md) structure that contains information about the previous error that occurred to a profile administration object.</span></span> 
  
```cpp
HRESULT GetLastError(
  HRESULT hResult,
  ULONG ulFlags,
  LPMAPIERROR FAR * lppMAPIError
);
```

## <a name="parameters"></a><span data-ttu-id="087ca-106">参数</span><span class="sxs-lookup"><span data-stu-id="087ca-106">Parameters</span></span>

 <span data-ttu-id="087ca-107">_hResult_</span><span class="sxs-lookup"><span data-stu-id="087ca-107">_hResult_</span></span>
  
> <span data-ttu-id="087ca-108">[in]包含上一方法调用中生成的错误值 HRESULT 数据类型。</span><span class="sxs-lookup"><span data-stu-id="087ca-108">[in] An HRESULT data type that contains the error value generated in the previous method call.</span></span>
    
 <span data-ttu-id="087ca-109">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="087ca-109">_ulFlags_</span></span>
  
> <span data-ttu-id="087ca-110">[in]返回控制的字符串类型的标志位掩码。</span><span class="sxs-lookup"><span data-stu-id="087ca-110">[in] A bitmask of flags that controls the type of strings returned.</span></span> <span data-ttu-id="087ca-111">可以设置以下标记：</span><span class="sxs-lookup"><span data-stu-id="087ca-111">The following flag can be set:</span></span>
    
<span data-ttu-id="087ca-112">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="087ca-112">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="087ca-113">返回_lppMAPIError_参数中的[MAPIERROR](mapierror.md)结构中的字符串采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="087ca-113">The strings in the [MAPIERROR](mapierror.md) structure returned in the  _lppMAPIError_ parameter are in Unicode format.</span></span> <span data-ttu-id="087ca-114">如果未设置 MAPI_UNICODE 标志的字符串是以 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="087ca-114">If the MAPI_UNICODE flag is not set, the strings are in ANSI format.</span></span> 
    
 <span data-ttu-id="087ca-115">_lppMAPIError_</span><span class="sxs-lookup"><span data-stu-id="087ca-115">_lppMAPIError_</span></span>
  
> <span data-ttu-id="087ca-116">[输出]指向包含错误的版本、 组件及上下文信息**MAPIERROR**结构的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="087ca-116">[out] A pointer to a pointer to the **MAPIERROR** structure that contains version, component, and context information for the error.</span></span> <span data-ttu-id="087ca-117">如果不没有返回任何**MAPIERROR**结构， _lppMAPIError_参数可以设置为 NULL。</span><span class="sxs-lookup"><span data-stu-id="087ca-117">The  _lppMAPIError_ parameter can be set to NULL if there is no **MAPIERROR** structure to return.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="087ca-118">返回值</span><span class="sxs-lookup"><span data-stu-id="087ca-118">Return value</span></span>

<span data-ttu-id="087ca-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="087ca-119">S_OK</span></span> 
  
> <span data-ttu-id="087ca-120">呼叫成功或多个预期值返回。</span><span class="sxs-lookup"><span data-stu-id="087ca-120">The call succeeded and has returned the expected value or values.</span></span>
    
<span data-ttu-id="087ca-121">MAPI_E_BAD_CHARWIDTH</span><span class="sxs-lookup"><span data-stu-id="087ca-121">MAPI_E_BAD_CHARWIDTH</span></span> 
  
> <span data-ttu-id="087ca-122">既设置了 MAPI_UNICODE 标志实现不支持 Unicode，或未设置 MAPI_UNICODE 并实现支持仅 Unicode。</span><span class="sxs-lookup"><span data-stu-id="087ca-122">Either the MAPI_UNICODE flag was set and the implementation does not support Unicode, or MAPI_UNICODE was not set and the implementation supports only Unicode.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="087ca-123">注解</span><span class="sxs-lookup"><span data-stu-id="087ca-123">Remarks</span></span>

<span data-ttu-id="087ca-124">**IProfAdmin::GetLastError**方法检索信息从配置文件管理对象方法调用返回的最后一个错误。</span><span class="sxs-lookup"><span data-stu-id="087ca-124">The **IProfAdmin::GetLastError** method retrieves information about the last error returned from a method call for the profile administration object.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="087ca-125">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="087ca-125">Notes to callers</span></span>

<span data-ttu-id="087ca-126">您可以使用**MAPIERROR**结构中，如果 MAPI 提供一个，由指向_lppMAPIError_参数才**GetLastError**返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="087ca-126">You can use the **MAPIERROR** structure, if MAPI supplies one, pointed to by the  _lppMAPIError_ parameter only if **GetLastError** returns S_OK.</span></span> <span data-ttu-id="087ca-127">有时 MAPI 无法确定最后一个错误已或某种更多有关错误报告。</span><span class="sxs-lookup"><span data-stu-id="087ca-127">Sometimes MAPI cannot determine what the last error was or has nothing more to report about the error.</span></span> <span data-ttu-id="087ca-128">在此情况下，为 NULL 的指针返回_lppMAPIError_。</span><span class="sxs-lookup"><span data-stu-id="087ca-128">In this situation, a pointer to NULL is returned in  _lppMAPIError_.</span></span> 
  
<span data-ttu-id="087ca-129">释放所有 MAPI **MAPIERROR**结构所分配的内存，调用[MAPIFreeBuffer](mapifreebuffer.md)函数。</span><span class="sxs-lookup"><span data-stu-id="087ca-129">To release all the memory allocated by MAPI for the **MAPIERROR** structure, call the [MAPIFreeBuffer](mapifreebuffer.md) function.</span></span> 
  
<span data-ttu-id="087ca-130">有关**GetLastError**方法的详细信息，请参阅[使用扩展的错误](mapi-extended-errors.md)。</span><span class="sxs-lookup"><span data-stu-id="087ca-130">For more information about the **GetLastError** method, see [Using Extended Errors](mapi-extended-errors.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="087ca-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="087ca-131">See also</span></span>



[<span data-ttu-id="087ca-132">MAPIERROR</span><span class="sxs-lookup"><span data-stu-id="087ca-132">MAPIERROR</span></span>](mapierror.md)
  
[<span data-ttu-id="087ca-133">MAPIFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="087ca-133">MAPIFreeBuffer</span></span>](mapifreebuffer.md)
  
[<span data-ttu-id="087ca-134">IProfAdmin : IUnknown</span><span class="sxs-lookup"><span data-stu-id="087ca-134">IProfAdmin : IUnknown</span></span>](iprofadminiunknown.md)

