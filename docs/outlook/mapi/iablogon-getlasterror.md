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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 311299b00143667b3f2fb22bd7be6c3a52c7141d
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33434247"
---
# <a name="iablogongetlasterror"></a><span data-ttu-id="fc597-103">IABLogon::GetLastError</span><span class="sxs-lookup"><span data-stu-id="fc597-103">IABLogon::GetLastError</span></span>

  
  
<span data-ttu-id="fc597-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="fc597-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="fc597-105">返回一 [个 MAPIERROR](mapierror.md) 结构，其中包含有关以前的通讯簿提供程序错误的信息。</span><span class="sxs-lookup"><span data-stu-id="fc597-105">Returns a [MAPIERROR](mapierror.md) structure that contains information about the previous address book provider error.</span></span> 
  
```cpp
HRESULT GetLastError(
  HRESULT hResult,
  ULONG ulFlags,
  LPMAPIERROR FAR * lppMAPIError
);
```

## <a name="parameters"></a><span data-ttu-id="fc597-106">参数</span><span class="sxs-lookup"><span data-stu-id="fc597-106">Parameters</span></span>

 <span data-ttu-id="fc597-107">_hResult_</span><span class="sxs-lookup"><span data-stu-id="fc597-107">_hResult_</span></span>
  
> <span data-ttu-id="fc597-108">[in]上一个方法调用中生成的错误值的句柄。</span><span class="sxs-lookup"><span data-stu-id="fc597-108">[in] A handle to the error value generated in the previous method call.</span></span>
    
 <span data-ttu-id="fc597-109">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="fc597-109">_ulFlags_</span></span>
  
> <span data-ttu-id="fc597-110">[in]控制返回的字符串类型的标志位掩码。</span><span class="sxs-lookup"><span data-stu-id="fc597-110">[in] A bitmask of flags that controls the type of strings returned.</span></span> <span data-ttu-id="fc597-111">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="fc597-111">The following flag can be set:</span></span>
    
<span data-ttu-id="fc597-112">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="fc597-112">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="fc597-113">_lppMAPIError_ 参数中返回的 **MAPIERROR** 结构中的字符串采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="fc597-113">The strings in the **MAPIERROR** structure returned in the  _lppMAPIError_ parameter are in Unicode format.</span></span> <span data-ttu-id="fc597-114">如果未MAPI_UNICODE，则字符串采用 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="fc597-114">If the MAPI_UNICODE flag is not set, the strings are in ANSI format.</span></span> 
    
 <span data-ttu-id="fc597-115">_lppMAPIError_</span><span class="sxs-lookup"><span data-stu-id="fc597-115">_lppMAPIError_</span></span>
  
> <span data-ttu-id="fc597-116">[out]指向 **MAPIERROR** 结构的指针的指针，其中包含错误的版本、组件和上下文信息。</span><span class="sxs-lookup"><span data-stu-id="fc597-116">[out] A pointer to a pointer to a **MAPIERROR** structure that contains version, component, and context information for the error.</span></span> <span data-ttu-id="fc597-117">如果提供程序无法向 **MAPIERROR** 结构提供适当的信息，则 _lppMAPIError_ 参数可以设置为 NULL。</span><span class="sxs-lookup"><span data-stu-id="fc597-117">The  _lppMAPIError_ parameter can be set to NULL if the provider cannot supply a **MAPIERROR** structure with appropriate information.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="fc597-118">返回值</span><span class="sxs-lookup"><span data-stu-id="fc597-118">Return value</span></span>

<span data-ttu-id="fc597-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="fc597-119">S_OK</span></span> 
  
> <span data-ttu-id="fc597-120">调用成功并返回了预期值。</span><span class="sxs-lookup"><span data-stu-id="fc597-120">The call succeeded and has returned the expected value or values.</span></span>
    
<span data-ttu-id="fc597-121">MAPI_E_BAD_CHARWIDTH</span><span class="sxs-lookup"><span data-stu-id="fc597-121">MAPI_E_BAD_CHARWIDTH</span></span> 
  
> <span data-ttu-id="fc597-122">设置 MAPI_UNICODE 标志，通讯簿提供程序不支持 Unicode，或者MAPI_UNICODE设置该地址簿提供程序仅支持 Unicode。</span><span class="sxs-lookup"><span data-stu-id="fc597-122">Either the MAPI_UNICODE flag was set and the address book provider does not support Unicode, or MAPI_UNICODE was not set and the address book provider supports only Unicode.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="fc597-123">备注</span><span class="sxs-lookup"><span data-stu-id="fc597-123">Remarks</span></span>

<span data-ttu-id="fc597-124">通讯簿提供程序实现 **GetLastError** 方法，以提供有关失败的之前方法调用的信息。</span><span class="sxs-lookup"><span data-stu-id="fc597-124">Address book providers implement the **GetLastError** method to supply information about a prior method call that failed.</span></span> <span data-ttu-id="fc597-125">调用方可以通过在对话框中包含 **MAPIERROR** 结构的数据来为用户提供有关错误的详细信息。</span><span class="sxs-lookup"><span data-stu-id="fc597-125">Callers can provide their users with detailed information about the error by including the data from the **MAPIERROR** structure in a dialog box.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="fc597-126">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="fc597-126">Notes to callers</span></span>

<span data-ttu-id="fc597-127">如果通讯簿提供程序提供结构并且仅在 **GetLastError** 返回 S_OK，您可以使用 _lppMAPIError_ 参数指向的 **MAPIERROR** 结构。</span><span class="sxs-lookup"><span data-stu-id="fc597-127">You can use the **MAPIERROR** structure pointed to by the  _lppMAPIError_ parameter if the address book provider supplies the structure and only if **GetLastError** returns S_OK.</span></span> <span data-ttu-id="fc597-128">有时，通讯簿提供程序无法确定上一个错误是什么，或者没有更多关于错误的报告。</span><span class="sxs-lookup"><span data-stu-id="fc597-128">Sometimes the address book provider cannot determine what the last error was or has nothing more to report about the error.</span></span> <span data-ttu-id="fc597-129">在这种情况下，通讯簿提供程序会改为在  _lppMAPIError_ 中返回指向 NULL 的指针。</span><span class="sxs-lookup"><span data-stu-id="fc597-129">In this situation, the address book provider returns a pointer to NULL in  _lppMAPIError_ instead.</span></span> 
  
<span data-ttu-id="fc597-130">有关 **GetLastError** 方法的详细信息，请参阅 [MAPI 扩展错误](mapi-extended-errors.md)。</span><span class="sxs-lookup"><span data-stu-id="fc597-130">For more information about the **GetLastError** method, see [MAPI Extended Errors](mapi-extended-errors.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="fc597-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fc597-131">See also</span></span>



[<span data-ttu-id="fc597-132">MAPIERROR</span><span class="sxs-lookup"><span data-stu-id="fc597-132">MAPIERROR</span></span>](mapierror.md)
  
[<span data-ttu-id="fc597-133">MAPIFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="fc597-133">MAPIFreeBuffer</span></span>](mapifreebuffer.md)
  
[<span data-ttu-id="fc597-134">IABLogon : IUnknown</span><span class="sxs-lookup"><span data-stu-id="fc597-134">IABLogon : IUnknown</span></span>](iablogoniunknown.md)

