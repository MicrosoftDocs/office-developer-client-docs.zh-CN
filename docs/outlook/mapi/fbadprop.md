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
ms.openlocfilehash: d899c8af541da231b015f6178eb7bc8f0ffd86e0
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33426714"
---
# <a name="fbadprop"></a><span data-ttu-id="f8575-103">FBadProp</span><span class="sxs-lookup"><span data-stu-id="f8575-103">FBadProp</span></span>

  
  
<span data-ttu-id="f8575-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="f8575-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="f8575-105">验证指定的属性。</span><span class="sxs-lookup"><span data-stu-id="f8575-105">Validates a specified property.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="f8575-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="f8575-106">Header file:</span></span>  <br/> |<span data-ttu-id="f8575-107">Mapival.h</span><span class="sxs-lookup"><span data-stu-id="f8575-107">Mapival.h</span></span>  <br/> |
|<span data-ttu-id="f8575-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="f8575-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="f8575-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="f8575-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="f8575-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="f8575-110">Called by:</span></span>  <br/> |<span data-ttu-id="f8575-111">服务提供程序</span><span class="sxs-lookup"><span data-stu-id="f8575-111">Service providers</span></span>  <br/> |
   
```cpp
ULONG FBadProp(
  LPSPropValue lpprop
);
```

## <a name="parameters"></a><span data-ttu-id="f8575-112">参数</span><span class="sxs-lookup"><span data-stu-id="f8575-112">Parameters</span></span>

 <span data-ttu-id="f8575-113">_lpprop_</span><span class="sxs-lookup"><span data-stu-id="f8575-113">_lpprop_</span></span>
  
> <span data-ttu-id="f8575-114">[in] 用于定义要验证的属性的 [SPropValue](spropvalue.md) 结构。</span><span class="sxs-lookup"><span data-stu-id="f8575-114">[in] An [SPropValue](spropvalue.md) structure defining the property to be validated.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="f8575-115">返回值</span><span class="sxs-lookup"><span data-stu-id="f8575-115">Return value</span></span>

<span data-ttu-id="f8575-116">TRUE</span><span class="sxs-lookup"><span data-stu-id="f8575-116">TRUE</span></span> 
  
> <span data-ttu-id="f8575-117">指定的属性无效。</span><span class="sxs-lookup"><span data-stu-id="f8575-117">The specified property is invalid.</span></span> 
    
<span data-ttu-id="f8575-118">FALSE</span><span class="sxs-lookup"><span data-stu-id="f8575-118">FALSE</span></span> 
  
> <span data-ttu-id="f8575-119">指定的属性有效。</span><span class="sxs-lookup"><span data-stu-id="f8575-119">The specified property is valid.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="f8575-120">备注</span><span class="sxs-lookup"><span data-stu-id="f8575-120">Remarks</span></span>

<span data-ttu-id="f8575-121">服务提供程序可以出于多种原因调用 **FBadProp** 函数，例如，准备调用 [IMAPIProp::SetProps](imapiprop-setprops.md) 方法设置属性。</span><span class="sxs-lookup"><span data-stu-id="f8575-121">A service provider can call the **FBadProp** function for several reasons, for example to prepare for a call to the [IMAPIProp::SetProps](imapiprop-setprops.md) method setting a property.</span></span> <span data-ttu-id="f8575-122">**FBadProp** 根据属性类型验证指定属性。</span><span class="sxs-lookup"><span data-stu-id="f8575-122">**FBadProp** validates the specified property depending on the property type.</span></span> <span data-ttu-id="f8575-123">例如，如果属性为布尔，则 **FBadProp** 确定其值为 TRUE 或 FALSE。</span><span class="sxs-lookup"><span data-stu-id="f8575-123">For example, if the property is Boolean, **FBadProp** make sures that its value is either TRUE or FALSE.</span></span> <span data-ttu-id="f8575-124">如果属性为二进制，则 **FBadProp** 检查其指针和大小，并确保其得以正确分配。</span><span class="sxs-lookup"><span data-stu-id="f8575-124">If the property is binary, **FBadProp** checks its pointer and size and makes sure that it is allocated correctly.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="f8575-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f8575-125">See also</span></span>



[<span data-ttu-id="f8575-126">FBadPropTag</span><span class="sxs-lookup"><span data-stu-id="f8575-126">FBadPropTag</span></span>](fbadproptag.md)

