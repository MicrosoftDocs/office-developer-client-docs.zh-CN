---
title: FBadRestriction
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- FBadRestriction
api_type:
- HeaderDef
ms.assetid: 6ad3638c-d088-4a89-9b0d-f5b672162203
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: eb3e0d5a96121f63166da2025743b7ef89f4ecf6
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33432238"
---
# <a name="fbadrestriction"></a><span data-ttu-id="fa6f5-103">FBadRestriction</span><span class="sxs-lookup"><span data-stu-id="fa6f5-103">FBadRestriction</span></span>

  
  
<span data-ttu-id="fa6f5-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="fa6f5-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="fa6f5-105">验证用于限制表视图的限制。</span><span class="sxs-lookup"><span data-stu-id="fa6f5-105">Validates a restriction used to limit a table view.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="fa6f5-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="fa6f5-106">Header file:</span></span>  <br/> |<span data-ttu-id="fa6f5-107">Mapival.h</span><span class="sxs-lookup"><span data-stu-id="fa6f5-107">Mapival.h</span></span>  <br/> |
|<span data-ttu-id="fa6f5-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="fa6f5-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="fa6f5-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="fa6f5-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="fa6f5-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="fa6f5-110">Called by:</span></span>  <br/> |<span data-ttu-id="fa6f5-111">服务提供程序</span><span class="sxs-lookup"><span data-stu-id="fa6f5-111">Service providers</span></span>  <br/> |
   
```cpp
ULONG FBadRestriction(
  LPSRestriction lpres
);
```

## <a name="parameters"></a><span data-ttu-id="fa6f5-112">参数</span><span class="sxs-lookup"><span data-stu-id="fa6f5-112">Parameters</span></span>

 <span data-ttu-id="fa6f5-113">_lpres_</span><span class="sxs-lookup"><span data-stu-id="fa6f5-113">_lpres_</span></span>
  
> <span data-ttu-id="fa6f5-114">实时定义要验证的限制的[SRestriction](srestriction.md)结构。</span><span class="sxs-lookup"><span data-stu-id="fa6f5-114">[in] An [SRestriction](srestriction.md) structure defining the restriction to be validated.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="fa6f5-115">返回值</span><span class="sxs-lookup"><span data-stu-id="fa6f5-115">Return value</span></span>

<span data-ttu-id="fa6f5-116">TRUE</span><span class="sxs-lookup"><span data-stu-id="fa6f5-116">TRUE</span></span> 
  
> <span data-ttu-id="fa6f5-117">指定的限制, 或其 subrestrictions 的一个或多个无效。</span><span class="sxs-lookup"><span data-stu-id="fa6f5-117">The specified restriction, or one or more of its subrestrictions, is invalid.</span></span> 
    
<span data-ttu-id="fa6f5-118">FALSE</span><span class="sxs-lookup"><span data-stu-id="fa6f5-118">FALSE</span></span> 
  
> <span data-ttu-id="fa6f5-119">指定的限制及其所有 subrestrictions 都是有效的。</span><span class="sxs-lookup"><span data-stu-id="fa6f5-119">The specified restriction and all its subrestrictions are valid.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="fa6f5-120">说明</span><span class="sxs-lookup"><span data-stu-id="fa6f5-120">Remarks</span></span>

<span data-ttu-id="fa6f5-121">在验证限制后, 可以将其传递给[imapitable:: Restrict](imapitable-restrict.md)方法, 以将表限制到某些行、用于查找表行的[imapitable:: FindRow](imapitable-findrow.md)方法, 以及[IMAPIContainer](imapicontainerimapiprop.md)的方法。用于对容器对象执行限制的接口。</span><span class="sxs-lookup"><span data-stu-id="fa6f5-121">Once a restriction is validated, it can be passed in calls to the [IMAPITable::Restrict](imapitable-restrict.md) method to restrict the table to certain rows, to the [IMAPITable::FindRow](imapitable-findrow.md) method to locate a table row, and to methods of the [IMAPIContainer](imapicontainerimapiprop.md) interface to perform a restriction on a container object.</span></span> 
  

