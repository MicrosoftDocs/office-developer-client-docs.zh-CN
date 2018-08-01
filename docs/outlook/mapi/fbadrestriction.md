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
ms.openlocfilehash: 43e0d8d28836b3114ab2029bc1f241197c569ffc
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774909"
---
# <a name="fbadrestriction"></a><span data-ttu-id="f1152-103">FBadRestriction</span><span class="sxs-lookup"><span data-stu-id="f1152-103">FBadRestriction</span></span>

  
  
<span data-ttu-id="f1152-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="f1152-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="f1152-105">验证用于限制表视图的限制。</span><span class="sxs-lookup"><span data-stu-id="f1152-105">Validates a restriction used to limit a table view.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="f1152-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="f1152-106">Header file:</span></span>  <br/> |<span data-ttu-id="f1152-107">Mapival.h</span><span class="sxs-lookup"><span data-stu-id="f1152-107">Mapival.h</span></span>  <br/> |
|<span data-ttu-id="f1152-108">通过实现：</span><span class="sxs-lookup"><span data-stu-id="f1152-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="f1152-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="f1152-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="f1152-110">调用：</span><span class="sxs-lookup"><span data-stu-id="f1152-110">Called by:</span></span>  <br/> |<span data-ttu-id="f1152-111">服务提供商</span><span class="sxs-lookup"><span data-stu-id="f1152-111">Service providers</span></span>  <br/> |
   
```cpp
ULONG FBadRestriction(
  LPSRestriction lpres
);
```

## <a name="parameters"></a><span data-ttu-id="f1152-112">参数</span><span class="sxs-lookup"><span data-stu-id="f1152-112">Parameters</span></span>

 <span data-ttu-id="f1152-113">_lpres_</span><span class="sxs-lookup"><span data-stu-id="f1152-113">_lpres_</span></span>
  
> <span data-ttu-id="f1152-114">[in]定义要验证的限制[SRestriction](srestriction.md)结构。</span><span class="sxs-lookup"><span data-stu-id="f1152-114">[in] An [SRestriction](srestriction.md) structure defining the restriction to be validated.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="f1152-115">返回值</span><span class="sxs-lookup"><span data-stu-id="f1152-115">Return value</span></span>

<span data-ttu-id="f1152-116">TRUE</span><span class="sxs-lookup"><span data-stu-id="f1152-116">TRUE</span></span> 
  
> <span data-ttu-id="f1152-117">指定的限制，或一个或多个其 subrestrictions，无效。</span><span class="sxs-lookup"><span data-stu-id="f1152-117">The specified restriction, or one or more of its subrestrictions, is invalid.</span></span> 
    
<span data-ttu-id="f1152-118">FALSE</span><span class="sxs-lookup"><span data-stu-id="f1152-118">FALSE</span></span> 
  
> <span data-ttu-id="f1152-119">指定的限制和所有 subrestrictions 有效。</span><span class="sxs-lookup"><span data-stu-id="f1152-119">The specified restriction and all its subrestrictions are valid.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="f1152-120">说明</span><span class="sxs-lookup"><span data-stu-id="f1152-120">Remarks</span></span>

<span data-ttu-id="f1152-121">一旦限制进行验证后，可以传递给[IMAPITable::Restrict](imapitable-restrict.md)方法的呼叫来为特定行、 [IMAPITable::FindRow](imapitable-findrow.md)方法查找表行和[IMAPIContainer](imapicontainerimapiprop.md)的方法限制表中对 container 对象执行限制的接口。</span><span class="sxs-lookup"><span data-stu-id="f1152-121">Once a restriction is validated, it can be passed in calls to the [IMAPITable::Restrict](imapitable-restrict.md) method to restrict the table to certain rows, to the [IMAPITable::FindRow](imapitable-findrow.md) method to locate a table row, and to methods of the [IMAPIContainer](imapicontainerimapiprop.md) interface to perform a restriction on a container object.</span></span> 
  

