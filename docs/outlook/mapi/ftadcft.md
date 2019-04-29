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
ms.openlocfilehash: f308c1f6f3cd2c9904dd94cd6761517bd5b410b6
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33429703"
---
# <a name="ftadcft"></a><span data-ttu-id="64e76-103">FtAdcFt</span><span class="sxs-lookup"><span data-stu-id="64e76-103">FtAdcFt</span></span>

  
  
<span data-ttu-id="64e76-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="64e76-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="64e76-105">将一个无符号64位整数添加到另一个, 可以选择使用带有标志。</span><span class="sxs-lookup"><span data-stu-id="64e76-105">Adds one unsigned 64-bit integer to another, optionally using a carry flag.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="64e76-106">实现者：</span><span class="sxs-lookup"><span data-stu-id="64e76-106">Implemented by:</span></span>  <br/> |<span data-ttu-id="64e76-107">MAPI</span><span class="sxs-lookup"><span data-stu-id="64e76-107">MAPI</span></span>  <br/> |
|<span data-ttu-id="64e76-108">调用者：</span><span class="sxs-lookup"><span data-stu-id="64e76-108">Called by:</span></span>  <br/> |<span data-ttu-id="64e76-109">客户端应用程序和服务提供程序</span><span class="sxs-lookup"><span data-stu-id="64e76-109">Client applications and service providers</span></span>  <br/> |
   
```cpp
FILETIME FtAdcFt( 
  FILETIME ft1, 
  FILETIME ft2, 
  WORD FAR *pwCarry
);
```

## <a name="parameters"></a><span data-ttu-id="64e76-110">参数</span><span class="sxs-lookup"><span data-stu-id="64e76-110">Parameters</span></span>

 <span data-ttu-id="64e76-111">_ft1_</span><span class="sxs-lookup"><span data-stu-id="64e76-111">_ft1_</span></span>
  
> <span data-ttu-id="64e76-112">实时一个[FILETIME](filetime.md)结构, 其中包含要添加的第一个不带符号的64位整数。</span><span class="sxs-lookup"><span data-stu-id="64e76-112">[in] A [FILETIME](filetime.md) structure that contains the first unsigned 64-bit integer to be added.</span></span> 
    
 <span data-ttu-id="64e76-113">_ft2_</span><span class="sxs-lookup"><span data-stu-id="64e76-113">_ft2_</span></span>
  
> <span data-ttu-id="64e76-114">实时一个 FILETIME 结构, 其中包含要添加的第二个带符号的64位整数。</span><span class="sxs-lookup"><span data-stu-id="64e76-114">[in] A FILETIME structure that contains the second unsigned 64-bit integer to be added.</span></span>
    
 <span data-ttu-id="64e76-115">_pwCarry_</span><span class="sxs-lookup"><span data-stu-id="64e76-115">_pwCarry_</span></span>
  
> <span data-ttu-id="64e76-116">[in、out、optional]在输入时, 指向传入的传输标志的指针。</span><span class="sxs-lookup"><span data-stu-id="64e76-116">[in, out, optional] On input, a pointer to the incoming carry flag.</span></span> <span data-ttu-id="64e76-117">在输出时, 指向添加项的承载结果的指针。</span><span class="sxs-lookup"><span data-stu-id="64e76-117">On output, a pointer to the carry result for the addition.</span></span> <span data-ttu-id="64e76-118">如果不需要 "执行" 结果, 则此参数可以为 NULL。</span><span class="sxs-lookup"><span data-stu-id="64e76-118">This parameter can be NULL if the carry result is not required.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="64e76-119">返回值</span><span class="sxs-lookup"><span data-stu-id="64e76-119">Return value</span></span>

<span data-ttu-id="64e76-120">**FtAdcFt**函数返回一个**FILETIME**结构, 其中包含两个整数的和。</span><span class="sxs-lookup"><span data-stu-id="64e76-120">The **FtAdcFt** function returns a **FILETIME** structure that contains the sum of the two integers.</span></span> <span data-ttu-id="64e76-121">这两个输入参数保持不变。</span><span class="sxs-lookup"><span data-stu-id="64e76-121">The two input parameters remain unchanged.</span></span> <span data-ttu-id="64e76-122">如果**pwCarry**为非 NULL, 则它包含总和的包含结果, 即0或1。</span><span class="sxs-lookup"><span data-stu-id="64e76-122">If **pwCarry** is non-NULL, it contains the carry result for the sum, either 0 or 1.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="64e76-123">说明</span><span class="sxs-lookup"><span data-stu-id="64e76-123">Remarks</span></span>

<span data-ttu-id="64e76-124">当_pwCarry_为 NULL 时, **FtAdcFt**函数等同于**FtAddFt** 。</span><span class="sxs-lookup"><span data-stu-id="64e76-124">The **FtAdcFt** function is identical to **FtAddFt** when  _pwCarry_ is NULL.</span></span> <span data-ttu-id="64e76-125">如果_pwCarry_不为 NULL, 并指向 0, 则**FtAdcFt**将返回**FtAddFt**返回的同一**FILETIME**值。</span><span class="sxs-lookup"><span data-stu-id="64e76-125">If  _pwCarry_ is not NULL and points to 0, **FtAdcFt** returns the same **FILETIME** value that **FtAddFt** returns.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="64e76-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="64e76-126">See also</span></span>



[<span data-ttu-id="64e76-127">FtAddFt</span><span class="sxs-lookup"><span data-stu-id="64e76-127">FtAddFt</span></span>](ftaddft.md)

