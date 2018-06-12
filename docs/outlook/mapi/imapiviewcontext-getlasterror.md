---
title: IMAPIViewContextGetLastError
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIViewContext.GetLastError
api_type:
- COM
ms.assetid: 3306e37a-2500-4281-96c3-ca0d5c81909d
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: f7455e9013f3bd9460ae5f4d876c135594840b68
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775739"
---
# <a name="imapiviewcontextgetlasterror"></a><span data-ttu-id="395ee-103">IMAPIViewContext::GetLastError</span><span class="sxs-lookup"><span data-stu-id="395ee-103">IMAPIViewContext::GetLastError</span></span>

  
  
<span data-ttu-id="395ee-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="395ee-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="395ee-105">返回一个[MAPIERROR](mapierror.md)结构，其中包含有关前面对视图上下文对象发生的错误的信息。</span><span class="sxs-lookup"><span data-stu-id="395ee-105">Returns a [MAPIERROR](mapierror.md) structure that contains information about the previous error occurring to the view context object.</span></span> 
  
```cpp
HRESULT GetLastError(
HRESULT hResult,
ULONG ulFlags,
LPMAPIERROR FAR * lppMAPIError
);
```

## <a name="parameters"></a><span data-ttu-id="395ee-106">参数</span><span class="sxs-lookup"><span data-stu-id="395ee-106">Parameters</span></span>

 <span data-ttu-id="395ee-107">_hResult_</span><span class="sxs-lookup"><span data-stu-id="395ee-107">_hResult_</span></span>
  
> <span data-ttu-id="395ee-108">[in]包含上一方法调用中生成的错误值的 HRESULT 数据类型。</span><span class="sxs-lookup"><span data-stu-id="395ee-108">[in] HRESULT data type that contains the error value generated in the previous method call.</span></span>
    
 <span data-ttu-id="395ee-109">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="395ee-109">_ulFlags_</span></span>
  
> <span data-ttu-id="395ee-110">[in]返回的标志的控制的字符串类型的位掩码。</span><span class="sxs-lookup"><span data-stu-id="395ee-110">[in] Bitmask of flags that controls the type of strings returned.</span></span> <span data-ttu-id="395ee-111">可以设置以下标记：</span><span class="sxs-lookup"><span data-stu-id="395ee-111">The following flag can be set:</span></span>
    
<span data-ttu-id="395ee-112">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="395ee-112">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="395ee-113">返回_lppMAPIError_参数中的**MAPIERROR**结构中的字符串采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="395ee-113">The strings in the **MAPIERROR** structure returned in the  _lppMAPIError_ parameter are in Unicode format.</span></span> <span data-ttu-id="395ee-114">如果未设置 MAPI_UNICODE 标志的字符串是以 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="395ee-114">If the MAPI_UNICODE flag is not set, the strings are in ANSI format.</span></span> 
    
 <span data-ttu-id="395ee-115">_lppMAPIError_</span><span class="sxs-lookup"><span data-stu-id="395ee-115">_lppMAPIError_</span></span>
  
> <span data-ttu-id="395ee-116">[输出]为包含用于错误的版本、 组件及上下文信息返回**MAPIERROR**结构指针的指针。</span><span class="sxs-lookup"><span data-stu-id="395ee-116">[out] Pointer to a pointer to the returned **MAPIERROR** structure that contains version, component, and context information for the error.</span></span> <span data-ttu-id="395ee-117">如果不没有返回任何**MAPIERROR**结构，此参数可以设置为 NULL。</span><span class="sxs-lookup"><span data-stu-id="395ee-117">This parameter can be set to NULL if there is no **MAPIERROR** structure to return.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="395ee-118">返回值</span><span class="sxs-lookup"><span data-stu-id="395ee-118">Return value</span></span>

<span data-ttu-id="395ee-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="395ee-119">S_OK</span></span> 
  
> <span data-ttu-id="395ee-120">呼叫成功或多个预期值返回。</span><span class="sxs-lookup"><span data-stu-id="395ee-120">The call succeeded and has returned the expected value or values.</span></span>
    
<span data-ttu-id="395ee-121">MAPI_E_BAD_CHARWIDTH</span><span class="sxs-lookup"><span data-stu-id="395ee-121">MAPI_E_BAD_CHARWIDTH</span></span> 
  
> <span data-ttu-id="395ee-122">可以设置该 MAPI_UNICODE 标记**GetLastError**不支持 Unicode，或未设置 MAPI_UNICODE 和**GetLastError**仅支持 Unicode。</span><span class="sxs-lookup"><span data-stu-id="395ee-122">Either the MAPI_UNICODE flag was set and **GetLastError** does not support Unicode, or MAPI_UNICODE was not set and **GetLastError** only supports Unicode.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="395ee-123">备注</span><span class="sxs-lookup"><span data-stu-id="395ee-123">Remarks</span></span>

<span data-ttu-id="395ee-124">**IMAPIViewContext::GetLastError**方法提供有关失败的前一个方法调用的信息。</span><span class="sxs-lookup"><span data-stu-id="395ee-124">The **IMAPIViewContext::GetLastError** method supplies information about a prior method call that failed.</span></span> <span data-ttu-id="395ee-125">呼叫者可以向其用户提供有关错误的详细信息通过在对话框中包括的**MAPIERROR**结构中的数据。</span><span class="sxs-lookup"><span data-stu-id="395ee-125">Callers can provide their users with detailed information about the error by including the data from the **MAPIERROR** structure in a dialog box.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="395ee-126">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="395ee-126">Notes to callers</span></span>

<span data-ttu-id="395ee-127">您可以利用**MAPIERROR**结构_lppMAPIError_参数指向如果 MAPI 提供一个仅当**时出错**，则返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="395ee-127">You can make use of the **MAPIERROR** structure pointed to by the  _lppMAPIError_ parameter if MAPI supplies one only if **GetLastError** returns S_OK.</span></span> <span data-ttu-id="395ee-128">有时 MAPI 无法确定最后一个错误已或某种更多有关错误报告。</span><span class="sxs-lookup"><span data-stu-id="395ee-128">Sometimes MAPI cannot determine what the last error was or has nothing more to report about the error.</span></span> <span data-ttu-id="395ee-129">在这种情况下，为 NULL 的指针被返回在_lppMAPIError_中。</span><span class="sxs-lookup"><span data-stu-id="395ee-129">In this situation, a pointer to NULL is returned in  _lppMAPIError_ instead.</span></span> 
  
<span data-ttu-id="395ee-130">有关**GetLastError**方法的详细信息，请参阅[MAPI 扩展错误](mapi-extended-errors.md)。</span><span class="sxs-lookup"><span data-stu-id="395ee-130">For more information about the **GetLastError** method, see [MAPI Extended Errors](mapi-extended-errors.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="395ee-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="395ee-131">See also</span></span>



[<span data-ttu-id="395ee-132">MAPIERROR</span><span class="sxs-lookup"><span data-stu-id="395ee-132">MAPIERROR</span></span>](mapierror.md)
  
[<span data-ttu-id="395ee-133">MAPIFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="395ee-133">MAPIFreeBuffer</span></span>](mapifreebuffer.md)
  
[<span data-ttu-id="395ee-134">IMAPIViewContext: IUnknown</span><span class="sxs-lookup"><span data-stu-id="395ee-134">IMAPIViewContext : IUnknown</span></span>](imapiviewcontextiunknown.md)

