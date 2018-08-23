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
ms.openlocfilehash: 7b29eab30677dae7f720cecd9fde71e8bbbf752c
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22579716"
---
# <a name="validateparms"></a><span data-ttu-id="470fd-103">ValidateParms</span><span class="sxs-lookup"><span data-stu-id="470fd-103">ValidateParms</span></span>

  
  
<span data-ttu-id="470fd-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="470fd-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="470fd-105">调用检查参数客户端应用程序已传递给服务提供商的内部函数。</span><span class="sxs-lookup"><span data-stu-id="470fd-105">Calls an internal function to check the parameters client applications have passed to service providers.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="470fd-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="470fd-106">Header file:</span></span>  <br/> |<span data-ttu-id="470fd-107">Mapival.h</span><span class="sxs-lookup"><span data-stu-id="470fd-107">Mapival.h</span></span>  <br/> |
|<span data-ttu-id="470fd-108">通过实现：</span><span class="sxs-lookup"><span data-stu-id="470fd-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="470fd-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="470fd-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="470fd-110">调用：</span><span class="sxs-lookup"><span data-stu-id="470fd-110">Called by:</span></span>  <br/> |<span data-ttu-id="470fd-111">服务提供商</span><span class="sxs-lookup"><span data-stu-id="470fd-111">Service providers</span></span>  <br/> |
   
```cpp
HRESULT ValidateParms(
  METHODS eMethod,
  LPVOID First
);
```

## <a name="parameters"></a><span data-ttu-id="470fd-112">参数</span><span class="sxs-lookup"><span data-stu-id="470fd-112">Parameters</span></span>

 <span data-ttu-id="470fd-113">_eMethod_</span><span class="sxs-lookup"><span data-stu-id="470fd-113">_eMethod_</span></span>
  
> <span data-ttu-id="470fd-114">[in]通过枚举，指定要验证的方法。</span><span class="sxs-lookup"><span data-stu-id="470fd-114">[in] Specifies, by enumeration, the method to validate.</span></span> 
    
 <span data-ttu-id="470fd-115">_第一_</span><span class="sxs-lookup"><span data-stu-id="470fd-115">_First_</span></span>
  
> <span data-ttu-id="470fd-116">[in]堆栈上第一个参数的指针。</span><span class="sxs-lookup"><span data-stu-id="470fd-116">[in] Pointer to the first argument on the stack.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="470fd-117">返回值</span><span class="sxs-lookup"><span data-stu-id="470fd-117">Return value</span></span>

<span data-ttu-id="470fd-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="470fd-118">S_OK</span></span> 
  
> <span data-ttu-id="470fd-119">所有参数都是有效的。</span><span class="sxs-lookup"><span data-stu-id="470fd-119">All of the parameters are valid.</span></span> 
    
<span data-ttu-id="470fd-120">MAPI_E_CALL_FAILED</span><span class="sxs-lookup"><span data-stu-id="470fd-120">MAPI_E_CALL_FAILED</span></span> 
  
> <span data-ttu-id="470fd-121">一个或多个参数不是有效的。</span><span class="sxs-lookup"><span data-stu-id="470fd-121">One or more of the parameters are not valid.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="470fd-122">注解</span><span class="sxs-lookup"><span data-stu-id="470fd-122">Remarks</span></span>

<span data-ttu-id="470fd-123">MAPI 和服务之间传递参数提供程序将假定它们正确，且经过仅调试验证与[CheckParms](checkparms.md)宏。</span><span class="sxs-lookup"><span data-stu-id="470fd-123">Parameters passed between MAPI and service providers are assumed to be correct and undergo only debug validation with the [CheckParms](checkparms.md) macro.</span></span> <span data-ttu-id="470fd-124">提供程序应检查所有参数中传递的客户端应用程序，但客户端应假定 MAPI 和提供程序参数正确。</span><span class="sxs-lookup"><span data-stu-id="470fd-124">Providers should check all parameters passed in by client applications, but clients should assume that MAPI and provider parameters are correct.</span></span> <span data-ttu-id="470fd-125">使用**HR_FAILED**宏来测试返回值。</span><span class="sxs-lookup"><span data-stu-id="470fd-125">Use the **HR_FAILED** macro to test return values.</span></span> 
  
 <span data-ttu-id="470fd-126">**ValidateParms**称为根据调用的代码是否为 C 或 c + + 的不同。</span><span class="sxs-lookup"><span data-stu-id="470fd-126">**ValidateParms** is called differently depending on whether the calling code is C or C++.</span></span> <span data-ttu-id="470fd-127">C + + 将传递到每个方法的调用，以将成为显式 c，是对象的地址称为，_此_隐式参数。</span><span class="sxs-lookup"><span data-stu-id="470fd-127">C++ passes an implicit parameter known as  _this_ to each method call, which becomes explicit in C and is the address of the object.</span></span> <span data-ttu-id="470fd-128">第一个参数， _eMethod_，是从接口和正在进行验证的方法进行的枚举和告知所期望堆栈上找到的参数。</span><span class="sxs-lookup"><span data-stu-id="470fd-128">The first parameter,  _eMethod_, is an enumerator made from the interface and method being validated and tells what parameters to expect to find on the stack.</span></span> <span data-ttu-id="470fd-129">第二个参数是不同的 C 和 c + +。</span><span class="sxs-lookup"><span data-stu-id="470fd-129">The second parameter is different for C and C++.</span></span> <span data-ttu-id="470fd-130">在 c + + 调用_第一个_，并且正在进行验证的方法的第一个参数。</span><span class="sxs-lookup"><span data-stu-id="470fd-130">In C++ it is called  _First_, and it is the first parameter to the method being validated.</span></span> <span data-ttu-id="470fd-131">C 语言， _ppThis_，第二个参数是第一个参数方法它始终是对象指针的地址。</span><span class="sxs-lookup"><span data-stu-id="470fd-131">The second parameter for the C language,  _ppThis_, is the address of the first parameter to the method which is always an object pointer.</span></span> <span data-ttu-id="470fd-132">在这两种情况下，第二个参数提供的方法的参数列表的开头的地址和基于_eMethod_、 下移堆栈和验证参数。</span><span class="sxs-lookup"><span data-stu-id="470fd-132">In both cases, the second parameter gives the address of the beginning of the method's parameter list, and based on  _eMethod_, moves down the stack and validates the parameters.</span></span> 
  
<span data-ttu-id="470fd-133">提供程序实现**IMAPIProp** **IMAPITable**等公共接口应始终检查以确保一致性使跨所有提供商使用**ValidateParms**函数的参数。</span><span class="sxs-lookup"><span data-stu-id="470fd-133">Providers implementing common interfaces such as **IMAPITable** and **IMAPIProp** should always check parameters using the **ValidateParms** function in order to make sure consistency across all providers.</span></span> <span data-ttu-id="470fd-134">对于某些复杂参数类型，而是根据使用已定义其他参数验证函数。</span><span class="sxs-lookup"><span data-stu-id="470fd-134">Additional parameter validation functions have been defined for some complex parameter types to be used instead as appropriate.</span></span> <span data-ttu-id="470fd-135">请参阅以下功能的参考主题：</span><span class="sxs-lookup"><span data-stu-id="470fd-135">See the reference topics for the following functions:</span></span> 
  
- [<span data-ttu-id="470fd-136">FBadColumnSet</span><span class="sxs-lookup"><span data-stu-id="470fd-136">FBadColumnSet</span></span>](fbadcolumnset.md)
    
- [<span data-ttu-id="470fd-137">FBadEntryList</span><span class="sxs-lookup"><span data-stu-id="470fd-137">FBadEntryList</span></span>](fbadentrylist.md)
    
- [<span data-ttu-id="470fd-138">FBadProp</span><span class="sxs-lookup"><span data-stu-id="470fd-138">FBadProp</span></span>](fbadprop.md)
    
- [<span data-ttu-id="470fd-139">FBadProp</span><span class="sxs-lookup"><span data-stu-id="470fd-139">FBadProp</span></span>](fbadprop.md)
    
- [<span data-ttu-id="470fd-140">FBadRestriction</span><span class="sxs-lookup"><span data-stu-id="470fd-140">FBadRestriction</span></span>](fbadrestriction.md)
    
- [<span data-ttu-id="470fd-141">FBadRestriction</span><span class="sxs-lookup"><span data-stu-id="470fd-141">FBadRestriction</span></span>](fbadrestriction.md)
    
- [<span data-ttu-id="470fd-142">FBadRglpszW</span><span class="sxs-lookup"><span data-stu-id="470fd-142">FBadRglpszW</span></span>](fbadrglpszw.md)
    
- [<span data-ttu-id="470fd-143">FBadRow</span><span class="sxs-lookup"><span data-stu-id="470fd-143">FBadRow</span></span>](fbadrow.md)
    
- [<span data-ttu-id="470fd-144">FBadRowSet</span><span class="sxs-lookup"><span data-stu-id="470fd-144">FBadRowSet</span></span>](fbadrowset.md)
    
- [<span data-ttu-id="470fd-145">FBadSortOrderSet</span><span class="sxs-lookup"><span data-stu-id="470fd-145">FBadSortOrderSet</span></span>](fbadsortorderset.md)
    
<span data-ttu-id="470fd-146">继承的方法将相同参数验证用作它们所继承的接口。</span><span class="sxs-lookup"><span data-stu-id="470fd-146">Inherited methods use the same parameter validation as the interface from which they inherit.</span></span> <span data-ttu-id="470fd-147">例如，检查**IMessage**和**IMAPIProp**参数应是相同。</span><span class="sxs-lookup"><span data-stu-id="470fd-147">For example, the parameter checking for **IMessage** and **IMAPIProp** should be the same.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="470fd-148">另请参阅</span><span class="sxs-lookup"><span data-stu-id="470fd-148">See also</span></span>



[<span data-ttu-id="470fd-149">UlValidateParms</span><span class="sxs-lookup"><span data-stu-id="470fd-149">UlValidateParms</span></span>](ulvalidateparms.md)

