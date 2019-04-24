---
title: FBadPropTag
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- FBadPropTag
api_type:
- HeaderDef
ms.assetid: 143bd3c6-5a55-4122-8522-9c48473aa781
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 9764be2788db8d2649be8708cad4ec67a85af845
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32340997"
---
# <a name="fbadproptag"></a><span data-ttu-id="9f481-103">FBadPropTag</span><span class="sxs-lookup"><span data-stu-id="9f481-103">FBadPropTag</span></span>

  
  
<span data-ttu-id="9f481-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="9f481-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="9f481-105">验证指定的属性标记。</span><span class="sxs-lookup"><span data-stu-id="9f481-105">Validates a specified property tag.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="9f481-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="9f481-106">Header file:</span></span>  <br/> |<span data-ttu-id="9f481-107">Mapival.h</span><span class="sxs-lookup"><span data-stu-id="9f481-107">Mapival.h</span></span>  <br/> |
|<span data-ttu-id="9f481-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="9f481-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="9f481-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="9f481-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="9f481-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="9f481-110">Called by:</span></span>  <br/> |<span data-ttu-id="9f481-111">服务提供程序</span><span class="sxs-lookup"><span data-stu-id="9f481-111">Service providers</span></span>  <br/> |
   
```cpp
ULONG FBadPropTag(
  ULONG ulPropTag
);
```

## <a name="parameters"></a><span data-ttu-id="9f481-112">参数</span><span class="sxs-lookup"><span data-stu-id="9f481-112">Parameters</span></span>

 <span data-ttu-id="9f481-113">_ulPropTag_</span><span class="sxs-lookup"><span data-stu-id="9f481-113">_ulPropTag_</span></span>
  
> <span data-ttu-id="9f481-114">实时要验证的属性标记。</span><span class="sxs-lookup"><span data-stu-id="9f481-114">[in] The property tag to be validated.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="9f481-115">返回值</span><span class="sxs-lookup"><span data-stu-id="9f481-115">Return value</span></span>

<span data-ttu-id="9f481-116">TRUE</span><span class="sxs-lookup"><span data-stu-id="9f481-116">TRUE</span></span> 
  
> <span data-ttu-id="9f481-117">指定的属性标记不是有效的 MAPI 属性标记。</span><span class="sxs-lookup"><span data-stu-id="9f481-117">The specified property tag is not a valid MAPI property tag.</span></span> 
    
<span data-ttu-id="9f481-118">FALSE</span><span class="sxs-lookup"><span data-stu-id="9f481-118">FALSE</span></span> 
  
> <span data-ttu-id="9f481-119">指定的属性标记是一个有效的 MAPI 属性标记。</span><span class="sxs-lookup"><span data-stu-id="9f481-119">The specified property tag is a valid MAPI property tag.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="9f481-120">注解</span><span class="sxs-lookup"><span data-stu-id="9f481-120">Remarks</span></span>

<span data-ttu-id="9f481-121">**FBadPropTag**函数根据 MAPI 定义验证指定的属性标记。</span><span class="sxs-lookup"><span data-stu-id="9f481-121">The **FBadPropTag** function validates the specified property tag based on MAPI definitions.</span></span> <span data-ttu-id="9f481-122">它使 sures 属性类型是 MAPI 定义的类型之一, 并且属性标识符定义为该类型。</span><span class="sxs-lookup"><span data-stu-id="9f481-122">It make sures that the property type is one of the types defined by MAPI and that the property identifier is defined to be of that type.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="9f481-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9f481-123">See also</span></span>



[<span data-ttu-id="9f481-124">FBadProp</span><span class="sxs-lookup"><span data-stu-id="9f481-124">FBadProp</span></span>](fbadprop.md)

