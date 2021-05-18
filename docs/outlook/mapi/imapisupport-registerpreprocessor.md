---
title: IMAPISupportRegisterPreprocessor
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISupport.RegisterPreprocessor
api_type:
- COM
ms.assetid: 9b5659ab-2b49-41ab-92ce-ca343e35d670
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 58215de6cc4e9e68386f8f017839752acc6e1753
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33404895"
---
# <a name="imapisupportregisterpreprocessor"></a><span data-ttu-id="49bff-103">IMAPISupport::RegisterPreprocessor</span><span class="sxs-lookup"><span data-stu-id="49bff-103">IMAPISupport::RegisterPreprocessor</span></span>

  
  
<span data-ttu-id="49bff-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="49bff-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="49bff-105">在符合 [PreprocessMessage](preprocessmessage.md) 原型模型 (注册传输提供程序的预处理器) 。</span><span class="sxs-lookup"><span data-stu-id="49bff-105">Registers a transport provider's preprocessor function (a function that conforms to the [PreprocessMessage](preprocessmessage.md) prototype).</span></span> 
  
```cpp
HRESULT RegisterPreprocessor(
LPMAPIUID lpMuid,
LPSTR lpszAdrType,
LPSTR lpszDLLName,
LPSTR lpszPreprocess,
LPSTR lpszRemovePreprocessInfo,
ULONG ulFlags
);
```

## <a name="parameters"></a><span data-ttu-id="49bff-106">参数</span><span class="sxs-lookup"><span data-stu-id="49bff-106">Parameters</span></span>

 <span data-ttu-id="49bff-107">_lpMuid_</span><span class="sxs-lookup"><span data-stu-id="49bff-107">_lpMuid_</span></span>
  
> <span data-ttu-id="49bff-108">[in]指向 [MAPIUID](mapiuid.md) 结构的指针，该结构包含预处理器函数处理的标识符。</span><span class="sxs-lookup"><span data-stu-id="49bff-108">[in] A pointer to the [MAPIUID](mapiuid.md) structure that contains the identifier that the preprocessor function handles.</span></span> <span data-ttu-id="49bff-109">_lpMuid_ 参数可以是 NULL。</span><span class="sxs-lookup"><span data-stu-id="49bff-109">The  _lpMuid_ parameter can be NULL.</span></span> 
    
 <span data-ttu-id="49bff-110">_lpszAdrType_</span><span class="sxs-lookup"><span data-stu-id="49bff-110">_lpszAdrType_</span></span>
  
> <span data-ttu-id="49bff-111">[in]指向函数所操作的邮件的地址类型的指针，例如 FAX、SMTP 或 X500。</span><span class="sxs-lookup"><span data-stu-id="49bff-111">[in] A pointer to the address type for the messages the function operates on, such as FAX, SMTP, or X500.</span></span> <span data-ttu-id="49bff-112">_lpszAdrType_ 参数可以是 NULL。</span><span class="sxs-lookup"><span data-stu-id="49bff-112">The  _lpszAdrType_ parameter can be NULL.</span></span> 
    
 <span data-ttu-id="49bff-113">_lpszDLLName_</span><span class="sxs-lookup"><span data-stu-id="49bff-113">_lpszDLLName_</span></span>
  
> <span data-ttu-id="49bff-114">[in]指向动态链接库名称的指针 (DLL) ，其中包含预处理器函数的入口点。</span><span class="sxs-lookup"><span data-stu-id="49bff-114">[in] A pointer to the name of the dynamic-link library (DLL) that contains the entry point for the preprocessor function.</span></span>
    
 <span data-ttu-id="49bff-115">_lpszPreprocess_</span><span class="sxs-lookup"><span data-stu-id="49bff-115">_lpszPreprocess_</span></span>
  
> <span data-ttu-id="49bff-116">[in]指向预处理器函数名称的指针。</span><span class="sxs-lookup"><span data-stu-id="49bff-116">[in] A pointer to the name of the preprocessor function.</span></span> <span data-ttu-id="49bff-117">_lpszPreprocess 参数_ 可以是 NULL。</span><span class="sxs-lookup"><span data-stu-id="49bff-117">The  _lpszPreprocess_ parameter can be NULL.</span></span> 
    
 <span data-ttu-id="49bff-118">_lpszRemovePreprocessInfo_</span><span class="sxs-lookup"><span data-stu-id="49bff-118">_lpszRemovePreprocessInfo_</span></span>
  
> <span data-ttu-id="49bff-119">[in]指向函数名称的指针，该名称将删除符合 [RemovePreprocessInfo](removepreprocessinfo.md) 原型 (函数的预处理器) 。</span><span class="sxs-lookup"><span data-stu-id="49bff-119">[in] A pointer to the name of the function that removes preprocessor information (a function that conforms to the [RemovePreprocessInfo](removepreprocessinfo.md) prototype).</span></span> <span data-ttu-id="49bff-120">_lpszRemovePreprocessInfo_ 参数可以是 NULL。</span><span class="sxs-lookup"><span data-stu-id="49bff-120">The  _lpszRemovePreprocessInfo_ parameter can be NULL.</span></span> 
    
 <span data-ttu-id="49bff-121">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="49bff-121">_ulFlags_</span></span>
  
> <span data-ttu-id="49bff-122">保留;必须为零。</span><span class="sxs-lookup"><span data-stu-id="49bff-122">Reserved; must be zero.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="49bff-123">返回值</span><span class="sxs-lookup"><span data-stu-id="49bff-123">Return value</span></span>

<span data-ttu-id="49bff-124">S_OK</span><span class="sxs-lookup"><span data-stu-id="49bff-124">S_OK</span></span> 
  
> <span data-ttu-id="49bff-125">预处理器函数已成功注册。</span><span class="sxs-lookup"><span data-stu-id="49bff-125">The preprocessor function was successfully registered.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="49bff-126">备注</span><span class="sxs-lookup"><span data-stu-id="49bff-126">Remarks</span></span>

<span data-ttu-id="49bff-127">**IMAPISupport：：RegisterPreprocessor** 方法仅为传输提供程序支持对象实现。</span><span class="sxs-lookup"><span data-stu-id="49bff-127">The **IMAPISupport::RegisterPreprocessor** method is implemented for transport provider support objects only.</span></span> <span data-ttu-id="49bff-128">传输提供程序调用 **RegisterPreprocessor** 以在符合 [PreprocessMessage](preprocessmessage.md) 原型 (的函数中注册预处理器) 。</span><span class="sxs-lookup"><span data-stu-id="49bff-128">Transport providers call **RegisterPreprocessor** to register a preprocessor function (a function that conforms to the [PreprocessMessage](preprocessmessage.md) prototype).</span></span> <span data-ttu-id="49bff-129">必须先注册预处理器函数，MAPI 后台处理程序才能调用它。</span><span class="sxs-lookup"><span data-stu-id="49bff-129">A preprocessor function must be registered before the MAPI spooler can call it.</span></span> 
  
<span data-ttu-id="49bff-130">_lpszPreprocess、lpszRemovePreprocessInfo_ 和 _lpszDLLName_ 参数都应指向可与 Win32 **GetProcAddress** 函数调用结合使用的字符串，从而允许正确调用预处理器的 DLL 入口点。 </span><span class="sxs-lookup"><span data-stu-id="49bff-130">The  _lpszPreprocess_,  _lpszRemovePreprocessInfo_, and  _lpszDLLName_ parameters should all point to strings that can be used in conjunction with calls to the Win32 **GetProcAddress** function, allowing the preprocessor's DLL entry point to be called correctly.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="49bff-131">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="49bff-131">Notes to callers</span></span>

<span data-ttu-id="49bff-132">对预处理器的调用特定于传输提供程序顺序。</span><span class="sxs-lookup"><span data-stu-id="49bff-132">Calls to preprocessors are specific to transport provider order.</span></span> <span data-ttu-id="49bff-133">这意味着，如果提供程序之前的另一个传输提供程序能够处理邮件，将不会为邮件调用预处理器函数。</span><span class="sxs-lookup"><span data-stu-id="49bff-133">This means that if another transport provider ahead of your provider is able to handle a message, your preprocessor function will not be called for that message.</span></span> <span data-ttu-id="49bff-134">将仅对将处理的邮件调用预处理器函数。</span><span class="sxs-lookup"><span data-stu-id="49bff-134">Your preprocessor function will be called only for messages that you will handle.</span></span>
  
<span data-ttu-id="49bff-135">你可以编写预处理器函数来处理 [MAPIUID](mapiuid.md) 结构中存储的特定标识符或地址类型。</span><span class="sxs-lookup"><span data-stu-id="49bff-135">You can write preprocessor functions to handle either a specific identifier stored in a [MAPIUID](mapiuid.md) structure or a type of address.</span></span> <span data-ttu-id="49bff-136">如果在 _lpMuid_ 参数中同时指定 **MAPIUID** 结构，在 _lpszAdrType_ 参数中指定地址类型，将调用与 **MAPIUID** 或地址类型匹配的邮件收件人的函数。</span><span class="sxs-lookup"><span data-stu-id="49bff-136">If you specify both a **MAPIUID** structure in the  _lpMuid_ parameter and an address type in the  _lpszAdrType_ parameter, your function will be called for message recipients that match either the **MAPIUID** or the address type.</span></span> <span data-ttu-id="49bff-137">如果  _lpMuid_ 为 NULL 且  _lpszAdrType_ 为非 NULL，则仅对地址与  _lpszAdrType_ 指向的类型匹配的收件人调用函数。</span><span class="sxs-lookup"><span data-stu-id="49bff-137">If  _lpMuid_ is NULL and  _lpszAdrType_ is non-NULL, your function will be called only for recipients that have an address that matches the type pointed to by  _lpszAdrType_.</span></span> <span data-ttu-id="49bff-138">如果  _lpMuid_ 为非 NULL 且  _lpszAdrType_ 为 NULL，则无论收件人的地址类型如何，都将为 **匹配 MAPIUID** 的收件人调用函数。</span><span class="sxs-lookup"><span data-stu-id="49bff-138">If  _lpMuid_ is non-NULL and  _lpszAdrType_ is NULL, your function will be called for recipients that match **MAPIUID**, regardless of their address type.</span></span> <span data-ttu-id="49bff-139">如果两者都是 NULL，则为邮件的所有收件人调用函数。</span><span class="sxs-lookup"><span data-stu-id="49bff-139">If both are NULL, your function is called for all recipients of the message.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="49bff-140">另请参阅</span><span class="sxs-lookup"><span data-stu-id="49bff-140">See also</span></span>



[<span data-ttu-id="49bff-141">MAPIUID</span><span class="sxs-lookup"><span data-stu-id="49bff-141">MAPIUID</span></span>](mapiuid.md)
  
[<span data-ttu-id="49bff-142">PreprocessMessage</span><span class="sxs-lookup"><span data-stu-id="49bff-142">PreprocessMessage</span></span>](preprocessmessage.md)
  
[<span data-ttu-id="49bff-143">RemovePreprocessInfo</span><span class="sxs-lookup"><span data-stu-id="49bff-143">RemovePreprocessInfo</span></span>](removepreprocessinfo.md)
  
[<span data-ttu-id="49bff-144">IMAPISupport : IUnknown</span><span class="sxs-lookup"><span data-stu-id="49bff-144">IMAPISupport : IUnknown</span></span>](imapisupportiunknown.md)

