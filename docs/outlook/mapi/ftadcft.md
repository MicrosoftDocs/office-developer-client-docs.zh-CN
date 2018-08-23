---
title: FtAdcFt
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 2635a829-0f3a-49ed-a672-2f350a2cf979
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: f073dbb9655585ee56ab38be35bea4ef320042c0
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22569769"
---
# <a name="ftadcft"></a><span data-ttu-id="bc5af-103">FtAdcFt</span><span class="sxs-lookup"><span data-stu-id="bc5af-103">FtAdcFt</span></span>

  
  
<span data-ttu-id="bc5af-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="bc5af-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="bc5af-105">向另一个，（可选） 使用携带标志添加一个无符号的 64 位整数。</span><span class="sxs-lookup"><span data-stu-id="bc5af-105">Adds one unsigned 64-bit integer to another, optionally using a carry flag.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="bc5af-106">通过实现：</span><span class="sxs-lookup"><span data-stu-id="bc5af-106">Implemented by:</span></span>  <br/> |<span data-ttu-id="bc5af-107">MAPI</span><span class="sxs-lookup"><span data-stu-id="bc5af-107">MAPI</span></span>  <br/> |
|<span data-ttu-id="bc5af-108">调用：</span><span class="sxs-lookup"><span data-stu-id="bc5af-108">Called by:</span></span>  <br/> |<span data-ttu-id="bc5af-109">客户端应用程序和服务提供商</span><span class="sxs-lookup"><span data-stu-id="bc5af-109">Client applications and service providers</span></span>  <br/> |
   
```cpp
FILETIME FtAdcFt( 
  FILETIME ft1, 
  FILETIME ft2, 
  WORD FAR *pwCarry
);
```

## <a name="parameters"></a><span data-ttu-id="bc5af-110">参数</span><span class="sxs-lookup"><span data-stu-id="bc5af-110">Parameters</span></span>

 <span data-ttu-id="bc5af-111">_ft1_</span><span class="sxs-lookup"><span data-stu-id="bc5af-111">_ft1_</span></span>
  
> <span data-ttu-id="bc5af-112">[in]包含的第一个无符号的 64 位整数，要添加的[FILETIME](filetime.md)结构。</span><span class="sxs-lookup"><span data-stu-id="bc5af-112">[in] A [FILETIME](filetime.md) structure that contains the first unsigned 64-bit integer to be added.</span></span> 
    
 <span data-ttu-id="bc5af-113">_ft2_</span><span class="sxs-lookup"><span data-stu-id="bc5af-113">_ft2_</span></span>
  
> <span data-ttu-id="bc5af-114">[in]包含的第二个无符号的 64 位整数，要添加的 FILETIME 结构。</span><span class="sxs-lookup"><span data-stu-id="bc5af-114">[in] A FILETIME structure that contains the second unsigned 64-bit integer to be added.</span></span>
    
 <span data-ttu-id="bc5af-115">_pwCarry_</span><span class="sxs-lookup"><span data-stu-id="bc5af-115">_pwCarry_</span></span>
  
> <span data-ttu-id="bc5af-116">[传入、 传出，可选]在输入时，指向传入的执行标志。</span><span class="sxs-lookup"><span data-stu-id="bc5af-116">[in, out, optional] On input, a pointer to the incoming carry flag.</span></span> <span data-ttu-id="bc5af-117">在输出，指向增加的执行结果的指针。</span><span class="sxs-lookup"><span data-stu-id="bc5af-117">On output, a pointer to the carry result for the addition.</span></span> <span data-ttu-id="bc5af-118">如果要结果，则不需要此参数可以是 NULL。</span><span class="sxs-lookup"><span data-stu-id="bc5af-118">This parameter can be NULL if the carry result is not required.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="bc5af-119">返回值</span><span class="sxs-lookup"><span data-stu-id="bc5af-119">Return value</span></span>

<span data-ttu-id="bc5af-120">**FtAdcFt**函数将返回一个**FILETIME**结构，其中包含两个包含整数的总和。</span><span class="sxs-lookup"><span data-stu-id="bc5af-120">The **FtAdcFt** function returns a **FILETIME** structure that contains the sum of the two integers.</span></span> <span data-ttu-id="bc5af-121">两个输入的参数保持不变。</span><span class="sxs-lookup"><span data-stu-id="bc5af-121">The two input parameters remain unchanged.</span></span> <span data-ttu-id="bc5af-122">如果**pwCarry**为非 NULL，则它包含的执行结果 sum、 0 或 1。</span><span class="sxs-lookup"><span data-stu-id="bc5af-122">If **pwCarry** is non-NULL, it contains the carry result for the sum, either 0 or 1.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="bc5af-123">注解</span><span class="sxs-lookup"><span data-stu-id="bc5af-123">Remarks</span></span>

<span data-ttu-id="bc5af-124">**FtAdcFt**函数等同于**FtAddFt** _pwCarry_为 NULL 时。</span><span class="sxs-lookup"><span data-stu-id="bc5af-124">The **FtAdcFt** function is identical to **FtAddFt** when  _pwCarry_ is NULL.</span></span> <span data-ttu-id="bc5af-125">如果_pwCarry_不为 NULL，并指向 0， **FtAdcFt**返回**FtAddFt**返回的同一个**FILETIME**值。</span><span class="sxs-lookup"><span data-stu-id="bc5af-125">If  _pwCarry_ is not NULL and points to 0, **FtAdcFt** returns the same **FILETIME** value that **FtAddFt** returns.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="bc5af-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bc5af-126">See also</span></span>



[<span data-ttu-id="bc5af-127">FtAddFt</span><span class="sxs-lookup"><span data-stu-id="bc5af-127">FtAddFt</span></span>](ftaddft.md)

