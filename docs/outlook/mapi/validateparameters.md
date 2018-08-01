---
title: ValidateParameters
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.ValidateParameters
api_type:
- COM
ms.assetid: 80aadd11-5409-4636-8fad-fa2206336671
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 921417d8fc73ca9c1f126b2cb0add23f6625e3f4
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779085"
---
# <a name="validateparameters"></a><span data-ttu-id="037c1-103">ValidateParameters</span><span class="sxs-lookup"><span data-stu-id="037c1-103">ValidateParameters</span></span>

  
  
<span data-ttu-id="037c1-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="037c1-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="037c1-105">调用检查参数客户端应用程序已传递给服务提供商的内部函数。</span><span class="sxs-lookup"><span data-stu-id="037c1-105">Calls an internal function to check the parameters client applications have passed to service providers.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="037c1-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="037c1-106">Header file:</span></span>  <br/> |<span data-ttu-id="037c1-107">Mapival.h</span><span class="sxs-lookup"><span data-stu-id="037c1-107">Mapival.h</span></span>  <br/> |
|<span data-ttu-id="037c1-108">通过实现：</span><span class="sxs-lookup"><span data-stu-id="037c1-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="037c1-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="037c1-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="037c1-110">调用：</span><span class="sxs-lookup"><span data-stu-id="037c1-110">Called by:</span></span>  <br/> |<span data-ttu-id="037c1-111">服务提供商</span><span class="sxs-lookup"><span data-stu-id="037c1-111">Service providers</span></span>  <br/> |
   
```cpp
HRESULT ValidateParameters(
  METHODS eMethod,
  LPVOID First
);
```

## <a name="parameters"></a><span data-ttu-id="037c1-112">参数</span><span class="sxs-lookup"><span data-stu-id="037c1-112">Parameters</span></span>

 <span data-ttu-id="037c1-113">_eMethod_</span><span class="sxs-lookup"><span data-stu-id="037c1-113">_eMethod_</span></span>
  
> <span data-ttu-id="037c1-114">[in]通过枚举，指定要验证的方法。</span><span class="sxs-lookup"><span data-stu-id="037c1-114">[in] Specifies, by enumeration, the method to validate.</span></span> 
    
 <span data-ttu-id="037c1-115">_第一_</span><span class="sxs-lookup"><span data-stu-id="037c1-115">_First_</span></span>
  
> <span data-ttu-id="037c1-116">[in]堆栈上第一个参数的指针。</span><span class="sxs-lookup"><span data-stu-id="037c1-116">[in] Pointer to the first argument on the stack.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="037c1-117">返回值</span><span class="sxs-lookup"><span data-stu-id="037c1-117">Return value</span></span>

<span data-ttu-id="037c1-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="037c1-118">S_OK</span></span> 
  
> <span data-ttu-id="037c1-119">所有参数都是有效的。</span><span class="sxs-lookup"><span data-stu-id="037c1-119">All of the parameters are valid.</span></span> 
    
<span data-ttu-id="037c1-120">MAPI_E_CALL_FAILED</span><span class="sxs-lookup"><span data-stu-id="037c1-120">MAPI_E_CALL_FAILED</span></span> 
  
> <span data-ttu-id="037c1-121">一个或多个参数不是有效的。</span><span class="sxs-lookup"><span data-stu-id="037c1-121">One or more of the parameters are not valid.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="037c1-122">说明</span><span class="sxs-lookup"><span data-stu-id="037c1-122">Remarks</span></span>

<span data-ttu-id="037c1-123">已由[ValidateParms](validateparms.md)宏取代**ValidateParameters**宏。</span><span class="sxs-lookup"><span data-stu-id="037c1-123">The **ValidateParameters** macro has been superseded by the [ValidateParms](validateparms.md) macro.</span></span> <span data-ttu-id="037c1-124">**ValidateParameters** RISC 平台上不会无法正常工作，现在将会阻止对它们进行编译。</span><span class="sxs-lookup"><span data-stu-id="037c1-124">**ValidateParameters** does not work correctly on RISC platforms and is now prevented from compiling on them.</span></span> <span data-ttu-id="037c1-125">仍编译，并能够正常运行 Intel 平台上，但**ValidateParms**建议所有平台上。</span><span class="sxs-lookup"><span data-stu-id="037c1-125">It still compiles and works correctly on Intel platforms, but **ValidateParms** is recommended on all platforms.</span></span> 
  

