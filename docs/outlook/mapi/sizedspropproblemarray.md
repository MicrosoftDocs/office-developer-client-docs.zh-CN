---
title: SizedSPropProblemArray
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.SizedSPropProblemArray
api_type:
- COM
ms.assetid: 2fc3febb-8c69-4315-a112-a28eee98013d
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: bbced8412c2c3438c58af74ef072a46606b59ddc
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22594612"
---
# <a name="sizedspropproblemarray"></a><span data-ttu-id="28f66-103">SizedSPropProblemArray</span><span class="sxs-lookup"><span data-stu-id="28f66-103">SizedSPropProblemArray</span></span>

<span data-ttu-id="28f66-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="28f66-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="28f66-105">创建包含指定的数目的[SPropProblem](spropproblem.md)结构的命名的[SPropProblemArray](spropproblemarray.md)结构。</span><span class="sxs-lookup"><span data-stu-id="28f66-105">Creates a named [SPropProblemArray](spropproblemarray.md) structure that contains a specified number of [SPropProblem](spropproblem.md) structures.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="28f66-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="28f66-106">Header file:</span></span>  <br/> |<span data-ttu-id="28f66-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="28f66-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="28f66-108">相关的结构：</span><span class="sxs-lookup"><span data-stu-id="28f66-108">Related structure:</span></span>  <br/> |<span data-ttu-id="28f66-109">**SPropProblemArray**</span><span class="sxs-lookup"><span data-stu-id="28f66-109">**SPropProblemArray**</span></span> <br/> |
   
```cpp
SizedSPropProblemArray(_cprob, _name)
```

## <a name="parameters"></a><span data-ttu-id="28f66-110">参数</span><span class="sxs-lookup"><span data-stu-id="28f66-110">Parameters</span></span>

<span data-ttu-id="28f66-111">__cprob_</span><span class="sxs-lookup"><span data-stu-id="28f66-111">__cprob_</span></span>
  
> <span data-ttu-id="28f66-112">要包含在新结构**SPropProblem**结构的计数。</span><span class="sxs-lookup"><span data-stu-id="28f66-112">Count of **SPropProblem** structures to be included in the new structure.</span></span> 
    
<span data-ttu-id="28f66-113">__名称_</span><span class="sxs-lookup"><span data-stu-id="28f66-113">__name_</span></span>
  
> <span data-ttu-id="28f66-114">新结构的的名称。</span><span class="sxs-lookup"><span data-stu-id="28f66-114">Name for the new structure.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="28f66-115">注解</span><span class="sxs-lookup"><span data-stu-id="28f66-115">Remarks</span></span>

<span data-ttu-id="28f66-116">使用**SizedSPropProblemArray**宏来使用显式边界创建属性问题数组。</span><span class="sxs-lookup"><span data-stu-id="28f66-116">Use the **SizedSPropProblemArray** macro to create a property problem array with explicit bounds.</span></span> <span data-ttu-id="28f66-117">若要使用新结构的结果从**SizedSPropProblemArray**宏作为指针指向**SPropProblemArray**结构，执行下列转换：</span><span class="sxs-lookup"><span data-stu-id="28f66-117">To use the new structure that results from the **SizedSPropProblemArray** macro as a pointer to an **SPropProblemArray** structure, perform the following cast:</span></span> 
  
```cpp
lpPropProbArray = (LPSPropProblemArray) &SizedSPropProblemArray;
```

## <a name="see-also"></a><span data-ttu-id="28f66-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="28f66-118">See also</span></span>

- [<span data-ttu-id="28f66-119">SPropProblemArray</span><span class="sxs-lookup"><span data-stu-id="28f66-119">SPropProblemArray</span></span>](spropproblemarray.md)
- [<span data-ttu-id="28f66-120">SPropProblem</span><span class="sxs-lookup"><span data-stu-id="28f66-120">SPropProblem</span></span>](spropproblem.md)
- [<span data-ttu-id="28f66-121">与结构相关的宏</span><span class="sxs-lookup"><span data-stu-id="28f66-121">Macros Related to Structures</span></span>](macros-related-to-structures.md)

