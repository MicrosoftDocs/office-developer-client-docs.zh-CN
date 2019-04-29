---
title: FBadRowSet
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.FBadRowSet
api_type:
- COM
ms.assetid: 3890dd50-e6ca-4859-bada-f6752ab61d41
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 49e6c8254cbd527635685c3f974da57ee3ac82a5
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33411790"
---
# <a name="fbadrowset"></a><span data-ttu-id="7e30f-103">FBadRowSet</span><span class="sxs-lookup"><span data-stu-id="7e30f-103">FBadRowSet</span></span>

  
  
<span data-ttu-id="7e30f-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="7e30f-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="7e30f-105">验证包含在一组表行中的所有表行。</span><span class="sxs-lookup"><span data-stu-id="7e30f-105">Validates all table rows included in a set of table rows.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="7e30f-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="7e30f-106">Header file:</span></span>  <br/> |<span data-ttu-id="7e30f-107">Mapival.h</span><span class="sxs-lookup"><span data-stu-id="7e30f-107">Mapival.h</span></span>  <br/> |
|<span data-ttu-id="7e30f-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="7e30f-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="7e30f-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="7e30f-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="7e30f-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="7e30f-110">Called by:</span></span>  <br/> |<span data-ttu-id="7e30f-111">服务提供程序</span><span class="sxs-lookup"><span data-stu-id="7e30f-111">Service providers</span></span>  <br/> |
   
```cpp
BOOL FBadRowSet(
  LPSRowSet lpRowSet
);
```

## <a name="parameters"></a><span data-ttu-id="7e30f-112">参数</span><span class="sxs-lookup"><span data-stu-id="7e30f-112">Parameters</span></span>

 <span data-ttu-id="7e30f-113">_lpRowSet_</span><span class="sxs-lookup"><span data-stu-id="7e30f-113">_lpRowSet_</span></span>
  
> <span data-ttu-id="7e30f-114">实时指向标识要验证的行集的[SRowSet](srowset.md)结构的指针。</span><span class="sxs-lookup"><span data-stu-id="7e30f-114">[in] Pointer to an [SRowSet](srowset.md) structure identifying the row set to be validated.</span></span> <span data-ttu-id="7e30f-115">如果指针为 NULL, 则结构无效。</span><span class="sxs-lookup"><span data-stu-id="7e30f-115">If the pointer is NULL, the structure is invalid.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="7e30f-116">返回值</span><span class="sxs-lookup"><span data-stu-id="7e30f-116">Return value</span></span>

<span data-ttu-id="7e30f-117">TRUE</span><span class="sxs-lookup"><span data-stu-id="7e30f-117">TRUE</span></span> 
  
> <span data-ttu-id="7e30f-118">指定的行集的行无效, 或行集本身无效。</span><span class="sxs-lookup"><span data-stu-id="7e30f-118">A row of the specified row set is invalid, or the row set itself is invalid.</span></span> 
    
<span data-ttu-id="7e30f-119">FALSE</span><span class="sxs-lookup"><span data-stu-id="7e30f-119">FALSE</span></span> 
  
> <span data-ttu-id="7e30f-120">指定的行集和行集本身的行都是有效的。</span><span class="sxs-lookup"><span data-stu-id="7e30f-120">The rows of the specified row set and the row set itself are all valid.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="7e30f-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7e30f-121">See also</span></span>



[<span data-ttu-id="7e30f-122">FBadRow</span><span class="sxs-lookup"><span data-stu-id="7e30f-122">FBadRow</span></span>](fbadrow.md)

