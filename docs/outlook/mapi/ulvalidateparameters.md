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
ms.openlocfilehash: 465069f08e2026dcbf98e24f0f5f59e12ed17eca
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32315286"
---
# <a name="ulvalidateparameters"></a><span data-ttu-id="6dcad-103">UlValidateParameters</span><span class="sxs-lookup"><span data-stu-id="6dcad-103">UlValidateParameters</span></span>

  
  
<span data-ttu-id="6dcad-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="6dcad-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="6dcad-105">调用内部函数以检查客户端应用程序已传递给服务提供程序和 MAPI 的参数。</span><span class="sxs-lookup"><span data-stu-id="6dcad-105">Calls an internal function to check the parameters client applications have passed to service providers and MAPI.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="6dcad-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="6dcad-106">Header file:</span></span>  <br/> |<span data-ttu-id="6dcad-107">Mapival.h</span><span class="sxs-lookup"><span data-stu-id="6dcad-107">Mapival.h</span></span>  <br/> |
|<span data-ttu-id="6dcad-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="6dcad-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="6dcad-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="6dcad-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="6dcad-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="6dcad-110">Called by:</span></span>  <br/> |<span data-ttu-id="6dcad-111">服务提供程序</span><span class="sxs-lookup"><span data-stu-id="6dcad-111">Service providers</span></span>  <br/> |
   
```cpp
HRESULT UlValidateParameters(
  METHODS eMethod,
  LPVOID First
);
```

## <a name="parameters"></a><span data-ttu-id="6dcad-112">参数</span><span class="sxs-lookup"><span data-stu-id="6dcad-112">Parameters</span></span>

 <span data-ttu-id="6dcad-113">_eMethod_</span><span class="sxs-lookup"><span data-stu-id="6dcad-113">_eMethod_</span></span>
  
> <span data-ttu-id="6dcad-114">实时通过枚举指定要验证的方法。</span><span class="sxs-lookup"><span data-stu-id="6dcad-114">[in] Specifies, by enumeration, the method to validate.</span></span> 
    
 <span data-ttu-id="6dcad-115">_第一_</span><span class="sxs-lookup"><span data-stu-id="6dcad-115">_First_</span></span>
  
> <span data-ttu-id="6dcad-116">实时指向堆栈上第一个参数的指针。</span><span class="sxs-lookup"><span data-stu-id="6dcad-116">[in] Pointer to the first argument on the stack.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="6dcad-117">返回值</span><span class="sxs-lookup"><span data-stu-id="6dcad-117">Return value</span></span>

<span data-ttu-id="6dcad-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="6dcad-118">S_OK</span></span> 
  
> <span data-ttu-id="6dcad-119">调用成功, 并返回了所需的值或值。</span><span class="sxs-lookup"><span data-stu-id="6dcad-119">The call succeeded and has returned the expected value or values.</span></span> 
    
<span data-ttu-id="6dcad-120">MAPI_E_CALL_FAILED</span><span class="sxs-lookup"><span data-stu-id="6dcad-120">MAPI_E_CALL_FAILED</span></span> 
  
> <span data-ttu-id="6dcad-121">意外或未知来源的错误阻止操作完成。</span><span class="sxs-lookup"><span data-stu-id="6dcad-121">An error of unexpected or unknown origin prevented the operation from completing.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="6dcad-122">注解</span><span class="sxs-lookup"><span data-stu-id="6dcad-122">Remarks</span></span>

<span data-ttu-id="6dcad-123">**UlValidateParameters**宏已被[UlValidateParms](ulvalidateparms.md)宏取代。</span><span class="sxs-lookup"><span data-stu-id="6dcad-123">The **UlValidateParameters** macro has been superseded by the [UlValidateParms](ulvalidateparms.md) macro.</span></span> <span data-ttu-id="6dcad-124">**UlValidateParameters**不能在 RISC 平台上正常运行, 现在无法在其上进行编译。</span><span class="sxs-lookup"><span data-stu-id="6dcad-124">**UlValidateParameters** does not work correctly on RISC platforms and is now prevented from compiling on them.</span></span> <span data-ttu-id="6dcad-125">它仍可在 Intel 平台上正常编译和工作, 但建议在所有平台上使用**UlValidateParms** 。</span><span class="sxs-lookup"><span data-stu-id="6dcad-125">It still compiles and works correctly on Intel platforms, but **UlValidateParms** is recommended on all platforms.</span></span> 
  

