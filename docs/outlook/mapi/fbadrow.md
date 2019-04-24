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
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 153bcbfd87ea9e85d834cba2fd9028e98fa25750
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32340955"
---
# <a name="fbadrow"></a><span data-ttu-id="daeed-103">FBadRow</span><span class="sxs-lookup"><span data-stu-id="daeed-103">FBadRow</span></span>

  
  
<span data-ttu-id="daeed-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="daeed-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="daeed-105">验证表中的行。</span><span class="sxs-lookup"><span data-stu-id="daeed-105">Validates a row in a table.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="daeed-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="daeed-106">Header file:</span></span>  <br/> |<span data-ttu-id="daeed-107">Mapival.h</span><span class="sxs-lookup"><span data-stu-id="daeed-107">Mapival.h</span></span>  <br/> |
|<span data-ttu-id="daeed-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="daeed-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="daeed-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="daeed-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="daeed-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="daeed-110">Called by:</span></span>  <br/> |<span data-ttu-id="daeed-111">服务提供程序</span><span class="sxs-lookup"><span data-stu-id="daeed-111">Service providers</span></span>  <br/> |
   
```cpp
ULONG FBadRow(
  LPSRow lprow
);
```

## <a name="parameters"></a><span data-ttu-id="daeed-112">参数</span><span class="sxs-lookup"><span data-stu-id="daeed-112">Parameters</span></span>

 <span data-ttu-id="daeed-113">_lprow_</span><span class="sxs-lookup"><span data-stu-id="daeed-113">_lprow_</span></span>
  
> <span data-ttu-id="daeed-114">实时指向标识要验证的行的[SRow](srow.md)结构的指针。</span><span class="sxs-lookup"><span data-stu-id="daeed-114">[in] Pointer to an [SRow](srow.md) structure identifying the row to be validated.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="daeed-115">返回值</span><span class="sxs-lookup"><span data-stu-id="daeed-115">Return value</span></span>

<span data-ttu-id="daeed-116">TRUE</span><span class="sxs-lookup"><span data-stu-id="daeed-116">TRUE</span></span> 
  
> <span data-ttu-id="daeed-117">指定的行无效。</span><span class="sxs-lookup"><span data-stu-id="daeed-117">The specified row is invalid.</span></span>
    
<span data-ttu-id="daeed-118">FALSE</span><span class="sxs-lookup"><span data-stu-id="daeed-118">FALSE</span></span> 
  
> <span data-ttu-id="daeed-119">指定的行有效。</span><span class="sxs-lookup"><span data-stu-id="daeed-119">The specified row is valid.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="daeed-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="daeed-120">See also</span></span>



[<span data-ttu-id="daeed-121">FBadRowSet</span><span class="sxs-lookup"><span data-stu-id="daeed-121">FBadRowSet</span></span>](fbadrowset.md)

