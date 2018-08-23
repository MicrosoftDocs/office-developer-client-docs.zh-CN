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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 87f5e3f159542359f614a6ab698e6f06a2faf41a
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22567914"
---
# <a name="imapisupportregisterpreprocessor"></a><span data-ttu-id="5f94d-103">IMAPISupport::RegisterPreprocessor</span><span class="sxs-lookup"><span data-stu-id="5f94d-103">IMAPISupport::RegisterPreprocessor</span></span>

  
  
<span data-ttu-id="5f94d-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="5f94d-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="5f94d-105">注册传输提供程序的预处理器函数 （符合[PreprocessMessage](preprocessmessage.md)原型函数）。</span><span class="sxs-lookup"><span data-stu-id="5f94d-105">Registers a transport provider's preprocessor function (a function that conforms to the [PreprocessMessage](preprocessmessage.md) prototype).</span></span> 
  
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

## <a name="parameters"></a><span data-ttu-id="5f94d-106">参数</span><span class="sxs-lookup"><span data-stu-id="5f94d-106">Parameters</span></span>

 <span data-ttu-id="5f94d-107">_lpMuid_</span><span class="sxs-lookup"><span data-stu-id="5f94d-107">_lpMuid_</span></span>
  
> <span data-ttu-id="5f94d-108">[in]一个指向[MAPIUID](mapiuid.md)结构，其中包含预处理器的函数处理的标识符。</span><span class="sxs-lookup"><span data-stu-id="5f94d-108">[in] A pointer to the [MAPIUID](mapiuid.md) structure that contains the identifier that the preprocessor function handles.</span></span> <span data-ttu-id="5f94d-109">_LpMuid_参数可以是 NULL。</span><span class="sxs-lookup"><span data-stu-id="5f94d-109">The  _lpMuid_ parameter can be NULL.</span></span> 
    
 <span data-ttu-id="5f94d-110">_lpszAdrType_</span><span class="sxs-lookup"><span data-stu-id="5f94d-110">_lpszAdrType_</span></span>
  
> <span data-ttu-id="5f94d-111">[in]函数如传真、 SMTP 或 X500 的操作，一个指向邮件的地址类型。</span><span class="sxs-lookup"><span data-stu-id="5f94d-111">[in] A pointer to the address type for the messages the function operates on, such as FAX, SMTP, or X500.</span></span> <span data-ttu-id="5f94d-112">_LpszAdrType_参数可以是 NULL。</span><span class="sxs-lookup"><span data-stu-id="5f94d-112">The  _lpszAdrType_ parameter can be NULL.</span></span> 
    
 <span data-ttu-id="5f94d-113">_lpszDLLName_</span><span class="sxs-lookup"><span data-stu-id="5f94d-113">_lpszDLLName_</span></span>
  
> <span data-ttu-id="5f94d-114">[in]一个指向包含预处理器函数的入口点的动态链接库 (DLL) 的名称。</span><span class="sxs-lookup"><span data-stu-id="5f94d-114">[in] A pointer to the name of the dynamic-link library (DLL) that contains the entry point for the preprocessor function.</span></span>
    
 <span data-ttu-id="5f94d-115">_lpszPreprocess_</span><span class="sxs-lookup"><span data-stu-id="5f94d-115">_lpszPreprocess_</span></span>
  
> <span data-ttu-id="5f94d-116">[in]一个指向预处理器函数的名称。</span><span class="sxs-lookup"><span data-stu-id="5f94d-116">[in] A pointer to the name of the preprocessor function.</span></span> <span data-ttu-id="5f94d-117">_LpszPreprocess_参数可以是 NULL。</span><span class="sxs-lookup"><span data-stu-id="5f94d-117">The  _lpszPreprocess_ parameter can be NULL.</span></span> 
    
 <span data-ttu-id="5f94d-118">_lpszRemovePreprocessInfo_</span><span class="sxs-lookup"><span data-stu-id="5f94d-118">_lpszRemovePreprocessInfo_</span></span>
  
> <span data-ttu-id="5f94d-119">[in]一个指向删除预处理器信息 （符合[RemovePreprocessInfo](removepreprocessinfo.md)原型函数） 函数的名称。</span><span class="sxs-lookup"><span data-stu-id="5f94d-119">[in] A pointer to the name of the function that removes preprocessor information (a function that conforms to the [RemovePreprocessInfo](removepreprocessinfo.md) prototype).</span></span> <span data-ttu-id="5f94d-120">_LpszRemovePreprocessInfo_参数可以是 NULL。</span><span class="sxs-lookup"><span data-stu-id="5f94d-120">The  _lpszRemovePreprocessInfo_ parameter can be NULL.</span></span> 
    
 <span data-ttu-id="5f94d-121">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="5f94d-121">_ulFlags_</span></span>
  
> <span data-ttu-id="5f94d-122">保留;必须为零。</span><span class="sxs-lookup"><span data-stu-id="5f94d-122">Reserved; must be zero.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="5f94d-123">返回值</span><span class="sxs-lookup"><span data-stu-id="5f94d-123">Return value</span></span>

<span data-ttu-id="5f94d-124">S_OK</span><span class="sxs-lookup"><span data-stu-id="5f94d-124">S_OK</span></span> 
  
> <span data-ttu-id="5f94d-125">预处理器函数已成功注册。</span><span class="sxs-lookup"><span data-stu-id="5f94d-125">The preprocessor function was successfully registered.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="5f94d-126">注解</span><span class="sxs-lookup"><span data-stu-id="5f94d-126">Remarks</span></span>

<span data-ttu-id="5f94d-127">对于传输提供程序支持对象仅实现**IMAPISupport::RegisterPreprocessor**方法。</span><span class="sxs-lookup"><span data-stu-id="5f94d-127">The **IMAPISupport::RegisterPreprocessor** method is implemented for transport provider support objects only.</span></span> <span data-ttu-id="5f94d-128">传输提供程序调用**RegisterPreprocessor**注册预处理器函数 （符合[PreprocessMessage](preprocessmessage.md)原型的函数）。</span><span class="sxs-lookup"><span data-stu-id="5f94d-128">Transport providers call **RegisterPreprocessor** to register a preprocessor function (a function that conforms to the [PreprocessMessage](preprocessmessage.md) prototype).</span></span> <span data-ttu-id="5f94d-129">MAPI 后台处理程序可调用它之前，必须注册预处理器函数。</span><span class="sxs-lookup"><span data-stu-id="5f94d-129">A preprocessor function must be registered before the MAPI spooler can call it.</span></span> 
  
<span data-ttu-id="5f94d-130">_LpszPreprocess_、 _lpszRemovePreprocessInfo_和_lpszDLLName_参数应指向可以与呼叫允许预处理器的 DLL 的 Win32 **GetProcAddress**函数结合使用的字符串正确调用入口点。</span><span class="sxs-lookup"><span data-stu-id="5f94d-130">The  _lpszPreprocess_,  _lpszRemovePreprocessInfo_, and  _lpszDLLName_ parameters should all point to strings that can be used in conjunction with calls to the Win32 **GetProcAddress** function, allowing the preprocessor's DLL entry point to be called correctly.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="5f94d-131">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="5f94d-131">Notes to callers</span></span>

<span data-ttu-id="5f94d-132">调用 preprocessors 是特定于传输提供程序的顺序。</span><span class="sxs-lookup"><span data-stu-id="5f94d-132">Calls to preprocessors are specific to transport provider order.</span></span> <span data-ttu-id="5f94d-133">这意味着您的提供商之前的另一个传输提供程序是能够处理一条消息，如果您预处理器函数将不会调用该邮件。</span><span class="sxs-lookup"><span data-stu-id="5f94d-133">This means that if another transport provider ahead of your provider is able to handle a message, your preprocessor function will not be called for that message.</span></span> <span data-ttu-id="5f94d-134">只对将处理的消息，将调用您预处理器函数。</span><span class="sxs-lookup"><span data-stu-id="5f94d-134">Your preprocessor function will be called only for messages that you will handle.</span></span>
  
<span data-ttu-id="5f94d-135">您可以编写预处理器函数来处理存储在[MAPIUID](mapiuid.md)结构或类型的地址中的任一一个特定的标识符。</span><span class="sxs-lookup"><span data-stu-id="5f94d-135">You can write preprocessor functions to handle either a specific identifier stored in a [MAPIUID](mapiuid.md) structure or a type of address.</span></span> <span data-ttu-id="5f94d-136">如果指定这两个**MAPIUID**结构_lpMuid_参数和_lpszAdrType_参数中的地址类型，您的函数将调用**MAPIUID**或地址类型相匹配的邮件收件人。</span><span class="sxs-lookup"><span data-stu-id="5f94d-136">If you specify both a **MAPIUID** structure in the  _lpMuid_ parameter and an address type in the  _lpszAdrType_ parameter, your function will be called for message recipients that match either the **MAPIUID** or the address type.</span></span> <span data-ttu-id="5f94d-137">如果_lpszAdrType_为非 NULL _lpMuid_为 NULL，将只为收件人的地址所指的_lpszAdrType_的类型相匹配的调用您函数。</span><span class="sxs-lookup"><span data-stu-id="5f94d-137">If  _lpMuid_ is NULL and  _lpszAdrType_ is non-NULL, your function will be called only for recipients that have an address that matches the type pointed to by  _lpszAdrType_.</span></span> <span data-ttu-id="5f94d-138">_LpMuid_非空并且_lpszAdrType_为 NULL，如果您的函数将调用的匹配**MAPIUID**，无论其地址类型的收件人。</span><span class="sxs-lookup"><span data-stu-id="5f94d-138">If  _lpMuid_ is non-NULL and  _lpszAdrType_ is NULL, your function will be called for recipients that match **MAPIUID**, regardless of their address type.</span></span> <span data-ttu-id="5f94d-139">如果二者均为空，函数调用的所有收件人的邮件。</span><span class="sxs-lookup"><span data-stu-id="5f94d-139">If both are NULL, your function is called for all recipients of the message.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="5f94d-140">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5f94d-140">See also</span></span>



[<span data-ttu-id="5f94d-141">MAPIUID</span><span class="sxs-lookup"><span data-stu-id="5f94d-141">MAPIUID</span></span>](mapiuid.md)
  
[<span data-ttu-id="5f94d-142">PreprocessMessage</span><span class="sxs-lookup"><span data-stu-id="5f94d-142">PreprocessMessage</span></span>](preprocessmessage.md)
  
[<span data-ttu-id="5f94d-143">RemovePreprocessInfo</span><span class="sxs-lookup"><span data-stu-id="5f94d-143">RemovePreprocessInfo</span></span>](removepreprocessinfo.md)
  
[<span data-ttu-id="5f94d-144">IMAPISupport : IUnknown</span><span class="sxs-lookup"><span data-stu-id="5f94d-144">IMAPISupport : IUnknown</span></span>](imapisupportiunknown.md)

