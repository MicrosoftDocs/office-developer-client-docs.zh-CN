---
title: IMAPIMessageSiteGetLastError
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIMessageSite.GetLastError
api_type:
- COM
ms.assetid: 7ea282d7-388a-4f05-9780-f8dbc5c5d395
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 3426fd29090a6ab1bb0e66f9bb746e84abe3a25e
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22589446"
---
# <a name="imapimessagesitegetlasterror"></a><span data-ttu-id="7353e-103">IMAPIMessageSite::GetLastError</span><span class="sxs-lookup"><span data-stu-id="7353e-103">IMAPIMessageSite::GetLastError</span></span>

  
  
<span data-ttu-id="7353e-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="7353e-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="7353e-105">返回一个[MAPIERROR](mapierror.md)结构，其中包含有关前面的错误消息网站对象发生的信息。</span><span class="sxs-lookup"><span data-stu-id="7353e-105">Returns a [MAPIERROR](mapierror.md) structure that contains information about the previous error occurring to the message site object.</span></span> 
  
```cpp
HRESULT GetLastError(
  HRESULT hResult,
  ULONG ulFlags,
  LPMAPIERROR FAR * lppMAPIError
);
```

## <a name="parameters"></a><span data-ttu-id="7353e-106">参数</span><span class="sxs-lookup"><span data-stu-id="7353e-106">Parameters</span></span>

 <span data-ttu-id="7353e-107">_hResult_</span><span class="sxs-lookup"><span data-stu-id="7353e-107">_hResult_</span></span>
  
> <span data-ttu-id="7353e-108">[in]HRESULT 值，它包含在以前的方法调用中生成的错误值。</span><span class="sxs-lookup"><span data-stu-id="7353e-108">[in] An HRESULT that contains the error value generated in the previous method call.</span></span>
    
 <span data-ttu-id="7353e-109">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="7353e-109">_ulFlags_</span></span>
  
> <span data-ttu-id="7353e-110">[in]返回控制的字符串类型的标志位掩码。</span><span class="sxs-lookup"><span data-stu-id="7353e-110">[in] A bitmask of flags that controls the type of strings returned.</span></span> <span data-ttu-id="7353e-111">可以设置以下标记：</span><span class="sxs-lookup"><span data-stu-id="7353e-111">The following flag can be set:</span></span>
    
<span data-ttu-id="7353e-112">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="7353e-112">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="7353e-113">返回_lppMAPIError_参数中的**MAPIERROR**结构中的字符串采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="7353e-113">The strings in the **MAPIERROR** structure returned in the  _lppMAPIError_ parameter are in Unicode format.</span></span> <span data-ttu-id="7353e-114">如果未设置 MAPI_UNICODE 标志的字符串是以 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="7353e-114">If the MAPI_UNICODE flag is not set, the strings are in ANSI format.</span></span> 
    
 <span data-ttu-id="7353e-115">_lppMAPIError_</span><span class="sxs-lookup"><span data-stu-id="7353e-115">_lppMAPIError_</span></span>
  
> <span data-ttu-id="7353e-116">[输出]指向包含错误的版本、 组件及上下文信息返回**MAPIERROR**结构的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="7353e-116">[out] A pointer to a pointer to the returned **MAPIERROR** structure that contains version, component, and context information for the error.</span></span> <span data-ttu-id="7353e-117">如果不没有返回任何**MAPIERROR**结构，此参数可以设置为 NULL。</span><span class="sxs-lookup"><span data-stu-id="7353e-117">This parameter can be set to NULL if there is no **MAPIERROR** structure to return.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="7353e-118">返回值</span><span class="sxs-lookup"><span data-stu-id="7353e-118">Return value</span></span>

<span data-ttu-id="7353e-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="7353e-119">S_OK</span></span>
  
> <span data-ttu-id="7353e-120">呼叫成功或多个预期值返回。</span><span class="sxs-lookup"><span data-stu-id="7353e-120">The call succeeded and has returned the expected value or values.</span></span>
    
<span data-ttu-id="7353e-121">MAPI_E_BAD_CHARWIDTH</span><span class="sxs-lookup"><span data-stu-id="7353e-121">MAPI_E_BAD_CHARWIDTH</span></span>
  
> <span data-ttu-id="7353e-122">既设置了 MAPI_UNICODE 标志**GetLastError**不支持 Unicode，或未设置 MAPI_UNICODE 和**GetLastError**支持仅 Unicode。</span><span class="sxs-lookup"><span data-stu-id="7353e-122">Either the MAPI_UNICODE flag was set and **GetLastError** does not support Unicode, or MAPI_UNICODE was not set and **GetLastError** supports only Unicode.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="7353e-123">注解</span><span class="sxs-lookup"><span data-stu-id="7353e-123">Remarks</span></span>

<span data-ttu-id="7353e-124">**IMAPIMessageSite::GetLastError**方法提供有关失败的前一个方法调用的信息。</span><span class="sxs-lookup"><span data-stu-id="7353e-124">The **IMAPIMessageSite::GetLastError** method supplies information about a prior method call that failed.</span></span> <span data-ttu-id="7353e-125">呼叫者可以向其用户提供有关错误的详细信息通过在对话框中包括的**MAPIERROR**结构中的数据。</span><span class="sxs-lookup"><span data-stu-id="7353e-125">Callers can provide their users with detailed information about the error by including the data from the **MAPIERROR** structure in a dialog box.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="7353e-126">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="7353e-126">Notes to callers</span></span>

<span data-ttu-id="7353e-127">您可以利用**MAPIERROR**结构_lppMAPIError_参数指向如果 MAPI 提供一个仅当**时出错**，则返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="7353e-127">You can make use of the **MAPIERROR** structure pointed to by the  _lppMAPIError_ parameter if MAPI supplies one only if **GetLastError** returns S_OK.</span></span> <span data-ttu-id="7353e-128">有时 MAPI 无法确定最后一个错误，或某种更多有关错误报告。</span><span class="sxs-lookup"><span data-stu-id="7353e-128">Sometimes MAPI cannot determine what the last error was, or has nothing more to report about the error.</span></span> <span data-ttu-id="7353e-129">在这种情况下，为 NULL 的指针被返回在_lppMAPIError_中。</span><span class="sxs-lookup"><span data-stu-id="7353e-129">In this situation, a pointer to NULL is returned in  _lppMAPIError_ instead.</span></span> 
  
<span data-ttu-id="7353e-130">有关**GetLastError**方法的详细信息，请参阅[使用扩展的错误](mapi-extended-errors.md)。</span><span class="sxs-lookup"><span data-stu-id="7353e-130">For more information about the **GetLastError** method, see [Using Extended Errors](mapi-extended-errors.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="7353e-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7353e-131">See also</span></span>



[<span data-ttu-id="7353e-132">MAPIERROR</span><span class="sxs-lookup"><span data-stu-id="7353e-132">MAPIERROR</span></span>](mapierror.md)
  
[<span data-ttu-id="7353e-133">IMAPIMessageSite : IUnknown</span><span class="sxs-lookup"><span data-stu-id="7353e-133">IMAPIMessageSite : IUnknown</span></span>](imapimessagesiteiunknown.md)

