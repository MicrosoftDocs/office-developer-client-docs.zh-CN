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
ms.openlocfilehash: cbead0a9953ae5106e1fcc7d07d965d4dc7bacb9
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22570987"
---
# <a name="proptag"></a><span data-ttu-id="2efce-103">PROP_TAG</span><span class="sxs-lookup"><span data-stu-id="2efce-103">PROP_TAG</span></span>

<span data-ttu-id="2efce-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="2efce-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="2efce-105">返回属性标记创建的组合指定的属性类型和标识符。</span><span class="sxs-lookup"><span data-stu-id="2efce-105">Returns a property tag created by combining a specified property type and identifier.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="2efce-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="2efce-106">Header file:</span></span>  <br/> |<span data-ttu-id="2efce-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="2efce-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="2efce-108">相关的结构：</span><span class="sxs-lookup"><span data-stu-id="2efce-108">Related structure:</span></span>  <br/> |[<span data-ttu-id="2efce-109">SPropValue</span><span class="sxs-lookup"><span data-stu-id="2efce-109">SPropValue</span></span>](spropvalue.md) <br/> |
   
```cpp
PROP_TAG (ulPropType, ulPropID)
```

## <a name="parameters"></a><span data-ttu-id="2efce-110">参数</span><span class="sxs-lookup"><span data-stu-id="2efce-110">Parameters</span></span>

<span data-ttu-id="2efce-111">_ulPropType_</span><span class="sxs-lookup"><span data-stu-id="2efce-111">_ulPropType_</span></span>
  
> <span data-ttu-id="2efce-112">新属性标记的属性类型。</span><span class="sxs-lookup"><span data-stu-id="2efce-112">Property type for the new property tag.</span></span>
    
<span data-ttu-id="2efce-113">_ulPropID_</span><span class="sxs-lookup"><span data-stu-id="2efce-113">_ulPropID_</span></span>
  
> <span data-ttu-id="2efce-114">新属性标记属性标识符。</span><span class="sxs-lookup"><span data-stu-id="2efce-114">Property identifier for the new property tag.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="2efce-115">注解</span><span class="sxs-lookup"><span data-stu-id="2efce-115">Remarks</span></span>

<span data-ttu-id="2efce-116">**属性\_标记**宏创建类型_ulPropType_和_ulPropID_中指定的标识符的属性的属性标记。</span><span class="sxs-lookup"><span data-stu-id="2efce-116">The **PROP\_TAG** macro creates a property tag for a property of type  _ulPropType_ and the identifier that is specified in  _ulPropID_.</span></span> <span data-ttu-id="2efce-117">例如，可以通过，如下所示使用**PROP_TAG**宏创建的项标识符的属性标记：</span><span class="sxs-lookup"><span data-stu-id="2efce-117">For example, a property tag for an entry identifier can be created by using the **PROP_TAG** macro as follows:</span></span> 
  
```cpp
PROP_TAG( PT_BINARY, 0x0FFF)

```

<span data-ttu-id="2efce-118">低序位 16 位的返回的属性标记包含属性类型，PT_BINARY，但高阶 16 位包含属性标识符，0xFFFF。</span><span class="sxs-lookup"><span data-stu-id="2efce-118">The low-order 16 bits of the returned property tag contain the property type, PT_BINARY, and the high-order 16 bits contain the property identifier, 0xFFFF.</span></span>
  
<span data-ttu-id="2efce-119">有关属性标记的详细信息，请参阅[MAPI 属性标记](mapi-property-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="2efce-119">For more information about property tags, see [MAPI Property Tags](mapi-property-tags.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="2efce-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2efce-120">See also</span></span>

- [<span data-ttu-id="2efce-121">SPropValue</span><span class="sxs-lookup"><span data-stu-id="2efce-121">SPropValue</span></span>](spropvalue.md)
- [<span data-ttu-id="2efce-122">与结构相关的宏</span><span class="sxs-lookup"><span data-stu-id="2efce-122">Macros Related to Structures</span></span>](macros-related-to-structures.md)

