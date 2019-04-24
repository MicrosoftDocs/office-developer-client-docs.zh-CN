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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32360492"
---
# <a name="ulvalidateparms"></a><span data-ttu-id="034fa-103">UlValidateParms</span><span class="sxs-lookup"><span data-stu-id="034fa-103">UlValidateParms</span></span>

  
  
<span data-ttu-id="034fa-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="034fa-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="034fa-105">调用内部函数以检查客户端应用程序已传递给服务提供程序和 MAPI 的参数。</span><span class="sxs-lookup"><span data-stu-id="034fa-105">Calls an internal function to check the parameters client applications have passed to service providers and MAPI.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="034fa-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="034fa-106">Header file:</span></span>  <br/> |<span data-ttu-id="034fa-107">Mapival.h</span><span class="sxs-lookup"><span data-stu-id="034fa-107">Mapival.h</span></span>  <br/> |
|<span data-ttu-id="034fa-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="034fa-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="034fa-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="034fa-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="034fa-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="034fa-110">Called by:</span></span>  <br/> |<span data-ttu-id="034fa-111">服务提供程序</span><span class="sxs-lookup"><span data-stu-id="034fa-111">Service providers</span></span>  <br/> |
   
```cpp
HRESULT UlValidateParms(
  METHODS eMethod,
  LPVOID First
);
```

## <a name="parameters"></a><span data-ttu-id="034fa-112">参数</span><span class="sxs-lookup"><span data-stu-id="034fa-112">Parameters</span></span>

 <span data-ttu-id="034fa-113">_eMethod_</span><span class="sxs-lookup"><span data-stu-id="034fa-113">_eMethod_</span></span>
  
> <span data-ttu-id="034fa-114">实时通过枚举指定要验证的方法。</span><span class="sxs-lookup"><span data-stu-id="034fa-114">[in] Specifies, by enumeration, the method to validate.</span></span> 
    
 <span data-ttu-id="034fa-115">_第一_</span><span class="sxs-lookup"><span data-stu-id="034fa-115">_First_</span></span>
  
> <span data-ttu-id="034fa-116">实时指向堆栈上第一个参数的指针。</span><span class="sxs-lookup"><span data-stu-id="034fa-116">[in] Pointer to the first argument on the stack.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="034fa-117">返回值</span><span class="sxs-lookup"><span data-stu-id="034fa-117">Return value</span></span>

<span data-ttu-id="034fa-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="034fa-118">S_OK</span></span> 
  
> <span data-ttu-id="034fa-119">调用成功, 并返回了所需的值或值。</span><span class="sxs-lookup"><span data-stu-id="034fa-119">The call succeeded and has returned the expected value or values.</span></span> 
    
<span data-ttu-id="034fa-120">MAPI_E_CALL_FAILED</span><span class="sxs-lookup"><span data-stu-id="034fa-120">MAPI_E_CALL_FAILED</span></span> 
  
> <span data-ttu-id="034fa-121">错误阻止操作完成。</span><span class="sxs-lookup"><span data-stu-id="034fa-121">An error prevented the operation from completing.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="034fa-122">注解</span><span class="sxs-lookup"><span data-stu-id="034fa-122">Remarks</span></span>

<span data-ttu-id="034fa-123">假定在 MAPI 和服务提供程序之间传递的参数是正确的, 并且仅使用[CheckParms](checkparms.md)宏进行调试验证。</span><span class="sxs-lookup"><span data-stu-id="034fa-123">Parameters passed between MAPI and service providers are assumed to be correct and undergo only debug validation with the [CheckParms](checkparms.md) macro.</span></span> <span data-ttu-id="034fa-124">提供程序应检查客户端应用程序传入的所有参数, 但客户端应假定 MAPI 和提供程序参数正确。</span><span class="sxs-lookup"><span data-stu-id="034fa-124">Providers should check all parameters passed in by client applications, but clients should assume that MAPI and provider parameters are correct.</span></span> <span data-ttu-id="034fa-125">使用**HR_FAILED**宏可测试返回值。</span><span class="sxs-lookup"><span data-stu-id="034fa-125">Use the **HR_FAILED** macro to test return values.</span></span> 
  
<span data-ttu-id="034fa-126">**UlValidateParms**宏的调用方式取决于调用代码是否为 c 或 c + +。</span><span class="sxs-lookup"><span data-stu-id="034fa-126">The **UlValidateParms** macro is called differently depending on whether the calling code is C or C++.</span></span> <span data-ttu-id="034fa-127">此宏用于验证几个**IUnknown**和 MAPI 方法的参数, 这些方法返回 ULONG 而不是 HRESULT 值;[ValidateParms](validateparms.md)宏适用于所有其他宏。</span><span class="sxs-lookup"><span data-stu-id="034fa-127">This macro is used to validate parameters for the few **IUnknown** and MAPI methods that return ULONG instead of HRESULT values; the [ValidateParms](validateparms.md) macro works for all others.</span></span> 
  

