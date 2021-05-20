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
# <a name="fbadrestriction"></a><span data-ttu-id="895dc-103">FBadRestriction</span><span class="sxs-lookup"><span data-stu-id="895dc-103">FBadRestriction</span></span>

  
  
<span data-ttu-id="895dc-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="895dc-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="895dc-105">验证用于限制表视图的限制。</span><span class="sxs-lookup"><span data-stu-id="895dc-105">Validates a restriction used to limit a table view.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="895dc-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="895dc-106">Header file:</span></span>  <br/> |<span data-ttu-id="895dc-107">Mapival.h</span><span class="sxs-lookup"><span data-stu-id="895dc-107">Mapival.h</span></span>  <br/> |
|<span data-ttu-id="895dc-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="895dc-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="895dc-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="895dc-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="895dc-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="895dc-110">Called by:</span></span>  <br/> |<span data-ttu-id="895dc-111">服务提供程序</span><span class="sxs-lookup"><span data-stu-id="895dc-111">Service providers</span></span>  <br/> |
   
```cpp
ULONG FBadRestriction(
  LPSRestriction lpres
);
```

## <a name="parameters"></a><span data-ttu-id="895dc-112">参数</span><span class="sxs-lookup"><span data-stu-id="895dc-112">Parameters</span></span>

 <span data-ttu-id="895dc-113">_lpres_</span><span class="sxs-lookup"><span data-stu-id="895dc-113">_lpres_</span></span>
  
> <span data-ttu-id="895dc-114">[in] [定义要验证的限制的 SRestriction](srestriction.md) 结构。</span><span class="sxs-lookup"><span data-stu-id="895dc-114">[in] An [SRestriction](srestriction.md) structure defining the restriction to be validated.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="895dc-115">返回值</span><span class="sxs-lookup"><span data-stu-id="895dc-115">Return value</span></span>

<span data-ttu-id="895dc-116">TRUE</span><span class="sxs-lookup"><span data-stu-id="895dc-116">TRUE</span></span> 
  
> <span data-ttu-id="895dc-117">指定的限制（或它的一个或多个子限制）无效。</span><span class="sxs-lookup"><span data-stu-id="895dc-117">The specified restriction, or one or more of its subrestrictions, is invalid.</span></span> 
    
<span data-ttu-id="895dc-118">FALSE</span><span class="sxs-lookup"><span data-stu-id="895dc-118">FALSE</span></span> 
  
> <span data-ttu-id="895dc-119">指定的限制及其所有子范围均有效。</span><span class="sxs-lookup"><span data-stu-id="895dc-119">The specified restriction and all its subrestrictions are valid.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="895dc-120">备注</span><span class="sxs-lookup"><span data-stu-id="895dc-120">Remarks</span></span>

<span data-ttu-id="895dc-121">验证限制后，可以传入 [对 IMAPITable：：Restrict](imapitable-restrict.md) 方法的调用，以将表限制为特定行、将表限制为查找表行的 [IMAPITable：：FindRow](imapitable-findrow.md) 方法，以及 [IMAPIContainer](imapicontainerimapiprop.md) 接口的方法，以对容器对象执行限制。</span><span class="sxs-lookup"><span data-stu-id="895dc-121">Once a restriction is validated, it can be passed in calls to the [IMAPITable::Restrict](imapitable-restrict.md) method to restrict the table to certain rows, to the [IMAPITable::FindRow](imapitable-findrow.md) method to locate a table row, and to methods of the [IMAPIContainer](imapicontainerimapiprop.md) interface to perform a restriction on a container object.</span></span> 
  

