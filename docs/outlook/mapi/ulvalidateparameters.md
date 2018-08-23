---
title: UlValidateParameters
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.UlValidateParameters
api_type:
- COM
ms.assetid: fb9050c9-5797-44f0-8bf5-6264f4e6d7c3
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 297b5a516f8275b236092f9f385afcb673c95de0
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22585239"
---
# <a name="ulvalidateparameters"></a><span data-ttu-id="aeffd-103">UlValidateParameters</span><span class="sxs-lookup"><span data-stu-id="aeffd-103">UlValidateParameters</span></span>

  
  
<span data-ttu-id="aeffd-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="aeffd-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="aeffd-105">调用检查参数客户端应用程序已传递给服务提供商和 MAPI 内部函数。</span><span class="sxs-lookup"><span data-stu-id="aeffd-105">Calls an internal function to check the parameters client applications have passed to service providers and MAPI.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="aeffd-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="aeffd-106">Header file:</span></span>  <br/> |<span data-ttu-id="aeffd-107">Mapival.h</span><span class="sxs-lookup"><span data-stu-id="aeffd-107">Mapival.h</span></span>  <br/> |
|<span data-ttu-id="aeffd-108">通过实现：</span><span class="sxs-lookup"><span data-stu-id="aeffd-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="aeffd-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="aeffd-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="aeffd-110">调用：</span><span class="sxs-lookup"><span data-stu-id="aeffd-110">Called by:</span></span>  <br/> |<span data-ttu-id="aeffd-111">服务提供商</span><span class="sxs-lookup"><span data-stu-id="aeffd-111">Service providers</span></span>  <br/> |
   
```cpp
HRESULT UlValidateParameters(
  METHODS eMethod,
  LPVOID First
);
```

## <a name="parameters"></a><span data-ttu-id="aeffd-112">参数</span><span class="sxs-lookup"><span data-stu-id="aeffd-112">Parameters</span></span>

 <span data-ttu-id="aeffd-113">_eMethod_</span><span class="sxs-lookup"><span data-stu-id="aeffd-113">_eMethod_</span></span>
  
> <span data-ttu-id="aeffd-114">[in]通过枚举，指定要验证的方法。</span><span class="sxs-lookup"><span data-stu-id="aeffd-114">[in] Specifies, by enumeration, the method to validate.</span></span> 
    
 <span data-ttu-id="aeffd-115">_第一_</span><span class="sxs-lookup"><span data-stu-id="aeffd-115">_First_</span></span>
  
> <span data-ttu-id="aeffd-116">[in]堆栈上第一个参数的指针。</span><span class="sxs-lookup"><span data-stu-id="aeffd-116">[in] Pointer to the first argument on the stack.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="aeffd-117">返回值</span><span class="sxs-lookup"><span data-stu-id="aeffd-117">Return value</span></span>

<span data-ttu-id="aeffd-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="aeffd-118">S_OK</span></span> 
  
> <span data-ttu-id="aeffd-119">呼叫成功或多个预期值返回。</span><span class="sxs-lookup"><span data-stu-id="aeffd-119">The call succeeded and has returned the expected value or values.</span></span> 
    
<span data-ttu-id="aeffd-120">MAPI_E_CALL_FAILED</span><span class="sxs-lookup"><span data-stu-id="aeffd-120">MAPI_E_CALL_FAILED</span></span> 
  
> <span data-ttu-id="aeffd-121">意外或未知的原点出现错误，无法完成操作。</span><span class="sxs-lookup"><span data-stu-id="aeffd-121">An error of unexpected or unknown origin prevented the operation from completing.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="aeffd-122">注解</span><span class="sxs-lookup"><span data-stu-id="aeffd-122">Remarks</span></span>

<span data-ttu-id="aeffd-123">已由[UlValidateParms](ulvalidateparms.md)宏取代**UlValidateParameters**宏。</span><span class="sxs-lookup"><span data-stu-id="aeffd-123">The **UlValidateParameters** macro has been superseded by the [UlValidateParms](ulvalidateparms.md) macro.</span></span> <span data-ttu-id="aeffd-124">**UlValidateParameters** RISC 平台上不会无法正常工作，现在将会阻止对它们进行编译。</span><span class="sxs-lookup"><span data-stu-id="aeffd-124">**UlValidateParameters** does not work correctly on RISC platforms and is now prevented from compiling on them.</span></span> <span data-ttu-id="aeffd-125">仍编译，并能够正常运行 Intel 平台上，但**UlValidateParms**建议所有平台上。</span><span class="sxs-lookup"><span data-stu-id="aeffd-125">It still compiles and works correctly on Intel platforms, but **UlValidateParms** is recommended on all platforms.</span></span> 
  

