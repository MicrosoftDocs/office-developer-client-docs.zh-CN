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
# <a name="fbadentrylist"></a><span data-ttu-id="c9d29-103">FBadEntryList</span><span class="sxs-lookup"><span data-stu-id="c9d29-103">FBadEntryList</span></span>

  
  
<span data-ttu-id="c9d29-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="c9d29-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="c9d29-105">验证 MAPI 项标识符的列表。</span><span class="sxs-lookup"><span data-stu-id="c9d29-105">Validates a list of MAPI entry identifiers.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="c9d29-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="c9d29-106">Header file:</span></span>  <br/> |<span data-ttu-id="c9d29-107">Mapival.h</span><span class="sxs-lookup"><span data-stu-id="c9d29-107">Mapival.h</span></span>  <br/> |
|<span data-ttu-id="c9d29-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="c9d29-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="c9d29-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="c9d29-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="c9d29-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="c9d29-110">Called by:</span></span>  <br/> |<span data-ttu-id="c9d29-111">服务提供程序</span><span class="sxs-lookup"><span data-stu-id="c9d29-111">Service providers</span></span>  <br/> |
   
```cpp
BOOL FBadEntryList(
  LPENTRYLIST lpEntryList
);
```

## <a name="parameters"></a><span data-ttu-id="c9d29-112">参数</span><span class="sxs-lookup"><span data-stu-id="c9d29-112">Parameters</span></span>

 <span data-ttu-id="c9d29-113">_lpEntryList_</span><span class="sxs-lookup"><span data-stu-id="c9d29-113">_lpEntryList_</span></span>
  
> <span data-ttu-id="c9d29-114">实时指向包含要验证的条目标识符数组的[ENTRYLIST](entrylist.md)结构的指针。</span><span class="sxs-lookup"><span data-stu-id="c9d29-114">[in] Pointer to an [ENTRYLIST](entrylist.md) structure that contains an array of entry identifiers to be validated.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="c9d29-115">返回值</span><span class="sxs-lookup"><span data-stu-id="c9d29-115">Return value</span></span>

<span data-ttu-id="c9d29-116">TRUE</span><span class="sxs-lookup"><span data-stu-id="c9d29-116">TRUE</span></span> 
  
> <span data-ttu-id="c9d29-117">一个或多个列出的条目标识符无效。</span><span class="sxs-lookup"><span data-stu-id="c9d29-117">One or more of the listed entry identifiers are invalid.</span></span> 
    
<span data-ttu-id="c9d29-118">FALSE</span><span class="sxs-lookup"><span data-stu-id="c9d29-118">FALSE</span></span> 
  
> <span data-ttu-id="c9d29-119">所有列出的条目标识符都是有效的。</span><span class="sxs-lookup"><span data-stu-id="c9d29-119">All of the listed entry identifiers are valid.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="c9d29-120">说明</span><span class="sxs-lookup"><span data-stu-id="c9d29-120">Remarks</span></span>

<span data-ttu-id="c9d29-121">**FBadEntryList**函数确定条目标识符列表是否已正确生成。</span><span class="sxs-lookup"><span data-stu-id="c9d29-121">The **FBadEntryList** function determines if the entry identifier list has been correctly generated.</span></span> <span data-ttu-id="c9d29-122">无效标识符的一个示例是内存分配不正确或标识符大小不正确的情况。</span><span class="sxs-lookup"><span data-stu-id="c9d29-122">An example of an invalid identifier is one for which memory has been incorrectly allocated or an identifier of an incorrect size.</span></span> 
  

