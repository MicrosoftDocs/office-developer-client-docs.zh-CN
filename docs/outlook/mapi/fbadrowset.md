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
ms.openlocfilehash: e86e9fbf4901b5944775886f38db1ba12c4b122d
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22590958"
---
# <a name="fbadrowset"></a><span data-ttu-id="1884e-103">FBadRowSet</span><span class="sxs-lookup"><span data-stu-id="1884e-103">FBadRowSet</span></span>

  
  
<span data-ttu-id="1884e-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="1884e-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="1884e-105">验证一表格行中包含的所有表格行。</span><span class="sxs-lookup"><span data-stu-id="1884e-105">Validates all table rows included in a set of table rows.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="1884e-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="1884e-106">Header file:</span></span>  <br/> |<span data-ttu-id="1884e-107">Mapival.h</span><span class="sxs-lookup"><span data-stu-id="1884e-107">Mapival.h</span></span>  <br/> |
|<span data-ttu-id="1884e-108">通过实现：</span><span class="sxs-lookup"><span data-stu-id="1884e-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="1884e-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="1884e-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="1884e-110">调用：</span><span class="sxs-lookup"><span data-stu-id="1884e-110">Called by:</span></span>  <br/> |<span data-ttu-id="1884e-111">服务提供商</span><span class="sxs-lookup"><span data-stu-id="1884e-111">Service providers</span></span>  <br/> |
   
```cpp
BOOL FBadRowSet(
  LPSRowSet lpRowSet
);
```

## <a name="parameters"></a><span data-ttu-id="1884e-112">参数</span><span class="sxs-lookup"><span data-stu-id="1884e-112">Parameters</span></span>

 <span data-ttu-id="1884e-113">_lpRowSet_</span><span class="sxs-lookup"><span data-stu-id="1884e-113">_lpRowSet_</span></span>
  
> <span data-ttu-id="1884e-114">[in]指向[SRowSet](srowset.md)结构标识设置要验证的行的指针。</span><span class="sxs-lookup"><span data-stu-id="1884e-114">[in] Pointer to an [SRowSet](srowset.md) structure identifying the row set to be validated.</span></span> <span data-ttu-id="1884e-115">如果将指针为 NULL，则结构无效。</span><span class="sxs-lookup"><span data-stu-id="1884e-115">If the pointer is NULL, the structure is invalid.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="1884e-116">返回值</span><span class="sxs-lookup"><span data-stu-id="1884e-116">Return value</span></span>

<span data-ttu-id="1884e-117">TRUE</span><span class="sxs-lookup"><span data-stu-id="1884e-117">TRUE</span></span> 
  
> <span data-ttu-id="1884e-118">指定的行集的行无效，或行集本身无效。</span><span class="sxs-lookup"><span data-stu-id="1884e-118">A row of the specified row set is invalid, or the row set itself is invalid.</span></span> 
    
<span data-ttu-id="1884e-119">FALSE</span><span class="sxs-lookup"><span data-stu-id="1884e-119">FALSE</span></span> 
  
> <span data-ttu-id="1884e-120">指定的行集的行和行集本身均有效。</span><span class="sxs-lookup"><span data-stu-id="1884e-120">The rows of the specified row set and the row set itself are all valid.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="1884e-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1884e-121">See also</span></span>



[<span data-ttu-id="1884e-122">FBadRow</span><span class="sxs-lookup"><span data-stu-id="1884e-122">FBadRow</span></span>](fbadrow.md)

