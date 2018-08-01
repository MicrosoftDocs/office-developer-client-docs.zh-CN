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
ms.openlocfilehash: d7601eb50818fa6f39384a6b024215fc4917e83a
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776150"
---
# <a name="lpvalfindprop"></a><span data-ttu-id="3e192-103">LpValFindProp</span><span class="sxs-lookup"><span data-stu-id="3e192-103">LpValFindProp</span></span>

  
  
<span data-ttu-id="3e192-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="3e192-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="3e192-105">搜索属性中指定属性设置。</span><span class="sxs-lookup"><span data-stu-id="3e192-105">Searches for a specified property in a property set.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="3e192-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="3e192-106">Header file:</span></span>  <br/> |<span data-ttu-id="3e192-107">mapiutil.h</span><span class="sxs-lookup"><span data-stu-id="3e192-107">mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="3e192-108">通过实现：</span><span class="sxs-lookup"><span data-stu-id="3e192-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="3e192-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="3e192-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="3e192-110">调用：</span><span class="sxs-lookup"><span data-stu-id="3e192-110">Called by:</span></span>  <br/> |<span data-ttu-id="3e192-111">客户端应用程序和服务提供商。</span><span class="sxs-lookup"><span data-stu-id="3e192-111">Client applications and service providers.</span></span>  <br/> |
   
```cpp
LPSPropValue LpValFindProp(
  ULONG ulPropTag,
  ULONG cValues,
  LPSPropValue lpPropArray
);
```

## <a name="parameters"></a><span data-ttu-id="3e192-112">参数</span><span class="sxs-lookup"><span data-stu-id="3e192-112">Parameters</span></span>

 <span data-ttu-id="3e192-113">_ulPropTag_</span><span class="sxs-lookup"><span data-stu-id="3e192-113">_ulPropTag_</span></span>
  
> <span data-ttu-id="3e192-114">[in]标记中的属性集，由_lpPropArray_参数指示搜索的属性。</span><span class="sxs-lookup"><span data-stu-id="3e192-114">[in] Tag for the property to search for in the property set, indicated by the  _lpPropArray_ parameter.</span></span> 
    
 <span data-ttu-id="3e192-115">_cValues_</span><span class="sxs-lookup"><span data-stu-id="3e192-115">_cValues_</span></span>
  
> <span data-ttu-id="3e192-116">[in]属性集，由_lpPropArray_参数中的属性的计数。</span><span class="sxs-lookup"><span data-stu-id="3e192-116">[in] Count of properties in the property set, indicated by the  _lpPropArray_ parameter.</span></span> 
    
 <span data-ttu-id="3e192-117">_lpPropArray_</span><span class="sxs-lookup"><span data-stu-id="3e192-117">_lpPropArray_</span></span>
  
> <span data-ttu-id="3e192-118">[in]**SPropValue**结构的数组，用于定义要搜索的属性。</span><span class="sxs-lookup"><span data-stu-id="3e192-118">[in] Array of **SPropValue** structures that defines the properties to be searched.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="3e192-119">返回值</span><span class="sxs-lookup"><span data-stu-id="3e192-119">Return value</span></span>

<span data-ttu-id="3e192-120">**LpValFindProp**函数将返回**SPropValue**结构，它定义符合输入的属性标记，则为 NULL，如果没有匹配的属性。</span><span class="sxs-lookup"><span data-stu-id="3e192-120">The **LpValFindProp** function returns an **SPropValue** structure that defines the property that matches the input property tag, or NULL if there is no match.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="3e192-121">说明</span><span class="sxs-lookup"><span data-stu-id="3e192-121">Remarks</span></span>

<span data-ttu-id="3e192-122">**LpValFindProp**函数等同于**PpropFindProp**。</span><span class="sxs-lookup"><span data-stu-id="3e192-122">The **LpValFindProp** function is identical to **PpropFindProp**.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="3e192-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3e192-123">See also</span></span>



[<span data-ttu-id="3e192-124">PpropFindProp</span><span class="sxs-lookup"><span data-stu-id="3e192-124">PpropFindProp</span></span>](ppropfindprop.md)
  
[<span data-ttu-id="3e192-125">SPropValue</span><span class="sxs-lookup"><span data-stu-id="3e192-125">SPropValue</span></span>](spropvalue.md)

