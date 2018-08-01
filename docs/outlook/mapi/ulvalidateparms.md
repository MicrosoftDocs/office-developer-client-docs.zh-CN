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
ms.openlocfilehash: 12b1655b1e6786d2ebc985e834b635679e59f7d2
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779035"
---
# <a name="ulvalidateparms"></a><span data-ttu-id="fac6d-103">UlValidateParms</span><span class="sxs-lookup"><span data-stu-id="fac6d-103">UlValidateParms</span></span>

  
  
<span data-ttu-id="fac6d-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="fac6d-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="fac6d-105">调用检查参数客户端应用程序已传递给服务提供商和 MAPI 内部函数。</span><span class="sxs-lookup"><span data-stu-id="fac6d-105">Calls an internal function to check the parameters client applications have passed to service providers and MAPI.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="fac6d-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="fac6d-106">Header file:</span></span>  <br/> |<span data-ttu-id="fac6d-107">Mapival.h</span><span class="sxs-lookup"><span data-stu-id="fac6d-107">Mapival.h</span></span>  <br/> |
|<span data-ttu-id="fac6d-108">通过实现：</span><span class="sxs-lookup"><span data-stu-id="fac6d-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="fac6d-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="fac6d-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="fac6d-110">调用：</span><span class="sxs-lookup"><span data-stu-id="fac6d-110">Called by:</span></span>  <br/> |<span data-ttu-id="fac6d-111">服务提供商</span><span class="sxs-lookup"><span data-stu-id="fac6d-111">Service providers</span></span>  <br/> |
   
```cpp
HRESULT UlValidateParms(
  METHODS eMethod,
  LPVOID First
);
```

## <a name="parameters"></a><span data-ttu-id="fac6d-112">参数</span><span class="sxs-lookup"><span data-stu-id="fac6d-112">Parameters</span></span>

 <span data-ttu-id="fac6d-113">_eMethod_</span><span class="sxs-lookup"><span data-stu-id="fac6d-113">_eMethod_</span></span>
  
> <span data-ttu-id="fac6d-114">[in]通过枚举，指定要验证的方法。</span><span class="sxs-lookup"><span data-stu-id="fac6d-114">[in] Specifies, by enumeration, the method to validate.</span></span> 
    
 <span data-ttu-id="fac6d-115">_第一_</span><span class="sxs-lookup"><span data-stu-id="fac6d-115">_First_</span></span>
  
> <span data-ttu-id="fac6d-116">[in]堆栈上第一个参数的指针。</span><span class="sxs-lookup"><span data-stu-id="fac6d-116">[in] Pointer to the first argument on the stack.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="fac6d-117">返回值</span><span class="sxs-lookup"><span data-stu-id="fac6d-117">Return value</span></span>

<span data-ttu-id="fac6d-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="fac6d-118">S_OK</span></span> 
  
> <span data-ttu-id="fac6d-119">呼叫成功或多个预期值返回。</span><span class="sxs-lookup"><span data-stu-id="fac6d-119">The call succeeded and has returned the expected value or values.</span></span> 
    
<span data-ttu-id="fac6d-120">MAPI_E_CALL_FAILED</span><span class="sxs-lookup"><span data-stu-id="fac6d-120">MAPI_E_CALL_FAILED</span></span> 
  
> <span data-ttu-id="fac6d-121">出现错误，无法完成操作。</span><span class="sxs-lookup"><span data-stu-id="fac6d-121">An error prevented the operation from completing.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="fac6d-122">说明</span><span class="sxs-lookup"><span data-stu-id="fac6d-122">Remarks</span></span>

<span data-ttu-id="fac6d-123">MAPI 和服务之间传递参数提供程序将假定它们正确，且经过仅调试验证与[CheckParms](checkparms.md)宏。</span><span class="sxs-lookup"><span data-stu-id="fac6d-123">Parameters passed between MAPI and service providers are assumed to be correct and undergo only debug validation with the [CheckParms](checkparms.md) macro.</span></span> <span data-ttu-id="fac6d-124">提供程序应检查所有参数中传递的客户端应用程序，但客户端应假定 MAPI 和提供程序参数正确。</span><span class="sxs-lookup"><span data-stu-id="fac6d-124">Providers should check all parameters passed in by client applications, but clients should assume that MAPI and provider parameters are correct.</span></span> <span data-ttu-id="fac6d-125">使用**HR_FAILED**宏来测试返回值。</span><span class="sxs-lookup"><span data-stu-id="fac6d-125">Use the **HR_FAILED** macro to test return values.</span></span> 
  
<span data-ttu-id="fac6d-126">根据调用的代码是否为 C 或 c + + 不同调用**UlValidateParms**宏。</span><span class="sxs-lookup"><span data-stu-id="fac6d-126">The **UlValidateParms** macro is called differently depending on whether the calling code is C or C++.</span></span> <span data-ttu-id="fac6d-127">使用此宏来验证返回 ULONG 而不是 HRESULT 值; 几**IUnknown**和 MAPI 方法的参数[ValidateParms](validateparms.md)宏适用于所有其他人。</span><span class="sxs-lookup"><span data-stu-id="fac6d-127">This macro is used to validate parameters for the few **IUnknown** and MAPI methods that return ULONG instead of HRESULT values; the [ValidateParms](validateparms.md) macro works for all others.</span></span> 
  

