---
title: ValidateParms
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.ValidateParms
api_type:
- COM
ms.assetid: 3ede1a35-4acc-4b8f-a1bd-027f35798a37
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: f2669f703827924493387c4beac0b64b25672860
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33436799"
---
# <a name="validateparms"></a><span data-ttu-id="76916-103">ValidateParms</span><span class="sxs-lookup"><span data-stu-id="76916-103">ValidateParms</span></span>

  
  
<span data-ttu-id="76916-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="76916-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="76916-105">调用内部函数以检查客户端应用程序已传递给服务提供商的参数。</span><span class="sxs-lookup"><span data-stu-id="76916-105">Calls an internal function to check the parameters client applications have passed to service providers.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="76916-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="76916-106">Header file:</span></span>  <br/> |<span data-ttu-id="76916-107">Mapival.h</span><span class="sxs-lookup"><span data-stu-id="76916-107">Mapival.h</span></span>  <br/> |
|<span data-ttu-id="76916-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="76916-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="76916-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="76916-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="76916-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="76916-110">Called by:</span></span>  <br/> |<span data-ttu-id="76916-111">服务提供程序</span><span class="sxs-lookup"><span data-stu-id="76916-111">Service providers</span></span>  <br/> |
   
```cpp
HRESULT ValidateParms(
  METHODS eMethod,
  LPVOID First
);
```

## <a name="parameters"></a><span data-ttu-id="76916-112">参数</span><span class="sxs-lookup"><span data-stu-id="76916-112">Parameters</span></span>

 <span data-ttu-id="76916-113">_eMethod_</span><span class="sxs-lookup"><span data-stu-id="76916-113">_eMethod_</span></span>
  
> <span data-ttu-id="76916-114">[in]通过枚举指定要验证的方法。</span><span class="sxs-lookup"><span data-stu-id="76916-114">[in] Specifies, by enumeration, the method to validate.</span></span> 
    
 <span data-ttu-id="76916-115">_第一_</span><span class="sxs-lookup"><span data-stu-id="76916-115">_First_</span></span>
  
> <span data-ttu-id="76916-116">[in]指向堆栈上第一个参数的指针。</span><span class="sxs-lookup"><span data-stu-id="76916-116">[in] Pointer to the first argument on the stack.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="76916-117">返回值</span><span class="sxs-lookup"><span data-stu-id="76916-117">Return value</span></span>

<span data-ttu-id="76916-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="76916-118">S_OK</span></span> 
  
> <span data-ttu-id="76916-119">所有参数都有效。</span><span class="sxs-lookup"><span data-stu-id="76916-119">All of the parameters are valid.</span></span> 
    
<span data-ttu-id="76916-120">MAPI_E_CALL_FAILED</span><span class="sxs-lookup"><span data-stu-id="76916-120">MAPI_E_CALL_FAILED</span></span> 
  
> <span data-ttu-id="76916-121">其中一个或多个参数无效。</span><span class="sxs-lookup"><span data-stu-id="76916-121">One or more of the parameters are not valid.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="76916-122">备注</span><span class="sxs-lookup"><span data-stu-id="76916-122">Remarks</span></span>

<span data-ttu-id="76916-123">在 MAPI 和服务提供商之间传递的参数被认为是正确的，并且只接受 [CheckParms 宏的调试](checkparms.md) 验证。</span><span class="sxs-lookup"><span data-stu-id="76916-123">Parameters passed between MAPI and service providers are assumed to be correct and undergo only debug validation with the [CheckParms](checkparms.md) macro.</span></span> <span data-ttu-id="76916-124">提供程序应检查客户端应用程序传入的所有参数，但客户端应假定 MAPI 和提供程序参数正确。</span><span class="sxs-lookup"><span data-stu-id="76916-124">Providers should check all parameters passed in by client applications, but clients should assume that MAPI and provider parameters are correct.</span></span> <span data-ttu-id="76916-125">使用 **HR_FAILED** 宏测试返回值。</span><span class="sxs-lookup"><span data-stu-id="76916-125">Use the **HR_FAILED** macro to test return values.</span></span> 
  
 <span data-ttu-id="76916-126">**ValidateParms** 的调用方式不同，具体取决于调用代码是 C 还是 C++。</span><span class="sxs-lookup"><span data-stu-id="76916-126">**ValidateParms** is called differently depending on whether the calling code is C or C++.</span></span> <span data-ttu-id="76916-127">C++ 将隐式参数（称为  _this）_ 传递给每个方法调用，该方法调用在 C 中变为显式，并且是对象的地址。</span><span class="sxs-lookup"><span data-stu-id="76916-127">C++ passes an implicit parameter known as  _this_ to each method call, which becomes explicit in C and is the address of the object.</span></span> <span data-ttu-id="76916-128">第一个参数  _eMethod_ 是一个从正在验证的接口和方法所创建枚举器，并告知期望在堆栈上找到的参数。</span><span class="sxs-lookup"><span data-stu-id="76916-128">The first parameter,  _eMethod_, is an enumerator made from the interface and method being validated and tells what parameters to expect to find on the stack.</span></span> <span data-ttu-id="76916-129">对于 C 和 C++，第二个参数不同。</span><span class="sxs-lookup"><span data-stu-id="76916-129">The second parameter is different for C and C++.</span></span> <span data-ttu-id="76916-130">在 C++ 中，它称为  _First_，它是要验证的方法的第一个参数。</span><span class="sxs-lookup"><span data-stu-id="76916-130">In C++ it is called  _First_, and it is the first parameter to the method being validated.</span></span> <span data-ttu-id="76916-131">C 语言的第二个参数  _ppThis_ 是方法的第一个参数的地址，该方法始终是对象指针。</span><span class="sxs-lookup"><span data-stu-id="76916-131">The second parameter for the C language,  _ppThis_, is the address of the first parameter to the method which is always an object pointer.</span></span> <span data-ttu-id="76916-132">在这两种情况下，第二个参数都提供方法参数列表开头的地址，并基于  _eMethod_ 向下移动堆栈并验证参数。</span><span class="sxs-lookup"><span data-stu-id="76916-132">In both cases, the second parameter gives the address of the beginning of the method's parameter list, and based on  _eMethod_, moves down the stack and validates the parameters.</span></span> 
  
<span data-ttu-id="76916-133">实现常见接口（如 **IMAPITable** 和 **IMAPIProp）** 的提供程序应始终使用 **ValidateParms** 函数检查参数，以确保所有提供程序之间的一致性。</span><span class="sxs-lookup"><span data-stu-id="76916-133">Providers implementing common interfaces such as **IMAPITable** and **IMAPIProp** should always check parameters using the **ValidateParms** function in order to make sure consistency across all providers.</span></span> <span data-ttu-id="76916-134">为要在适当使用某些复杂参数类型定义了其他参数验证函数。</span><span class="sxs-lookup"><span data-stu-id="76916-134">Additional parameter validation functions have been defined for some complex parameter types to be used instead as appropriate.</span></span> <span data-ttu-id="76916-135">有关以下函数，请参阅参考主题：</span><span class="sxs-lookup"><span data-stu-id="76916-135">See the reference topics for the following functions:</span></span> 
  
- [<span data-ttu-id="76916-136">FBadColumnSet</span><span class="sxs-lookup"><span data-stu-id="76916-136">FBadColumnSet</span></span>](fbadcolumnset.md)
    
- [<span data-ttu-id="76916-137">FBadEntryList</span><span class="sxs-lookup"><span data-stu-id="76916-137">FBadEntryList</span></span>](fbadentrylist.md)
    
- [<span data-ttu-id="76916-138">FBadProp</span><span class="sxs-lookup"><span data-stu-id="76916-138">FBadProp</span></span>](fbadprop.md)
    
- [<span data-ttu-id="76916-139">FBadProp</span><span class="sxs-lookup"><span data-stu-id="76916-139">FBadProp</span></span>](fbadprop.md)
    
- [<span data-ttu-id="76916-140">FBadRestriction</span><span class="sxs-lookup"><span data-stu-id="76916-140">FBadRestriction</span></span>](fbadrestriction.md)
    
- [<span data-ttu-id="76916-141">FBadRestriction</span><span class="sxs-lookup"><span data-stu-id="76916-141">FBadRestriction</span></span>](fbadrestriction.md)
    
- [<span data-ttu-id="76916-142">FBadRglpszW</span><span class="sxs-lookup"><span data-stu-id="76916-142">FBadRglpszW</span></span>](fbadrglpszw.md)
    
- [<span data-ttu-id="76916-143">FBadRow</span><span class="sxs-lookup"><span data-stu-id="76916-143">FBadRow</span></span>](fbadrow.md)
    
- [<span data-ttu-id="76916-144">FBadRowSet</span><span class="sxs-lookup"><span data-stu-id="76916-144">FBadRowSet</span></span>](fbadrowset.md)
    
- [<span data-ttu-id="76916-145">FBadSortOrderSet</span><span class="sxs-lookup"><span data-stu-id="76916-145">FBadSortOrderSet</span></span>](fbadsortorderset.md)
    
<span data-ttu-id="76916-146">继承的方法使用的参数验证与继承自的接口相同。</span><span class="sxs-lookup"><span data-stu-id="76916-146">Inherited methods use the same parameter validation as the interface from which they inherit.</span></span> <span data-ttu-id="76916-147">例如 **，IMessage** 和 **IMAPIProp** 的参数检查应该相同。</span><span class="sxs-lookup"><span data-stu-id="76916-147">For example, the parameter checking for **IMessage** and **IMAPIProp** should be the same.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="76916-148">另请参阅</span><span class="sxs-lookup"><span data-stu-id="76916-148">See also</span></span>



[<span data-ttu-id="76916-149">UlValidateParms</span><span class="sxs-lookup"><span data-stu-id="76916-149">UlValidateParms</span></span>](ulvalidateparms.md)

