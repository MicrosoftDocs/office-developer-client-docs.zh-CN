---
title: UlValidateParms
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.UlValidateParms
api_type:
- COM
ms.assetid: 02c66b46-1f01-43fb-832c-bac27aaae19f
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: e0cdcb92238dd4dffbcd6514e698e5511b05bf45
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33419609"
---
# <a name="ulvalidateparms"></a><span data-ttu-id="9b037-103">UlValidateParms</span><span class="sxs-lookup"><span data-stu-id="9b037-103">UlValidateParms</span></span>

  
  
<span data-ttu-id="9b037-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="9b037-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="9b037-105">调用内部函数以检查客户端应用程序已传递给服务提供商和 MAPI 的参数。</span><span class="sxs-lookup"><span data-stu-id="9b037-105">Calls an internal function to check the parameters client applications have passed to service providers and MAPI.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="9b037-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="9b037-106">Header file:</span></span>  <br/> |<span data-ttu-id="9b037-107">Mapival.h</span><span class="sxs-lookup"><span data-stu-id="9b037-107">Mapival.h</span></span>  <br/> |
|<span data-ttu-id="9b037-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="9b037-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="9b037-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="9b037-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="9b037-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="9b037-110">Called by:</span></span>  <br/> |<span data-ttu-id="9b037-111">服务提供程序</span><span class="sxs-lookup"><span data-stu-id="9b037-111">Service providers</span></span>  <br/> |
   
```cpp
HRESULT UlValidateParms(
  METHODS eMethod,
  LPVOID First
);
```

## <a name="parameters"></a><span data-ttu-id="9b037-112">参数</span><span class="sxs-lookup"><span data-stu-id="9b037-112">Parameters</span></span>

 <span data-ttu-id="9b037-113">_eMethod_</span><span class="sxs-lookup"><span data-stu-id="9b037-113">_eMethod_</span></span>
  
> <span data-ttu-id="9b037-114">[in]通过枚举指定要验证的方法。</span><span class="sxs-lookup"><span data-stu-id="9b037-114">[in] Specifies, by enumeration, the method to validate.</span></span> 
    
 <span data-ttu-id="9b037-115">_第一_</span><span class="sxs-lookup"><span data-stu-id="9b037-115">_First_</span></span>
  
> <span data-ttu-id="9b037-116">[in]指向堆栈上第一个参数的指针。</span><span class="sxs-lookup"><span data-stu-id="9b037-116">[in] Pointer to the first argument on the stack.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="9b037-117">返回值</span><span class="sxs-lookup"><span data-stu-id="9b037-117">Return value</span></span>

<span data-ttu-id="9b037-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="9b037-118">S_OK</span></span> 
  
> <span data-ttu-id="9b037-119">调用成功并返回了预期值。</span><span class="sxs-lookup"><span data-stu-id="9b037-119">The call succeeded and has returned the expected value or values.</span></span> 
    
<span data-ttu-id="9b037-120">MAPI_E_CALL_FAILED</span><span class="sxs-lookup"><span data-stu-id="9b037-120">MAPI_E_CALL_FAILED</span></span> 
  
> <span data-ttu-id="9b037-121">错误阻止了操作完成。</span><span class="sxs-lookup"><span data-stu-id="9b037-121">An error prevented the operation from completing.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="9b037-122">备注</span><span class="sxs-lookup"><span data-stu-id="9b037-122">Remarks</span></span>

<span data-ttu-id="9b037-123">在 MAPI 和服务提供商之间传递的参数被认为是正确的，并且只接受 [CheckParms 宏的调试](checkparms.md) 验证。</span><span class="sxs-lookup"><span data-stu-id="9b037-123">Parameters passed between MAPI and service providers are assumed to be correct and undergo only debug validation with the [CheckParms](checkparms.md) macro.</span></span> <span data-ttu-id="9b037-124">提供程序应检查客户端应用程序传入的所有参数，但客户端应假定 MAPI 和提供程序参数正确。</span><span class="sxs-lookup"><span data-stu-id="9b037-124">Providers should check all parameters passed in by client applications, but clients should assume that MAPI and provider parameters are correct.</span></span> <span data-ttu-id="9b037-125">使用 **HR_FAILED** 宏测试返回值。</span><span class="sxs-lookup"><span data-stu-id="9b037-125">Use the **HR_FAILED** macro to test return values.</span></span> 
  
<span data-ttu-id="9b037-126">根据调用代码是 C 还是 C++，调用 **UlValidateParms** 宏的方式不同。</span><span class="sxs-lookup"><span data-stu-id="9b037-126">The **UlValidateParms** macro is called differently depending on whether the calling code is C or C++.</span></span> <span data-ttu-id="9b037-127">此宏用于验证返回 ULONG（而不是 HRESULT 值）的一些 **IUnknown** 和 MAPI 方法的参数; [ValidateParms](validateparms.md) 宏适用于所有其他宏。</span><span class="sxs-lookup"><span data-stu-id="9b037-127">This macro is used to validate parameters for the few **IUnknown** and MAPI methods that return ULONG instead of HRESULT values; the [ValidateParms](validateparms.md) macro works for all others.</span></span> 
  

