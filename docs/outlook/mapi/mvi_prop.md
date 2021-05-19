---
title: MVI_PROP
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.MVI_PROP
api_type:
- COM
ms.assetid: d7f07524-6935-4a60-aaf3-3f753ea8d86a
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 087d38face72e1e067350b1959b37313ebbd7c44
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33410677"
---
# <a name="mvi_prop"></a><span data-ttu-id="d4c8e-103">MVI_PROP</span><span class="sxs-lookup"><span data-stu-id="d4c8e-103">MVI_PROP</span></span>

  
  
<span data-ttu-id="d4c8e-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="d4c8e-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="d4c8e-105">设置MVI_FLAG属性的属性值。</span><span class="sxs-lookup"><span data-stu-id="d4c8e-105">Sets the MVI_FLAG for a specified property.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="d4c8e-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="d4c8e-106">Header file:</span></span>  <br/> |<span data-ttu-id="d4c8e-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="d4c8e-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="d4c8e-108">相关结构：</span><span class="sxs-lookup"><span data-stu-id="d4c8e-108">Related structure:</span></span>  <br/> |[<span data-ttu-id="d4c8e-109">SPropValue</span><span class="sxs-lookup"><span data-stu-id="d4c8e-109">SPropValue</span></span>](spropvalue.md) <br/> |
   
```cpp
MVI_PROP (tag)
```

## <a name="parameters"></a><span data-ttu-id="d4c8e-110">参数</span><span class="sxs-lookup"><span data-stu-id="d4c8e-110">Parameters</span></span>

 <span data-ttu-id="d4c8e-111">_tag_</span><span class="sxs-lookup"><span data-stu-id="d4c8e-111">_tag_</span></span>
  
> <span data-ttu-id="d4c8e-112">要修改的属性标记。</span><span class="sxs-lookup"><span data-stu-id="d4c8e-112">The property tag to be modified.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="d4c8e-113">备注</span><span class="sxs-lookup"><span data-stu-id="d4c8e-113">Remarks</span></span>

<span data-ttu-id="d4c8e-114">该MVI_FLAG组合了 MV_FLAG 设置，将属性标识为多值属性和 MV_INSTANCE，并请求多值属性显示在多行的表中。</span><span class="sxs-lookup"><span data-stu-id="d4c8e-114">The MVI_FLAG combines the setting of MV_FLAG, identifying a property as multi-valued, and MV_INSTANCE, requesting that a multi-valued property be displayed in a table in multiple rows.</span></span> <span data-ttu-id="d4c8e-115">修改受影响属性的属性类型，但标识符保持不变。</span><span class="sxs-lookup"><span data-stu-id="d4c8e-115">The property type of the affected property is modified, but the identifier remains unchanged.</span></span> 
  
<span data-ttu-id="d4c8e-116">例如，当MVI_PROP宏应用于 PT_FLOAT 类型的属性时，其类型将更改为 PT_MV_FLOAT。</span><span class="sxs-lookup"><span data-stu-id="d4c8e-116">For example, when the MVI_PROP macro is applied to a property of type PT_FLOAT, its type is changed to PT_MV_FLOAT.</span></span> <span data-ttu-id="d4c8e-117">当包含在表中时，多行用于表示每个值具有一行的属性。</span><span class="sxs-lookup"><span data-stu-id="d4c8e-117">When included in a table, multiple rows are used to represent the property that has one row for each value.</span></span> <span data-ttu-id="d4c8e-118">其他列的属性是重复的。</span><span class="sxs-lookup"><span data-stu-id="d4c8e-118">The properties for the other columns are repeated.</span></span> 
  
<span data-ttu-id="d4c8e-119">有关这些标志的信息，请参阅 [MAPI 属性类型概述](mapi-property-type-overview.md) 和 [处理多值列](working-with-multivalued-columns.md)。</span><span class="sxs-lookup"><span data-stu-id="d4c8e-119">For more information about these flags, see [MAPI Property Type Overview](mapi-property-type-overview.md) and [Working with Multivalued Columns](working-with-multivalued-columns.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d4c8e-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d4c8e-120">See also</span></span>



[<span data-ttu-id="d4c8e-121">SPropValue</span><span class="sxs-lookup"><span data-stu-id="d4c8e-121">SPropValue</span></span>](spropvalue.md)


[<span data-ttu-id="d4c8e-122">与结构相关的宏</span><span class="sxs-lookup"><span data-stu-id="d4c8e-122">Macros Related to Structures</span></span>](macros-related-to-structures.md)

