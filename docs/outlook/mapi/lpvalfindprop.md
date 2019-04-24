---
title: LpValFindProp
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 67461a38-bb60-467b-901b-39c645e764f7
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: fa1588d4a58824b57c132fc8e66a0abd6e9acd0a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32357426"
---
# <a name="lpvalfindprop"></a><span data-ttu-id="1b25b-103">LpValFindProp</span><span class="sxs-lookup"><span data-stu-id="1b25b-103">LpValFindProp</span></span>

  
  
<span data-ttu-id="1b25b-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="1b25b-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="1b25b-105">在属性集中搜索指定的属性。</span><span class="sxs-lookup"><span data-stu-id="1b25b-105">Searches for a specified property in a property set.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="1b25b-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="1b25b-106">Header file:</span></span>  <br/> |<span data-ttu-id="1b25b-107">mapiutil</span><span class="sxs-lookup"><span data-stu-id="1b25b-107">mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="1b25b-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="1b25b-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="1b25b-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="1b25b-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="1b25b-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="1b25b-110">Called by:</span></span>  <br/> |<span data-ttu-id="1b25b-111">客户端应用程序和服务提供程序。</span><span class="sxs-lookup"><span data-stu-id="1b25b-111">Client applications and service providers.</span></span>  <br/> |
   
```cpp
LPSPropValue LpValFindProp(
  ULONG ulPropTag,
  ULONG cValues,
  LPSPropValue lpPropArray
);
```

## <a name="parameters"></a><span data-ttu-id="1b25b-112">参数</span><span class="sxs-lookup"><span data-stu-id="1b25b-112">Parameters</span></span>

 <span data-ttu-id="1b25b-113">_ulPropTag_</span><span class="sxs-lookup"><span data-stu-id="1b25b-113">_ulPropTag_</span></span>
  
> <span data-ttu-id="1b25b-114">实时要在属性集中搜索的属性的标记, 由_lpPropArray_参数指示。</span><span class="sxs-lookup"><span data-stu-id="1b25b-114">[in] Tag for the property to search for in the property set, indicated by the  _lpPropArray_ parameter.</span></span> 
    
 <span data-ttu-id="1b25b-115">_cValues_</span><span class="sxs-lookup"><span data-stu-id="1b25b-115">_cValues_</span></span>
  
> <span data-ttu-id="1b25b-116">实时属性集中属性的计数, 由_lpPropArray_参数指示。</span><span class="sxs-lookup"><span data-stu-id="1b25b-116">[in] Count of properties in the property set, indicated by the  _lpPropArray_ parameter.</span></span> 
    
 <span data-ttu-id="1b25b-117">_lpPropArray_</span><span class="sxs-lookup"><span data-stu-id="1b25b-117">_lpPropArray_</span></span>
  
> <span data-ttu-id="1b25b-118">实时**SPropValue**结构的数组, 这些结构定义要搜索的属性。</span><span class="sxs-lookup"><span data-stu-id="1b25b-118">[in] Array of **SPropValue** structures that defines the properties to be searched.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="1b25b-119">返回值</span><span class="sxs-lookup"><span data-stu-id="1b25b-119">Return value</span></span>

<span data-ttu-id="1b25b-120">**LpValFindProp**函数返回一个**SPropValue**结构, 该结构定义与输入属性标记匹配的属性; 如果没有匹配项, 则返回 NULL。</span><span class="sxs-lookup"><span data-stu-id="1b25b-120">The **LpValFindProp** function returns an **SPropValue** structure that defines the property that matches the input property tag, or NULL if there is no match.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="1b25b-121">注解</span><span class="sxs-lookup"><span data-stu-id="1b25b-121">Remarks</span></span>

<span data-ttu-id="1b25b-122">**LpValFindProp**函数与**PpropFindProp**相同。</span><span class="sxs-lookup"><span data-stu-id="1b25b-122">The **LpValFindProp** function is identical to **PpropFindProp**.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="1b25b-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1b25b-123">See also</span></span>



[<span data-ttu-id="1b25b-124">PpropFindProp</span><span class="sxs-lookup"><span data-stu-id="1b25b-124">PpropFindProp</span></span>](ppropfindprop.md)
  
[<span data-ttu-id="1b25b-125">SPropValue</span><span class="sxs-lookup"><span data-stu-id="1b25b-125">SPropValue</span></span>](spropvalue.md)

