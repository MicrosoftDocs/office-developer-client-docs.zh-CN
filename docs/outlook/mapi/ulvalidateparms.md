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
ms.openlocfilehash: b71d1f477435b4a9327b4156560d1aa2e6079536
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22578701"
---
# <a name="ulvalidateparms"></a><span data-ttu-id="a9788-103">UlValidateParms</span><span class="sxs-lookup"><span data-stu-id="a9788-103">UlValidateParms</span></span>

  
  
<span data-ttu-id="a9788-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="a9788-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="a9788-105">调用检查参数客户端应用程序已传递给服务提供商和 MAPI 内部函数。</span><span class="sxs-lookup"><span data-stu-id="a9788-105">Calls an internal function to check the parameters client applications have passed to service providers and MAPI.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="a9788-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="a9788-106">Header file:</span></span>  <br/> |<span data-ttu-id="a9788-107">Mapival.h</span><span class="sxs-lookup"><span data-stu-id="a9788-107">Mapival.h</span></span>  <br/> |
|<span data-ttu-id="a9788-108">通过实现：</span><span class="sxs-lookup"><span data-stu-id="a9788-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="a9788-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="a9788-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="a9788-110">调用：</span><span class="sxs-lookup"><span data-stu-id="a9788-110">Called by:</span></span>  <br/> |<span data-ttu-id="a9788-111">服务提供商</span><span class="sxs-lookup"><span data-stu-id="a9788-111">Service providers</span></span>  <br/> |
   
```cpp
HRESULT UlValidateParms(
  METHODS eMethod,
  LPVOID First
);
```

## <a name="parameters"></a><span data-ttu-id="a9788-112">参数</span><span class="sxs-lookup"><span data-stu-id="a9788-112">Parameters</span></span>

 <span data-ttu-id="a9788-113">_eMethod_</span><span class="sxs-lookup"><span data-stu-id="a9788-113">_eMethod_</span></span>
  
> <span data-ttu-id="a9788-114">[in]通过枚举，指定要验证的方法。</span><span class="sxs-lookup"><span data-stu-id="a9788-114">[in] Specifies, by enumeration, the method to validate.</span></span> 
    
 <span data-ttu-id="a9788-115">_第一_</span><span class="sxs-lookup"><span data-stu-id="a9788-115">_First_</span></span>
  
> <span data-ttu-id="a9788-116">[in]堆栈上第一个参数的指针。</span><span class="sxs-lookup"><span data-stu-id="a9788-116">[in] Pointer to the first argument on the stack.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="a9788-117">返回值</span><span class="sxs-lookup"><span data-stu-id="a9788-117">Return value</span></span>

<span data-ttu-id="a9788-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="a9788-118">S_OK</span></span> 
  
> <span data-ttu-id="a9788-119">呼叫成功或多个预期值返回。</span><span class="sxs-lookup"><span data-stu-id="a9788-119">The call succeeded and has returned the expected value or values.</span></span> 
    
<span data-ttu-id="a9788-120">MAPI_E_CALL_FAILED</span><span class="sxs-lookup"><span data-stu-id="a9788-120">MAPI_E_CALL_FAILED</span></span> 
  
> <span data-ttu-id="a9788-121">出现错误，无法完成操作。</span><span class="sxs-lookup"><span data-stu-id="a9788-121">An error prevented the operation from completing.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="a9788-122">注解</span><span class="sxs-lookup"><span data-stu-id="a9788-122">Remarks</span></span>

<span data-ttu-id="a9788-123">MAPI 和服务之间传递参数提供程序将假定它们正确，且经过仅调试验证与[CheckParms](checkparms.md)宏。</span><span class="sxs-lookup"><span data-stu-id="a9788-123">Parameters passed between MAPI and service providers are assumed to be correct and undergo only debug validation with the [CheckParms](checkparms.md) macro.</span></span> <span data-ttu-id="a9788-124">提供程序应检查所有参数中传递的客户端应用程序，但客户端应假定 MAPI 和提供程序参数正确。</span><span class="sxs-lookup"><span data-stu-id="a9788-124">Providers should check all parameters passed in by client applications, but clients should assume that MAPI and provider parameters are correct.</span></span> <span data-ttu-id="a9788-125">使用**HR_FAILED**宏来测试返回值。</span><span class="sxs-lookup"><span data-stu-id="a9788-125">Use the **HR_FAILED** macro to test return values.</span></span> 
  
<span data-ttu-id="a9788-126">根据调用的代码是否为 C 或 c + + 不同调用**UlValidateParms**宏。</span><span class="sxs-lookup"><span data-stu-id="a9788-126">The **UlValidateParms** macro is called differently depending on whether the calling code is C or C++.</span></span> <span data-ttu-id="a9788-127">使用此宏来验证返回 ULONG 而不是 HRESULT 值; 几**IUnknown**和 MAPI 方法的参数[ValidateParms](validateparms.md)宏适用于所有其他人。</span><span class="sxs-lookup"><span data-stu-id="a9788-127">This macro is used to validate parameters for the few **IUnknown** and MAPI methods that return ULONG instead of HRESULT values; the [ValidateParms](validateparms.md) macro works for all others.</span></span> 
  

