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
ms.openlocfilehash: baa2ac2e859b42234fcb07dd2bf521424ef9b465
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778904"
---
# <a name="stnefproblemarray"></a><span data-ttu-id="3389a-103">STnefProblemArray</span><span class="sxs-lookup"><span data-stu-id="3389a-103">STnefProblemArray</span></span>

  
  
<span data-ttu-id="3389a-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="3389a-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="3389a-105">包含描述一个或多个处理的编码期间出现的问题或解码传输中性封装格式 (TNEF) 可将 stream 的**STnefProblem**结构的数组。</span><span class="sxs-lookup"><span data-stu-id="3389a-105">Contains an array of **STnefProblem** structures describing one or more processing problems that occurred during the encoding or decoding of a Transport Neutral Encapsulation Format (TNEF) stream.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="3389a-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="3389a-106">Header file:</span></span>  <br/> |<span data-ttu-id="3389a-107">Tnef.h</span><span class="sxs-lookup"><span data-stu-id="3389a-107">Tnef.h</span></span>  <br/> |
   
```cpp
typedef struct _STnefProblemArray
{
  ULONG cProblem;
  STnefProblem aProblem[MAPI_DIM];
}STnefProblemArray, FAR * LPSTnefProblemArray

```

## <a name="members"></a><span data-ttu-id="3389a-108">Members</span><span class="sxs-lookup"><span data-stu-id="3389a-108">Members</span></span>

 <span data-ttu-id="3389a-109">**cProblem**</span><span class="sxs-lookup"><span data-stu-id="3389a-109">**cProblem**</span></span>
  
> <span data-ttu-id="3389a-110">指定在**aProblem**成员中声明的数组中的元素的计数。</span><span class="sxs-lookup"><span data-stu-id="3389a-110">Count of elements in the array specified in the **aProblem** member.</span></span> 
    
 <span data-ttu-id="3389a-111">**aProblem**</span><span class="sxs-lookup"><span data-stu-id="3389a-111">**aProblem**</span></span>
  
> <span data-ttu-id="3389a-112">[STnefProblem](stnefproblem.md)结构的数组。</span><span class="sxs-lookup"><span data-stu-id="3389a-112">Array of [STnefProblem](stnefproblem.md) structures.</span></span> <span data-ttu-id="3389a-113">每个结构包含有关的属性或特性处理问题的信息。</span><span class="sxs-lookup"><span data-stu-id="3389a-113">Each structure contains information about a property or attribute processing problem.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="3389a-114">说明</span><span class="sxs-lookup"><span data-stu-id="3389a-114">Remarks</span></span>

<span data-ttu-id="3389a-115">输出参数在[ITnef::ExtractProps](itnef-extractprops.md)方法并在每个[ITnef::Finish](itnef-finish.md)方法属性或属性处理过程中出现问题，如果收到一个指向**STnefProblemArray**结构和**ExtractProps**并**完成**每个返回 MAPI_W_ERRORS_RETURNED 的值。</span><span class="sxs-lookup"><span data-stu-id="3389a-115">If a problem occurs during attribute or property processing, an output parameter in the [ITnef::ExtractProps](itnef-extractprops.md) method and in the [ITnef::Finish](itnef-finish.md) method each receive a pointer to an **STnefProblemArray** structure and **ExtractProps** and **Finish** each return the value MAPI_W_ERRORS_RETURNED.</span></span> <span data-ttu-id="3389a-116">此错误值指示处理过程中出现的问题和生成**STnefProblemArray**结构。</span><span class="sxs-lookup"><span data-stu-id="3389a-116">This error value indicates that a problem arose during processing and an **STnefProblemArray** structure was generated.</span></span> 
  
<span data-ttu-id="3389a-117">如果属性或属性的处理过程中未生成**STnefProblem**结构，客户端应用程序可以继续处理属性或属性的成功假定下。</span><span class="sxs-lookup"><span data-stu-id="3389a-117">If an **STnefProblem** structure is not generated during the processing of an attribute or property, the client application can continue under the assumption that the processing of that attribute or property succeeded.</span></span> <span data-ttu-id="3389a-118">解码封装块的过程中出现问题时，发生此事件唯一的例外。</span><span class="sxs-lookup"><span data-stu-id="3389a-118">The only exception occurs when the problem arose during decoding of an encapsulation block.</span></span> <span data-ttu-id="3389a-119">如果此解码期间发生错误，则可以作为[SCODE](scode.md)结构中返回 MAPI_E_UNABLE_TO_COMPLETE。</span><span class="sxs-lookup"><span data-stu-id="3389a-119">If the error occurred during this decoding, MAPI_E_UNABLE_TO_COMPLETE can be returned as the [SCODE](scode.md) in the structure.</span></span> <span data-ttu-id="3389a-120">在这种情况下，解码阻止到相应的组件已停止，解码继续使用在另一个组件。</span><span class="sxs-lookup"><span data-stu-id="3389a-120">In this case, the decoding of the component corresponding to the block is stopped and decoding is continued in another component.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="3389a-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3389a-121">See also</span></span>



[<span data-ttu-id="3389a-122">STnefProblem</span><span class="sxs-lookup"><span data-stu-id="3389a-122">STnefProblem</span></span>](stnefproblem.md)
  
[<span data-ttu-id="3389a-123">SCODE</span><span class="sxs-lookup"><span data-stu-id="3389a-123">SCODE</span></span>](scode.md)


[<span data-ttu-id="3389a-124">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="3389a-124">MAPI Structures</span></span>](mapi-structures.md)

