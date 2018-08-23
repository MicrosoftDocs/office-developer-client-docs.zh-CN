---
title: IABLogonGetLastError
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IABLogon.GetLastError
api_type:
- COM
ms.assetid: d157e29e-7731-4e47-b4a7-e8622b223001
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 1cd432540a4336b46a589e953b5ce4dde7553597
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22573661"
---
# <a name="iablogongetlasterror"></a><span data-ttu-id="b08bb-103">IABLogon::GetLastError</span><span class="sxs-lookup"><span data-stu-id="b08bb-103">IABLogon::GetLastError</span></span>

  
  
<span data-ttu-id="b08bb-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="b08bb-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="b08bb-105">返回一个[MAPIERROR](mapierror.md)结构，其中包含有关以前的通讯簿提供程序错误的信息。</span><span class="sxs-lookup"><span data-stu-id="b08bb-105">Returns a [MAPIERROR](mapierror.md) structure that contains information about the previous address book provider error.</span></span> 
  
```cpp
HRESULT GetLastError(
  HRESULT hResult,
  ULONG ulFlags,
  LPMAPIERROR FAR * lppMAPIError
);
```

## <a name="parameters"></a><span data-ttu-id="b08bb-106">参数</span><span class="sxs-lookup"><span data-stu-id="b08bb-106">Parameters</span></span>

 <span data-ttu-id="b08bb-107">_hResult_</span><span class="sxs-lookup"><span data-stu-id="b08bb-107">_hResult_</span></span>
  
> <span data-ttu-id="b08bb-108">[in]在以前的方法调用中生成的错误值句柄。</span><span class="sxs-lookup"><span data-stu-id="b08bb-108">[in] A handle to the error value generated in the previous method call.</span></span>
    
 <span data-ttu-id="b08bb-109">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="b08bb-109">_ulFlags_</span></span>
  
> <span data-ttu-id="b08bb-110">[in]返回控制的字符串类型的标志位掩码。</span><span class="sxs-lookup"><span data-stu-id="b08bb-110">[in] A bitmask of flags that controls the type of strings returned.</span></span> <span data-ttu-id="b08bb-111">可以设置以下标记：</span><span class="sxs-lookup"><span data-stu-id="b08bb-111">The following flag can be set:</span></span>
    
<span data-ttu-id="b08bb-112">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="b08bb-112">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="b08bb-113">返回_lppMAPIError_参数中的**MAPIERROR**结构中的字符串采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="b08bb-113">The strings in the **MAPIERROR** structure returned in the  _lppMAPIError_ parameter are in Unicode format.</span></span> <span data-ttu-id="b08bb-114">如果未设置 MAPI_UNICODE 标志的字符串是以 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="b08bb-114">If the MAPI_UNICODE flag is not set, the strings are in ANSI format.</span></span> 
    
 <span data-ttu-id="b08bb-115">_lppMAPIError_</span><span class="sxs-lookup"><span data-stu-id="b08bb-115">_lppMAPIError_</span></span>
  
> <span data-ttu-id="b08bb-116">[输出]指向包含错误的版本、 组件及上下文信息**MAPIERROR**结构的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="b08bb-116">[out] A pointer to a pointer to a **MAPIERROR** structure that contains version, component, and context information for the error.</span></span> <span data-ttu-id="b08bb-117">_LppMAPIError_参数可以设置为 NULL，如果提供程序不能提供一个**MAPIERROR**相应的信息。</span><span class="sxs-lookup"><span data-stu-id="b08bb-117">The  _lppMAPIError_ parameter can be set to NULL if the provider cannot supply a **MAPIERROR** structure with appropriate information.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="b08bb-118">返回值</span><span class="sxs-lookup"><span data-stu-id="b08bb-118">Return value</span></span>

<span data-ttu-id="b08bb-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="b08bb-119">S_OK</span></span> 
  
> <span data-ttu-id="b08bb-120">呼叫成功或多个预期值返回。</span><span class="sxs-lookup"><span data-stu-id="b08bb-120">The call succeeded and has returned the expected value or values.</span></span>
    
<span data-ttu-id="b08bb-121">MAPI_E_BAD_CHARWIDTH</span><span class="sxs-lookup"><span data-stu-id="b08bb-121">MAPI_E_BAD_CHARWIDTH</span></span> 
  
> <span data-ttu-id="b08bb-122">既设置了 MAPI_UNICODE 标志通讯簿提供程序不支持 Unicode，或未设置 MAPI_UNICODE 和通讯簿提供程序支持仅 Unicode。</span><span class="sxs-lookup"><span data-stu-id="b08bb-122">Either the MAPI_UNICODE flag was set and the address book provider does not support Unicode, or MAPI_UNICODE was not set and the address book provider supports only Unicode.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="b08bb-123">注解</span><span class="sxs-lookup"><span data-stu-id="b08bb-123">Remarks</span></span>

<span data-ttu-id="b08bb-124">通讯簿提供程序实现**GetLastError**方法以提供有关失败的前一个方法调用的信息。</span><span class="sxs-lookup"><span data-stu-id="b08bb-124">Address book providers implement the **GetLastError** method to supply information about a prior method call that failed.</span></span> <span data-ttu-id="b08bb-125">呼叫者可以向其用户提供有关错误的详细信息通过在对话框中包括的**MAPIERROR**结构中的数据。</span><span class="sxs-lookup"><span data-stu-id="b08bb-125">Callers can provide their users with detailed information about the error by including the data from the **MAPIERROR** structure in a dialog box.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="b08bb-126">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="b08bb-126">Notes to callers</span></span>

<span data-ttu-id="b08bb-127">您可以使用通讯簿提供程序提供结构且仅当**时出错**，则返回 S_OK _lppMAPIError_参数指向的**MAPIERROR**结构。</span><span class="sxs-lookup"><span data-stu-id="b08bb-127">You can use the **MAPIERROR** structure pointed to by the  _lppMAPIError_ parameter if the address book provider supplies the structure and only if **GetLastError** returns S_OK.</span></span> <span data-ttu-id="b08bb-128">有时通讯簿提供程序无法确定最后一个错误已或某种更多有关错误报告。</span><span class="sxs-lookup"><span data-stu-id="b08bb-128">Sometimes the address book provider cannot determine what the last error was or has nothing more to report about the error.</span></span> <span data-ttu-id="b08bb-129">在此情况下，通讯簿提供程序返回一个指针为 NULL 中_lppMAPIError_相反。</span><span class="sxs-lookup"><span data-stu-id="b08bb-129">In this situation, the address book provider returns a pointer to NULL in  _lppMAPIError_ instead.</span></span> 
  
<span data-ttu-id="b08bb-130">有关**GetLastError**方法的详细信息，请参阅[MAPI 扩展错误](mapi-extended-errors.md)。</span><span class="sxs-lookup"><span data-stu-id="b08bb-130">For more information about the **GetLastError** method, see [MAPI Extended Errors](mapi-extended-errors.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="b08bb-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b08bb-131">See also</span></span>



[<span data-ttu-id="b08bb-132">MAPIERROR</span><span class="sxs-lookup"><span data-stu-id="b08bb-132">MAPIERROR</span></span>](mapierror.md)
  
[<span data-ttu-id="b08bb-133">MAPIFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="b08bb-133">MAPIFreeBuffer</span></span>](mapifreebuffer.md)
  
[<span data-ttu-id="b08bb-134">IABLogon : IUnknown</span><span class="sxs-lookup"><span data-stu-id="b08bb-134">IABLogon : IUnknown</span></span>](iablogoniunknown.md)

