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
ms.openlocfilehash: b8521172b441bd26a6562aa28f836d453544928f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778796"
---
# <a name="sizedspropproblemarray"></a><span data-ttu-id="f8ad0-103">SizedSPropProblemArray</span><span class="sxs-lookup"><span data-stu-id="f8ad0-103">SizedSPropProblemArray</span></span>

<span data-ttu-id="f8ad0-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="f8ad0-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="f8ad0-105">创建包含指定的数目的[SPropProblem](spropproblem.md)结构的命名的[SPropProblemArray](spropproblemarray.md)结构。</span><span class="sxs-lookup"><span data-stu-id="f8ad0-105">Creates a named [SPropProblemArray](spropproblemarray.md) structure that contains a specified number of [SPropProblem](spropproblem.md) structures.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="f8ad0-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="f8ad0-106">Header file:</span></span>  <br/> |<span data-ttu-id="f8ad0-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="f8ad0-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="f8ad0-108">相关的结构：</span><span class="sxs-lookup"><span data-stu-id="f8ad0-108">Related structure:</span></span>  <br/> |<span data-ttu-id="f8ad0-109">**SPropProblemArray**</span><span class="sxs-lookup"><span data-stu-id="f8ad0-109">**SPropProblemArray**</span></span> <br/> |
   
```cpp
SizedSPropProblemArray(_cprob, _name)
```

## <a name="parameters"></a><span data-ttu-id="f8ad0-110">参数</span><span class="sxs-lookup"><span data-stu-id="f8ad0-110">Parameters</span></span>

<span data-ttu-id="f8ad0-111">__cprob_</span><span class="sxs-lookup"><span data-stu-id="f8ad0-111">__cprob_</span></span>
  
> <span data-ttu-id="f8ad0-112">要包含在新结构**SPropProblem**结构的计数。</span><span class="sxs-lookup"><span data-stu-id="f8ad0-112">Count of **SPropProblem** structures to be included in the new structure.</span></span> 
    
<span data-ttu-id="f8ad0-113">__名称_</span><span class="sxs-lookup"><span data-stu-id="f8ad0-113">__name_</span></span>
  
> <span data-ttu-id="f8ad0-114">新结构的的名称。</span><span class="sxs-lookup"><span data-stu-id="f8ad0-114">Name for the new structure.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="f8ad0-115">说明</span><span class="sxs-lookup"><span data-stu-id="f8ad0-115">Remarks</span></span>

<span data-ttu-id="f8ad0-116">使用**SizedSPropProblemArray**宏来使用显式边界创建属性问题数组。</span><span class="sxs-lookup"><span data-stu-id="f8ad0-116">Use the **SizedSPropProblemArray** macro to create a property problem array with explicit bounds.</span></span> <span data-ttu-id="f8ad0-117">若要使用新结构的结果从**SizedSPropProblemArray**宏作为指针指向**SPropProblemArray**结构，执行下列转换：</span><span class="sxs-lookup"><span data-stu-id="f8ad0-117">To use the new structure that results from the **SizedSPropProblemArray** macro as a pointer to an **SPropProblemArray** structure, perform the following cast:</span></span> 
  
```cpp
lpPropProbArray = (LPSPropProblemArray) &SizedSPropProblemArray;
```

## <a name="see-also"></a><span data-ttu-id="f8ad0-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f8ad0-118">See also</span></span>

- [<span data-ttu-id="f8ad0-119">SPropProblemArray</span><span class="sxs-lookup"><span data-stu-id="f8ad0-119">SPropProblemArray</span></span>](spropproblemarray.md)
- [<span data-ttu-id="f8ad0-120">SPropProblem</span><span class="sxs-lookup"><span data-stu-id="f8ad0-120">SPropProblem</span></span>](spropproblem.md)
- [<span data-ttu-id="f8ad0-121">与结构相关的宏</span><span class="sxs-lookup"><span data-stu-id="f8ad0-121">Macros Related to Structures</span></span>](macros-related-to-structures.md)

