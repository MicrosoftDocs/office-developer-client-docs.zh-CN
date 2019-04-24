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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32326563"
---
# <a name="imapisupportregisterpreprocessor"></a><span data-ttu-id="3fe40-103">IMAPISupport::RegisterPreprocessor</span><span class="sxs-lookup"><span data-stu-id="3fe40-103">IMAPISupport::RegisterPreprocessor</span></span>

  
  
<span data-ttu-id="3fe40-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="3fe40-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="3fe40-105">注册传输提供程序的预处理器函数 (符合[PreprocessMessage](preprocessmessage.md)原型的函数)。</span><span class="sxs-lookup"><span data-stu-id="3fe40-105">Registers a transport provider's preprocessor function (a function that conforms to the [PreprocessMessage](preprocessmessage.md) prototype).</span></span> 
  
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

## <a name="parameters"></a><span data-ttu-id="3fe40-106">参数</span><span class="sxs-lookup"><span data-stu-id="3fe40-106">Parameters</span></span>

 <span data-ttu-id="3fe40-107">_lpMuid_</span><span class="sxs-lookup"><span data-stu-id="3fe40-107">_lpMuid_</span></span>
  
> <span data-ttu-id="3fe40-108">实时指向[MAPIUID](mapiuid.md)结构的指针, 该结构包含预处理器函数所处理的标识符。</span><span class="sxs-lookup"><span data-stu-id="3fe40-108">[in] A pointer to the [MAPIUID](mapiuid.md) structure that contains the identifier that the preprocessor function handles.</span></span> <span data-ttu-id="3fe40-109">_lpMuid_参数可以为 NULL。</span><span class="sxs-lookup"><span data-stu-id="3fe40-109">The  _lpMuid_ parameter can be NULL.</span></span> 
    
 <span data-ttu-id="3fe40-110">_lpszAdrType_</span><span class="sxs-lookup"><span data-stu-id="3fe40-110">_lpszAdrType_</span></span>
  
> <span data-ttu-id="3fe40-111">实时指向函数所运行的邮件的地址类型的指针, 例如传真、SMTP 或 X500。</span><span class="sxs-lookup"><span data-stu-id="3fe40-111">[in] A pointer to the address type for the messages the function operates on, such as FAX, SMTP, or X500.</span></span> <span data-ttu-id="3fe40-112">_lpszAdrType_参数可以为 NULL。</span><span class="sxs-lookup"><span data-stu-id="3fe40-112">The  _lpszAdrType_ parameter can be NULL.</span></span> 
    
 <span data-ttu-id="3fe40-113">_lpszDLLName_</span><span class="sxs-lookup"><span data-stu-id="3fe40-113">_lpszDLLName_</span></span>
  
> <span data-ttu-id="3fe40-114">实时指向包含预处理器函数入口点的动态链接库 (DLL) 名称的指针。</span><span class="sxs-lookup"><span data-stu-id="3fe40-114">[in] A pointer to the name of the dynamic-link library (DLL) that contains the entry point for the preprocessor function.</span></span>
    
 <span data-ttu-id="3fe40-115">_lpszPreprocess_</span><span class="sxs-lookup"><span data-stu-id="3fe40-115">_lpszPreprocess_</span></span>
  
> <span data-ttu-id="3fe40-116">实时指向预处理器函数名称的指针。</span><span class="sxs-lookup"><span data-stu-id="3fe40-116">[in] A pointer to the name of the preprocessor function.</span></span> <span data-ttu-id="3fe40-117">_lpszPreprocess_参数可以为 NULL。</span><span class="sxs-lookup"><span data-stu-id="3fe40-117">The  _lpszPreprocess_ parameter can be NULL.</span></span> 
    
 <span data-ttu-id="3fe40-118">_lpszRemovePreprocessInfo_</span><span class="sxs-lookup"><span data-stu-id="3fe40-118">_lpszRemovePreprocessInfo_</span></span>
  
> <span data-ttu-id="3fe40-119">实时指向删除预处理器信息的函数名称的指针 (符合[RemovePreprocessInfo](removepreprocessinfo.md)原型的函数)。</span><span class="sxs-lookup"><span data-stu-id="3fe40-119">[in] A pointer to the name of the function that removes preprocessor information (a function that conforms to the [RemovePreprocessInfo](removepreprocessinfo.md) prototype).</span></span> <span data-ttu-id="3fe40-120">_lpszRemovePreprocessInfo_参数可以为 NULL。</span><span class="sxs-lookup"><span data-stu-id="3fe40-120">The  _lpszRemovePreprocessInfo_ parameter can be NULL.</span></span> 
    
 <span data-ttu-id="3fe40-121">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="3fe40-121">_ulFlags_</span></span>
  
> <span data-ttu-id="3fe40-122">保留必须为零。</span><span class="sxs-lookup"><span data-stu-id="3fe40-122">Reserved; must be zero.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="3fe40-123">返回值</span><span class="sxs-lookup"><span data-stu-id="3fe40-123">Return value</span></span>

<span data-ttu-id="3fe40-124">S_OK</span><span class="sxs-lookup"><span data-stu-id="3fe40-124">S_OK</span></span> 
  
> <span data-ttu-id="3fe40-125">已成功注册预处理器函数。</span><span class="sxs-lookup"><span data-stu-id="3fe40-125">The preprocessor function was successfully registered.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="3fe40-126">注解</span><span class="sxs-lookup"><span data-stu-id="3fe40-126">Remarks</span></span>

<span data-ttu-id="3fe40-127">仅为传输提供程序支持对象实现了**IMAPISupport:: RegisterPreprocessor**方法。</span><span class="sxs-lookup"><span data-stu-id="3fe40-127">The **IMAPISupport::RegisterPreprocessor** method is implemented for transport provider support objects only.</span></span> <span data-ttu-id="3fe40-128">传输提供程序调用**RegisterPreprocessor**以注册预处理器函数 (符合[PreprocessMessage](preprocessmessage.md)原型的函数)。</span><span class="sxs-lookup"><span data-stu-id="3fe40-128">Transport providers call **RegisterPreprocessor** to register a preprocessor function (a function that conforms to the [PreprocessMessage](preprocessmessage.md) prototype).</span></span> <span data-ttu-id="3fe40-129">预处理器函数必须先注册, 然后 MAPI 后台处理程序才能调用它。</span><span class="sxs-lookup"><span data-stu-id="3fe40-129">A preprocessor function must be registered before the MAPI spooler can call it.</span></span> 
  
<span data-ttu-id="3fe40-130">_lpszPreprocess_、 _lpszRemovePreprocessInfo_和_lpszDLLName_参数都应指向可与 Win32 **GetProcAddress**函数的调用结合使用的字符串, 从而允许预处理器 DLL要正确调用的入口点。</span><span class="sxs-lookup"><span data-stu-id="3fe40-130">The  _lpszPreprocess_,  _lpszRemovePreprocessInfo_, and  _lpszDLLName_ parameters should all point to strings that can be used in conjunction with calls to the Win32 **GetProcAddress** function, allowing the preprocessor's DLL entry point to be called correctly.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="3fe40-131">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="3fe40-131">Notes to callers</span></span>

<span data-ttu-id="3fe40-132">对 preprocessors 的调用特定于传输提供程序的顺序。</span><span class="sxs-lookup"><span data-stu-id="3fe40-132">Calls to preprocessors are specific to transport provider order.</span></span> <span data-ttu-id="3fe40-133">这意味着, 如果您的提供程序前面的另一个传输提供程序能够处理邮件, 则不会为该邮件调用预处理程序函数。</span><span class="sxs-lookup"><span data-stu-id="3fe40-133">This means that if another transport provider ahead of your provider is able to handle a message, your preprocessor function will not be called for that message.</span></span> <span data-ttu-id="3fe40-134">将仅调用您要处理的邮件的预处理器函数。</span><span class="sxs-lookup"><span data-stu-id="3fe40-134">Your preprocessor function will be called only for messages that you will handle.</span></span>
  
<span data-ttu-id="3fe40-135">您可以编写预处理器函数来处理存储在[MAPIUID](mapiuid.md)结构或地址类型中的特定标识符。</span><span class="sxs-lookup"><span data-stu-id="3fe40-135">You can write preprocessor functions to handle either a specific identifier stored in a [MAPIUID](mapiuid.md) structure or a type of address.</span></span> <span data-ttu-id="3fe40-136">如果在_lpMuid_参数中指定了**MAPIUID**结构, 并在_lpszAdrType_参数中指定了地址类型, 则将为与**MAPIUID**或地址类型匹配的邮件收件人调用函数。</span><span class="sxs-lookup"><span data-stu-id="3fe40-136">If you specify both a **MAPIUID** structure in the  _lpMuid_ parameter and an address type in the  _lpszAdrType_ parameter, your function will be called for message recipients that match either the **MAPIUID** or the address type.</span></span> <span data-ttu-id="3fe40-137">如果_lpMuid_为 NULL 且_lpszAdrType_为非 NULL, 则仅对其地址与_lpszAdrType_指向的类型相匹配的收件人调用函数。</span><span class="sxs-lookup"><span data-stu-id="3fe40-137">If  _lpMuid_ is NULL and  _lpszAdrType_ is non-NULL, your function will be called only for recipients that have an address that matches the type pointed to by  _lpszAdrType_.</span></span> <span data-ttu-id="3fe40-138">如果_lpMuid_为非 null, 并且_lpszAdrType_为 null, 则将为匹配**MAPIUID**的收件人调用您的函数, 而不考虑其地址类型。</span><span class="sxs-lookup"><span data-stu-id="3fe40-138">If  _lpMuid_ is non-NULL and  _lpszAdrType_ is NULL, your function will be called for recipients that match **MAPIUID**, regardless of their address type.</span></span> <span data-ttu-id="3fe40-139">如果两者都为 NULL, 则为邮件的所有收件人调用函数。</span><span class="sxs-lookup"><span data-stu-id="3fe40-139">If both are NULL, your function is called for all recipients of the message.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="3fe40-140">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3fe40-140">See also</span></span>



[<span data-ttu-id="3fe40-141">MAPIUID</span><span class="sxs-lookup"><span data-stu-id="3fe40-141">MAPIUID</span></span>](mapiuid.md)
  
[<span data-ttu-id="3fe40-142">PreprocessMessage</span><span class="sxs-lookup"><span data-stu-id="3fe40-142">PreprocessMessage</span></span>](preprocessmessage.md)
  
[<span data-ttu-id="3fe40-143">RemovePreprocessInfo</span><span class="sxs-lookup"><span data-stu-id="3fe40-143">RemovePreprocessInfo</span></span>](removepreprocessinfo.md)
  
[<span data-ttu-id="3fe40-144">IMAPISupport : IUnknown</span><span class="sxs-lookup"><span data-stu-id="3fe40-144">IMAPISupport : IUnknown</span></span>](imapisupportiunknown.md)

