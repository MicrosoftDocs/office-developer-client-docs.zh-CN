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
ms.openlocfilehash: f8f58ee18095dec8a222ae8b5a19cbefbaafa663
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776556"
---
# <a name="mviprop"></a><span data-ttu-id="3e69c-103">MVI_PROP</span><span class="sxs-lookup"><span data-stu-id="3e69c-103">MVI_PROP</span></span>

  
  
<span data-ttu-id="3e69c-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="3e69c-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="3e69c-105">设置指定属性 MVI_FLAG。</span><span class="sxs-lookup"><span data-stu-id="3e69c-105">Sets the MVI_FLAG for a specified property.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="3e69c-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="3e69c-106">Header file:</span></span>  <br/> |<span data-ttu-id="3e69c-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="3e69c-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="3e69c-108">相关的结构：</span><span class="sxs-lookup"><span data-stu-id="3e69c-108">Related structure:</span></span>  <br/> |[<span data-ttu-id="3e69c-109">SPropValue</span><span class="sxs-lookup"><span data-stu-id="3e69c-109">SPropValue</span></span>](spropvalue.md) <br/> |
   
```cpp
MVI_PROP (tag)
```

## <a name="parameters"></a><span data-ttu-id="3e69c-110">参数</span><span class="sxs-lookup"><span data-stu-id="3e69c-110">Parameters</span></span>

 <span data-ttu-id="3e69c-111">_标记_</span><span class="sxs-lookup"><span data-stu-id="3e69c-111">_tag_</span></span>
  
> <span data-ttu-id="3e69c-112">要修改的属性标记。</span><span class="sxs-lookup"><span data-stu-id="3e69c-112">The property tag to be modified.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="3e69c-113">说明</span><span class="sxs-lookup"><span data-stu-id="3e69c-113">Remarks</span></span>

<span data-ttu-id="3e69c-114">MVI_FLAG 结合使用的 MV_FLAG，标识为多个值的属性和 MV_INSTANCE，请求的表中多行显示多值的属性的设置。</span><span class="sxs-lookup"><span data-stu-id="3e69c-114">The MVI_FLAG combines the setting of MV_FLAG, identifying a property as multi-valued, and MV_INSTANCE, requesting that a multi-valued property be displayed in a table in multiple rows.</span></span> <span data-ttu-id="3e69c-115">修改受影响的属性的属性类型，但标识符保持不变。</span><span class="sxs-lookup"><span data-stu-id="3e69c-115">The property type of the affected property is modified, but the identifier remains unchanged.</span></span> 
  
<span data-ttu-id="3e69c-116">例如，当 MVI_PROP 宏应用于 PT_FLOAT 类型的属性，其类型更改为 PT_MV_FLOAT。</span><span class="sxs-lookup"><span data-stu-id="3e69c-116">For example, when the MVI_PROP macro is applied to a property of type PT_FLOAT, its type is changed to PT_MV_FLOAT.</span></span> <span data-ttu-id="3e69c-117">当包括在表中，多个行用于表示具有一行，每个值的属性。</span><span class="sxs-lookup"><span data-stu-id="3e69c-117">When included in a table, multiple rows are used to represent the property that has one row for each value.</span></span> <span data-ttu-id="3e69c-118">重复其他列的属性。</span><span class="sxs-lookup"><span data-stu-id="3e69c-118">The properties for the other columns are repeated.</span></span> 
  
<span data-ttu-id="3e69c-119">有关这些标志的详细信息，请参阅[MAPI 属性类型概述](mapi-property-type-overview.md)和[使用多值列](working-with-multivalued-columns.md)。</span><span class="sxs-lookup"><span data-stu-id="3e69c-119">For more information about these flags, see [MAPI Property Type Overview](mapi-property-type-overview.md) and [Working with Multivalued Columns](working-with-multivalued-columns.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="3e69c-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3e69c-120">See also</span></span>



[<span data-ttu-id="3e69c-121">SPropValue</span><span class="sxs-lookup"><span data-stu-id="3e69c-121">SPropValue</span></span>](spropvalue.md)


[<span data-ttu-id="3e69c-122">与结构相关的宏</span><span class="sxs-lookup"><span data-stu-id="3e69c-122">Macros Related to Structures</span></span>](macros-related-to-structures.md)

