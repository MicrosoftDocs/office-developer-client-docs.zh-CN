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
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 31840923e24cddd0dc3dfa9cc67b610d0dcd7e47
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32336972"
---
# <a name="fbadsortorderset"></a><span data-ttu-id="79aa3-103">FBadSortOrderSet</span><span class="sxs-lookup"><span data-stu-id="79aa3-103">FBadSortOrderSet</span></span>

  
  
<span data-ttu-id="79aa3-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="79aa3-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="79aa3-105">验证是否通过验证其内存分配来设置排序顺序。</span><span class="sxs-lookup"><span data-stu-id="79aa3-105">Validates a sort order set by verifying its memory allocation.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="79aa3-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="79aa3-106">Header file:</span></span>  <br/> |<span data-ttu-id="79aa3-107">Mapival.h</span><span class="sxs-lookup"><span data-stu-id="79aa3-107">Mapival.h</span></span>  <br/> |
|<span data-ttu-id="79aa3-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="79aa3-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="79aa3-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="79aa3-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="79aa3-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="79aa3-110">Called by:</span></span>  <br/> |<span data-ttu-id="79aa3-111">服务提供程序</span><span class="sxs-lookup"><span data-stu-id="79aa3-111">Service providers</span></span>  <br/> |
   
```cpp
ULONG FBadSortOrderSet(
  LPSSortOrderSet lpsos
);
```

## <a name="parameters"></a><span data-ttu-id="79aa3-112">参数</span><span class="sxs-lookup"><span data-stu-id="79aa3-112">Parameters</span></span>

 <span data-ttu-id="79aa3-113">_lpsos_</span><span class="sxs-lookup"><span data-stu-id="79aa3-113">_lpsos_</span></span>
  
> <span data-ttu-id="79aa3-114">实时指向标识排序顺序设置为要验证的[SSortOrderSet](ssortorderset.md)结构的指针。</span><span class="sxs-lookup"><span data-stu-id="79aa3-114">[in] Pointer to an [SSortOrderSet](ssortorderset.md) structure identifying the sort order set to be validated.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="79aa3-115">返回值</span><span class="sxs-lookup"><span data-stu-id="79aa3-115">Return value</span></span>

<span data-ttu-id="79aa3-116">TRUE</span><span class="sxs-lookup"><span data-stu-id="79aa3-116">TRUE</span></span> 
  
> <span data-ttu-id="79aa3-117">指定的排序次序设置无效。</span><span class="sxs-lookup"><span data-stu-id="79aa3-117">The specified sort order set is invalid.</span></span> 
    
<span data-ttu-id="79aa3-118">FALSE</span><span class="sxs-lookup"><span data-stu-id="79aa3-118">FALSE</span></span> 
  
> <span data-ttu-id="79aa3-119">指定的排序次序设置有效。</span><span class="sxs-lookup"><span data-stu-id="79aa3-119">The specified sort order set is valid.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="79aa3-120">注解</span><span class="sxs-lookup"><span data-stu-id="79aa3-120">Remarks</span></span>

<span data-ttu-id="79aa3-121">**FBadSortOrderSet**函数可用于准备对[IMAPITable:: SortTable](imapitable-sorttable.md)方法等 sort 方法的调用。</span><span class="sxs-lookup"><span data-stu-id="79aa3-121">The **FBadSortOrderSet** function can be used to prepare for a call to a sort method such as the [IMAPITable::SortTable](imapitable-sorttable.md) method.</span></span> 
  

