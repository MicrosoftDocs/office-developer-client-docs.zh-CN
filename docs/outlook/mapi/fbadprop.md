---
title: FBadProp
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- FBadProp
api_type:
- HeaderDef
ms.assetid: 929330c8-e6f2-4adf-a36e-fba18fa055d4
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 2fbff399e088edaf3ad864f0ec7fecda3af6bc8e
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22578848"
---
# <a name="fbadprop"></a><span data-ttu-id="2646d-103">FBadProp</span><span class="sxs-lookup"><span data-stu-id="2646d-103">FBadProp</span></span>

  
  
<span data-ttu-id="2646d-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="2646d-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="2646d-105">验证指定的属性。</span><span class="sxs-lookup"><span data-stu-id="2646d-105">Validates a specified property.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="2646d-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="2646d-106">Header file:</span></span>  <br/> |<span data-ttu-id="2646d-107">Mapival.h</span><span class="sxs-lookup"><span data-stu-id="2646d-107">Mapival.h</span></span>  <br/> |
|<span data-ttu-id="2646d-108">通过实现：</span><span class="sxs-lookup"><span data-stu-id="2646d-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="2646d-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="2646d-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="2646d-110">调用：</span><span class="sxs-lookup"><span data-stu-id="2646d-110">Called by:</span></span>  <br/> |<span data-ttu-id="2646d-111">服务提供商</span><span class="sxs-lookup"><span data-stu-id="2646d-111">Service providers</span></span>  <br/> |
   
```cpp
ULONG FBadProp(
  LPSPropValue lpprop
);
```

## <a name="parameters"></a><span data-ttu-id="2646d-112">参数</span><span class="sxs-lookup"><span data-stu-id="2646d-112">Parameters</span></span>

 <span data-ttu-id="2646d-113">_lpprop_</span><span class="sxs-lookup"><span data-stu-id="2646d-113">_lpprop_</span></span>
  
> <span data-ttu-id="2646d-114">[in]定义要验证的属性[SPropValue](spropvalue.md)结构。</span><span class="sxs-lookup"><span data-stu-id="2646d-114">[in] An [SPropValue](spropvalue.md) structure defining the property to be validated.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="2646d-115">返回值</span><span class="sxs-lookup"><span data-stu-id="2646d-115">Return value</span></span>

<span data-ttu-id="2646d-116">TRUE</span><span class="sxs-lookup"><span data-stu-id="2646d-116">TRUE</span></span> 
  
> <span data-ttu-id="2646d-117">指定的属性无效。</span><span class="sxs-lookup"><span data-stu-id="2646d-117">The specified property is invalid.</span></span> 
    
<span data-ttu-id="2646d-118">FALSE</span><span class="sxs-lookup"><span data-stu-id="2646d-118">FALSE</span></span> 
  
> <span data-ttu-id="2646d-119">指定的属性才有效。</span><span class="sxs-lookup"><span data-stu-id="2646d-119">The specified property is valid.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="2646d-120">注解</span><span class="sxs-lookup"><span data-stu-id="2646d-120">Remarks</span></span>

<span data-ttu-id="2646d-121">服务提供商可以调用**FBadProp**函数原因，例如，若要准备设置属性的[IMAPIProp::SetProps](imapiprop-setprops.md)方法调用。</span><span class="sxs-lookup"><span data-stu-id="2646d-121">A service provider can call the **FBadProp** function for several reasons, for example to prepare for a call to the [IMAPIProp::SetProps](imapiprop-setprops.md) method setting a property.</span></span> <span data-ttu-id="2646d-122">**FBadProp**验证指定的属性，具体取决于属性类型。</span><span class="sxs-lookup"><span data-stu-id="2646d-122">**FBadProp** validates the specified property depending on the property type.</span></span> <span data-ttu-id="2646d-123">例如，如果属性为布尔值， **FBadProp**使 sures 其值是否为 TRUE 或 FALSE。</span><span class="sxs-lookup"><span data-stu-id="2646d-123">For example, if the property is Boolean, **FBadProp** make sures that its value is either TRUE or FALSE.</span></span> <span data-ttu-id="2646d-124">如果该属性是二进制， **FBadProp**检查其指针和大小，并确保正确地分配。</span><span class="sxs-lookup"><span data-stu-id="2646d-124">If the property is binary, **FBadProp** checks its pointer and size and makes sure that it is allocated correctly.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="2646d-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2646d-125">See also</span></span>



[<span data-ttu-id="2646d-126">FBadPropTag</span><span class="sxs-lookup"><span data-stu-id="2646d-126">FBadPropTag</span></span>](fbadproptag.md)

