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
# <a name="ftadcft"></a><span data-ttu-id="ca334-103">FtAdcFt</span><span class="sxs-lookup"><span data-stu-id="ca334-103">FtAdcFt</span></span>

  
  
<span data-ttu-id="ca334-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="ca334-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="ca334-105">将一个无符号 64 位整数添加到另一个整数（可选）使用一个携带标志。</span><span class="sxs-lookup"><span data-stu-id="ca334-105">Adds one unsigned 64-bit integer to another, optionally using a carry flag.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="ca334-106">实现者：</span><span class="sxs-lookup"><span data-stu-id="ca334-106">Implemented by:</span></span>  <br/> |<span data-ttu-id="ca334-107">MAPI</span><span class="sxs-lookup"><span data-stu-id="ca334-107">MAPI</span></span>  <br/> |
|<span data-ttu-id="ca334-108">调用者：</span><span class="sxs-lookup"><span data-stu-id="ca334-108">Called by:</span></span>  <br/> |<span data-ttu-id="ca334-109">客户端应用程序和服务提供商</span><span class="sxs-lookup"><span data-stu-id="ca334-109">Client applications and service providers</span></span>  <br/> |
   
```cpp
FILETIME FtAdcFt( 
  FILETIME ft1, 
  FILETIME ft2, 
  WORD FAR *pwCarry
);
```

## <a name="parameters"></a><span data-ttu-id="ca334-110">参数</span><span class="sxs-lookup"><span data-stu-id="ca334-110">Parameters</span></span>

 <span data-ttu-id="ca334-111">_ft1_</span><span class="sxs-lookup"><span data-stu-id="ca334-111">_ft1_</span></span>
  
> <span data-ttu-id="ca334-112">[in] [FILETIME](filetime.md) 结构，包含要添加的第一个无符号 64 位整数。</span><span class="sxs-lookup"><span data-stu-id="ca334-112">[in] A [FILETIME](filetime.md) structure that contains the first unsigned 64-bit integer to be added.</span></span> 
    
 <span data-ttu-id="ca334-113">_ft2_</span><span class="sxs-lookup"><span data-stu-id="ca334-113">_ft2_</span></span>
  
> <span data-ttu-id="ca334-114">[in]FILETIME 结构，包含要添加的第二个无符号 64 位整数。</span><span class="sxs-lookup"><span data-stu-id="ca334-114">[in] A FILETIME structure that contains the second unsigned 64-bit integer to be added.</span></span>
    
 <span data-ttu-id="ca334-115">_pwCarry_</span><span class="sxs-lookup"><span data-stu-id="ca334-115">_pwCarry_</span></span>
  
> <span data-ttu-id="ca334-116">[in、out、optional]输入时，指向传入的携带标志的指针。</span><span class="sxs-lookup"><span data-stu-id="ca334-116">[in, out, optional] On input, a pointer to the incoming carry flag.</span></span> <span data-ttu-id="ca334-117">输出时，指向加法结果的指针。</span><span class="sxs-lookup"><span data-stu-id="ca334-117">On output, a pointer to the carry result for the addition.</span></span> <span data-ttu-id="ca334-118">如果不需要执行结果，则此参数可以是 NULL。</span><span class="sxs-lookup"><span data-stu-id="ca334-118">This parameter can be NULL if the carry result is not required.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="ca334-119">返回值</span><span class="sxs-lookup"><span data-stu-id="ca334-119">Return value</span></span>

<span data-ttu-id="ca334-120">**FtAdcFt** 函数返回 **FILETIME** 结构，其中包含两个整数的总和。</span><span class="sxs-lookup"><span data-stu-id="ca334-120">The **FtAdcFt** function returns a **FILETIME** structure that contains the sum of the two integers.</span></span> <span data-ttu-id="ca334-121">两个输入参数保持不变。</span><span class="sxs-lookup"><span data-stu-id="ca334-121">The two input parameters remain unchanged.</span></span> <span data-ttu-id="ca334-122">如果 **pwCarry** 为非 NULL，则它包含和的携带结果，可以是 0 或 1。</span><span class="sxs-lookup"><span data-stu-id="ca334-122">If **pwCarry** is non-NULL, it contains the carry result for the sum, either 0 or 1.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="ca334-123">备注</span><span class="sxs-lookup"><span data-stu-id="ca334-123">Remarks</span></span>

<span data-ttu-id="ca334-124">当 _pwCarry_ 为 NULL 时 **，FtAdcFt** 函数与 **FtAddFt** 相同。</span><span class="sxs-lookup"><span data-stu-id="ca334-124">The **FtAdcFt** function is identical to **FtAddFt** when  _pwCarry_ is NULL.</span></span> <span data-ttu-id="ca334-125">如果 _pwCarry_ 不为 NULL 且指向 0，**则 FtAdcFt** 将返回 **FtAddFt** 返回的同一 **FILETIME** 值。</span><span class="sxs-lookup"><span data-stu-id="ca334-125">If  _pwCarry_ is not NULL and points to 0, **FtAdcFt** returns the same **FILETIME** value that **FtAddFt** returns.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="ca334-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ca334-126">See also</span></span>



[<span data-ttu-id="ca334-127">FtAddFt</span><span class="sxs-lookup"><span data-stu-id="ca334-127">FtAddFt</span></span>](ftaddft.md)

