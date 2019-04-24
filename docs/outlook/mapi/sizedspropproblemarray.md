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
ms.openlocfilehash: b3818e5e1429c7e2b7d5f7533db733ba29e672c8
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32282689"
---
# <a name="sizedspropproblemarray"></a><span data-ttu-id="8f6c2-103">SizedSPropProblemArray</span><span class="sxs-lookup"><span data-stu-id="8f6c2-103">SizedSPropProblemArray</span></span>

<span data-ttu-id="8f6c2-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="8f6c2-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="8f6c2-105">创建一个包含指定数量的[SPropProblem](spropproblem.md)结构的命名[SPropProblemArray](spropproblemarray.md)结构。</span><span class="sxs-lookup"><span data-stu-id="8f6c2-105">Creates a named [SPropProblemArray](spropproblemarray.md) structure that contains a specified number of [SPropProblem](spropproblem.md) structures.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="8f6c2-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="8f6c2-106">Header file:</span></span>  <br/> |<span data-ttu-id="8f6c2-107">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="8f6c2-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="8f6c2-108">相关结构:</span><span class="sxs-lookup"><span data-stu-id="8f6c2-108">Related structure:</span></span>  <br/> |<span data-ttu-id="8f6c2-109">**SPropProblemArray**</span><span class="sxs-lookup"><span data-stu-id="8f6c2-109">**SPropProblemArray**</span></span> <br/> |
   
```cpp
SizedSPropProblemArray(_cprob, _name)
```

## <a name="parameters"></a><span data-ttu-id="8f6c2-110">参数</span><span class="sxs-lookup"><span data-stu-id="8f6c2-110">Parameters</span></span>

<span data-ttu-id="8f6c2-111">__cprob_</span><span class="sxs-lookup"><span data-stu-id="8f6c2-111">__cprob_</span></span>
  
> <span data-ttu-id="8f6c2-112">要包含在新结构中的**SPropProblem**结构的计数。</span><span class="sxs-lookup"><span data-stu-id="8f6c2-112">Count of **SPropProblem** structures to be included in the new structure.</span></span> 
    
<span data-ttu-id="8f6c2-113">__名称_</span><span class="sxs-lookup"><span data-stu-id="8f6c2-113">__name_</span></span>
  
> <span data-ttu-id="8f6c2-114">新结构的名称。</span><span class="sxs-lookup"><span data-stu-id="8f6c2-114">Name for the new structure.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="8f6c2-115">注解</span><span class="sxs-lookup"><span data-stu-id="8f6c2-115">Remarks</span></span>

<span data-ttu-id="8f6c2-116">使用**SizedSPropProblemArray**宏创建具有显式界限的属性问题数组。</span><span class="sxs-lookup"><span data-stu-id="8f6c2-116">Use the **SizedSPropProblemArray** macro to create a property problem array with explicit bounds.</span></span> <span data-ttu-id="8f6c2-117">若要使用作为指向**SPropProblemArray**结构的指针的**SizedSPropProblemArray**宏生成的新结构, 请执行以下转换:</span><span class="sxs-lookup"><span data-stu-id="8f6c2-117">To use the new structure that results from the **SizedSPropProblemArray** macro as a pointer to an **SPropProblemArray** structure, perform the following cast:</span></span> 
  
```cpp
lpPropProbArray = (LPSPropProblemArray) &SizedSPropProblemArray;
```

## <a name="see-also"></a><span data-ttu-id="8f6c2-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8f6c2-118">See also</span></span>

- [<span data-ttu-id="8f6c2-119">SPropProblemArray</span><span class="sxs-lookup"><span data-stu-id="8f6c2-119">SPropProblemArray</span></span>](spropproblemarray.md)
- [<span data-ttu-id="8f6c2-120">SPropProblem</span><span class="sxs-lookup"><span data-stu-id="8f6c2-120">SPropProblem</span></span>](spropproblem.md)
- [<span data-ttu-id="8f6c2-121">与结构相关的宏</span><span class="sxs-lookup"><span data-stu-id="8f6c2-121">Macros Related to Structures</span></span>](macros-related-to-structures.md)

