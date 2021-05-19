---
title: STnefProblemArray
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.STnefProblemArray
api_type:
- COM
ms.assetid: 115d845b-4168-4d49-b880-219ee28baa9a
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 721b14f101e87299f654507f94d4a957f905cac1
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33434261"
---
# <a name="stnefproblemarray"></a><span data-ttu-id="2ae17-103">STnefProblemArray</span><span class="sxs-lookup"><span data-stu-id="2ae17-103">STnefProblemArray</span></span>

  
  
<span data-ttu-id="2ae17-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="2ae17-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="2ae17-105">包含一个 **STnefProblem** 结构数组，该数组描述在 TNEF 流中对传输中性封装格式 (进行编码或解码期间发生的一个或多个) 问题。</span><span class="sxs-lookup"><span data-stu-id="2ae17-105">Contains an array of **STnefProblem** structures describing one or more processing problems that occurred during the encoding or decoding of a Transport Neutral Encapsulation Format (TNEF) stream.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="2ae17-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="2ae17-106">Header file:</span></span>  <br/> |<span data-ttu-id="2ae17-107">Tnef.h</span><span class="sxs-lookup"><span data-stu-id="2ae17-107">Tnef.h</span></span>  <br/> |
   
```cpp
typedef struct _STnefProblemArray
{
  ULONG cProblem;
  STnefProblem aProblem[MAPI_DIM];
}STnefProblemArray, FAR * LPSTnefProblemArray

```

## <a name="members"></a><span data-ttu-id="2ae17-108">Members</span><span class="sxs-lookup"><span data-stu-id="2ae17-108">Members</span></span>

 <span data-ttu-id="2ae17-109">**cProblem**</span><span class="sxs-lookup"><span data-stu-id="2ae17-109">**cProblem**</span></span>
  
> <span data-ttu-id="2ae17-110">在problem 成员中指定的 **数组中的元素** 计数。</span><span class="sxs-lookup"><span data-stu-id="2ae17-110">Count of elements in the array specified in the **aProblem** member.</span></span> 
    
 <span data-ttu-id="2ae17-111">**aProblem**</span><span class="sxs-lookup"><span data-stu-id="2ae17-111">**aProblem**</span></span>
  
> <span data-ttu-id="2ae17-112">[STnefProblem 结构](stnefproblem.md)数组。</span><span class="sxs-lookup"><span data-stu-id="2ae17-112">Array of [STnefProblem](stnefproblem.md) structures.</span></span> <span data-ttu-id="2ae17-113">每个结构都包含有关属性或属性处理问题的信息。</span><span class="sxs-lookup"><span data-stu-id="2ae17-113">Each structure contains information about a property or attribute processing problem.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="2ae17-114">备注</span><span class="sxs-lookup"><span data-stu-id="2ae17-114">Remarks</span></span>

<span data-ttu-id="2ae17-115">如果在属性或属性处理过程中出现问题， [则 ITnef：：ExtractProps](itnef-extractprops.md) 方法和 [ITnef：：Finish](itnef-finish.md) 方法中的输出参数各自会收到一个指向 **STnefProblemArray** 结构的指针 **，ExtractProps** 和 **Finish** 各自返回值 MAPI_W_ERRORS_RETURNED。</span><span class="sxs-lookup"><span data-stu-id="2ae17-115">If a problem occurs during attribute or property processing, an output parameter in the [ITnef::ExtractProps](itnef-extractprops.md) method and in the [ITnef::Finish](itnef-finish.md) method each receive a pointer to an **STnefProblemArray** structure and **ExtractProps** and **Finish** each return the value MAPI_W_ERRORS_RETURNED.</span></span> <span data-ttu-id="2ae17-116">此错误值指示处理过程中出现问题，并生成 **STnefProblemArray** 结构。</span><span class="sxs-lookup"><span data-stu-id="2ae17-116">This error value indicates that a problem arose during processing and an **STnefProblemArray** structure was generated.</span></span> 
  
<span data-ttu-id="2ae17-117">如果在处理属性或属性期间未生成 **STnefProblem** 结构，则客户端应用程序可以在该属性或属性处理成功的假设下继续。</span><span class="sxs-lookup"><span data-stu-id="2ae17-117">If an **STnefProblem** structure is not generated during the processing of an attribute or property, the client application can continue under the assumption that the processing of that attribute or property succeeded.</span></span> <span data-ttu-id="2ae17-118">唯一的异常是在解码封装块期间出现问题时发生。</span><span class="sxs-lookup"><span data-stu-id="2ae17-118">The only exception occurs when the problem arose during decoding of an encapsulation block.</span></span> <span data-ttu-id="2ae17-119">如果在此解码过程中发生错误，MAPI_E_UNABLE_TO_COMPLETE返回为[结构中的 SCODE。](scode.md)</span><span class="sxs-lookup"><span data-stu-id="2ae17-119">If the error occurred during this decoding, MAPI_E_UNABLE_TO_COMPLETE can be returned as the [SCODE](scode.md) in the structure.</span></span> <span data-ttu-id="2ae17-120">在这种情况下，将停止与块对应的组件解码，并且在另一个组件中继续解码。</span><span class="sxs-lookup"><span data-stu-id="2ae17-120">In this case, the decoding of the component corresponding to the block is stopped and decoding is continued in another component.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="2ae17-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2ae17-121">See also</span></span>



[<span data-ttu-id="2ae17-122">STnefProblem</span><span class="sxs-lookup"><span data-stu-id="2ae17-122">STnefProblem</span></span>](stnefproblem.md)
  
[<span data-ttu-id="2ae17-123">SCODE</span><span class="sxs-lookup"><span data-stu-id="2ae17-123">SCODE</span></span>](scode.md)


[<span data-ttu-id="2ae17-124">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="2ae17-124">MAPI Structures</span></span>](mapi-structures.md)

