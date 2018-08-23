---
title: IMAPIFormFactoryGetLastError
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIFormFactory.GetLastError
api_type:
- COM
ms.assetid: 4b1d85f6-7996-4839-b985-abf83e305651
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: b4d9838846a124b1c81ec9f9fc6309dcd37c7f2d
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22578141"
---
# <a name="imapiformfactorygetlasterror"></a><span data-ttu-id="e06d0-103">IMAPIFormFactory::GetLastError</span><span class="sxs-lookup"><span data-stu-id="e06d0-103">IMAPIFormFactory::GetLastError</span></span>

  
  
<span data-ttu-id="e06d0-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="e06d0-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="e06d0-105">返回一个[MAPIERROR](mapierror.md)结构，其中包含有关前面对窗体中心对象发生的错误的信息。</span><span class="sxs-lookup"><span data-stu-id="e06d0-105">Returns a [MAPIERROR](mapierror.md) structure that contains information about the previous error occurring to the form factory object.</span></span> 
  
```cpp
HRESULT GetLastError(
  HRESULT hResult,
  ULONG ulFlags,
  LPMAPIERROR FAR * lppMAPIError
);
```

## <a name="parameters"></a><span data-ttu-id="e06d0-106">参数</span><span class="sxs-lookup"><span data-stu-id="e06d0-106">Parameters</span></span>

 <span data-ttu-id="e06d0-107">_hResult_</span><span class="sxs-lookup"><span data-stu-id="e06d0-107">_hResult_</span></span>
  
> <span data-ttu-id="e06d0-108">[in]包含上一方法调用中生成的错误值 HRESULT 数据类型。</span><span class="sxs-lookup"><span data-stu-id="e06d0-108">[in] An HRESULT data type that contains the error value generated in the previous method call.</span></span>
    
 <span data-ttu-id="e06d0-109">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="e06d0-109">_ulFlags_</span></span>
  
> <span data-ttu-id="e06d0-110">[in]返回控制的字符串类型的标志位掩码。</span><span class="sxs-lookup"><span data-stu-id="e06d0-110">[in] A bitmask of flags that controls the type of strings returned.</span></span> <span data-ttu-id="e06d0-111">可以设置以下标记：</span><span class="sxs-lookup"><span data-stu-id="e06d0-111">The following flag can be set:</span></span> 
    
<span data-ttu-id="e06d0-112">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="e06d0-112">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="e06d0-113">返回_lppMAPIError_参数中的**MAPIERROR**结构中的字符串采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="e06d0-113">The strings in the **MAPIERROR** structure returned in the  _lppMAPIError_ parameter are in Unicode format.</span></span> <span data-ttu-id="e06d0-114">如果未设置 MAPI_UNICODE 标志的字符串是以 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="e06d0-114">If the MAPI_UNICODE flag is not set, the strings are in ANSI format.</span></span> 
    
 <span data-ttu-id="e06d0-115">_lppMAPIError_</span><span class="sxs-lookup"><span data-stu-id="e06d0-115">_lppMAPIError_</span></span>
  
> <span data-ttu-id="e06d0-116">[输出]指向包含错误的版本、 组件及上下文信息返回**MAPIERROR**结构的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="e06d0-116">[out] A pointer to a pointer to the returned **MAPIERROR** structure that contains version, component, and context information for the error.</span></span> <span data-ttu-id="e06d0-117">如果不没有返回任何**MAPIERROR**结构，此参数可以设置为 NULL。</span><span class="sxs-lookup"><span data-stu-id="e06d0-117">This parameter can be set to NULL if there is no **MAPIERROR** structure to return.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="e06d0-118">返回值</span><span class="sxs-lookup"><span data-stu-id="e06d0-118">Return value</span></span>

<span data-ttu-id="e06d0-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="e06d0-119">S_OK</span></span> 
  
> <span data-ttu-id="e06d0-120">呼叫成功或多个预期值返回。</span><span class="sxs-lookup"><span data-stu-id="e06d0-120">The call succeeded and has returned the expected value or values.</span></span>
    
<span data-ttu-id="e06d0-121">MAPI_E_BAD_CHARWIDTH</span><span class="sxs-lookup"><span data-stu-id="e06d0-121">MAPI_E_BAD_CHARWIDTH</span></span> 
  
> <span data-ttu-id="e06d0-122">既设置了 MAPI_UNICODE 标志**GetLastError**不支持 Unicode，或未设置 MAPI_UNICODE 和**GetLastError**支持仅 Unicode。</span><span class="sxs-lookup"><span data-stu-id="e06d0-122">Either the MAPI_UNICODE flag was set and **GetLastError** does not support Unicode, or MAPI_UNICODE was not set and **GetLastError** supports only Unicode.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="e06d0-123">注解</span><span class="sxs-lookup"><span data-stu-id="e06d0-123">Remarks</span></span>

<span data-ttu-id="e06d0-124">**IMAPIFormFactory::GetLastError**方法提供有关失败的前一个方法调用的信息。</span><span class="sxs-lookup"><span data-stu-id="e06d0-124">The **IMAPIFormFactory::GetLastError** method supplies information about a prior method call that failed.</span></span> <span data-ttu-id="e06d0-125">呼叫者可以向其用户提供有关错误的详细信息通过在对话框中包括的**MAPIERROR**结构中的数据。</span><span class="sxs-lookup"><span data-stu-id="e06d0-125">Callers can provide their users with detailed information about the error by including the data from the **MAPIERROR** structure in a dialog box.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="e06d0-126">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="e06d0-126">Notes to callers</span></span>

<span data-ttu-id="e06d0-127">您可以利用**MAPIERROR**结构_lppMAPIError_参数指向如果 MAPI 提供一个仅当**时出错**，则返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="e06d0-127">You can make use of the **MAPIERROR** structure pointed to by the  _lppMAPIError_ parameter if MAPI supplies one only if **GetLastError** returns S_OK.</span></span> <span data-ttu-id="e06d0-128">有时 MAPI 无法确定最后一个错误已或某种更多有关错误报告。</span><span class="sxs-lookup"><span data-stu-id="e06d0-128">Sometimes MAPI cannot determine what the last error was or has nothing more to report about the error.</span></span> <span data-ttu-id="e06d0-129">在这种情况下，为 NULL 的指针被返回在_lppMAPIError_中。</span><span class="sxs-lookup"><span data-stu-id="e06d0-129">In this situation, a pointer to NULL is returned in  _lppMAPIError_ instead.</span></span> 
  
<span data-ttu-id="e06d0-130">有关**GetLastError**方法的详细信息，请参阅[使用扩展的错误](mapi-extended-errors.md)。</span><span class="sxs-lookup"><span data-stu-id="e06d0-130">For more information about the **GetLastError** method, see [Using Extended Errors](mapi-extended-errors.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="e06d0-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e06d0-131">See also</span></span>



[<span data-ttu-id="e06d0-132">MAPIERROR</span><span class="sxs-lookup"><span data-stu-id="e06d0-132">MAPIERROR</span></span>](mapierror.md)
  
[<span data-ttu-id="e06d0-133">MAPIFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="e06d0-133">MAPIFreeBuffer</span></span>](mapifreebuffer.md)
  
[<span data-ttu-id="e06d0-134">IMAPIFormFactory : IUnknown</span><span class="sxs-lookup"><span data-stu-id="e06d0-134">IMAPIFormFactory : IUnknown</span></span>](imapiformfactoryiunknown.md)

