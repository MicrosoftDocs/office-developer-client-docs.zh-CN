---
title: IProviderAdminGetLastError
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IProviderAdmin.GetLastError
api_type:
- COM
ms.assetid: 853ddee5-24d6-423d-b483-6a07a12de51f
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: f00418efa068ea81fab94605cbdfd139e24bb4a0
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776018"
---
# <a name="iprovideradmingetlasterror"></a><span data-ttu-id="67f86-103">IProviderAdmin::GetLastError</span><span class="sxs-lookup"><span data-stu-id="67f86-103">IProviderAdmin::GetLastError</span></span>

  
  
<span data-ttu-id="67f86-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="67f86-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="67f86-105">返回一个[MAPIERROR](mapierror.md)结构，其中包含有关前面的提供程序的管理对象发生的错误的信息。</span><span class="sxs-lookup"><span data-stu-id="67f86-105">Returns a [MAPIERROR](mapierror.md) structure that contains information about the previous error that occurred to the provider administration object.</span></span> 
  
```cpp
HRESULT GetLastError(
  HRESULT hResult,
  ULONG ulFlags,
  LPMAPIERROR FAR * lppMAPIError
);
```

## <a name="parameters"></a><span data-ttu-id="67f86-106">参数</span><span class="sxs-lookup"><span data-stu-id="67f86-106">Parameters</span></span>

 <span data-ttu-id="67f86-107">_hResult_</span><span class="sxs-lookup"><span data-stu-id="67f86-107">_hResult_</span></span>
  
> <span data-ttu-id="67f86-108">[in]包含上一方法调用中生成的错误值 HRESULT 数据类型。</span><span class="sxs-lookup"><span data-stu-id="67f86-108">[in] An HRESULT data type that contains the error value generated in the previous method call.</span></span>
    
 <span data-ttu-id="67f86-109">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="67f86-109">_ulFlags_</span></span>
  
> <span data-ttu-id="67f86-110">[in]返回控制的字符串类型的标志位掩码。</span><span class="sxs-lookup"><span data-stu-id="67f86-110">[in] A bitmask of flags that controls the type of strings returned.</span></span> <span data-ttu-id="67f86-111">可以设置以下标记：</span><span class="sxs-lookup"><span data-stu-id="67f86-111">The following flag can be set:</span></span>
    
<span data-ttu-id="67f86-112">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="67f86-112">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="67f86-113">中**MAPIERROR** _lppMAPIError_参数中返回的字符串采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="67f86-113">The strings in the **MAPIERROR** returned in the  _lppMAPIError_ parameter are in Unicode format.</span></span> <span data-ttu-id="67f86-114">如果未设置 MAPI_UNICODE 标志的字符串是以 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="67f86-114">If the MAPI_UNICODE flag is not set, the strings are in ANSI format.</span></span> 
    
 <span data-ttu-id="67f86-115">_lppMAPIError_</span><span class="sxs-lookup"><span data-stu-id="67f86-115">_lppMAPIError_</span></span>
  
> <span data-ttu-id="67f86-116">[输出]指向包含错误的版本、 组件及上下文信息返回**MAPIERROR**结构的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="67f86-116">[out] A pointer to a pointer to the returned **MAPIERROR** structure that contains version, component, and context information for the error.</span></span> <span data-ttu-id="67f86-117">如果不没有返回任何**MAPIERROR** ， _lppMAPIError_参数可以设置为 NULL。</span><span class="sxs-lookup"><span data-stu-id="67f86-117">The  _lppMAPIError_ parameter can be set to NULL if there is no **MAPIERROR** to return.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="67f86-118">返回值</span><span class="sxs-lookup"><span data-stu-id="67f86-118">Return value</span></span>

<span data-ttu-id="67f86-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="67f86-119">S_OK</span></span> 
  
> <span data-ttu-id="67f86-120">呼叫成功，并返回预期的值。</span><span class="sxs-lookup"><span data-stu-id="67f86-120">The call succeeded and returned the expected value or values.</span></span>
    
<span data-ttu-id="67f86-121">MAPI_E_BAD_CHARWIDTH</span><span class="sxs-lookup"><span data-stu-id="67f86-121">MAPI_E_BAD_CHARWIDTH</span></span> 
  
> <span data-ttu-id="67f86-122">既设置了 MAPI_UNICODE 标志**GetLastError**不支持 Unicode，或未设置 MAPI_UNICODE 和**GetLastError**支持仅 Unicode。</span><span class="sxs-lookup"><span data-stu-id="67f86-122">Either the MAPI_UNICODE flag was set and **GetLastError** does not support Unicode, or MAPI_UNICODE was not set and **GetLastError** supports only Unicode.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="67f86-123">说明</span><span class="sxs-lookup"><span data-stu-id="67f86-123">Remarks</span></span>

<span data-ttu-id="67f86-124">**IProviderAdmin::GetLastError**方法提供有关失败的前一个方法调用的信息。</span><span class="sxs-lookup"><span data-stu-id="67f86-124">The **IProviderAdmin::GetLastError** method supplies information about a prior method call that failed.</span></span> <span data-ttu-id="67f86-125">呼叫者可以向其用户提供有关错误的详细信息通过在对话框中包括的**MAPIERROR**结构中的数据。</span><span class="sxs-lookup"><span data-stu-id="67f86-125">Callers can provide their users with detailed information about the error by including the data from the **MAPIERROR** structure in a dialog box.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="67f86-126">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="67f86-126">Notes to callers</span></span>

<span data-ttu-id="67f86-127">您可以使用**MAPIERROR**结构中，如果 MAPI 提供一个，仅当**时出错**，则返回 S_OK _lppMAPIError_参数，指向。</span><span class="sxs-lookup"><span data-stu-id="67f86-127">You can use the **MAPIERROR** structure, if MAPI supplies one, that the  _lppMAPIError_ parameter points to only if **GetLastError** returns S_OK.</span></span> <span data-ttu-id="67f86-128">有时 MAPI 无法确定最后一个错误已或某种更多有关错误报告。</span><span class="sxs-lookup"><span data-stu-id="67f86-128">Sometimes MAPI cannot determine what the last error was or has nothing more to report about the error.</span></span> <span data-ttu-id="67f86-129">在这种情况下，为 NULL 的指针被返回在_lppMAPIError_中。</span><span class="sxs-lookup"><span data-stu-id="67f86-129">In this situation, a pointer to NULL is returned in  _lppMAPIError_ instead.</span></span> 
  
<span data-ttu-id="67f86-130">有关**GetLastError**方法的详细信息，请参阅[使用扩展的错误](mapi-extended-errors.md)。</span><span class="sxs-lookup"><span data-stu-id="67f86-130">For more information about the **GetLastError** method, see [Using Extended Errors](mapi-extended-errors.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="67f86-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="67f86-131">See also</span></span>



[<span data-ttu-id="67f86-132">MAPIERROR</span><span class="sxs-lookup"><span data-stu-id="67f86-132">MAPIERROR</span></span>](mapierror.md)
  
[<span data-ttu-id="67f86-133">MAPIFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="67f86-133">MAPIFreeBuffer</span></span>](mapifreebuffer.md)
  
[<span data-ttu-id="67f86-134">IProviderAdmin : IUnknown</span><span class="sxs-lookup"><span data-stu-id="67f86-134">IProviderAdmin : IUnknown</span></span>](iprovideradminiunknown.md)

