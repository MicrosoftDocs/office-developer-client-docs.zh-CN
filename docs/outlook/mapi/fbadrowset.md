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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32341018"
---
# <a name="fbadrowset"></a><span data-ttu-id="89515-103">FBadRowSet</span><span class="sxs-lookup"><span data-stu-id="89515-103">FBadRowSet</span></span>

  
  
<span data-ttu-id="89515-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="89515-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="89515-105">验证包含在一组表行中的所有表行。</span><span class="sxs-lookup"><span data-stu-id="89515-105">Validates all table rows included in a set of table rows.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="89515-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="89515-106">Header file:</span></span>  <br/> |<span data-ttu-id="89515-107">Mapival.h</span><span class="sxs-lookup"><span data-stu-id="89515-107">Mapival.h</span></span>  <br/> |
|<span data-ttu-id="89515-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="89515-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="89515-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="89515-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="89515-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="89515-110">Called by:</span></span>  <br/> |<span data-ttu-id="89515-111">服务提供程序</span><span class="sxs-lookup"><span data-stu-id="89515-111">Service providers</span></span>  <br/> |
   
```cpp
BOOL FBadRowSet(
  LPSRowSet lpRowSet
);
```

## <a name="parameters"></a><span data-ttu-id="89515-112">参数</span><span class="sxs-lookup"><span data-stu-id="89515-112">Parameters</span></span>

 <span data-ttu-id="89515-113">_lpRowSet_</span><span class="sxs-lookup"><span data-stu-id="89515-113">_lpRowSet_</span></span>
  
> <span data-ttu-id="89515-114">实时指向标识要验证的行集的[SRowSet](srowset.md)结构的指针。</span><span class="sxs-lookup"><span data-stu-id="89515-114">[in] Pointer to an [SRowSet](srowset.md) structure identifying the row set to be validated.</span></span> <span data-ttu-id="89515-115">如果指针为 NULL, 则结构无效。</span><span class="sxs-lookup"><span data-stu-id="89515-115">If the pointer is NULL, the structure is invalid.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="89515-116">返回值</span><span class="sxs-lookup"><span data-stu-id="89515-116">Return value</span></span>

<span data-ttu-id="89515-117">TRUE</span><span class="sxs-lookup"><span data-stu-id="89515-117">TRUE</span></span> 
  
> <span data-ttu-id="89515-118">指定的行集的行无效, 或行集本身无效。</span><span class="sxs-lookup"><span data-stu-id="89515-118">A row of the specified row set is invalid, or the row set itself is invalid.</span></span> 
    
<span data-ttu-id="89515-119">FALSE</span><span class="sxs-lookup"><span data-stu-id="89515-119">FALSE</span></span> 
  
> <span data-ttu-id="89515-120">指定的行集和行集本身的行都是有效的。</span><span class="sxs-lookup"><span data-stu-id="89515-120">The rows of the specified row set and the row set itself are all valid.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="89515-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="89515-121">See also</span></span>



[<span data-ttu-id="89515-122">FBadRow</span><span class="sxs-lookup"><span data-stu-id="89515-122">FBadRow</span></span>](fbadrow.md)

