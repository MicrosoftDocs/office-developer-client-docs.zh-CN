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
ms.openlocfilehash: d1503aaa5bddd23a90035219901e1dc232dbd026
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774908"
---
# <a name="fbadproptag"></a><span data-ttu-id="2f329-103">FBadPropTag</span><span class="sxs-lookup"><span data-stu-id="2f329-103">FBadPropTag</span></span>

  
  
<span data-ttu-id="2f329-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="2f329-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="2f329-105">验证指定的属性标记。</span><span class="sxs-lookup"><span data-stu-id="2f329-105">Validates a specified property tag.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="2f329-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="2f329-106">Header file:</span></span>  <br/> |<span data-ttu-id="2f329-107">Mapival.h</span><span class="sxs-lookup"><span data-stu-id="2f329-107">Mapival.h</span></span>  <br/> |
|<span data-ttu-id="2f329-108">通过实现：</span><span class="sxs-lookup"><span data-stu-id="2f329-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="2f329-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="2f329-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="2f329-110">调用：</span><span class="sxs-lookup"><span data-stu-id="2f329-110">Called by:</span></span>  <br/> |<span data-ttu-id="2f329-111">服务提供商</span><span class="sxs-lookup"><span data-stu-id="2f329-111">Service providers</span></span>  <br/> |
   
```cpp
ULONG FBadPropTag(
  ULONG ulPropTag
);
```

## <a name="parameters"></a><span data-ttu-id="2f329-112">参数</span><span class="sxs-lookup"><span data-stu-id="2f329-112">Parameters</span></span>

 <span data-ttu-id="2f329-113">_ulPropTag_</span><span class="sxs-lookup"><span data-stu-id="2f329-113">_ulPropTag_</span></span>
  
> <span data-ttu-id="2f329-114">[in]要验证属性标记。</span><span class="sxs-lookup"><span data-stu-id="2f329-114">[in] The property tag to be validated.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="2f329-115">返回值</span><span class="sxs-lookup"><span data-stu-id="2f329-115">Return value</span></span>

<span data-ttu-id="2f329-116">TRUE</span><span class="sxs-lookup"><span data-stu-id="2f329-116">TRUE</span></span> 
  
> <span data-ttu-id="2f329-117">指定的属性标记不是有效的 MAPI 属性标记。</span><span class="sxs-lookup"><span data-stu-id="2f329-117">The specified property tag is not a valid MAPI property tag.</span></span> 
    
<span data-ttu-id="2f329-118">FALSE</span><span class="sxs-lookup"><span data-stu-id="2f329-118">FALSE</span></span> 
  
> <span data-ttu-id="2f329-119">指定的属性标记是一个有效的 MAPI 属性标记。</span><span class="sxs-lookup"><span data-stu-id="2f329-119">The specified property tag is a valid MAPI property tag.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="2f329-120">说明</span><span class="sxs-lookup"><span data-stu-id="2f329-120">Remarks</span></span>

<span data-ttu-id="2f329-121">**FBadPropTag**函数验证基于 MAPI 定义的指定的属性标记。</span><span class="sxs-lookup"><span data-stu-id="2f329-121">The **FBadPropTag** function validates the specified property tag based on MAPI definitions.</span></span> <span data-ttu-id="2f329-122">它使的 sures 属性类型之一的 MAPI 所定义的类型和属性标识符定义的类型。</span><span class="sxs-lookup"><span data-stu-id="2f329-122">It make sures that the property type is one of the types defined by MAPI and that the property identifier is defined to be of that type.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="2f329-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2f329-123">See also</span></span>



[<span data-ttu-id="2f329-124">FBadProp</span><span class="sxs-lookup"><span data-stu-id="2f329-124">FBadProp</span></span>](fbadprop.md)

