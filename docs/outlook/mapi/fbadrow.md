---
title: FBadRow
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.FBadRow
api_type:
- COM
ms.assetid: 205d00df-488d-4888-8782-a1f70f54d720
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: c3025c353c71958a19303c5e79cec319a3bf8015
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774929"
---
# <a name="fbadrow"></a><span data-ttu-id="fd3b3-103">FBadRow</span><span class="sxs-lookup"><span data-stu-id="fd3b3-103">FBadRow</span></span>

  
  
<span data-ttu-id="fd3b3-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="fd3b3-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="fd3b3-105">验证表中的行。</span><span class="sxs-lookup"><span data-stu-id="fd3b3-105">Validates a row in a table.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="fd3b3-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="fd3b3-106">Header file:</span></span>  <br/> |<span data-ttu-id="fd3b3-107">Mapival.h</span><span class="sxs-lookup"><span data-stu-id="fd3b3-107">Mapival.h</span></span>  <br/> |
|<span data-ttu-id="fd3b3-108">通过实现：</span><span class="sxs-lookup"><span data-stu-id="fd3b3-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="fd3b3-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="fd3b3-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="fd3b3-110">调用：</span><span class="sxs-lookup"><span data-stu-id="fd3b3-110">Called by:</span></span>  <br/> |<span data-ttu-id="fd3b3-111">服务提供商</span><span class="sxs-lookup"><span data-stu-id="fd3b3-111">Service providers</span></span>  <br/> |
   
```cpp
ULONG FBadRow(
  LPSRow lprow
);
```

## <a name="parameters"></a><span data-ttu-id="fd3b3-112">参数</span><span class="sxs-lookup"><span data-stu-id="fd3b3-112">Parameters</span></span>

 <span data-ttu-id="fd3b3-113">_lprow_</span><span class="sxs-lookup"><span data-stu-id="fd3b3-113">_lprow_</span></span>
  
> <span data-ttu-id="fd3b3-114">[in]标识要验证的行[SRow](srow.md)结构的指针。</span><span class="sxs-lookup"><span data-stu-id="fd3b3-114">[in] Pointer to an [SRow](srow.md) structure identifying the row to be validated.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="fd3b3-115">返回值</span><span class="sxs-lookup"><span data-stu-id="fd3b3-115">Return value</span></span>

<span data-ttu-id="fd3b3-116">TRUE</span><span class="sxs-lookup"><span data-stu-id="fd3b3-116">TRUE</span></span> 
  
> <span data-ttu-id="fd3b3-117">指定的行无效。</span><span class="sxs-lookup"><span data-stu-id="fd3b3-117">The specified row is invalid.</span></span>
    
<span data-ttu-id="fd3b3-118">FALSE</span><span class="sxs-lookup"><span data-stu-id="fd3b3-118">FALSE</span></span> 
  
> <span data-ttu-id="fd3b3-119">指定的行是有效的。</span><span class="sxs-lookup"><span data-stu-id="fd3b3-119">The specified row is valid.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="fd3b3-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fd3b3-120">See also</span></span>



[<span data-ttu-id="fd3b3-121">FBadRowSet</span><span class="sxs-lookup"><span data-stu-id="fd3b3-121">FBadRowSet</span></span>](fbadrowset.md)

