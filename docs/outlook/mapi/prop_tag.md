---
title: PROP_TAG
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PROP_TAG
api_type:
- COM
ms.assetid: d8c9d18c-4043-41f3-8501-8be8e3a2c9ac
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 9e53c39b713aa782eb387b85667f5ded6193006f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778551"
---
# <a name="proptag"></a><span data-ttu-id="26b35-103">PROP_TAG</span><span class="sxs-lookup"><span data-stu-id="26b35-103">PROP_TAG</span></span>

<span data-ttu-id="26b35-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="26b35-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="26b35-105">返回属性标记创建的组合指定的属性类型和标识符。</span><span class="sxs-lookup"><span data-stu-id="26b35-105">Returns a property tag created by combining a specified property type and identifier.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="26b35-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="26b35-106">Header file:</span></span>  <br/> |<span data-ttu-id="26b35-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="26b35-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="26b35-108">相关的结构：</span><span class="sxs-lookup"><span data-stu-id="26b35-108">Related structure:</span></span>  <br/> |[<span data-ttu-id="26b35-109">SPropValue</span><span class="sxs-lookup"><span data-stu-id="26b35-109">SPropValue</span></span>](spropvalue.md) <br/> |
   
```cpp
PROP_TAG (ulPropType, ulPropID)
```

## <a name="parameters"></a><span data-ttu-id="26b35-110">参数</span><span class="sxs-lookup"><span data-stu-id="26b35-110">Parameters</span></span>

<span data-ttu-id="26b35-111">_ulPropType_</span><span class="sxs-lookup"><span data-stu-id="26b35-111">_ulPropType_</span></span>
  
> <span data-ttu-id="26b35-112">新属性标记的属性类型。</span><span class="sxs-lookup"><span data-stu-id="26b35-112">Property type for the new property tag.</span></span>
    
<span data-ttu-id="26b35-113">_ulPropID_</span><span class="sxs-lookup"><span data-stu-id="26b35-113">_ulPropID_</span></span>
  
> <span data-ttu-id="26b35-114">新属性标记属性标识符。</span><span class="sxs-lookup"><span data-stu-id="26b35-114">Property identifier for the new property tag.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="26b35-115">说明</span><span class="sxs-lookup"><span data-stu-id="26b35-115">Remarks</span></span>

<span data-ttu-id="26b35-116">**属性\_标记**宏创建类型_ulPropType_和_ulPropID_中指定的标识符的属性的属性标记。</span><span class="sxs-lookup"><span data-stu-id="26b35-116">The **PROP\_TAG** macro creates a property tag for a property of type  _ulPropType_ and the identifier that is specified in  _ulPropID_.</span></span> <span data-ttu-id="26b35-117">例如，可以通过，如下所示使用**PROP_TAG**宏创建的项标识符的属性标记：</span><span class="sxs-lookup"><span data-stu-id="26b35-117">For example, a property tag for an entry identifier can be created by using the **PROP_TAG** macro as follows:</span></span> 
  
```cpp
PROP_TAG( PT_BINARY, 0x0FFF)

```

<span data-ttu-id="26b35-118">低序位 16 位的返回的属性标记包含属性类型，PT_BINARY，但高阶 16 位包含属性标识符，0xFFFF。</span><span class="sxs-lookup"><span data-stu-id="26b35-118">The low-order 16 bits of the returned property tag contain the property type, PT_BINARY, and the high-order 16 bits contain the property identifier, 0xFFFF.</span></span>
  
<span data-ttu-id="26b35-119">有关属性标记的详细信息，请参阅[MAPI 属性标记](mapi-property-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="26b35-119">For more information about property tags, see [MAPI Property Tags](mapi-property-tags.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="26b35-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="26b35-120">See also</span></span>

- [<span data-ttu-id="26b35-121">SPropValue</span><span class="sxs-lookup"><span data-stu-id="26b35-121">SPropValue</span></span>](spropvalue.md)
- [<span data-ttu-id="26b35-122">与结构相关的宏</span><span class="sxs-lookup"><span data-stu-id="26b35-122">Macros Related to Structures</span></span>](macros-related-to-structures.md)

