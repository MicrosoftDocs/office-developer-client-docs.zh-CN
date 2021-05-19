---
title: FBadEntryList
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- FBadEntryList
api_type:
- HeaderDef
ms.assetid: 270c47c3-ae68-4995-b304-27f861b350d6
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 21ed5a23b96dabdd594547109ecb1e6c048a4844
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33427771"
---
# <a name="fbadentrylist"></a><span data-ttu-id="12048-103">FBadEntryList</span><span class="sxs-lookup"><span data-stu-id="12048-103">FBadEntryList</span></span>

  
  
<span data-ttu-id="12048-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="12048-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="12048-105">验证 MAPI 条目标识符的列表。</span><span class="sxs-lookup"><span data-stu-id="12048-105">Validates a list of MAPI entry identifiers.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="12048-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="12048-106">Header file:</span></span>  <br/> |<span data-ttu-id="12048-107">Mapival.h</span><span class="sxs-lookup"><span data-stu-id="12048-107">Mapival.h</span></span>  <br/> |
|<span data-ttu-id="12048-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="12048-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="12048-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="12048-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="12048-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="12048-110">Called by:</span></span>  <br/> |<span data-ttu-id="12048-111">服务提供程序</span><span class="sxs-lookup"><span data-stu-id="12048-111">Service providers</span></span>  <br/> |
   
```cpp
BOOL FBadEntryList(
  LPENTRYLIST lpEntryList
);
```

## <a name="parameters"></a><span data-ttu-id="12048-112">参数</span><span class="sxs-lookup"><span data-stu-id="12048-112">Parameters</span></span>

 <span data-ttu-id="12048-113">_lpEntryList_</span><span class="sxs-lookup"><span data-stu-id="12048-113">_lpEntryList_</span></span>
  
> <span data-ttu-id="12048-114">[in]指向包含要验证的条目标识符数组的 [ENTRYLIST](entrylist.md) 结构的指针。</span><span class="sxs-lookup"><span data-stu-id="12048-114">[in] Pointer to an [ENTRYLIST](entrylist.md) structure that contains an array of entry identifiers to be validated.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="12048-115">返回值</span><span class="sxs-lookup"><span data-stu-id="12048-115">Return value</span></span>

<span data-ttu-id="12048-116">TRUE</span><span class="sxs-lookup"><span data-stu-id="12048-116">TRUE</span></span> 
  
> <span data-ttu-id="12048-117">列出的一个或多个条目标识符无效。</span><span class="sxs-lookup"><span data-stu-id="12048-117">One or more of the listed entry identifiers are invalid.</span></span> 
    
<span data-ttu-id="12048-118">FALSE</span><span class="sxs-lookup"><span data-stu-id="12048-118">FALSE</span></span> 
  
> <span data-ttu-id="12048-119">列出的所有条目标识符都有效。</span><span class="sxs-lookup"><span data-stu-id="12048-119">All of the listed entry identifiers are valid.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="12048-120">备注</span><span class="sxs-lookup"><span data-stu-id="12048-120">Remarks</span></span>

<span data-ttu-id="12048-121">**FBadEntryList** 函数确定是否已正确生成条目标识符列表。</span><span class="sxs-lookup"><span data-stu-id="12048-121">The **FBadEntryList** function determines if the entry identifier list has been correctly generated.</span></span> <span data-ttu-id="12048-122">无效标识符的示例是内存分配不正确或大小不正确的标识符。</span><span class="sxs-lookup"><span data-stu-id="12048-122">An example of an invalid identifier is one for which memory has been incorrectly allocated or an identifier of an incorrect size.</span></span> 
  

