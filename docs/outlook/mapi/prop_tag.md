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
ms.openlocfilehash: 7ab4e4e9e51849037a91a071f16294cfdf10870c
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33425881"
---
# <a name="prop_tag"></a><span data-ttu-id="3772f-103">PROP_TAG</span><span class="sxs-lookup"><span data-stu-id="3772f-103">PROP_TAG</span></span>

<span data-ttu-id="3772f-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="3772f-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="3772f-105">返回通过组合指定的属性类型和标识符创建的属性标记。</span><span class="sxs-lookup"><span data-stu-id="3772f-105">Returns a property tag created by combining a specified property type and identifier.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="3772f-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="3772f-106">Header file:</span></span>  <br/> |<span data-ttu-id="3772f-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="3772f-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="3772f-108">相关结构：</span><span class="sxs-lookup"><span data-stu-id="3772f-108">Related structure:</span></span>  <br/> |[<span data-ttu-id="3772f-109">SPropValue</span><span class="sxs-lookup"><span data-stu-id="3772f-109">SPropValue</span></span>](spropvalue.md) <br/> |
   
```cpp
PROP_TAG (ulPropType, ulPropID)
```

## <a name="parameters"></a><span data-ttu-id="3772f-110">参数</span><span class="sxs-lookup"><span data-stu-id="3772f-110">Parameters</span></span>

<span data-ttu-id="3772f-111">_ulPropType_</span><span class="sxs-lookup"><span data-stu-id="3772f-111">_ulPropType_</span></span>
  
> <span data-ttu-id="3772f-112">新属性标记的属性类型。</span><span class="sxs-lookup"><span data-stu-id="3772f-112">Property type for the new property tag.</span></span>
    
<span data-ttu-id="3772f-113">_ulPropID_</span><span class="sxs-lookup"><span data-stu-id="3772f-113">_ulPropID_</span></span>
  
> <span data-ttu-id="3772f-114">新属性标记的属性标识符。</span><span class="sxs-lookup"><span data-stu-id="3772f-114">Property identifier for the new property tag.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="3772f-115">备注</span><span class="sxs-lookup"><span data-stu-id="3772f-115">Remarks</span></span>

<span data-ttu-id="3772f-116">**PROP \_ TAG** 宏为 _ulPropType_ 类型的属性和 _ulPropID_ 中指定的标识符创建属性标记。</span><span class="sxs-lookup"><span data-stu-id="3772f-116">The **PROP\_TAG** macro creates a property tag for a property of type  _ulPropType_ and the identifier that is specified in  _ulPropID_.</span></span> <span data-ttu-id="3772f-117">例如，可以使用以下宏创建条目标识符 **PROP_TAG标记：**</span><span class="sxs-lookup"><span data-stu-id="3772f-117">For example, a property tag for an entry identifier can be created by using the **PROP_TAG** macro as follows:</span></span> 
  
```cpp
PROP_TAG( PT_BINARY, 0x0FFF)

```

<span data-ttu-id="3772f-118">返回的属性标记的低顺序 16 位包含属性类型 PT_BINARY，高顺序 16 位包含属性标识符 0xFFFF。</span><span class="sxs-lookup"><span data-stu-id="3772f-118">The low-order 16 bits of the returned property tag contain the property type, PT_BINARY, and the high-order 16 bits contain the property identifier, 0xFFFF.</span></span>
  
<span data-ttu-id="3772f-119">有关属性标记详细信息，请参阅 [MAPI Property Tags](mapi-property-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="3772f-119">For more information about property tags, see [MAPI Property Tags](mapi-property-tags.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="3772f-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3772f-120">See also</span></span>

- [<span data-ttu-id="3772f-121">SPropValue</span><span class="sxs-lookup"><span data-stu-id="3772f-121">SPropValue</span></span>](spropvalue.md)
- [<span data-ttu-id="3772f-122">与结构相关的宏</span><span class="sxs-lookup"><span data-stu-id="3772f-122">Macros Related to Structures</span></span>](macros-related-to-structures.md)

