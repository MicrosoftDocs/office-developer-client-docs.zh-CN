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
ms.openlocfilehash: aae2e97b987414fc5e46b410465d3232b61f1ffe
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774898"
---
# <a name="fbadentrylist"></a><span data-ttu-id="2dbe8-103">FBadEntryList</span><span class="sxs-lookup"><span data-stu-id="2dbe8-103">FBadEntryList</span></span>

  
  
<span data-ttu-id="2dbe8-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="2dbe8-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="2dbe8-105">验证 MAPI 项标识符的列表。</span><span class="sxs-lookup"><span data-stu-id="2dbe8-105">Validates a list of MAPI entry identifiers.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="2dbe8-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="2dbe8-106">Header file:</span></span>  <br/> |<span data-ttu-id="2dbe8-107">Mapival.h</span><span class="sxs-lookup"><span data-stu-id="2dbe8-107">Mapival.h</span></span>  <br/> |
|<span data-ttu-id="2dbe8-108">通过实现：</span><span class="sxs-lookup"><span data-stu-id="2dbe8-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="2dbe8-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="2dbe8-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="2dbe8-110">调用：</span><span class="sxs-lookup"><span data-stu-id="2dbe8-110">Called by:</span></span>  <br/> |<span data-ttu-id="2dbe8-111">服务提供商</span><span class="sxs-lookup"><span data-stu-id="2dbe8-111">Service providers</span></span>  <br/> |
   
```cpp
BOOL FBadEntryList(
  LPENTRYLIST lpEntryList
);
```

## <a name="parameters"></a><span data-ttu-id="2dbe8-112">参数</span><span class="sxs-lookup"><span data-stu-id="2dbe8-112">Parameters</span></span>

 <span data-ttu-id="2dbe8-113">_lpEntryList_</span><span class="sxs-lookup"><span data-stu-id="2dbe8-113">_lpEntryList_</span></span>
  
> <span data-ttu-id="2dbe8-114">[in]指向[ENTRYLIST](entrylist.md)结构，其中包含要验证的项标识符的数组。</span><span class="sxs-lookup"><span data-stu-id="2dbe8-114">[in] Pointer to an [ENTRYLIST](entrylist.md) structure that contains an array of entry identifiers to be validated.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="2dbe8-115">返回值</span><span class="sxs-lookup"><span data-stu-id="2dbe8-115">Return value</span></span>

<span data-ttu-id="2dbe8-116">TRUE</span><span class="sxs-lookup"><span data-stu-id="2dbe8-116">TRUE</span></span> 
  
> <span data-ttu-id="2dbe8-117">一个或多个列出的项标识符是无效。</span><span class="sxs-lookup"><span data-stu-id="2dbe8-117">One or more of the listed entry identifiers are invalid.</span></span> 
    
<span data-ttu-id="2dbe8-118">FALSE</span><span class="sxs-lookup"><span data-stu-id="2dbe8-118">FALSE</span></span> 
  
> <span data-ttu-id="2dbe8-119">所有列出的项标识符都是有效的。</span><span class="sxs-lookup"><span data-stu-id="2dbe8-119">All of the listed entry identifiers are valid.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="2dbe8-120">说明</span><span class="sxs-lookup"><span data-stu-id="2dbe8-120">Remarks</span></span>

<span data-ttu-id="2dbe8-121">**FBadEntryList**函数确定是否已正确生成条目标识符列表。</span><span class="sxs-lookup"><span data-stu-id="2dbe8-121">The **FBadEntryList** function determines if the entry identifier list has been correctly generated.</span></span> <span data-ttu-id="2dbe8-122">无效的示例是标识符的一个已正确分配的内存或大小不正确的标识符。</span><span class="sxs-lookup"><span data-stu-id="2dbe8-122">An example of an invalid identifier is one for which memory has been incorrectly allocated or an identifier of an incorrect size.</span></span> 
  

