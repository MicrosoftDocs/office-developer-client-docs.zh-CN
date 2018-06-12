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
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: b7755f2ec067003e47d358a9736c6d7d96ede267
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778565"
---
# <a name="ppropfindprop"></a><span data-ttu-id="ac46d-103">PpropFindProp</span><span class="sxs-lookup"><span data-stu-id="ac46d-103">PpropFindProp</span></span>

  
  
<span data-ttu-id="ac46d-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="ac46d-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="ac46d-105">搜索属性中指定属性设置。</span><span class="sxs-lookup"><span data-stu-id="ac46d-105">Searches for a specified property in a property set.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="ac46d-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="ac46d-106">Header file:</span></span>  <br/> |<span data-ttu-id="ac46d-107">Mapiutil.h</span><span class="sxs-lookup"><span data-stu-id="ac46d-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="ac46d-108">通过实现：</span><span class="sxs-lookup"><span data-stu-id="ac46d-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="ac46d-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="ac46d-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="ac46d-110">调用：</span><span class="sxs-lookup"><span data-stu-id="ac46d-110">Called by:</span></span>  <br/> |<span data-ttu-id="ac46d-111">客户端应用程序和服务提供商</span><span class="sxs-lookup"><span data-stu-id="ac46d-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
LPSPropValue PpropFindProp(
  LPSPropValue rgprop,
  ULONG cprop,
  ULONG ulPropTag
);
```

## <a name="parameters"></a><span data-ttu-id="ac46d-112">参数</span><span class="sxs-lookup"><span data-stu-id="ac46d-112">Parameters</span></span>

 <span data-ttu-id="ac46d-113">_rgprop_</span><span class="sxs-lookup"><span data-stu-id="ac46d-113">_rgprop_</span></span>
  
> <span data-ttu-id="ac46d-114">[in]定义要搜索的属性的[SPropValue](spropvalue.md)结构的数组。</span><span class="sxs-lookup"><span data-stu-id="ac46d-114">[in] Array of [SPropValue](spropvalue.md) structures that define the properties to be searched.</span></span> 
    
 <span data-ttu-id="ac46d-115">_cprop_</span><span class="sxs-lookup"><span data-stu-id="ac46d-115">_cprop_</span></span>
  
> <span data-ttu-id="ac46d-116">[in]设置由_rgprop_参数指示的属性中的属性的计数。</span><span class="sxs-lookup"><span data-stu-id="ac46d-116">[in] Count of properties in the property set indicated by the  _rgprop_ parameter.</span></span> 
    
 <span data-ttu-id="ac46d-117">_ulPropTag_</span><span class="sxs-lookup"><span data-stu-id="ac46d-117">_ulPropTag_</span></span>
  
> <span data-ttu-id="ac46d-118">[in]要设置由_rgprop_参数指示的属性中搜索的属性的属性标记。</span><span class="sxs-lookup"><span data-stu-id="ac46d-118">[in] Property tag for the property to search for in the property set indicated by the  _rgprop_ parameter.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="ac46d-119">返回值</span><span class="sxs-lookup"><span data-stu-id="ac46d-119">Return value</span></span>

 <span data-ttu-id="ac46d-120">**PpropFindProp**返回[SPropValue](spropvalue.md)结构定义符合输入的属性标记，则为 NULL，如果没有匹配的属性。</span><span class="sxs-lookup"><span data-stu-id="ac46d-120">**PpropFindProp** returns an [SPropValue](spropvalue.md) structure defining the property that matches the input property tag, or NULL if there is no match.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="ac46d-121">备注</span><span class="sxs-lookup"><span data-stu-id="ac46d-121">Remarks</span></span>

<span data-ttu-id="ac46d-122">如果给定的属性标记指示 PT_UNSPECIFIED 类型的属性， **PpropFindProp**函数标记中找到仅属性标识符的匹配项。</span><span class="sxs-lookup"><span data-stu-id="ac46d-122">If the given property tag indicates a property of type PT_UNSPECIFIED, the **PpropFindProp** function finds a match only for the property identifier in the tag.</span></span> <span data-ttu-id="ac46d-123">否则为它找到匹配项整个属性标记，其中包括属性类型，并返回标识的属性。</span><span class="sxs-lookup"><span data-stu-id="ac46d-123">Otherwise, it finds a match for the entire property tag, including the property type, and returns the property identified.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="ac46d-124">MFCMAPI 参考 （英文）</span><span class="sxs-lookup"><span data-stu-id="ac46d-124">MFCMAPI reference</span></span>

<span data-ttu-id="ac46d-125">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="ac46d-125">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="ac46d-126">**文件**</span><span class="sxs-lookup"><span data-stu-id="ac46d-126">**File**</span></span>|<span data-ttu-id="ac46d-127">**函数**</span><span class="sxs-lookup"><span data-stu-id="ac46d-127">**Function**</span></span>|<span data-ttu-id="ac46d-128">**Comment**</span><span class="sxs-lookup"><span data-stu-id="ac46d-128">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ac46d-129">ContentsTableListCtrl.cpp</span><span class="sxs-lookup"><span data-stu-id="ac46d-129">ContentsTableListCtrl.cpp</span></span>  <br/> |<span data-ttu-id="ac46d-130">CContentsTableListCtrl::BuildDataItem</span><span class="sxs-lookup"><span data-stu-id="ac46d-130">CContentsTableListCtrl::BuildDataItem</span></span>  <br/> |<span data-ttu-id="ac46d-131">MFCMAPI 使用**PpropFindProp**方法来查找属性中的属性设置添加到列表。</span><span class="sxs-lookup"><span data-stu-id="ac46d-131">MFCMAPI uses the **PpropFindProp** method to find properties in a property set being added to the list.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="ac46d-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ac46d-132">See also</span></span>



[<span data-ttu-id="ac46d-133">MFCMAPI 作为的代码示例</span><span class="sxs-lookup"><span data-stu-id="ac46d-133">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

