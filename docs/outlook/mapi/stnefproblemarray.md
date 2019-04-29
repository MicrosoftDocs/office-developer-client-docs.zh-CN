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
# <a name="stnefproblemarray"></a><span data-ttu-id="8af0c-103">STnefProblemArray</span><span class="sxs-lookup"><span data-stu-id="8af0c-103">STnefProblemArray</span></span>

  
  
<span data-ttu-id="8af0c-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="8af0c-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="8af0c-105">包含描述在编码或解码传输中性封装格式 (TNEF) 流的过程中发生的一个或多个处理问题的**STnefProblem**结构数组。</span><span class="sxs-lookup"><span data-stu-id="8af0c-105">Contains an array of **STnefProblem** structures describing one or more processing problems that occurred during the encoding or decoding of a Transport Neutral Encapsulation Format (TNEF) stream.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="8af0c-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="8af0c-106">Header file:</span></span>  <br/> |<span data-ttu-id="8af0c-107">Tnef</span><span class="sxs-lookup"><span data-stu-id="8af0c-107">Tnef.h</span></span>  <br/> |
   
```cpp
typedef struct _STnefProblemArray
{
  ULONG cProblem;
  STnefProblem aProblem[MAPI_DIM];
}STnefProblemArray, FAR * LPSTnefProblemArray

```

## <a name="members"></a><span data-ttu-id="8af0c-108">Members</span><span class="sxs-lookup"><span data-stu-id="8af0c-108">Members</span></span>

 <span data-ttu-id="8af0c-109">**cProblem**</span><span class="sxs-lookup"><span data-stu-id="8af0c-109">**cProblem**</span></span>
  
> <span data-ttu-id="8af0c-110">**aProblem**成员中指定的数组中的元素数。</span><span class="sxs-lookup"><span data-stu-id="8af0c-110">Count of elements in the array specified in the **aProblem** member.</span></span> 
    
 <span data-ttu-id="8af0c-111">**aProblem**</span><span class="sxs-lookup"><span data-stu-id="8af0c-111">**aProblem**</span></span>
  
> <span data-ttu-id="8af0c-112">[STnefProblem](stnefproblem.md)结构的数组。</span><span class="sxs-lookup"><span data-stu-id="8af0c-112">Array of [STnefProblem](stnefproblem.md) structures.</span></span> <span data-ttu-id="8af0c-113">每个结构都包含有关属性或属性处理问题的信息。</span><span class="sxs-lookup"><span data-stu-id="8af0c-113">Each structure contains information about a property or attribute processing problem.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="8af0c-114">说明</span><span class="sxs-lookup"><span data-stu-id="8af0c-114">Remarks</span></span>

<span data-ttu-id="8af0c-115">如果在属性或属性处理过程中出现问题, 则[ITnef:: ExtractProps](itnef-extractprops.md)方法和[ITnef:: Finish](itnef-finish.md)方法中的 output 参数都会收到指向**STnefProblemArray**结构和 ExtractProps 的指针\*\*\*\* 并**完成**每个返回值 MAPI_W_ERRORS_RETURNED。</span><span class="sxs-lookup"><span data-stu-id="8af0c-115">If a problem occurs during attribute or property processing, an output parameter in the [ITnef::ExtractProps](itnef-extractprops.md) method and in the [ITnef::Finish](itnef-finish.md) method each receive a pointer to an **STnefProblemArray** structure and **ExtractProps** and **Finish** each return the value MAPI_W_ERRORS_RETURNED.</span></span> <span data-ttu-id="8af0c-116">此错误值指示在处理过程中出现问题并生成**STnefProblemArray**结构。</span><span class="sxs-lookup"><span data-stu-id="8af0c-116">This error value indicates that a problem arose during processing and an **STnefProblemArray** structure was generated.</span></span> 
  
<span data-ttu-id="8af0c-117">如果在处理属性或属性的过程中不会生成**STnefProblem**结构, 则在假定该属性或属性的处理成功的情况下, 客户端应用程序可以继续。</span><span class="sxs-lookup"><span data-stu-id="8af0c-117">If an **STnefProblem** structure is not generated during the processing of an attribute or property, the client application can continue under the assumption that the processing of that attribute or property succeeded.</span></span> <span data-ttu-id="8af0c-118">仅当在封装块解码过程中出现问题时, 才会发生此异常。</span><span class="sxs-lookup"><span data-stu-id="8af0c-118">The only exception occurs when the problem arose during decoding of an encapsulation block.</span></span> <span data-ttu-id="8af0c-119">如果在此解码过程中出现错误, 则 MAPI_E_UNABLE_TO_COMPLETE 可以作为[SCODE](scode.md)在结构中返回。</span><span class="sxs-lookup"><span data-stu-id="8af0c-119">If the error occurred during this decoding, MAPI_E_UNABLE_TO_COMPLETE can be returned as the [SCODE](scode.md) in the structure.</span></span> <span data-ttu-id="8af0c-120">在这种情况下, 将停止对与块相对应的组件进行解码, 并在另一个组件中继续解码。</span><span class="sxs-lookup"><span data-stu-id="8af0c-120">In this case, the decoding of the component corresponding to the block is stopped and decoding is continued in another component.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="8af0c-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8af0c-121">See also</span></span>



[<span data-ttu-id="8af0c-122">STnefProblem</span><span class="sxs-lookup"><span data-stu-id="8af0c-122">STnefProblem</span></span>](stnefproblem.md)
  
[<span data-ttu-id="8af0c-123">SCODE</span><span class="sxs-lookup"><span data-stu-id="8af0c-123">SCODE</span></span>](scode.md)


[<span data-ttu-id="8af0c-124">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="8af0c-124">MAPI Structures</span></span>](mapi-structures.md)

