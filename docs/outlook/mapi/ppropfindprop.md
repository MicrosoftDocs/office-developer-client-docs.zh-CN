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
# <a name="ppropfindprop"></a><span data-ttu-id="31319-103">PpropFindProp</span><span class="sxs-lookup"><span data-stu-id="31319-103">PpropFindProp</span></span>

  
  
<span data-ttu-id="31319-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="31319-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="31319-105">搜索属性集内指定的属性。</span><span class="sxs-lookup"><span data-stu-id="31319-105">Searches for a specified property in a property set.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="31319-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="31319-106">Header file:</span></span>  <br/> |<span data-ttu-id="31319-107">Mapiutil.h</span><span class="sxs-lookup"><span data-stu-id="31319-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="31319-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="31319-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="31319-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="31319-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="31319-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="31319-110">Called by:</span></span>  <br/> |<span data-ttu-id="31319-111">客户端应用程序和服务提供商</span><span class="sxs-lookup"><span data-stu-id="31319-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
LPSPropValue PpropFindProp(
  LPSPropValue rgprop,
  ULONG cprop,
  ULONG ulPropTag
);
```

## <a name="parameters"></a><span data-ttu-id="31319-112">参数</span><span class="sxs-lookup"><span data-stu-id="31319-112">Parameters</span></span>

 <span data-ttu-id="31319-113">_rgprop_</span><span class="sxs-lookup"><span data-stu-id="31319-113">_rgprop_</span></span>
  
> <span data-ttu-id="31319-114">[in] [定义要搜索的属性的 SPropValue](spropvalue.md) 结构数组。</span><span class="sxs-lookup"><span data-stu-id="31319-114">[in] Array of [SPropValue](spropvalue.md) structures that define the properties to be searched.</span></span> 
    
 <span data-ttu-id="31319-115">_cprop_</span><span class="sxs-lookup"><span data-stu-id="31319-115">_cprop_</span></span>
  
> <span data-ttu-id="31319-116">[in]  _rgprop_ 参数指示的属性集内的属性计数。</span><span class="sxs-lookup"><span data-stu-id="31319-116">[in] Count of properties in the property set indicated by the  _rgprop_ parameter.</span></span> 
    
 <span data-ttu-id="31319-117">_ulPropTag_</span><span class="sxs-lookup"><span data-stu-id="31319-117">_ulPropTag_</span></span>
  
> <span data-ttu-id="31319-118">[in]在  _rgprop_ 参数指示的属性集内搜索的属性的属性标记。</span><span class="sxs-lookup"><span data-stu-id="31319-118">[in] Property tag for the property to search for in the property set indicated by the  _rgprop_ parameter.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="31319-119">返回值</span><span class="sxs-lookup"><span data-stu-id="31319-119">Return value</span></span>

 <span data-ttu-id="31319-120">**PpropFindProp** 返回 [一个 SPropValue](spropvalue.md) 结构，该结构定义与输入属性标记匹配的属性;如果没有匹配项，则返回 NULL。</span><span class="sxs-lookup"><span data-stu-id="31319-120">**PpropFindProp** returns an [SPropValue](spropvalue.md) structure defining the property that matches the input property tag, or NULL if there is no match.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="31319-121">备注</span><span class="sxs-lookup"><span data-stu-id="31319-121">Remarks</span></span>

<span data-ttu-id="31319-122">如果给定的属性标记指示类型为 PT_UNSPECIFIED， **则 PpropFindProp** 函数将仅查找标记中属性标识符的匹配项。</span><span class="sxs-lookup"><span data-stu-id="31319-122">If the given property tag indicates a property of type PT_UNSPECIFIED, the **PpropFindProp** function finds a match only for the property identifier in the tag.</span></span> <span data-ttu-id="31319-123">否则，它将查找整个属性标记（包括属性类型）的匹配项，并返回标识的属性。</span><span class="sxs-lookup"><span data-stu-id="31319-123">Otherwise, it finds a match for the entire property tag, including the property type, and returns the property identified.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="31319-124">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="31319-124">MFCMAPI reference</span></span>

<span data-ttu-id="31319-125">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="31319-125">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="31319-126">**文件**</span><span class="sxs-lookup"><span data-stu-id="31319-126">**File**</span></span>|<span data-ttu-id="31319-127">**函数**</span><span class="sxs-lookup"><span data-stu-id="31319-127">**Function**</span></span>|<span data-ttu-id="31319-128">**备注**</span><span class="sxs-lookup"><span data-stu-id="31319-128">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="31319-129">ContentsTableListCtrl.cpp</span><span class="sxs-lookup"><span data-stu-id="31319-129">ContentsTableListCtrl.cpp</span></span>  <br/> |<span data-ttu-id="31319-130">CContentsTableListCtrl：：BuildDataItem</span><span class="sxs-lookup"><span data-stu-id="31319-130">CContentsTableListCtrl::BuildDataItem</span></span>  <br/> |<span data-ttu-id="31319-131">MFCMAPI 使用 **PpropFindProp** 方法在要添加到列表中的属性集内查找属性。</span><span class="sxs-lookup"><span data-stu-id="31319-131">MFCMAPI uses the **PpropFindProp** method to find properties in a property set being added to the list.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="31319-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="31319-132">See also</span></span>



[<span data-ttu-id="31319-133">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="31319-133">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

