---
title: PpropFindProp
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PpropFindProp
api_type:
- HeaderDef
ms.assetid: f23dd6f4-915b-4fe8-ab3f-6d625c7d6061
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 97021128f92af0486af1ba3125c7843eaa357648
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33406337"
---
# <a name="ppropfindprop"></a><span data-ttu-id="9f0a5-103">PpropFindProp</span><span class="sxs-lookup"><span data-stu-id="9f0a5-103">PpropFindProp</span></span>

  
  
<span data-ttu-id="9f0a5-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="9f0a5-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="9f0a5-105">在属性集中搜索指定的属性。</span><span class="sxs-lookup"><span data-stu-id="9f0a5-105">Searches for a specified property in a property set.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="9f0a5-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="9f0a5-106">Header file:</span></span>  <br/> |<span data-ttu-id="9f0a5-107">Mapiutil</span><span class="sxs-lookup"><span data-stu-id="9f0a5-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="9f0a5-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="9f0a5-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="9f0a5-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="9f0a5-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="9f0a5-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="9f0a5-110">Called by:</span></span>  <br/> |<span data-ttu-id="9f0a5-111">客户端应用程序和服务提供程序</span><span class="sxs-lookup"><span data-stu-id="9f0a5-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
LPSPropValue PpropFindProp(
  LPSPropValue rgprop,
  ULONG cprop,
  ULONG ulPropTag
);
```

## <a name="parameters"></a><span data-ttu-id="9f0a5-112">参数</span><span class="sxs-lookup"><span data-stu-id="9f0a5-112">Parameters</span></span>

 <span data-ttu-id="9f0a5-113">_rgprop_</span><span class="sxs-lookup"><span data-stu-id="9f0a5-113">_rgprop_</span></span>
  
> <span data-ttu-id="9f0a5-114">实时定义要搜索的属性的[SPropValue](spropvalue.md)结构的数组。</span><span class="sxs-lookup"><span data-stu-id="9f0a5-114">[in] Array of [SPropValue](spropvalue.md) structures that define the properties to be searched.</span></span> 
    
 <span data-ttu-id="9f0a5-115">_cprop_</span><span class="sxs-lookup"><span data-stu-id="9f0a5-115">_cprop_</span></span>
  
> <span data-ttu-id="9f0a5-116">实时由_rgprop_参数指示的属性集中属性的计数。</span><span class="sxs-lookup"><span data-stu-id="9f0a5-116">[in] Count of properties in the property set indicated by the  _rgprop_ parameter.</span></span> 
    
 <span data-ttu-id="9f0a5-117">_ulPropTag_</span><span class="sxs-lookup"><span data-stu-id="9f0a5-117">_ulPropTag_</span></span>
  
> <span data-ttu-id="9f0a5-118">实时要在由_rgprop_参数指示的属性集中搜索的属性的属性标记。</span><span class="sxs-lookup"><span data-stu-id="9f0a5-118">[in] Property tag for the property to search for in the property set indicated by the  _rgprop_ parameter.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="9f0a5-119">返回值</span><span class="sxs-lookup"><span data-stu-id="9f0a5-119">Return value</span></span>

 <span data-ttu-id="9f0a5-120">**PpropFindProp**返回一个[SPropValue](spropvalue.md)结构, 该结构定义与输入属性标记相匹配的属性; 如果没有匹配项, 则返回 NULL。</span><span class="sxs-lookup"><span data-stu-id="9f0a5-120">**PpropFindProp** returns an [SPropValue](spropvalue.md) structure defining the property that matches the input property tag, or NULL if there is no match.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="9f0a5-121">说明</span><span class="sxs-lookup"><span data-stu-id="9f0a5-121">Remarks</span></span>

<span data-ttu-id="9f0a5-122">如果给定的属性标记指示 PT_UNSPECIFIED 类型的属性, 则**PpropFindProp**函数仅查找标记中的属性标识符的匹配项。</span><span class="sxs-lookup"><span data-stu-id="9f0a5-122">If the given property tag indicates a property of type PT_UNSPECIFIED, the **PpropFindProp** function finds a match only for the property identifier in the tag.</span></span> <span data-ttu-id="9f0a5-123">否则, 它找到整个属性标记的匹配项 (包括属性类型), 并返回标识的属性。</span><span class="sxs-lookup"><span data-stu-id="9f0a5-123">Otherwise, it finds a match for the entire property tag, including the property type, and returns the property identified.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="9f0a5-124">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="9f0a5-124">MFCMAPI reference</span></span>

<span data-ttu-id="9f0a5-125">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="9f0a5-125">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="9f0a5-126">**文件**</span><span class="sxs-lookup"><span data-stu-id="9f0a5-126">**File**</span></span>|<span data-ttu-id="9f0a5-127">**函数**</span><span class="sxs-lookup"><span data-stu-id="9f0a5-127">**Function**</span></span>|<span data-ttu-id="9f0a5-128">**备注**</span><span class="sxs-lookup"><span data-stu-id="9f0a5-128">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="9f0a5-129">ContentsTableListCtrl</span><span class="sxs-lookup"><span data-stu-id="9f0a5-129">ContentsTableListCtrl.cpp</span></span>  <br/> |<span data-ttu-id="9f0a5-130">CContentsTableListCtrl:: BuildDataItem</span><span class="sxs-lookup"><span data-stu-id="9f0a5-130">CContentsTableListCtrl::BuildDataItem</span></span>  <br/> |<span data-ttu-id="9f0a5-131">MFCMAPI 使用**PpropFindProp**方法来查找要添加到列表中的属性集的属性。</span><span class="sxs-lookup"><span data-stu-id="9f0a5-131">MFCMAPI uses the **PpropFindProp** method to find properties in a property set being added to the list.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="9f0a5-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9f0a5-132">See also</span></span>



[<span data-ttu-id="9f0a5-133">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="9f0a5-133">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

