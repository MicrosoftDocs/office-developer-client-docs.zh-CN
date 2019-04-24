---
title: PROP_TYPE
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PROP_TYPE
api_type:
- COM
ms.assetid: 746d63fa-bfb7-479f-94dc-ba40011c1ec9
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 0c33633c4decd697cf241f8b7c27360f776a1ade
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32332758"
---
# <a name="proptype"></a><span data-ttu-id="921de-103">PROP_TYPE</span><span class="sxs-lookup"><span data-stu-id="921de-103">PROP_TYPE</span></span>

  
  
<span data-ttu-id="921de-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="921de-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="921de-105">返回指定的属性标记的属性类型。</span><span class="sxs-lookup"><span data-stu-id="921de-105">Returns the property type of a specified property tag.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="921de-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="921de-106">Header file:</span></span>  <br/> |<span data-ttu-id="921de-107">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="921de-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="921de-108">相关结构:</span><span class="sxs-lookup"><span data-stu-id="921de-108">Related structure:</span></span>  <br/> |[<span data-ttu-id="921de-109">SPropValue</span><span class="sxs-lookup"><span data-stu-id="921de-109">SPropValue</span></span>](spropvalue.md) <br/> |
   
```cpp
PROP_TYPE (ulPropTag)
```

## <a name="parameters"></a><span data-ttu-id="921de-110">参数</span><span class="sxs-lookup"><span data-stu-id="921de-110">Parameters</span></span>

 <span data-ttu-id="921de-111">_ulPropTag_</span><span class="sxs-lookup"><span data-stu-id="921de-111">_ulPropTag_</span></span>
  
> <span data-ttu-id="921de-112">包含要返回的属性类型的属性标记。</span><span class="sxs-lookup"><span data-stu-id="921de-112">Property tag that contains the property type to be returned.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="921de-113">注解</span><span class="sxs-lookup"><span data-stu-id="921de-113">Remarks</span></span>

<span data-ttu-id="921de-114">**PROP_TYPE**宏可用于确定属性的类型。</span><span class="sxs-lookup"><span data-stu-id="921de-114">The **PROP_TYPE** macro can be used to determine the type of a property.</span></span> <span data-ttu-id="921de-115">例如, 调用 PROP_TYPE (**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md))) 会导致返回 PT_BINARY 值。</span><span class="sxs-lookup"><span data-stu-id="921de-115">For example, calling PROP_TYPE (**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md))) results in the value PT_BINARY being returned.</span></span>
  
<span data-ttu-id="921de-116">每个属性标记都包含低序位字 (0 到 15) 中的属性类型和高序位字 (位16到 31) 中的属性标识符。</span><span class="sxs-lookup"><span data-stu-id="921de-116">Every property tag contains the property type in the low-order word (bits 0 through 15) and the property identifier in the high-order word (bits 16 through 31).</span></span> <span data-ttu-id="921de-117">**PROP_TYPE**宏提取属性类型, 并将其放在要返回的整数的0到15位。</span><span class="sxs-lookup"><span data-stu-id="921de-117">The **PROP_TYPE** macro extracts the property type and puts it in bits 0 through 15 of the integer to be returned.</span></span> <span data-ttu-id="921de-118">返回值的剩余位设置为零。</span><span class="sxs-lookup"><span data-stu-id="921de-118">The remaining bits of the return value are set to zeros.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="921de-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="921de-119">See also</span></span>



[<span data-ttu-id="921de-120">SPropValue</span><span class="sxs-lookup"><span data-stu-id="921de-120">SPropValue</span></span>](spropvalue.md)


[<span data-ttu-id="921de-121">与结构相关的宏</span><span class="sxs-lookup"><span data-stu-id="921de-121">Macros Related to Structures</span></span>](macros-related-to-structures.md)

