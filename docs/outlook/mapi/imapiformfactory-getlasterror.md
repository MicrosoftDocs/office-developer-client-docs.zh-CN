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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 2c83f7788d9c01ab02f1a2bc39a35abe2c5a21c5
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33417005"
---
# <a name="imapiformfactorygetlasterror"></a><span data-ttu-id="a3a65-103">IMAPIFormFactory::GetLastError</span><span class="sxs-lookup"><span data-stu-id="a3a65-103">IMAPIFormFactory::GetLastError</span></span>

  
  
<span data-ttu-id="a3a65-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="a3a65-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="a3a65-105">返回一个[MAPIERROR](mapierror.md)结构, 该结构包含上一个错误发生于表单工厂对象的相关信息。</span><span class="sxs-lookup"><span data-stu-id="a3a65-105">Returns a [MAPIERROR](mapierror.md) structure that contains information about the previous error occurring to the form factory object.</span></span> 
  
```cpp
HRESULT GetLastError(
  HRESULT hResult,
  ULONG ulFlags,
  LPMAPIERROR FAR * lppMAPIError
);
```

## <a name="parameters"></a><span data-ttu-id="a3a65-106">参数</span><span class="sxs-lookup"><span data-stu-id="a3a65-106">Parameters</span></span>

 <span data-ttu-id="a3a65-107">_hResult_</span><span class="sxs-lookup"><span data-stu-id="a3a65-107">_hResult_</span></span>
  
> <span data-ttu-id="a3a65-108">实时一个 HRESULT 数据类型, 其中包含在上一方法调用中生成的错误值。</span><span class="sxs-lookup"><span data-stu-id="a3a65-108">[in] An HRESULT data type that contains the error value generated in the previous method call.</span></span>
    
 <span data-ttu-id="a3a65-109">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="a3a65-109">_ulFlags_</span></span>
  
> <span data-ttu-id="a3a65-110">实时用于控制返回的字符串类型的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="a3a65-110">[in] A bitmask of flags that controls the type of strings returned.</span></span> <span data-ttu-id="a3a65-111">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="a3a65-111">The following flag can be set:</span></span> 
    
<span data-ttu-id="a3a65-112">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="a3a65-112">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="a3a65-113">在_lppMAPIError_参数中返回的**MAPIERROR**结构中的字符串采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="a3a65-113">The strings in the **MAPIERROR** structure returned in the  _lppMAPIError_ parameter are in Unicode format.</span></span> <span data-ttu-id="a3a65-114">如果未设置 MAPI_UNICODE 标志, 则字符串将采用 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="a3a65-114">If the MAPI_UNICODE flag is not set, the strings are in ANSI format.</span></span> 
    
 <span data-ttu-id="a3a65-115">_lppMAPIError_</span><span class="sxs-lookup"><span data-stu-id="a3a65-115">_lppMAPIError_</span></span>
  
> <span data-ttu-id="a3a65-116">排除指向包含错误的版本、组件和上下文信息的返回的**MAPIERROR**结构的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="a3a65-116">[out] A pointer to a pointer to the returned **MAPIERROR** structure that contains version, component, and context information for the error.</span></span> <span data-ttu-id="a3a65-117">如果没有要返回的**MAPIERROR**结构, 则可以将此参数设置为 NULL。</span><span class="sxs-lookup"><span data-stu-id="a3a65-117">This parameter can be set to NULL if there is no **MAPIERROR** structure to return.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="a3a65-118">返回值</span><span class="sxs-lookup"><span data-stu-id="a3a65-118">Return value</span></span>

<span data-ttu-id="a3a65-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="a3a65-119">S_OK</span></span> 
  
> <span data-ttu-id="a3a65-120">调用成功, 并返回了所需的值或值。</span><span class="sxs-lookup"><span data-stu-id="a3a65-120">The call succeeded and has returned the expected value or values.</span></span>
    
<span data-ttu-id="a3a65-121">MAPI_E_BAD_CHARWIDTH</span><span class="sxs-lookup"><span data-stu-id="a3a65-121">MAPI_E_BAD_CHARWIDTH</span></span> 
  
> <span data-ttu-id="a3a65-122">设置了 MAPI_UNICODE 标志, 且**getlasterror**不支持 unicode, 或者未设置 MAPI_UNICODE, 且**GetLastError**仅支持 UNICODE。</span><span class="sxs-lookup"><span data-stu-id="a3a65-122">Either the MAPI_UNICODE flag was set and **GetLastError** does not support Unicode, or MAPI_UNICODE was not set and **GetLastError** supports only Unicode.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="a3a65-123">说明</span><span class="sxs-lookup"><span data-stu-id="a3a65-123">Remarks</span></span>

<span data-ttu-id="a3a65-124">**IMAPIFormFactory:: GetLastError**方法提供有关失败的上一个方法调用的信息。</span><span class="sxs-lookup"><span data-stu-id="a3a65-124">The **IMAPIFormFactory::GetLastError** method supplies information about a prior method call that failed.</span></span> <span data-ttu-id="a3a65-125">通过在对话框中包含**MAPIERROR**结构中的数据, 呼叫者可以向其用户提供有关错误的详细信息。</span><span class="sxs-lookup"><span data-stu-id="a3a65-125">Callers can provide their users with detailed information about the error by including the data from the **MAPIERROR** structure in a dialog box.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="a3a65-126">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="a3a65-126">Notes to callers</span></span>

<span data-ttu-id="a3a65-127">如果 MAPI 返回 S_OK, 则可以使用_lppMAPIError_参数指向的**MAPIERROR**结构 (如果 MAPI 仅提供一个\*\*\*\* )。</span><span class="sxs-lookup"><span data-stu-id="a3a65-127">You can make use of the **MAPIERROR** structure pointed to by the  _lppMAPIError_ parameter if MAPI supplies one only if **GetLastError** returns S_OK.</span></span> <span data-ttu-id="a3a65-128">有时 MAPI 无法确定最后一个错误是什么, 或者没有更多要报告错误的内容。</span><span class="sxs-lookup"><span data-stu-id="a3a65-128">Sometimes MAPI cannot determine what the last error was or has nothing more to report about the error.</span></span> <span data-ttu-id="a3a65-129">在这种情况下, 将在_lppMAPIError_中返回指向 NULL 的指针。</span><span class="sxs-lookup"><span data-stu-id="a3a65-129">In this situation, a pointer to NULL is returned in  _lppMAPIError_ instead.</span></span> 
  
<span data-ttu-id="a3a65-130">有关**GetLastError**方法的详细信息, 请参阅[使用扩展错误](mapi-extended-errors.md)。</span><span class="sxs-lookup"><span data-stu-id="a3a65-130">For more information about the **GetLastError** method, see [Using Extended Errors](mapi-extended-errors.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a3a65-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a3a65-131">See also</span></span>



[<span data-ttu-id="a3a65-132">MAPIERROR</span><span class="sxs-lookup"><span data-stu-id="a3a65-132">MAPIERROR</span></span>](mapierror.md)
  
[<span data-ttu-id="a3a65-133">MAPIFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="a3a65-133">MAPIFreeBuffer</span></span>](mapifreebuffer.md)
  
[<span data-ttu-id="a3a65-134">IMAPIFormFactory : IUnknown</span><span class="sxs-lookup"><span data-stu-id="a3a65-134">IMAPIFormFactory : IUnknown</span></span>](imapiformfactoryiunknown.md)

