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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33428457"
---
# <a name="fbadsortorderset"></a><span data-ttu-id="f4b95-103">FBadSortOrderSet</span><span class="sxs-lookup"><span data-stu-id="f4b95-103">FBadSortOrderSet</span></span>

  
  
<span data-ttu-id="f4b95-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="f4b95-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="f4b95-105">验证是否通过验证其内存分配来设置排序顺序。</span><span class="sxs-lookup"><span data-stu-id="f4b95-105">Validates a sort order set by verifying its memory allocation.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="f4b95-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="f4b95-106">Header file:</span></span>  <br/> |<span data-ttu-id="f4b95-107">Mapival.h</span><span class="sxs-lookup"><span data-stu-id="f4b95-107">Mapival.h</span></span>  <br/> |
|<span data-ttu-id="f4b95-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="f4b95-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="f4b95-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="f4b95-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="f4b95-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="f4b95-110">Called by:</span></span>  <br/> |<span data-ttu-id="f4b95-111">服务提供程序</span><span class="sxs-lookup"><span data-stu-id="f4b95-111">Service providers</span></span>  <br/> |
   
```cpp
ULONG FBadSortOrderSet(
  LPSSortOrderSet lpsos
);
```

## <a name="parameters"></a><span data-ttu-id="f4b95-112">参数</span><span class="sxs-lookup"><span data-stu-id="f4b95-112">Parameters</span></span>

 <span data-ttu-id="f4b95-113">_lpsos_</span><span class="sxs-lookup"><span data-stu-id="f4b95-113">_lpsos_</span></span>
  
> <span data-ttu-id="f4b95-114">实时指向标识排序顺序设置为要验证的[SSortOrderSet](ssortorderset.md)结构的指针。</span><span class="sxs-lookup"><span data-stu-id="f4b95-114">[in] Pointer to an [SSortOrderSet](ssortorderset.md) structure identifying the sort order set to be validated.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="f4b95-115">返回值</span><span class="sxs-lookup"><span data-stu-id="f4b95-115">Return value</span></span>

<span data-ttu-id="f4b95-116">TRUE</span><span class="sxs-lookup"><span data-stu-id="f4b95-116">TRUE</span></span> 
  
> <span data-ttu-id="f4b95-117">指定的排序次序设置无效。</span><span class="sxs-lookup"><span data-stu-id="f4b95-117">The specified sort order set is invalid.</span></span> 
    
<span data-ttu-id="f4b95-118">FALSE</span><span class="sxs-lookup"><span data-stu-id="f4b95-118">FALSE</span></span> 
  
> <span data-ttu-id="f4b95-119">指定的排序次序设置有效。</span><span class="sxs-lookup"><span data-stu-id="f4b95-119">The specified sort order set is valid.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="f4b95-120">说明</span><span class="sxs-lookup"><span data-stu-id="f4b95-120">Remarks</span></span>

<span data-ttu-id="f4b95-121">**FBadSortOrderSet**函数可用于准备对[IMAPITable:: SortTable](imapitable-sorttable.md)方法等 sort 方法的调用。</span><span class="sxs-lookup"><span data-stu-id="f4b95-121">The **FBadSortOrderSet** function can be used to prepare for a call to a sort method such as the [IMAPITable::SortTable](imapitable-sorttable.md) method.</span></span> 
  

