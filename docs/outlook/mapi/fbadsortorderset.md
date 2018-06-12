---
title: FBadSortOrderSet
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.FBadSortOrderSet
api_type:
- COM
ms.assetid: b7f80e0a-8ddd-4b24-ab63-2078a8152058
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 0e200ea20c55cfd5729ce4c1f590de2d61ca73bc
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774910"
---
# <a name="fbadsortorderset"></a><span data-ttu-id="f72cf-103">FBadSortOrderSet</span><span class="sxs-lookup"><span data-stu-id="f72cf-103">FBadSortOrderSet</span></span>

  
  
<span data-ttu-id="f72cf-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="f72cf-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="f72cf-105">验证排序顺序设置通过验证其内存分配。</span><span class="sxs-lookup"><span data-stu-id="f72cf-105">Validates a sort order set by verifying its memory allocation.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="f72cf-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="f72cf-106">Header file:</span></span>  <br/> |<span data-ttu-id="f72cf-107">Mapival.h</span><span class="sxs-lookup"><span data-stu-id="f72cf-107">Mapival.h</span></span>  <br/> |
|<span data-ttu-id="f72cf-108">通过实现：</span><span class="sxs-lookup"><span data-stu-id="f72cf-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="f72cf-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="f72cf-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="f72cf-110">调用：</span><span class="sxs-lookup"><span data-stu-id="f72cf-110">Called by:</span></span>  <br/> |<span data-ttu-id="f72cf-111">服务提供商</span><span class="sxs-lookup"><span data-stu-id="f72cf-111">Service providers</span></span>  <br/> |
   
```cpp
ULONG FBadSortOrderSet(
  LPSSortOrderSet lpsos
);
```

## <a name="parameters"></a><span data-ttu-id="f72cf-112">参数</span><span class="sxs-lookup"><span data-stu-id="f72cf-112">Parameters</span></span>

 <span data-ttu-id="f72cf-113">_lpsos_</span><span class="sxs-lookup"><span data-stu-id="f72cf-113">_lpsos_</span></span>
  
> <span data-ttu-id="f72cf-114">[in]指向标识设置要验证的排序次序[SSortOrderSet](ssortorderset.md)结构。</span><span class="sxs-lookup"><span data-stu-id="f72cf-114">[in] Pointer to an [SSortOrderSet](ssortorderset.md) structure identifying the sort order set to be validated.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="f72cf-115">返回值</span><span class="sxs-lookup"><span data-stu-id="f72cf-115">Return value</span></span>

<span data-ttu-id="f72cf-116">TRUE</span><span class="sxs-lookup"><span data-stu-id="f72cf-116">TRUE</span></span> 
  
> <span data-ttu-id="f72cf-117">设置指定的排序顺序无效。</span><span class="sxs-lookup"><span data-stu-id="f72cf-117">The specified sort order set is invalid.</span></span> 
    
<span data-ttu-id="f72cf-118">FALSE</span><span class="sxs-lookup"><span data-stu-id="f72cf-118">FALSE</span></span> 
  
> <span data-ttu-id="f72cf-119">有效设置的指定的排序顺序。</span><span class="sxs-lookup"><span data-stu-id="f72cf-119">The specified sort order set is valid.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="f72cf-120">备注</span><span class="sxs-lookup"><span data-stu-id="f72cf-120">Remarks</span></span>

<span data-ttu-id="f72cf-121">**FBadSortOrderSet**函数可用于准备 sort 方法，如[IMAPITable::SortTable](imapitable-sorttable.md)方法调用。</span><span class="sxs-lookup"><span data-stu-id="f72cf-121">The **FBadSortOrderSet** function can be used to prepare for a call to a sort method such as the [IMAPITable::SortTable](imapitable-sorttable.md) method.</span></span> 
  

