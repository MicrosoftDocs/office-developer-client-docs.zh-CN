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
ms.openlocfilehash: b3862ea539907bb0570a0e845b09a15e7bed0507
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33425199"
---
# <a name="validateparameters"></a><span data-ttu-id="2e494-103">ValidateParameters</span><span class="sxs-lookup"><span data-stu-id="2e494-103">ValidateParameters</span></span>

  
  
<span data-ttu-id="2e494-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="2e494-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="2e494-105">调用内部函数以检查客户端应用程序已传递给服务提供程序的参数。</span><span class="sxs-lookup"><span data-stu-id="2e494-105">Calls an internal function to check the parameters client applications have passed to service providers.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="2e494-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="2e494-106">Header file:</span></span>  <br/> |<span data-ttu-id="2e494-107">Mapival.h</span><span class="sxs-lookup"><span data-stu-id="2e494-107">Mapival.h</span></span>  <br/> |
|<span data-ttu-id="2e494-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="2e494-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="2e494-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="2e494-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="2e494-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="2e494-110">Called by:</span></span>  <br/> |<span data-ttu-id="2e494-111">服务提供程序</span><span class="sxs-lookup"><span data-stu-id="2e494-111">Service providers</span></span>  <br/> |
   
```cpp
HRESULT ValidateParameters(
  METHODS eMethod,
  LPVOID First
);
```

## <a name="parameters"></a><span data-ttu-id="2e494-112">参数</span><span class="sxs-lookup"><span data-stu-id="2e494-112">Parameters</span></span>

 <span data-ttu-id="2e494-113">_eMethod_</span><span class="sxs-lookup"><span data-stu-id="2e494-113">_eMethod_</span></span>
  
> <span data-ttu-id="2e494-114">实时通过枚举指定要验证的方法。</span><span class="sxs-lookup"><span data-stu-id="2e494-114">[in] Specifies, by enumeration, the method to validate.</span></span> 
    
 <span data-ttu-id="2e494-115">_第一_</span><span class="sxs-lookup"><span data-stu-id="2e494-115">_First_</span></span>
  
> <span data-ttu-id="2e494-116">实时指向堆栈上第一个参数的指针。</span><span class="sxs-lookup"><span data-stu-id="2e494-116">[in] Pointer to the first argument on the stack.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="2e494-117">返回值</span><span class="sxs-lookup"><span data-stu-id="2e494-117">Return value</span></span>

<span data-ttu-id="2e494-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="2e494-118">S_OK</span></span> 
  
> <span data-ttu-id="2e494-119">所有参数都有效。</span><span class="sxs-lookup"><span data-stu-id="2e494-119">All of the parameters are valid.</span></span> 
    
<span data-ttu-id="2e494-120">MAPI_E_CALL_FAILED</span><span class="sxs-lookup"><span data-stu-id="2e494-120">MAPI_E_CALL_FAILED</span></span> 
  
> <span data-ttu-id="2e494-121">一个或多个参数无效。</span><span class="sxs-lookup"><span data-stu-id="2e494-121">One or more of the parameters are not valid.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="2e494-122">说明</span><span class="sxs-lookup"><span data-stu-id="2e494-122">Remarks</span></span>

<span data-ttu-id="2e494-123">**ValidateParameters**宏已被[ValidateParms](validateparms.md)宏取代。</span><span class="sxs-lookup"><span data-stu-id="2e494-123">The **ValidateParameters** macro has been superseded by the [ValidateParms](validateparms.md) macro.</span></span> <span data-ttu-id="2e494-124">**ValidateParameters**不能在 RISC 平台上正常运行, 现在无法在其上进行编译。</span><span class="sxs-lookup"><span data-stu-id="2e494-124">**ValidateParameters** does not work correctly on RISC platforms and is now prevented from compiling on them.</span></span> <span data-ttu-id="2e494-125">它仍可在 Intel 平台上正常编译和工作, 但建议在所有平台上使用**ValidateParms** 。</span><span class="sxs-lookup"><span data-stu-id="2e494-125">It still compiles and works correctly on Intel platforms, but **ValidateParms** is recommended on all platforms.</span></span> 
  

