---
title: SizedSSortOrderSet
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.SizedSSortOrderSet
api_type:
- COM
ms.assetid: f0b9c2f4-7011-414d-8e6c-ab22893ef132
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 2eb92c3f1555407a77332bd6ec3b2b7202f0553f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778814"
---
# <a name="sizedssortorderset"></a><span data-ttu-id="66e34-103">SizedSSortOrderSet</span><span class="sxs-lookup"><span data-stu-id="66e34-103">SizedSSortOrderSet</span></span>

<span data-ttu-id="66e34-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="66e34-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="66e34-105">创建命名的[SSortOrderSet](ssortorderset.md)结构，其中包含指定的数目的排序次序。</span><span class="sxs-lookup"><span data-stu-id="66e34-105">Creates a named [SSortOrderSet](ssortorderset.md) structure that contains a specified number of sort orders.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="66e34-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="66e34-106">Header file:</span></span>  <br/> |<span data-ttu-id="66e34-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="66e34-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="66e34-108">相关的结构：</span><span class="sxs-lookup"><span data-stu-id="66e34-108">Related structure:</span></span>  <br/> |<span data-ttu-id="66e34-109">**SSortOrderSet**</span><span class="sxs-lookup"><span data-stu-id="66e34-109">**SSortOrderSet**</span></span> <br/> |
   
```cpp
SizedSSortOrderSet (_csort,_name)
```

## <a name="parameters"></a><span data-ttu-id="66e34-110">参数</span><span class="sxs-lookup"><span data-stu-id="66e34-110">Parameters</span></span>

<span data-ttu-id="66e34-111">__csort_</span><span class="sxs-lookup"><span data-stu-id="66e34-111">__csort_</span></span>
  
> <span data-ttu-id="66e34-112">排序次序要包含的新结构中的计数。</span><span class="sxs-lookup"><span data-stu-id="66e34-112">Count of sort orders to be included in the new structure.</span></span>
    
<span data-ttu-id="66e34-113">__名称_</span><span class="sxs-lookup"><span data-stu-id="66e34-113">__name_</span></span>
  
> <span data-ttu-id="66e34-114">新结构的的名称。</span><span class="sxs-lookup"><span data-stu-id="66e34-114">Name for the new structure.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="66e34-115">说明</span><span class="sxs-lookup"><span data-stu-id="66e34-115">Remarks</span></span>

<span data-ttu-id="66e34-116">使用**SizedSSortOrderSet**宏来创建使用显式边界设置排序顺序。</span><span class="sxs-lookup"><span data-stu-id="66e34-116">Use the **SizedSSortOrderSet** macro to create a sort order set with explicit bounds.</span></span> 
  
<span data-ttu-id="66e34-117">若要使用新结构的结果从**SizedSSortOrderSet**宏作为指针指向**SSortOrderSet**结构，执行下列转换：</span><span class="sxs-lookup"><span data-stu-id="66e34-117">To use the new structure that results from the **SizedSSortOrderSet** macro as a pointer to an **SSortOrderSet** structure, perform the following cast:</span></span> 
  
```cpp
lpSSortOrderSet = (LPSSortOrderSet) &SizedSSortOrderSet;

```

## <a name="see-also"></a><span data-ttu-id="66e34-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="66e34-118">See also</span></span>

- [<span data-ttu-id="66e34-119">SSortOrderSet</span><span class="sxs-lookup"><span data-stu-id="66e34-119">SSortOrderSet</span></span>](ssortorderset.md)
- [<span data-ttu-id="66e34-120">与结构相关的宏</span><span class="sxs-lookup"><span data-stu-id="66e34-120">Macros Related to Structures</span></span>](macros-related-to-structures.md)

