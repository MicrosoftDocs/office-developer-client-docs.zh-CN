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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: b6964ecde3a78bd1e9ce0ae1dcab0342c5a21a03
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33430771"
---
# <a name="iprofadmingetlasterror"></a><span data-ttu-id="4bc0f-103">IProfAdmin::GetLastError</span><span class="sxs-lookup"><span data-stu-id="4bc0f-103">IProfAdmin::GetLastError</span></span>

  
  
<span data-ttu-id="4bc0f-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="4bc0f-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="4bc0f-105">返回 [一个 MAPIERROR](mapierror.md) 结构，其中包含有关配置文件管理对象发生的上一个错误的信息。</span><span class="sxs-lookup"><span data-stu-id="4bc0f-105">Returns a [MAPIERROR](mapierror.md) structure that contains information about the previous error that occurred to a profile administration object.</span></span> 
  
```cpp
HRESULT GetLastError(
  HRESULT hResult,
  ULONG ulFlags,
  LPMAPIERROR FAR * lppMAPIError
);
```

## <a name="parameters"></a><span data-ttu-id="4bc0f-106">参数</span><span class="sxs-lookup"><span data-stu-id="4bc0f-106">Parameters</span></span>

 <span data-ttu-id="4bc0f-107">_hResult_</span><span class="sxs-lookup"><span data-stu-id="4bc0f-107">_hResult_</span></span>
  
> <span data-ttu-id="4bc0f-108">[in]HRESULT 数据类型，其中包含在上一个方法调用中生成的错误值。</span><span class="sxs-lookup"><span data-stu-id="4bc0f-108">[in] An HRESULT data type that contains the error value generated in the previous method call.</span></span>
    
 <span data-ttu-id="4bc0f-109">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="4bc0f-109">_ulFlags_</span></span>
  
> <span data-ttu-id="4bc0f-110">[in]控制返回的字符串类型的标志位掩码。</span><span class="sxs-lookup"><span data-stu-id="4bc0f-110">[in] A bitmask of flags that controls the type of strings returned.</span></span> <span data-ttu-id="4bc0f-111">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="4bc0f-111">The following flag can be set:</span></span>
    
<span data-ttu-id="4bc0f-112">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="4bc0f-112">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="4bc0f-113">_lppMAPIError_ 参数中返回的 [MAPIERROR](mapierror.md)结构中的字符串采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="4bc0f-113">The strings in the [MAPIERROR](mapierror.md) structure returned in the  _lppMAPIError_ parameter are in Unicode format.</span></span> <span data-ttu-id="4bc0f-114">如果未MAPI_UNICODE，则字符串采用 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="4bc0f-114">If the MAPI_UNICODE flag is not set, the strings are in ANSI format.</span></span> 
    
 <span data-ttu-id="4bc0f-115">_lppMAPIError_</span><span class="sxs-lookup"><span data-stu-id="4bc0f-115">_lppMAPIError_</span></span>
  
> <span data-ttu-id="4bc0f-116">[out]指向指向 **MAPIERROR** 结构的指针的指针，该结构包含错误的版本、组件和上下文信息。</span><span class="sxs-lookup"><span data-stu-id="4bc0f-116">[out] A pointer to a pointer to the **MAPIERROR** structure that contains version, component, and context information for the error.</span></span> <span data-ttu-id="4bc0f-117">如果没有要返回的 **MAPIERROR** 结构，可以将 _lppMAPIError_ 参数设置为 NULL。</span><span class="sxs-lookup"><span data-stu-id="4bc0f-117">The  _lppMAPIError_ parameter can be set to NULL if there is no **MAPIERROR** structure to return.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="4bc0f-118">返回值</span><span class="sxs-lookup"><span data-stu-id="4bc0f-118">Return value</span></span>

<span data-ttu-id="4bc0f-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="4bc0f-119">S_OK</span></span> 
  
> <span data-ttu-id="4bc0f-120">调用成功并返回了预期值。</span><span class="sxs-lookup"><span data-stu-id="4bc0f-120">The call succeeded and has returned the expected value or values.</span></span>
    
<span data-ttu-id="4bc0f-121">MAPI_E_BAD_CHARWIDTH</span><span class="sxs-lookup"><span data-stu-id="4bc0f-121">MAPI_E_BAD_CHARWIDTH</span></span> 
  
> <span data-ttu-id="4bc0f-122">设置 MAPI_UNICODE 标志，而实现不支持 Unicode，或者MAPI_UNICODE未设置，并且实现仅支持 Unicode。</span><span class="sxs-lookup"><span data-stu-id="4bc0f-122">Either the MAPI_UNICODE flag was set and the implementation does not support Unicode, or MAPI_UNICODE was not set and the implementation supports only Unicode.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="4bc0f-123">备注</span><span class="sxs-lookup"><span data-stu-id="4bc0f-123">Remarks</span></span>

<span data-ttu-id="4bc0f-124">**IProfAdmin：：GetLastError** 方法检索有关从配置文件管理对象的方法调用返回的最后一个错误的信息。</span><span class="sxs-lookup"><span data-stu-id="4bc0f-124">The **IProfAdmin::GetLastError** method retrieves information about the last error returned from a method call for the profile administration object.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="4bc0f-125">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="4bc0f-125">Notes to callers</span></span>

<span data-ttu-id="4bc0f-126">如果 MAPI 提供由 _lppMAPIError_ 参数指向的 **MAPIERROR** 结构，则仅在 **GetLastError** 返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="4bc0f-126">You can use the **MAPIERROR** structure, if MAPI supplies one, pointed to by the  _lppMAPIError_ parameter only if **GetLastError** returns S_OK.</span></span> <span data-ttu-id="4bc0f-127">有时 MAPI 无法确定上一个错误是什么，或者没有更多关于错误的报告。</span><span class="sxs-lookup"><span data-stu-id="4bc0f-127">Sometimes MAPI cannot determine what the last error was or has nothing more to report about the error.</span></span> <span data-ttu-id="4bc0f-128">在这种情况下，在  _lppMAPIError_ 中返回指向 NULL 的指针。</span><span class="sxs-lookup"><span data-stu-id="4bc0f-128">In this situation, a pointer to NULL is returned in  _lppMAPIError_.</span></span> 
  
<span data-ttu-id="4bc0f-129">若要释放 MAPI 为 **MAPIERROR** 结构分配的所有内存，请调用 [MAPIFreeBuffer](mapifreebuffer.md) 函数。</span><span class="sxs-lookup"><span data-stu-id="4bc0f-129">To release all the memory allocated by MAPI for the **MAPIERROR** structure, call the [MAPIFreeBuffer](mapifreebuffer.md) function.</span></span> 
  
<span data-ttu-id="4bc0f-130">有关 **GetLastError** 方法的详细信息，请参阅 [使用扩展错误](mapi-extended-errors.md)。</span><span class="sxs-lookup"><span data-stu-id="4bc0f-130">For more information about the **GetLastError** method, see [Using Extended Errors](mapi-extended-errors.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="4bc0f-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4bc0f-131">See also</span></span>



[<span data-ttu-id="4bc0f-132">MAPIERROR</span><span class="sxs-lookup"><span data-stu-id="4bc0f-132">MAPIERROR</span></span>](mapierror.md)
  
[<span data-ttu-id="4bc0f-133">MAPIFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="4bc0f-133">MAPIFreeBuffer</span></span>](mapifreebuffer.md)
  
[<span data-ttu-id="4bc0f-134">IProfAdmin : IUnknown</span><span class="sxs-lookup"><span data-stu-id="4bc0f-134">IProfAdmin : IUnknown</span></span>](iprofadminiunknown.md)

